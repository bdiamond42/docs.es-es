---
title: 205 - OperationInvoked
ms.date: 03/30/2017
ms.assetid: 9c8d6c90-dfa5-4ae0-a589-96679a8fb3ba
ms.openlocfilehash: e95b6923d21307b2ef68d4a5369b3cee86540239
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33458354"
---
# <a name="205---operationinvoked"></a>205 - OperationInvoked
## <a name="properties"></a>Propiedades  
  
|||  
|-|-|  
|Id.|205|  
|Palabras clave|Troubleshooting, ServiceModel|  
|Nivel|Información|  
|Canal|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>Descripción  
 Este evento se emite justo antes de que el `OperationInvoker` predeterminado del modelo de servicio inicie una llamada a un método.  
  
## <a name="message"></a>Mensaje  
 Un OperationInvoker invocó el método '%1'. Información del autor de la llamada: '%2'.  
  
## <a name="details"></a>Detalles  
  
|Nombre del elemento de datos|Tipo del elemento de datos|Descripción|  
|--------------------|--------------------|-----------------|  
|Nombre del método|`xs:string`|El nombre de CLR del método invocado por `OperationInvoker`.|  
|Información del llamador|`xs:string`|La dirección IP y el número de puerto del cliente en el formato 'IPAddress:PortNumber'. Los dos valores se recuperan de la propiedad de mensaje 'System.ServiceModel.Channels.RemoteEndpointMessageProperty' en el contexto de la operación. Tenga en cuenta que, para los enlaces que no son de TCP, este valor es `null`.|  
|HostReference|`xs:string`|En el caso de los servicios hospedados en web, este campo identifica de manera única el servicio en la jerarquía web. El formato se define como ' ruta de acceso Virtual de sitio Web de nombre aplicación&#124;ruta de acceso Virtual del servicio&#124;ServiceName'. Ejemplo: ' predeterminado sitio Web/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.|  
|AppDomain|`xs:string`|La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.|
