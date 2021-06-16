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
ms.openlocfilehash: 14452b0caeee33f90b59f6581b6fccf4d5e0311b
ms.sourcegitcommit: 4a039550bc5c3a497b6b52c7fed08cadf8268b06
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/14/2021
ms.locfileid: "52926749"
---
# <a name="set-up-for-webinars-in-microsoft-teams"></a><span data-ttu-id="0e033-103">Microsoft Teams でのウェビナーのMicrosoft Teams</span><span class="sxs-lookup"><span data-stu-id="0e033-103">Set up for webinars in Microsoft Teams</span></span>

<span data-ttu-id="0e033-104">この記事は、ウェビナーをホストする組織を設定する場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="0e033-104">This article will help you set up your organization to host webinars.</span></span>

## <a name="what-are-webinars"></a><span data-ttu-id="0e033-105">ウェビナーとは</span><span class="sxs-lookup"><span data-stu-id="0e033-105">What are webinars?</span></span>

<span data-ttu-id="0e033-106">ウェビナーは、発表者と参加者が明確な役割を持つ構造化された会議です。多くの場合、トレーニング目的や販売およびマーケティングリード生成シナリオに使用されます。</span><span class="sxs-lookup"><span data-stu-id="0e033-106">Webinars are structured meetings where presenters and participants have clear roles, often used for training purposes or sales and marketing lead generation scenarios.</span></span>

<span data-ttu-id="0e033-107">組織内でウェビナーを設定した後、ユーザーはウェビナーのスケジュールを設定し、出席者に登録を開きます。</span><span class="sxs-lookup"><span data-stu-id="0e033-107">After setting up webinars in your organization, your users can schedule webinars and open registration to attendees.</span></span> <span data-ttu-id="0e033-108">多くのディスカッションやタスクの割り当てを含む従来の会議とは異なり、ウェビナーは対話型のプレゼンテーション用であり、出席者分析用のツールを提供します。</span><span class="sxs-lookup"><span data-stu-id="0e033-108">Unlike traditional meetings that include many discussions and task assignment, webinars are meant for interactive presentations and provide tools for attendee analysis.</span></span>

## <a name="allow-users-to-schedule-webinars-using-powershell"></a><span data-ttu-id="0e033-109">ユーザーが PowerShell を使用してウェビナーのスケジュールを設定できる</span><span class="sxs-lookup"><span data-stu-id="0e033-109">Allow users to schedule webinars using PowerShell</span></span>

<span data-ttu-id="0e033-110">**Set-CsTeamsMeetingPolicy** コマンドレット内でWindows PowerShell属性を使用して、Teams のウェビナー用に設定できます。</span><span class="sxs-lookup"><span data-stu-id="0e033-110">You can use the following attributes within the Windows PowerShell **Set-CsTeamsMeetingPolicy** cmdlet to set up for webinars in Teams.</span></span>

- <span data-ttu-id="0e033-111">AllowMeetingRegistration</span><span class="sxs-lookup"><span data-stu-id="0e033-111">AllowMeetingRegistration</span></span>
- <span data-ttu-id="0e033-112">WhoCanRegister</span><span class="sxs-lookup"><span data-stu-id="0e033-112">WhoCanRegister</span></span>
- <span data-ttu-id="0e033-113">AllowPrivateMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="0e033-113">AllowPrivateMeetingScheduling</span></span>

<span data-ttu-id="0e033-114">コマンドレット [の詳細については、「Set-CsTeamsMeetingPolicy」](/powershell/module/skype/set-csteamsmeetingpolicy) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0e033-114">Read [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy) for more information on the cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="0e033-115">これらのコマンドレットを実行する前に、PowerShell を使用して Microsoft Teamsする必要があります。</span><span class="sxs-lookup"><span data-stu-id="0e033-115">Before you can run these cmdlets you must be connected to Microsoft Teams PowerShell.</span></span> <span data-ttu-id="0e033-116">詳細については[、「PowerShell を使用してTeams管理Microsoft Teams参照してください](/microsoftteams/teams-powershell-managing-teams)。</span><span class="sxs-lookup"><span data-stu-id="0e033-116">For more information, see [Manage Teams with Microsoft Teams PowerShell](/microsoftteams/teams-powershell-managing-teams).</span></span>

### <a name="allow-users-to-schedule-webinars"></a><span data-ttu-id="0e033-117">ユーザーにウェビナーのスケジュールを設定する</span><span class="sxs-lookup"><span data-stu-id="0e033-117">Allow users to schedule webinars</span></span>

<span data-ttu-id="0e033-118">登録を組織内のユーザーにのみ制限したり、テナントの内部と外部の両方のすべてのユーザーに登録を開くことができます。</span><span class="sxs-lookup"><span data-stu-id="0e033-118">You can restrict registration to users only in your organization or open it up to everyone both inside and outside your tenant.</span></span> <span data-ttu-id="0e033-119">既定では **、WhoCanRegister は** 有効であり、[すべてのユーザー] に **設定されています**。</span><span class="sxs-lookup"><span data-stu-id="0e033-119">By default, **WhoCanRegister** is enabled and set to **Everyone**.</span></span> <span data-ttu-id="0e033-120">会議の登録をオフにする場合は **、AllowMeetingRegistration** を False に **設定します**。</span><span class="sxs-lookup"><span data-stu-id="0e033-120">If you want to turn off meeting registration, set **AllowMeetingRegistration** to **False**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0e033-121">**AllowMeetingRegistration を機能するには、AllowPrivateMeetingScheduling** を **True** に設定 **する** 必要があります。</span><span class="sxs-lookup"><span data-stu-id="0e033-121">**AllowPrivateMeetingScheduling** must be set to **True** for **AllowMeetingRegistration** to work.</span></span> <span data-ttu-id="0e033-122">また、Microsoft リストは、SharePoint で設定する必要SharePoint。</span><span class="sxs-lookup"><span data-stu-id="0e033-122">Additionally, Microsoft Lists needs to be set up in SharePoint.</span></span> <span data-ttu-id="0e033-123">詳細については、「Microsoft リストの [コントロール設定」を参照してください](/sharepoint/control-lists)。</span><span class="sxs-lookup"><span data-stu-id="0e033-123">To learn more, see [Control settings for Microsoft Lists](/sharepoint/control-lists).</span></span>

1. <span data-ttu-id="0e033-124">会議の登録を有効にする</span><span class="sxs-lookup"><span data-stu-id="0e033-124">Turn on meeting registration</span></span>

```powershell
Set-CsTeamsMeetingPolicy -AllowMeetingRegistration $True
```

2. <span data-ttu-id="0e033-125">プライベート会議のスケジュールを有効にする</span><span class="sxs-lookup"><span data-stu-id="0e033-125">Turn on private meeting scheduling</span></span>

```powershell
Set-CsTeamsMeetingPolicy -AllowPrivateMeetingScheduling $True
```

3. <span data-ttu-id="0e033-126">ウェビナーに登録できるユーザーを構成する</span><span class="sxs-lookup"><span data-stu-id="0e033-126">Configure who can register for webinars</span></span>

<span data-ttu-id="0e033-127">**組織内 *の* ユーザーにのみウェビナーへの登録を許可する**</span><span class="sxs-lookup"><span data-stu-id="0e033-127">**Allow *only* users in your organization to register for webinars**</span></span>

```powershell
Set-CsTeamsMeetingPolicy -WhoCanRegister EveryoneInCompany
```

<span data-ttu-id="0e033-128">**匿名ユーザーを含むすべてのユーザーがウェビナーに登録するには、次のコマンドを実行します。**</span><span class="sxs-lookup"><span data-stu-id="0e033-128">**To allow anyone, including anonymous users, to register for webinars, run:**</span></span>

```powershell
Set-CsTeamsMeetingPolicy -WhoCanRegister Everyone
```

> [!CAUTION]
> <span data-ttu-id="0e033-129">会議の設定で匿名参加がオフになっている場合、匿名ユーザーはウェビナーに参加できます。</span><span class="sxs-lookup"><span data-stu-id="0e033-129">If anonymous join is turned off in meeting settings, anonymous users can't join webinars.</span></span> <span data-ttu-id="0e033-130">詳細とこの設定を有効にするには、「会議の設定」を参照[Teams。](meeting-settings-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="0e033-130">To learn more and enable this setting, see [Meeting settings in Teams](meeting-settings-in-teams.md).</span></span>

### <a name="collect-meeting-attendance"></a><span data-ttu-id="0e033-131">会議出席を収集する</span><span class="sxs-lookup"><span data-stu-id="0e033-131">Collect meeting attendance</span></span>

<span data-ttu-id="0e033-132">開催者にウェビナーの登録者と参加したユーザーを分析する場合は **、AllowEngagementReport** ポリシーを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="0e033-132">If you want organizers to analyze who registered and attended webinars, you'll need to turn on the **AllowEngagementReport** policy.</span></span> <span data-ttu-id="0e033-133">これを行うには、PowerShell で次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="0e033-133">To do this, run the following command in PowerShell.</span></span>

```powershell
Set-CsTeamsMeetingPolicy -AllowEngagementReport Enabled
```

### <a name="configure-webinar-settings"></a><span data-ttu-id="0e033-134">ウェビナー設定を構成する</span><span class="sxs-lookup"><span data-stu-id="0e033-134">Configure webinar settings</span></span>

<span data-ttu-id="0e033-135">ウェビナー用に環境を有効にした後は、それ以上の管理者管理は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="0e033-135">After enabling your environment for webinars, no further admin management is required.</span></span> <span data-ttu-id="0e033-136">ポリシーは、ウェビナー開催者に表示されるオプションを制御します。</span><span class="sxs-lookup"><span data-stu-id="0e033-136">The policy controls which options show up for webinar organizers.</span></span>

## <a name="related-topics"></a><span data-ttu-id="0e033-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="0e033-137">Related topics</span></span>

- [<span data-ttu-id="0e033-138">Teams の会議ポリシー - 全般</span><span class="sxs-lookup"><span data-stu-id="0e033-138">Meeting policies in Teams - General</span></span>](meeting-policies-in-teams-general.md)
- [<span data-ttu-id="0e033-139">Set-CsTeamsMeetingPolicy のドキュメント</span><span class="sxs-lookup"><span data-stu-id="0e033-139">Set-CsTeamsMeetingPolicy documentation</span></span>](/powershell/module/skype/set-csteamsmeetingpolicy)
