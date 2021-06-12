---
title: Microsoft Teams 必須デスクトップ クライアント診断データ
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: majaisin
description: Microsoft Teams のポリシー コントロールのデスクトップ プロパティとイベントの一覧。
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: c255fd02342eb6db1878608ad2da09683d7a83ec
ms.sourcegitcommit: 2591c96d8613660220c5af71fc945e27b31175d7
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2021
ms.locfileid: "52863228"
---
# <a name="required-desktop-diagnostic-data-for-microsoft-teams"></a>Microsoft Teams 必須デスクトップ診断データ

次の記事では、Microsoft Teams デスクトップ イベントの一覧と、各イベントが収集するプロパティの一覧について説明します。

Microsoft に送信される診断データを制御する方法を含め、診断データに関する詳細については、「[Teams アプリから Microsoft に送信される診断データ](policy-control-overview.md#diagnostic-data-sent-from-the-teams-app-to-microsoft)」を参照してください。 [診断データ ビューアー](https://support.microsoft.com/topic/cf761ce9-d805-4c60-a339-4e07f3182855)を使用すると、Microsoft に送信されている診断データを表示できます。

## <a name="events"></a>イベント

> [!NOTE]
> 以下にリストされているすべてのイベントに共通のプロパティがあります。それらを確認するには、[すべてのイベントで送信されるプロパティ](#properties-sent-with-all-events)を参照してください。

### <a name="logging"></a>ログ記録

> [!NOTE]
> ログ記録イベントのプロパティについては、[ログ記録イベントで送信されるプロパティ](#properties-sent-with-logging-events)を参照してください。

- **adal-anonymous-mac.ts:this.logger.logError** - Mac デバイスに匿名でログインするときに一般的な sso エラーが発生したことを記録します。
- **adalAnonymousUtil.ts:loggingService.getInstance** - アプリが匿名ユーザー認証を起動できなかったことをログに記録するエラー ステートメントを記録します。
- **adal-anonymous-windows.ts:this.logger.logError** - Windows デバイスに匿名でログインするときに一般的な sso エラーが発生したことを記録します。
- **adalBase.ts:this.loggingService.logError** - ユーザー プロファイルが null または空であることを確認するために必要な情報を記録します。
- **adal-impl-mac.ts:this.loggingService.logError** - 認証中に受信したテレメトリの解析時に発生した問題、またはMac デバイスへのログイン時に発生した genaric sso エラーが発生したことを記録します。
- **adal-rigel-windows.ts:this.logger.logError** - ミーティング ルーム デバイスにログインするときに一般的な sso エラーが発生したことを示す一般的なログステートメント。
- **adal-sso-windows.ts:this.loggingService.logError** - Windows デバイスへのログイン時に一般的な sso エラーが発生したこと、チャット サービスの開始エラー、またはログイン失敗情報を記録します。
- **appOnlineService.ts:loggingService.getInstance** - 起動時に解析できなかった設定、または事前ユーザー認証、事前承認された設定のダウンロードでエラーが発生したことを記録します。
- **appStart.ts:loggingService.logError** - アプリケーションを起動できなかった場合、ディスク容量エラー、有効な証明書エラーが発生した場合、または正しい証明書が見つからず、アプリを再起動した場合のエラーの発生を記録します。
- **browserWindowHttp.ts:this.loggingService.logError** - ファイル システムの問題が原因でアプリケーションを更新できなかったことを示す情報を記録します。
- **contextInstallService.ts:loggingService.getInstance** - 次の場合にエラーの発生を記録します:
  - ファイルを解析または読み取るか、コンテキスト インストール機能にとって重要なURLを解決しようとする。
  - URL 短縮プログラムが、コンテキスト インストール機能を実行しようとする。
- **crashManager.ts:loggingService.logError** - アプリケーションがクラッシュしたときのエラーの原因を特定するための情報を記録します。
- **localStorageService.ts:loggingService.getInstance** - アプリケーションを実行するために重要なブート データが適切にロードされない場合のエラーの発生を記録します。
- **logProviders \ pageDumpProvider.ts:loggingService.getInstance** - アプリケーションがクラッシュしたときにエラー情報を記録します。
- **multiWindowManager.ts:this.logError** - アプリケーションを実行するために重要なブート データが適切にロードされない場合のエラーの発生を記録します。
- **nativeElectronNotifications \ osNotificationService.ts:this.loggingService.logError** - このイベントは、失敗に関する通知を起動しようとしたときにエラーの発生を記録します。
- **OutlookMeetingAddinHelper.ts:loggingService.getInstance** - Outlook ミーティング アドインを使用してミーティングに接続しようとしたときのエラーの発生を記録します。
- **recoveryManager.ts:loggingService.getInstance** - 更新のロールバック中に発生したエラーを記録します。
- **renderer \ startPage \ startPage.ts:this.logger.logError** - アプリケーションの開始ページでのエラーの発生を記録します。
- **settingsService.ts:loggingService.getInstance** - アプリケーション設定でのエラーの発生を記録します。
- **updateInfo.ts:loggingService.getInstance** - アップデートの送信に関するエラーの発生を記録します。
- **updatenotification.js:this._loggingService.logError** - ディスク容量の問題の発生を記録します。
- **utility.ts:loggingService.logError** - ローカル ファイル（アプリケーション内のファイル）へのアクセス エラーを記録します。
- **utility.ts:loggingService.getInstance** - アプリケーションをロードするためのマシン上の利用可能なディスク容量、表示の問題、URL の問題、Cookie の問題、プロトコル、または regkey の問題のエラーを記録します。
- **windowmanager.js:this._loggingService.logError** - Cookie の問題、ホワイト スクリーンの問題、デスクトップとシェルの通信間の問題、URL の問題、ページ メッセージの読み込み、プロセス レンダリングのエラー、ネットワーク接続の問題のエラーを記録します。
- **windowmanager.js:loggingService.getInstance** - リカバリ ウィンドウを表示できない場合を示す情報を記録します。

### <a name="outlook-addin"></a>Outlook アドイン

> [!NOTE]
> Outlook アドイン イベントのプロパティについては、[Outlook アドイン イベントで送信されるプロパティ](#properties-sent-with-outlook-addin-events)を参照してください。

- **joinmeetingoperation** - ユーザーを会議に参加させるために必要な情報を記録します。
- **meetingaddinapplifecycle** - 起動や終了など、アプリの状態に関する情報を記録します。
- **meetingaddinloadtime** - Outlook から会議情報を読み込むのにかかる時間を記録します。
- **openmeetingoperation** - スケジュールされた会議を開くために必要な情報を記録します。
- **savemeetingoperation** - 会議のスケジュール中に会議を保存するために必要な情報を記録します。

### <a name="scenario"></a>シナリオ

> [!NOTE]
> シナリオ イベントのプロパティについては、[シナリオ イベントで送信されるプロパティ](#properties-sent-with-scenario-events)を参照してください。

- **desktop_app_load** - デスクトップ アプリケーションが起動したこと、サービスを初期化する必要があること、およびサービスを初期化できることを確認するために必要な情報を記録します。
- **desktop_app_not_ready** - デスクトップ アプリケーションが機能する準備ができていないことを確認するために必要な情報を記録します。
- **desktop_install** - デスクトップ アプリケーションが正常にインストールされたか、インストールに失敗したかを判断するために必要な情報を記録します。
- **desktop_previous_lifecycle_invalid** - デスクトップ アプリケーションが以前に実行されていた後に再起動し、その後クラッシュしたことを特定するために必要な情報を記録します。

### <a name="tracking"></a>変更履歴​​

> [!NOTE]
> トラッキング イベントのプロパティについては、[トラッキング イベントで送信されるプロパティ](#properties-sent-with-tracking-events)を参照してください。

- **deeplink_scenario_missing** - Teams がディープ リンクから起動しましたが、テレメトリ/診断がありません。
- **desktop_app_initialized** - デスクトップ アプリケーションの初期化時にアプリケーションが正常に起動したかどうかを判断するために必要な情報を記録します。
- **desktop_app_quit_exception** - アプリケーションを閉じようとしたときにクラッシュしました。
- **desktop_blankScreenDetected** - デスクトップ アプリケーションが空白の画面をレンダリングするときにエラーを特定するために必要な情報を記録します。
- **desktop_blankScreenDetectedAfterRepaint** - レンダリングの試みを検出すると、ページが空白であることを検出しました。
- **desktop_blankScreenRecoveredAfterRepaint** - 画面が以前にレンダリングされなかったというレンダリングの問題から回復しました。
- **desktop_configuration_failed_to_save** - デスクトップ設定の保存に失敗したときに構成エラーを特定するために必要な情報を収集します。
- **desktop_navigation_error_recovery** - 5 回試行してもページの読み込みに失敗したときにデスクトップ ナビゲーション エラーを特定するために必要な情報を収集します。
- **desktop_previous_gpu_crashed** - デスクトップがクラッシュしたときにグラフィックス プロセッシング ユニットのエラーを特定するために必要な情報を記録します。
- **desktop_previous_plugin_host_crashed** - デスクトップ アプリケーションのクラッシュに関連するメディア スタックの問題を特定するために必要な情報を収集します。
- **desktop_recovery_cleared_user_data** - レコード アプリケーションが複数回クラッシュし、アプリは回復するためにローカル キャッシュをクリアする必要がありました。
- **desktop_settings_blank_on_load** - これは、アプリケーション設定が存在しないというエラーです。
- **desktop_settings_failed_to_load** - デスクトップ設定の読み込みに失敗した原因を特定するために必要な情報を収集します。
- **desktop_silent_restart** - クライアントの更新がステージングされ、ユーザーが中断することなくクライアントが更新されます。
- **desktop_terminated** - ユーザーがデスクトップ アプリケーションを閉じたときにプロセス間通信が切断されたかどうかを判断するために必要な情報を記録します。
- **desktop_uncaught_exception** 未定義のオブジェクトに対する関数呼び出し。これにより、クラッシュ/アプリの再起動が発生します。
- **desktop_write_storage_failed** - デスクトップ アプリケーションがストレージへの書き込みに失敗したときにディスクエラーを特定するために必要な情報を記録します。
- **registration_failed** - アドイン登録の失敗を解決するために必要な情報を記録します。
- **registration_success** - アドイン登録が成功したかどうかを判断するために必要な情報を記録します。
- **security_unsupported_ipc_channel** - 許可されなかったプロセス間メッセージが受信されました。
- **sfb_running_not_connected** - Skype for Business アプリが実行されていないことが検出されました。
- **sfb_not_running** - 通話から Skype of Business への「応答待ち」がタイムアウトしたことを記録します。
- **sfb_never_replied** - Skype for Business と通信するときに API 応答を追跡しません。
- **server_error_hit** - Skype for Business と通信する ipc パイプからのエラーを追跡します。
- **unexpected_sfb_ipc_disconnection** - サービスへの接続の失敗を判断するために必要な情報を記録します。
- **unregister_failed** - Outlook ミーティング アドインの登録解除のエラーを判別するために必要な情報を記録します。

## <a name="userbi-panelaction"></a>UserBI パネルアクション

> [!NOTE]
> UserBI panelaction イベントのプロパティについては、[UserBI panelaction イベントで送信されるプロパティ](#properties-sent-with-userbi-panelaction-events)を参照してください。

- **inlinereply** - ユーザーが通知に返信したかどうかの情報を記録します。
- **toastclick** - ユーザーのクリックを記録してメッセージ エントリに移動し、通知をトーストしてサービス SLA を監視し、トースト通知への適切な応答をロードします。
- **toastdismiss** - ユーザーがトースト通知のレンダリングを却下したときのエラーと遅延を特定するために必要な情報を記録します。

- **toast_skip** - 遅延トースト通知の送信を回避するために必要な情報を記録します。
- **toasttimeout** - トースト通知のレンダリングがタイムアウトしたときのエラーと遅延を特定するために必要な情報を記録します。

### <a name="userbi-panelview"></a>UserBI パネルビュー

> [!NOTE]
> UserBI panelview イベントのプロパティについては、[UserBI panelviewイベントで送信されるプロパティ](#properties-sent-with-userbi-panelview-events)を参照してください。

- **toastshow** - トーストがレンダリングされたことを確認するために必要な情報を記録します。

## <a name="property-lists"></a>プロパティ リスト

### <a name="properties-sent-with-all-events"></a>すべてのイベントで送信されるプロパティ

| プロパティ名                              | 説明                                                        |
|--------------------------------------------|--------------------------------------------------------------------|
| EventInfo_Time                             | イベント発生時刻                                              |
| EventInfo_Name                             | イベント名 - イベントの種類を区別するために使用します             |
| EventInfo_BaseType/name                    | イベントの種類 - イベント内のイベントの種類を区別するために使用します |
| EventInfo_Sequence                         | イベントのシーケンス                                              |
| userAgent                                  | ブラウザ エージェント文字列                                               |
| userpdclevel                               | ユーザーのプライバシー データ管理設定                           |
| eventpdclevel                              | イベントのプライバシー データ コントロールの分類レベル             |
| AppInfo_Language                           | アプリの言語                                                       |
| clientType/AppInfo_ClientType              | アプリが実行されているクライアントの種類                               |
| environment/AppInfo_Environment            | ユーザーのリクエストに応えたエンジニアリング環境               |
| clientVersion/appversion/AppInfo_Version/desktopBuildVersion | アプリのバージョン                               |
| buildtime                                  | アプリがエンジニアリング システムに組み込まれたタイムスタンプ            |
| osversion/DeviceInfo_OsVersion             | OS バージョン                                                         |
| AppInfo_ProcessArchitecture                | システム アーキテクチャ（32ビット/ 64ビット）                                  |
| preferredLocales                           | ユーザーの優先ロケール                                      |
| locale/AppInfo_Locale                      | アプリのロケール                                                         |
| os/DeviceInfo_OsName                       | OS 名                                                            |
| UserInfo_Language                          | 選択したユーザー言語                                             |
| UserInfo_Id                                | ユーザー ID                                                            |
| UserInfo_TenantId/TenantId                 | テナント ID                                                          |
| ring/UserInfo_Ring                         | アプリケーションを段階的に提供するのに役立つ概念          |
| region                                     | ユーザーのリクエストを処理したデータ センター リージョン                       |
| UserInfo_ConfigIds/UserInfo_Etag           | 異なる実験/ロールアウトでユーザーを識別するのに役立つ ID     |
| DeviceInfo_BrowserName                     | ブラウザ名                                                       |
| DeviceInfo_BrowserVersion                  | ブラウザのバージョン                                                    |
| DeviceInfo_Id/machineId/DeviceInfo_IdV2    | デバイスの識別に役立つ ID                                  |
| totalMemory                                | デバイスのハードウェア メモリ                                      |
| cores                                      | デバイスのハードウェア コア                                       |
| cpuspeed                                   | デバイスのハードウェア CPU 速度                                   |
| DeviceInfo_CpuArchitecture/cpuarchitecture | デバイスのCPU アーキテクチャ                                     |
| UserRole                                   | テナントでのユーザー ロールの識別に役立ちます                               |
| DeviceInfo_WindowsMode                     | Windows セキュリティ モードの識別に役立ちます                               |
| desktopSession/Session_Id                  | セッションの識別に役立ちます                                           |
| dbOpen                                     | ローカル データベースの状態をキャプチャします                               |
| UserInfo_Upn                               | ユーザー識別子の片側ハッシュ                                  |

### <a name="properties-sent-with-logging-events"></a>ログ記録イベントとともに送信されるプロパティ

| プロパティ名         | 説明                                                        |
|-----------------------|--------------------------------------------------------------------|
| message               | ログに関する詳細なメッセージをキャプチャします                          |

### <a name="properties-sent-with-scenario-events"></a>シナリオ イベントで送信されるプロパティ

| プロパティ名                     | 説明                                                                        |
|-----------------------------------|------------------------------------------------------------------------------------|
| Scenario_Status                   | シナリオのステータス                                                               |
| Scenario_Step                     | シナリオのステップ                                                                 |
| sequence                          | シナリオのシーケンス番号                                                    |
| delta                             | シナリオの異なるステップを完了するのにかかる時間                               |
| elapsed                           | シナリオ開始からの時間                                                    |
| scenario                          | シナリオを一意に識別する                                                       |
| Scenario_Name                     | シナリオの名前                                                               |
| errorInfo                         | シナリオ中に発生した可能性のあるエラーの情報                       |
| session                           | 一意のセッション ID                                                                  |
| freeMemory                        | 利用可能な空きメモリをキャプチャします                                                     |
| processMemory                     | プロセス メモリをキャプチャします                                                            |
| scenarioDelta                     | 2つのシナリオステップ間で異なる時間をキャプチャします                                   |
| Session_DesktopId                 | 一意のセッション ID                                                                  |
| machineLocked                     | マシンがロックされているかどうかをキャプチャします                                          |
| windowIsVisible                   | アプリ ウィンドウが使用可能であるかどうかをキャプチャします                                      |
| appStates/webAppStates            | アプリが通過したアプリの状態の一覧を記録します。これによりアプリの状態について確認できるため、クラッシュの原因調査に役立ちます |
| crashDesktopSession               | クラッシュしたセッションの ID をキャプチャします                                                 |
| appRuntime                        | アプリのランタイムをキャプチャします                                                        |
| diagnosticEvents                  | アプリがクラッシュする前の過去50件のウェブ アプリ診断イベント                                 |
| activities                        | クラッシュ前に発生した最後の50のユーザー シナリオ名                            |
| crashSession                      | クラッシュしたセッションの ID をキャプチャします                                                 |
| crashId                           | クラッシュしたセッションの ID をキャプチャします                                                 |
| isPreviousLifecycleValid          | 以前のアプリが完全に初期化され、正常に終了したかどうか             |
| isSettingValid                    | 事前認証設定が有効かどうか                                                 |
| rollbackReason                    | どのアプリがロールバックされたかによる理由                                            |
| deeplinkType                      | ディープリンクの種類                                                               |
| watchdogCrash                     | ハングが原因でアプリがクラッシュしたかどうか                                                    |
| protocols                         | アプリの起動に使用されたプロトコル                                                    |
| electronBuild                     | electron アプリのビルド バージョン                                                      |
| distribution                      |  Teams が exe、msi、dmg、pkg のいずれを介してインストールされたかなど。                    |
| updateTimeOfDay                   | アプリが更新された時刻                                                           |
| launchPath                        | Teams が %LOCALAPPDATA%、%PROGRAMFILES%、またはその他の場所にインストールされているかどうか   |
| loggedIn                          | ユーザーがログインしていたか                                                          |
| envType/complianceEnvironmentType | 商用クラウドまたはプライベート（DoD、GCC-High など）                              |
| cpuusage                          | CPU 使用率                                                                          |
| installationSource                | インストール ユーザーの種類                                                      |
| adalVersion                       | 認証ライブラリのバージョン                                                        |
| asyncStart                        | アプリは同期起動または非同期起動を使用していますか                                 |
| attempts                          | ブロック画面を表示する前にユーザーに対して行われたオンライン チェックの試行回数 |

### <a name="properties-sent-with-tracking-events"></a>追跡イベントと共に送信されるプロパティ

| プロパティ名                      | 説明                                                                      |
|------------------------------------|----------------------------------------------------------------------------------|
| name2                              | 追跡イベントの名前をキャプチャします                                              |
| numVisibleNotifications            | 表示されるアプリケーション通知の数                                      |
| giphyEnabled                       | Giphy サービスが有効になっていたかどうか                                                |
| error                              | 追跡イベントに関連するエラーの詳細をキャプチャします                             |
| method                             | プロトコル メソッド GET または POST                                                      |
| channel                            | アプリ内のプロセス間通信チャネルをキャプチャします                      |
| windowTitle                        | イベントに関連付けられている表示ウィンドウの種類                                     |
| message                            | エラー メッセージの種類                                                        |
| crashSession/crashDesktopSession/crashId/Session_DesktopId/Session_DesktopBackgroundId | セッションのデバッグ目的で一意の IDをキャプチャします |
| responseCode                       | サービス呼び出しの応答コードをキャプチャします                                      |
| errorUrl                           | ロードに失敗したURL                                                      |
| errorCode                          | エラーコードをキャプチャします                                                              |
| ssoEventData                       | 認証の状態とステータス                                                  |
| correlationId                      | イベントをデバッグ目的でサービス側と関連付けるID                      |
| errorDescription                   | エラーコードの説明をキャプチャします                                            |
| source                             | Teams アプリを取得する方法と Teams のインストール元のパッケージの種類       |
| windowIsDestroyed                  | イベント中のアプリケーション ウィンドウの真/偽の状態                             |
| windowIsFocused                    | イベント中のアプリケーション ウィンドウの真/偽の状態                             |
| windowIsVisible                    | イベントが発生したときにアプリケーションが表示されていましたか                                  |
| windowIsMinimized                  | イベント中のアプリケーション ウィンドウの真/偽の状態                             |
| windowIsMaximized                  | イベント中のアプリケーション ウィンドウの真/偽の状態                             |
| windowIsFullscreen                 | イベント中のアプリケーション ウィンドウの真/偽の状態                             |
| distSrc                            | アプリへのユーザーランディングの配布ソースをキャプチャします                    |
| 再試行                            | エンドポイントに接続しようとしたときに再試行カウント                            |
| uses_slimcore                      | Web コールがスリムコアを使用している場合は真または偽                                      |
| persistCookieExpiresIn             | Web アプリケーション Cookie の有効期間の残り時間                             |
| tenantName                         | アプリケーションのユーザーのテナント名                                       |
| appStartReason                     | アプリケーション セッションの開始方法（ユーザーが開始した、更新後など）。 |
| machineLocked                      | イベント中にマシンがロックされたかどうか                        |
| data                               | シナリオ調査のための技術データをキャプチャします                               |
| appRuntime                         | アプリのランタイムをキャプチャします                                                      |
| activities                         | クラッシュ前に発生した最後の50のユーザー シナリオ名                          |
| timeSinceActivity                  | 最後のユーザー アクティビティからの時間                                                    |
| appStates                          | デスクトップ アプリが通過したアプリの状態の一覧を記録します。これは、デスクトップ アプリの状態を示すため、クラッシュ調査に役立ちます。 |
| timeSinceAppState                  | アプリの状態が変化してからの時間                                                 |
| webAppStates                       | Web クライアントが通過したアプリの状態の一覧を記録します。これは、Web クライアント アプリの状態を示すため、クラッシュ調査に役立ちます。 |
| timeSinceWebAppState               | Web アプリの状態が変化してからの時間                                             |
| diagnosticEvents                   | アプリがクラッシュする前の過去50件のウェブ アプリ診断イベント                               |
| timeSinceLastDiagnosticEvent       | 最後の診断イベントが送信されてからの時間                                            |
| timeSinceSecondLastDiagnosticEvent | 最後から 2 番目の診断イベントが送信されてからの時間                                     |
| appInitialized                     | Web アプリケーションが起動したかどうか                                               |
| targetVersion                      | バージョン アプリケーションは次のように更新されます                                    |
| port                               | インターネット メッセージ ポート番号                                                     |
| originalUrl                        | レンダリングされるページの元の場所                                         |
| deeplinkId                         | Teams リンクの宛先の種類の GUID                                          |
| appSessionEnd                      | アプリケーション セッションの終了時にイベントが発生したかどうか                             |
| eventData                          | 問題が発生した場合のデバッグに役立つマシンの状態とアプリの構成をキャプチャします        |
| deeplinkType                       | ディープリンクの種類（チャット、会議、チャネル）                                    |
| previousUpdateUrl                  | アプリケーションが最後に更新を取得した場所                        |
| previousUpdateVersion              | 最新バージョンのアプリケーションが次に更新されました：                                          |
| previousUpdateTime                 | アプリケーション バイナリが最後に更新されたとき                                      |
| protocol                           | ファイルや画像などのリンクのハンドラーの種類                                     |
| files                              | イベントに関連付けられているファイルの種類（アプリケーション キャッシュや GPU キャッシュなど）    |
| Perf_WorkingSetSizeKB              | メモリ キャッシュのサイズ                                                             |
| isTimeboxingWebAppInitialize       | タイムボックス カウンターがなくなる前にアプリが初期化されたかどうか                          |
| isExp                              | 使用中のアプリのバージョンが実験の一部であるかどうか                          |
| deviceType                         | デバイスの種類をキャプチャします                                                      |
| sanitizedErr                       | エラー情報のサニタイズされたバージョンをキャプチャします                              |
| rigelVersion                       | Rigel デバイスのバージョンをキャプチャします                                                 |
| DeviceInfo_OsSku                   | OS SKU 情報をキャプチャします                                                      |
| isLoggedOut                        | ユーザーがログ アウトしたかどうかをキャプチャします                                               |
| ComplianceEnvironmentType          | 商用クラウドまたはプライベート（DoD、GCC-High など）                           |
| restartTimes                       | 前回の再起動の正確な時刻                                                 |
| Skype_ResultCode                   | SkypeとTeams 間の相互運用通信の結果をキャプチャします                 |
| cpumodel                           | CPUのモデルをキャプチャします                                                            |
| isSlimCoreRunningOutproc           | Slimcore コンポーネントが独自のプロセスで実行されているかどうか                         |
| isSlimCoreStartedAsync             | 内部オーディオ/ビデオ（A/V）スタックの起動の種類                               |
| networkState                       | ネットワークの状態をキャプチャします                                                    |
| desktopBuildAge                    | イベント発生時のアプリケーション ビルドの古さ                                   |
| vdiMode                            | アプリが VDI モードで実行されているかどうかをキャプチャします                                       |

### <a name="properties-sent-with-userbi-panelview-events"></a>UserBI panelview イベントで送信されるプロパティ

| プロパティ           | 説明                                              |
|--------------------|----------------------------------------------------------|
| Panel_Uri          | ユーザーに配信されるパネルの URI                   |
| Panel_Type         | ユーザーがアクセスするパネルの種類                          |
| Team_Id            | ユーザーがアクションを実行したチームの ID |
| Thread_Id          | ユーザーがアクセスしたスレッドの ID               |
| Panel_PreviousUri  | 前のパネルの URI                                |
| Panel_Region       | アプリでパネルがホストされていた地域             |
| Panel_LaunchMethod | パネルが起動された方法              |
| Panel_PreviousType | 前のパネルの種類                               |
| Thread_Type        | ユーザーがアクセスするスレッドの種類                          |
| Panel_LaunchSource | 起動されたパネルのソース情報        |
| Tab_Type           | ユーザーがアクセスするタブの種類                         |
| Team_Type          | ユーザーがアクセスするチームの種類                            |

### <a name="properties-sent-with-userbi-panelaction-events"></a>UserBI panelaction イベントで送信されるプロパティ

| プロパティ名         | 説明                                                        |
|-----------------------|--------------------------------------------------------------------|
| Action_DestinationUri | ユーザー アクションによってアクセスされているリソースの URI                  |
| Panel_Uri             | ユーザーに配信されるパネルの URI                             |
| Action_Gesture        | アプリでユーザーが実行するジェスチャの種類                       |
| Action_ScenarioType   | 機能のビジネス メトリックに関連する機能のグループ化       |
| Panel_Type            | ユーザーがアクセスするパネルの種類                                    |
| Action_Outcome        | ユーザーが実行したアクションの結果                            |
| Team_Id               | ユーザーがアクションを実行したチームの ID           |
| Module_Type           | ユーザーのアクションをホストしたモジュールの種類                        |
| Module_Name           | ユーザー アクションをホストしたモジュールの名前                        |
| Module_Summary        | ユーザー アクションをホースしたモジュールのまとめ                       |
| Thread_Id             | ユーザーがアクセスしたスレッドの ID                         |
| Panel_PreviousUri     | 前のパネルの URI                                          |
| Panel_Region          | アプリでパネルがホストされていた地域                       |
| Panel_LaunchMethod    | パネルが起動された方法                        |
| Panel_PreviousType    | 前のパネルの種類                                         |
| Thread_Type           | ユーザーがアクセスするスレッドの種類                                    |
| Module_State          | ユーザーがアクセスしたモジュールの状態                               |
| Action_Scenario       | ビジネス指標に関連する機能グループ内の機能 |
| Panel_LaunchSource    | 起動されたパネルのソース情報                  |
| Tab_Type              | ユーザーがアクセスするタブの種類                                   |
| Team_Type             | ユーザーがアクセスするチームの種類                                      |

### <a name="properties-sent-with-outlook-addin-events"></a>Outlook アドイン イベントで送信されるプロパティ

| プロパティ名                   | 説明                                                              |
|---------------------------------|--------------------------------------------------------------------------|
| AccountComparisonFailedReason   | アドインはアカウントを Teams アカウントと比較して、作成が許可されているかどうかを確認します。このイベントは、比較が失敗した場合に送信されます |
| AccountComparisonSuccessful     | アドインはアカウントを Teams アカウントと比較して、作成が許可されているかどうかを確認します。比較が成功した場合、このイベントが送信されます |
| AdalVersion                     | 使用する認証ライブラリのバージョン                               |
| AddinBitness                    | アドインのバージョン                                                         |
| AddinLanguage                   | 使用されているアドイン文字列の言語                                     |
| AggregatorSetupCompletedTime    | アドイン ローダーのセットアップ時刻                                              |
| AppDomainCreatedTime            | アドイン ローダーがアプリ ドメインを初期化する時刻                            |
| AppointmentDisplayTime          | 会議の作成中に予定アイテムが表示された時刻 |
| AuthenticationCompletedTime     | 特定のリクエストに対して認証が提供された時刻            |
| ConnectionMode                  | ユーザーのプライマリ Exchange アカウントの接続モードを示します     |
| ConnectionStartedTime           | Outlook が OnConnection を呼び出す時刻                                     |
| ErrorDetails                    | エラーの詳細をキャプチャします                                            |
| エラー名                       | エラーの名前をキャプチャします                                               |
| ExchangeVersion                 | Exchange のバージョンをキャプチャします                                             |
| IsSmtpFormatError               | SMTP アドレスのエラー                                                    |
| IsTeamsRunning                  | 実行中の Teams プロセスがあるかどうかをキャプチャします                             |
| IsTeamsUserLoggedOut            | ユーザーがTeams からログアウトしているかどうかをキャプチャします                              |
| LanguageSetupCompletedTime      | 言語設定が完了した時刻                               |
| ManagedConnectTime              | マネージ アドインが接続コールバックを受信した時刻               |
| ManagedOnStartupTime            | 管理対象がスタートアップを開始した時刻                                    |
| MTFetchCompleted                | MT 会議のオプション リクエストが完了した時刻                        |
| NetFrameworkVersion             | 使用される .nET フレームワーク                                                      |
| NetworkAvailable                | ネットワークは利用可能ですか                                                     |
| OperationStartTime              |  異なる操作が開始された時刻                                  |
| OsBitness                       | OS の ビットネス                                                            |
| Outlook Language                 | Outlook アプリの言語をキャプチャします                                     |
| Outlook Version                  | Outlook アプリのバージョンをキャプチャします                                          |
| OwnerResolutionTime             | 会議の所有者を解決する時刻                                        |
| ParseResponseCompletedTime      | 応答の解析が完了した時刻                                  |
| RecipientResolutionError        | 受信者を解決するときのエラーの詳細                                 |
| RecipientsResolutionTime        | すべての受信者を解決するための合計時間                                     |
| RehydrateCompletedTime          | プロパティが Outlook から読み取られる時刻                               |
| SaveToOutlook CompletedTime      | プロパティが Outlook に保存される時刻                                |
| ServiceRequestStartTime         | サービス リクエストの開始時刻                                        |
| ServiceResponseReceiveTime      | サービスからの応答時刻                                        |
| SettingsInitializeCompletedTime | 設定が初期化された時刻                                           |
| SetupLoggingCompletedTime       | ログ記録が設定された時刻                                             |
| ShutdownBeginTime               | アドインのシャットダウンが始まる時刻                                       |
| ShutdownCompletedTime           | シャットダウンが完了した時刻                                             |
| StartupBeginTime                | アドインの起動開始時刻                                        |
| StartupCompletedTime            | 起動完了時                                              |
| TeamsDeployment                 | Teams クライアントの展開（Dev、Prod）                                   |
| TeamsRing                       | Teams クライアントにログインしている現在のユーザーのリング                            |
| TeamsVersion                    | Teams アプリのバージョンをキャプチャします                                            |
| TelemetrySetupCompletedTime     | テレメトリーのセットアップが完了した時刻                                   |
| UpnMismatch                     | Outlook とTeams の間にミスマッチがあるかどうか                  |
| UserDomain                      | ユーザーのドメイン                                                       |
| ViewUpdatedTime                 | ビューが更新された時刻                                           |
