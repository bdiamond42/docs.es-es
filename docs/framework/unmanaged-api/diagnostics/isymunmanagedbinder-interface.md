---
title: ISymUnmanagedBinder (Interfaz)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedBinder
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedBinder
helpviewer_keywords: ISymUnmanagedBinder interface [.NET Framework debugging]
ms.assetid: b22fbe19-b30f-4696-8175-e6b91da9edab
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 00b0b5ee330a606ae7417185a804f3d37ab6664a
ms.sourcegitcommit: 5177d6ae2e9baf026f07ee0631556700a5a193f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="isymunmanagedbinder-interface"></a>ISymUnmanagedBinder (Interfaz)
Representa un enlazador de símbolos de código no administrado.  
  
> [!IMPORTANT]
>  Es un riesgo de seguridad para abrir un archivo de programa (PDB) de la base de datos desde un origen de confianza.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[GetReaderForFile (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-getreaderforfile-method.md)|A partir de una interfaz de metadatos y un nombre de archivo, devuelve el valor correcto [ISymUnmanagedReader](isymunmanagedreader-interface.md) estructura que va a leer los símbolos de depuración asociados al módulo.|  
|[GetReaderFromStream (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-getreaderfromstream-method.md)|A partir de una interfaz de metadatos y una secuencia que contiene el almacén de símbolos, devuelve el valor correcto [ISymUnmanagedReader](isymunmanagedreader-interface.md) símbolos estructura que va a leer la depuración desde el almacén de símbolos especificado.|  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Vea también  
 [Interfaces de almacén de símbolos de diagnósticos](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)  
 [ISymUnmanagedBinder2 (interfaz)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-interface.md)  
 [ISymUnmanagedBinder3 (interfaz)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-interface.md)