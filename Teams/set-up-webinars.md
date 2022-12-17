---
title: ウェビナーを設定する
ms.author: mabond
author: mkbond007
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
- highpri
description: Teams でウェビナーと会議の登録ポリシーを管理する方法について説明します。
ms.openlocfilehash: 5493104b93a74dad6763e0a5ba6c9e6fd57575de
ms.sourcegitcommit: b710fc61558a0e031d4e3e4000f234c495e2c4c6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2022
ms.locfileid: "69438475"
---
# <a name="set-up-webinars-in-microsoft-teams"></a>Microsoft Teams でウェビナーを設定する

> [!NOTE]
> この記事では、プレビュー段階であり、Teams Premium ライセンスが必要となるウェビナーの一部の機能について説明します。

Microsoft新しいウェビナー エクスペリエンスが提供されるようになりました。この記事では、これらの機能を使用するように設定を更新する方法について説明します。

ウェビナーを使用する予定の場合は、新しいウェビナー エクスペリエンスを使用することをお勧めします。

会議の登録には、基本的なウェビナー機能、会議の登録を要求する機能、出席レポートが含まれます。 新しいウェビナー エクスペリエンスを有効にすると、会議登録や次のような多くの新しいウェビナー機能を使用できます。

- ウェビナーの専用イベントと登録ページ
- 共同開催者
- イベント ページの発表者 bios
- 登録状態の概要と管理

エンド ユーザーが利用できる新機能の詳細については、「Teams の [概要」ウェビナーを参照してください](https://support.microsoft.com/office/42f3f874-22dc-4289-b53f-bbc1a69013e3)。

組織で会議登録が有効になっている場合、新しく作成されたすべてのウェビナーに新しいエクスペリエンスが追加されます。 以前にスケジュールされたウェビナーでは、以前のウェビナー エクスペリエンスを使用します。 新しいエクスペリエンスでは、TeamsEventsPolicy が使用されます。 ウェビナーをオフにしている場合は、新しいエクスペリエンスがロールアウトされてもオフのままです。

現時点では、基本的なウェビナー エクスペリエンスは、Teams 会議ポリシー (Set-CsTeamsMeetingPolicy) を使用した会議登録によって制御されます。 今後、会議登録設定はウェビナーを制御しません。ウェビナーは、Teams イベント ポリシー (Set-CsTeamsEventsPolicy) によって制御されるように移行しています。

新しいウェビナー エクスペリエンスは PowerShell で構成されています。 [新しいウェビナー エクスペリエンスを設定する方法の例を](#set-up-new-webinar-experience)参照してください。

会議、ウェビナー、ライブ イベントの違いの詳細については、「 [会議、ウェビナー、ライブ イベント](quick-start-meetings-live-events.md)」を参照してください。

> [!NOTE]
> 新しいウェビナー エクスペリエンスは、Microsoft 365 GCC、Microsoft 365 GCC High、または Microsoft 365 DoD では使用できません。 既存のウェビナー エクスペリエンスは、Microsoft 365 GCC High または Microsoft 365 DoD では使用できません。

> [!IMPORTANT]
> ユーザーがウェビナーを設定できるようにするには、Microsoft Lists電子情報開示のために個人用リストの作成を有効にして SharePoint で構成する必要があります。 詳細については、「[Microsoft Listsの制御設定](/sharepoint/control-lists)」を参照してください。

## <a name="set-up-new-webinar-experience"></a>新しいウェビナー エクスペリエンスを設定する

PowerShell を使用して、組織の新しいウェビナー エクスペリエンスを設定する必要があります。 Teams 管理センターで新しいウェビナー エクスペリエンスを構成する機能はまだ利用できません。

新しいウェビナー エクスペリエンスを使用するには、会議の登録がオンである必要があります。

### <a name="configure-the-new-webinar-experience-with-powershell"></a>PowerShell で新しいウェビナー エクスペリエンスを構成する

新しいウェビナー エクスペリエンスを設定するには、**Windows PowerShell Set-CsTeamsEventsPolicy** コマンドレット内で次の属性を使用します。

|パラメーター|既定の設定|説明|
|---------|-----------|---------------|
|AllowWebinars|有効|この設定は、ユーザーがウェビナーを作成できるかどうかを決定します。|
|EventAccessType|すべてのユーザー|この設定は、登録するイベント登録ページまたはイベント サイトにアクセスできるユーザーと、イベントでセッションに参加できるユーザーの種類を決定します。|

これらのコマンドレットを実行するには、Teams PowerShell に接続Microsoft必要があります。 詳細については、「[Microsoft Teams PowerShell を使用した Teams の管理](/microsoftteams/teams-powershell-managing-teams)」を参照してください。

1. 会議の登録を有効にします。

    ```powershell
    Set-CsTeamsMeetingPolicy -Identity <policy name> -AllowMeetingRegistration $True
    ```

1. 新しいウェビナー エクスペリエンスをアクティブ化します。

    ```powershell
    Set-CsTeamsEventsPolicy -Identity <policy name> -AllowWebinars Enabled
    ```

1. ウェビナーや会議に登録できるユーザーを構成します。

    - **組織内の **_only_* _ ユーザーにウェビナーとmeetings_への登録を許可する*

        ```powershell
        Set-CsTeamsEventsPolicy -Identity <policy name> -EventAccessType EveryoneInCompanyExcludingGuests
        ```

    - **匿名ユーザーを含むすべてのユーザーにウェビナーや会議への登録を許可する**

        ```powershell
        Set-CsTeamsEventsPolicy -Identity <policy name> -EventAccessType Everyone
        ```

> [!IMPORTANT]
> [会議 **の設定****] で匿名ユーザーが会議に参加できる** 場合、匿名ユーザーはウェビナーに参加できません。 詳細を確認し、この設定を有効にするには、「 [Teams での会議の設定](meeting-settings-in-teams.md)」を参照してください。

## <a name="configure-meeting-registration"></a>会議の登録を構成する

ウェビナーを使用する場合は、会議の登録を有効にする必要があります。

会議 **会議ポリシー****の下** > にある Teams 管理センターを使用して、会議の登録とウェビナーを設定できます。

### <a name="meeting-registration"></a>会議の登録

**会議の登録** を有効にした場合、組織内のユーザーは、登録を必要とするウェビナーや会議をスケジュールできます。 既定では、これはオンになっています。 会議の登録とウェビナーをオフにする場合は、このポリシーを **[オフ]** に設定します。

**会議の登録を** 機能させるには、プライベート会議のスケジュール設定がオンである必要があります。 [プライベート会議のスケジュール設定](meeting-policies-in-teams-general.md)の詳細をご覧ください。

教育テナントの学生の場合、このポリシーは既定でオフになっています。 学生のプライベート会議スケジュールを有効にする方法の詳細については、「[Microsoft Teams for Education ポリシーとポリシー パッケージ](policy-packages-edu.md)」を参照してください。

#### <a name="who-can-register"></a>登録できるユーザー

> [!NOTE]
> このポリシーは、新しいウェビナー エクスペリエンスには適用されません。 新しいウェビナー エクスペリエンスに登録できるユーザーを構成するには、「[PowerShell で新しいウェビナー エクスペリエンスを構成する](#configure-the-new-webinar-experience-with-powershell)」に示すように、 を使用`Set-CsTeamsEventsPolicy -EventAccessType`します。

このポリシーは、会議登録のみでウェビナーを登録および参加できるユーザーを制御します。 このポリシーには、**[会議の登録]** が有効になっている場合にのみ使用できる 2 つのオプションがあります。 既定では、**[登録できるユーザー]** は **[すべてのユーザー]** に設定されています。

[ **すべてのユーザー**] を選択すると、匿名ユーザーを含むすべてのユーザーがウェビナーに登録して参加できます。 **[組織内のすべてのユーザー**] を選択すると、組織内のユーザーのみがウェビナーに登録して参加できます。 会議の登録がオフになっている場合、[ **登録できるユーザー** ] 設定は使用できません。ウェビナーに登録することはできません。

[ **登録できるユーザー** ] の既定値は、教育機関テナント **の組織内のすべてのユーザー** です。 詳細については、「[Microsoft Teams for Education ポリシー ウィザード](easy-policy-setup-edu.md)」を参照してください。

## <a name="collect-webinar-and-meeting-registration-attendance"></a>ウェビナーと会議の登録出席を収集する

**会議** > **会議ポリシー** の下にある Teams 管理センターを使用して、**エンゲージメント レポート** を有効にすることができます。

オンにすると、開催者は、設定したウェビナーまたは会議に登録して出席したユーザーのレポートを表示できます。 このポリシーは既定でオンになっています。 詳細については、「 [Teams の会議ポリシー - エンゲージメント レポート](meeting-policies-in-teams-general.md#engagement-report)」を参照してください。 エンド ユーザー エクスペリエンスの詳細については、「 [会議出席レポートの表示とダウンロード](https://support.microsoft.com/office/ae7cf170-530c-47d3-84c1-3aedac74d310)」を参照してください。

PowerShell では、 **AllowEngagementReport** パラメーターを使用してこれを有効にすることができます。 このポリシーは既定でオンになっています。 無効にするには、PowerShell で次のコマンドを実行します。

```powershell
Set-CsTeamsMeetingPolicy -Identity <policy name> -AllowEngagementReport Disabled
```

コマンドレットの詳細については、「 [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy) 」を参照してください。

## <a name="turn-off-webinars"></a>ウェビナーをオフにする

PowerShell を使用してウェビナーをオフにすることができます。 これにより、新しいウェビナー エクスペリエンスと、会議登録のみのウェビナーがオフになります。

ウェビナーをオフにするには、次の PowerShell スクリプトを使用します。

```powershell
Set-CsTeamsMeetingPolicy -Identity <policy name> -AllowMeetingRegistration $False
Set-CSTeamsEventsPolicy -Identity <policy name> -AllowWebinars Disabled
```

## <a name="related-topics"></a>関連項目

- [Teams の会議ポリシー - 全般](meeting-policies-in-teams-general.md)
- [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)
- [Set-CsTeamsEventsPolicy](/powershell/module/teams/set-csteamseventspolicy)
