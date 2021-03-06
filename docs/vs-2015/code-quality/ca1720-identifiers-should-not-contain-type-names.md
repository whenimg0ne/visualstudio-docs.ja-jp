---
title: 'Ca 1720: 識別子が型名含めることはできません |Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- CA1720
- IdentifiersShouldNotContainTypeNames
helpviewer_keywords:
- IdentifiersShouldNotContainTypeNames
- CA1720
ms.assetid: c95ee48f-f23a-45f0-ac9e-a3c1ecfabdea
caps.latest.revision: 17
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 60b7bbb0852544f7e2c5267daf0d9fdf1e1214cb
ms.sourcegitcommit: 99d097d82ee4f9eff6f588e5ebb6b17d8f724b04
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/24/2018
ms.locfileid: "47549262"
---
# <a name="ca1720-identifiers-should-not-contain-type-names"></a>CA1720: 識別子には型名を含めないでください
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

このトピックの最新バージョンをご覧[ca 1720: 識別子は型名を含めることはできません](https://docs.microsoft.com/visualstudio/code-quality/ca1720-identifiers-should-not-contain-type-names)します。

|||
|-|-|
|TypeName|IdentifiersShouldNotContainTypeNames|
|CheckId|CA1720|
|カテゴリ|Microsoft.Naming|
|互換性に影響する変更点|あり|

## <a name="cause"></a>原因
 外部から参照できるメンバーのパラメーターの名前には、データ型の名前が含まれています。

 - または -

 外部から参照できるメンバーの名前には、言語固有のデータ型の名前が含まれています。

## <a name="rule-description"></a>規則の説明
 パラメーターおよびメンバーの名前は、その意味は、開発ツールが提供する予定されている、型を説明するよりもを通信に使用される向上します。 データ型の名前を使用する場合は、メンバーの名前は、言語固有ではなく、言語に依存しない名前を使用します。 など、c# の型名 'int' ではなく、言語に依存しないデータ型の名前、Int32 を使用します。

 各トークンのパラメーターまたはメンバーの名前は、大文字と小文字で、次の言語に固有のデータ型名に対してチェックされます。

-   Bool

-   WChar

-   Int8

-   UInt8

-   Short

-   UShort

-   Int

-   UInt

-   整数型

-   UInteger

-   Long

-   ULong

-   符号なし

-   符号付き

-   Float

-   float32

-   float64

 さらに、パラメーターの名前もチェックされます、次の言語に依存しないデータ型名に対して大文字と小文字。

-   Object

-   obj

-   ブール型

-   Char

-   String

-   SByte

-   Byte

-   UByte

-   Int16

-   UInt16

-   Int32

-   UInt32

-   Int64

-   UInt64

-   IntPtr

-   ptr

-   ポインター

-   UInptr

-   UPtr

-   UPointer

-   Single

-   倍精度浮動小数点型

-   Decimal (10 進数型)

-   GUID

## <a name="how-to-fix-violations"></a>違反の修正方法
 **場合は、パラメーターに対して起動します。**

 パラメーターの名前のデータ型識別子をその意味をより詳しく説明している用語をまたは 'value' などの汎用的な用語のいずれかに置き換えます。

 **メンバーに対して起動: 場合**

 その意味、言語に依存しないに相当する、または 'value' などの汎用的な用語をより詳しく説明している用語を言語に固有のデータ型識別子、メンバーの名前に置き換えます。

## <a name="when-to-suppress-warnings"></a>警告を抑制する状況
 型に基づくパラメーターおよびメンバーの名前は、適切な可能性があります。 ただし、新規の開発、されていないシナリオが発生する、この規則による警告を抑制する必要があります。 ライブラリが以前のリリースでは、この規則による警告を抑制する必要があります。

## <a name="related-rules"></a>関連規則
 [CA1709: 識別子では、大文字と小文字が正しく区別されなければなりません](../code-quality/ca1709-identifiers-should-be-cased-correctly.md)

 [CA1708: 識別子は、大文字と小文字の区別以外にも相違していなければなりません](../code-quality/ca1708-identifiers-should-differ-by-more-than-case.md)

 [CA1707: 識別子はアンダースコアを含むことはできません](../code-quality/ca1707-identifiers-should-not-contain-underscores.md)

 [CA1719: パラメーター名はメンバー名と同一にすることはできません](../code-quality/ca1719-parameter-names-should-not-match-member-names.md)



