---
title: '方法: コマンド ラインを使用してプロファイラーによってスタンドアロンのネイティブ アプリケーションを起動し、コンカレンシー データを収集する | Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e5aed651-afed-4b70-9a7e-1a6032cc614f
caps.latest.revision: 28
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 5060b22603f5cab408e6f15a9f33f104e76cd7bf
ms.sourcegitcommit: d705e015cb525bfa87a0b93e93376c3956ec2707
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "47592543"
---
# <a name="how-to-launch-a-stand-alone-native-application-with-the-profiler-to-collect-concurrency-data-by-using-the-command-line"></a>方法: コマンド ラインを使用してプロファイラーによってスタンドアロンのネイティブ アプリケーションを起動し、コンカレンシー データを収集する
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

このトピックの最新バージョンをご覧[方法: コマンドラインを使用して同時実行データを収集する、Profiler のスタンドアロン ネイティブ アプリケーションを起動](https://docs.microsoft.com/visualstudio/profiling/how-to-launch-a-stand-alone-native-application-with-the-profiler-to-collect-concurrency-data-by-using-the-command-line)します。  
  
ここでは、[!INCLUDE[vsprvs](../includes/vsprvs-md.md)] プロファイリング ツールのコマンド ライン ツールを使用して、ネイティブのスタンドアロン (クライアント) アプリケーションを起動し、プロセスおよびスレッドのコンカレンシー データを収集する方法について説明します。  
  
 プロファイル セッションには、以下の部分があります。  
  
-   プロファイラーによるアプリケーションの起動  
  
-   データ収集の制御  
  
-   プロファイル セッションの終了  
  
> [!NOTE]
>  プロファイリング ツールのコマンド ライン ツールは、[!INCLUDE[vs_current_short](../includes/vs-current-short-md.md)] インストール ディレクトリの \Team Tools\Performance Tools サブディレクトリにあります。 64 ビット コンピューター上では、64 ビット バージョンのツールと 32 ビット バージョンのツールの両方を使用できます。 コマンド プロンプトでプロファイラーを使用するには、**[コマンド プロンプト]** ウィンドウの PATH 環境変数にツールのパスを追加するか、コマンド自体にそれを追加します。 詳細については、「[コマンド ライン ツールへのパスの指定](../profiling/specifying-the-path-to-profiling-tools-command-line-tools.md)」をご覧ください。  
  
## <a name="starting-the-application-with-the-profiler"></a>プロファイラーによるアプリケーションの起動  
 プロファイラーを使用して対象アプリケーションを起動するには、[VSPerfCmd.exe](../profiling/vsperfcmd.md)**/start** オプションと **/launch** オプションを使用して、プロファイラーを初期化し、アプリケーションを起動します。 **/start** と **/launch**、およびそれぞれのオプションを指定できます。 **/globaloff** オプションを追加して、対象アプリケーションの起動時にデータ収集を一時停止することもできます。 次に、**/globalon** を使用してデータの収集を開始します。  
  
#### <a name="to-start-an-application-with-the-profiler"></a>プロファイラーを使用してアプリケーションを起動するには  
  
1.  コマンド プロンプトに次のコマンドを入力します。  
  
     [VSPerfCmd](../profiling/vsperfcmd.md) **/start:concurrency  /output:** `OutputFile` [`Options`]  
  
     **/start** を使用するには、[/output](../profiling/output.md)**:**`OutputFile` オプションを指定する必要があります。 `OutputFile` には、プロファイル データ (.vsp) ファイルの名前と場所を指定します。  
  
     **/start:concurrency** オプションと共に、次の表の任意のオプションを指定できます。  
  
    |オプション|説明|  
    |------------|-----------------|  
    |[/wincounter](../profiling/wincounter.md) **:** `WinCounterPath`|プロファイリング実行中に収集する Windows パフォーマンス カウンターを指定します。|  
    |[/automark](../profiling/automark.md) **:** `Interval`|**/wincounter** との組み合わせでのみ使用します。 Windows パフォーマンス カウンター コレクション イベントの間隔をミリ秒単位で指定します。 既定値は 500 です。|  
    |[/events](../profiling/events-vsperfcmd.md) **:** `Config`|プロファイリング実行中に収集する ETW (Event Tracing for Windows) イベントを指定します。 ETW イベントは独立した (.etl) ファイルに収集されます。|  
  
2.  次のように入力して対象アプリケーションを起動します。  
  
     **VSPerfCmd**  [/launch](../profiling/launch.md) **:** `AppName` [`Options`]  
  
     **/launch** オプションと共に、次の表の任意のオプションを指定できます。  
  
    |オプション|説明|  
    |------------|-----------------|  
    |[/args](../profiling/args.md) **:** `Arguments`|対象アプリケーションへ渡されるコマンド ライン引数を格納する文字列を指定します。|  
    |[/console](../profiling/console.md)|対象のコマンド ライン アプリケーションを別のウィンドウで起動でします。|  
    |[/targetclr](../profiling/targetclr.md) **:** `CLRVersion`|アプリケーションに複数のバージョンの CLR (共通言語ランタイム) が読み込まれている場合に、プロファイリングを行う CLR のバージョンを指定します。|  
  
## <a name="controlling-data-collection"></a>データ コレクションの制御  
 対象アプリケーションの実行中は、VSPerfCmd.exe のオプションを使用してファイルへのデータ書き込みを開始および停止することにより、データ収集を制御できます。 データ収集を制御することにより、アプリケーションの起動や終了など、プログラム実行の特定部分のデータを収集できます。  
  
#### <a name="to-start-and-stop-data-collection"></a>データ収集を開始および停止するには  
  
-   次の表に示すオプションの組み合わせにより、データ収集を開始および停止します。 個別のコマンド ラインで各オプションを指定します。 データ収集のオンとオフは複数回切り替えることができます。  
  
    |オプション|説明|  
    |------------|-----------------|  
    |[/globalon /globaloff](../profiling/globalon-and-globaloff.md)|すべてのプロセスのデータ収集を開始 (**/globalon**) または停止 (**/globaloff**) します。|  
    |[/processon](../profiling/processon-and-processoff.md) **:** `PID` [/processoff](../profiling/processon-and-processoff.md) **:** `PID`|プロセス ID (`PID`) で指定されたプロセスのデータ収集を開始 (**/processon**) または停止 (**/processoff**) します。|  
    |[/attach](../profiling/attach.md) **:**{`PID`&#124;`ProcName`} [/detach](../profiling/detach.md)[**:**{`PID`&#124;`ProcName`}]|**/attach** は、プロセス ID (`PID`) またはプロセス名 (*ProcName*) で指定したプロセスのデータ収集を開始します。 **/detach** は、指定されたプロセスのデータ コレクションを停止します。プロセスが指定されていない場合は、すべてのプロセスのデータ コレクションを停止します。|  
  
-   **VSPerfCmd.exe**[/mark](../profiling/mark.md) オプションを使用して、データ ファイルにプロファイル マークを挿入することもできます。 **/mark** コマンドは、識別子、タイム スタンプ、およびオプションのユーザー定義文字列を追加します。 マークは、プロファイラー レポートおよびデータ ビューでデータをフィルター処理するために使用できます。  
  
## <a name="ending-the-profiling-session"></a>プロファイル セッションの終了  
 プロファイル セッションを終了するには、プロファイラーがデータ収集を停止している必要があります。 コンカレンシー データの収集を停止するには **VSPerfCmd /detach** オプションを呼び出して、プロファイリング対象のアプリケーションを終了する必要があります。 次に、**VSPerfCmd /shutdown** オプションを呼び出して、プロファイラーをオフにし、プロファイル データ ファイルを閉じます。  
  
#### <a name="to-end-a-profiling-session"></a>プロファイル セッションを終了するには  
  
1.  対象のアプリケーションを終了するか、コマンド プロンプトで次のコマンドを入力して、アプリケーションからプロファイラーをデタッチします。  
  
     **VSPerfCmd /detach**  
  
2.  コマンド プロンプトに次のコマンドを入力し、プロファイラーを終了します。  
  
     **VSPerfCmd**  [/shutdown](../profiling/shutdown.md)



