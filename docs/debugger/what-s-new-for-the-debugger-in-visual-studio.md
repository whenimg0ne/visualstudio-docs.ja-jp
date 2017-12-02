---
title: "Visual Studio 2017 のデバッガーの新機能 |Microsoft ドキュメント"
ms.custom: 
ms.date: 03/07/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugger, what's new
- what's new [debugger]
- debugging [Visual Studio], what's new
- what's new [Visual Studio], debugging
ms.assetid: 2aed9caa-2384-4e49-8595-82d8b06cf271
caps.latest.revision: "81"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 2a08c56ae60822e6d4183e5789c68cbe383b4dd5
ms.sourcegitcommit: 2c7f48ad6073a81fa927568793633f26cc1f0b15
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2017
---
# <a name="whats-new-for-the-debugger-in-includevsdev15miscincludesvsdev15mdmd"></a>デバッガーの新機能します。[!include[vs_dev15](../misc/includes/vs_dev15_md.md)]

デバッガーには、これらの新機能が含まれています。

- 15.5 の新機能、**スナップショット デバッガー**興味のあるコードを実行するときに、実稼働環境でアプリのスナップショットを取得します。 スナップショットを取得するデバッガーを指示するには、コードで snappoints と logpoints を設定します。 デバッガーでは、正確にどのような問題が発生した、実稼働アプリケーションのトラフィックの影響を与えずを確認できます。 スナップショットのデバッガーには、実稼働環境で発生する問題の解決にかかる時間を大幅に削減するのに役立ちます。

    スナップショットのコレクションは、Azure App Service で実行されている次の web アプリを入手できます。

    * .NET Framework 4.6.1 で実行されている ASP.NET アプリケーションまたはそれ以降。
    * ASP.NET Core アプリケーションが .NET Core 2.0 または後で Windows 上で実行します。

    詳細については、次を参照してください。[スナップショット デバッガーを使用してライブの ASP.NET アプリのデバッグ](../debugger/debug-live-azure-applications.md)です。

- Visual Studio Enterprise でのみ、15.5 で新しい**IntelliTrace ステップ ライトバック**手順イベント、アプリケーションのすべてのブレークポイントとデバッガーのスナップショットを自動的に取得します。 記録されたスナップショットを使用すると、前のブレークポイントまたは手順に戻るし、過去になっていたようにアプリケーションの状態を表示できます。 IntelliTrace 手順戻ることができますの以前のアプリケーション状態を確認しますが、デバッグを再起動するか、必要なアプリケーションの状態を再作成したくないです。

    移動しを使用してスナップショットを表示することができます、**手順旧バージョンと**と**つ進む**デバッグ ツールバーのボタンです。 これらのボタンに表示されるイベントの移動、**イベント** タブで、**診断ツール**ウィンドウです。

    ![ステップ後退と転送ボタン](../debugger/media/intellitrace-step-back-icons-description.png  "旧バージョンとステップと転送ボタン")

    詳細については、次を参照してください。、 [IntelliTrace ステップ ライトバックを使用してスナップショットを表示する](../debugger/how-to-use-intellitrace-step-back.md)ページ。

- **例外ヘルパー**置換、例外処理アシスタントと、エラーが発生した非モーダル ダイアログ ボックスに表示されます。 **例外ヘルパー**簡単にアクセスするには、内部例外、(使用可能な場合)、デバッガーによってさらに分析および即時アクセスを提供、**例外設定**例外。 例外ヘルパーはブロックして表示する必要がある場合浮動ビューにドラッグできます。

    たとえば、 **NullReferenceException**を null 参照 (追加情報) を持つ変数が表示されます。

    ![デバッガーの例外ヘルパー](../debugger/media/dbg-exception-helper.png "DbgExceptionHelper")

    詳細については、「[Using the New Exception Helper in Visual Studio](https://blogs.msdn.microsoft.com/visualstudioalm/2016/03/31/using-the-new-exception-helper-in-visual-studio-15-preview/)」 (Visual Studio で新しい例外ヘルパーを使用する) のブログの投稿を参照してください。

- コードを選択すると、デバッガーで一時停止中に行を実行できます、**ここまで実行**緑色の矢印アイコン (アイコンが表示、コード行にポインターを置いたときに)。 これにより、一時的なブレークポイントを設定する必要があります。

    ![デバッガーの実行 をクリックを](../debugger/media/dbg-run-to-click.png "DbgRunToClick") 

- 例外に条件を設定することができます、**例外設定** ダイアログ ボックス (を使用してこれを行う、**条件の編集**アイコンを右クリック メニューを使用してまたは例外設定 ダイアログ ボックスで、例外です。)現在サポートされている条件には、例外のるまたは除外するには、モジュール名が含まれます。

    ![例外条件](../debugger/media/dbg-conditional-exception.png "DbgConditionalException")

- プロセスにアタッチ ダイアログ ボックスに、プロセスにアタッチする必要のあるをすばやく識別するのに役立つ新しい検索機能が含まれています。

    ![検索プロセスにアタッチする](../debugger/media/dbg-attach-to-process-search.png "DbgAttachToProcessSearch") 

これらの新機能の詳細については、次を参照してください。、[のリリース ノート[!include[vs_dev15](../misc/includes/vs_dev15_md.md)]](https://www.visualstudio.com/en-us/news/releasenotes/vs2017-relnotes#debuggingdiag)です。
  
## <a name="see-also"></a>関連項目  
 [Visual Studio でのデバッグ](../debugger/index.md)  
 [デバッガー機能ツアー](../debugger/debugger-feature-tour.md)