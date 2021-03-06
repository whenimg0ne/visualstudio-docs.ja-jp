---
title: 使用した分離シェルを変更します。Pkgdef ファイル |Microsoft Docs
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
- Visual Studio shell, isolated mode%2C .pkgdef file
ms.assetid: 69e8f78e-bcf1-46cb-8866-7de37d134997
caps.latest.revision: 28
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: f70036f91eb52d85054465e6eea9f82672d851f6
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "47540162"
---
# <a name="modifying-the-isolated-shell-by-using-the-pkgdef-file"></a>使用した分離シェルを変更します。Pkgdef ファイル
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

このトピックの最新バージョンをご覧[分離シェルを使用して変更します。Pkgdef ファイル](https://docs.microsoft.com/visualstudio/extensibility/modifying-the-isolated-shell-by-using-the-dot-pkgdef-file)します。  
  
.Pkgdef ファイルには、分離シェル アプリケーションをカスタマイズに使用できる設定がサポートしています。 これには、アプリケーションがコンピューターにインストールされているし、アプリケーションを開始するときに、Visual Studio shell によって参照されているときに作成される値を指定します。 設定は、該当するレジストリ キーに基づくファイルで構成されます。  
  
> [!WARNING]
>  Visual Studio の起動時、VSPackage の .vsixmanifest ファイルで宣言されていない .pkgdef ファイルはスキャンされませんに注意してください。  
  
 .Pkgdef ファイルには、各によって識別される、キー、いずれかのセクションが含まれています。`[$RootKey$]`または`[$RootKey$\`*サブキー*`]`$RootKey。 $embedded$ には、アプリケーションのルート キーです。  
  
 各セクションには、次の形式を持つ名前/値ペアが含まれています: `"` *ValueName*`"=`*値*します。  
  
 値は引用符で囲まれた文字列または dword として表される 32 ビット整数のいずれか。 値には、次の制約があります。  
  
-   たとえば、16 進数形式ですべて dword 値`dword:00000001`します。  
  
     ブール値は、1 が true の場合に表し、0 は false を表します。  
  
-   たとえばがレジストリ形式ですべての GUID 文字列`"{00000000-0000-0000-0000-000000000000}"`します。  
  
-   すべてのローカライズ可能なリソース識別子があるフォーム"@*resourceID*"または"#*resourceID*"ここで、 *resourceID*アプリケーションの UI パッケージのリソース id ですたとえば、`"@102"`します。 アプリケーション UI パッケージ AppLocalizationPackage 設定で参照されているパッケージでは。  
  
 たとえば、オブジェクトに適用された  
  
```  
"HideSolutionConcept"=dword:00000001  
"DefaultDebugEngine"="{00000000-0000-0000-0000-000000000000}"  
```  
  
 .Pkgdef ファイルにコメントを追加することができます。 単一行コメントは、最初の 2 つの文字と 2 つのスラッシュを持ちます。  
  
 代替文字列の一覧は、次を参照してください。[で置換文字列を使用します。Pkgdef とします。Pkgundef ファイル](../extensibility/substitution-strings-used-in-dot-pkgdef-and-dot-pkgundef-files.md)します。  
  
 次のセクションでは、分離モードで Visual Studio シェルの動作に影響する特定のレジストリ値について説明します。 このファイルで、アプリケーションの追加のレジストリ値を定義することもできます。  
  
> [!NOTE]
>  .Pkgdef ファイルで設定を指定しない場合、対応するエントリは行われません、レジストリで。  
  
## <a name="settings"></a>設定  
 次の表では、[$RootKey$] の下で定義された値について説明します。  
  
|名前|型|[値]|  
|----------|----------|-----------|  
|AddinsAllowed|dword|True の場合は、アドインを読み込むことができます。それ以外の場合、false です。<br /><br /> 既定値は true です。|  
|AllowsDroppedFilesOnMainWindow|dword|メイン ウィンドウがドロップされたファイルは; を受け入れることができる場合は true。それ以外の場合、false です。 使用して開かれているメイン ウィンドウで削除されたファイル、<xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument.OpenDocumentViaProject%2A>メソッド。 これを使用してドキュメントを開くために、**オープン**コマンドを**ファイル**アプリケーションのメニュー。<br /><br /> 既定値は true です。|  
|AppIcon|string|プログラム アイコンの完全パス。 このアイコンは、アプリケーション名の左側に、タイトル バーに表示されます。<br /><br /> 既定値は"$RootFolder$\\*solutionName*.ico"ここで、 *solutionName*アプリケーション ソリューション ファイルの名前を指定します。|  
|AppLocalizationPackage|string|アプリケーションの UI のサテライト アセンブリを含む VSPackage の GUID です。 この VSPackage は、.vsct ファイルのコンパイル済みのバージョンを含み、他のローカライズされた文字列を含めることができます。 機能セットとメニュー コマンドは、グループを有効になっているか、UI プロジェクトの .vsct ファイルの設定を変更することで無効になっています。<br /><br /> 既定値は"{*vsUiPackageGuid*}"ここで、 *vsUiPackageGuid*はアプリケーションの UI パッケージに割り当てられた GUID です。|  
|アプリ名|string|アプリケーションの名前。 アプリケーション ウィンドウのタイトル バーに名前が表示されます。<br /><br /> 既定値では、アプリケーションのソリューション ファイルの名前です。|  
|CommandLineLogo|string|コンソール ウィンドウで、アプリケーションの実行時に、バナー テキスト。 この設定では、コマンド ライン ビルド操作をサポートするアプリケーションのみに影響します。<br /><br /> 既定値は"*companyName * * solutionName*バージョン 1.0"ここで、 *companyName* 、Windows のインストール時に提供されている会社の名前を指定し、 *solutionName*。アプリケーション ソリューション ファイルの名前を指定します。|  
|DefaultDebugEngine|string|既定の GUID はデバッグ、アプリケーションで使用するエンジンです。<br /><br /> 注: 空の GUID (すべてゼロ) では、アプリケーションに既定のデバッグ エンジンが指定されていないことを示します。 これにより、デバッガーを使用するデバッグ エンジンを選択します。<br /><br /> 既定値は "{00000000-0000-0000-0000-000000000000}" です。|  
|DefaultHomePage|string|内部の Web ブラウザー ウィンドウの既定のホーム ページの URL。<br /><br /> 場合、**ホーム ページ**オプションは、アプリケーションで使用し、この設定は、オプションの既定の状態も影響します。 詳細については、次を参照してください。[環境では、Web ブラウザーのオプション ダイアログ ボックス](../ide/reference/web-browser-environment-options-dialog-box.md)します。<br /><br /> 既定値は、Windows のインストール時に提供されている会社の URL です。|  
|DefaultProjectsLocation|string|既定のプロジェクト フォルダーの完全パス。 たとえば、オブジェクトに適用された<br /><br /> `"DefaultProjectsLocation"="$MyDocuments$\MyVSShellStub\Projects"`<br /><br /> 場合、 **Visual Studio プロジェクトの場所**オプションは、アプリケーションで使用し、この設定は、オプションの既定の状態も影響します。 詳細については、次を参照してください。 [NIB: [全般]、プロジェクトおよびソリューション オプション] ダイアログ ボックス](http://msdn.microsoft.com/en-us/8f8e37e8-b28d-4b13-bfeb-ea4d3312aeca)します。<br /><br /> 既定値は"$MyDocuments$\\*solutionName*"ここで、 *solutionName*アプリケーション ソリューション ファイルの名前を指定します。|  
|DefaultSearchPage|string|内部の Web ブラウザー ウィンドウの既定の検索ページ URL。<br /><br /> 場合、**検索ページ**オプションは、アプリケーションで使用し、この設定は、オプションの既定の状態も影響します。 詳細については、次を参照してください。[環境では、Web ブラウザーのオプション ダイアログ ボックス](../ide/reference/web-browser-environment-options-dialog-box.md)します。<br /><br /> 既定値は "http://search.live.com" です。|  
|DefaultUserFilesFolderRoot|string|現在のユーザーの基準とした、ユーザー フォルダーの名前はのマイ ドキュメント フォルダーです。<br /><br /> 既定値では、アプリケーションのソリューション ファイルの名前です。|  
|DisableOutputWindow|dword|分離シェルに出力ウィンドウを扱う必要があります無効になっているかどうかを示します。<br /><br /> この値が設定されている場合は true、Visual Studio 出力は表示されず、ソリューション ビルド マネージャーで、**出力**ウィンドウと非表示に、**ビルド開始時に出力を表示するウィンドウ** チェック ボックス、 **プロジェクトおよびソリューション**カテゴリで、**オプション** ダイアログ ボックス。<br /><br /> 既定値は false です。|  
|HideMiscellaneousFilesByDefault|dword|非表示にする場合は true、**その他のファイル**フォルダーで既定**ソリューション エクスプ ローラー**場合は false。<br /><br /> 場合、**ソリューション エクスプ ローラーで表示するその他のファイル**オプションは、アプリケーションで使用し、この設定は、オプションの既定の状態も影響します。 詳細については、次を参照してください。[オプション] ダイアログ ボックスの [ドキュメント](../ide/reference/documents-environment-options-dialog-box.md)します。<br /><br /> 既定値は false です。|  
|HideSolutionConcept|dword|スタンドアロン プロジェクトのすべてのプロジェクトを作成し、既定では、ソリューションとプロジェクトのスタンドアロン ソリューションに関連するコマンドを非表示にする場合は trueそれ以外の場合、false です。<br /><br /> 場合、**常にソリューションを表示する**オプションは、アプリケーションで使用し、この設定は、オプションの既定の状態も影響します。 詳細については、次を参照してください。 [NIB: [全般]、プロジェクトおよびソリューション オプション] ダイアログ ボックス](http://msdn.microsoft.com/en-us/8f8e37e8-b28d-4b13-bfeb-ea4d3312aeca)します。<br /><br /> 既定値は false です。|  
|NewProjDlgInstalledTemplatesHdr|string|Visual Studio のインストール済みテンプレート ヘッダーの名前、**テンプレート**の一覧で、**新しいプロジェクト** ダイアログ ボックス。 これは、文字列またはアプリケーションの UI パッケージから読み込まれる、ローカライズ可能なリソース識別子です。<br /><br /> 既定値は"*solutionName*にインストールされたテンプレート"ここで、 *solutionName*アプリケーション ソリューション ファイルの名前を指定します。|  
|NewProjDlgSlnTreeNodeTitle|string|名前、 **Visual Studio ソリューション**内のノード、**プロジェクトの種類**ツリーで、**新しいプロジェクト** ダイアログ ボックス。 これは、文字列またはアプリケーションの UI パッケージから読み込まれる、ローカライズ可能なリソース識別子です。<br /><br /> 既定値は"*solutionName*にインストールされたテンプレート"ここで、 *solutionName*アプリケーション ソリューション ファイルの名前を指定します。|  
|SolutionFileCreatorIdentifier|string|アプリケーション id、アプリケーションによって生成されるソリューション ファイルの 2 つ目の行として表示されます。 この行は、ファイルを作成したアプリケーションを示します。 慣例により、この値には、アプリケーションとアプリケーションのバージョン番号の名両方にはが含まれます。 たとえば、オブジェクトに適用された<br /><br /> `"SolutionFileCreatorIdentifier"="MyVSShellStub Solution File, Format Version 10.00"`<br /><br /> VSLauncher.exe プログラムを Visual Studio ソリューション ファイルを開くときの既定のプログラムでは、この 2 行目を使用して、ソリューション ファイルを開くときに Visual Studio のバージョンを確認します。 アプリケーションでは、その関連するソリューション ファイルを処理するために、独自のランチャーを必要があります。 ランチャーはこの 2 行目でソリューションを開くアプリケーションのバージョンを決定するソリューション ファイルの使用もできます。<br /><br /> 注: Visual Studio VSLauncher.exe プログラムは、分離シェル アプリケーションによって作成された .sln ファイルを処理しません。<br /><br /> 既定値は"*solutionName*ソリューション ファイル、$10.00" 形式のバージョン、 *solutionName*アプリケーション ソリューション ファイルの名前を指定します。|  
|SolutionFileExt|string|アプリケーションのソリューション ファイル名拡張子。 一意のファイル名拡張子 (not.sln) を選択することをお勧めします。<br /><br /> 既定値は"*solutionName*_sln"ここで、 *solutionName*アプリケーション ソリューション ファイルの名前を指定します。|  
|SplashScreenBitmap|string|アプリケーションのスプラッシュ スクリーンのビットマップ ファイルの完全なパス。<br /><br /> 既定値は、"$RootFolder$\Splash.bmp"です。|  
|ThisVersionDTECLSID|string|アプリケーションのオートメーション オブジェクトのクラス id (CLSID)。<br /><br /> アプリケーションのオートメーション オブジェクトは、Visual Studio シェルのオートメーション モデルおよび実装でのアプリケーションのトップレベルのオブジェクト、<xref:EnvDTE._DTE?displayProperty=fullName>インターフェイス。<br /><br /> Hkey_classes_root \clsid レジストリ キーの下のアプリケーションのオートメーション オブジェクトが正しく登録されているかどうかを使用して、 [CComPtrBase::CoCreateInstance](http://msdn.microsoft.com/library/c0965041-6cb6-40c5-b272-2b99f02668a6)を直接、アプリケーションのインスタンスを作成する関数。<br /><br /> Visual Studio shell では、この CLSID を使用して、ACTIVEOBJECT_WEAK フラグを使用して、アプリケーションのオートメーション オブジェクトを実行しているオブジェクト テーブル (ROT) で登録します。 これにより使用できます、 [GetActiveObject](http://msdn.microsoft.com/en-us/a276e30c-6a7f-4cde-9639-21a9f5170b62)アプリケーションの実行中のインスタンスへのポインターを取得します。 さらに、アプリケーションのオートメーション オブジェクトの ProgID を定義する場合 Visual Studio shell はまた、アプリケーションの各インスタンスに登録 ROT アイテム フォームのモニカーを使用して*progID*:*processID*ここで、 *progID*は、アプリケーションのオートメーション オブジェクトの ProgID および*processID*はアプリケーションのインスタンスのプロセス識別子です。 たとえば、次のように、モニカーを作成するとします。<br /><br /> `CreateItemMoniker(L"!",`  *instanceString* `, &instanceMoniker)`<br /><br /> 場所`instanceString`は、 *progID*:*processID*文字列。 使用できます`instanceMoniker`インスタンスの取得に回転 GetObject 関数を使用します。<br /><br /> ThisVersionDTECLSID 設定を省略した場合、アプリケーションにはコンポーネント オブジェクト モデル (COM) を通じて項目公開されません。 ここでは、呼び出すことによって、アプリケーションのインスタンスを作成できません、 [CComPtrBase::CoCreateInstance](http://msdn.microsoft.com/library/c0965041-6cb6-40c5-b272-2b99f02668a6)機能し、ROT に登録することはできません。<br /><br /> VSPackage の各バージョンには、異なる CLSID が必要です。<br /><br /> 既定値には、Visual Studio は、アプリケーションのオートメーション オブジェクトに対して生成される GUID です。|  
|ThisVersionSolutionCLSID|string|アプリケーションのソリューション オブジェクトの CLSID。<br /><br /> ソリューションのオートメーション オブジェクトは、アプリケーションと実装のインスタンスで現在開いているソリューションに関する情報を格納、<xref:EnvDTE._Solution?displayProperty=fullName>インターフェイス。<br /><br /> Hkey_classes_root \clsid レジストリ キーの下のソリューションのオートメーション オブジェクトが正しく登録されているかどうかを使用して、 [CComPtrBase::CoCreateInstance](http://msdn.microsoft.com/library/c0965041-6cb6-40c5-b272-2b99f02668a6)を直接アプリケーションのソリューション オブジェクトを作成する関数。<br /><br /> Visual Studio shell では、この CLSID を使用して、ACTIVEOBJECT_WEAK フラグを使用してソリューションのオートメーション オブジェクトを ROT に登録します。<br /><br /> この設定を省略すると、し、ソリューションのクラスはコンポーネント オブジェクト モデル (COM) に登録されていません、呼び出すことによって、ソリューションのオブジェクトを作成できない場合、 [CComPtrBase::CoCreateInstance](http://msdn.microsoft.com/library/c0965041-6cb6-40c5-b272-2b99f02668a6)関数を登録することはできませんROT します。<br /><br /> 既定値は、Visual Studio がアプリケーションのソリューション オブジェクトに対して生成される GUID です。|  
|UserFilesSubFolderName|string|ユーザー ファイルとサブフォルダーに作成し、アプリケーション ユーザーのマイ ドキュメント フォルダーのサブフォルダーの名前。<br /><br /> 既定値では、アプリケーションのソリューション ファイルの名前です。|  
|UserOptsFileExt|string|アプリケーションのソリューション ユーザー オプション ファイルの拡張機能。<br /><br /> 既定値では、アプリケーションのソリューション ファイルの名前です。|  
  
## <a name="binding-path-settings"></a>バインド パスの設定  
 [$RootKey$ \BindingPaths\\{00000000-0000-0000-0000-000000000000}] キーには、シェルがアセンブリをチェックするディレクトリの一覧が含まれています。 これらのディレクトリは、シェルは、アプリケーションのプライベート アセンブリがプローブされるディレクトリの一覧に追加されます。  
  
 既定では、バインド パスのエントリに追加されますありません .pkgdef ファイル。 ただし、Visual Studio のインストール ディレクトリの次のサブディレクトリは、レジストリのアプリケーション バインド パスの一覧に自動的に追加されます。  
  
-   Common7 \ide\  
  
-   Common7\IDE\\\PrivateAssemblies  
  
-   Common7\IDE\\\PublicAssemblies  
  
 バインド パスにディレクトリを追加するには、フォームのエントリを追加"*directoryName*「=」"という*directoryName*絶対パスです。 たとえば、オブジェクトに適用された  
  
```  
[$RootKey$\BindingPaths\{00000000-0000-0000-0000-000000000000}]  
"$RootFolder$\directory1"=""  
"%CommonProgramFiles%\directory2"=""  
```  
  
## <a name="profile-settings"></a>プロファイルの設定  
 次の表では、[$RootKey$ \Profile] [関連付けられている各パッケージに対して定義されている値について説明します。  
  
|名前|型|[値]|  
|----------|----------|-----------|  
|AutoSaveFile|string|アプリケーションが自動保存ファイルを格納するディレクトリ。<br /><br /> 既定値は、"$RootFolder$\Profiles\CurrentSettings.vssettings"です。|  
  
## <a name="package-satellite-dll-settings"></a>パッケージ サテライト DLL の設定  
 次の表に、値で定義されている [$RootKey$ \Packages\\{*vsPackageGuid*} \SatelliteDll] サテライト DLL は、関連付けられている各パッケージの場所*vsPackageGuid* 、関連付けられたパッケージの GUID です。  
  
|名前|型|[値]|  
|----------|----------|-----------|  
|DllName|string|DLL のファイル名。<br /><br /> 既定値は"*solutionName*ui.dll"ここで、 *solutionName*アプリケーション ソリューション ファイルの名前を指定します。|  
|パス|string|サテライト DLL を格納するディレクトリ。<br /><br /> 既定値は、「$PackageFolder$」です。|  
  
## <a name="package-menu-item-settings"></a>パッケージのメニュー項目の設定  
 [$RootKey$ \Menus] レジストリ キーは、アプリケーションの UI リソース ファイルを定義します。  
  
 メニュー項目の値があるフォーム"{*vsUiPackageGuid*}「=」 *resourceId*、 *versionNumber*"ここで、 *vsUiPackageGuid*の GUID ですアプリケーションの UI パッケージ*resourceId*は、UI 要素を含む CTMENU のリソースのリソース識別子と*versionNumber* CTMENU の仮想バージョン番号は、リソースです。 詳細については、次を参照してください。[相互運用機能アセンブリ コマンド ハンドラーの登録](../extensibility/internals/registering-interop-assembly-command-handlers.md)します。  
  
 既定では、メニュー項目は、アプリケーションの UI パッケージ .pkgdef ファイルに作成されます。  
  
 メニュー項目を提供して、アプリケーションの一部として付属している各パッケージのパッケージのメニュー項目を追加します。  
  
## <a name="see-also"></a>関連項目  
 [分離シェルのカスタマイズ](../extensibility/customizing-the-isolated-shell.md)   
 [.pkgundef ファイル](../extensibility/modifying-the-isolated-shell-by-using-the-dot-pkgundef-file.md)

