---
title: ワークフロー デザイナー - Throw アクティビティ デザイナー
ms.date: 11/04/2016
ms.topic: reference
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
f1_keywords:
- System.Activities.Statements.Throw.UI
ms.assetid: 5e97c947-be39-4a1f-af04-000e2e09528a
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 71cf547a1ea3599de8926e40ca5a43f3bdea0f71
ms.sourcegitcommit: 30f653d9625ba763f6b58f02fb74a24204d064ea
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/25/2018
ms.locfileid: "36758322"
---
# <a name="throw-activity-designer"></a>Throw アクティビティ デザイナー

**スロー**作成および構成するアクティビティ デザイナーが使用される、<xref:System.Activities.Statements.Throw>アクティビティ。

## <a name="the-throw-activity"></a>Throw アクティビティ

<xref:System.Activities.Statements.Throw> アクティビティによって例外がスローされます。

### <a name="using-the-throw-activity-designer"></a>Throw アクティビティ デザイナーの使用

アクセス、**スロー**内のアクティビティ デザイナー、**エラー処理**のカテゴリ、**ツールボックス**します。

**スロー**からアクティビティ デザイナーをドラッグすることができます、**ツールボックス**どこにも、アクティビティを通常配置など内に、ワークフロー デザイナー画面にドロップし、<xref:System.Activities.Statements.Sequence>します。 これを作成、 <xref:System.Activities.Statements.Throw> 、既定値は、アクティビティ**DisplayName** Throw の。 <xref:System.Activities.Activity.DisplayName%2A>のヘッダーに値を編集できる、**スロー**アクティビティ デザイナーまたは、 **DisplayName**プロパティ グリッドのボックスです。 この <xref:System.Activities.Statements.Throw.Exception%2A> プロパティは、プロパティ グリッドで編集する必要があります。

### <a name="the-throw-properties"></a>Throw プロパティ

次の表に、<xref:System.Activities.Statements.Throw> のプロパティと、デザイナーでのその使用方法を示します。

|プロパティ名|必須|使用方法|
|-------------------|--------------|-----------|
|<xref:System.Activities.Activity.DisplayName%2A>|False|<xref:System.Activities.Statements.Throw> アクティビティの表示名を指定します (省略可能)。 既定値は Throw です。|
|<xref:System.Activities.Statements.Throw.Exception%2A>|True|スローされる例外。 この例外は、<xref:System.Exception> から派生していることが必要です。 例外を指定するには、プロパティ グリッドで Visual Basic の式を入力します。|

## <a name="see-also"></a>関連項目

- [コレクション](../workflow-designer/collection-activity-designers.md)
- [再スローします。](../workflow-designer/rethrow-activity-designer.md)
- [Throw アクティビティ デザイナー](../workflow-designer/throw-activity-designer.md)
- [TryCatch](../workflow-designer/trycatch-activity-designer.md)