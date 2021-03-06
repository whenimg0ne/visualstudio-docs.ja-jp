---
title: '方法: ローカライズされた名前、プロパティ、およびアクセス許可を指定するリソース ファイルを使用して |Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- VB
- CSharp
helpviewer_keywords:
- Business Data Connectivity service [SharePoint development in Visual Studio], localize strings
- BDC [SharePoint development in Visual Studio], localize strings
- BDC [SharePoint development in Visual Studio], resource file
- Business Data Connectivity service [SharePoint development in Visual Studio], resource strings
- BDC [SharePoint development in Visual Studio], properties
- Business Data Connectivity service [SharePoint development in Visual Studio], properties
- Business Data Connectivity service [SharePoint development in Visual Studio], resource file
- BDC [SharePoint development in Visual Studio], resource strings
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: c54aa87f09d4821f9fde5cceb95e6ec3a8e089fa
ms.sourcegitcommit: d9e4ea95d0ea70827de281754067309a517205a1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/29/2018
ms.locfileid: "37119446"
---
# <a name="how-to-use-a-resource-file-to-specify-localized-names-properties-and-permissions"></a>方法: リソース ファイルを使用して、ローカライズされた名前、プロパティ、およびアクセス許可を指定するには
  リソース ファイルを使用すると、ローカライズされた名前を指定、プロパティを定義およびビジネス データ接続 (BDC) モデルで定義されているアクセス許可の tor オブジェクトを適用することができます。 この情報を指定する追加、**ビジネス データ接続リソース**項目を含むプロジェクトを**Business Data Connectivity モデル**項目。 次のリソース ファイルの XML を編集することによって名前、プロパティ、およびアクセス許可を指定します。  
  
### <a name="to-add-a-bdc-resource-file-to-a-sharepoint-project"></a>BDC リソース ファイルを SharePoint プロジェクトに追加するには  
  
1.  **ソリューション エクスプ ローラー**SharePoint プロジェクトのフォルダーを展開し、BDC モデルを含むフォルダーを選択します。  
  
2.  メニュー バーで **[プロジェクト]** > **[新しい項目の追加]** の順に選択します。  
  
3.  展開、 **SharePoint**ノードを選択し、 **2010**ノード。  
  
4.  **新しい項目の追加** ダイアログ ボックスで、選択**ビジネス データ接続リソース項目**します。  
  
5.  **名前**ボックス、リソース ファイルの名前を指定し、選択、**追加**ボタンをクリックします。  
  
     .Bdcr 拡張子を持つリソース ファイルがプロジェクトに追加し、編集用に開きます。  
  
6.  ローカライズされた名前、プロパティ、および BDC モデルを適用するアクセス許可を定義する XML を追加します。  
  
     これらの要素を定義する方法については、次を参照してください。[モデル ファイルとリソース ファイル](http://go.microsoft.com/fwlink/?LinkID=169283)します。  
  
## <a name="see-also"></a>関連項目
 [方法: SharePoint プロジェクトに既存の BDC モデル ファイルを追加](../sharepoint/how-to-add-an-existing-bdc-model-file-to-a-sharepoint-project.md)   
 [ビジネス データ接続モデルを作成します。](../sharepoint/creating-a-business-data-connectivity-model.md)   
 [方法: BDC モデルの作成](../sharepoint/how-to-create-a-bdc-model.md)   
 [方法: BDC 機能にカスタム アセンブリを含める](../sharepoint/how-to-include-a-custom-assembly-in-a-bdc-feature.md)   
 [SharePoint にビジネス データの統合](../sharepoint/integrating-business-data-into-sharepoint.md)  
  
