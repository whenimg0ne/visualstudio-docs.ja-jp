---
title: Visual Studio でのリモート デバッグ |Microsoft Docs
ms.custom: remotedebugging
ms.date: 07/02/2018
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.debug.remote.overview
dev_langs:
- C++
- FSharp
- CSharp
- JScript
- VB
helpviewer_keywords:
- remote debugging, setup
ms.assetid: 5a94ad64-100d-43ca-9779-16cb5af86f97
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 46913c1bb671c1986c4f302a84d4183fe17f5878
ms.sourcegitcommit: c57ae28181ffe14a30731736661bf59c3eff1211
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/11/2018
ms.locfileid: "38778295"
---
# <a name="remote-debugging"></a>Remote Debugging
別のコンピューターに配置されている Visual Studio アプリケーションをデバッグすることができます。 このデバッグを行うには、Visual Studio リモート デバッガーを使用します。

リモート デバッグに関する詳細な手順については、これらのトピックを参照してください。

|シナリオ|リンク|
|-|-|-|
|Azure App Service|[スナップショット デバッガー](../debugger/debug-live-azure-applications.md)または[Azure での ASP.NET のリモート デバッグ](../debugger/remote-debugging-azure.md)|
|Azure 仮想マシン|[Azure での ASP.NET のリモート デバッグ](../debugger/remote-debugging-azure.md)|
|Azure Service Fabric|[Azure Service Fabric アプリケーションをデバッグします。](/azure/service-fabric/service-fabric-debugging-your-application#debug-a-remote-service-fabric-application)|
|ASP.NET|[ASP.NET Core のリモート デバッグ](../debugger/remote-debugging-aspnet-on-a-remote-iis-computer.md)または[リモート デバッグの ASP.NET](../debugger/remote-debugging-aspnet-on-a-remote-iis-7-5-computer.md)|
|C# または Visual Basic|[C# プロジェクトまたは Visual Basic プロジェクトのリモート デバッグ](../debugger/remote-debugging-csharp.md)|
|C++|[C++ Project プロジェクトのリモート デバッグ](../debugger/remote-debugging-cpp.md)|
|ユニバーサル Windows アプリ (UWP)|[リモート コンピューターで UWP アプリを実行](../debugger/run-windows-store-apps-on-a-remote-machine.md)または[インストールされているアプリ パッケージのデバッグ](../debugger/debug-installed-app-package.md)|

だけをダウンロードして、リモート デバッガーをインストールして、実際のシナリオについて、追加の手順は不要する場合、はこの記事の手順に従います。

## <a name="download-and-install-the-remote-tools"></a>ダウンロードして、リモート ツールのインストール

[!INCLUDE [remote-debugger-download](../debugger/includes/remote-debugger-download.md)]

## <a name="unblock_msvsmon"></a> Windows Server のリモート ツールのダウンロードをブロック解除します。

Windows Server 上の Internet Explorer で、既定のセキュリティ設定により、リモート ツールなどのコンポーネントをダウンロードする時間がかかる。

* Web サイトを開くと、リソースを含むドメインが明示的に許可しない限り、web リソースへのアクセスが阻止される Internet explorer セキュリティ強化の構成が有効になっている (つまり、信頼されている)。 この設定を無効にすることができます、お勧めしません可能性があるためには、セキュリティ リスクです。

* 既定の設定、Windows Server 2016 で**インターネット オプション** > **セキュリティ** > **インターネット** >  **カスタム レベル** > **ダウンロード**ファイルのダウンロードも無効にします。 Windows サーバー上で直接リモート ツールをダウンロードする場合は、ファイルのダウンロードを有効にする必要があります。

Windows Server 上のツールをダウンロードするには、次のいずれかを勧め。

* 1 つ実行中の Visual Studio などの別のコンピューターにリモート ツールをダウンロードし、コピー、 *.exe*ファイルを Windows サーバーにします。

* リモート デバッガーを実行する[ファイル共有から](#fileshare_msvsmon)Visual Studio コンピューターにします。

* Windows サーバー上で直接リモート ツールをダウンロードし、信頼済みサイトを追加するプロンプトに同意します。 多くの場合、最新の web サイトには、これにより、多くのプロンプトのため、多くのサードパーティのリソースが含まれます。 さらに、リダイレクトされたリンクは、手動で追加する必要があります。 ダウンロードを開始する前に、信頼済みサイトの一部を追加することができます。 移動して**インターネット オプション > セキュリティ > 信頼済みサイト > サイト**し、次のサイトを追加します。

  * visualstudio.microsoft.com
  * download.visualstudio.microsoft.com
  * 方法: 空

  My.visualstudio.com にデバッガーの古いバージョンは、これらの追加サイトをそのログインが成功したかどうかを確認を追加します。

  * microsoft.com
  * go.microsoft.com
  * download.microsoft.com
  * my.visualstudio.com
  * login.microsoftonline.com
  * login.live.com
  * secure.aadcdn.microsoftonline されました。
  * msft.sts.microsoft.com
  * auth.gfx.ms
  * app.vssps.visualstudio.com
  * vlscppe.microsoft.com
  * query.prod.cms.rt.microsoft.com

    選択して、リモート ツールのダウンロード中にこれらのドメインを追加する場合は**追加**入力を求められたらします。

    ![ブロックされたコンテンツ ダイアログ ボックス](../debugger/media/remotedbg-blocked-content.png)

    ソフトウェアをダウンロードすると、さまざまな web サイトのスクリプトおよびリソースを読み込むためのアクセス許可を与えるいくつか追加の要求が表示されます。 My.visualstudio.com でそのログインが成功したかどうかを確認する追加のドメインを追加することをお勧めします。

## <a name="requirements_msvsmon"></a> 必要条件

[!INCLUDE [remote-debugger-requirements](../debugger/includes/remote-debugger-requirements.md)]

## <a name="fileshare_msvsmon"></a> (省略可能)ファイル共有からリモート デバッガーを実行するには

リモート デバッガーを検索することができます (*msvsmon.exe*) Visual Studio Community、Professional、または Enterprise が既にインストールされているコンピューターでします。 シナリオによっては、リモート デバッグをセットアップする最も簡単な方法では、ファイル共有からリモート デバッガー (msvsmon.exe) を実行します。 使用量の制限については、リモート デバッガーのヘルプ ページを参照してください (**ヘルプ > 使用状況**リモート デバッガーで)。

1. 検索*msvsmon.exe*で Visual Studio のバージョンに一致するディレクトリ。 Visual Studio enterprise 2017。

      *Program Files (x86) \Microsoft Visual Studio\2017\Enterprise\Common7\IDE\Remote Debugger\x86\msvsmon.exe*

      *Program Files (x86) \Microsoft Visual Studio\2017\Enterprise\Common7\IDE\Remote Debugger\x64\msvsmon.exe*

2. 共有、**リモート デバッガー** Visual Studio コンピューター上のフォルダー。

3. リモートのコンピューターで実行して*msvsmon.exe*共有フォルダーから。 に従って、[セットアップ手順](#bkmk_setup)します。

> [!TIP]
> コマンド ライン インストールおよびコマンド ライン リファレンスでは、ヘルプ ページをご覧ください*msvsmon.exe* 」と入力して``msvsmon.exe /?``で Visual Studio がインストールされているコンピューターでコマンドラインで (に移動または**ヘルプ > 使用状況**リモート デバッガーで)。

## <a name="bkmk_setup"></a> リモート デバッガーを設定します。

[!INCLUDE [remote-debugger-configuration](../debugger/includes/remote-debugger-configuration.md)]

### <a name="configure_msvsmon"></a> リモート デバッガーを構成します。
リモート デバッガーを初めて起動した後、リモート デバッガーの構成の一部を変更できます。

-   リモート デバッガーへの接続を選択するには、他のユーザーのアクセス許可を追加する必要がある場合**ツール > アクセス許可**します。 アクセス許可を付与または拒否するには、管理者特権が必要です。

     > [!IMPORTANT]
     > Visual Studio コンピューターを使用しているユーザー アカウントとは異なるユーザー アカウントでリモート デバッガーを実行することができますが、リモート デバッガーのアクセス許可を別のユーザー アカウントを追加する必要があります。

     または、使用してコマンドラインからリモート デバッガーを起動、 **/allow\<ユーザー名 >** パラメーター: **msvsmon/allow \< username@computer>** します。

-   認証モードや、ポート番号を変更したり、リモート ツールのタイムアウト値を指定する必要がある場合: 選択**ツール > オプション**します。

     既定で使用されるポート番号の一覧については、次を参照してください。 [Remote Debugger Port Assignments](../debugger/remote-debugger-port-assignments.md)します。

     > [!WARNING]
     >  リモート ツールを [認証なし] モードで実行することも選択できますが、このモードの使用は避けることを強く推奨します。 このモードで実行した場合、ネットワーク セキュリティはまったく提供されません。 [認証なし] モードは、ネットワークに悪意のあるコードや悪意のあるトラフィックのリスクがないことが確実である場合にのみ選択してください。

##  <a name="bkmk_configureService"></a> (省略可能)サービスとしてリモート デバッガーを構成します。
ASP.NET およびその他のサーバー環境でデバッグ、リモート デバッガーを管理者として実行かを常に実行する場合は、サービスとしてリモート デバッガーを実行します。

 サービスとしてリモート デバッガーを構成するには、以下の手順を実行します。

1.  **リモート デバッガー構成ウィザード** (rdbgwiz.exe) を見つけます (このアプリケーションは、リモート デバッガーとは別のアプリケーションです)。このアプリケーションは、リモート ツールをインストールした場合にのみ入手でき、 Visual Studio と共にはインストールされません。

2.  構成ウィザードの実行を開始します。 最初のページが表示されたら、 **[次へ]** をクリックします。

3.  **[Visual Studio 2015 リモート デバッガー サービスを実行する]** チェック ボックスをオンにします。

4.  ユーザー アカウントの名前とパスワードを追加します。

     追加する必要があります、**サービスとしてログオン**ユーザー権限をこのアカウント (検索**ローカル セキュリティ ポリシー** (secpol.msc) で、**開始**ページまたはウィンドウ (または型**secpol**コマンド プロンプトで)。 ウィンドウが表示されたら、 **[ユーザー権利の割り当て]** をダブルクリックし、右ペインで **[サービスとしてログオン]** を見つけます。 これをダブルクリックします。 ユーザー アカウントを追加、**プロパティ**ウィンドウをクリックします**OK**)。 **[次へ]** をクリックします。

5.  リモート ツールが通信するネットワークの種類を選択します。 少なくとも 1 つのネットワークの種類を選択する必要があります。 コンピューターがドメインを介して接続されている場合は、最初の項目を選択する必要があります。 コンピューターがワークグループまたはホーム グループを介して接続されている場合は、2 番目または 3 番目の項目を選択する必要があります。 **[次へ]** をクリックします。

6.  サービスを開始できた場合は、「 **Visual Studio リモート デバッガー構成ウィザードは正常に完了しました**」と表示されます。 サービスを開始できなかった場合は、「 **Visual Studio リモート デバッガー構成ウィザードを完了できませんでした**」と表示されます。 このページには、サービスを開始するために従う必要があるヒントもいくつか提供されます。

7.  **[完了]** をクリックします。

 この時点で、リモート デバッガーはサービスとして実行されています。 これを確認するに移動して**コントロール パネル > サービス**を探して**Visual Studio 2015 リモート デバッガー**。

 停止してから、リモート デバッガー サービスを再開**コントロール パネル > サービス**します。

## <a name="set-up-debugging-with-remote-symbols"></a>リモート シンボルを使用したデバッグのセットアップ

[!INCLUDE [remote-debugger-symbols](../debugger/includes/remote-debugger-symbols.md)]

## <a name="see-also"></a>関連項目

- [デバッガー機能ツアー](../debugger/debugger-feature-tour.md)
- [Windows ファイアウォールをリモート デバッグ用に構成する](../debugger/configure-the-windows-firewall-for-remote-debugging.md)
- [リモート デバッガーのポートの割り当て](../debugger/remote-debugger-port-assignments.md)
- [リモート デバッグ、リモートの IIS コンピューター上の ASP.NET Core](../debugger/remote-debugging-aspnet-on-a-remote-iis-computer.md)
- [リモート デバッグ エラーとトラブルシューティング](../debugger/remote-debugging-errors-and-troubleshooting.md)