---
title: "ICorDebugFunction::GetLocalVarSigToken (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugFunction.GetLocalVarSigToken
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugFunction::GetLocalVarSigToken
helpviewer_keywords:
- ICorDebugFunction::GetLocalVarSigToken method [.NET Framework debugging]
- GetLocalVarSigToken method [.NET Framework debugging]
ms.assetid: 31e53494-bcc9-4981-91a4-f7e0f02cad48
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 67cdb14577ca44f44685807fda4f308b50462002
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugfunctiongetlocalvarsigtoken-method"></a><span data-ttu-id="205db-102">ICorDebugFunction::GetLocalVarSigToken (Método)</span><span class="sxs-lookup"><span data-stu-id="205db-102">ICorDebugFunction::GetLocalVarSigToken Method</span></span>
<span data-ttu-id="205db-103">Obtiene los metadatos del token para la firma de variable local de la función que está representada por esta instancia ICorDebugFunction.</span><span class="sxs-lookup"><span data-stu-id="205db-103">Gets the metadata token for the local variable signature of the function that is represented by this ICorDebugFunction instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="205db-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="205db-104">Syntax</span></span>  
  
```  
HRESULT GetLocalVarSigToken (  
    [out] mdSignature *pmdSig  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="205db-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="205db-105">Parameters</span></span>  
 `pmdSig`  
 <span data-ttu-id="205db-106">[out] Un puntero a la `mdSignature` símbolo (token) de la firma de variable local de esta función, o `mdSignatureNil`, si esta función no tiene variables locales.</span><span class="sxs-lookup"><span data-stu-id="205db-106">[out] A pointer to the `mdSignature` token for the local variable signature of this function, or `mdSignatureNil`, if this function has no local variables.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="205db-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="205db-107">Requirements</span></span>  
 <span data-ttu-id="205db-108">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="205db-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="205db-109">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="205db-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="205db-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="205db-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="205db-111">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="205db-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>