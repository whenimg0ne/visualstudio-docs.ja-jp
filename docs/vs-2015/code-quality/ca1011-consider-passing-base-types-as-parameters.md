---
title: 'Ca 1011: 基本型をパラメーターとして渡すことを検討してください |Microsoft Docs'
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
- ConsiderPassingBaseTypesAsParameters
- CA1011
helpviewer_keywords:
- CA1011
- ConsiderPassingBaseTypesAsParameters
ms.assetid: ce1e1241-dcf4-419b-9363-1d5bc4989279
caps.latest.revision: 20
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: a2ddf1e4f1edc319fdc5744878d4f962ce5b46bb
ms.sourcegitcommit: 99d097d82ee4f9eff6f588e5ebb6b17d8f724b04
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/24/2018
ms.locfileid: "47592263"
---
# <a name="ca1011-consider-passing-base-types-as-parameters"></a>CA1011: 基本型をパラメーターとして渡すことを考慮します
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

このトピックの最新バージョンをご覧[ca 1011: 基本型をパラメーターとして渡すことを検討してください](https://docs.microsoft.com/visualstudio/code-quality/ca1011-consider-passing-base-types-as-parameters)します。

|||
|-|-|
|TypeName|ConsiderPassingBaseTypesAsParameters|
|CheckId|CA1011|
|カテゴリ|Microsoft.Design|
|互換性に影響する変更点|あり|

## <a name="cause"></a>原因
 メソッドの宣言には、派生型では、仮パラメーターが含まれていて、メソッドは、パラメーターの基本型のメンバーだけを呼び出します。

## <a name="rule-description"></a>規則の説明
 メソッドの宣言で基本型をパラメーターとして指定すると、その基本型から派生した型は、メソッドに対応する引数として渡すことができます。 メソッド本体内で、引数を使用する場合に実行される特定のメソッドは、引数の型に依存します。 派生型によって提供される追加機能が必要ない場合、基本データ型の使用により、メソッドのより広範囲に利用します。

## <a name="how-to-fix-violations"></a>違反の修正方法
 この規則違反を解決するには、その基本型にパラメーターの型を変更します。

## <a name="when-to-suppress-warnings"></a>警告を抑制する状況
 このルールから警告を抑制しても安全です。

-   メソッドが派生型によって提供される特定の機能が必要な場合

     \- または -

-   派生型のみ、またはより強い派生型では、適用するのには、メソッドに渡されます。

 このような場合は、コードは、堅牢になります、コンパイラとランタイムによって提供される厳密な型チェックのためです。

## <a name="example"></a>例
 次の例では、メソッド、`ManipulateFileStream`でのみ使用できる、<xref:System.IO.FileStream>オブジェクトで、この規則に違反します。 2 番目のメソッド`ManipulateAnyStream`、置き換えることで、ルールを満たす、<xref:System.IO.FileStream>パラメーターを使用して、<xref:System.IO.Stream>します。

 [!code-cpp[FxCop.Design.ConsiderPassingBaseTypes#1](../snippets/cpp/VS_Snippets_CodeAnalysis/FxCop.Design.ConsiderPassingBaseTypes/cpp/FxCop.Design.ConsiderPassingBaseTypes.cpp#1)]
 [!code-csharp[FxCop.Design.ConsiderPassingBaseTypes#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Design.ConsiderPassingBaseTypes/cs/FxCop.Design.ConsiderPassingBaseTypes.cs#1)]
 [!code-vb[FxCop.Design.ConsiderPassingBaseTypes#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Design.ConsiderPassingBaseTypes/vb/FxCop.Design.ConsiderPassingBaseTypes.vb#1)]

## <a name="related-rules"></a>関連規則
 [CA1059: メンバーは特定の具象型を公開できません](../code-quality/ca1059-members-should-not-expose-certain-concrete-types.md)



