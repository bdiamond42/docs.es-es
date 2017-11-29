---
title: "ICLRStrongName::StrongNameCompareAssemblies (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRStrongName.StrongNameCompareAssemblies
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRStrongName::StrongNameCompareAssemblies
helpviewer_keywords:
- ICLRStrongName::StrongNameCompareAssemblies method [.NET Framework hosting]
- StrongNameCompareAssemblies method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: b1fb356c-72cf-4aa4-8376-f291a6d97c01
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ab69a0d0bb5894c2393e240b4f89b9a16dd98939
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="iclrstrongnamestrongnamecompareassemblies-method"></a><span data-ttu-id="d4b45-102">ICLRStrongName::StrongNameCompareAssemblies (Método)</span><span class="sxs-lookup"><span data-stu-id="d4b45-102">ICLRStrongName::StrongNameCompareAssemblies Method</span></span>
<span data-ttu-id="d4b45-103">Determina si dos ensamblados difieren solo en sus firmas de nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="d4b45-103">Determines whether two assemblies differ only by their strong name signatures.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d4b45-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d4b45-104">Syntax</span></span>  
  
```  
HRESULT StrongNameCompareAssemblies (  
    [in]  LPCWSTR   wszAssembly1,  
    [in]  LPCWSTR   wszAssembly2,  
    [out] DWORD     *pdwResult  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d4b45-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d4b45-105">Parameters</span></span>  
 `wszAssembly1`  
 <span data-ttu-id="d4b45-106">[in] La ruta de acceso al primer ensamblado.</span><span class="sxs-lookup"><span data-stu-id="d4b45-106">[in] The path to the first assembly.</span></span>  
  
 `wszAssembly2`  
 <span data-ttu-id="d4b45-107">[in] La ruta de acceso al segundo ensamblado.</span><span class="sxs-lookup"><span data-stu-id="d4b45-107">[in] The path to the second assembly.</span></span>  
  
 `pdwResult`  
 <span data-ttu-id="d4b45-108">[out] Uno de los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="d4b45-108">[out] One of the following values:</span></span>  
  
-   <span data-ttu-id="d4b45-109">`SN_CMP_DIFFERENT`(0): Especifica que los ensamblados contienen datos distintos.</span><span class="sxs-lookup"><span data-stu-id="d4b45-109">`SN_CMP_DIFFERENT` (0) - Specifies that the assemblies contain different data.</span></span>  
  
-   <span data-ttu-id="d4b45-110">`SN_CMP_IDENTICAL`(1): Especifica que los ensamblados son exactamente iguales, incluidas sus firmas y la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="d4b45-110">`SN_CMP_IDENTICAL` (1) - Specifies that the assemblies are exactly the same, including their signatures and checksum.</span></span>  
  
-   <span data-ttu-id="d4b45-111">`SN_CMP_SIGONLY`(2): Especifica si los ensamblados difieren solo en la firma y la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="d4b45-111">`SN_CMP_SIGONLY` (2) - Specifies that the assemblies differ only by signature and checksum.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d4b45-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="d4b45-112">Return Value</span></span>  
 <span data-ttu-id="d4b45-113">`S_OK`Si el método se completó correctamente; en caso contrario, un valor HRESULT que indica un error (vea [valores HRESULT comunes](http://go.microsoft.com/fwlink/?LinkId=213878) para obtener una lista).</span><span class="sxs-lookup"><span data-stu-id="d4b45-113">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](http://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d4b45-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d4b45-114">Requirements</span></span>  
 <span data-ttu-id="d4b45-115">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d4b45-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d4b45-116">**Encabezado:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="d4b45-116">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="d4b45-117">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d4b45-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d4b45-118">**Versiones de .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d4b45-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d4b45-119">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d4b45-119">Remarks</span></span>  
 <span data-ttu-id="d4b45-120">La firma de nombre seguro de un ensamblado consta del nombre de texto, versión, referencia cultural y token de clave pública del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="d4b45-120">The strong name signature of an assembly consists of the assembly's text name, version, culture, and public key token.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4b45-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="d4b45-121">See Also</span></span>  
 [<span data-ttu-id="d4b45-122">ICLRStrongName (interfaz)</span><span class="sxs-lookup"><span data-stu-id="d4b45-122">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)