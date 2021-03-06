---
title: ': Ca 1020 名前空間をいくつかの種類 |Microsoft Docs'
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
- CA1020
- AvoidNamespacesWithFewTypes
helpviewer_keywords:
- CA1020
- AvoidNamespacesWithFewTypes
ms.assetid: 9cb272f6-a3ff-45af-b35d-70dea620b074
caps.latest.revision: 19
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: b3a7f1c0b6cdfbf96542d9edc76596295f2d695a
ms.sourcegitcommit: 99d097d82ee4f9eff6f588e5ebb6b17d8f724b04
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/24/2018
ms.locfileid: "47549264"
---
# <a name="ca1020-avoid-namespaces-with-few-types"></a>CA1020: 型をほとんど含まない名前空間を使用しません
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

このトピックの最新バージョンをご覧[CA1020: いくつかの種類と名前空間を避けるため](https://docs.microsoft.com/visualstudio/code-quality/ca1020-avoid-namespaces-with-few-types)します。

|||
|-|-|
|TypeName|AvoidNamespacesWithFewTypes|
|CheckId|CA1020|
|カテゴリ|Microsoft.Design|
|互換性に影響する変更点|あり|

## <a name="cause"></a>原因
 グローバル名前空間以外の名前空間には、5 未満の型が含まれています。

## <a name="rule-description"></a>規則の説明
 各名前空間には、論理的な少ない名前空間で型を配置する正当な理由が存在することを確認します。 名前空間には、ほとんどのシナリオで同時に使用される型を含める必要があります。 自分のアプリケーションが相互に排他的な場合は、個別の名前空間で型を配置する必要があります。 たとえば、<xref:System.Web.UI>名前空間には、Web アプリケーションで使用される型が含まれています。 および<xref:System.Windows.Forms>名前空間で使用される型が含まれています[!INCLUDE[TLA#tla_mswin](../includes/tlasharptla-mswin-md.md)]-ベースのアプリケーション。 両方の名前空間では、ユーザー インターフェイスの側面を制御する型がある、でも、これらの型では、同じアプリケーションで使用する設計されていません。 そのため、個別の名前空間内にあります。 注意名前空間の組織も役に立ちます機能の探索可能性が増えるためです。 名前空間の階層を確認するには、ライブラリのコンシューマーは、機能を実装する型を特定できる必要があります。

> [!NOTE]
>  このガイドラインに準拠する他の名前空間には、デザイン時の型とアクセス許可しないマージする必要があります。 メインの名前空間の下に独自の名前空間に属しているこれらの型と名前空間の末尾に`.Design`と`.Permissions`、それぞれします。

## <a name="how-to-fix-violations"></a>違反の修正方法
 この規則違反を修正するのには、単一の名前空間にはいくつかの種類を含む名前空間を結合するしてみてください。

## <a name="when-to-suppress-warnings"></a>警告を抑制する状況
 名前空間には、他の名前空間の型で使用される型が含まれていない場合、このルールから警告を抑制しても安全です。



