---
title: "方法: パッケージング エクスプローラーを使用してパッケージのフィーチャーおよび項目を追加および削除する | Microsoft Docs"
ms.custom: ""
ms.date: "02/02/2017"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "office-development"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VS.SharePointTools.RAD.PackagingExplorer"
dev_langs: 
  - "VB"
  - "CSharp"
  - "VB"
  - "CSharp"
helpviewer_keywords: 
  - "Visual Studio での SharePoint 開発, パッケージ"
ms.assetid: 549d5848-f0c9-42c6-b7f5-bc1e626a30e6
caps.latest.revision: 18
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 17
---
# 方法: パッケージング エクスプローラーを使用してパッケージのフィーチャーおよび項目を追加および削除する
  SharePoint アイテムおよびフィーチャーを配置するためのパッケージを構成するには、パッケージング エクスプローラーを使用します。  .wsp ファイルに含める SharePoint のプロジェクト項目およびフィーチャーは適宜調整できます。  
  
 また、パッケージ デザイナーを使用してフィーチャーを表示し、並べ替えることで、アクティブ化の順序を変更することもできます。  詳細については、「[方法: パッケージ デザイナーを使用してパッケージのフィーチャーおよび項目を追加および削除する](../sharepoint/how-to-add-and-remove-features-and-items-to-a-package-by-using-the-package-designer.md)」を参照してください。  
  
## パッケージング エクスプローラーを開く  
 Visual Studio ソリューションに SharePoint プロジェクトが少なくとも 1 つ含まれている場合、パッケージング エクスプローラーは次の手順で開くことができます。  また、パッケージング エクスプローラーは、フィーチャー デザイナーまたはパッケージ デザイナーを表示すると自動的に開きます。  フィーチャー デザイナーとパッケージ デザイナーをすべて閉じると、パッケージング エクスプローラーも閉じます。  
  
#### パッケージング エクスプローラーを開くには  
  
1.  メニュー バーで、**\[その他のウィンドウ\]**、**\[パッケージング エクスプローラー\]\[表示\]** をクリックします。  
  
     **\[パッケージング エクスプローラー\]** は **\[ツールボックス\]** に表示されます。  
  
## パッケージにフィーチャーを追加する  
 パッケージング エクスプローラーを使用して、新しいフィーチャーおよび既存のフィーチャーをパッケージに追加できます。  
  
#### SharePoint フィーチャーを追加するには  
  
1.  **\[パッケージング エクスプローラー\]** を開き、プロジェクトのショートカット メニューを開き、**\[フィーチャーの追加\(F\)\]** をクリックします。  
  
#### 既存の SharePoint フィーチャーを移動するには  
  
1.  **\[パッケージング エクスプローラー\]** を開き、次の手順の実行: 1  
  
    -   1 種類のプロジェクトから別のプロジェクトに **\[フィーチャー\]** をドラッグします。  
  
    -   機能のショートカット メニューを開き、**\[切り取り\]** をクリックします、機能を移動先を開き、**\[貼り付け\]** をクリックしますプロジェクトのショートカット メニューを。  
  
    > [!NOTE]  
    >  ソリューション内に複数の SharePoint プロジェクトがある場合は、この手順を使用してください。  
  
## フィーチャーまたはパッケージを検証する  
 SharePoint のフィーチャーおよびパッケージに存在する可能性のある問題は、ファイルを検証することによって特定できます。  警告およびエラーは出力ウィンドウおよび \[エラー一覧\] ウィンドウに表示されます。  
  
#### SharePoint のフィーチャーまたはパッケージを検証するには  
  
1.  **\[パッケージング エクスプローラー\]** を開きます。  
  
2.  フィーチャー デザイナーまたはパッケージのショートカット メニューを開き、**\[検証\(V\)\]** をクリックします。  
  
## 参照  
 [SharePoint ソリューションのパッケージ化と配置](../sharepoint/packaging-and-deploying-sharepoint-solutions.md)  
  
  