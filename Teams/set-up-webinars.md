---
title: Microsoft Teams でのウェビナーのセットアップ
author: KarliStites
ms.author: kastites
manager: serdars
ms.reviewer: sachung, emryan
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: ''
ms.collection:
- M365-collaboration
- m365initiative-meetings
description: Teams会議のウェビナー ポリシーを管理する方法について説明します。
ms.openlocfilehash: 5536a6c03df15be349edea7d980932b5fc0173ab
ms.sourcegitcommit: faeb8976299375e7658499ff31d25e8ef6003144
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2022
ms.locfileid: "62224004"
---
# <a name="set-up-for-webinars-in-microsoft-teams"></a>Microsoft Teams でのウェビナーのセットアップ

この記事は、ウェビナーをホストするように組織を設定するのに役立ちます。

## <a name="what-are-webinars"></a>ウェビナーとは

ウェビナーは、発表者と参加者が明確な役割を持つ構造化された会議であり、多くの場合、トレーニング目的や営業およびマーケティングのリード生成シナリオに使用されます。

組織内でウェビナーを設定した後、ユーザーはウェビナーをスケジュールし、出席者に登録を開くことができます。 多くのディスカッションやタスクの割り当てを含む従来の会議とは異なり、ウェビナーは対話型のプレゼンテーションを目的とし、出席者分析用のツールを提供します。

> [!IMPORTANT]
> ユーザーがウェビナーを設定できるようにするには、個人用リストの作成を有効にしてSharePointでMicrosoft Listsを構成する必要があります。 詳細については、「[Microsoft Listsの制御設定」を](/sharepoint/control-lists)参照してください。

## <a name="allow-users-to-schedule-webinars-in-the-teams-admin-center"></a>Teams管理センターでウェビナーをスケジュールできるようにする

Teams管理センターを使用して、組織のウェビナーを設定できます。 ウェビナーを設定するポリシーは、**MeetingsMeeting** >  ポリシーのTeams管理センターにあります。

### <a name="meeting-registration"></a>会議の登録

これを有効にすると、ユーザーはウェビナーをスケジュールできます。 既定では、これはオンになっています。 会議の登録を無効にする場合は、このポリシーを **[オフ]** に設定します。

> [!IMPORTANT]
> 会議の登録を機能させるには、プライベート会議の **スケジュール設定** をオンにする必要があります。 既定では、このポリシーはTeams管理センターで有効になっています。 教育機関テナントの学生の場合、このポリシーは既定で無効になっています。 学生のプライベート会議のスケジュール設定を有効にする方法の詳細については、「[Microsoft Teams for Education ポリシーとポリシー パッケージ](policy-packages-edu.md)」を参照してください。

### <a name="who-can-register"></a>登録できるユーザー

**[すべての** ユーザー] を選択すると、匿名ユーザーを含むすべてのユーザーがウェビナーに登録して参加できます。 **[組織内のすべてのユーザー**] を選択した場合、組織内のユーザーのみがウェビナーに登録できます。 会議の登録がオフになっている場合、このオプションは使用できず、ウェビナーに登録することはできません。

> [!NOTE]
> **登録できるWho** の既定値は、教育機関テナント **内の組織内のすべてのユーザー** です。 詳細については、「[Microsoft Teams for Education ポリシー ウィザード](easy-policy-setup-edu.md)」を参照してください。

### <a name="engagement-report"></a>エンゲージメント レポート

これがオンの場合、開催者は、設定したウェビナーを登録して参加したユーザーのレポートを表示できます。 このポリシーは既定でオンになっています。 詳細については、「[Teams - エンゲージメント レポートの会議ポリシー](meeting-policies-in-teams-general.md#engagement-report)」を参照してください。 エンド ユーザー エクスペリエンスの詳細については、「 [会議出席レポートの表示とダウンロード](https://support.microsoft.com/office/view-and-download-meeting-attendance-reports-in-teams-ae7cf170-530c-47d3-84c1-3aedac74d310?ui=en-US&#x26;rs=en-US&#x26;ad=US)」を参照してください。

## <a name="allow-users-to-schedule-webinars-using-powershell"></a>ユーザーが PowerShell を使用してウェビナーをスケジュールできるようにする

Windows PowerShell **Set-CsTeamsMeetingPolicy** コマンドレット内で次の属性を使用して、Teamsのウェビナー用に設定できます。

- AllowMeetingRegistration
- WhoCanRegister
- AllowPrivateMeetingScheduling

コマンドレットの詳細については、 [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy) を参照してください。

> [!NOTE]
> これらのコマンドレットを実行する前に、powerShell Microsoft Teamsに接続する必要があります。 詳細については、「[Microsoft Teams PowerShell を使用したTeamsの管理](/microsoftteams/teams-powershell-managing-teams)」を参照してください。

### <a name="allow-users-to-schedule-webinars"></a>ユーザーがウェビナーをスケジュールできるようにする

登録を組織内のユーザーのみに制限したり、テナント内と外部の両方のすべてのユーザーに開放したりできます。 既定では、**WhoCanRegister** が有効になっており、**グローバル (組織全体の既定)** ポリシーの **[すべてのユーザー**] に設定されます。 会議の登録を無効にする場合は、 **AllowMeetingRegistration** を False に設定 **します**。

> [!IMPORTANT]
> **AllowMeetingRegistration を機能させるには、AllowPrivateMeetingScheduling** を **True** に設定する必要があります。

1. 会議の登録を有効にする

```powershell
Set-CsTeamsMeetingPolicy -AllowMeetingRegistration $True
```

2. プライベート会議のスケジュール設定を有効にする

```powershell
Set-CsTeamsMeetingPolicy -AllowPrivateMeetingScheduling $True
```

3. ウェビナーに登録できるユーザーを構成する

**組織内のユーザー *のみが* ウェビナーに登録できるようにする**

```powershell
Set-CsTeamsMeetingPolicy -WhoCanRegister EveryoneInCompany
```

**匿名ユーザーを含むすべてのユーザーがウェビナーに登録できるようにするには、次のコマンドを実行します。**

```powershell
Set-CsTeamsMeetingPolicy -WhoCanRegister Everyone
```

> [!CAUTION]
> 会議の設定で匿名参加が無効になっている場合、匿名ユーザーはウェビナーに参加できません。 詳細を確認し、この設定を有効にするには、[Teamsの会議設定に](meeting-settings-in-teams.md)関するページを参照してください。

### <a name="collect-meeting-attendance"></a>会議出席を収集する

**AllowEngagementReport** パラメーターを使用すると、ウェビナーを登録して参加したユーザーを確認できます。 このポリシーは既定で有効になっています。 無効にするには、PowerShell で次のコマンドを実行します。

```powershell
Set-CsTeamsMeetingPolicy -AllowEngagementReport Disabled
```

## <a name="configure-webinar-settings"></a>ウェビナー設定を構成する

ウェビナー用に環境を有効にした後は、それ以上の管理者管理は必要ありません。 ポリシーは、ウェビナー開催者に表示されるオプションを制御します。

## <a name="related-topics"></a>関連項目

- [Teamsの会議ポリシー - 全般](meeting-policies-in-teams-general.md)
- [Set-CsTeamsMeetingPolicy のドキュメント](/powershell/module/skype/set-csteamsmeetingpolicy)
- [Microsoft Teams for Education ポリシー ウィザード](easy-policy-setup-edu.md)
