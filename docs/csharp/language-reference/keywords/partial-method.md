---
title: 'Método partial: Referencia de C#'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- partialmethod_CSharpKeyword
helpviewer_keywords:
- partial methods [C#]
ms.assetid: 43f40242-17e0-4452-8573-090503ad3137
ms.openlocfilehash: 742d6ca744ac723179718f1400e600411712dd40
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/11/2018
ms.locfileid: "53238291"
---
# <a name="partial-method-c-reference"></a>partial (Método) (Referencia de C#)

Un método parcial tiene su signatura definida en una parte de un tipo parcial y su implementación definida en otra parte del tipo. Los métodos parciales permiten a los diseñadores de clases proporcionar enlaces de método, similares a los controladores de eventos, que los desarrolladores pueden decidir implementar o no. Si el desarrollador no proporciona una implementación, el compilador quita la signatura en tiempo de compilación. Se aplican las siguientes condiciones a los métodos parciales:

- Las signaturas de ambas partes del tipo parcial deben coincidir.

- El método debe devolver el valor void.

- No se permiten modificadores de acceso. Los métodos parciales son privados implícitamente.

En el ejemplo siguiente se muestra un método parcial definido en dos partes de una clase parcial:

[!code-csharp[csrefKeywordsContextual#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsContextual/CS/csrefKeywordsContextual.cs#9)]

Para más información, vea [Clases y métodos parciales](../../programming-guide/classes-and-structs/partial-classes-and-methods.md).

## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [partial (tipo)](partial-type.md)