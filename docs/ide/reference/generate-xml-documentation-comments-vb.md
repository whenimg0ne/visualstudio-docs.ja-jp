---
title: "XML ドキュメントのコメントの生成 (Visual Basic) | Microsoft Docs"
ms.custom: 
ms.date: 11/17/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 2f421553657dfafb265140e44e38a2c7722a7303
ms.sourcegitcommit: b01406355e3b97547b7cbf8ce3960f101b165cec
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2018
---
# <a name="generate-xml-documentation-comments-in-visual-basic"></a>XML ドキュメントのコメントの生成 (Visual Basic)

**機能:** 選択した要素のドキュメント化に必要な、基本 XML をすぐに生成できます。 

**条件:** Sandcastle などのドキュメント ツールによって後で処理するために XML ドキュメント コメントを作成したいとき。

**理由:** 手動でコメント ブロック全体を作成できますが、基本テンプレートと追加要素を生成すると、時間の節約になり、精度が向上します。 

**方法:**

1. メソッドなど、ドキュメント化する要素の上にテキスト カーソルを置きます。

   ![ドキュメント化するメソッド](media/doc-highlight-vb.png)

1. 次に、**'''** (3 つの一重引用符) を入力します。これで、基本テンプレートと必要に応じて追加要素が自動生成されます。  たとえば、メソッドのコメントを記述するときに、**\<summary\>** タグ、メソッドに渡されるすべてのパラメーターの **\<param\>** タグ、メソッドが返す内容をドキュメント化する **\<returns\>** タグが生成されます。

   ![テンプレート](media/doc-preview-vb.png)

1. コメントを完了し、必要と思われるその他の情報を追加します。

   ![完了したコメント](media/doc-result-vb.png)

## <a name="see-also"></a>関連項目

[XML の使用によるコードのドキュメントの作成 (Visual Basic)](/dotnet/visual-basic/programming-guide/program-structure/documenting-your-code-with-xml)  
[コード生成](../code-generation-in-visual-studio.md)