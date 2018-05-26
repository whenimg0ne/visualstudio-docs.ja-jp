
1. ASP.NET プロジェクトを Visual Studio で開くがあるコンピューターで、ソリューション エクスプ ローラーでプロジェクトを右クリックし **発行**です。

1. 任意の発行プロファイルを構成していない場合、**発行**ウィンドウが表示されます。 をクリックして**新しいプロファイルを作成**です。

1. **発行先の選択**ダイアログ ボックスで、をクリックして**プロファイルのインポート**です。

    ![選択を発行](../../deployment/media/tutorial-publish-tool-import-profile.png)

1. 前のセクションで作成した発行設定ファイルの場所に移動します。

1. **発行設定ファイルのインポート**ダイアログ ボックスに移動し、前のセクションで作成したプロファイルを選択し、をクリックして**開く**です。

    Visual Studio は、展開プロセスを開始し、進行状況と結果は、出力ウィンドウを示しています。

    場合は、任意の展開エラーが発生する、クリックして**設定**設定を編集します。 設定を変更し、をクリックして**検証**新しい設定をテストします。 ホスト名が見つからない場合は、内のホスト名の代わりに IP アドレスを再試行してください、**サーバー**と**送信先 URL**フィールドです。

    ![発行ツールで設定を編集します。](../../deployment/media/tutorial-configure-publish-settings-in-tool.png)