---
title: UML モデル要素にステレオタイプを追加 |Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-tfs-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- UML model, stereotypes
ms.assetid: 82545252-83ce-4e11-a419-61373be75d16
caps.latest.revision: 17
author: alexhomer1
ms.author: gewarren
manager: douge
ms.openlocfilehash: b570889c117f2fac037ddf40efe32abbd0b309c9
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "47545976"
---
# <a name="add-stereotypes-to-uml-model-elements"></a>UML モデル要素にステレオタイプを追加する
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

このトピックの最新バージョンをご覧[モデル要素を UML にステレオタイプを追加](https://docs.microsoft.com/visualstudio/modeling/add-stereotypes-to-uml-model-elements)します。  
  
UML モデル要素にステレオタイプを追加して、注釈を付けたり、特別なプロパティを追加したりすることができます。 モデル要素にステレオタイプを追加するには、プロファイル内にステレオタイプを定義しておき、モデル要素が含まれているパッケージまたはモデルにそのプロファイルをリンクする必要があります。 ステレオタイプは、UML クラス、ユース ケース、コンポーネントなど、特定の種類のモデル要素にのみ追加できます。  
  
 たとえば、«specification» ステレオタイプを持つ UML クラスを定義する場合は、標準プロファイル L2 にリンクされたパッケージまたはモデル内にそのクラスを作成する必要があります。  
  
 既定では、すべてのモデルが UML 標準プロファイル L2 および L3 にリンクされます。  
  
### <a name="to-link-a-profile-to-a-model-or-a-package"></a>プロファイルをモデルまたはパッケージにリンクするには  
  
1.  開いている**UML モデル エクスプ ローラー**します。 **アーキテクチャ**メニューで、 **Windows**、 をクリックし、 **UML モデル エクスプ ローラー**します。  
  
2.  プロファイル内のステレオタイプの適用先とする要素がすべて含まれるパッケージまたはモデルを見つけます。  
  
3.  パッケージまたはモデルを右クリックし、をクリックし、**プロパティ**します。  
  
4.  **プロパティ**ウィンドウで、設定、**プロファイル**プロパティを使用しステレオタイプが含まれているプロファイル。  
  
     これで、このプロファイルのステレオタイプを、モデルまたはパッケージに含まれているすべての要素で使用できるようになります。 パッケージに他のパッケージが含まれている場合、そのパッケージでも要素にステレオタイプを使用できるようになります。  
  
### <a name="to-add-stereotypes-to-model-elements-or-relationships"></a>モデル要素または関係にステレオタイプを追加するには  
  
1.  モデル要素または関係を図または内を右クリックして**UML モデル エクスプ ローラー**、 をクリックし、**プロパティ**します。  
  
    > [!NOTE]
    >  複数の要素に同じステレオタイプを追加する場合は、複数の要素を選択してから、その中の 1 つを右クリックします。  
  
2.  をクリックして、**ステレオタイプ**プロパティと適用するステレオタイプを選択します。  
  
     ほとんどの要素や関係では、選択したステレオタイプが << >> に囲まれてモデル要素内に表示されます。  
  
    > [!NOTE]
    >  表示されない場合、**ステレオタイプ**プロパティ、または使用ステレオタイプが表示されない場合は、モデル要素が、パッケージまたは適切なプロファイルがリンクされているモデル内に存在することを確認します。  
  
3.  一部のステレオタイプでは、モデル要素に対して追加のプロパティの値を設定できます。 これらのプロパティを表示するには、展開、**ステレオタイプ**プロパティ。  
  
### <a name="to-create-model-elements-within-a-package"></a>パッケージ内にモデル要素を作成するには  
  
1.  UML クラス図、またはパッケージを作成**UML モデル エクスプ ローラー**します。  
  
2.  そのパッケージに、次のいずれかの方法でモデル要素を追加します。  
  
    -   UML クラス図で、要素を扱うツールをクリックし、図上のパッケージの内部をクリックします。  
  
         \- または -  
  
    -   UML モデル エクスプ ローラーでパッケージを右クリックして**追加**要素型を順にクリックします。  
  
         \- または -  
  
    -   UML モデル エクスプローラーで、既存の要素をパッケージにドラッグします。  
  
         \- または -  
  
    -   図をパッケージにリンクさせた後、図内に要素を作成します。  
  
         これを行うには、図の空白部分を右クリックし、**プロパティ**します。 **プロパティ**ウィンドウで、設定**リンクされたパッケージ**パッケージにします。  
  
         この図で作成した新しい要素はすべて、このパッケージ内に定義されることになります。  
  
         この操作を実行できるのは、一部の種類の図に限られます。  
  
## <a name="see-also"></a>関連項目  
 [プロファイルを定義すると、UML を拡張](../modeling/define-a-profile-to-extend-uml.md)   
 [プロファイルとステレオタイプを使用したモデルをカスタマイズします。](../modeling/customize-your-model-with-profiles-and-stereotypes.md)   
 [パッケージと名前空間を定義します。](../modeling/define-packages-and-namespaces.md)   
 [ステレオタイプにより UML クラスの色](http://code.msdn.microsoft.com/UML-Color-Classes-by-07de2b70)



