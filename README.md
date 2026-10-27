# Multi Quest Connect 0.4.0

QuestとWindowsのMulti Quest Viewerをつなぐ補助アプリです。QuestBladeやGitHub認証キーは不要です。USB Setupは **0.4.3** です。

1. [このRelease](https://github.com/noriki-mochizuki/multi-quest-connect/releases/tag/v0.4.0) の **MultiQuestConnect-Setup.zip** を取得し、全ファイルを新しいフォルダーに展開します。
2. QuestをUSB接続し、**Multi Quest Connect Setup.exe** を開きます。Quest内のUSBデバッグ許可は本人が行い、信頼するPCでは「このパソコンから常に許可」を選びます。
3. 接続を設定します。導入済みなら「そのまま使う」が初期選択です。「再インストール」もデータを保持する上書きで、アンインストールやダウングレードは行いません。
4. USBを外し、同じLANでViewerを起動します。Viewerは独立した [公開インストーラー](https://github.com/noriki-mochizuki/multi-quest-viewer/releases/latest) から導入できます。

0.4.0は共通端末IDに対応します。PCが実機シリアルを検証し、DUMP権限で保護した登録口へ渡します。Connect画面に全文を表示し、保持済みの異なるIDへ黙って置き換えません。読み取りは自身・ADB shell・署名を確認した対応Bladeに限定します。通常APK更新でもIDと設定を保持します。旧版をそのまま利用する場合も既存接続は妨げませんが、共通IDには本体アプリの更新が必要です。

普段はQuest内のConnectから公開Releaseの更新を確認できます。APKのアプリID・署名・バージョン・整合性を検証した後、本人がOS標準の確認を押します。PC・USB・Viewer・QuestBladeは更新操作に不要です。インターネットがない場合も既存のLAN接続を妨げません。

PCごとにADBの信頼関係が必要です。別PCの初回はUSB準備が必要な場合があります。PCの認証鍵を消去・作り直しません。専用Setupが起動したADBは処理後に終了し、共有ADBは止めません。Setup 0.4.3には正規のabb_execインストール要求を拒否していた問題の修正を含みます。

PCのソフトウェア／パッケージ／署名検査は完了。Quest実機のインストール・更新保持・再起動・USBなし・オフラインLAN・共通ID取得は未確認です。公開Viewerの実機同時映像は受入前の合計2台上限を維持します。

ReleaseにはAPK、Windows USB Setup、更新JSON、説明、ライセンス、SHA256SUMSを含めます。署名鍵、端末情報、設定、ログ、Unityプロジェクトやゲーム素材は含めません。