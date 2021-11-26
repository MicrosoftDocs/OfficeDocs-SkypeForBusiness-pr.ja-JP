---
title: 一般会議ポリシーを管理する
author: CarolynRowe
ms.author: crowe
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
description: 会議の全般ポリシー設定を管理する方法については、Teams。
ms.openlocfilehash: b7c08799ee9e7c2b1e6239b17abaa66b7d1e3d47
ms.sourcegitcommit: 7cc7e237b0da270c9cf4a3e535db16dd113e4300
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/25/2021
ms.locfileid: "61177938"
---
# <a name="meeting-policy-settings---general"></a>会議ポリシーの設定 - 全般

<a name="bkgeneral"> </a>

この記事では、会議の一般的なポリシー設定についてTeamsします。

- [チャネルで今すぐ会う](#meet-now-in-channels)
- [Outlook アドイン](#outlook-add-in)
- [チャネル会議のスケジュール](#channel-meeting-scheduling)
- [プライベート会議のスケジュール設定](#private-meeting-scheduling)
- [プライベート会議で今すぐ会議を行う](#meet-now-in-private-meetings)
- [指定された発表者ロール モード](#designated-presenter-role-mode)
- [エンゲージメント レポート](#engagement-report)
- [会議の登録](#meeting-registration)
- [Who登録可能](#who-can-register)
- [諸島モードの会議プロバイダー](#meeting-provider-for-islands-mode)

## <a name="meet-now-in-channels"></a>チャネルで今すぐ会う

これはユーザーごとのポリシーであり、会議が始まる前に適用されます。 この設定は、ユーザーが Teams チャネルでアドホック会議を開始できるかどうかを制御します。 これを有効にした場合、ユーザーは [会議] ボタンをクリックして、臨時の会議を開始したり、チャネルで会議をスケジュールすることができます。 既定値は True です。

[![メッセージの下に [今すぐ会う] アイコンを示すスクリーンショット。 ](media/meeting-policies-meet-now.png) ](media/meeting-policies-meet-now.png#lightbox)

## <a name="outlook-add-in"></a>Outlook アドイン

これはユーザーごとのポリシーであり、会議が始まる前に適用されます。 この設定は、Outlook (Windows、Mac、Web、およびモバイル) 内から Teams 会議をスケジュールできるかどうかを制御します。

![新しい会議をスケジュールする機能が表示されたスクリーンショット。](media/meeting-policies-outlook-add-in.png)

これをオフにすると、ユーザーは Outlook で新しい会議を作成するときに Teams 会議をスケジュールできなくなります。 たとえば、Windows 上の Outlook では、[**新しい Teams 会議**] オプションはリボンに表示されません。

## <a name="channel-meeting-scheduling"></a>チャネル会議のスケジュール

既存の[AllowChannelMeetingScheduling] ポリシーを使用して、チームのチャネルの予定表で作成できるイベントの種類を制御します。 これはユーザーごとのポリシーであり、会議が始まる前に適用されます。 この設定は、ユーザーが Teams チャネルで会議をスケジュールできるかどうかを制御します。 既定では、この設定は[オン] に設定されています。 

このポリシーがオフになっている場合、ユーザーは新しいチャネル会議を作成できます。 ただし、既存のチャネル会議は、イベントの開催者が編集できます。

会議のスケジュールは無効になります。

![[会議のスケジュール] オプションを示すスクリーンショットTeams。](media/schedule-meeting-option.png)

チャネルの選択が無効になっています。

[![会議のスケジュールを設定するチャネルを選択する予定表オプションを示すスクリーンショット。 ](media/meeting-policies-select-a-channel-to-meet-in.png) ](media/meeting-policies-select-a-channel-to-meet-in.png#lightbox)

チャネルの投稿ページで、次の機能が無効になります。

- [チャネル返信の作成] ボックスの [**会議のスケジュール**] ボタン
  ![会議をスケジュールするチャネルを選択する予定表オプションを示すスクリーンショット。](media/schedule-meeting-disabled-in-chat2.png)
  
- チャネル ヘッダーの [**会議のスケジュール**] ボタン。
  ![会議のスケジュールを設定するチャネルを選択する予定表オプションを示すスクリーンショット。](media/schedule-now-in-header.png)

[チャネル カレンダー] で、次の操作を行います。

- チャンネル予定表ヘッダーの[**新しいイベントの追加**] ボタンは、無効になります。
  ![会議のスケジュールを設定できるチャネルを選択する予定表オプションを示すスクリーンショット。](media/add-new-event-disabled.png)

- ユーザーは、チャネル予定表で時間ブロックをドラッグして選択して、チャネル会議を作成できない。

- ユーザーは、キーボード ショートカットを使用して、チャネルの予定表に会議を作成することはできません。

管理センターにて

[アプリのアクセス許可ポリシー] ページの [**Microsoft アプリ**] セクションに、チャネル カレンダー アプリが表示されます。

![管理センターのアプリのアクセス許可ポリシー Teamsスクリーンショット。](media/manage-microsoft-apps-policy.png)

## <a name="private-meeting-scheduling"></a>プライベート会議のスケジュール設定

これはユーザーごとのポリシーであり、会議が始まる前に適用されます。 この設定は、ユーザーが Teams でプライベート会議をスケジュールできるかどうかを制御します。 チームのチャネルに公開されていない会議はプライベートです。

[**プライベート会議のスケジュールを許可する**] および [**チャネルの会議スケジュールを許可する**] を無効にすると、Teams のユーザーに対して [**必須出席者の追加**] および [**チャネルの追加**] オプションが無効になります。 既定では、この設定は[オン] に設定されています。

## <a name="meet-now-in-private-meetings"></a>プライベート会議で今すぐ会議を行う

これはユーザーごとのポリシーであり、会議が始まる前に適用されます。 この設定は、ユーザーがアドホック プライベート会議を開始できるかどうかを制御します。  既定では、この設定は[オン] に設定されています。

## <a name="designated-presenter-role-mode"></a>指定された発表者ロール モード

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

このポリシーは既定でオフになっています。開催者は、設定した会議やウェビナーを誰が登録して参加したのか確認できます。 管理センターでこれを有効Teams、[**会議の会議** ポリシー] に移動し、ポリシーを [有効]  >  に **設定します**。

[Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy) コマンドレットを使用して、既存の Teams 会議ポリシーを編集することができます。 または、[New-CsTeamsMeetingPolicy](/powershell/module/skype/new-csteamsmeetingpolicy) コマンドレットを使用して、新しい Teams の会議ポリシーを作成し、ユーザーに割り当てます。

会議の開催者が会議出席レポートをダウンロードするには **、AllowEngagementReport** パラメーターを [有効] に **設定します**。 有効にすると、**参加者** ウィンドウに、レポートをダウンロードするためのオプションが表示されます。 既定では、この設定は有効になっていません。

会議の開催者がレポートをダウンロードしないようにするには、パラメーターを [**無効**] に設定します。

## <a name="meeting-registration"></a>会議の登録

これは、ユーザーごとのポリシーです。 これを有効にした場合、組織内のユーザーはウェビナーを設定できます。 このポリシーは既定で有効になっています。

管理センターでこのポリシーを編集Teams、[会議の会議ポリシー]  >  **に移動します**。 会議の登録をオフにする場合は、ポリシーを [オフ] に **設定します**。

[Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy) コマンドレットを使用して、既存の Teams 会議ポリシーを編集することができます。 または、[New-CsTeamsMeetingPolicy](/powershell/module/skype/new-csteamsmeetingpolicy) コマンドレットを使用して、新しい Teams の会議ポリシーを作成し、ユーザーに割り当てます。

会議の登録を有効にする場合は  **、MeetingRegistration パラメーター** を True に **設定します**。 これは既定で **True に** 設定されています。

会議の登録をオフにし、ユーザーがウェビナーをスケジュールできない場合は、 パラメーターを False に **設定します**。

## <a name="who-can-register"></a>Who登録可能

このポリシーは、ウェビナーを登録して参加できるユーザーを制御します。 このポリシーには 2 つのオプションがあります。このオプションは、会議の登録が有効 **になっている** 場合にのみ使用できます。

- 匿名 **Who** を含むすべてのユーザーが、組織内のユーザーが設定したウェビナーの登録と参加を許可する場合は、[すべてのユーザー] に登録できます。
- 組織内 **Whoの** ユーザーにのみウェビナーの登録と参加を許可する場合は、[組織内のすべてのユーザー] に登録できるオプションを設定します。

既定では、**登録Whoは [すべてのユーザー** ] に **設定されています**。 管理センターでこのポリシーを編集Teams、[会議の会議ポリシー]  >  **に移動します**。

[Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy) コマンドレットを使用して、既存の Teams 会議ポリシーを編集することができます。 または、[New-CsTeamsMeetingPolicy](/powershell/module/skype/new-csteamsmeetingpolicy) コマンドレットを使用して、新しい Teams の会議ポリシーを作成し、ユーザーに割り当てます。

匿名ユーザーを含むすべてのユーザーがウェビナーを登録して参加するには **、WhoCanRegister** パラメーターを Everyone に設定 **します**。 これは既定で [ **すべてのユーザー] に** 設定されています。

組織内のユーザーだけがウェビナーの登録と参加を許可するには、 パラメーターを **EveryoneInCompany に設定します**。

## <a name="meeting-provider-for-islands-mode"></a>諸島モードの会議プロバイダー

これは、ユーザーごとのポリシーです。 この設定は、*アイランド モードのユーザー* がどの Outlook 会議アドインを使用するかを制御できます。 Teams 会議アドインのみを使用するか、Teams 会議アドインと Skype for Business 会議アドインの両方を使用するかを指定して、Outlook で会議をスケジュールできます。

このポリシーは、アイランドモードで、Teams の会議ポリシーで **AllowOutlookAddIn** パラメーターが **True** に設定されているユーザーにのみ適用できます。

現在、このポリシーを設定するには PowerShell を使用する必要があります。 [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy) コマンドレットを使用して、既存の Teams 会議ポリシーを編集することができます。 または、[New-CsTeamsMeetingPolicy](/powershell/module/skype/new-csteamsmeetingpolicy) コマンドレットを使用して、新しい Teams の会議ポリシーを作成し、ユーザーに割り当てます。

ユーザーが使用できる会議アドインを指定するには、次のように **PreferredMeetingProviderForIslandsMode** パラメーターを指定します。

- パラメーターを **TeamsAndSfB** に設定すると、Outlook の Teams 会議アドインと Skype for Business アドインの両方が有効になります。 これが既定値です。
- パラメーターを **Teams** に設定すると、Outlook の Teams 会議アドインのみが有効になります。 このポリシー設定では、今後のすべての会議にTeams の会議への参加リンクがあることが確実になります。 既存の Skype for Business 会議の参加リンクはTeams には移行されません。 このポリシー設定は、ユーザーが Skype for Business への参加、チャット、PSTN 通話、その他の機能を使用することに影響を与えません。ユーザーが Skype for Business の機能を引き続き使用できることを意味します。

  パラメーターを **Teams** に設定し、**の TeamsAndSfB** に戻すと、両方の会議アドインが有効になります。 ただし、既存の Teams 会議の参加リンクは、Skype for Business に移行されないことにご注意ください。 変更の後にスケジュールされた Skype for Business の会議のみが、Skype for Business の会議参加リンクを持つようになります。

## <a name="meeting-reactions"></a>会議の反応

AllowMeetingReactions 設定は、PowerShell を使用してのみ適用できます。 Teams 管理センターから AllowMeetingReactions のオンまたはオフを切り替えるオプションはありません。

会議の反応は、既定ではオフになっています。 ユーザーに対して反応をオフにしても、ユーザーがスケジュールする会議で反応を利用できないという意味ではありません。 既定の設定に関係なく、会議の開催者は [会議のオプション] ページで反応をオンにできます。


## <a name="related-topics"></a>関連項目

- [Teams での PowerShell の概要](teams-powershell-overview.md)
- [[ポリシーの割り当て] Teams](policy-assignment-overview.md)
- [ユーザーから RestrictedAnonymousAccess Teams 会議ポリシーを削除する](meeting-policies-restricted-anonymous-access.md)
