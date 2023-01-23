---
title: Microsoft Teams でイベントの監査ログを検索する
description: Microsoft Purview コンプライアンス ポータルの監査ログから Microsoft Teams データを取得する方法について説明します。
author: robmazz
ms.author: robmazz
manager: laurawi
ms.topic: article
audience: admin
ms.service: msteams
ms.collection:
- tier1
- purview-compliance
- M365-collaboration
- audit
f1.keywords:
- NOCSH
ms.reviewer: anwara
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: f7219ee11f6818890b8be34f42f76dfa26ef0d12
ms.sourcegitcommit: 5e0900ed7a21ed4e854cc00dbfb4ae4ff2372262
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2023
ms.locfileid: "69950444"
---
# <a name="search-the-audit-log-for-events-in-microsoft-teams"></a>Microsoft Teams でイベントの監査ログを検索する

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

監査ログは Microsoft 365 の複数のサービスにわたって特定のアクティビティを調査するのに役立ちます。 Microsoft Teams の場合は、次のいくつかのアクティビティが監査対象になります。

- チームの作成
- チームの削除
- 追加されたチャネル
- チャネルの削除
- チャンネル設定の変更

監査対象となる Teams アクティビティの完全な一覧については、「[Teams アクティビティ](#teams-activities)」および「[Teams アクティビティでのシフト](#shifts-in-teams-activities)」を参照してください。

> [!NOTE]
> プライベート チャネルからの監査イベントも、チームや標準チャネルの場合と同様に記録されます。

## <a name="turn-on-auditing-in-teams"></a>Teams で監査をオンにする

監査データを確認するには、まず、Microsoft Purview コンプライアンス ポータルで監査を有効にする必要があります。 詳細については、「[監査のオンとオフを切り替える](/microsoft-365/compliance/turn-audit-log-search-on-or-off)」を参照してください。

> [!IMPORTANT]
> 利用できる監査データは、監査を有効にした時点以降のデータのみです。

## <a name="retrieve-teams-data-from-the-audit-log"></a>監査ログから Teams データを取得する

1. Teams アクティビティの監査ログを取得するには、<https://compliance.microsoft.com> に移動し、**[監査]** を選択します。

2. **[検索]** ページで、監査するアクティビティ、日付、ユーザーをフィルター処理します。

3. さらに詳しく分析するために、結果を Excel にエクスポートします。

詳しい手順については、「[コンプライアンス センターでの監査ログの検索](/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance#search-the-audit-log)」を参照してください。

> [!IMPORTANT]
> 監査データは、監査がオンになっている場合に、監査ログでのみ見ることができます。

The length of time that an audit record is retained and searchable in the audit log depends on your Microsoft 365 or Office 365 subscription, and specifically the type of license that's assigned to users. To learn more, see the [Security & Compliance Center service description](/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center).

## <a name="tips-for-searching-the-audit-log"></a>監査ログを検索するためのヒント

ここでは、監査ログで Teams アクティビティを検索するためのヒントをご紹介します。

:::image type="content" alt-text="コンプライアンス センターの監査ログの検索ページを示すスクリーンショット" source="media/audit-log-search-page.png" lightbox="media/audit-log-search-page.png":::

- 検索する特定のアクティビティを選択するには、1 つまたは複数のアクティビティの横にあるチェックボックスをクリックします。 アクティビティが選択されている場合は、そのアクティビティをクリックして、選択を取り消すことができます。 また、検索ボックスを使用して、入力したキーワードを含むアクティビティを表示することもできます。

  ![監査ログの検索ページのアクティビティ ドロップダウン リストを示すスクリーンショット](media/audit-log-search.png)

- cmdlets を使用して実行したアクティビティのイベントを表示するには、**[アクティビティ]** リストの **[すべてのアクティビティの結果を表示]** を選択します。 これらのアクティビティの操作の名前がわかっている場合は、検索ボックスに入力してアクティビティを表示し、選択します。

- 現在の検索条件をクリアするには、**[すべてクリア]** をクリックします。 日付の範囲が、過去 7 日間の既定値に戻ります。

- 5,000 件の結果が見つかった場合、検索条件に一致するイベントが 5,000 件を超えていると見なすことができます。 検索条件を絞り込み、返される結果が少なくなるように検索を再実行するか、**[エクスポート]** > **[すべての結果をダウンロード]** を選択して、すべての検索結果をエクスポートできます。 監査ログをエクスポートする手順の詳細については、「[検索結果をファイルにエクスポートする](/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance#step-3-export-the-search-results-to-a-file)」を参照してください。

Check out [this video](https://www.youtube.com/embed/UBxaRySAxyE) for using audio log search. Join Ansuman Acharya, a program manager for Teams, as he demonstrates how to do an audit log search for Teams.

## <a name="teams-activities"></a>Teams アクティビティ

ここでは、Microsoft 365 の監査ログで Teams のユーザーと管理者のアクティビティのために記録されるすべてのイベントの一覧を紹介します。 表には、**[アクティビティ]** 列に表示されるフレンドリ名と、監査レコードの詳細情報および検索結果をエクスポートするときに CSV ファイルに表示される対応する操作名が含まれています。

|**フレンドリ名**|**操作​​**|**説明**|
|:----------------|:------------|:--------------|
|チームへのボットの追加|BotAddedToTeam|ユーザーがチームにボットを追加しました。|
|チャネルの追加|ChannelAdded|ユーザーがチームにチャネルを追加しました。|
|コネクタの追加|ConnectorAdded|ユーザーがチャネルにコネクタを追加しました。|
|Teams 会議に関する詳細を追加しました <sup>2</sup>|MeetingDetail|Teams では、監査ログには、開始時刻、終了時刻、会議に参加するための URL など、会議に関する情報を追加しました。|
|会議の参加者に関する情報が追加されました <sup>2</sup>|MeetingParticipantDetail|Teams では、各参加者のユーザー ID、参加者が会議に参加した時間、参加者が会議を離れた時間など、会議の参加者に関する情報を追加しました。|
|メンバーの追加|MemberAdded|チームの所有者が、チーム、チャネル、またはグループ チャットにメンバーを追加しました。|
|タブの追加|TabAdded|ユーザーがチャネルにタブを追加しました。|
| 適用された秘密度ラベル | SensitivityLabelApplied | ユーザーまたは会議の開催者は、Teams 会議に秘密度ラベルを適用しました。 |
|チャンネル設定の変更|ChannelSettingChanged|次のアクティビティがチーム メンバーにより実行されると、ChannelSettingChanged 操作が記録されます。 これらの各アクティビティについては、変更された設定 (かっこ内) の説明が、監査ログの検索結果の **[項目]** 列に表示されます。 <ul><li>チーム チャネルの名前が変更されます (**チャネル名**)</li><li>チーム チャネルの説明が変更されます (**チャネルの説明**)</li> </ul>|
|組織の設定の変更|TeamsTenantSettingChanged|TeamsTenantSettingChanged は、全体管理者が Microsoft 365 管理センターを使用して次のアクティビティを実行したときに記録されます。 これらの活動は、組織全体の Teams 設定に影響を与えます。 詳細については、「[組織の Teams 設定を管理する](enable-features-office-365.md)」を参照してください。 <br>これらの各アクティビティについては、変更された設定 (かっこ内) の説明が、監査ログの検索結果の **[項目]** 列に表示されます。<ul><li>組織に対して Teams が有効または無効になります (**Microsoft Teams**)。</li><li>組織に対して Microsoft Teams と Skype for Business の相互運用が有効または無効になります (**Skype for Business の相互運用性**)。</li><li>Microsoft Teams クライアント内の組織図ビューが有効または無効になります (**組織図**)。</li><li>チーム メンバーによるプライベート会議のスケジュール機能を有効または無効にします (**プライベート会議のスケジュール**)。</li><li>チーム メンバーによるチャネル会議のスケジュール機能を有効または無効にします (**チャネル会議のスケジュール**)。</li><li>チーム会議でのビデオ通話を有効または無効にします (**Skype 会議のビデオ**)。</li><li>組織に対して Microsoft Teams 会合での画面共有が有効または無効になります (**Skype 会議向け画面共有**)。</li><li>Teams の会話にアニメーション画像 (Giphy と呼ばれる) を追加する機能が有効または無効になります (**アニメーション画像**)。</li><li>組織のコンテンツの規制設定を変更します (**コンテンツの規制**)。 コンテンツの評価により、会話に表示されるアニメーション画像の種類が制限されます。</li><li>チーム メンバーがカスタマイズ可能な画像 (カスタム ミームと呼ばれる) をインターネットからチームの会話に追加する機能が、有効または無効になります (**インターネットからのカスタマイズ可能な画像**)。</li><li>チーム メンバーが編集可能な画像 (ステッカーと呼ばれる) をチームの会話に追加する機能が、有効または無効になります (**インターネットからのカスタマイズ可能な画像**)。</li><li>チーム メンバーが Microsoft Teams のチャットおよびチャネルでボットを使用する機能が、有効または無効になります (**組織全体にわたるボット**)。</li><li>Enables specific bots for Microsoft Teams. This doesn't include the T-Bot, which is Teams help bot that's available when bots are enabled for the organization (**Individual bots**).</li><li>チーム メンバーが拡張機能またはタブを追加する機能を有効または無効にします (**拡張機能またはタブ**)。</li><li>Microsoft Teams に対して専用ボットのサイドローディングが有効または無効になります (**ボットのサイドローディング**)。</li><li>ユーザーがメール メッセージを Microsoft Teams に送信する機能が、有効または無効になります (**チャネルのメール**)。</li></ul>|
|メンバーの役割の変更|MemberRoleChanged|チーム所有者がチームのメンバーの役割を変更します。 次の値は、ユーザーに割り当てられる役割の種類を示します。 <br><br>**1** - メンバー ロールを意味します。<br>**2** - 所有者ロールを示します。<br>**3** - ゲスト ロールを意味します。<br><br>メンバー プロパティには、組織の名前とメンバーのメール アドレスも含まれます。|
|チーム設定の変更|TeamSettingChanged|次のアクティビティがチームの所有者により実行されると、TeamSettingChanged 操作が記録されます。 これらの各アクティビティについては、変更された設定 (かっこ内) の説明が、監査ログの検索結果の **[項目]** 列に表示されます。<ul><li>チームのアクセスの種類を変更します。 チームは非公開または公開として設定できます (**チームのアクセスの種類**)。 チームが非公開 (既定の設定) の場合、ユーザーはチームには招待状でのみアクセスでき暗ます。 チームが公開されている場合、誰でもチームにアクセスできます。</li><li>チームの情報の分類を変更します (**チーム分類**)。 たとえば、チームのデータは業務への影響が大きい、業務への影響が中程度、業務への影響が小さい、といったように分類できます。</li><li>チームの名前を変更します (**チーム名**)。</li><li>チームの説明を変更します (**チームの説明**)。</li><li>Changes made to team settings. To access these settings,  a team owner can right-click a team, select **Manage team**, and then click the **Settings** tab. For these activities, the name of the setting that was changed is displayed in the **Item** column in the audit log search results.</li></ul>|
| 秘密度ラベルを変更しました | SensitivityLabelChanged | ユーザーが Teams 会議で秘密度ラベルを変更しました。 |
|チャットを作成しました <sup>1、</sup><sup>2</sup>|ChatCreated|Teams チャットが作成されました。|
|チームの作成|TeamCreated|ユーザーがチームを作成しました。|
|メッセージを削除しました|MessageDeleted|チャットまたはチャネルのメッセージが削除されました。|
|すべての組織のアプリが削除されました|DeletedAllOrganizationApps|カタログからすべての組織アプリを削除しました。|
|削除されたアプリ|AppDeletedFromCatalog|カタログからアプリが削除されました。|
|チャネルの削除|ChannelDeleted|ユーザーがチームからチャネルを削除しました。|
|チームの削除|TeamDeleted|チーム所有者がチームを削除しました。|
|Teams 内の URL リンクを含むメッセージを編集しました|MessageEditedHasLink|ユーザーがメッセージを編集し、 Teams 内でそのメッセージへの URL リンクを追加します。|
|メッセージをエクスポートしました <sup>1、</sup><sup>2</sup>|MessagesExported|チャットまたはチャネル メッセージがエクスポートされた。|
|共有チャネルへの招待を検証できませんでした<sup>3</sup>|FailedValidation|ユーザーが共有チャネルへの招待に応答しますが、招待の検証に失敗しました。|
|チャットを取得しました <sup>1、</sup><sup>2</sup>|ChatRetrieved|Microsoft Teams チャットを取得しました。|
|メッセージのホストされているすべてのコンテンツを取得しました<sup>1、</sup><sup>2</sup>|MessageHostedContentsListed|画像やコード スニペットなど、メッセージにホストされているすべてのコンテンツを取得しました。|
|インストールされたアプリ|AppInstalled|アプリがインストールされました。|
|カードに対して実行されたアクション|PerformedCardAction|ユーザーがチャット内のアダプティブ カードでアクションを起こしました。 アダプティブ カードは通常ボットで使用し、チャットで情報を豊富に表示して、相互作用することを可能にします。 <br/><br/>**注:** チャット内のアダプティブ カードでのインライン入力アクションだけが監査ログで利用可能になります。 たとえば、チャネルでの会話の中で、ユーザーがポーリング ボットによって生成されたアダプティブ カード上でポーリング応答を送信した場合。 ダイアログを開く「結果を表示」などのユーザー アクションや、ダイアログ内のユーザー アクションは、監査ログには表示されません。|
|新しいメッセージを投稿しました <sup>1、</sup><sup>2</sup>|MessageSent|新しいメッセージがチャットまたはチャネルに投稿されました。|
|公開済みのアプリ|AppPublishedToCatalog|アプリがカタログに追加されました。|
|メッセージを表示する <sup>1、</sup><sup>2</sup>|MessageRead|チャットまたはチャネルのメッセージを取得しました。|
|メッセージのホストされているコンテンツを読む <sup>1、</sup><sup>2</sup>|MessageHostedContentRead|画像やコード スニペットなど、メッセージにホストされているコンテンツを取得しました。|
|チームからのボットの削除|BotRemovedFromTeam|ユーザーがチームからボットを削除しました。|
|コネクタの削除|ConnectorRemoved|ユーザーがチャネルからコネクタを削除しました。|
|メンバーの削除|MemberRemoved|チームの所有者が、チーム、チャネル、またはグループ チャットからメンバーを削除しました。|
| 秘密度ラベルを削除しました | SensitivityLabelRemoved | ユーザーが Teams 会議から秘密度ラベルを削除しました。 |
|チーム チャネルの共有を削除しました<sup>3</sup>|TerminatedSharing|チームまたはチャネルの所有者が共有チャネルの共有を無効にしました。|
|チーム チャネルの共有を復元しました<sup>3</sup>|SharingRestored|チームまたはチャネルの所有者が共有チャネルの共有を再び有効にしました。|
|タブの削除|TabRemoved|ユーザーがチャネルからタブを削除しました。|
|共有チャネルの招待に応答しました<sup>3</sup>|InviteeResponded|ユーザーが共有チャネルの招待に応答しました。|
|共有チャネルへの招待者の応答に応答しました<sup>3</sup>|ChannelOwnerResponded|チャネルの所有者が共有チャネルの招待に応答したユーザーからの応答に応答しました。|
|メッセージを取得しました <sup>1、</sup><sup>2</sup>|MessagesListed|チャットまたはチャネルからのメッセージが取得されました。|
|Teams 内の URL リンクを含むメッセージを送信しました|MessageCreatedHasLink|ユーザーがTeams 内の URL リンクを含むメッセージを送信します。|
|メッセージ作成のために変更通知を送信しました <sup>1、</sup><sup>2</sup>|MessageCreatedNotification|サブスクライブしているリスナー アプリケーションに、新しいメッセージを通知する変更通知が送信されました。|
|メッセージ削除の変更通知を送信しました <sup>1、</sup><sup>2</sup>|MessageDeletedNotification|サブスクライブしているリスナー アプリケーションに、メッセージが削除されたことを通知する変更通知が送信されました。|
|メッセージ更新の変更通知を送信しました <sup>1、</sup><sup>2</sup>|MessageUpdatedNotification|サブスクライブしているリスナー アプリケーションに、メッセージが更新されたことを通知する変更通知が送信されました。|
|共有チャネルの招待を送信しました<sup>3</sup>|InviteSent|A channel owner or member sends an invitation to a shared channel. Invitations to shared channels can be sent to people outside of your organization if the channel policy is configured to share the channel with external users.|
|メッセージの変更通知が登録されました <sup>1、</sup><sup>2</sup>|SubscribedToMessages|メッセージの変更通知を受け取るためのサブスクリプションがリスナー アプリケーションによって作成されました。|
|削除されたアプリ|AppUninstalled|アプリがアンインストールされました。|
|更新されたアプリ|AppUpdatedInCatalog|アプリがカタログで更新されました。|
|チャットを更新しました <sup>1、</sup><sup>2</sup>|ChatUpdated|Teams チャットが更新されました。|
|メッセージを更新しました <sup>1、</sup><sup>2</sup>|MessageUpdated|チャットまたはチャネルのメッセージが更新されました。|
|コネクタの更新|ConnectorUpdated|ユーザーがチャネルのコネクタを変更しました。|
|タブの更新|TabUpdated|ユーザーがチャネルのタブを変更しました。|
|アップグレードされたアプリ|AppUpgraded|アプリがカタログで最新版にアップグレードされました。|
|Teams へのユーザーのサインイン|TeamsSessionStarted|ユーザーが Microsoft Teams クライアントにサインインしました。 このイベントは、トークン更新アクティビティをキャプチャしません。|

> [!NOTE]
> <sup>1</sup> このイベントの監査レコードは、Microsoft Graph API の呼び出しによって操作が実行された場合にのみログに記録されます。 操作が Teams クライアントで実行された場合、監査レコードはログに記録されません<br/><sup>2</sup> このイベントは監査 (Premium) でのみ使用できます。 つまり、これらのイベントが監査ログに記録される前に、ユーザーに適切なライセンスを割り当てる必要があります。 監査 (Premium) でのみ使用できるアクティビティの詳細については、「 [Microsoft Purview の監査 (Premium)」](/microsoft-365/compliance/advanced-audit#advanced-audit-events)を参照してください。 監査 (Premium) ライセンス要件については、「 [Microsoft 365 の監査ソリューション](/microsoft-365/compliance/auditing-solutions-overview#licensing-requirements)」を参照してください。 <br/> <sup>3</sup> このイベントはパブリック プレビュー中です。

## <a name="shifts-in-teams-activities"></a>Teams アクティビティにサインイン

**(プレビュー段階)**

組織で Teams の Shifts アプリを使用している場合は、Shifts アプリに関連するアクティビティの監査ログを検索できます。 ここでは、Microsoft 365 の監査ログで Teams の Shifts アクティビティのために記録されるすべてのイベントの一覧を紹介します。

|フレンドリ名|操作​​|説明|
|---|---|---|
|追加済みのスケジューリング グループ|ScheduleGroupAdded|ユーザーが新しいスケジューリング グループをスケジュールに追加することに成功しました。|
|編集済みのスケジューリング グループ|ScheduleGroupEdited|ユーザーがスケジューリング グループの編集に成功しました。|
|削除済みのスケジューリング グループ|ScheduleGroupDeleted|ユーザーがスケジューリング グループをスケジュールから削除することに成功しました。|
|スケジュールの撤回|ScheduleWithdrawn|ユーザーが公開されたスケジュールの撤回に成功しました。|
|追加済みのシフト|ShiftAdded|ユーザーがシフトの追加に成功しました。|
|編集済みのシフト|ShiftEdited|ユーザーがシフトの編集に成功しました。|
|削除済みのシフト|ShiftDeleted|ユーザーがシフトの削除に成功しました。|
|追加済みの休暇|TimeOffAdded|ユーザーがスケジュールに休暇を追加することに成功しました。|
|編集済みの休暇|TimeOffEdited|ユーザーが休暇の編集に成功しました。|
|削除済みの休暇|TimeOffDeleted|ユーザーが休暇の削除に成功しました。|
|追加済みの空きシフト|OpenShiftAdded|ユーザーが空きシフトをスケジューリング グループに追加することに成功しました。|
|編集済みの空きシフト|OpenShiftEdited|ユーザーがスケジューリング グループの空きシフトを編集することに成功しました。|
|削除済みの空きシフト|OpenShiftDeleted|ユーザーがスケジューリング グループから空きシフトを削除することに成功しました。|
|共有済みのスケジュール|ScheduleShared|ユーザーが期間中のチーム スケジュールを共有することに成功しました。|
|業務時間記録を使用して出勤済み|ClockedIn|ユーザーが業務時間記録を使用して出勤することに成功しました。|
|業務時間記録を使用して退勤済み|ClockedOut|ユーザーが業務時間記録を使用して退勤することに成功しました。|
|業務時間記録を使用して開始済みの休憩|BreakStarted|ユーザーがアクティブな業務時間記録セッション中の休憩の開始に成功しました。|
|業務時間記録を使用して終了した休憩|BreakEnded|ユーザーがアクティブな業務時間記録セッション中の休憩の終了に成功しました。|
|追加済みの業務時間記録エントリ|TimeClockEntryAdded|ユーザーがタイムシートに手動で業務時間記録エントリを追加することに成功しました。|
|編集済みの業務時間記録エントリ|TimeClockEntryEdited|ユーザーがタイムシートの業務時間記録エントリを編集することに成功しました。|
|削除済みの業務時間記録エントリ|TimeClockEntryDeleted|ユーザーがタイムシートの業務時間記録エントリを削除することに成功しました。|
|追加済みのシフト要求|RequestAdded|ユーザーがシフト要求を追加しました。|
|シフト要求に応答済み|RequestRespondedTo|ユーザーがシフト要求に応答しました。|
|キャンセルされたシフト要求|RequestCancelled|ユーザーがシフト要求をキャンセルしました。|
|変更されたスケジュール設定|ScheduleSettingChanged|ユーザーがシフト設定で設定を変更しました。|
|追加済みの従業員の統合|WorkforceIntegrationAdded|シフト アプリは、サードパーティのシステムと統合されています。|
|承諾済みのシフト外メッセージ|OffShiftDialogAccepted|ユーザーは、シフト時間後に Teams にアクセスするためのシフト外メッセージを承認します。|

## <a name="office-365-management-activity-api"></a>Office 365 マネージメント アクティビティ API

Office 365 マネージメント アクティビティ API を使用して、Teams のイベント情報を取得することができます。 マネージメント アクティビティ API の詳細については、「[Teams スキーマ](/office/office-365-management-api/office-365-management-activity-api-schema#microsoft-teams-schema)」を参照してください。

## <a name="attribution-in-teams-audit-logs"></a>Teams の監査ログでの属性

Membership changes to Teams (such as users added or deleted) made through Azure Active Directory (Azure AD), Microsoft 365 admin portal, or Microsoft 365 Groups Graph API will appear in Teams audit messages and in the General channel with an attribution to an existing owner of the team, and not to the actual initiator of the action. In these scenarios, consult Azure AD or [Microsoft 365 Group audit logs](/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance) to see the relevant information.

## <a name="use-defender-for-cloud-apps-to-set-activity-policies"></a>Defender for Cloud Apps を使用してアクティビティ ポリシーを設定する

[Microsoft Defender for Cloud Apps](/cloud-app-security/what-is-cloud-app-security) の統合を使用し、[アクティビティ ポリシー](/cloud-app-security/user-activity-policies)を設定して、アプリ プロバイダーの API を使用した幅広い自動処理を適用することができます。 これらのポリシーにより、さまざまなユーザーが行う特定のアクティビティを監視したり、予想外に高率で発生する特定のタイプのアクティビティをフォローしたりすることができます。

アクティビティ検出ポリシーを設定すると、アラートの生成を開始します。 アラートは、ポリシーを作成した後に発生したアクティビティに対してのみ生成されます。 ここでは、Defender for Cloud Apps でアクティビティ ポリシーを使用して Teams アクティビティを監視する方法について、いくつかのシナリオ例を紹介します。

### <a name="external-user-scenario"></a>外部ユーザーのシナリオ

ビジネスの観点から注意したいシナリオの一つに、Teams 環境に外部ユーザーを追加することがあります。 外部ユーザーが有効になっている場合は、そのプレゼンスを監視することをお勧めします。  [Defender for Cloud Apps](/cloud-app-security/what-is-cloud-app-security) を使用して、脅威の可能性を特定することができます。

:::image type="content" alt-text="外部ユーザーの追加を監視するポリシー。" source="media/TeamsExternalUserAddPolicy.png" lightbox="media/TeamsExternalUserAddPolicy.png":::

外部ユーザーの追加を監視するこのポリシーのスクリーンショットでは、ポリシーに名前を付け、ビジネスの必要に応じて重大度を設定し、(この場合は) 単一のアクティビティとして設定した上で、内部ユーザー以外の追加のみを具体的に監視するパラメーターを設定し、このアクティビティを Teams に限定することができます。

本ポリシーの結果は、次の活動ログで確認することができます。

:::image type="content" alt-text="外部ユーザー ポリシーによってトリガーされるイベント。" source="media/TeamsExternalUserList.png" lightbox="media/TeamsExternalUserList.png":::

ここでは、設定したポリシーとの一致を確認し、必要に応じて調整を行ったり、結果をエクスポートして他の場所で使用することができます。

### <a name="mass-delete-scenario"></a>大量削除のシナリオ

前述したように、削除シナリオを監視することができます。 Teams サイトの大量削除を監視するポリシーを作成することができます。 この例では、30 分間隔でチームの大量削除を検知するアラートベースのポリシーを設定しています。

:::image type="content" alt-text="大量のチーム削除を検出するためのポリシーの設定を示すポリシー" source="media/TeamsMassDeletePolicy.png" lightbox="media/TeamsMassDeletePolicy.png":::

スクリーンショットが示すように、このポリシーには、重大度、単一または繰り返されたアクション、Teams とサイトの削除に限定するパラメーターなど、さまざまなパラメーターを設定して Teams の削除を監視することができます。 これは、テンプレートとは別に行うこともできますし、組織の必要に応じて、このポリシーのベースとなるテンプレートを作成させることもできます。

ビジネスに有効なポリシーを設定した後は、イベントがトリガーされるとアクティビティ ログの結果を確認することができます。

:::image type="content" alt-text="大量削除によって引き起こされるイベントのスクリーンショット" source="media/TeamsMassDeleteList.png" lightbox="media/TeamsMassDeleteList.png":::

You can filter down to the policy you've set to see the results of that policy. If the results you're getting in the activity log are not satisfactory (maybe you're seeing lots of results, or nothing at all), this may help you to fine-tune the query to make it more relevant to what you need it to do.

### <a name="alert-and-governance-scenario"></a>アラートとガバナンスのシナリオ

アクティビティ ポリシーがトリガーされた場合にアラートを設定し、管理者や他のユーザーにメール送信することができます。 ユーザーの保留や、ユーザーに再度サインインさせるなどの自動化されたガバナンス アクションを自動で設定することができます。 この例では、アクティビティ ポリシーがトリガーされ、ユーザーが 30 分間で 2 つ以上のチームを削除したと判断した場合に、ユーザー アカウントを一時停止する方法を示しています。

![アクティビティ ポリシーのアラートとガバナンス アクションのスクリーンショット。](media/audit-log-governance.png)

## <a name="use-defender-for-cloud-apps-to-set-anomaly-detection-policies"></a>Defender for Cloud Apps を使用して異常検出ポリシーを設定する

Defender for Cloud Apps の[異常検出ポリシー](/cloud-app-security/anomaly-detection-policy)では、ユーザー/エンティティ行動分析 (UEBA) と機械学習 (ML) をすぐに利用できるので、クラウド環境全体で高度な脅威検出をすぐに実行することができます。 新しい異常検出ポリシーは自動的に有効化されているため、ユーザーやネットワークに接続されているマシンやデバイス全体の多数の動作異常をターゲットにして即時検出を行い、すぐに結果を出すことができます。 さらに、新しいポリシーでは、Defender for Cloud Apps の検出エンジンからより多くのデータが公開され、調査手順を加速して進行中の脅威の抑制に役立ちます。

We're working to integrate Teams events into anomaly detection policies. For now, you can set up anomaly detection policies for other Office products and take action items on users who match those policies.

## <a name="related-topics"></a>関連項目

- [Microsoft Purview コンプライアンス ポータルで監査ログを検索します](/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance)
