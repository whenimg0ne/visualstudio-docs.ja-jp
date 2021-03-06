---
title: フォントと色の概要 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], font and color
- font and color control [Visual Studio SDK], editors
ms.assetid: 2203e4e7-8b7f-44ec-8884-6ff718d4f278
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 75db379b6a94d0c40fdbc1aa3946315f5fbc4edc
ms.sourcegitcommit: 1c2ed640512ba613b3bbbc9ce348e28be6ca3e45
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/03/2018
ms.locfileid: "39498471"
---
# <a name="font-and-color-overview"></a>フォントと色の概要
このトピックでは説明のテキストのフォントと色の設定、[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]統合開発環境 (IDE) です。 カテゴリとアイテムの表示の概念も導入されていて、Vspackage とコア エディターのテキスト属性を使用する方法について説明します。  
  
## <a name="the-fonts-and-colors-property-page"></a>フォントおよび色のプロパティ ページ  
 表示されるテキストの属性を管理することができます、[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]を通じて統合開発環境 (IDE)、**フォントおよび色**プロパティ ページ。 検索する、**フォントおよび色**プロパティ ページで、**ツール** メニューのをクリックして**オプション**します。 展開**環境**、 をクリックし、**フォントおよび色**します。  
  
## <a name="categories-and-display-items"></a>カテゴリとアイテムを表示  
 フォントおよび色で構成された**カテゴリ**と**表示項目**します。  
  
-   A**カテゴリ**論理または機能の数のコンテナー**表示項目**します。  
  
     一連の**カテゴリ**では、**設定の表示**のドロップダウン ボックス、**フォントおよび色**プロパティ ページ。  
  
-   A**表示項目**は、コメント、文字列、または表示されるときに色で表示されますが、制御構造などのテキストが適切に定義されたエンティティです。  
  
 各**表示項目**内で一意に定義されて、**カテゴリ**含まれています。 その結果、複数の**カテゴリ**できますが、**表示項目**と同じ名前です。  
  
## <a name="vspackage-control-of-fonts-and-colors"></a>VSPackage のコントロールのフォントと色  
 [!INCLUDE[vsipsdk](../extensibility/includes/vsipsdk_md.md)]に Vspackage を使用します。  
  
-   フォントと色を定義する**カテゴリ**します。  
  
-   フォントと色を使用して指定**表示項目**します。  
  
-   対話、**フォントおよび色**プロパティ ページ。  
  
-   複数の集計**カテゴリ**をグループにします。  
  
-   既定の設定の変更を保持します。  
  
 内のフォントと色の選択範囲と対話する 2 つの方法がある、[!INCLUDE[vsipsdk](../extensibility/includes/vsipsdk_md.md)]します。  
  
-   1 つの方法と呼びます*構文の色分け*します。 既存をカスタマイズする VSPackage によって使用されて[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]エディターの言語サービスを実装し、エディターのソースを作成します。  
  
     1 つだけ**カテゴリ**つまり、このメカニズムをサポートしている場合、**テキスト エディター**します。  
  
-   他のすべての一般的な代替手段をサポートしています**カテゴリ**とテキストを表示するときに、ソース エディター以外のユーザー インターフェイス コンポーネント。 詳細については、「<xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorDefaultsProvider>」を参照してください。  
  
## <a name="core-editor-text-settings"></a>コア エディターのテキストの設定  
 言語サービス オブジェクトのコア エディターのフォントと色の設定が適用されます、**テキスト EditorCategory**で見つかった、**設定の表示**のドロップダウン ボックス、**フォントおよび色**プロパティ ページ。  
  
 エディターを使用する場合は、特殊なフォントおよび色の制御メカニズムを制御し、拡張言語サービスを提供するを使用する必要があります、**テキスト エディター**設定します。 メカニズムと呼びます*構文の色分け表示*提供と。  
  
-   フォントと色の表示項目を管理するための簡略化された手法です。  
  
     詳細については、<xref:Microsoft.VisualStudio.TextManager.Interop.IVsProvideColorableItems> および <xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorableItem> を参照してください。  
  
-   適切に定義された、最適化された色づけのメカニズムです。  
  
     詳細については、「<xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorizer>」を参照してください。  
  
-   両方の機能を使用して、組み込みの表示項目から、**テキスト EditorCategory**とそれらを拡張します。  
  
     詳細については、次を参照してください。[方法: ビルトインの配色可能な項目を使用して、](../extensibility/internals/how-to-use-built-in-colorable-items.md)と[カスタム装飾が可能なアイテム](../extensibility/internals/custom-colorable-items.md)します。  
  
-   現在の状態の両方の組み込みとカスタムの永続化を自動で項目を表示する、**テキスト エディター**カテゴリ。  
  
 構文の色分け表示の詳細については[構文の色分け、従来の言語サービス](../extensibility/internals/syntax-coloring-in-a-legacy-language-service.md)します。  
  
## <a name="see-also"></a>関連項目  
 [エディターでのレガシー インターフェイス](../extensibility/legacy-interfaces-in-the-editor.md)   
 [構文の色分け、従来の言語サービス](../extensibility/internals/syntax-coloring-in-a-legacy-language-service.md)