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
description: 会議に使用するウェビナー ポリシーを管理Teamsします。
ms.openlocfilehash: 5536a6c03df15be349edea7d980932b5fc0173ab
ms.sourcegitcommit: faeb8976299375e7658499ff31d25e8ef6003144
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2022
ms.locfileid: "62224004"
---
# <a name="set-up-for-webinars-in-microsoft-teams"></a>Microsoft Teams でのウェビナーのセットアップ

この記事は、ウェビナーをホストする組織を設定する場合に役立ちます。

## <a name="what-are-webinars"></a>ウェビナーとは

ウェビナーは、発表者と参加者が明確な役割を持つ構造化された会議です。多くの場合、トレーニング目的や販売およびマーケティングリード生成シナリオに使用されます。

組織内でウェビナーを設定した後、ユーザーはウェビナーのスケジュールを設定し、出席者に登録を開きます。 多くのディスカッションやタスクの割り当てを含む従来の会議とは異なり、ウェビナーは対話型のプレゼンテーション用であり、出席者分析用のツールを提供します。

> [!IMPORTANT]
> ユーザーがウェビナーを設定Microsoft Lists個人用リストを作成SharePointで構成する必要があります。 詳細については、「コントロールの設定[」を参照Microsoft Lists。](/sharepoint/control-lists)

## <a name="allow-users-to-schedule-webinars-in-the-teams-admin-center"></a>ユーザーが管理センターでウェビナーをTeams許可する

組織のウェビナー Teams管理センターを使用して設定できます。 ウェビナーを設定するポリシーは、Teams 会議ポリシー **に**  >  **表示されます**。

### <a name="meeting-registration"></a>会議の登録

これを有効にした場合、ユーザーはウェビナーのスケジュールを設定できます。 既定では、この設定はオンになっています。 会議の登録をオフにする場合は、このポリシーを [オフ] に **設定します**。

> [!IMPORTANT]
> **会議の登録を機能** するには、プライベート会議のスケジュールをオンにする必要があります。 既定では、このポリシーは管理センター Teamsオンになっています。 教育テナントの学生の場合、このポリシーは既定で無効になっています。 学生のプライベート会議のスケジュール設定を有効にする方法の詳細については、「Microsoft Teams for Education ポリシーとポリシー パッケージ[」を参照してください](policy-packages-edu.md)。

### <a name="who-can-register"></a>Who登録可能

[すべてのユーザー] **を選択** すると、匿名ユーザーを含むすべてのユーザーがウェビナーに登録し、ウェビナーに参加できます。 [組織内のすべての **ユーザー] を選択した場合** は、組織内のユーザーだけがウェビナーに登録できます。 会議の登録が無効になっている場合、このオプションは使用できません。また、ウェビナーに登録できるユーザーはいます。

> [!NOTE]
> 登録できるユーザーの **Whoは、Education** **テナントの組織内のすべての** ユーザーです。 詳細については、ポリシー ウィザードのMicrosoft Teams for Education[を参照してください](easy-policy-setup-edu.md)。

### <a name="engagement-report"></a>エンゲージメント レポート

オンの場合、開催者は、設定したウェビナーに誰が登録し、参加したのかのレポートを確認できます。 このポリシーは既定でオンになっています。 詳細については、「会議 - 契約[レポートの会議ポリシー」Teamsを参照してください](meeting-policies-in-teams-general.md#engagement-report)。 エンド ユーザー エクスペリエンスの詳細については、「会議出席レポートを表示 [およびダウンロードする」を参照してください](https://support.microsoft.com/office/view-and-download-meeting-attendance-reports-in-teams-ae7cf170-530c-47d3-84c1-3aedac74d310?ui=en-US&#x26;rs=en-US&#x26;ad=US)。

## <a name="allow-users-to-schedule-webinars-using-powershell"></a>ユーザーが PowerShell を使用してウェビナーのスケジュールを設定できる

**Set-CsTeamsMeetingPolicy** コマンドレット内でWindows PowerShell属性を使用して、Teams のウェビナー用に設定できます。

- AllowMeetingRegistration
- WhoCanRegister
- AllowPrivateMeetingScheduling

コマンドレット [の詳細については、「Set-CsTeamsMeetingPolicy」](/powershell/module/skype/set-csteamsmeetingpolicy) を参照してください。

> [!NOTE]
> これらのコマンドレットを実行する前に、PowerShell を使用して Microsoft Teamsする必要があります。 詳細については[、「PowerShell を使用したTeams管理Microsoft Teams参照してください](/microsoftteams/teams-powershell-managing-teams)。

### <a name="allow-users-to-schedule-webinars"></a>ユーザーにウェビナーのスケジュールを設定する

登録を組織内のユーザーにのみ制限したり、テナントの内部と外部の両方のすべてのユーザーに登録を開くことができます。 既定では **、WhoCanRegister は** 有効であり、グローバル (組織全体の既定) ポリシーの [すべてのユーザー **] に設定** されます。 会議の登録をオフにする場合は **、AllowMeetingRegistration** を False に **設定します**。

> [!IMPORTANT]
> **AllowMeetingRegistration を機能するには、AllowPrivateMeetingScheduling** を **True** に設定 **する** 必要があります。

1. 会議の登録を有効にする

```powershell
Set-CsTeamsMeetingPolicy -AllowMeetingRegistration $True
```

2. プライベート会議のスケジュールを有効にする

```powershell
Set-CsTeamsMeetingPolicy -AllowPrivateMeetingScheduling $True
```

3. ウェビナーに登録できるユーザーを構成する

**組織内 *の* ユーザーにのみウェビナーへの登録を許可する**

```powershell
Set-CsTeamsMeetingPolicy -WhoCanRegister EveryoneInCompany
```

**匿名ユーザーを含むすべてのユーザーがウェビナーに登録するには、次のコマンドを実行します。**

```powershell
Set-CsTeamsMeetingPolicy -WhoCanRegister Everyone
```

> [!CAUTION]
> 会議の設定で匿名参加がオフになっている場合、匿名ユーザーはウェビナーに参加できます。 詳細とこの設定を有効にするには、「会議の設定」を参照[Teams。](meeting-settings-in-teams.md)

### <a name="collect-meeting-attendance"></a>会議出席を収集する

**AllowEngagementReport パラメーターを** 使用すると、ウェビナーの登録者と参加したユーザーを確認できます。 このポリシーは既定で有効になっています。 オフにするには、PowerShell で次のコマンドを実行します。

```powershell
Set-CsTeamsMeetingPolicy -AllowEngagementReport Disabled
```

## <a name="configure-webinar-settings"></a>ウェビナー設定を構成する

ウェビナー用に環境を有効にした後は、それ以上の管理者管理は必要ありません。 ポリシーは、ウェビナー開催者に表示されるオプションを制御します。

## <a name="related-topics"></a>関連トピック

- [Teams の会議ポリシー - 全般](meeting-policies-in-teams-general.md)
- [Set-CsTeamsMeetingPolicy のドキュメント](/powershell/module/skype/set-csteamsmeetingpolicy)
- [Microsoft Teams for Education ポリシー ウィザード](easy-policy-setup-edu.md)
