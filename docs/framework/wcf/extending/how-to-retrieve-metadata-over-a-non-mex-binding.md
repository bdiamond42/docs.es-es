---
title: Procedimiento Recuperar metadatos mediante un enlace que no sea - MEX
ms.date: 03/30/2017
ms.assetid: 2292e124-81b2-4317-b881-ce9c1ec66ecb
ms.openlocfilehash: ac0a7d979e6b86933c4acd88b1a2fa11ba5bc991
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54689560"
---
# <a name="how-to-retrieve-metadata-over-a-non-mex-binding"></a>Procedimiento Recuperar metadatos mediante un enlace que no sea - MEX
En este tema se describe cómo recuperar metadatos de un punto de conexión MEX mediante un enlace que no sea MEX. El código en este ejemplo se basa en el [extremo de metadatos personalizada Secure](../../../../docs/framework/wcf/samples/custom-secure-metadata-endpoint.md) ejemplo.  
  
### <a name="to-retrieve-metadata-over-a-non-mex-binding"></a>Para recuperar metadatos mediante un enlace que no sea MEX  
  
1.  Determine el enlace utilizado por el punto de conexión MEX. Para los servicios de Windows Communication Foundation (WCF), puede determinar el enlace MEX obteniendo acceso al archivo de configuración del servicio. En este caso, el enlace de MEX se define en la configuración de servicio siguiente.  
  
    ```xml  
    <services>  
        <service name="Microsoft.ServiceModel.Samples.CalculatorService"  
                behaviorConfiguration="CalculatorServiceBehavior">  
         <!-- Use the base address provided by the host. -->  
         <endpoint address=""  
           binding="wsHttpBinding"  
           bindingConfiguration="Binding2"  
           contract="Microsoft.ServiceModel.Samples.ICalculator" />  
         <endpoint address="mex"  
           binding="wsHttpBinding"  
           bindingConfiguration="Binding1"  
           contract="IMetadataExchange" />  
         </service>  
     </services>  
     <bindings>  
       <wsHttpBinding>  
         <binding name="Binding1">  
           <security mode="Message">  
             <message clientCredentialType="Certificate" />  
           </security>  
         </binding>  
         <binding name="Binding2">  
           <reliableSession inactivityTimeout="00:01:00" enabled="true" />  
           <security mode="Message">  
             <message clientCredentialType="Certificate" />  
           </security>  
         </binding>  
       </wsHttpBinding>  
     </bindings>  
    ```  
  
2.  En el archivo de configuración del cliente, configure el mismo enlace personalizado. Aquí, el cliente también define un comportamiento `clientCredentials` para proporcionar un certificado que utilizar para autenticarse en el servicio al solicitar metadatos del punto de conexión MEX. Al utilizar Svcutil.exe para solicitar metadatos mediante un enlace personalizado, debería agregar la configuración del punto de conexión MEX al archivo de configuración para Svcutil.exe (Svcutil.exe.config) y el nombre de la configuración del punto de conexión debería coincidir con el esquema del URI de la dirección del punto de conexión MEX, tal y como se muestra en el código siguiente:  
  
    ```xml  
    <system.serviceModel>  
      <client>  
        <endpoint name="http"  
                  binding="wsHttpBinding"  
                  bindingConfiguration="Binding1"  
                  behaviorConfiguration="ClientCertificateBehavior"  
                  contract="IMetadataExchange" />  
      </client>  
      <bindings>  
        <wsHttpBinding>  
          <binding name="Binding1">  
            <security mode="Message">  
              <message clientCredentialType="Certificate"/>  
            </security>  
          </binding>  
        </wsHttpBinding>  
      </bindings>  
      <behaviors>  
        <endpointBehaviors>  
          <behavior name="ClientCertificateBehavior">  
            <clientCredentials>  
              <clientCertificate findValue="client.com" storeLocation="CurrentUser" storeName="My" x509FindType="FindBySubjectName" />  
              <serviceCertificate>  
                <authentication certificateValidationMode="PeerOrChainTrust" />  
              </serviceCertificate>  
            </clientCredentials>  
          </behavior>  
        </endpointBehaviors>  
      </behaviors>    
    </system.serviceModel>  
    ```  
  
3.  Cree un `MetadataExchangeClient` y llame a `GetMetadata`: Hay dos maneras de hacerlo: puede especificar el enlace personalizado mediante configuración o puede especificarlo mediante código, tal y como se muestra en el ejemplo siguiente:  
  
    ```  
    // The custom binding is specified in configuration.  
    EndpointAddress mexAddress = new EndpointAddress("http://localhost:8000/ServiceModelSamples/Service/mex");  
  
    MetadataExchangeClient mexClient = new MetadataExchangeClient("http");  
    mexClient.ResolveMetadataReferences = true;  
    MetadataSet mexSet = mexClient.GetMetadata(mexAddress);  
  
    // The custom binding is specified in code.  
    // Specify the Metadata Exchange binding and its security mode.  
    WSHttpBinding mexBinding = new WSHttpBinding(SecurityMode.Message);  
    mexBinding.Security.Message.ClientCredentialType = MessageCredentialType.Certificate;  
  
    // Create a MetadataExchangeClient and set the certificate details.  
    MetadataExchangeClient mexClient = new MetadataExchangeClient(mexBinding);  
    mexClient.SoapCredentials.ClientCertificate.SetCertificate(  
        StoreLocation.CurrentUser, StoreName.My,  
        X509FindType.FindBySubjectName, "client.com");  
    mexClient.SoapCredentials.ServiceCertificate.Authentication.  
        CertificateValidationMode =  
        X509CertificateValidationMode.PeerOrChainTrust;  
    mexClient.SoapCredentials.ServiceCertificate.SetDefaultCertificate(  
        StoreLocation.CurrentUser, StoreName.TrustedPeople,  
        X509FindType.FindBySubjectName, "localhost");  
    MetadataExchangeClient mexClient2 = new MetadataExchangeClient(customBinding);  
    mexClient2.ResolveMetadataReferences = true;  
    MetadataSet mexSet2 = mexClient2.GetMetadata(mexAddress);  
    ```  
  
4.  Cree una clase `WsdlImporter` y llame a `ImportAllEndpoints`, como se muestra en el código siguiente.  
  
    ```  
    WsdlImporter importer = new WsdlImporter(mexSet);  
    ServiceEndpointCollection endpoints = importer.ImportAllEndpoints();  
    ```  
  
5.  En este punto, tiene una colección de puntos de conexión de servicio. Para obtener más información sobre la importación de metadatos, vea [Cómo: Importar los metadatos en los puntos de conexión de servicio](../../../../docs/framework/wcf/feature-details/how-to-import-metadata-into-service-endpoints.md).  
  
## <a name="see-also"></a>Vea también
- [Metadatos](../../../../docs/framework/wcf/feature-details/metadata.md)
