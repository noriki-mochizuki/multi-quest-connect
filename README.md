# Multi Quest Connect

Meta Quest側の無線接続準備を担当するアプリと、Windows用の専用USBセットアップです。**QuestBladeも、QuestBlade用Setupも不要です。** Viewerを先にインストールしておく必要もありません。GitHubアカウント・認証キー・開発環境は利用時に不要です。

## 初回：同じPCでUSBセットアップ

1. [Connect専用Setup0.4.2](https://github.com/noriki-mochizuki/multi-quest-connect/releases/tag/setup-v0.4.2)から **MultiQuestConnect-Setup.zip** を取得し、全ファイルを展開します。
2. **Multi Quest Connect Setup.exe** を起動します。.NETと必要なADB、Connect APKを同梱しています。
3. QuestのDeveloper Modeを準備し、PCとQuestを同じLANへ接続します。USBデータケーブルでつなぎ、Quest内のUSBデバッグ許可で、信頼するPCでは **「このパソコンから常に許可」** を本人が選びます。PCによってはMeta公式USBドライバーの別途導入が必要です。
4. セットアップで対象Questを選び、導入・設定を実行します。Connectを上書き導入し、必要な権限とサービス、無線ADBを設定し、USBとLANの実機IDが一致した接続先だけPCへ登録します。
   Connect導入済みの場合は「そのまま使う／再インストールする」を尋ねます。初期選択は「そのまま使う」。再インストールは設定を保持する上書きで、アンインストールやデータ消去は行いません。導入済みの方が新しい場合はダウングレードせず、そのまま使います。
5. 完了後にUSBを外し、[Multi Quest Viewerのインストーラー](https://github.com/noriki-mochizuki/multi-quest-viewer/releases/latest)を同じWindowsユーザーでインストールして起動します。Viewer0.9.1以降が、専用セットアップの登録を読み込みます。

表示するVRアプリは利用者がQuest上で起動します。QuestBladeを先に起動・接続する必要はありません。Viewerの通常のQuest表示を使用してください。QuestBlade専用のゲーム内配信もViewerの選択肢として残ります。

**信頼関係はPCごとです。** 別PCでは、そのPCで初回のUSB設定・信頼確認を行う必要がある場合があります。PCの通常のADB認証鍵を継続利用し、毎回生成・削除しません。Quest標準の許可画面は自動操作しません。

## 普段の利用

認証済みのPCとQuestを同じLANへ接続し、Viewerを起動します。初回設定後はUSBを外して使用する構成です。ConnectがQuest側を準備し、Viewerが接続・映像表示を担当します。登録はPCのローカル領域に保存し、個体ラベルはViewerで設定します。

OSやルーターによって無線デバッグ・mDNS・再起動後の認証挙動が異なります。接続できない場合はUSBでセットアップを再実行してください。再起動後の完全自動接続は実機未確認です。アプリのデータ消去やアンインストールで解決しないでください。

## Connect自身を更新

1. Questのアプリ一覧から **Multi Quest Connect** を開きます。
2. **更新を確認** → 新版があれば **新版をダウンロード**。
3. 初回は、このアプリからのインストールを本人が許可します。
4. 戻って **更新をインストール** → Quest標準の確認画面でインストールします。完了後にConnectを開き直します。

Viewer・QuestBladeの起動は不要です。公開GitHubから鍵なしで取得し、署名・ID・版・SHA-256・サイズを確認します。通信失敗・オフライン・中断でも既存のLAN接続機能は使用できます。既存と同じappId `jp.mqv.companion` と署名を使い、設定を保持する上書き方式です。

## 配布物と検証段階

Releaseには `multi-quest-connect.apk`、Windows用ZIP、`connect-update.json`、この説明、ライセンス・チェックサムを添付します。署名鍵、PC認証鍵、端末情報、設定・ログ、意図しないソース・ゲーム素材は含みません。QuestBladeの非公開配布は別です。

PCのJavaテスト・実APK署名検証・Windows設定ツールの模擬試験・所有ADBの後始末・WPF表示・公開ファイル取得を確認します。**Quest実機への導入・USB切離し・他のVRアプリ表示・実更新・権限／設定保持・再起動・オフラインLANは未確認です。** Viewerの実機同時上限2台を維持し、模擬試験を実機6台の受入とは扱いません。

Windows実行ファイルは未コード署名のため、SmartScreen等で確認が出る場合があります。利用・再配布条件と各OSSのNOTICEは添付LICENSE.txtとZIP内を参照してください。
