﻿---
title: '方法: マネージ コードの自動コード分析を有効/無効にする'
ms.date: 09/28/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- dotnet
ms.openlocfilehash: 3113143b07ccb6f765cd0cf1735b34be6e952c72
ms.sourcegitcommit: 6672a1e9d135d7e5cca3cceea07c6fe5a0871475
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/28/2018
ms.locfileid: "47443546"
---
# <a name="how-to-enable-and-disable-automatic-code-analysis-for-managed-code"></a>方法: マネージ コードの自動コード分析を有効/無効にします

マネージ コード プロジェクトのビルド後に実行されるコード分析を構成することができます。 別のコードに各ビルド構成に対して分析プロパティを設定などのデバッグおよびリリースします。

## <a name="to-enable-or-disable-automatic-code-analysis"></a>自動コード分析を有効または無効にするには

1. **ソリューション エクスプ ローラー** で、プロジェクトを右クリックし、**プロパティ**を選択します。

1. プロジェクトのプロパティ ダイアログ ボックスで、選択、**コード分析**タブ。

1. **プラットフォーム** の **構成およびターゲット プラットフォーム** でビルドの種類を指定します。

1. 自動コード分析を有効または無効にするには、**ビルドに対するコード分析を有効にする**のチェック ボックスをオンまたはオフします。

> [!NOTE]
> **ビルドに対するコード分析を有効にする** チェック ボックスでは、静的コード分析のみに影響します。 影響しない[Roslyn コード アナライザー](roslyn-analyzers-overview.md)、NuGet パッケージとしてインストールした場合、ビルドで常に実行します。 アナライザー エラーをクリアする場合、**エラー一覧**を選択して、現在のすべての違反を抑制する**分析** > **コード分析を実行し、アクティブな抑制問題**メニュー バーでします。 詳細については、次を参照してください。[違反を抑制する](use-roslyn-analyzers.md#suppress-violations)します。
