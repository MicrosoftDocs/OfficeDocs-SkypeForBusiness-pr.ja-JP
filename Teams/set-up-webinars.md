---
title: Microsoft Teams でのウェビナーのMicrosoft Teams
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
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: ''
ms.collection:
- M365-collaboration
- m365initiative-meetings
description: 会議のウェビナー ポリシーを管理するTeamsします。
ms.openlocfilehash: bc1460f93259a9dd3095cf764c38b56ab703bba0
ms.sourcegitcommit: 592e5a0638c7739dfaa3565b67d4edc621eebc9f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/26/2021
ms.locfileid: "52656050"
---
# <a name="set-up-for-webinars-in-microsoft-teams"></a>Microsoft Teams でのウェビナーのMicrosoft Teams

この記事は、ウェビナーをホストする組織を設定する場合に役立ちます。

## <a name="what-are-webinars"></a>ウェビナーとは

ウェビナーは、講師と参加者が明確な役割を持つ構造化された会議です。多くの場合、トレーニング目的や販売およびマーケティングリード生成シナリオに使用されます。

組織内でウェビナーを設定した後、ユーザーはウェビナーのスケジュールを設定し、出席者に登録を開きます。 多くのディスカッションやタスクの割り当てを含む従来の会議とは異なり、ウェビナーは対話型のプレゼンテーション用であり、出席者分析用のツールを提供します。

## <a name="allow-users-to-schedule-webinars-using-powershell"></a>ユーザーが PowerShell を使用してウェビナーのスケジュールを設定できる

**Set-CsTeamsMeetingPolicy** コマンドレット内でWindows PowerShell属性を使用して、Teams のウェビナー用に設定できます。

- AllowMeetingRegistration
- WhoCanRegister
- AllowPrivateMeetingScheduling

コマンドレット [の詳細については、「Set-CsTeamsMeetingPolicy」](/powershell/module/skype/set-csteamsmeetingpolicy) を参照してください。

> [!NOTE]
> これらのコマンドレットを実行する前に、オンライン PowerShell Skype for Business接続する必要があります。 詳細については、「Manage Skype for Business Online with Microsoft 365 または Office 365 [PowerShell 」を参照してください](/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)。

### <a name="allow-users-to-schedule-webinars"></a>ユーザーにウェビナーのスケジュールを設定する

組織内のユーザーがウェビナーのスケジュールを設定するには、次のコマンドを実行します。

```powershell
Set-CsTeamsMeetingPolicy -AllowMeetingRegistration True
```
### <a name="configure-who-can-register-for-webinars"></a>ウェビナーに登録できるユーザーを構成する

登録を組織内のユーザーにのみ制限したり、テナントの内部と外部の両方のすべてのユーザーに登録を開くことができます。 既定では **、WhoCanRegister は** 有効であり、[すべてのユーザー] に **設定されています**。 会議の登録をオフにする場合は **、AllowMeetingRegistration** を False に **設定します**。

> [!IMPORTANT]
> **AllowMeetingRegistration** を機能するには **、AllowPrivateMeetingScheduling** を **True** に設定する必要があります。 また、Microsoft リストは、SharePoint で設定する必要SharePoint。 詳細については、「Microsoft リストの [コントロール設定」を参照してください](/sharepoint/control-lists)。

**組織内の *ユーザーにのみ* ウェビナーへの登録を許可するには、次のコマンドを実行します。**

```powershell
Set-CsTeamsMeetingPolicy -AllowPrivateMeetingScheduling True
```

次に、次のコマンドを実行します。

```powershell
Set-CsTeamsMeetingPolicy -WhoCanRegister EveryoneInCompany
```

**匿名ユーザーを含むすべてのユーザーがウェビナーに登録するには、次のコマンドを実行します。**

```powershell
Set-CsTeamsMeetingPolicy -AllowPrivateMeetingScheduling True
```

次に、次のコマンドを実行します。

```powershell
Set-CsTeamsMeetingPolicy -WhoCanRegister Everyone
```

> [!IMPORTANT]
> 会議の設定で匿名参加がオフになっている場合、匿名ユーザーはウェビナーに参加できます。 詳細とこの設定を有効にするには、「会議の設定」を参照[Teams。](meeting-settings-in-teams.md)

### <a name="collect-meeting-attendance"></a>会議出席を収集する

開催者にウェビナーの登録者と参加したユーザーを分析する場合は **、AllowEngagementReport** ポリシーを有効にする必要があります。 これを行うには、PowerShell で次のコマンドを実行します。

```powershell
Set-CsTeamsMeetingPolicy -AllowEngagementReport Enabled
```

### <a name="configure-webinar-settings"></a>ウェビナー設定を構成する

ウェビナー用に環境を有効にした後は、それ以上の管理者管理は必要ありません。 ポリシーは、ウェビナー開催者に表示されるオプションを制御します。

## <a name="related-topics"></a>関連項目

- [Teams の会議ポリシー - 全般](meeting-policies-in-teams-general.md)
- [Set-CsTeamsMeetingPolicy のドキュメント](/powershell/module/skype/set-csteamsmeetingpolicy)
