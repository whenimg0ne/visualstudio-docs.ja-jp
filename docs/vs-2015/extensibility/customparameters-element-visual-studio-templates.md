---
title: CustomParameters 要素 (Visual Studio テンプレート) |Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/developer/vstemplate/2005#CustomParameters
helpviewer_keywords:
- CustomParameters element [Visual Studio project templates]
ms.assetid: cf3efc91-1532-4022-bbb8-a18658424fee
caps.latest.revision: 7
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: b74b32b3134dbbb2fefdf9fc7d1913a36efbdb5d
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "47548195"
---
# <a name="customparameters-element-visual-studio-templates"></a>CustomParameters 要素 (Visual Studio テンプレート)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

このトピックの最新バージョンをご覧[CustomParameters 要素 (Visual Studio テンプレート)](https://docs.microsoft.com/visualstudio/extensibility/customparameters-element-visual-studio-templates)します。  
  
このウィザードは、パラメーター置換時に、テンプレートのウィザードに渡されるカスタム パラメーターをグループ化します。  
  
## <a name="syntax"></a>構文  
  
```  
<CustomParameters>  
    <CustomParameter/>  
    <CustomParameter/>  
</CustomParameters>  
```  
  
## <a name="attributes-and-elements"></a>属性および要素  
 以降のセクションでは、属性、子要素、および親要素について説明します。  
  
### <a name="attributes"></a>属性  
 なし。  
  
### <a name="child-elements"></a>子要素  
  
|要素|説明|  
|-------------|-----------------|  
|[CustomParameter](../extensibility/customparameter-element-visual-studio-templates.md)|省略可能な要素です。<br /><br /> カスタム パラメーターの名前と、テンプレートからプロジェクトまたは項目を作成するときに使用する値が含まれています。 `CustomParameter` 要素に 0 個以上の `CustomParameters` 要素があります。|  
  
### <a name="parent-elements"></a>親要素  
  
|要素|説明|  
|-------------|-----------------|  
|[TemplateContent](../extensibility/templatecontent-element-visual-studio-templates.md)|テンプレートの内容を指定します。|  
  
## <a name="remarks"></a>Remarks  
  
## <a name="example"></a>例  
 次の例では、テンプレートでいくつかのカスタム パラメーターを使用する方法を示します。 次のカスタム パラメーターのすべてのインスタンスを使用してテンプレートからプロジェクトまたは項目を作成するときに`$color1$`と`$color2$`でテンプレート ファイルが置き換えられる`Red`と`Blue`、それぞれします。  
  
```  
<CustomParameters>  
    <CustomParameter Name="$color1$" Value="Red"/>  
    <CustomParameter Name="$color2$" Value="Blue "/>  
</CustomParameters>  
```  
  
## <a name="see-also"></a>関連項目  
 [CustomParameter 要素 (Visual Studio テンプレート)](../extensibility/customparameter-element-visual-studio-templates.md)   
 [テンプレート パラメーター](../ide/template-parameters.md)   
 [Visual Studio テンプレート スキーマ参照](../extensibility/visual-studio-template-schema-reference.md)

