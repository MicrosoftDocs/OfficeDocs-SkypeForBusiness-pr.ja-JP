---
title: Microsoft Teams 必須モバイル診断データ
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: majaisin
description: Microsoft Teams のポリシー コントロールのモバイル プロパティとイベントの一覧。
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 200e3c34c5c7136a441f492d0228c6af6f551a94
ms.sourcegitcommit: fdef9b52247097e5cae64f01b6b2b710c5b203cf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/20/2021
ms.locfileid: "49909151"
---
# <a name="required-mobile-diagnostic-data-for-microsoft-teams"></a>Microsoft Teams 必須モバイル診断データ

次の記事では、Microsoft Teams モバイル イベントの一覧と、各イベントが収集するプロパティの一覧について説明します。

## <a name="events"></a>イベント

> [!NOTE]
> 以下にリストされているすべてのイベントに共通のプロパティがあります。それらを確認するには、[すべてのイベントで送信されるプロパティ](#properties-sent-with-all-events)を参照してください。

### <a name="panelaction"></a>パネルアクション

> [!NOTE]
> パネルアクション イベントのプロパティについては、[パネルアクション イベントで送信されるプロパティ](#properties-sent-with-panelaction-events)を参照してください。

- **accessibilityUserConfiguration** - ユーザーがアクセシビリティ機能を切り替える場合。
- **acknowledgeSettingChange** - 通知設定ダイアログが更新された際の更新の確認。 これは、更新通知を確認し、全体的な通知の信頼性を判断するために使用される機能の成功指標です。
- **actionComposeMenu**
  - メッセージの拡張機能の用途を作成します。
  - アクション メッセージの拡張機能の用途。
- **active_session_banner_dismissed** - 位置情報の共有のアクティブ リマインダー通知バナーが閉じられました。
- **activityChatClicked** - [**アクティビティ**] タブで [ライブチャット以外] が選択されている場合、または分割ビューが表示されている場合に トリガーされます。
- **activityContextMenu** - アクティビティ フィードのオーバー フロー アクション。
- **activityFeedClick** - アクティビティ フィード アイテムのタップによりチャット ボットに移動します。
- **activityFeedLongPress** - フィード アイテムの長押しジェスチャをキャプチャします。
- **activityFeedSwipe** - フィード アイテムのスワイプ ジェスチャをキャプチャします。
- **activityFilterClick** - アクティビティ フィルターの用途をキャプチャします。
- **activityFilterOptionsClick** - アクティビティ フィルターの用途をキャプチャします。
- **activityFilterOptionsClicked** - アクティビティ フィルターの用途をキャプチャします。
- **activityLiveChatClicked** - チャットが [**アクティビティ**] タブのライブ会議で選択されるとトリガーされます。
- **activityLiveDetailsClicked** - [**詳細**] が [**アクティビティ**] タブのライブ会議で選択されるとトリガーされます。
- **activityTabClicked** - 以下を判断するサポートをします。
  - [**アクティビティ**] タブが表示されているかどうか。
  - Teams が [**アクティビティ**] タブ イベントをキャプチャするかどうか。
- **activityTypeDropdown** - アクティビティ フィルターの用途をキャプチャして [**マイ アクティビティ**] と [**フィード**] を切り替えます。
- **addChannel** - チャネルの追加。 このアイテムは、チャネル作成の成功に関する成功データを示します。
- **addMember** - [**ユーザーの招待**] ボタンが[**その他**] メニューで選択されるとトリガーされます。
- **addMembers** - チームまたはプライベートチャネルにメンバーを追加します。
- **addToCalendar** - [**カレンダーに追加**] ボタンを選択しプライベートのカレンダーにないカレンダーイベントを表示します。
- **addToList** - 連絡先が連絡先リストに追加されます。
- **addToMeeting** - 会議の参加者リストにある [**会議に追加**] ボタンを選択します (チャットに参加している参加者の場合)。
- **addUserAsContact** - 連絡先を追加するには、連絡先のプロファイルカードから [**連絡先を追加する**] アイコンを選択します。
- **admitAll** - ロビー セクションで [**全員を許可**] ボタンが選択される回数。
- **admitParticipant** - 会議参加者一覧よりユーザーが会議への参加を許可される回数。
- **alertsNavAlert** - フィード アイテムをタップ。
- **android: null** - チャット ボットのミュートまたはミュート解除。 これによりチャットの既存のテレメトリが強化され、アプリケーション情報のみが追加されます。
- **anonymousMeetingJoin** - [**会議に参加**]が匿名での参加提供名のページで選択されている、または名前ダイアログボックスで [**OK**] がタップされています。
- **anonymousMeetingJoinWelcome** - [**ゲストとして参加**] が匿名での会議参加ランディング ページで選択されています。
- **anonymousMeetingPostMeetingChat** - 通話の最終画面にあるチャットのユーザー閲覧数。
- **anonymousMeetingPostMeetingRejoin** - 匿名ユーザーが会議に再度参加を試みた回数。
- **anonymousMeetingSignIn** - ユーザーが名前の入力画面からサインインに移動した回数。
- **anonymousMeetingJoinWelcome** - [**サインインして参加**] が匿名での会議参加ランディング ページで選択されています。
- **anonymousMeetingToggleMuted** - ミュートのトグル ボタンが選択された回数。
- **anonymousMeetingToggleMuted** - ビデオのトグル ボタンが選択された回数。
- **appKilled** - アプリケーションを終了します。
- **approveTimeOffRequest** -  現場担当者マネージャーが現場担当者の休暇をとりたいという要求を承認した場合。
- **assigneeChange** - 新しい担当者がタスク アイテムに追加されるとトリガーされます。
- **assignmentPickerClicked** - [**割り当て先**] ボタンが選択されて、[担当者選択] ページが開きます。
- **assignmentRemoved** - [**x**] を選択してタスク アイテムから担当者が削除されるとトリガーされます (これが担当者を削除する唯一の方法です)。
- **attachmentAdded** - タスクの添付ファイルが正常に追加されたことを確認します。
- **attachmentDeleted** - タスクの添付ファイルが正常に削除されたことを確認します。
- **attachmentUpdated** - タスクの添付ファイルが正常に更新されたことを確認します。
- **audioOnlyLowBatteryBanner** - バッテリー残量不足のバナーが出たため、[**オーディオのみ**] のオプションが選択されています。
- **audioOnlyPoorNetworkBanner** - 接続不良のバナーが出たため、[**ビデオ オフ**] のオプションが選択されています。
- **audioUserDoubleTap** - オーディオ参加者をダブル タップします。
- **autoReconnectCallmebackCallDrop** - [**もう一度通話する**] ボタンが通話の最終画面で選択された回数。
- **autoReconnectDialIn**
  - [再接続 UFD] で [**ダイヤルイン**] ボタンが選択されています。
  - 再接続している間に [**ダイヤルイン**] ボタンが選択された回数。
- **autoReconnectDialInonCallDrop** - [通話切断済み UFD] で [**ダイヤルイン**] ボタンが選択されています。
- **autoReconnectDialOut** - [再接続 UFD] で [**もう一度通話する**] ボタンが選択されています。
- **autoReconnectRejoinonCallDrop** - [**再度参加**] または [**リダイヤル**] ボタンが通話の最終画面で選択された回数。
- **backFromCallMePSTN** - [もう一度通話する] PSTN 番号フローが完了していません。
- **backToPhotoShare** - カメラに戻ります。
- **backToStageFromWhiteboard** - ホワイトボードの通話画面に戻ります。
- **backToWhiteboardFromStage** - 通話画面からホワイトボードに移動します。
- **blockAnonymous** - 以下の場合:
  - 通話設定を有効にして、設定から発信者番号通知のない通話を禁止します。
  - 通話設定を無効にして、設定から発信者番号通知のない通話を禁止します。
  - 通話設定を有効にして、アクション シートから発信者番号通知のない通話を禁止します。
  - 通話設定を無効にして、アクション シートから発信者番号通知のない通話を禁止します。
- **blockCaller** - 拒否:
  - 新しい iOS 通話のアクション シートの番号と連絡先。
  - 連絡先カードの連絡先と番号。
  - [設定] の番号。
- **blockChat** - チャット ボットをブロックします。 これによりチャットの既存のテレメトリが強化され、アプリケーション情報のみが追加されます。
- **botClickCardAction** - コネクタ カードの用途。
- **brbFeedback** - BRB フィードバック フォームのパフォーマンスに関連。
- **brbFormCancelled** - フィードバック フォームが取り消され、ユーザーがアプリに戻るときに送信されるイベント。
- **brbFormOpened** - BRB フォームが開かれたときに送信されるイベント。
- **brbFormSubmit** - ユーザーがフィードバック フォームで [**送信**] を選択したときに送信されるイベント。
- **breakStartEndClicked** - 画面の時計で、[**開始**] または [**休憩終了**] が選択されています。
- **breakStartEndTriggered** - ユーザーが休憩の開始と終了を選択すると登録。
- **bucketSelected** - バケットの選択が完了したことを確認します。
- **bucketSelected** - バケットの選択解除が完了したことを確認します。
- **bucketPickerClicked** - [バケット ピッカー] が正常に起動したことを確認します。
- **BYOELiveEventJoin** - BYOE (独自のイベントを配信) ライブ イベントにユーザーが参加します。
- **calendarLiveChatClicked** - [**スケジュール**] タブのライブ会議のチャット。
- **calendarMeetingJoin** - [**会議参加**] ボタンがカレンダーで選択されました。
- **calendarTab** - 下部レールの [**会議**] タブを選択します。 カレンダーの用途を理解し、下部レールにある他のアプリと比較したり、カレンダーの投稿を下部バーで選択した後、レンダリングする際に、エラーが発生したかどうかを確認したりするのに便利です。
- **calendarTabClicked** - 以下に挙げられた状況では、これによりカレンダーの用途が表示されるので、下部レールにある他のナビゲーションバー アプリとの比較ができます。 これを利用して、次の場合にエラーが発生したかどうか判断できます。
  - [**スケジュール**] タブを表示する。
  - [**会議**] タブを下部レールで選択する。
- **calendarUpcomingChatClicked** - [**スケジュール**] タブの今後の会議のチャット。
- **callAccepted** - 通話が承認されました。
- **callAcceptedSFB** -通話が承認されました。
- **callAppPreference** - 優先通話アプリが選択されています。
- **callControlsManualDismiss** - 通話コントロールを手動で閉じます。
- **Callcontrols Manualinvoke** - 通話コントロールを手動で呼び出します。
- **callHistoryItemExpand** - 通話履歴アイテムが展開されます。
- **callHistoryTab** - [**通話履歴**] タブが [通話] で選択されています。
- **callInProgressShown** - * *_[通話中]_* バナーが表示されています。
- **callMePSTNConnected** - [**電話**] に成功しました。
- **callOrMeetUpAddParticipants** - 以下の場合にトリガーされます。
  - [参加者の追加] ボタンが、1:1の通話画面でタップされている。
  - [参加者の追加] で [ユーザー (VoIP)] を選択する。
  - [参加者の追加] で [PSTN] を選択する。
  - ライブ プライベート会議でユーザーを追加する。
  - ライブ プライベート会議で PSTN を選択する。
  - ライブ プライベート会議で [会社の連絡先] を選択する。
  - ライブ プライベート会議で [デバイスの連絡先] を選択する。
  - ライブ プライベート会議で [完了済み参加者] を追加する。
  - ライブ プライベート会議でメンバーを追加する。
  - ライブ チャネル会議で PSTN を選択する。
  - ライブ チャネル会議でチーム メンバーを選択する。
  - ライブ チャネル会議で [デバイスの連絡先] を選択する。
  - ライブ チャネル会議で [完了済み参加者] を追加する。
- **callOrMeetUpAddParticipantsDone** - ユーザーが参加者の追加を終了します。
- **callOrMeetUpAddRoom** - 以下の場合にトリガーされます。
  - 名簿で [**部屋の追加**] が選択される。
  - 検索結果が [部屋の追加］ で選択される。
  - [この近く] に [**閉じる**] が選択される。
  - [**BTを有効にする**］ または [**位置**] が [この近く] で選択される。
  - 近くの部屋の検索結果が [部屋の追加］ で選択される。
  - おすすめの部屋の検索結果が [部屋の追加］ で選択される。
  - [**完了**] が [部屋の追加］ で選択される。
- **callOrMeetUpAudioOffSwitch** - ライブ通話または Meetup のコンパニオン参加モードで [**音声オフ**]　のボタンを反転させます。
- **callOrMeetUpAutoReconnect** - ネットワーク パフォーマンスが低下すると、ユーザーのデバイスが Autoreconnect モードになります。
- **callOrMeetUpCallAccepted** - 以下の場合にトリガーされます。
  - 通話が承認されている。
  - PSTN 通話が承認されている。
- **callOrMeetUpCallEnded** - 以下の場合にトリガーされます。
  - [**通話の終了**] ボタンがタップされている。
  - CallOrMeetupLive で [**通話終了**] のボタンがタップされている。
  - lockScreen で [**通話終了**] のボタンがタップされている。
  - 通知で [**通話終了**] のボタンがタップされている。
  - inApp で [**通話終了**] のボタンがタップされている。
  - callKit で [**通話終了**] のボタンがタップされている。
  - PSTN の [**通話終了**] のボタンがタップされている。
- **callOrMeetUpChatWithParticipants** - Live Meeting または通話でのチャット切り替え。
- **callOrMeetUpDeviceAudioSwitch** - 以下の場合にトリガーされます。
  - オーディオ ソースをスピーカーに切り替える。
  - オーディオ ソースをデバイスに切り替える。
  - オーディオ ソースを Bluetooth に切り替える。
  - オーディオ ソースを [オーディオ オフ] に切り替える。
  - Live Meeting または通話中にスピーカーを切り替える。
  - Live meeting または通話中に、スピーカーを [オーディオ オフ] に切り替える。
  - ライブ通話または Meetup のコンパニオン参加モードで [**オーディオ オフ**]　のボタンを反転させる。
  - PSTN でのデバイス オーディオ切り替え。
- **callOrMeetUpEnterDriveMode** - 手動で [**...**] メニューからドライブ モードに切り替えます。
- **callOrMeetupExitDriveMode** - [**ドライブ モード終了**] ボタンがタップされています。
- **callOrMeetUpHold** - 以下の場合にトリガーされます。
  - ライブ会議または通話中に[**ホールド**] ボタンがタップされる。
  - PSTN での通話ホールド。
- **callOrMeetUpIncomingVideoSwitch** - ライブ会議または通話中に着信ビデオをオフにします。
- **callOrMeetUpInvitedParticipants** - 以下の場合にトリガーされます。
  - プライベート ライブ会議中に [**招待済み他のユーザー**] 参加者グループの下部にある [**すべて表示**] がクリックされた。
  - ライブ チャネル会議中に [**招待済み他のユーザー**] 参加者グループの下部にある [**すべて表示**] がクリックされた。
- **callOrMeetUpJoinedParticipants** - 以下の場合にトリガーされます。
  - プライベート ライブ会議中に [**会議中**] 参加者グループの下部にある [**すべて表示**] がクリックされた。
  - ライブ チャネル会議中に [**会議中**] 参加者グループの下部にある [**すべて表示**] がクリックされた。
- **callOrMeetUpLobbyParticipants** - 以下の場合にトリガーされます。
  - プライベート ライブ会議中に [**ロビー**] 参加者グループの下部にある [**すべて表示**] がクリックされた。
  - ライブ チャネル会議中に [**ロビー**] 参加者グループの下部にある [**すべて表示**] がクリックされた。
- **callOrMeetUpMicrophoneSwitch** - 以下の場合にトリガーされます。
  - マイクをオンに切り替える。
  - マイクをオフに切り替える。
  - ライブ会議または通話中に [**マイク**] ボタンを選択。
  - PSTN でのマイク切り替え。
- **callOrMeetUpMuteParticipant** - リモート参加者をミュートにします。
- **callOrMeetUpMuteParticipants** - ライブ会議または通話中の全参加者をミュートにします。
- **callOrMeetUpParticipants** - 参加者がライブ会議または通話中に切り替えます。
- **callOrMeetUpRemoteMuteUFD** - UFD をミュートにしました。
- **callOrMeetUpResume** - 以下の場合にトリガーされます。
  - ライブ会議または通話中に [**再開**] ボタンが選択されている。
  - PSTN で [再開] を呼び出す。
- **callOrMeetUpSearchParticipants** - 以下の場合にトリガーされます。
  - プライベート ライブ会議中にミーティング参加者で [**検索**] がクリックされた。
  - プライベート会議中に [**ロビー**] 参加者グループを表示した後、[**検索**] がクリックされた。
  - プライベート会議中に [**会議中**] 参加者グループを表示した後、[**検索**] がクリックされた。
  - プライベート会議中に [**招待済み他のユーザー**] 参加者グループを表示した後、[**検索**] がクリックされた。
  - ライブ チャネル会議中にミーティング参加者で [**検索**] がクリックされた。
  - ライブ チャネル会議中に [**ロビー**] 参加者グループを表示した後、[**検索**] がクリックされた。
  - ライブ チャネル会議中に [**会議中**] 参加者グループを表示した後、[**検索**] がクリックされた。
  - ライブ チャネル会議中に [**招待済み他のユーザー**] 参加者グループを表示した後、 [**検索**] がクリックされた。
- **callOrMeetUpVideoSwitch** - 以下の場合にトリガーされます。
  - ビデオをオンに切り替える。
  - ビデオをオフに切り替える。
  - ライブ会議または通話中に [ビデオ] ボタンを選択。
- **callPark** - 以下の場合にトリガーされます。
  - **パーク通話** が [**...**] メニューで 選択される。
  - [**保留解除**] ボタンが選択される。
  - 保留解除のダイアログで [**ピックアップ**] が選択される。
  - 保留解除のダイアログで [**キャンセル**] が選択される。
- **callPreferenceSetting** - 通話環境設定アプリの設定。
- **callsTabNewCall** - [**新しい通話**] が [**通話**] タブで選択されています。
- **callTransfer** - 通話呼び出しが開始されます。
- **callVoicemailTab** - [**ボイスメール**] タブが [通話] で選択されています。
- **cameraPermissionCancel** - [カメラのアクセス許可] ダイアログで [**キャンセル**] が選択されています。
- **cameraPermissionGoToSettings** - [カメラのアクセス許可] ダイアログから [**設定**] に移動します。
- **cancelEditMeeting** - [**会議の編集**] を選択した後、[会議のスケジューラー] ページで [**閉じる**] ボタンを選択します。 ユーザーが会議の編集の選択を破棄すると記録されます。
- **cancelFileShare** - 確認ダイアログで [**キャンセル**] が選択されています。
- **cancelFileUpload** - [**x**] がアップロード ダイアログで選択されています。
- **cancelMeeting** - [会議の詳細] ページで [**イベントをキャンセル**] を選択します。 取り消された会議の数について集計データを取得するために利用します。
- **cancelNavigationToLink** - ナビゲーションのキャンセルが選択されました。
- **cancelRequestToJoinTeam** - チームに参加する要求をキャンセルします。
- **cancelRequestToJoinTeamError** - 参加要求キャンセルのエラー。
- **cancelNewMeeting** - 放棄された [会議を作成] の選択をログして、以下の場合にその原因を検証します。
  - [会議スケジューラー] ページにいる間に [**閉じる**] ボタンが選択される。
  - [**会議の編集**] を選択した後、[会議スケジューラー] ページにいる間に [**閉じる**] ボタンが選択される。
- **cardView - No AS assigned** - カード ビューおよびカード レンダリング。 カードは主要なプラットフォーム コンストラクトで、その用途とパターンを測定することは、プラットフォームの用途を理解し、クライアント側の潜在的な問題を探し出すのに必要となります。 この項目は、チーム参加時のエラーを測定するのに必須です。
- **castPpt** - イベントが以下の場合にトリガーされます。
  - PowerPoint のオプションが選択される。
  - 特定の PowerPoint が選択される。
  - [ファイル ピッカー] ページで [Teams とチャネル] フォルダーを選択する。
  - [ファイル ピッカー] ページで [OneDrive フォルダー] を選択する。
  - キャスト セッションを停止する。
  - マルチタスク PiP をタップする。
  - ファイル ビューの表示オプションを選択する。
- **castScreen** - 参照先: 
  - [画面の共有] オプションをタップする。
  - [画面の共有] セッションを停止する。
  - ファイル ビューで表示オプションを選択する。
- **center_on_team_clicked** - ユーザーが正常にグループ中心にマップを配置しました。
- **channelFollow** - チャネルの通知をオンにします。
- **channelUnfollow** - チャネルの通知をオフにします。
- **channelsActiveSetting** - デスクトップで **アクティブな時を知らせる通知の** 通知設定が変更されます。
- **chatCreation** - チャットの作成に成功しました。
- **changeIsActiveSetting** - デスクトップ アクティビティ ベースの通知を変更します。
- **channel** - チャットの [新しいメッセージ] ボタンまたはテキストボックス。
- **channelDetails** - 以下の場合のチャネル ナビゲーション情報：
  - チャネル ヘッダーが選択されている。
  - チャネル詳細情報ページに移動する。
- **channelFollow/channelUnfollow** - チャネルをフォローするか、フォローを解除します。
- **channelNav** - 任意の場所からチャネルに移動します。
- **channelNavTab** - Teams のファイルに対して、以下の場合に成功および検出可能なデータを提供します。
  - [チャネル] で [**ファイル**] タブが選択されている。
  - コネクタ カードの返信がある。
- **channelNotificationSettings** - 以下の場合にトリガーされます。
  - [**新しい通知の設定**] ダイアログを選択。
  - チャネル ビューで [チャネル通知の設定] ボタンを選択。
  - チャネル通知設定を選択。
- **channelSelected** - 新しいプランのチャネルが正常に選択されたことを確認します。
- **channelSendMessage**- 以下の場合にトリガーされます。
  - チャネル メッセージの送信。
  - ボットが作成ボックスで @ メンションされる。
- **channelTabOverflow** - チャネルの **[その他]** タブを選択します。
- **チャット** - 参照先:
  - チャット内の [新しいメッセージ] ボタンまたはテキストボックス。
  - [callHistory] の項目で選択されている 1:1のチャット。
  - 通話リストでの 1:1のチャットの選択。
- **chat - No AS Assigned** - 特に以下のような場合、未読のチャットを表示、またはチャット参加者一覧を編集します。 
  - チャットにユーザーを追加する際に [**完了**] ボタンを選択する。
  - [未読] でフィルター処理を行うため、[チャットリスト] フィルタを選択する。
- **chatAddChat** - [チャット] ボタンをタップしてメンバーを追加します (これは 1:1のチャットとグループチャットで同じ)。
- **chatAllowJoinViaLink** - [チャットの詳細] ページの参加リンク機能を有効または無効にします。
- **chatAvatarEdit** - [チャットの詳細] ページで、自分のアバターを変更するグループの数を追跡します。
- **chatAvatarEditCamera** - ユーザーがライブ カメラ フィードでアバターを編集するとトリガーされます。
- **chatAvatarEditGallery** - ユーザーが電話のギャラリーでアバターを編集するとトリガーされます。
- **chatAvatarEditView** - ユーザーが既存のアバター画像を表示するとトリガーされます。
- **chatListNavConversations** - ユーザーがチャット リスト アイテムをタップしたとき。
- **chatCancelAudioCall** - グループ オーディオ通話のキャンセル - 確認ダイアログ。
- **chatCancelVideoCall** - グループ ビデオ通話のキャンセル - 確認ダイアログ。
- **chatCM_CopyText** - チャット コンテキスト メニューの [**テキストをコピーする**] をタップします。
- **chatCM_DeleteMessage** - チャット コンテキスト メニューの [**メッセージを削除する**] をタップします。
- **chatCM_edit** - チャット コンテキスト メニューの [**編集**] をタップします。
- **chatCM_Forward** - チャット コンテキスト メニューの [**転送**] をタップします。
- **chatCM_markUnread** - チャット コンテキスト メニューの [**未読にする**] をタップします。
- **chatCM_save** - チャット コンテキスト メニューの [**保存**] をタップします。
- **chatCM_SeenBy** - コンテキスト メニューの [**表示済み**] をタップします。 閲覧済みなど、開封確認。
- **chatContactsEnter** - **[チャットの連絡先**] タブを入力します。
- **chatDetails** - 以下の場合に、[チャットの詳細] ページの成功および検出可能なデータを提供します。
  - チャット ヘッダーが選択されている。
  - チャット詳細ページに移動する。
- **chatRecentEnter** - **[最近のチャット** ] タブを入力します。
- **chatSendMessage** - チャット メッセージを送信します。
- **chatShareLink** グループ招待リンクを送信するユーザーの数を追跡します。
- **chatStartAudioCall** - 以下の場合にトリガーされます。
  - [1:1のオーディオ通話] ボタンをタップする。
  - 検索結果の [**オーディオ**] ボタンをタップする。
  - 右側の [**通話開始**] ボタンをタップする。
  - [callHistory] の項目で [1:1のオーディオ通話] をタップする。
  - ボイスメールの項目で [1:1のオーディオ通話] をタップする。
  - グループ オーディオ通話の発信 - 確認ダイアログ。
- **chatStartAudioCallOnBehalfOf** - 代理人がアクション シートから上司として通話を開始します。
- **chatStartAudioCallOnBehalfOfMyself** - 代理人がアクション シートから自分自身として通話を開始します。
- **chatStartAudioCallSFB** - 1:1 [1:1のオーディオ通話] ボタンのタップ。
- **chatStartVideoCall** - 以下の場合にトリガーされます。
  - [1:1のビデオ通話] ボタンをタップする。
  - 検索結果の [ビデオ] ボタンをタップする。
  - [callHistory] の項目で [1:1のビデオ通話] をタップする。
  - グループ ビデオ通話の発信 - 確認ダイアログ。
- **chatStartVideoCallSFB**- 1:1 [1:1のビデオ通話] ボタンのタップ。
- **chatWithMeetingParticipants**- [会議の詳細] ページで [**チャット**] タブを選択します。
- **checkListAddClicked** - チェックリスト セクションの [タスクの詳細］で [**アイテムの追加**] が選択されています。
- **checkListItemAdded** - タスクのチェックリスト アイテムが作成されます。
- **checkListItemDeleted** - チェックリスト アイテムがタスクから削除されます。
- **checkListItemUpdated** - タスクのチェックリスト アイテムが更新されます。
- **bucketPickerClicked** - [チャネル ピッカー] が正常に起動したことを確認します。
- **checklistSeeAllClicked** [タスクの詳細] 内で [**すべて表示**] ボタンを選択して、すべてのチェックリスト アイテムを表示します。
- **chicletExpand** - モバイルでのカードのプレビューの様子や終了動作のプレビューを理解します。
- **clearFilter** - タスク リストの表示中にすべてのフィルターがクリアされます。
- **clickPhotoOfficeLens** - [**写真を撮る**] を選択 - カメラを起動します (アンドロイドのみ)。
- **clockInEntryTeamSelectionShown** - ユーザーが業務開始時間を記録していないチームを選択して、業務時間を記録します。　
- **clockInOutClicked** - 業務開始時間の記録画面で、[**業務開始時間を記録する**] または [**業務終了時間を記録する**] ボタンを選択します。
- **clockInOutTriggered** - ユーザーの業務開始または終了時間を登録します。位置が必要な場合は、位置が確認されるまでトリガーされません。
- **closedBannerMessage** - 通知のバナー メッセージを閉じるとトリガーされます。
- **closeLobbyBanner** - [**閉じる**] ボタンを使用してロビー トーストが閉じられる回数。
- **commentAdded** - コメントがタスクに追加されたことを確認します。
- **commentsClicked** - コメント ビューが正常に起動したことを確認します。
- **commentUpdated** - タスクのコメントが正常に更新されたことを確認します。
- **companionBannerJoin** - トップレベル バナーで [**参加**] を選択します。
- **companionDismiss** - コンパニオン バナーを閉じます。
- **companionDismissProximity** - コンパニオン バナーを閉じます。
- **companionJoin** - シートで [コンパニオン オプションとして参加] が選択されています。
- **companionJoinProximity** - コンパニオン バナーから参加しました。
- **completionStateChange** - タスク リストの [フィルター表示] で [完了済みフィルター] または [未完了フィルター] の切り替えが行われるとトリガーされます。
- **composeExpandComposer** - [**フォーマット**] ボタンがタップされました。
- **composeFilePick** - [ネイティブ ファイル ピッカー] が起動しました。
- **composeImagePicker** - [**画像**] ボタンをタップしました。
- **composeLocation** - [作成] で [**場所**] ボタンがタップされました。
- **composeMention** - @メンション。
- **composeOpenEmoticonPicker** - [絵文字ピッカー] がタップされました。
- **composeOpenFunPicker** - [娯楽ピッカー] がタップされました。
- **composeParticipantAdded** - シフト アプリに参加者が追加されたとき。
- **composeSearchResult** - メッセージ拡張機能の結果選択。アプリ検索結果の関連性を理解するのに役立ちます。 また、アプリ データを使用して、メッセージ送信テレメトリを強化します。
- **composeSelectExtension** - ME アプリ上でタップ。
- **composeSendMessage** - アプリ データを使用して、メッセージ送信テレメトリを強化します。
- **confirmAudioOn** - ユーザーがオーディオをオンにしたいことを確認します。
- **confirmFileShare** - 確認ダイアログで [**共有**] を選択します。
- **consultTransfer** - 以下の場合にトリガーされます。
  - [**転送**] > [**最初に問い合わせる**] を選択する
  - ターゲット セットをユーザーに転送する
  - ターゲット セットを電話番号に転送する。
- **consultTransferCall** - 以下の場合にトリガーされます。
  - 問い合わせ通話の開始。
  - [転送の確認] ダイアログで [確認] が選択される。
  - [転送の確認] ダイアログで [キャンセル] が選択される。
  - [**バナー転送**] ボタンが選択される。
  - [**バナー再開**] ボタンが選択される。
- **consultTransferChat** - 以下の場合にトリガーされます。
  - 問い合わせチャットの開始。
  - [転送の確認] ダイアログで [確認] が選択される。
  - [転送の確認] ダイアログで [確認] が選択される。
  - [**バナー転送**] ボタンまたは[**バナー再開**] ボタンが選択される。
- **consumeVoiceMessage** - 音声メッセージが再生されます。
- **ContactCard_SeeMoreOOF** - 長い不在メッセージを表示します。
- **contactOrganizer** - **[連絡先開催者**] が選択されました。
- **conversation, tabs** - タブが選択されました。
- **copyLink** - チャネル投稿へのリンクをコピーします。
- **contactActivity** - ユーザーのアクティビティを連絡先カードから表示するボタンが選択されたとき。
- **conversation** - ユーザーが [**チャット**] または [**投稿**] タブに移動したとき。
- **createChannel** - 新しいチャネル作成のために、以下のような場合に、正常な作成または破棄の操作に関する成功データを提供します。
  - [**完了**] ボタンが[**チャネルの作成**] ページで選択される。
  - [**キャンセル**] ボタンが[**チャネルの作成**] ページで選択される。
- **createComposeExtension** - メッセージの拡張機能の用途、またはアクション ME 用途を作成します。
- **createConversationClicked** - 他のユーザーと会話が作成されたとき。 
- **createDefaultPlannerPlan** - グループ内のユーザーによりタスク アプリが初めて開かれると共有リストが自動的に作成され、Planner サービスで作成された自動リストをチェックします。 ユーザーが初めて共有タスク リストを作成しようとするときに、Planner で既定の共有タスク リストが正常に作成されたことを確認します。
- **createOrJoinTeam** - **+** チームを作成またはチームに参加するボタンを選択します。
- **createPersonalPlan** - 個人用リストが作成され、ToDo サービスで作成されたリストをチェックします。 To Do リストで新しい個人タスク リストが作成されたことを確認します。
- **createPersonalSubtask** - 個人サブタスクが正常に作成されたことを確認します。
- **createPersonalTask** - 個人タスクが正常に作成されたことを確認します。
- **createPlan** - 共有タスク リストが正常に作成されたことを確認します。 共有プランが中間層で正常に作成されたことを確認します。
- **createPlannerPlan** - 共有リストが作成され、Planner サービスで作成されたリストをチェックします。 Planner で新しい共有タスク リストが作成されたことを確認します。
- **createPlannerTask** - Planner サービスの呼び出しをチェックします。 共有タスク リストでタスクが正常に作成されたことを確認します。
- **createShiftClicked** - マネージャーが [**シフトの作成**] を選択したとき。
- **createShiftOrTimeOffClicked** - [**シフトの作成**] または [**休暇**] を選択するとトリガーされます。
- **createTask** - 作成操作の失敗時に利用され、Planner サービスの呼び出しをチェックします。 タスクの作成操作が失敗したことを確認します。
- **createTaskList** - ユーザーが [ホーム] ビューから [プランの作成] ビューに移動したとき。
- **createTeam** - 新しいチーム作成のために、以下のような場合に、正常な作成または破棄の操作に関する成功データを提供します。
  - [**完了**] ボタンが[**チームの作成**] ページで選択される。
  - [**キャンセル**] ボタンが[**チームの作成**] ページで選択される。
- **createTeam, createChannel** - チームにメンバーを正常に追加し、以下の場合に新しいチームが正常に作成されると、成功データが提供されます。
  - [**スキップ**] ボタンを [**メンバーの追加**] ページで選択します (最初に既存をチェック)。
  - [**完了**] ボタンを [**メンバーの追加**] ページで選択します (最初に既存をチェック)。
  - チームやチャネル作成の確認が表示されます。
- **crossCloudDialogCancel** - クロス クラウド ダイアログに [**キャンセル**] を選択します。
- **crossCloudDialogJoin** - クロス クラウド ダイアログに [**ゲストとして参加**] を選択します。
- **dashboardNav** - ユーザーがチャット ダッシュボードのタイルに移動します。
- **dateChanged** - ユーザーがシフトの日付を変更しました。
- **datePickerLaunch** - [日付の選択] が正常に起動したことを確認します。
- **dayClicked** - ユーザーのシフトが表示されると、日ビューを選択します。
- **daySaved** -　ユーザーが対応可能な日付を保存すると、シフトの日付が保存されます。
- **declineTimeOffRequest** - ユーザーが職場の休暇要求を拒否するとき。 マネージャーが休暇要求を拒否するための休暇についての重要な機能です。
- **deleteClicked** - [タスクの詳細] で [**削除する**] が選択されると、確認ダイアログが表示されます。
- **deleteContact** - ユーザーが既存の個人連絡先を削除します。
- **deleteMeeting** - [会議の詳細] ページで [**削除**] ボタンを選択します。
- **deletePersonalTask** - 個人タスクが正常に削除されたことを確認します。
- **deletePersonalSubtask** - 個人サブタスクが正常に削除されたことを確認します。
- **deletePlannerTask** - 共有タスクの削除操作が正常に完了したことを確認します。
- **deleteShift** - シフトを削除します。
- **duration_picker_dismissed** - [期間の選択] を終了します。
- **deleteTask** - 削除操作が正常に行われたかどうかについて、Planner サービスで確認します。 タスクの削除に失敗した、つまりタスクの削除が正常に行われなかったことを確認します。
- **deleteVoicemail** - [ボイスメールを削除する] の項目がタップされました。
- **demotedToAttendee** - ユーザーが、ダイアログ ボックスの [**変更する**] ボタンで発表者を降格させます。
- **denyParticipant** - ユーザーが参加者一覧からの入場を拒否した回数。
- **descriptionChanged** - 共有タスクの説明が正常に変更されたことを確認します。
- **descriptionClicked** - ユーザーが [タスクの詳細] から [**説明を表示する**] を選択したとき。
- **detailsTabClicked** - 会議で [**詳細**] タブが選択されています。
- **deviceAddressBookSync** -[設定] ページでアドレス帳の同期が有効になっているときに始動します。
- **deviceAddressBookUnsync** - [設定] ページでアドレス帳の同期が無効になっているときに始動します。
- **dialIn** - ユーザーが会議へのダイヤルインを選択します (さまざまな場所)。
- **dialInBadNetworkBanner** - 接続不良のバナーに対して [**ダイヤルイン**] が選択されています。
- **dialInBadNetworkBannerCancel** - [**ダイヤルイン**]がネイティブ ダイアログでキャンセルされます。
- **dialInBadNetworkBannerConfirm** - [**ダイヤルイン**]がネイティブ ダイアログで確認されます。
- **dialInCall** - [**通話**] が [**ダイヤルイン**] ポップアップで選択されています。
- **dialInCancel** - [**キャンセル**] が [**ダイヤルイン**] ポップアップで選択されています。
- **dialOutCall** - ユーザーが以下を行うとトリガーされます。
  - ドライブ モードでの参加。
  - [**通話**] を [**もう一度通話する**] ポップアップで選択する。
- **dialOutCallAAD** - いずれかの番号がアクション シートの [**マイ ナンバー**] で選択されたとき。
- **dialOutCallRecent** - いずれかの番号がアクション シートの [最近使った番号] で選択されたとき。
- **dialOutCancel** - [**キャンセル**] が[**もう一度通話する**] ポップアップで選択されています。
- **dialOutDialog** - [**新しい番号**] がをアクション シートで選択されています。
- **dialOutFailRetry** - [**再試行**] がエラー バナーで選択されています。
- **DialPad** - 通話リストから [**DialPad**] ボタンが選択されています。
- **disableCategory** - 通知の種類を無効にするか、または着信呼び出し通知を無効にします。
- **disabled** - [最初の実行エクスペリエンス] で [**通知をスキップする**] が選択されています。 これにより、[最初の実行エクスペリエンス] フローで通知をスキップするための重要な成功データが提供されます。
- **disableQuietDays** - [通知オフ日] が無効です。 通知オフ日についての機能の成功テレメトリ。
- **disableQuietHours** - [通知オフ時間］ が無効です。
- **discoverTeams** - [チームを参照して参加する] ページに移動します。
- **Dismiss_earlycancelledCQF** - CQF の早期にキャンセルされた通話フォームを閉じます。
- **Dismiss_ratemycallCQF** - CQF の通話の評価フォームを閉じます。
- **Dismiss_ratemyliveeventCQF** - CQF のライブ イベント評価フォームを閉じます。
- **dismissBadNetworkBanner** - 不十分な接続バナーに対して [**閉じる**] が選択されています。
- **dismissFlyout** - [**閉じる**] が選択されています。
- **dismissModality** - モダリティ ピッカーを共有せずに終了します。
- **dismissModalityPicker** - [**モダリティピッカー**] ボタンが選択されています。
- **dismissReadReceiptsNotice** - [**OK**] が機能通知から選択されています。
- **dismissStartRecording** - レコーディングを開始すると、エラーが閉じられます。
- **dismissBadNetworkBanner** - レコーディングを停止すると、エラーが閉じられます。
- **dismissUseWifiForVideoBanner** - ユーザーが次のバナーを閉じるとトリガーされます。
  - リモート参加者のビデオがブロックされているため、ユーザーは WiFi に切り替えて表示しなくてはならないことをユーザーに通知するもの。
  - ユーザーが WiFi に切り替えてビデオを共有する必要があることをユーザーに通知するもの。
- **DLPDelete** - ユーザーがブロックされたメッセージを削除しました。
- **DLPEdit** - ユーザーがブロックされたメッセージを編集しました。
- **DLPOverride** - ユーザーがブロックされたメッセージを上書きしました。
- **DLPOverrideReport** - ユーザーが誤検知を報告し、メッセージを上書きしました。
- **DLPReport** - ユーザーが誤検知を報告しました。
- **DLPResolve** - ユーザーが DLP メッセージの解決を試みました。
- **DLPSeeOriginal** - ユーザーが元のメッセージを表示するためにタップしました。
- **downloadFile** - 以下のことに役立ちます。
  - ダウンロード操作が開始されたかどうかを判断します。
  - ファイルが正常にダウンロードされたかどうかを判断します。
- **dragDatePickerHandle**
- **DialPad の dtmfPSTNCall** - ダイヤルパッドの DTMF ボタンがタップされます。
- **dueDateChanged** - ユーザーが期限をタスクに割り当てるときにトリガーされます。
- **dueDatePickerClicked** - [タスクの詳細] で [**期限**] ボタンが選択されて、[期限ピッカー] ページが開くと、トリガーされます。
- **dueDateSelected** -　ユーザーがタスク リストの表示中に期限によりフィルターを適用するとトリガーされます。
- **dueDateUnselected** - ユーザーがタスク リストの表示中に期限によりフィルター適用を外すとトリガーされます。
- **edit** - チャット メッセージの [**編集**] ボタン。
- **editChannel** - ユーザーが所有または管理しているチャネルを編集するためのボタンを選択します。
- **Edit Contact** - ユーザーが既存の個人連絡先を編集する場合は、連絡先カードに移動すると行えます。
- **editMeetingResponse** - [会議の詳細] ページで会議の応答を編集します。
- **editNavigation** - [**並べ替える**] を [**その他**] メニューで選択して、下部バー アプリの順番を編集します。
- **editRsvpMeetingOptions** - [**出欠確認**] を選択して、以前の選択を変更します。
- **editShiftClicked** - シフトを編集します。
- **editTeam** - ユーザーがボタンをタップして、所有または管理しているチームを編集します。
- **editTeam、Edit Channel** - 以下の場合のチームへの正常なメンバー追加と、既存チームの正常な作成に関連。
  - [**キャンセル**] ボタンを [**メンバーの追加**] ページで選択します (既存チームまたはチャネル)。
  - [**完了**] ボタンを [**メンバーの追加**] ページで選択します (既存チームまたはチャネル)。
- **emergencyCall** - 通話プランが設定された緊急通報。
- **emergencyCallDirectRouting** -直接ルーティングが設定された緊急通報。
- **emergencyCallLocationPolicyBased** - ダイヤルパッドを使用する緊急ダイヤル。
- **emergencycallSecurityDeskNotify** -緊急通報、セキュリティデスクに通知します。
- **enableCategory** - 以下を有効にするときの通知の設定に関連。
  - 通知の種類。
  - 着信通知。
- **enabled** - 最初の実行エクスペリエンス フローでの通知の有効化に関連。
  - **Enable notifications** が [最初の実行エクスペリエンス] で選択されています。
  - リマインダーで [有効化] が選択されています。
- **enabled/disabled** - 通話中のアクセス許可または連絡先のアクセス許可 (Android のみ)。
- **enabled, notNow** - 通知アクセス許可のプロンプト [**同意**] ボタン、最初の実行エクスペリエンスの通知アクセス許可 (iOS)。 これにより、通知機能を有効にしているユーザー数がキャプチャされ、情報が提供されます。
- **enablediOSPrompt** - ユーザーが実際に iOS 通知アクセス許可のプロンプトで通知を有効にします。 これにより、通知アクセス許可のプロンプトから iOS で実際に通知を有効にしているユーザーについての情報が得られます。
- **enabledQuietDays** - [通知オフ日］ が有効です。
- **enableLocationPermission** - ユーザーが共有場所の機能に対して場所のアクセス許可を有効にしたとき。
- **enableQuietDays** - ユーザーが [通知オフ日] を有効にします。
- **disableQuietHours** - [通知オフ時間］ が有効です。
- **endEditing** - [**保存**] ボタンが押されました。
- **endFileShare** - [**戻る**] がファイル共有ダイアログで選択されています。
- **endMyShift** - 共有モードのデバイスの数またはサインアウトした回数。
- **endPhotoShare** - 写真共有からの [**x**]。
- **entryPointClicked** - [**スケジュール**] タブの [**リクエスト**] を選択します。リクエストは現場担当者がシフト時間などをリクエストする場合に使用するものです。
- **endPSTNCallSelected** - ユーザーが PSTN およびコンテンツの呼び出しを終了します。
- **endPSTNCallShown** - ユーザーにプロンプトで PSTN またはコンテンツの呼び出しを終了するように求めます。
- **endVideoShare** - ビデオ共有からの[**x**]。
- **errorShown** - エラーが表示されています。
- **expand/collapse** - デバイスの連絡先または会社の連絡先セクション。
- **expandCollapseSection** - セクション ヘッダーをタップしてセクションを展開するか、または折りたたみます。
- **Expected: atMention - Android: chatSendMessage - iOS: sendMsg** - 作成ボックスでボットに@メンション。
- **Expected: botClickCardAction - Android: showCard - iOS: missing** - カードボタンのタップ。 カードは主要なプラットフォーム コンストラクトで、その用途とパターンを測定することは、プラットフォームの用途を理解し、クライアント側の潜在的な問題を探し出すのに必要となります。
- **Expected: chatSendMessage - iOS: composeSendMessage** - [**返信**] をタップして、チャネルのチャット ボットに返信します。
- **Expected: composeSendMessage - Android: replyChannel - iOS: missing** - [**返信**] をタップして、チャネルのチャット ボットに返信します。
- **Expected: messageLike - Android: reactLike_CM** - ボット メッセージにいいね! をします。
- **Expected: messageUnread - Android: markAsLastUnread** - ボット メッセージ向けのメッセージ コンテキスト メニュー オプション。
- **federatedUpgradeNewChat** - レガシ チャットがネイティブにアップグレードされます。
- **ファイル** - チャットとチャネルの [ファイル] タブでファイル リストが正常に完了したかどうかを追跡します。
- **fileSelected** - PowerPoint プレゼンテーションが選択されています。
- **fileThumbnailPreviewDownloaded** - ファイルのサムネイルの正常なレンダリングを特定する手助けをします。
- **fileThumbnailPreviewFromCache** - サムネイルが正常にキャッシュから表示されているかどうかをキャプチャし、ファイルのサムネイルが正常にレンダリングされているかを特定します。
- **fileThumbnailPreviewNotAvailable** - ファイルのサムネイルの正常なレンダリングを特定する手助けをします。
- **fillFrameVideo** - アクション シートからフレームを塗りつぶします。
- **firstTimeSignedIn** 以下によるサインインまたはサインアップ イベント。
  - サインインに成功。
  - 初回サインインに成功しました。
  - サインイン エラーがユーザーに表示されます。
  - 初回ログイン時に実装される MAM/MDM ポリシーに関するテレメトリを記録します。
  - 初回ログインに成功した後、アプリ インストール参照元パラメーターを記録します。
- **fillFrameVideo** - アクション シートからフレームに自動調整します。
- **flipCamera** - カメラの反転。
- **forcedUpdateAccept** - ユーザーが [更新の強制] ダイアログでアプリのバージョン更新を受け入れます。
- **forcedUpdateExit** - ユーザーが [更新の強制] ダイアログでアプリのバージョンを更新するのではなく、アプリを終了します。
- **forcedUpdatePrompt** - 最新のセキュリティおよびプライバシーの修正が行われていない可能性がある旧バージョンのユーザーに連絡を取る必要がある状況で使用します。
- **formattingBold** - ユーザーが太字の書式設定を選択します。
- **formattingHighlight** - ユーザーが蛍光ペンの書式設定を選択します。
- **formattingImportant** - ユーザーが重要度を選択します。
- **formattingItatlics** - ユーザーが斜体を選択します。
- **formattingTextColor** - ユーザーがテキストの色の書式設定を選択します。
- **formattingUnderline** - ユーザーが下線を選択します。
- **FRE - No AS Assigned** - アプリの起動に関する MAM/MDM ポリシーに関するテレメトリを記録します。 MAM および MDM の Intune 統合のテレメトリ。 [最初の実行エクスペリエンス] の間のエラーについて成功データを提供します。
- **freActionClicked** - [最初の実行時エクスペリエンス] で、[**開始する**]、[**後で試す**]、または[**閉じる**] （GPS）が選択されています。
- **freDone** - 最初の実行エクスペリエンスが完了しました。
- **freTriggered** - ユーザーが最初の実行エクスペリエンスの業務時間記録を閲覧します。
- **funSearchQueryEntered** - Giphy クエリを実行しました。 Teams の giphy 添付ファイル機能の成功データ。
- **funSelectItem** -Giphy の画像が選択されました。 Teams の giphy 添付ファイル機能の成功データ。
- **galleryImage** - 画像がアップロードされました - ギャラリー。
- **get_directions_clicked** - [**ルート案内を使用する**] が選択されています。
- **goToNotificationSettings** - [**通知設定を更新しました**] のダイアログから [通知設定] ページに移動します。
- **GPSPromptClicked** - [**許可**] または [**許可しない**] が OS のプロンプトで選択されています。 GPS を許可するかどうか。
- **group_map_closed** - ユーザーがチャットからマップを開きます。
- **group_map_open** - ユーザーがマップ ビューを閉じます。
- **groupCallJoin** - ユーザーがグループ通話に参加します。
- **groupClicked** - ユーザーがシフト グループを選択すると追跡します。
- **guideMe** - ユーザーが 3P アプリのブロック通知を行い、トラブルシューティング ガイダンスを提供するバナーを選択します。
- **hamburgerMenu** - [ハンバーガー] メニューに移動します。 [ハンバーガー] メニューには、[アカウントの切り替え]、[通知の設定]、[データの設定]、[プロファイルの設定] など、重要なアクションが含まれています。
- **handoffComplete** - このデバイスで会議や通話が引き継がれました。
- **handoffJoin** アクション シートで会議のハンドオフ オプションが選択されています。
- **hardwareAudioOff** - ハードウェア ボタンからオーディオをオフにします。
- **hardwareAudioOn** - ハードウェア ボタンからオーディオをオンにします。
- **hide** - チャットを非表示にします。
- **hideChannel** - チームとチャネル リストからチャネルを非表示にします。
- **image** - 画像。
- **immediateCallForward** - 即時通話転送先が設定されている、または即時通話転送が有効 ([通話を自分に着信する] は無効) になっている場合。
- **importanceToggleClicked** - [**!**] フィールドが タスク アイテムの詳細内に切り替えられるとトリガーされます。
- **importantMessage_select** - ユーザーが重要なメッセージを優先コンテキスト メニューから選択します。
- **importantMessageSend** - ユーザーが重要なメッセージを送信します。
- **inCallDialOut** - ユーザーが [**もう一度通話する**] ボタンをその他の通話オプションから選択します。
- **initiatePhotoShare** -　写真共有を開始します。
- **initiateVideoShare** - ビデオ共有を開始します。
- **install** - インストールまたはイベントのインストール。
- **installReferrer** - 初回インストール後、アプリ インストール参照元パラメーターを記録します。
- **invisionWhiteboardClicked** - Invision ホワイト ボードが選択されています。
  - [**チャネル ファイル**] タブ。
  - 会議の [**チャット ファイル**] タブ。
- **inviteFreemium** - [招待] 画面の **+** ボタンをタップします。
- **inviteGuest** - [招待] 画面の **+** ボタンをタップします。
- **joinFromDeeplinkInTeams** - ディープリンクを介してユーザーが Teams アプリ内から参加しました。
- **joinFromDeeplinkOutsideTeams** - ディープリンク外からユーザーが Teams アプリ内から参加しました。
- **joinFromJoinLauncher** - ユーザーが参加起動ツールから参加しました。
- **joinFromNudge** - ユーザーがナッジから参加しました。
- **joinFromStore** - ユーザーがアプリ ストアからアプリをダウンロードした後に参加しました。
- **joinMeeting** - 以下のような状況で、カレンダーから会議への参加の成否を検出します。
  - [ダイヤルイン] で会議に参加します。
  - [もう一度通話する] で会議に参加します。
  - 会議コンテンツにのみ参加します。
  - [予定一覧] ビューで [**会議参加**] ボタンを選択します。
- **joinOptionsEdu** - EDU ユーザーが、スケジュール済みの会議に参加するためのオプションを選択すると、適切なオプションが表示されます。
- **joinTeam** - [**参加**] ボタンが押されました。
- **joinViaCode** - ユーザーがコードによって会議に参加します。
- **labelPickerClicked** - [ラベル ピッカー] が正常に起動したことを確認します。
- **labelSelected** - ラベルの選択が完了したことを確認します。
- **labelUnselected** - ラベルと選択解除が完了したことを確認します。
- **launchLinksGallery** - ユーザーがダッシュボードからリンク ギャラリーに入ります。
- **Launch source such as direct, link, appShortcut** - 直接またはリンクを介して起動します (アクティブなユーザーのデータを収集するために、アプリ起動時にモバイル アプリケーション管理 (MAM) またはモバイル デバイス管理 (MDM) テレメトリを記録します)。
- **leaveChat** - チャット終了を確認します。
- **legacyChatLink** - レガシ チャットにリンクが選択されています。
- **likeAppDismiss** - ユーザーがアプリを気に入ったかどうかを尋ねるプロンプトが表示され、応答がなければ終了します。
- **likeAppNo** - ユーザーがアプリを気に入ったかどうかお尋ねるプロンプトにより、「いいえ」の応答を受信しました。
- **likeAppYes** -ユーザーがアプリを気に入ったかどうかお尋ねるプロンプトにより、「はい」の応答を受信しました。
- **likeMsg** - [**いいね**] を選択します。
- **linkPreviewCancel** - プレビュー終了の動作を理解します。
- **listUserClicked** - ユーザーが [現在作業中] を選択したとき。
- **liveCaptions** - ライブ キャプションをオンまたはオフに切り替えます。
- **liveEventAdditonalLink** - 追加リンクが選択されました。
- **liveEventInfo** - [**情報**] ボタンが選択されました。
- **liveEventJoin** - ユーザーがライブ イベントに参加します。
- **liveEventLeave** - [**退出**] ボタンが押されます。
- **liveEventPresenterJoin** - ライブ イベントに発表者が参加します。
- **liveEventPresenterJoinAsAttendee** - ライブ イベントの発表者が出席者として参加します。
- **liveEventQnA** - [**Q＆A**] アイコンが選択されています。
- **liveEventYammer** - **Yammer** アイコンが選択されています。
- **liveMeetingPushNotificationClicked** - プッシュ通知が選択されています。
- **liveMeetingToastClicked** -　アプリ内トーストが選択されています。
- **live_location_in_chats_from_profile_clicked** - [**ライブ位置情報**] がプロフィール ビューで選択されています。
- **lobbyPickAudio** - ユーザーがロビーからオーディオ出力を切り替える回数。
- **lobbyToggleMuted** - ユーザーがロビーでマイクをオンまたはオフにした回数。
- **lobbyToggleVideo** - ユーザーがロビーでビデオをオンまたはオフにした回数。
- **logOutClicked** - ユーザーがログアウトしたとき。
- **location_active_tracking** - ユーザーのデバイスが [アクティブな追進捗管理] に切り替えられます。
- **locationCard** - 位置カードを選択します。
- **location_family_sync** - MSA ファミリ アプリで作成されたファミリ グループのメンバーが表示されています。 同意を得ることの可能なファミリの全メンバーが表示されることを確認します。
- **location_group_map_sync** - マップ ビューが開きます。
- **location_map_load** - マップビューを読み込みます。
- **location_map_markers_load** - マップビューを読み込みます。 マップ ビューに、アクティブに共有中のすべてのユーザーの位置マーカーが正しく表示されることを確認します。
- **location_message_send** - ユーザーが位置共有セッションを開始します。
- **location_data_use_privacy_denied** - ユーザーが TFL による位置データの使用を説明するポップアップで [**今はしない**] を無視する、または選択します。
- **location_data_use_privacy_granted** - ユーザーがTFL による位置データの使用を説明するポップアップで [**許可**] を無視する、または選択します。
- **location_settings_open** - ユーザーが位置情報の設定を開きます。
- **location_sharing_start** - ユーザーがチャットでライブ位置情報を共有します。
- **location_sharing_stop** - ユーザーがチャットでライブ位置情報の共有を停止します。
- **loginFailed** - ユーザーがログインできませんでした。
- **loginSuccess** - ユーザーがログインできました。
- **manageBlockedNumbers** - 設定でブロックされた回数にアクセスします。
- **mapAppPicker** - ユーザーが位置カードのタップ時に使用するマッピング アプリを選択したとき。
- **markAsRead** - 開封済みにします。
- **markAsUnread** - 未開封にします。
- **markChannelRead** - ユーザーがチャネル読み取りを設定します。
- **messageBookmarkMessage** - コネクタ カードの保存。 アプリ固有のデータで既存のテレメトリを使用します。 またはボット メッセージを保存します。
- **markAsLastUnread** - コネクタ カードのコンテキスト メニュー。
- **maskCallerId** - ユーザーが発信者番号のマスクのために呼び出し設定を有効または無効にします。
- **meetingDetailCalendarList** - カレンダー リストで [会議の詳細] ページを選択し、[会議の詳細] ページの [**詳細**] タブを選択します。
- **meetingDetailChatWithParticipants** - [会議の詳細] ページで参加者とチャットします。
- **meetingDetailDeleteMeetingforSelf** - 自分用に [会議の詳細] ページから会議を削除します。
- **meetingDetailJoin** - [会議の詳細] ページで [**会議参加**] ボタンが選択されています。
- **meetingDetailParticipants** - [会議の詳細] ページですべての参加者を表示します。
- **meetingDetailScheduledMeeting** - スケジュール済み会議オブジェクト （**…**）から [会議の詳細] ページを選択、または、スケジュール済み会議の [**詳細**] タブを選択します。
- **MeetingDetailSearchParticipants** - 会議スケジュールの会議参加者で [**検索**] が選択された。　
- **meetingJoinLeave** - [**参加**] ボタンをタップした後、タップを止めて [**x**] をタップします。
- **meetingJoinNow** - [**VOP に今すぐ参加**] が選択されました。
- **meetingJoinNowWithCallMe** - ユーザーが [**通話する**] で会議に参加します。
- **meetingJoinNowWithPSTN** - ユーザーがダイヤルインで会議に参加します。
- **meetingLeaveChat** - チャットを終了します。
- **meetingMuteChat** - チャットをミュートします。
- **meetingNotesCreatedInChatLink** - **作成済み** 会議ノートのチクレットがプライベート会議チャットまたはチャネル会議チャットで選択されます。
- **meetingNotesMentionCharLink** - プライベート会議チャットで [@mention] のリンクが選択されています。
- **meetingNotesMentionChatLink** - チャネル会議チャットで [@mention] のリンクが選択されています。
- **meetingNotesTabEntryPoint** - [**会議ノート**] タブが [プライベート会議] または [チャネル] で選択されています。
- **meetingNotificationSettingsAccepted** - 通知設定オプションが [承認済み] のみに変更されました。
- **meetingNotificationSettingsAll** - 通知設定オプションが [すべて] に変更されました。
- **meetingNotificationSettingsNone** - 通知設定オプションが [なし] に変更されました。
- **messagePriority_select** - メッセージの優先度入力ポイントが選択されています。
- **messageSeeOriginal** - ユーザーが翻訳されたメッセージを元のメッセージに戻します。
- **meetingSeeParticipantsChatDetails** - すべての参加者を表示します。
- **memberListLoadMore** - 下にスクロールしてさらに読み込みます。
- **messagedEditMessage** - ユーザーがメッセージを編集します。
- **messageShareMessage** - メッセージを共有します。
- **messageTranslate** - ユーザーがメッセージを翻訳します。
- **messageUnabletoEdit** - ユーザーがメッセージを編集できません。
- **meetingUserAnonB2B** - 匿名 B2B が会議に参加しました。
- **meetingUserAnonB2C** - 匿名 B2C が会議に参加しました。
- **meetingUserDialIn** - PSTN (ダイヤルイン) ユーザーが会議に参加しました。
- **meetingUserDialOut** - PSTN [もう一度通話する] ユーザーが会議に参加しました。
- **meetingUserFederated** - フェデレーション ユーザーが会議に参加しました。
- **meetingUserFreemium** -　フリーミアム ユーザーが会議に参加しました。
- **meetingUserGuest** - ゲスト ユーザーが会議に参加しました。
- **meetingUserTenant** - テナント内ユーザーが会議に参加しました。
- **messageCopyMessage** - メッセージをコピーします。
- **メッセージ削除** - メッセージの削除。
- **messageEditMessage** - メッセージを編集します。
- **messageForwardMessage** - ユーザーがメッセージ コンテキスト メニューから [転送エントリポイント] を選択します。
- **messageLike/messageUnlike** - メッセージのいいね! またはその解除。
- **messageMuteSender** - 送信者のミュートまたはミュート解除。
- **messageLike** - コネクタ カードのいいね!。 アプリ固有のデータで既存のテレメトリを使用します。
- **messageScheduledMeeting** - 選択されたチャネルの会議オブジェクト (スケジュール済みのものだけではない)。
- **messageTriggered** - メッセージに対して通知がトリガーされた場合。
- **micPermissionCancel** - [マイクのアクセス許可] ダイアログで [**キャンセルl**] が選択されています。
- **micPermissionGoToSettings** - ユーザーが [マイクのアクセス許可] ダイアログから設定に移動します。
- **MicrosoftWhiteboardClicked** - Microsoft ホワイト ボードが [**チャネル ファイル**] タブまたは [**会議チャット ファイル**] タブで選択されています。
- **moreOptionsClicked** - 右上の [**...**］ が [タスク アイテム エディター] 画面で選択されるとトリガーされます。
- **moveTaskClicked** - タスク アイテム内のオプションのその他のオプション リスト。
- **multiCallEndFromUFD** -　ユーザーが、マルチ呼出しのシナリオで保留通話を終了した回数。
- **multiCallResumeFromUFD** - ユーザーが通話を保留から再開することにした回数。
- **multiCallSwitch** - ユーザーが通話を切り替えるオプションを選択して、保留通話のリストが表示される回数。
- **multipleAccounts** - ユーザーのアカウント数。
- **multipleTenants** - アカウントあたりのテナント数。
- **mute** - チャットをミュートする。
- **muteOnWhiteboard** - ユーザーがホワイトボード画面でユーザーのミュートまたはミュート解除を行います。
- **muteParticipant** - 参加者のミュート (アクション シートへの移動)。
- **my_location_button_clicked** - ユーザーが [**自分の所在地**] ボタンを選択して、自分の位置をマップ中央に配置します。
- **my_location_clicked** - ユーザーがマップ上の **青い点** を選択して、自分の位置をマップ中央に配置します。
- **myShiftPickerClicked** - 送信された要求が割り込みかプランの場合にのみログされます。 [**自分のシフト**] ピッカーが選択されています。
- **nameGroupChat** - グループのチャットに名前をつけます。
- **nativeTimeClockBreak** -　業務時間記録上の休憩。
- **nativeChatLink** - ネイティブ チャットへのリンクが選択されています。
- **navActivity**-　[アクティビティ フィード] ページに移動します。

- **navBookmark** - ユーザーが、下部バーまたはアプリ トレイで [**保存済み**] タブまたはアプリに移動します。
- **navCalendar** - ユーザーがカレンダーに移動した場合に測定します。
- **navCallingSettings** - ユーザーが通話設定に移動します。
- **navCalls** - [**通話**] タブがタップされました。
- **navCamera** - ユーザーが、下部バーまたはアプリ トレイで [**カメラ**] タブまたはアプリに移動します。
- **navChat** - ユーザーが、下部バーまたはアプリ トレイで [**チャット**] タブまたはアプリに移動します。
- **navContacts** - ユーザーが、下部バーまたはアプリ トレイで [**連絡先**] または [**ユーザー**] タブまたはアプリに移動します。
- **navDashboardTab** - ユーザーが会話内の[**ダッシュボード**] タブに移動します。
- **navDynamics365** - Dynamics365 アプリが開いたときにトリガーされます。
- **navFiles** - ファイル アプリが選択されると、ユーザーがアプリ トレイ (iOS) でファイル アプリを起動できるかどうか追跡します。
- **navFilesTab** - ファイル アプリが選択されると、ユーザーが下部のナビゲーション バー (iOS) でファイル アプリを起動できるかどうか追跡します。
- **navMeetings** -  [**カレンダー**] タブがタップされました。
- **navNotes** - ノート アプリが開いたときにトリガーされます。
- **navOrganization** - 組織アプリが開いたときにトリガーされます。
- **navOrgChart** - Orgchart アプリが開いたときにトリガーされます。
- **navPeople** - People アプリを開くとイベントがトリガーされます。
- **navPeopleSettings** - 設定メニューで [**ユーザー**] カテゴリに移動するとトリガーされます。
- **navPersonalFiles** - ファイル アプリが選択されると、ユーザーが下部のナビゲーション バー (Android) でファイル アプリを起動できるかどうか追跡します。
- **navPhotoTab** - [**写真**] タブ。
- **navSaved** - ユーザーが、下部バーまたはアプリ トレイで [**保存済み**] タブまたはアプリに移動します。
- **navSelectPlan** - ユーザーが移動先の共有プランをホーム ビューから選択したとき。
- **navSelectPersonalList** -　ユーザーが移動先の個人プランをホーム ビューから選択したとき。
- **navSelectSmartList** - ユーザーが移動先のスマート プランをホーム ビューから選択したとき。
- **navTasks** - タスク アプリが開いたときにトリガーされます。
- **navTeams** - [**すべて表示**] をタップします。
- **navVideocamera** - ユーザーが、下部バーまたはアプリ トレイで [**カメラ**] タブまたはアプリに移動します。
- **navVideoTab** - [**ビデオ**] タブ。
- **navVoicemail** - ユーザーがボイスメール ページに移動します。
- **navWalkieTalkie** - ユーザーがトランシーバー アプリを開きました。
- **navWiki** - Wiki アプリが開いたときにトリガーされます。
- **newChat** - ユーザーがチャットを作成します。
- **newCall** - [**新しい通話**] ボタンをタップします。
- **newCallDialPad** - タブの[**ダイヤルパッド**] ボタンをタップします。
- **newCallPeople** - タブの [**ユーザー**] ボタンをタップします。
- **noBGActivityDetected** - 背景アクティビティのエラーのしきい値を超過しました。
- **notBlockedDevice** - ユーザーが 30 日間の背景アクティビティのエラーのしきい値に達していません。
- **notNow** - [**今はしない**] がリマインダーで選択されています。
- **notNowUpdate** - 更新保留。
- **notificationNavChannelConversation** - チャネルの会話の通知を使用してアプリを起動します。
- **notificationNavChannelThreadConversation** - チャネルの会話の特定のメッセージの通知を使用してアプリを起動します。
- **notificationSettingTurnedOff** - Teams Android アプリのプッシュ通知を無効にします。
- **notificationNavPreCall** - ユーザーは、選択時にプレコール自画面に移動する会議の開始通知を受け取ることができます。
- **ocvFeedback** - OCV フィードバック フォームのパフォーマンスに関連。
- **ocvFormCancelled** - OCV フィードバック フォームが取り消され、ユーザーがアプリに戻るときに送信されるイベント。
- **ocvFormOpened** - OCV フォームが開かれたときに送信されるイベント。
- **ocvFormSubmit** - ユーザーが OCV フィードバック フォームで [送信] を選択したときに送信されるイベント。
- **offerRecipientClicked** - 送信された要求がプランの場合にのみログされます。 ユーザーがチーム メンバー ピッカーを入力してシフトを提示します。 オファリングとは、シフト休暇のことです。
- **offerSwapShiftFromL1** - ユーザーがシフト リストの提示または割り込みを試すシフトの種類。 iOS での操作は **右にスワイプ** で、Android での操作は **長押し** です。
- **offerSwapShiftFromL1Triggered** - ユーザーが別のユーザーとシフトを交換できます。
- **officeLens** - アプリが officeLens カメラ機能を起動すると、以下のいずれかの場合に始動します。
  - ユーザーがメッセージに画像を添付しようとする
  - ユーザーが写真を撮影して、ギャラリーに直接アップロードしようとする。
- **officeLens or cameraImage** - カメラ画像が選択されています - 標準のカメラもしくは Office Lens。
- **onBackClicked** - [戻る] 矢印をクリックするといつでも元のページに移動します。
- **oneNote** - ユーザーが OneNote アプリを開いたとき。
- **open** - [通知設定] のタップ。
- **open edit** - Wiki 用途テレメトリ - ユーザーが wiki を編集するために選択します。
- **openApp** - 個人用アプリを開きます。
- **openAppDrawer** - 下部バーで [**その他**] を選択してアプリ ドロワーを開きます。
- **openEditMeetingForm** - [会議の詳細] ページで [**編集**] ボタンが選択されています。
- **openFile** - 以下をサポートします。
  - チャットで正常に開くことのできたファイルを特定する。
  - ファイル リストで正常に開くことのできたファイルを特定する。
  - OneDrive のリストからファイルを開くことができるかどうかを確認する。
  - 特定するには、チャンネルリストから開くことができるオープン ファイルを特定する。
  - グループ チャットからファイルを開くことができるかどうかを判断します。
  - ファイルをファイルアプリから正常に開くことができるかどうかを判断します。
  - チクレットからメッセージ ファイルを正常に開くことができるかどうかを判断します。
  - 最近使用したファイルのリストからファイルを正常に開くことができるかどうかを判断します。
  - ファイルのリストからファイルを正常に開くことができるかどうかを判断します。
  - チクレットからファイルを開くことができるかどうかを判断します。
  - ファイル リストからファイルを正常に開くことができるかどうかを判断します。
- **openInAppClicked** - タスク アイテム内のその他のオプション リスト、個人用タスクでのみ使用可能。
- **opensCalendarView** - [**スケジュール**] タブの [**空きシフト**] をタップします。
- **openContactCard** - ユーザーが [**連絡先**] アイコン、または、ユーザー アプリの連絡先をタップして、その連絡先のプロファイル カードを起動します。
- **openContactCard_ReactionSummary** - [リアクション サマリー] ページから連絡先カードに移動します。
- **openFileInApp** - ユーザーが Teams 外で、または Teams 内部でファイルを開くことを選択したかどうか特定するのに役立ちます。
- **openHamburgerMenu** - [**ハンバーガー**] アイコン (左上) を選択して、[設定]、[プレゼンス]、[テナント切り替え] にアクセスするため、サイド メニューを開きます。
- **openInStream** - Stream でビデオを開きます。
- **openMeetingDetails** - [会議の詳細]、または特定の会議の [会議を開く] の詳細ページを開きます。
- **openModalityPicker** - X = チャットとチャネル向けChatsAndChannels。
- **openNewMeetingForm** - サブタスクが正常に更新されたことを確認します。
- **openNewMeetingForm** - 新しい会議を設定するときにスケジューラーを開きます。
- **openPhotoLibrary** - フォト ライブラリを選択します。
- **openQuietDays** - [通知オフ日] ページに移動します。
- **openQuietHours** - [通知オフ時間] ページに移動します。
- **openReactionHoverBubble** - [リアクション サマリー] ページで **[リアクションの追加]** ボタンを押します。
- **openReactionSummary** - リアクション サマリー ドロワーを呼び出します。
- **openSettingsSetUpInstructions** - 手順から [**設定**] を開きます。
- **openSharedLink** - ユーザーがダッシュボード リンク タイルまたはリンク ギャラリーからリンクを開いたとき。
- **openShiftsClicked** - [**カレンダー**] アイコンをタップするユーザー数。
- **orgChart - No AS assigned** - 組織図の基本的用途テレメトリ。
- **pageEntered** - ユーザーがページを入りました。
- **parental_consent_grant** - ユーザーが MSFamily で未成年に対し、TFL でライブ位置情報機能を利用するためのアクセス許可を付与します。
- **parental_consent_remove** - ユーザーが MSFamily で未成年に対し、TFL でライブ位置情報機能を利用するためのアクセス許可を取り消します。
- **pauseVoicemail** - ボイスメール アイテムで [**一時停止**] がタっプされました。
- **peoplePickerInvoked** - People Picker が以下を含む (がそれに限定されない) Teams モバイルの 7 か所で使用されます。
  - 新しいチャット ピッカー。
  - メッセージを転送します。
  - 会議に参加者を追加します。
- **personalAppNavBotChat** - 個人用アプリ内のボットに移動します。
- **personalAppNavTab** - 個人用アプリ内のタブに移動します。
- **photoLibraryPicker** - [画像選択] で [**フォト ライブラリを開く**] がタップされました。
- **pickGalleryPhoto** - ギャラリーから写真を選択します。
- **pickParticipantChatDetails** - リストからユーザーを選びます。
- **pickRecentPhoto** - 共有する最近使用した画像を選びます。
- **pinChannel** - チャネルをピン留めして、チームとチャネル リストの上に表示します。
- **Pin セルフ** - アクション シートで自分自身をピン留めします。
- **pinUser** - アクションシートでユーザーをピン留めします。
- **play** - レコーディングを再生します。
- **playVoicemail** - ボイスメール アイテムで [**再生**] がタップされました。
- **plusButtonClicked** - **プラス記号ボタン** (**+**) を選択します。
- **pptNextSlide** - 発表者として、または個人用表示での次のスライド。
- **pptNextSlide** - 発表者として、または個人用表示での前のスライド。
- **pptReturnToPresenter** - [**ライブ**] スライド (発表者とその他全員がオンになっているもの) に移動します。
- **pptStopPresenting** - プレゼンテーションの停止。
- **pptTakeControl** -コントロールします。
- **preJoinAddRoom** - 事前参加ドロップダウンで [**会議の追加**] ボタンが選択され、[**参加**] が [**部屋を追加**] とシナリオで選択されています。
- **preJoinAudioOff** - 事前参加ドロップダウンで [**音声オフ**] ボタンが選択されています。
- **preJoinAutoAddRoom** - 部屋が近くの場合 [**今すぐ参加**] を選択します。
- **preJoinBack** - [**戻る**] または [**閉じる**] ボタンが選択されました。
- **preJoinDenied** - ユーザーが会議に参加することができません。
- **preJoinDeviceAudio** - ドロップダウンリストから [**デバイスのオーディオで参加する**] が選択されています。
- **preJoinDialIn** - 事前参加ドロップダウンリストにある [**ダイヤルイン**] ボタンが選択されています。
- **preJoinDialInCall** - ユーザーが参加前に [**ダイヤルイン**] のリクエストを確認します。
- **preJoinDialInCancel** - ユーザーが参加前に [**ダイヤルイン**] のリクエストをキャンセルします。
- **preJoinDialOut** - [**もう一度通話する**] ボタンが事前参加ドロップダウンで選択されています。
- **preJoinDialOutCall** - ユーザーが参加前に [**もう一度通話する**] のリクエストを確認します。
- **preJoinDialOutCancel** - ユーザーが参加前に [**もう一度通話する**] のリクエストをキャンセルします。
- **preJoinPSTNOptions** - ユーザーが他の参加オプションのドロップダウンを選択します。
- **priorityChange** - タスク リストの表示中に優先度フィルターが適用されるとトリガーされます。
- **priorityPickerClicked** - ユーザーが [タスク リスト フィルター] 画面から [優先度フィルター ピッカー] に移動するとトリガーされます。
- **privateMeetingJoin** - プライベート会議チャットで　[**会議参加**] ボタンがタップされました。
- **processInBG** - 着信通知をバックグラウンドで処理します (Android)。
- **processInFG** - 着信通知を前景で処理します (Android)。
- **progressItemClicked** - ユーザーがタスクの進行状況ピッカーを正常に開始したことを確認します。
- **promotedToPresenter** - ユーザーが出席者を昇格します - ダイアログ ボックスの [**変更**] ボタン。
- **provideFeedbackDismiss** - ユーザーにアプリが気に入らない理由についてのフィードバックを送信するかどうかを確認するプロンプトを閉じます。
- **provideFeedbackNo** - ユーザーにアプリが気に入らない理由についてのフィードバックを送信するかどうかを確認するプロンプトに [いいえ] と返信します。
- **provideFeedbackYes** - ユーザーにアプリが気に入らない理由についてのフィードバックを送信するかどうかを確認するプロンプトに [はい] と返信します。
- **provideRatingDismiss** - アプリが気に入ったと述べたユーザーに、アプリ ストアで評価を残したいかどうか尋ねるプロンプトを閉じます。
- **provideRatingNo** - アプリが気に入ったと述べたユーザーに、アプリ ストアで評価を残したいかどうか尋ねるプロンプトに対し、[いいえ] と返信します。
- **provideRatingYes** - アプリが気に入ったと述べたユーザーに、アプリ ストアで評価を残したいかどうか尋ねるプロンプトに対し、[はい] と返信します。
- **proximityPermissionDismissed** - アクセス許可のバナーが閉じられました。
- **proximityPermissionGranted** - アップアップでアクセス許可が付与されます。
- **proximityPermissionDismissed** - アクセス許可のバナーがタップされました。
- **pushNotification** - トリガー イベントは次のとおりです。
  - 通知により起動する。
  - プッシュ通知の選択。
  - プッシュ通知の再接続がタップされる。
  - **Reconnect failed** プッシュ通知がタップされる。
- **quickNotificationAction** -ユーザーが通知に対してクイック操作の応答のいずれかの操作を行うとき (プッシュ通知から直接メッセージにいいね! をする機能など)。
- **quickSelectImagePicker** - クイック選択。
- **quickStartLiveEventJoin** - クイック スタート ライブ イベントにユーザーが参加します。
- **quietHoursValues** - [戻る] ボタンのナビゲーションで [通知オフ時間] をキャプチャします。
- **quotedReplySent** - ユーザーがコンテキスト タイプで返信メッセージを送信しました。
- **reactAngry_CM** - コンテキスト メニューから怒りで対応します。
- **reactAngry_HB** - ホバー バブルから怒りで対応します。
- **reactHeart_CM** -コンテキスト メニューからハートで対応します。
- **reactHeart_HB** - ホバー バブルからハートで対応します。
- **reactLaugh_CM** - コンテキスト メニューから笑いで対応します。
- **reactLaugh_HB** - ホバー バブルから笑いで対応します。
- **reactLike_CM** - コンテキスト メニューからいいね! とリアクションをする、またはボット メッセージにいいね! を付けます。
- **reactLike_doubleTap** - ダブル タップでいいね! と対応します。
- **reactLike_HB** - ホバー バブルでいいね! と対応します。
- **reactSad_CM** - コンテキスト メニューから悲しみで対応します。
- **reactSad_HB** - ホバー バブルから悲しみで対応します。
- **reactSurprised_CM** - コンテキスト メニューから驚きで対応します。
- **reactSurprised_HB** - ホバー バブルから驚きで対応します。
- **reactRemoved_HB** - ユーザーが [リアクション サマリー] ページのエクスペリエンスにより、リアクションを削除した場合。
- **readReceipts** - ユーザーが昨日有効化しました。
- **redeemInvite** - アプリ内引き換え。
- **refreshCalendarList** - プル ダウンで予定一覧ビューを更新します。
- **refreshLinksGallery** - ユーザーが下方向にスワイプして、リンク ギャラリーを更新します。
- **removeAssignee** - 担当者が割り当て選択ビューから削除されたことを確認します (割り当て選択ビューの外側にある [**x**] を選択したときにトリガーされる *assignmentRemoved* とは対照)。
- **removeMeeting** - キャンセルされた会議の [会議の詳細] ページで、[**カレンダーから削除**] を選択します。
- **removeParticipantFromEditMeeting** - [会議の詳細] ページから [**会議を編集する**] を選択した後、参加者を削除します。
- **removeParticipantFromNewMeeting** - 新しい会議を設定するときに、スケジューラー ページから参加者を削除します。
- **removeReplyObject** - ユーザーが [作成] から返信オブジェクトを削除しました。
- **removeUser** - 担当者が割り当て選択ビューの内側から削除されたことを確認します (割り当て選択ビューの外側にある [**x**] を選択したときにトリガーされる *assignmentRemoved* とは対照)。
- **removeUser_CM** - ユーザーがチャット参加者リストを介してユーザーを削除した場合。
- **removeUserConfirm** - ユーザーが [ユーザーの削除] ダイアログを確認しました。
- **removeUserContextMenu** - ユーザーがコンテキスト メニューから参加者を削除しました。
- **removeUserSwipe** - ユーザーがスワイプして参加者を削除しました。
- **reorderChannelItem** - ユーザーがピン留めされたチャネルを並べ替えます。
- **reportAbuseConfirmation** - ユーザーが確認画面の [**完了**] ボタンを選択するとき。
- **reportAbuseOpen** [**問題を報告する**］ ボタンがコンテキスト メニューで選択される回数。
- **reportAbuseSend** - ユーザーが [**報告する**] ボタンを選択すると、選択済みレポートの種類がテレメトリに保存されます。
- **replyChain** - [**新しいメッセージe**] ボタン、または返信チェーン (スレッド) を選択しました。
- **replyChannel** - [**返信**] ボタンをチャネルで選択しました。
- **replyNavigation** - 返信オブジェクトが選択されて、参照元投稿に移動します。
- **replySendMessage** - チャネル返信を送信します。
- **replyViaMsgOptions** - コンテキスト メニュー経由でユーザーが返信を開始しました。
- **replyViaSwipe** - ユーザーがスワイプで返信を開始しました。
- **requestActedOn** - マネージャーが空きシフトの要求決定を行うとトリガーされます。
- **requestActionClicked** - シフトの要求が選択されている場合など、ユーザーがアクションを要求した場合 (現場担当マネージャー表示または現場担当者のいずれか)。
- **requestDetailsClicked** - シフトの要求が選択される場合 (現場担当マネージャー表示または現場担当者)。
- **requestJoinTeam** - [**要求**] ボタンが押されました。
- **requestSent** - 送信された要求があったかログします。
- **Requestto結合の** - チームに参加するよう要求します (公開またはプライベート)。
- **requestToJoinTeamError** - 参加要求のエラー。
- **requestTypeClicked** - ユーザーが [要求選択] から選択する要求の種類を決定します。
- **resolveIssue** - 通知のトラブルシューティング ツール ポップアップで [**解決する**] が選択されて、ブロック アプリに移動します。
- **responseClicked** - 応答ページをユーザーが選択します。
- **retryButtonClicked** - [**もう一度試す**] ボタンが選択されています。
- **returnToMessage** - [**戻る**] が選択されてメッセージに移動します。
- **runningLate** - ユーザーが遅れます。
- **safeLink** - 安全に認証されたリンク。
- **saveEditMeeting** - 会議の更新を行った後、 [会議のスケジューラー] ページで [**保存**] ボタンを選択します。
- **saveNewMeeting** - [会議のスケジューラー] ページで [**保存**] ボタンを選択します。 正常に保存された会議と、クライアント側またはサービス エラーのために作成に失敗した会議の割合をログします。
- **savePlanClicked** - [**作成**] がアプリの既定の起動により新しいプラン クリエータで選択されるとトリガーされます。
- **scheduledMeetingJoin** - スケジュール済みの会議オブジェクトから [**会議参加**] ボタンが選択されています。
- **scrollCalendarList** - [カレンダー] でのスクロール測定。
- **scrollDatePicker** - カレンダーの日付選択コントロールをスクロールします。
- **searchAbandoned** - 検索が中止されたかどうかを判断します。
- **searchCancelled** - 以下を判断します。
  - 検索が正常に行われたか、またはユーザーが検索を中止したか。
  - 検索クエリが正常に実行されたか。
- **searchContacts** - 通話リストから検索します。
- **searchIcon** - 以下を判断します。
  - 検索をトリガーできた場合。
  - 検索トリガーのソース。
  - 関連する結果が正常に検出された場合。
- **[searchInitiated**] - 検索をトリガーの可否と検索トリガーのソースを決定します。
- **searchMeetingParticipants** - 参加者を検索してスケジューラー フォーム内に追加します。 作成された予定の数と作成された会議の数を区別します。
- **searchResultsClicked** - 以下を判断します。
  - 関連性がある結果が正常に検出されたかどうか。
  - 検索結果が、個々のドメインとは異なる [すべて] のタブからのものか。
- **searchTab** - 以下を判断します。
  - 検索結果のドメイン情報 - ユーザー、チャット、メッセージ、およびファイル。
  - 検索結果が [すべて] のタブのものか、個々のドメインのものか。
- **searchTabClicked** - 以下を判断します。
  - 検索結果のドメイン情報 - ユーザー、チャット、メッセージ、およびファイル。
  - 関連性がある結果が正常に検出されたかどうか。
- **seeAllMeetingParticipants** - [会議の詳細] ページから [**すべて表示**] を選択するか、すべての参加者を表示します。 カレンダーの会議の詳細が重要な役割を果たすカレンダー フィルター全体に、ユーザーのデータをログします。これにより、ダイヤルインや Teams 会議、出欠確認 などの選択を検証できます。
- **seeMeetingDescription** - [会議の詳細] ページを開くか、[会議の詳細] ページの [会議の説明] で [**さらに表示**] を選択します。 カレンダーの会議の詳細が重要な役割を果たすカレンダー フィルター全体に、データがログされます。これにより、ダイヤルインや Teams 会議、出欠確認 などの選択を検証できます。
- **seeRsvpMeetingOptions** - [出欠確認] ポップアップで [**開催者に通知**] を選択するか、[会議の詳細] ページから [**出欠確認] オプション**] を選択します。
- **selectActivityType** - フィード項目の選択ジェスチャをキャプチャします。
- **selectCalendarDate** - カレンダーの日付選択コントロールで特定の日付を選択します。
- **selectDevice** - ディスプレイ アプリの特定のデバイスを選択します。
- **selectGeneralSetting** - [全般設定] に移動します。
- **selection** - デバイスの連絡先または会社の連絡先が選択されています。
- **selectMeetingChicklet** | 会議。
- **selectMeetingRsvpOption** - [**出欠確認**] ボタンを選択し、オプションを選択します。
- **selectMeetingRsvpOptions** - [**出欠確認**] ボタンを選択し、オプションを選択します。
- **selectPersonalList** - ユーザーが個人タスク リストをタップして正常に移動したことを確認します。
- **selectPlannerList** - ユーザーが共有タスク リストをタップして正常に移動したことを確認します。
- **selectSettingOption** - ハンバーガー メニューから [**設定**] タブに移動します。
- **selectTheme** - ダーク　テーマを有効にします。
- **selectUser** - タスクに担当者が正常に選ばれたことを確認します。
- **selfLongPress** - 自分自身を長押しします。
- **Send_earlycancelledCQF** - ユーザーがフィードバックを CQF の早期にキャンセルされた通話フォームに送信します。
- **send_map_pin_clicked** - ユーザーが静的位置情報を送信します。
- **Send_ratemycallCQF** - ユーザーが CQF の通話の評価フォームにフィードバックを送信します。
- **Send_ratemyliveeventCQF** - ユーザーが CQF のライブ イベント評価フォームにフィードバックを送信します。
- **sendForward** - ユーザーが、転送ピッカーからの転送メッセージ送信を確認します。
- **sendImage** - 画像を送信します。
- **sendLocation** - 送信場所。
- **sendMsg** - 返信で **送信** を選択します。
- **sendRequestBulkClicked** - バルク要求を送信するごとに 1 回ログされます。
- **sendRequestClicked** - [**シフト要求が送信されました**] が選択されています。
- **sendVoiceMessage** - [**レコード**] ボタンがリリースされます。
- **Setting/Dismiss** - デバイスの連絡先設定。
- **settingsNavReadReceiptNotice** -　ユーザーが [機能の通知] から [設定] に移動しました。
- **settingsOpened** - これは、ユーザーのデバイスのタイム ゾーンがチームのタイム ゾーンと一致せず、ユーザーが [設定] に移動するとトリガーされます。
- **shareFile** - [**ファイルの共有**] が選択されるとトリガーされます。 また、以下の確認も手助けします。
  - ユーザーがファイル共有操作を開始できたかどうか。
  - ユーザーがファイルを正常に共有できるかどうか。
- **shareHistory** - 共有履歴ピッカーが選択されています。
- **shareInto** - ユーザーが別のアプリにあるものを Teams に共有します。
- **sharePlanToChat** - 共有リストは、タスク アプリからグループ チャットにチクレットとして手動で共有されます。バックエンド メッセージング サービスを介して送信されるチックレットを確認してください。
- **sharePPTFromChannels** - [**Teams とチャネル**] が選択されています。
- **sharePPTFromOneDrive** - [**OneDrive**] が選択されています。
- **shareRecording** - レコーディングを共有します。
- **shareScreen** - スクリーン共有を開始または停止します。
- **共有シフト** - シフトが共有されているときに提供される情報。
- **shareShiftsClicked** - 空きシフトの詳細。
- **shareTray** - [**共有…**]  がアクション シートで選択されます。
- **shiftAssigneeClicked** - 特定のシフト詳細が表示されているシフト カレンダー ビュー。
- **shiftDetails** - これによりシフトの詳細を表示できます。
- **shiftDetailsCalendar** - ユーザーがシフトの詳細に移動します。
- **shiftDetailsMyShifts** - [**スケジュール**] タブから [**カレンダー**] をタップします。
- **shiftDetailsTodaysCoworkers** - 画面の時計で、[**開始**] または [**休憩終了**] ボタンが選択されています。
- **shortCircuitContactCount** -　連絡先の取得で受け取るアドレス帳に一致するショート サーキットの連絡先の数。
- **showBanner** - **WiFi に接続されていて、インターネット** バナーが表示されない回数。
- **showCard** - カード ボタンをタップします。 カードは主要なプラットフォーム コンストラクトで、その用途とパターンを測定することは、プラットフォームの用途を理解し、クライアント側の潜在的な問題を探し出すのに必要となります。
- **shownReadReceiptNotice** - ユーザーに [設定] オプションのある機能通知が示されます。
- **signIn** - [**サインイン**] がウェルカム ページで選択されている、または[**サインイン**] ボタンがタップされています。
- **signUp** - [**無料アカウントを作成する**] または [**無料でサインアップ**] が選択されています。
- **simultaneousCallForward** - 以下の場合にトリガーされます。
  - 同時通話転送先が設定されている。
  - 同時通話転送が有効になっている ([通話を自分に着信する] が有効になっており、着信も設定されている)。
- **skipVerificationForLink** - ユーザーが確認をスキップしました。
- **SMSSendMessage** - ユーザーが SMS メッセージを送信します。
- **sortChanged** - ユーザーがタスク リストの表示中に並べ替え順序を変更するとトリガーされます。
- **startEditing** - [**編集**] ボタンが選択されています。
- **startPresentPhoto** - 写真の提示を開始します。
- **startPresentVideo** - ビデオの提示を開始します。
- **startPSTNCall** - 以下の理由でトリガーされます。
  - グローバル検索 (ユーザー) の PSTN 結果。
  - PSTN 通話は、デバイスの contactCard から行われます。
  - callList からの PSTN 通話。
  - ダイヤルパッドを使用する DialPSTN。
- **startRecording** - レコーディングを開始します。
- **startVoicemailCall** - [**ボイスメールの案内応答を変更する**] が選択されています。
- **static_place_selected** - ユーザーがマップをドラッグして、静的位置情報を選択します。
- **statusCheckBoxClicked** - タスク アイテムが完了済み、または未完了のときにトリガーされます。
- **statusMsgCancel** - ユーザーがステータス メッセージの変更をキャンセルします。
- **statusMsgExpiry** - ユーザーが有効期限を設定します。
- **statusMsgSet** -　ユーザーが新しいステータス メッセージを設定します。
- **statusPageViaContactCard** - ユーザーが連絡先カードを使用してステータス作成環境を入力します。
- **statusPageViaHamburger** - ユーザーがハンバーガーを使用してステータス作成環境を入力します。
- **stop_location_sharing_logout** - ユーザーがアプリからログアウトします。
- **stopMeetingButton** - ユーザーが会議に許可されない状態でロビーから離れる回数。
- **stopPresentPhoto** - 写真の提示を停止します。
- **stopPresentVideo** - ビデオの提示を停止します。
- **stopRecording** - レコーディングを停止します。
- **structuredMeetingsBannerDismiss** - ユーザーが会議の役割について通知するバナーを閉じます。
- **stuckOnConnectingDialInSelected** - [**ダイヤルイン**] がドロワーで選択されています。
- **OnConnectingDialInSelected** - [**もう一度試す**] がドロワーで選択されています。
- **stuckOnConnectingShownDismissed** - ユーザーがドロワーを終了しました。
- **suggested_place_selected** - ユーザーがおすすめの場所を選択して、静的位置情報を共有します。
- **switchTeamAction** - ユーザーが業務時間記録内にチームを切り替えます。 これは、ユーザーが切り替え先のチームを選択すると始動します。
- **switchTeamsDialogTriggered** - ユーザーが [**シフト**] タブを表示。
- **tabActionCopyLink** - ユーザーがモバイルのタブ コピー リンクを検出して使用する方法。
- **tabActionMoreOptions** - タブ内の省略記号 (**...**) の用途を理解します。
- **tabActionOpenInBrowser** - ブラウザーで開く用途。 これは、ユーザーが Teams 外でタブを開くことを希望するかを理解するために必要となります。
- **tabActionOpenInBrowserFromTab** - 詳細なオプションについてタブ内からブラウザーで開く用途、検出の可能性と用途を理解します。
- **tabActionOpenInTeams** - Open in の用途。 これは、タブが既定で [Teams で開く] に設定できるかどうかを理解する上で重要です。
- **tabActionRemove** - 削除オプションが検出可能である様子と機能の用途を理解します。
- **tabActionRename** - 名前の変更が検出可能である様子および機能の用途を理解します。
- **tabActionSetting, Android - fix** - ユーザーがモバイルでタブ構成を検出して使用する方法。
- **table** - テーブルを選択します。
- **tabListMoreOptions** - タブのその他のオプションの用途を理解します。
- **tabOpen** - タブが正常に開いたか、または、タブが開くのに問題があるかを通知します。
- **tabViewed** - [**チーム シフト ピッカー**] へのエントリについて、送信される要求がスワップである場合にのみログされます。
- **takePhoto** - 写真を撮ります。
- **takePhotoPicker** - [**写真を撮る**] が [画像選択] 内で選択されました。
- **tapChicletExpand** - ユーザーがモバイルでカードをプレビューする方法。
- **tapDatePickerHandle** - カレンダーの日付選択コントロールを展開します。
- **tapSettings** - モバイルでアプリを再構成中のユーザーの数。
- **tasksAppLaunchAdaptiveCard** - タスク アプリがグループ チャットのアダプティブ カードから開きます。IC3 サービスの URL からアプリの起動を確認します。
- **tasksAppLaunchComposeExtension** - タスク アプリがグループチャットの作成拡張機能から開きます。MT サービス を介してアプリの起動を確認します。
- **tasksAppLaunchDashboard** - タスク アプリがダッシュボード タイルまたは特定のプランから開きます。MT サービスを介してアプリの起動を確認します。
- **tasksAppLaunchDashboardSeeAll** - タスク アプリがダッシュボードの [**すべて表示**] ボタンから開きます。MT サービスを介してアプリの起動を確認します。
- **tasksAppLaunchDefault** - タスクアプリにより下部ドロワーが開き、 MT サービスを介してアプリ起動を確認します。
- **tabCalendarClicked** - ユーザーが [チーム選択] からチームを選択しました。
- **teamChannelChanged** - ユーザーがプラン リストからプランを選択して移動するとトリガーされます。 Aria 以外の appInsights にのみ送信されます。
- **teamCreate** - ユーザーが新しいチームを作成するためのオプションを選択します。
- **teamEdit** - ユーザーが、所有または管理しているチームの側面を編集します。
- **teamNav** - チームのメニュー オプションを表示します。
- **teamsDeviceCallResumed** - Bluetooth に接続された周辺機器 (携帯電話ドック) を使用しているユーザーが、保留中の通話を再度有効にします。
- **teamSelectedClicked** - ユーザーが、タイムシートの[**選択済みチーム**] を選択するとき。
- **teamShiftPickerClicked** - ユーザーが新しい休憩エントリを追加したとき。 ユーザーが変更を保存すると、イベントがログされます。
- **tenantSwitch** テナントの切り替えについて。 MTMA の機能の成功指標 (複数のテナントと複数のアカウント) 機能は、予防的に問題を特定して解決し、スムーズな切り替えエクスペリエンスを提供するのに役立ちます。
- **tenantSwitchUnsupportedError** - テナントのサポートされていないエラー (ユーザーがエラーを確認した場合)。 MTMA の機能の成功指標 (複数のテナントと複数のアカウント) は、アカウントまたはテナントの切り替えエラーに関するテレメトリを提供するので、予防的に問題を特定して解決し、スムーズな切り替えエクスペリエンスを提供します。
- **timeClockClicked** - ユーザーが [自分のシフト] タブの [**業務時間記録**] ボタンを選択します。
- **timeOffReasonClicked** - 休暇の理由が引用されているかどうかを判断します。
- **timesheetAddClicked** - ユーザーが休憩の編集にメモを追加したとき。 ユーザーが変更を保存すると、イベントがログされます。
 **timesheetBreakAdded** - 新しい業務時間のエントリを追加します。 変更を保存すると、イベントがログされます。
- **timesheetBreakEdited** - ユーザーがタイムシートを確認したとき。 このイベントは、ユーザーがモーダルで [確認] をクリックするとログされます。
- **timesheetBreakNoteAdded** - ユーザーがタイムシートを削除したとき。 このイベントは、ユーザーがモーダルで削除を確認するとログされます。
- **timesheetClockAdded** - ユーザーがタイムシートの [編集] を選択したとき。
- **timesheetClockEdited** ユーザーが編集したタイムシートで [保存] を選択したとき。
- **timesheetConfirmed** - ユーザーが自分のタイムシート編集にメモを追加したとき。 ユーザーが変更を保存すると、イベントがログされます。
- **timesheetDeleted** - ユーザーがシフト リマインダー設定を行っているかどうか、およびユーザーがアラートを受けるシフトまでの分数。
- **timesheetEditClicked** - ユーザー構成テレメトリ。
- **timesheetEditSaved** - ユーザーがユーザーのプロファイルからタイムシートをタップして、そのユーザーのタイムシートを開きます。
- **timesheetNoteAdded** - 承認済休暇の要求を表示します。
- **タイトル Lechanged** - タスク アイテムのタイトルが変更されると、すべての文字変更でトリガーされます。
- **toast** - アプリ内トーストが選択されています。
- **toggleChannelsInChat** - 機能をオン/オフにします。 一体化されたチャットとチャネル エクスペリエンスのための機能の成功指標。
- **toggleClicked** - トグルが選択されています。
- **transferNow** - 以下の場合にトリガーされます。
  - ユーザーが [**転送**]  >  [**今すぐ転送**] を選択します。
  - 転送先がをユーザーに設定されます。
  - 転送先がを電話番号に設定されます。
- **translateFailed** - 翻訳に失敗しました (オフラインを除く)。 メッセージの翻訳機能についての機能の成功指標。
- **unansweredCallForward** - 不在着信の転送先が設定されます。 不在着信通話の転送も有効になります ([通話を自分に着信する] が有効になっており、[不在着信] が有効な場合)。
- **unblockCaller** - 以下のブロックを解除します。
  - アクション シートの連絡先または番号。
  - 連絡先カードの連絡先または番号。
  - [設定] の数値。
- **unblockChat** - チャット ボットのブロックを解除します。
- **unpinChannel** - チャネルのピン留めを外します。
- **unpinSelf** - アクション シートで自分自身のピン留めを外します。
- **pinUser** - アクションシートでユーザーのピン留めを外します。
- **Unsaf Elink** - リンクが安全でないと判断されました。
- **updatePersonalTask** - 個人タスクが正常に更新されたことを確認します。
- **updatePlaybackSpeedVoicemail** - ボイスメールの再生速度の値が変更されます。
- **updateTask** - 更新タスクの操作の失敗を確認します。
- **updateTaskState** - タスクの状態が更新されたことを確認します。
操作。
- **upgrade** - [**その他**] メニューの [**アップグレード**] ボタンを選択します。
- **uploadFile** - ユーザーが [**デバイスからアップロード**] を選択します。
- **uploadSelectedFile File** - 以下の状況でトリガーされます。
  - チャネルで正常にファイルをアップロードする。
  - チャットで正常にファイルをアップロードする。
  - [返信] ウィンドウでファイルをアップロードする。
  - グループ チャットでファイルを正常にアップロードする。
  - 主要シナリオの用途。
  - チャネルのアップロード シナリオの開始。
  - チャットのアップロード シナリオの開始。
  - チャネルのアップロード シナリオの終了。
  - ファイルを　[**ファイル**] タグに正常にアップロードする。
  - ファイルのアップロード中にプロンプトが実行された場合。
  - 選択したファイルが正常にアップロードされた場合。
- **uploadSelectFile** - ファイルを正常に選択します。[**ファイルのアップロード**] ボタンを正常に選択します。
- **urgentMessageSelect** - 優先度コンテキスト メニューから緊急メッセージを選択します。
- **urgentMessageSend** - 緊急メッセージを送信します。
- **url** - URL。
- **urlPreview** - URL プレビュー。
- **Urlpreview** - URL プレビューの追加。
- **urlPreviewOpen** - URL のプレビューが開いています。
- **Urlpreview** - URL のプレビューが削除されました。
- **userConfiguration** - 保留中の休暇要求を表示します。
- **userJoinedViaShareLink** - ユーザーがリンクから会議に参加した。
- **userLongPress** - 参加者を長押しします。
- **userProfileOpened** - ユーザーが [**ユーザー**] アイコンを選択して、ユーザー プロファイルを開きます。
- userTimesheetOpened** - ユーザーがユーザーのプロファイルからタイムシートを選択して、そのユーザーのタイムシートを開きます。
- **useWifiForAudioDialog** - システムによりプロンプトが表示され、管理者が携帯電話でのオーディオ通話とビデオ通話をブロックする間に、ユーザーが **OK** を選択します。
- **useWifiForVideoDialog** - 以下の場合にトリガーされます。
  - システムによりプロンプトが表示され、管理者が携帯電話でビデオ通話をブロックする間、[**OK**] が選択される。
  - 管理者が携帯電話でビデオをブロックする間、会議でビデオを有効にするよう試す。
  - システムによりプロンプトが表示され、管理者が携帯電話で会議のビデオ通話をブロックする間、[**OK**] が選択される。
- **videoUserDoubleTap** - ビデオ参加者をダブル タップします。
- **viewChannelMembers** - チャネル メンバー リストを表示します。
- **viewContactCard** - 連絡先カードが以下より選択されます。
  - CallHistory アイテム。
  - ボイスメール アイテム。
  - 通話リスト。
- **viewed** - ユーザーがページを表示しました。
- **viewFullAllDayMeetingList** - モバイルの予定一覧ビュー。
- **viewLobbyFromBanner** - ユーザーが通知バナーから [**ロビーの表示**] を選択した回数。
- **viewMeetingDetails** - [会議の詳細] ページで [**...**] メニューを選択します。 モバイル カレンダーの [**その他**] メニューの用途を示します。
- **viewMeetingOccurrence** - 定期的な会議のインスタンスの会議詳細を表示します。 カレンダーの会議の詳細が重要な役割を果たすカレンダーフィルター全体に、ユーザーのデータをログするテレメトリで、ダイヤルインや Teams 会議、出欠確認などの選択を検証できます。
- **viewMeetingSeries** - 以下の状況で、会議系列の正常なレンダリングをログします。
  - インスタンスから [系列会議の詳細] ページに切り替える場合。
  - [会議の詳細] ページから [**系列の表示**] を選択した場合。
- **viewOrgChart** - 組織図の基本的用途テレメトリ。
- **viewRequests** - [**要求の表示**] ボタンが押されています。
- **voiceDataCollectionOptOut** - ユーザーがバナーをクリックして、モバイルからのレコーディングを終了します。
- **voicemail - No AS Assigned** - 発表者がボイス メール アイテムをタップします。
- **whiteboardUsed** - ユーザーがホワイトボードに注釈をつけます (webview のアクション)。
- **wiki - No AS assigned** - Wiki 用途テレメトリ。

### <a name="scenario"></a>シナリオ

> [!NOTE]
> パネルアクション イベントのプロパティに関する情報については、[シナリオ イベントで送信されるプロパティ](#properties-sent-with-scenario-events)を参照してください。

- **create_default_plan_and_nav_to_view** - 既定の共有タスク リストを正常に作成したこと、ユーザーが操作後に結果のビューに到達するまでにかかった時間を確認します。
- **create_personal_plan_and_nav_to_view** - 既定の個人タスク リストを正常に作成したこと、ユーザーが操作後に結果のビューに到達するまでにかかった時間を確認します。
- **create_personal_task** - 正常に個人タスク アイテムの作成が完了したことを確認します。
- **create_planner_plan_and_nav_to_view** - 共有タスク リストを正常に作成したこと、ユーザーが操作後に結果のビューに到達するまでにかかった時間を確認します。
- **create_planner_task** - 共有タスク アイテムの正常な作成を確認します。
- **delete_personal_plan** - 個人タスク リストの正常な削除を確認します。
- **delete_personal_task** - 個人タスク項目の正常な削除を確認します。
- **delete_planner_plan** - 共有タスク リストの正常な削除を確認します。
- **create_planner_task** - 共有タスク アイテムの正常な削除を確認します。
- **get_sender_sub_scenario** - アクティビティの送信者サブシナリオを取得します。
- **load_chat_plans_list** - チャット プラン ビューの Planner プランの正常な取得を確認します。
- **load_home_page** - 主なホーム ビューの個人および共有のタスク リスト両方の正常な取得を確認します。
- **load_personal_task_list** - タスク リスト ビューで個人タスク リストにあるタスクの正常な取得を確認します。
- **load_shared_task_list** - タスク リスト ビューで共有タスク リストにあるタスクの正常な取得を確認します。
- **load_smart_task_list** - タスク リスト ビューでスマート タスク リストにあるタスクの正常な取得を確認します。
- **rename_personal_plan** - 個人タスク リストの名前の変更を確認します。
- **rename_planner_plan** - 共有タスク リストの名前変更が成功したことを確認します。
- **update_planner_task_and_nav_to_view** - 共有タスク アイテムの正常な更新と、ユーザーが操作後に結果のビューに到達するまでにかかった時間を確認します。
- **update_personal_task_and_nav_to_view** - 個人タスク アイテムの正常な更新、および [**Planner タスクと更新**] 後の結果のビューをユーザーが表示するのにかかる時間を確認します。ユーザーが共有タスク リストのタスクを正常に更新したことを確認します。

## <a name="property-lists"></a>プロパティ リスト

### <a name="properties-sent-with-all-events"></a>すべてのイベントで送信されるプロパティ

| プロパティ名                    | 説明                                                          |
|----------------------------------|----------------------------------------------------------------------|
| EventInfo_Time                   | イベント発生時刻                                                |
| EventInfo_Name                   | イベント名 - イベントの種類を区別するために使用します               |
| EventInfo_BaseType/name          | イベントの種類 - イベント内のイベントの種類を区別するために使用します   |
| EventInfo_Source                 | イベント世代のソース                                       |
| AppInfo_Language                 | アプリの言語                                                         |
| AppInfo_ETag                     | ユーザーに割り当てられる試用 ID                                     |
| DeviceInfo_OsBuild               | OS のビルド バージョン                                              |
| UserInfo_Mri                     | ユーザー ID の入力                                                       |
| Session_RunId                    | セッション ID の種類                                                 |
| DeviceInfo_DetailModel           | デバイスのモデル                                                  |
| UserInfo_TimeZone                | ユーザーのタイム ゾーン                                                |
| DeviceInfo_OsName                | デバイス OS 名                                                       |
| DeviceInfo_NetworkProvider       | デバイス ネットワークのプロバイダー                                              |
| DeviceInfo_Model                 | デバイスのモデル                                                         |
| DeviceInfo_NetworkType           | デバイス ネットワークの種類                                                  |
| UserInfo_Language                | ユーザーの言語 - アプリの言語に類似。                              |
| client_ring/UserInfo_Ring        | 早期導入者に機能をリリースするのに役立つユーザー リング           |
| UserInfo_Id                      | ユーザー ID                                                              |
| UserInfo_TenantId                | テナント ID                                                            |
| EventInfo_SdkVersion             | イベントを生成するのに使用される SDK バージョン                               |
| DeviceInfo_Id                    | デバイス OS により提供されるデバイス ID                                      |
| eventpriority                    | イベントの優先度                                                 |
| DeviceInfo_Make                  | デバイスの製造元。                                                  |
| AppInfo_Version                  | アプリのバージョン                                                   |
| DeviceInfo_OsVersion             | デバイス OS バージョン                                                    |
| Session_Id/SessionId             | 要求のセッション ID                                            |
| Session_Environment              | セッション環境                                                  |
| isNetworkIssue                   | 要求の提供中にネットワークの問題が発生した場合、情報をキャプチャします。 |
| UserRole                         | テナントでのユーザー ロール                                                |
| Tenant_Model                     | アカウントがフリーミアムまたはエンタープライズ アカウントであるかをキャプチャします。          |
| licenseType/UserInfo_LicenseType | ユーザーに割り当てられているライセンスの種類                                    |
| UserLocale                       | アプリにアクセスのあるロケール                                 |
| Intune_sdkVersion                | Intune SDK のバージョン                                            |
| Intune_sdkBundleVersion          | Intune SDK のバージョン詳細                                   |
| AppInfo_Environment              | アプリにアクセスのある環境                          |

### <a name="properties-sent-with-panelaction-events"></a>パネル アクションのイベントで送信されるプロパティ

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
| Module_Summary        | ユーザー アクションをホースしたモジュールのまとめ                      |
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

### <a name="properties-sent-with-panelview-events"></a>UserBI panelview イベントで送信されるプロパティ

| Panel_Uri          | ユーザーに配信されるパネルの URI                   |
|--------------------|----------------------------------------------------------|
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

### <a name="properties-sent-with-scenario-events"></a>シナリオ イベントで送信されるプロパティ

| プロパティ名        | 説明 |
|----------------------|-------------|
| Scenario_Status      | シナリオの状態 - 破棄する/OK/エラー |
| Scenario_Step        | シナリオにエラーのポイントが異なる複数のステップが含まれる場合、このプロパティはステップに関する詳細をキャプチャします |
| Scenario_StatusCode  | プロパティがシナリオの成功またはエラーに基づいて、シナリオの状態コードを記録します |

### <a name="properties-sent-with-trace-events"></a>追跡イベントと共に送信されるプロパティ

| プロパティ名 | 説明                                                                                    |
|---------------|------------------------------------------------------------------------------------------------|
| Trace_message | エラーが発生した理由についてのエラー文字列と詳細情報が含まれています |
