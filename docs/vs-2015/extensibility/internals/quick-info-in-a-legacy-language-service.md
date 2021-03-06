---
title: 従来の言語サービスで、クイック ヒント |Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Quick Info, supporting in language services [managed package framework]
- IntelliSense, Quick Info
- language services [managed package framework], IntelliSense Quick Info
ms.assetid: 159ccb0b-f5d6-4912-b88b-e9612924ed5e
caps.latest.revision: 17
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 2ba5d6d2c08d6b4d39efe9d662dda7a0e324cbf6
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "47533488"
---
# <a name="quick-info-in-a-legacy-language-service"></a>従来の言語サービスのクイック ヒント
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

このトピックの最新バージョンをご覧[従来の言語サービスで、クイック ヒント](https://docs.microsoft.com/visualstudio/extensibility/internals/quick-info-in-a-legacy-language-service)します。  
  
IntelliSense によるクイック ヒントでは、ユーザーが、識別子にキャレットを配置および選択ソースの識別子に関する情報を表示**クイック ヒント**から、 **IntelliSense**メニューまたはマウスを保持識別子の上にカーソル。 これにより、識別子に関する情報を表示するツールヒント。 この情報は通常、識別子の型で構成されます。 デバッグ エンジンがアクティブの場合、この情報には、現在の値が含まれます。 デバッグ エンジンは、言語サービスは、識別子のみを処理中に、式の値を提供します。  
  
 従来の言語サービスは、VSPackage の一部として実装されますが、言語サービスの機能を実装する新しい方法は MEF 拡張機能を使用します。 詳細については、次を参照してください。[チュートリアル: クイック ツールヒントを表示する](../../extensibility/walkthrough-displaying-quickinfo-tooltips.md)します。  
  
> [!NOTE]
>  新しいエディターの API をできるだけ早く使用を開始することをお勧めします。 言語サービスのパフォーマンスを向上させる、エディターの新機能を活用することができます。  
  
 マネージ パッケージ フレームワーク (MPF) 言語のサービス クラスでは、IntelliSense によるクイック ヒントのツールヒントを表示するため完全なサポートを提供します。 行う必要があるすべてが、表示、クイック ヒント機能を有効にするテキストを指定します。  
  
 表示されるテキストは呼び出すことによって取得、<xref:Microsoft.VisualStudio.Package.LanguageService.ParseSource%2A>メソッド パーサーの解析の理由の値を持つ<xref:Microsoft.VisualStudio.Package.ParseReason>します。 このため、種類の情報 (またはクイック ツールヒントに表示する適切なもの) を取得するパーサーに伝える識別子で指定された位置の<xref:Microsoft.VisualStudio.Package.ParseRequest>オブジェクト。 <xref:Microsoft.VisualStudio.Package.ParseRequest>オブジェクトに渡されたもの、<xref:Microsoft.VisualStudio.Package.LanguageService.ParseSource%2A>メソッド。  
  
 内の位置まで、パーサーが解析する必要があります、<xref:Microsoft.VisualStudio.Package.ParseRequest>オブジェクトのすべての識別子の種類を決定するためにします。 パーサーは解析要求の場所の識別子を取得する必要があります。 最後に、パーサーには、その id に関連付けられたツール ヒントのデータを渡す必要があります、<xref:Microsoft.VisualStudio.Package.AuthoringScope>オブジェクトのため、そのオブジェクトからテキストを返すことができます、<xref:Microsoft.VisualStudio.Package.AuthoringScope.GetDataTipText%2A>メソッド。  
  
## <a name="enabling-the-quick-info-feature"></a>クイック ヒント機能を有効にします。  
 クイック ヒント機能を有効に設定する必要があります、`CodeSense`と`QuickInfo`名前付きのパラメーター、<xref:Microsoft.VisualStudio.Shell.ProvideLanguageServiceAttribute>します。これらの属性の設定、<xref:Microsoft.VisualStudio.Package.LanguagePreferences.EnableCodeSense%2A>と<xref:Microsoft.VisualStudio.Package.LanguagePreferences.EnableQuickInfo%2A>プロパティ。  
  
## <a name="implementing-the-quick-info-feature"></a>クイック ヒント機能を実装します。  
 <xref:Microsoft.VisualStudio.Package.ViewFilter>クラスは、IntelliSense によるクイック ヒントの操作を処理します。 ときに、<xref:Microsoft.VisualStudio.Package.ViewFilter>クラスを受け取る、<xref:Microsoft.VisualStudio.VSConstants.VSStd2KCmdID>のコマンドは、クラスの呼び出し、<xref:Microsoft.VisualStudio.Package.LanguageService.ParseSource%2A>メソッドの解析の理由で<xref:Microsoft.VisualStudio.Package.ParseReason>と時にキャレットの位置、<xref:Microsoft.VisualStudio.VSConstants.VSStd2KCmdID>コマンドが送信されました。 <xref:Microsoft.VisualStudio.Package.LanguageService.ParseSource%2A>メソッド パーサーする必要がありますし、指定した位置までソースを解析してクイック ツールヒントに表示を決定するように指定した位置に識別子を解析しています。  
  
 ほとんどのパーサーでは、全体のソース ファイルの初期の解析を行うし、解析ツリーで、結果を格納します。 場合に、完全な解析が実行される<xref:Microsoft.VisualStudio.Package.ParseReason>に渡される<xref:Microsoft.VisualStudio.Package.LanguageService.ParseSource%2A>メソッド。 その他の種類の解析は、必要な情報を取得するのに解析ツリーを使用できます。  
  
 たとえば、解析理由の値の<xref:Microsoft.VisualStudio.Package.ParseReason>ソースの場所にある id を見つけるし、型情報を取得して解析ツリーで調べることができます。 この種類の情報に渡されます、<xref:Microsoft.VisualStudio.Package.AuthoringScope>クラスし、によって返される、<xref:Microsoft.VisualStudio.Package.AuthoringScope.GetDataTipText%2A>メソッド。

