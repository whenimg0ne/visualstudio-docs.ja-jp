---
title: TargetPlatformName 要素 (Visual Studio テンプレート) |Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3a6b1f45-b5d6-418e-add1-87ee8f15033d
caps.latest.revision: 6
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 4a82a30c8df696e5666d81b18a8f60641debf828
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "47539995"
---
# <a name="targetplatformname-element-visual-studio-templates"></a>TargetPlatformName 要素 (Visual Studio テンプレート)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

このトピックの最新バージョンをご覧[TargetPlatformName 要素 (Visual Studio テンプレート)](https://docs.microsoft.com/visualstudio/extensibility/targetplatformname-element-visual-studio-templates)します。  
  
プロジェクト テンプレートの対象となるプラットフォームを指定します。 この要素を使用して作成するプロジェクト テンプレートを使用することを指定[!INCLUDE[win8_appname_long](../includes/win8-appname-long-md.md)]アプリ。  
  
## <a name="syntax"></a>構文  
  
```xml  
<VSTemplate>  
    <TemplateData>   
        <TargetPlatformName> OperatingSystem</TargetPlatformName>  
```  
  
## <a name="attributes-and-elements"></a>属性および要素  
 以降のセクションでは、属性、子要素、および親要素について説明します。  
  
### <a name="attributes"></a>属性  
 なし。  
  
### <a name="child-elements"></a>子要素  
  
|要素|説明|  
|-------------|-----------------|  
|[RequiredPlatformVersion](../extensibility/requiredplatformversion-element-visual-studio-templates.md)|プロジェクト テンプレートの対象となるオペレーティング システムのバージョンを指定します。|  
  
### <a name="parent-elements"></a>親要素  
  
|要素|説明|  
|-------------|-----------------|  
|[TemplateData](../extensibility/templatedata-element-visual-studio-templates.md)|テンプレートをカテゴリに分類し、 **[新しいプロジェクト]** ダイアログ ボックス、または **[新しい項目の追加]** ダイアログ ボックスでどのように表示させるかを定義します。|  
  
## <a name="text-value"></a>テキスト値  
 テキスト値が必要です。  
  
## <a name="remarks"></a>Remarks  
 テキストは、 **Windows**である必要があります。  
  
## <a name="example"></a>例  
 次の例では、プロジェクト テンプレートで [!INCLUDE[win8](../includes/win8-md.md)] 以降が対象となるように指定しています。  
  
```xml  
<VSTemplate Type="Project" Version="3.0.0" xmlns="http://schemas.microsoft.com/developer/vstemplate/2005">   
    <TemplateData>   
        <TargetPlatformName>Windows</TargetPlatformName>   
        <RequiredPlatformVersion>8</RequiredPlatformVersion>   
    </TemplateData>   
    <TemplateContent> </TemplateContent>  
</VSTemplate>  
```  
  
## <a name="see-also"></a>関連項目  
 [プロジェクトと項目テンプレートの作成](../ide/creating-project-and-item-templates.md)   
 [Visual Studio テンプレート スキーマ参照](../extensibility/visual-studio-template-schema-reference.md)

