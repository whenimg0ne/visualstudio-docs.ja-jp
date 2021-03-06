---
title: ツールのユーザー インターフェイスをドメイン固有言語の概要 |Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-tfs-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.dsltools.dsldesigner.editor
helpviewer_keywords:
- Domain-Specific Language Tools, user interface
ms.assetid: 81ae6b35-6819-41d0-953b-6b4ed81f9227
caps.latest.revision: 27
author: gewarren
ms.author: gewarren
manager: douge
ms.openlocfilehash: 25d8f34488c0fee954eb9ab2d372750518433f4a
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "47533881"
---
# <a name="overview-of-the-domain-specific-language-tools-user-interface"></a>ドメイン固有言語ツールのユーザー インターフェイスの概要
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

このトピックの最新バージョンをご覧[ドメイン固有言語ツールのユーザー インターフェイスの概要](https://docs.microsoft.com/visualstudio/modeling/overview-of-the-domain-specific-language-tools-user-interface)します。  
  
ドメイン固有言語ツール (DSL ツール) ソリューションを初めて開く[!INCLUDE[vsprvs](../includes/vsprvs-md.md)]、ユーザー インターフェイスは、次の図のようになります。  
  
 ![dsl designer](../modeling/media/dsl-designer.png "dsl_designer")  
  
 次の表では、UI の部分を使用する方法について説明します。  
  
|**要素**|**定義**|  
|-----------------|--------------------|  
|図|図では、ドメイン モデルが表示されます。<br /><br /> ダイアグラムでは、2 つの辺が。 一方の側では、モデル内の要素の型を定義します。 もう一方の側では、画面でのモデルの表示方法を定義します。|  
|ツールボックス|ドメイン クラスを追加して、ダイアグラムの種類の図形をツールボックスからツールをドラッグします。 リレーションシップ、コネクタ、および図形マップを追加するには、ツールをクリックし、ダイアグラムで、ソース ノードとし、ターゲット ノードをクリックします。|  
|DSL エクスプローラー|**DSL エクスプ ローラー** DSL 定義がアクティブなウィンドウが表示されます。 DSL がツリーとして表示されます。 DSL エクスプ ローラーを使用して、モデルのダイアグラムに表示されていない機能を編集できます。 たとえば、ツールボックス項目を追加し、スイッチを使用して、検証プロセス、 **DSL エクスプ ローラー**します。|  
|DSL の詳細 ウィンドウ|**DSL の詳細**ウィンドウは、要素の表示方法と、要素がコピーされ、削除する方法を制御するためのモデルの要素のドメインのプロパティを示しています。<br /><br /> -既定で、 **DSL の詳細**ウィンドウが横に表示されます、**エラー一覧**と**出力**windows。|  
  
## <a name="the-domain-model-diagram"></a>ドメイン モデルのダイアグラム  
 ドメイン モデルの図は、2 つの部分に分かれています。 ダイアグラムの一方の側は、モデル要素と関係を示します。 もう一方の側の表示方法、モデルが表示されますが、要素とモデル図のプロパティを表示するために使用する図形が含まれています。 次の図は、図の要素を示します。  
  
 ![スイムレーンを含む dsl デザイナー](../modeling/media/dsl-desinger.png "dsl_desinger")  
  
 次の表では、いくつかのドメイン モデルの図の要素について説明します。  
  
|**用語**|**定義**|  
|--------------|--------------------|  
|ドメイン クラス|ドメイン クラスは、モデル内の要素の種類です。<br /><br /> 1 つ以上のリレーションシップのターゲットである場合は複数回ドメイン クラスを表示し、図では、ことができます。<br /><br /> ドメイン クラスを追加するから、ドメイン クラスのツールをドラッグ、**ツールボックス**を**クラスとリレーションシップ**ダイアグラムの側です。|  
|ドメイン リレーションシップ|ドメイン リレーションシップでは、モデル内の要素間のリンクの種類です。<br /><br /> *埋め込みリレーションシップ*実線として表示され、ターゲット要素を所有するか、ソース要素に含まれていることを示します。 モデル内のすべての要素は、モデルがツリーを形成するため、1 つの埋め込みリレーションシップのターゲットにすることがあります。 A*参照リレーションシップ*破線として表示され、モデルの要素間の一般的なリンクを示します。 任意の要素には、任意の数へのリンクを持つことができます。<br /><br /> ツールをクリックしてリレーションシップを作成、**ツールボックス**をソース ドメイン クラスをクリックし、[対象クラス] をクリックします。|  
|シェイプとコネクタ|コネクタでは、行を指定の関係を表示するために使用する DSL ダイアグラムで、図形は、DSL ダイアグラムでのモデル要素の表示方法を指定します。<br /><br /> シェイプまたはコネクタを作成するツールをドラッグして、**ダイアグラム要素**ダイアグラムの側です。|  
|シェイプ マップ|マップのシェイプは、ドメイン モデル ダイアグラムの図形をリンクする、表示されるドメイン クラスまたは表示するドメイン リレーションシップにコネクタの線として表示されます。|  
  
## <a name="see-also"></a>関連項目  
 [ドメイン固有言語ツールの概要](../modeling/overview-of-domain-specific-language-tools.md)   
 [ドメイン固有言語ツールの用語集](http://msdn.microsoft.com/en-us/ca5e84cb-a315-465c-be24-76aa3df276aa)   
 [ドメイン固有言語のカスタマイズおよび拡張](../modeling/customizing-and-extending-a-domain-specific-language.md)



