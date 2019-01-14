---
title: Método SqlStreamChars.Read (Char [], Int32, Int32) (System.Data.SqlTypes)
author: douglaslMS
ms.author: douglasl
ms.date: 12/20/2018
ms.technology:
- dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlStreamChars.Read
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: ce89e5f757034b79d5a60a1abbd49fdb2fdf3f06
ms.sourcegitcommit: a36cfc9dbbfc04bd88971f96e8a3f8e283c15d42
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/11/2019
ms.locfileid: "54222121"
---
# <a name="sqlstreamcharsreadchar-int32-int32-method"></a><span data-ttu-id="23ee2-102">Método SqlStreamChars.Read (Char [], Int32, Int32)</span><span class="sxs-lookup"><span data-stu-id="23ee2-102">SqlStreamChars.Read(Char[], Int32, Int32) Method</span></span>

<span data-ttu-id="23ee2-103">Cuando se invalida en una clase derivada, lee el siguiente conjunto de caracteres del flujo de entrada.</span><span class="sxs-lookup"><span data-stu-id="23ee2-103">When overridden in a derived class, reads the next set of characters from the input stream.</span></span> <span data-ttu-id="23ee2-104">El ensamblado que contiene este método tiene una relación de confianza con SQLAccess.dll.</span><span class="sxs-lookup"><span data-stu-id="23ee2-104">The assembly that contains this method has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="23ee2-105">Está pensado para su uso con SQL Server.</span><span class="sxs-lookup"><span data-stu-id="23ee2-105">It's intended for use by SQL Server.</span></span> <span data-ttu-id="23ee2-106">Para otras bases de datos, utilice el mecanismo de hospedaje proporcionado por esa base de datos.</span><span class="sxs-lookup"><span data-stu-id="23ee2-106">For other databases, use the hosting mechanism provided by that database.</span></span>

```csharp
public abstract int Read (char[] buffer, int offset, int count);
```

## <a name="parameters"></a><span data-ttu-id="23ee2-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="23ee2-107">Parameters</span></span>

`buffer`\
<span data-ttu-id="23ee2-108">Una matriz de caracteres para leer.</span><span class="sxs-lookup"><span data-stu-id="23ee2-108">A char array to read.</span></span>

`offset`\
<span data-ttu-id="23ee2-109">Un desplazamiento con respecto al origen.</span><span class="sxs-lookup"><span data-stu-id="23ee2-109">An offset relative to origin.</span></span>

`count`\
<span data-ttu-id="23ee2-110">El número de caracteres que leer en la secuencia actual.</span><span class="sxs-lookup"><span data-stu-id="23ee2-110">The number of characters to be read from the current stream.</span></span>

## <a name="returns"></a><span data-ttu-id="23ee2-111">Valores devueltos</span><span class="sxs-lookup"><span data-stu-id="23ee2-111">Returns</span></span>

<xref:System.Int32>\
<span data-ttu-id="23ee2-112">Número total de caracteres leídos en el búfer.</span><span class="sxs-lookup"><span data-stu-id="23ee2-112">The total number of characters read into the buffer.</span></span>

## <a name="remarks"></a><span data-ttu-id="23ee2-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="23ee2-113">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="23ee2-114">El `SqlStreamChars.Read` método es privado y no está pensado para usarse directamente en el código.</span><span class="sxs-lookup"><span data-stu-id="23ee2-114">The `SqlStreamChars.Read` method is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="23ee2-115">Microsoft no admite el uso de este campo en una aplicación de producción bajo ninguna circunstancia.</span><span class="sxs-lookup"><span data-stu-id="23ee2-115">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="23ee2-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="23ee2-116">Requirements</span></span>

<span data-ttu-id="23ee2-117">**Espacio de nombres:** <xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="23ee2-117">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="23ee2-118">**Ensamblado:** System.Data (en System.Data.dll)</span><span class="sxs-lookup"><span data-stu-id="23ee2-118">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="23ee2-119">**Versiones de .NET framework:** Disponible desde la versión 2.0.</span><span class="sxs-lookup"><span data-stu-id="23ee2-119">**.NET Framework versions:** Available since 2.0.</span></span>