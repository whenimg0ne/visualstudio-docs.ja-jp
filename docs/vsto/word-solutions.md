---
title: "Word ソリューション"
ms.custom: ""
ms.date: "02/02/2017"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "office-development"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
helpviewer_keywords: 
  - "ソリューション [Visual Studio での Office 開発]、Word"
  - "Office プロジェクト [Visual Studio での Office 開発]、Word"
  - "アプリケーション レベルのアドイン [Visual Studio での Office 開発]、Word"
  - "Word [Visual Studio での Office 開発]"
  - "プロジェクト [Visual Studio での Office 開発]、Word"
  - "Word [Visual Studio での Office 開発]、Word ソリューションの概要"
  - "Office ソリューション [Visual Studio での Office 開発]、Word"
  - "Word [Visual Studio での Office 開発]、アプリケーション レベルのアドイン"
  - "ドキュメント [Visual Studio での Office 開発]、Word"
  - "Visual Studio での Office 開発、Word ソリューション"
  - "アドイン [Visual Studio での Office 開発]、Word"
  - "Word [Visual Studio での Office 開発]、ドキュメント レベルのカスタマイズ"
  - "ユーザー インターフェイス [Visual Studio での Office 開発]、Word"
  - "Office ドキュメント [Visual Studio での Office 開発、Word"
  - "ドキュメント レベルのカスタマイズ [Visual Studio での Office 開発]、Word"
ms.assetid: ef339ad8-1897-4a44-b588-e6004d0b6d8b
caps.latest.revision: 36
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 31
---
# Word ソリューション
  Visual Studio には、Microsoft Office Word のドキュメント レベルのカスタマイズおよび VSTO アドインの作成に使用できるプロジェクト テンプレートが用意されています。 これらのソリューションを使用して、Word の自動化、Word の機能拡張、Word のユーザー インターフェイス \(UI\) のカスタマイズを行うことができます。 ドキュメント レベルのカスタマイズと VSTO アドインの違いの詳細については、「[Office ソリューションの開発の概要 &#40;VSTO&#41;](../vsto/office-solutions-development-overview-vsto.md)」を参照してください。  
  
 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]  
  
 ここでは、次の情報について説明します。  
  
-   [Word の自動化](#automating)  
  
-   [Word のドキュメント レベルのカスタマイズの作成](#doclevel)  
  
-   [Word 用の VSTO アドインの開発](#applevel)  
  
-   [Word のユーザー インターフェイスのカスタマイズ](#UI)  
  
##  <a name="automating"></a> Word の自動化  
 Word オブジェクト モデルでは、Word の自動化に使用できる型が多数公開されています。 たとえば、プログラムを使用して、表の作成、文書の書式設定、範囲内や段落内でのテキストの設定などを行うことができます。 詳細については、「[Word オブジェクト モデルの概要](../vsto/word-object-model-overview.md)」を参照してください。  
  
 Visual Studio で Word ソリューションを開発するときには、ソリューションの*ホスト項目*および*ホスト コントロール*を使用することもできます。 Word オブジェクト モデルには、<xref:Microsoft.Office.Interop.Word.Document> や <xref:Microsoft.Office.Interop.Word.ContentControl> などのよく使用される特定のオブジェクトを拡張したオブジェクトがあります。 これらの拡張オブジェクトは、基になる Word オブジェクトと同じように動作しますが、基のオブジェクトにはないイベントとデータ バインディング機能が追加されています。 詳細については、「[拡張オブジェクトによる Word の自動化](../vsto/automating-word-by-using-extended-objects.md)」を参照してください。  
  
##  <a name="doclevel"></a> Word のドキュメント レベルのカスタマイズの作成  
 Microsoft Office Word のドキュメント レベルのカスタマイズは、特定の文書に関連付けられたアセンブリで構成されます。 このアセンブリは、一般には UI のカスタマイズと Word の自動化によってドキュメントの機能を拡張します。 Word 自体と関連付けられる VSTO アドインとは異なり、カスタマイズに実装した機能は、関連付けられた文書が Word で開かれている場合にのみ利用できます。  
  
 Word のドキュメント レベルのカスタマイズ プロジェクトを作成するには、Visual Studio の **\[新しいプロジェクト\]** ダイアログ ボックスで Word 文書または Word テンプレートのプロジェクト テンプレートを使用します。 詳細については、「[方法: Visual Studio で Office プロジェクトを作成する](../vsto/how-to-create-office-projects-in-visual-studio.md)」を参照してください。  
  
 ドキュメント レベルのカスタマイズが機能するしくみの詳細については、「[ドキュメント レベルのカスタマイズのアーキテクチャ](../vsto/architecture-of-document-level-customizations.md)」を参照してください。  
  
### Word カスタマイズのプログラミング モデル  
 Word のドキュメント レベルのプロジェクトを作成すると、`ThisDocument` と呼ばれる、ソリューションの基礎となるクラスが Visual Studio によって生成されます。 このクラスは、ソリューションに関連付けられたドキュメントを表し、コードを記述する際の開始点となります。  
  
 `ThisDocument` クラスおよびドキュメント レベルのプロジェクトで使用できる他の機能の詳細については、「[ドキュメント レベルのカスタマイズのプログラミング](../vsto/programming-document-level-customizations.md)」を参照してください。  
  
##  <a name="applevel"></a> Word 用の VSTO アドインの開発  
 Microsoft Office Word の VSTO アドインは、Word によって読み込まれるアセンブリで構成されます。 このアセンブリは、一般には UI のカスタマイズと Word の自動化によって Word の機能を拡張します。 特定のドキュメントに関連付けられるドキュメント レベルのカスタマイズとは異なり、VSTO アドインに実装する機能の対象は 1 つの文書だけに制限されません。  
  
 Word 用の VSTO アドイン プロジェクトを作成するには、Visual Studio の **\[新しいプロジェクト\]** ダイアログ ボックスで Word アドイン プロジェクト テンプレートを使用します。 詳細については、「[方法: Visual Studio で Office プロジェクトを作成する](../vsto/how-to-create-office-projects-in-visual-studio.md)」を参照してください。  
  
 VSTO アドインが機能するしくみの概要については、「[VSTO アドインのアーキテクチャ](../vsto/architecture-of-vsto-add-ins.md)」を参照してください。  
  
### Word アドインのプログラミング モデル  
 Word VSTO アドイン プロジェクトを作成すると、`ThisAddIn` と呼ばれる、ソリューションの基礎となるクラスが Visual Studio によって生成されます。 このクラスは、コードを記述する際の開始点となり、Word のオブジェクト モデルを VSTO アドインに公開します。  
  
 `ThisAddIn` クラスおよび VSTO アドインで使用できる他の機能の詳細については、「[VSTO アドインのプログラミング](../vsto/programming-vsto-add-ins.md)」を参照してください。  
  
##  <a name="UI"></a> Word のユーザー インターフェイスのカスタマイズ  
 Word のユーザー インターフェイスをカスタマイズする方法はいくつかあります。 一部のオプションはすべてのプロジェクト タイプで使用できますが、VSTO アドインまたはドキュメント レベルのカスタマイズでのみ使用できるオプションもあります。  
  
### すべてのプロジェクト タイプのオプション  
 ドキュメント レベルのカスタマイズと VSTO アドインの両方に使用できるカスタマイズ オプションを次の表に示します。  
  
|タスク|詳細情報|  
|---------|----------|  
|リボンをカスタマイズする。|[リボンの概要](../vsto/ribbon-overview.md)|  
|カスタマイズされた文書 \(ドキュメント レベルのカスタマイズの場合\) または開いている任意の文書 \(VSTO アドインの場合\) に Windows フォーム コントロールまたは拡張された Word コントロールを追加する。|[方法 : Office ドキュメントに Windows フォーム コントロールを追加する](../vsto/how-to-add-windows-forms-controls-to-office-documents.md)<br /><br /> [方法 : Word 文書にコンテンツ コントロールを追加する](../vsto/how-to-add-content-controls-to-word-documents.md)<br /><br /> [方法 : Word 文書に Bookmark コントロールを追加する](../vsto/how-to-add-bookmark-controls-to-word-documents.md)|  
  
### ドキュメント レベルのカスタマイズのオプション  
 ドキュメント レベルのカスタマイズにのみ使用できるカスタマイズ オプションを次の表に示します。  
  
|タスク|詳細情報|  
|---------|----------|  
|文書に操作ウィンドウを追加する。|[操作ウィンドウの概要](../vsto/actions-pane-overview.md)<br /><br /> [方法: Word 文書または Excel ブックに操作ウィンドウを追加する](../vsto/how-to-add-an-actions-pane-to-word-documents-or-excel-workbooks.md)|  
|拡張された XMLNode コントロールおよび XMLNodes コントロールをドキュメントに追加する。|[方法 : Word 文書に XMLNode コントロールを追加する](../vsto/how-to-add-xmlnode-controls-to-word-documents.md)<br /><br /> [方法 : Word 文書に XMLNodes コントロールを追加する](../vsto/how-to-add-xmlnodes-controls-to-word-documents.md)|  
  
### VSTO アドインのオプション  
 VSTO アドインにのみ使用できるカスタマイズ オプションを次の表に示します。  
  
|タスク|詳細情報|  
|---------|----------|  
|カスタム作業ウィンドウを作成する。|[カスタム作業ウィンドウ](../vsto/custom-task-panes.md)|  
  
### 関連トピック  
  
|タイトル|説明|  
|----------|--------|  
|[Word オブジェクト モデルの概要](../vsto/word-object-model-overview.md)|Word オブジェクト モデルに用意されている主な型の概要について説明します。|  
|[拡張オブジェクトによる Word の自動化](../vsto/automating-word-by-using-extended-objects.md)|Word ソリューションで使用できる \([!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] に用意されている\) 拡張オブジェクトについて説明します。|  
|[Office ドキュメントでの Windows フォーム コントロールの概要](../vsto/windows-forms-controls-on-office-documents-overview.md)|Windows フォーム コントロールを Word 文書に追加する方法について説明します。|  
|[チュートリアル : 初めての Word 用ドキュメント レベルのカスタマイズの作成](../vsto/walkthrough-creating-your-first-document-level-customization-for-word.md)|Word 用の基本的なドキュメント レベルのカスタマイズを作成する方法を示します。|  
|[チュートリアル : 初めての Word 用 VSTO アドインの作成](../vsto/walkthrough-creating-your-first-vsto-add-in-for-word.md)|Word 用の基本的な VSTO アドインを作成する方法を示します。|  
|[チュートリアル: 実行時における VSTO アドインの文書へのコントロールの追加](../vsto/walkthrough-adding-controls-to-a-document-at-run-time-in-a-vsto-add-in.md)|VSTO アドインを使用して、実行時に Windows フォームのボタンおよび <xref:Microsoft.Office.Tools.Word.RichTextContentControl> を文書に追加する方法を示します。|  
|[Office 開発における Word 2010](http://go.microsoft.com/fwlink/?LinkId=199020)|Word ソリューションの開発に関する文書やリファレンス ドキュメントへのリンクを示します \(Visual Studio を使用した Office 開発に限定されません\)。|  
  
  