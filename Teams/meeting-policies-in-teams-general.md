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
- m365initiative-meetings
appliesto:
- Microsoft Teams
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.meetingpolicies.general
- seo-marvel-apr2020
description: Teams で一般的な会議ポリシー設定を管理する方法について説明します。
ms.openlocfilehash: cc0d704c5a78d09da4c1332d48f795cdb611d134
ms.sourcegitcommit: 84a832330c0a9f9fb818bbfb22e534fe035c1837
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/03/2023
ms.locfileid: "69693380"
---
# <a name="meeting-policy-settings---general"></a>会議ポリシーの設定 - 全般

<a name="bkgeneral"> </a>

この記事では、Teams 会議での次の一般的なポリシー設定について説明します。

- [チャネルでの "今すぐ会議"](#meet-now-in-channels)
- [Outlook アドイン](#outlook-add-in)
- [チャネル会議のスケジュール設定](#channel-meeting-scheduling)
- [プライベート会議のスケジュール設定](#private-meeting-scheduling)
- [エンゲージメント レポート](#engagement-report)
- [会議の登録](#meeting-registration)
- [ウェビナー](#webinars)
- [アイランド モードの会議プロバイダー](#meeting-provider-for-islands-mode)
- [会議の応答](#meeting-reactions)
- [スピーチ コーチ](#speaker-coach)

## <a name="meet-now-in-channels"></a>チャネルでの "今すぐ会議"

これはユーザーごとのポリシーであり、会議が始まる前に適用されます。 この設定は、ユーザーが Teams チャネルで予定外の会議を開始できるかどうかを制御します。 この設定を有効にすると、ユーザーは [ **会議** ] ボタンをクリックして計画外の会議を開始したり、チャネルで会議をスケジュールしたりできます。 この設定は既定でオンになっています。

[![メッセージの下の [今すぐ会議] アイコンを示すスクリーンショット。](media/meeting-policies-meet-now.png)](media/meeting-policies-meet-now.png#lightbox)

## <a name="outlook-add-in"></a>Outlook アドイン

これはユーザーごとのポリシーであり、会議が始まる前に適用されます。 この設定は、Outlook (Windows、Mac、Web、およびモバイル) 内から Teams 会議をスケジュールできるかどうかを制御します。

![新しい会議をスケジュールする機能が表示されたスクリーンショット。](media/meeting-policies-outlook-add-in.png)

この設定をオフにすると、ユーザーは Outlook で新しい会議を作成するときに Teams 会議をスケジュールできません。 たとえば、Windows 上の Outlook では、[**新しい Teams 会議**] オプションはリボンに表示されません。

## <a name="channel-meeting-scheduling"></a>チャネル会議のスケジュール設定

既存の[AllowChannelMeetingScheduling] ポリシーを使用して、チームのチャネルの予定表で作成できるイベントの種類を制御します。 これはユーザーごとのポリシーであり、会議が始まる前に適用されます。 この設定は、ユーザーが Teams チャネルで会議をスケジュールできるかどうかを制御します。 既定では、この設定は[オン] に設定されています。

このポリシーが無効になっている場合、ユーザーは新規のチャネル会議を作成できません。 ただし、既存のチャネル会議は、イベントの開催者が編集できます。

会議のスケジュールは無効になります。

![Teams での [会議のスケジュール設定] オプションを示すスクリーンショット。](media/schedule-meeting-option.png)

チャネルの選択が無効になっています。

[![会議をスケジュール設定するチャネルを選択するための予定表オプションを示すスクリーンショット。](media/meeting-policies-select-a-channel-to-meet-in.png)](media/meeting-policies-select-a-channel-to-meet-in.png#lightbox)

チャネル投稿ページでは、次の機能が無効になります。

- [チャネル返信の作成] ボックスの [**会議のスケジュール**] ボタン
  ![会議をスケジュール設定するチャネルを選択するための予定表オプションを示すスクリーンショット。](media/schedule-meeting-disabled-in-chat2.png)
  
- チャネル ヘッダーの [**会議のスケジュール**] ボタン。
  ![会議をスケジュール設定するチャネルを選択するための予定表オプションを示すスクリーンショット。](media/schedule-now-in-header.png)

[チャネル カレンダー] で、次の操作を行います。

- チャンネル予定表ヘッダーの[**新しいイベントの追加**] ボタンは、無効になります。
  ![会議をスケジュール設定できるようにするチャネルを選択するための予定表オプションを示すスクリーンショット。](media/add-new-event-disabled.png)

- ユーザーはチャネルの会議を作成するために、チャネルの予定表の時間ブロックをドラッグ アンド ドロップすることはできません。

- ユーザーがキーボード ショートカットを使用して、チャンネル予定表で会議を作成することはできません。

管理センターにて

[アプリのアクセス許可ポリシー] ページの [**Microsoft アプリ**] セクションに、チャネル カレンダー アプリが表示されます。

![Teams 管理センターでのアプリのアクセス許可ポリシーを示すスクリーンショット。](media/manage-microsoft-apps-policy.png)

## <a name="private-meeting-scheduling"></a>プライベート会議のスケジュール設定

これはユーザーごとのポリシーであり、会議が始まる前に適用されます。 この設定は、ユーザーが Teams でプライベート会議をスケジュールできるかどうかを制御します。 チームのチャネルに公開されていない会議はプライベートです。 **プライベート会議のスケジュール** 設定は、既定でオンになっています。

**プライベート会議のスケジュール設定とチャネル会議のスケジュール** 設定の両方 **を** オフにすると、Teams のユーザーに対して **[必要な出席者の追加]** オプションと **[チャネルの追加]** オプションが無効になります。

## <a name="engagement-report"></a>エンゲージメント レポート

これは、ユーザーごとのポリシーです。 この設定は、会議の開催者が [会議のエンゲージメント レポート](teams-analytics-and-reports/meeting-attendance-report.md)をダウンロードできるかどうかを制御します。

このポリシーは既定で有効になっているため、開催者は、自分が設定した会議やウェビナーに登録したユーザーと出席したユーザーを確認できます。 Teams 管理センターでこれを無効にするには、**[会議]** > **[会議ポリシー]** の順に移動し、**[エンゲージメント レポート]** 設定を **[オフ]** に設定します。

[Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy) コマンドレットを使用して、既存の Teams 会議ポリシーを編集することもできます。 または、[New-CsTeamsMeetingPolicy](/powershell/module/skype/new-csteamsmeetingpolicy) コマンドレットを使用して、新しい Teams の会議ポリシーを作成し、ユーザーに割り当てます。

既定では、PowerShell で **AllowEngagementReport** パラメーターは **Enabled** に設定されています。 会議の開催者が会議エンゲージメント レポートをダウンロードできないようにするには、[ **AllowEngagementReport** ] パラメーターを **[無効]** に設定します。

このポリシーを有効にすると、[ **参加者** ] ウィンドウに会議エンゲージメント レポートをダウンロードするオプションが表示されます。

> [!NOTE]
> 管理者は、自分が開催していない会議の出席レポートを表示できません。 ただし、特定の会議から 24 時間以内に、その会議の参加者の詳細を表示できます。 Teams 管理センターで、**[ユーザー]** > **[ユーザーの管理]** の順に移動します。 会議の開催者の表示名を選択します。 **[会議と通話]** タブを選択してから、適切な会議 ID または通話 ID を選択します。 次に、**[参加者の詳細]** を選択します。

エンゲージメント レポートの制限を含む詳細については、[Teams での会議出席レポートの表示とダウンロード](https://support.microsoft.com/office/ae7cf170-530c-47d3-84c1-3aedac74d310)に関するページを参照してください。

## <a name="meeting-registration"></a>会議の登録

これは、ユーザーごとのポリシーです。 この設定を有効にすると、組織内のユーザーが会議に登録を追加できます。 このポリシーは、既定で有効になっています。

会議の登録の詳細については、「会議登録の [構成」を](set-up-webinars.md#configure-meeting-registration)参照してください。

## <a name="webinars"></a>ウェビナー

これは、ユーザーごとのポリシーです。 ウェビナーを有効にした場合、組織内のユーザーは、堅牢な登録管理、カスタマイズ可能なイベントと登録サイト、イベント指向の既定の会議オプションを使用してウェビナーを作成できます。 このポリシーは、既定で有効になっています。

ウェビナーの詳細については、「ウェビナーのセットアップ」を [参照してください](set-up-webinars.md)。

会議、ウェビナー、ライブ イベントの違いの詳細については、「 [会議、ウェビナー、ライブ イベント](quick-start-meetings-live-events.md)」を参照してください。

## <a name="meeting-provider-for-islands-mode"></a>アイランド モードの会議プロバイダー

これは、ユーザーごとのポリシーです。 この設定は、*アイランド モードのユーザー* がどの Outlook 会議アドインを使用するかを制御できます。 Teams 会議アドインのみを使用するか、Teams 会議アドインと Skype for Business 会議アドインの両方を使用するかを指定して、Outlook で会議をスケジュールできます。

このポリシーは、アイランドモードで、Teams の会議ポリシーで **AllowOutlookAddIn** パラメーターが **True** に設定されているユーザーにのみ適用できます。

現在、このポリシーを設定するには PowerShell を使用する必要があります。 [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy) コマンドレットを使用して、既存の Teams 会議ポリシーを編集することができます。 または、[New-CsTeamsMeetingPolicy](/powershell/module/skype/new-csteamsmeetingpolicy) コマンドレットを使用して、新しい Teams の会議ポリシーを作成し、ユーザーに割り当てます。

ユーザーが使用できる会議アドインを指定するには、次のように **PreferredMeetingProviderForIslandsMode** パラメーターを指定します。

- パラメーターを **TeamsAndSfB** に設定すると、Outlook の Teams 会議アドインと Skype for Business アドインの両方が有効になります。 **TeamsAndSfB** は既定値です。
- パラメーターを **Teams** に設定すると、Outlook の Teams 会議アドインのみが有効になります。 このポリシー設定では、今後のすべての会議にTeams の会議への参加リンクがあることが確実になります。 既存の Skype for Business 会議の参加リンクはTeams には移行されません。 このポリシー設定は、ユーザーが Skype for Business への参加、チャット、PSTN 通話、その他の機能を使用することに影響を与えません。ユーザーが Skype for Business の機能を引き続き使用できることを意味します。

  パラメーターを **Teams** に設定し、**の TeamsAndSfB** に戻すと、両方の会議アドインが有効になります。 ただし、既存の Teams 会議の参加リンクは、Skype for Business に移行されないことにご注意ください。 変更の後にスケジュールされた Skype for Business の会議のみが、Skype for Business の会議参加リンクを持つようになります。

## <a name="meeting-reactions"></a>会議の応答

会議リアクションの可用性は、Teams 管理センターインターフェイスまたは PowerShell を使用して構成できます。 会議のリアクションは既定で有効になっています。

Teams 管理センターでは、会議ポリシーの [**参加者&ゲスト**] セクションの **[会議会議** > **ポリシー**] で、会議のリアクションを有効または無効にすることができます。

PowerShell で設定を構成するには、 [Set-CsTeamsMeetingPolicy コマンドレットを](/powershell/module/skype/set-csteamsmeetingpolicy) 使用します。 オフにするには、 **AllowMeetingReactions を** False に設定 **します**。

ユーザーのリアクションをオフにしても、ユーザーがスケジュールした会議でリアクションを使用できないわけではありません。 既定の設定に関係なく、会議の開催者は [会議のオプション] ページで反応をオンにできます。

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
