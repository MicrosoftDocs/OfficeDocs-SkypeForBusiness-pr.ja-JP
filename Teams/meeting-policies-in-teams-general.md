---
title: 一般的な会議ポリシーを管理する
ms.author: mabond
author: mkbond007
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: sonua, shalenc
audience: admin
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.meetingpolicies.general
- seo-marvel-apr2020
description: Teams で一般的な会議ポリシー設定を管理する方法について説明します。
ms.openlocfilehash: ba667e5fbbe4d0f5e4d1ece6dba5943691b572a6
ms.sourcegitcommit: 507e186972bcbc56c1547a1b9f357bfd38170b5a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/27/2022
ms.locfileid: "68046727"
---
# <a name="meeting-policy-settings---general"></a>会議ポリシーの設定 - 全般

<a name="bkgeneral"> </a>

この記事では、Teams 会議での次の一般的なポリシー設定について説明します。

- [チャネルでの "今すぐ会議"](#meet-now-in-channels)
- [Outlook アドイン](#outlook-add-in)
- [チャネル会議のスケジュール設定](#channel-meeting-scheduling)
- [プライベート会議のスケジュール設定](#private-meeting-scheduling)
- [プライベート会議での "今すぐ会議"](#meet-now-in-private-meetings)
- [指定された発表者の役割モード](#designated-presenter-role-mode)
- [エンゲージメント レポート](#engagement-report)
- [会議の登録](#meeting-registration)
- [登録できるユーザー](#who-can-register)
- [アイランド モードの会議プロバイダー](#meeting-provider-for-islands-mode)
- [スピーチ コーチ](#speaker-coach)

## <a name="meet-now-in-channels"></a>チャネルでの "今すぐ会議"

これはユーザーごとのポリシーであり、会議が始まる前に適用されます。 この設定は、ユーザーが Teams チャネルでアドホック会議を開始できるかどうかを制御します。 これを有効にすると、ユーザーは **[会議]** ボタンをクリックしてアドホック会議を開始したり、チャネルでの会議をスケジュール設定したりできます。 既定値は True です。

[ ![メッセージの下の [今すぐ会議] アイコンを示すスクリーンショット。](media/meeting-policies-meet-now.png) ](media/meeting-policies-meet-now.png#lightbox)

## <a name="outlook-add-in"></a>Outlook アドイン

これはユーザーごとのポリシーであり、会議が始まる前に適用されます。 この設定は、Outlook (Windows、Mac、Web、およびモバイル) 内から Teams 会議をスケジュールできるかどうかを制御します。

![新しい会議をスケジュールする機能が表示されたスクリーンショット。](media/meeting-policies-outlook-add-in.png)

これをオフにすると、ユーザーは Outlook で新しい会議を作成するときに Teams 会議をスケジュールできなくなります。 たとえば、Windows 上の Outlook では、[**新しい Teams 会議**] オプションはリボンに表示されません。

## <a name="channel-meeting-scheduling"></a>チャネル会議のスケジュール設定

既存の[AllowChannelMeetingScheduling] ポリシーを使用して、チームのチャネルの予定表で作成できるイベントの種類を制御します。 これはユーザーごとのポリシーであり、会議が始まる前に適用されます。 この設定は、ユーザーが Teams チャネルで会議をスケジュールできるかどうかを制御します。 既定では、この設定は[オン] に設定されています。

このポリシーが無効になっていると、ユーザーは新しいチャネル会議を作成できなくなります。 ただし、既存のチャネル会議は、イベントの開催者が編集できます。

会議のスケジュールは無効になります。

![Teams での [会議のスケジュール設定] オプションを示すスクリーンショット。](media/schedule-meeting-option.png)

チャネルの選択が無効になっています。

[ ![会議をスケジュール設定するチャネルを選択するための予定表オプションを示すスクリーンショット。](media/meeting-policies-select-a-channel-to-meet-in.png) ](media/meeting-policies-select-a-channel-to-meet-in.png#lightbox)

チャネル投稿ページで、次のものが無効になります。

- [チャネル返信の作成] ボックスの [**会議のスケジュール**] ボタン
  ![会議をスケジュール設定するチャネルを選択するための予定表オプションを示すスクリーンショット。](media/schedule-meeting-disabled-in-chat2.png)
  
- チャネル ヘッダーの [**会議のスケジュール**] ボタン。
  ![会議をスケジュール設定するチャネルを選択するための予定表オプションを示すスクリーンショット。](media/schedule-now-in-header.png)

[チャネル カレンダー] で、次の操作を行います。

- チャンネル予定表ヘッダーの[**新しいイベントの追加**] ボタンは、無効になります。
  ![会議をスケジュール設定できるようにするチャネルを選択するための予定表オプションを示すスクリーンショット。](media/add-new-event-disabled.png)

- ユーザーは、チャネルの予定表で時間ブロックをドラッグしたり、選択したりしてチャネル会議を作成することができなくなります。

- ユーザーは、キーボード ショートカットを使用してチャネルの予定表で会議を作成できません。

管理センターにて

[アプリのアクセス許可ポリシー] ページの [**Microsoft アプリ**] セクションに、チャネル カレンダー アプリが表示されます。

![Teams 管理センターでのアプリのアクセス許可ポリシーを示すスクリーンショット。](media/manage-microsoft-apps-policy.png)

## <a name="private-meeting-scheduling"></a>プライベート会議のスケジュール設定

これはユーザーごとのポリシーであり、会議が始まる前に適用されます。 この設定は、ユーザーが Teams でプライベート会議をスケジュールできるかどうかを制御します。 チームのチャネルに公開されていない会議はプライベートです。

Note that if you turn off **Allow scheduling private meetings** and **Allow channel meeting scheduling**,  the **Add required attendees** and **Add channel** options are disabled for users in Teams. By default, this setting is turned on.

## <a name="meet-now-in-private-meetings"></a>プライベート会議での "今すぐ会議"

これはユーザーごとのポリシーであり、会議が始まる前に適用されます。 この設定は、ユーザーがアドホック プライベート会議を開始できるかどうかを制御します。  既定では、この設定は[オン] に設定されています。

## <a name="designated-presenter-role-mode"></a>指定された発表者の役割モード

これは、ユーザーごとのポリシーです。 この設定では、Teams クライアントの **会議オプション** の **誰がプレゼンをするか?** の設定の既定値を変更することができます。 このポリシー設定は、Meet Now (今すぐ会議) を含むすべての会議に影響します。

**誰がプレゼンをするか?** の設定を使用すると、会議の開催者は会議の発表者を選択することができます。 詳細については、「[Teams 会議の参加者設定の変更](https://support.microsoft.com/article/change-participant-settings-for-a-teams-meeting-53261366-dbd5-45f9-aae9-a70e6354f88e)」 と 「[Teams 会議での役割](https://support.microsoft.com/article/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019)」を参照してください。

現在、このポリシー設定を構成することができるのは、PowerShell を使用した場合のみです。 [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy) コマンドレットを使用して、既存の Teams 会議ポリシーを編集することができます。 または、[New-CsTeamsMeetingPolicy](/powershell/module/skype/new-csteamsmeetingpolicy) コマンドレットを使用して、新しい Teams の会議ポリシーを作成し、ユーザーに割り当てます。

Teams の **誰がプレゼンをするか?** 設定の既定値を指定するには、**DesignatedPresenterRoleMode** パラメーターを次のいずれかに設定します。

- **EveryoneUserOverride**: すべての会議参加者は発表者になることができます。 これが既定値です。 このパラメーターは、 Teams 内の **すべてのユーザー** の設定 に呼応します。
- **EveryoneInCompanyUserOverride**: 組織内の認証済みユーザー (ゲスト ユーザーを含む) は、発表者になることができます。 このパラメーターは、Teams の **組織内の人たち** 設定に呼応します。
- **OrganizerOnlyUserOverride**: 会議の開催者のみが発表者となり、他のすべての会議参加者が出席者として指定されます。 このパラメーターは、Teams の [**私だけ**] 設定に呼応します。

既定値を設定した後でも、会議の開催者はチームの設定を変更し、スケジュールした会議での発表者を選ぶことができることにご注意ください。

## <a name="engagement-report"></a>エンゲージメント レポート

これは、ユーザーごとのポリシーです。 この設定では、会議の開催者が [会議出席レポート](teams-analytics-and-reports/meeting-attendance-report.md)をダウンロードできるかどうかを制御します。

このポリシーは既定で有効になっているため、開催者は、自分が設定した会議やウェビナーに登録したユーザーと出席したユーザーを確認できます。 Teams 管理センターでこれを無効にするには、**[会議]** > **[会議ポリシー]** の順に移動し、**[エンゲージメント レポート]** 設定を **[オフ]** に設定します。

[Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy) コマンドレットを使用して、既存の Teams 会議ポリシーを編集することもできます。 または、[New-CsTeamsMeetingPolicy](/powershell/module/skype/new-csteamsmeetingpolicy) コマンドレットを使用して、新しい Teams の会議ポリシーを作成し、ユーザーに割り当てます。

既定では、PowerShell で **AllowEngagementReport** パラメーターは **Enabled** に設定されています。 会議の開催者が会議出席レポートをダウンロードできないようにするには、**AllowEngagementReport** パラメーターを **Disabled** に設定します。

このポリシーが有効になっている場合は、会議出席レポートをダウンロードするためのオプションが **[参加者]** ウィンドウに表示されます。

> [!NOTE]
> 管理者は、自分が開催していない会議の出席レポートを表示できません。 ただし、特定の会議から 24 時間以内に、その会議の参加者の詳細を表示できます。 Teams 管理センターで、**[ユーザー]** > **[ユーザーの管理]** の順に移動します。 会議の開催者の表示名を選択します。 **[会議と通話]** タブを選択してから、適切な会議 ID または通話 ID を選択します。 次に、**[参加者の詳細]** を選択します。

エンゲージメント レポートの制限を含む詳細については、[Teams での会議出席レポートの表示とダウンロード](https://support.microsoft.com/office/view-and-download-meeting-attendance-reports-in-teams-ae7cf170-530c-47d3-84c1-3aedac74d310)に関するページを参照してください。

## <a name="meeting-registration"></a>会議の登録

これは、ユーザーごとのポリシーです。 これを有効にすると、組織内のユーザーはウェビナーを設定できます。 このポリシーは、既定で有効になっています。

Teams 管理センターでこのポリシーを編集するには、**[会議]** > **[会議ポリシー]** の順に移動します。 会議の登録を無効にするには、このポリシーを **[オフ]** に設定します。

[Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy) コマンドレットを使用して、既存の Teams 会議ポリシーを編集することができます。 または、[New-CsTeamsMeetingPolicy](/powershell/module/skype/new-csteamsmeetingpolicy) コマンドレットを使用して、新しい Teams の会議ポリシーを作成し、ユーザーに割り当てます。

会議の登録を有効にするには、**MeetingRegistration** パラメーターを **True** に設定します。 これは、既定では **True** に設定されています。

会議の登録を無効にし、ユーザーがウェビナーをスケジュール設定できないようにするには、このパラメーターを **False** に設定します。

## <a name="who-can-register"></a>登録できるユーザー

このポリシーでは、どのユーザーがウェビナーに登録して参加できるかを制御します。 このポリシーには、**[会議の登録]** が有効になっている場合にのみ使用できる 2 つのオプションがあります。

- 匿名ユーザーを含むすべてのユーザーに、組織内のユーザーが設定したウェビナーの登録と出席を許可する場合は、[だれが登録 **できるか** ] を [ **すべての** ユーザー] に設定します。
- 組織内のユーザーのみがウェビナーに登録して参加できるようにする場合は、**[登録できるユーザー]** を **[組織内のすべてのユーザー]** に設定します。

既定では、**[登録できるユーザー]** は **[すべてのユーザー]** に設定されています。 Teams 管理センターでこのポリシーを編集するには、**[会議]** > **[会議ポリシー]** の順に移動します。

[Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy) コマンドレットを使用して、既存の Teams 会議ポリシーを編集することができます。 または、[New-CsTeamsMeetingPolicy](/powershell/module/skype/new-csteamsmeetingpolicy) コマンドレットを使用して、新しい Teams の会議ポリシーを作成し、ユーザーに割り当てます。

To allow everyone, including anonymous users, to register and attend webinars, set the **WhoCanRegister** parameter to **Everyone**. This is set to **Everyone** by default.

組織内のユーザーのみがウェビナーに登録して参加できるようにするには、このパラメーターを **EveryoneInCompany** に設定します。

## <a name="meeting-provider-for-islands-mode"></a>アイランド モードの会議プロバイダー

これは、ユーザーごとのポリシーです。 この設定は、*アイランド モードのユーザー* がどの Outlook 会議アドインを使用するかを制御できます。 Teams 会議アドインのみを使用するか、Teams 会議アドインと Skype for Business 会議アドインの両方を使用するかを指定して、Outlook で会議をスケジュールできます。

このポリシーは、アイランドモードで、Teams の会議ポリシーで **AllowOutlookAddIn** パラメーターが **True** に設定されているユーザーにのみ適用できます。

現在、このポリシーを設定するには PowerShell を使用する必要があります。 [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy) コマンドレットを使用して、既存の Teams 会議ポリシーを編集することができます。 または、[New-CsTeamsMeetingPolicy](/powershell/module/skype/new-csteamsmeetingpolicy) コマンドレットを使用して、新しい Teams の会議ポリシーを作成し、ユーザーに割り当てます。

ユーザーが使用できる会議アドインを指定するには、次のように **PreferredMeetingProviderForIslandsMode** パラメーターを指定します。

- Set the parameter to **TeamsAndSfB** to enable both the Teams Meeting add-in and Skype for Business add-in in Outlook. This is the default value.
- パラメーターを **Teams** に設定すると、Outlook の Teams 会議アドインのみが有効になります。 このポリシー設定では、今後のすべての会議にTeams の会議への参加リンクがあることが確実になります。 既存の Skype for Business 会議の参加リンクはTeams には移行されません。 このポリシー設定は、ユーザーが Skype for Business への参加、チャット、PSTN 通話、その他の機能を使用することに影響を与えません。ユーザーが Skype for Business の機能を引き続き使用できることを意味します。

  パラメーターを **Teams** に設定し、**の TeamsAndSfB** に戻すと、両方の会議アドインが有効になります。 ただし、既存の Teams 会議の参加リンクは、Skype for Business に移行されないことにご注意ください。 変更の後にスケジュールされた Skype for Business の会議のみが、Skype for Business の会議参加リンクを持つようになります。

## <a name="meeting-reactions"></a>会議の応答
会議の反応の可用性は、Teams 管理センター インターフェイスまたは PowerShell を使用して構成できます。 会議の反応は、会議ポリシーの **[参加者&ゲスト** ] セクションで有効または無効にすることができます。

設定を構成するには、Set-CsTeamsMeetingPolicy コマンドレットを使用します。 この設定は既定で有効になっています。 オフにするには、 **AllowMeetingReactions** を False に設定 **します**。

会議の反応は、既定ではオフになっています。 ユーザーに対して反応をオフにしても、ユーザーがスケジュールする会議で反応を利用できないという意味ではありません。 既定の設定に関係なく、会議の開催者は [会議のオプション] ページで反応をオンにできます。

## <a name="speaker-coach"></a>スピーチ コーチ

この設定を使用すると、ユーザーは Teams 会議中にスピーチ コーチを有効にすることができます。 スピーチ コーチは、プレゼンテーション中にユーザーの音声に耳を傾け、改善のためのプライベートなリアルタイムのフィードバックと提案を提供します。 また、ユーザーは、会議の後にフィードバックの要約レポートを取得します。

> [!NOTE]
> The user who turned on Speaker Coach during the meeting is the only one who can see the summary report of feedback. Admins won't have access to any of this data.

現時点では、PowerShell でのみこのポリシーを設定および編集できます。 [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy) コマンドレットを使用します。 または、[New-CsTeamsMeetingPolicy](/powershell/module/skype/new-csteamsmeetingpolicy) コマンドレットを使用して、新しい Teams の会議ポリシーを作成し、ユーザーに割り当てます。

この設定は既定で有効になっています。 オフにするには、**AllowMeetingCoach** を **False** に設定します。

## <a name="related-topics"></a>関連項目

- [Teams での PowerShell の概要](teams-powershell-overview.md)
- [Teams でポリシーを割り当てる](policy-assignment-overview.md)
- [ユーザーから RestrictedAnonymousAccess Teams 会議ポリシーを削除する](meeting-policies-restricted-anonymous-access.md)
