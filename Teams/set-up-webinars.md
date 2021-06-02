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
ms.openlocfilehash: aafa7b57eea1228fa5565bb4d5e95304b42751a3
ms.sourcegitcommit: 90615674e9703aa5ea32be64ab3638aa30e83127
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/02/2021
ms.locfileid: "52718048"
---
# <a name="set-up-for-webinars-in-microsoft-teams"></a><span data-ttu-id="b9837-103">Microsoft Teams でのウェビナーのMicrosoft Teams</span><span class="sxs-lookup"><span data-stu-id="b9837-103">Set up for webinars in Microsoft Teams</span></span>

<span data-ttu-id="b9837-104">この記事は、ウェビナーをホストする組織を設定する場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="b9837-104">This article will help you set up your organization to host webinars.</span></span>

## <a name="what-are-webinars"></a><span data-ttu-id="b9837-105">ウェビナーとは</span><span class="sxs-lookup"><span data-stu-id="b9837-105">What are webinars?</span></span>

<span data-ttu-id="b9837-106">ウェビナーは、講師と参加者が明確な役割を持つ構造化された会議です。多くの場合、トレーニング目的や販売およびマーケティングリード生成シナリオに使用されます。</span><span class="sxs-lookup"><span data-stu-id="b9837-106">Webinars are structured meetings where instructors and participants have clear roles, often used for training purposes or sales and marketing lead generation scenarios.</span></span>

<span data-ttu-id="b9837-107">組織内でウェビナーを設定した後、ユーザーはウェビナーのスケジュールを設定し、出席者に登録を開きます。</span><span class="sxs-lookup"><span data-stu-id="b9837-107">After setting up webinars in your organization, your users can schedule webinars and open registration to attendees.</span></span> <span data-ttu-id="b9837-108">多くのディスカッションやタスクの割り当てを含む従来の会議とは異なり、ウェビナーは対話型のプレゼンテーション用であり、出席者分析用のツールを提供します。</span><span class="sxs-lookup"><span data-stu-id="b9837-108">Unlike traditional meetings that include many discussions and task assignment, webinars are meant for interactive presentations and provide tools for attendee analysis.</span></span>

## <a name="allow-users-to-schedule-webinars-using-powershell"></a><span data-ttu-id="b9837-109">ユーザーが PowerShell を使用してウェビナーのスケジュールを設定できる</span><span class="sxs-lookup"><span data-stu-id="b9837-109">Allow users to schedule webinars using PowerShell</span></span>

<span data-ttu-id="b9837-110">**Set-CsTeamsMeetingPolicy** コマンドレット内でWindows PowerShell属性を使用して、Teams のウェビナー用に設定できます。</span><span class="sxs-lookup"><span data-stu-id="b9837-110">You can use the following attributes within the Windows PowerShell **Set-CsTeamsMeetingPolicy** cmdlet to set up for webinars in Teams.</span></span>

- <span data-ttu-id="b9837-111">AllowMeetingRegistration</span><span class="sxs-lookup"><span data-stu-id="b9837-111">AllowMeetingRegistration</span></span>
- <span data-ttu-id="b9837-112">WhoCanRegister</span><span class="sxs-lookup"><span data-stu-id="b9837-112">WhoCanRegister</span></span>
- <span data-ttu-id="b9837-113">AllowPrivateMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="b9837-113">AllowPrivateMeetingScheduling</span></span>

<span data-ttu-id="b9837-114">コマンドレット [の詳細については、「Set-CsTeamsMeetingPolicy」](/powershell/module/skype/set-csteamsmeetingpolicy) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b9837-114">Read [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy) for more information on the cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="b9837-115">これらのコマンドレットを実行する前に、オンライン PowerShell Skype for Business接続する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b9837-115">Before you can run these cmdlets you must be connected to Skype for Business Online PowerShell.</span></span> <span data-ttu-id="b9837-116">詳細については、「Manage Skype for Business Online with Microsoft 365 または Office 365 [PowerShell 」を参照してください](/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)。</span><span class="sxs-lookup"><span data-stu-id="b9837-116">For more information, see [Manage Skype for Business Online with Microsoft 365 or Office 365 PowerShell](/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).</span></span>

### <a name="allow-users-to-schedule-webinars"></a><span data-ttu-id="b9837-117">ユーザーにウェビナーのスケジュールを設定する</span><span class="sxs-lookup"><span data-stu-id="b9837-117">Allow users to schedule webinars</span></span>

<span data-ttu-id="b9837-118">組織内のユーザーがウェビナーのスケジュールを設定するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="b9837-118">To allow users in your organization to schedule webinars, run:</span></span>

```powershell
Set-CsTeamsMeetingPolicy -AllowMeetingRegistration $True
```
### <a name="configure-who-can-register-for-webinars"></a><span data-ttu-id="b9837-119">ウェビナーに登録できるユーザーを構成する</span><span class="sxs-lookup"><span data-stu-id="b9837-119">Configure who can register for webinars</span></span>

<span data-ttu-id="b9837-120">登録を組織内のユーザーにのみ制限したり、テナントの内部と外部の両方のすべてのユーザーに登録を開くことができます。</span><span class="sxs-lookup"><span data-stu-id="b9837-120">You can restrict registration to users only in your organization or open it up to everyone both inside and outside your tenant.</span></span> <span data-ttu-id="b9837-121">既定では **、WhoCanRegister は** 有効であり、[すべてのユーザー] に **設定されています**。</span><span class="sxs-lookup"><span data-stu-id="b9837-121">By default, **WhoCanRegister** is enabled and set to **Everyone**.</span></span> <span data-ttu-id="b9837-122">会議の登録をオフにする場合は **、AllowMeetingRegistration** を False に **設定します**。</span><span class="sxs-lookup"><span data-stu-id="b9837-122">If you want to turn off meeting registration, set **AllowMeetingRegistration** to **False**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b9837-123">**AllowMeetingRegistration** を機能するには **、AllowPrivateMeetingScheduling** を **True** に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b9837-123">Keep in mind that **AllowPrivateMeetingScheduling** must be set to **True** for **AllowMeetingRegistration** to work.</span></span> <span data-ttu-id="b9837-124">また、Microsoft リストは、SharePoint で設定する必要SharePoint。</span><span class="sxs-lookup"><span data-stu-id="b9837-124">Additionally, Microsoft Lists needs to be set up in SharePoint.</span></span> <span data-ttu-id="b9837-125">詳細については、「Microsoft リストの [コントロール設定」を参照してください](/sharepoint/control-lists)。</span><span class="sxs-lookup"><span data-stu-id="b9837-125">To learn more, see [Control settings for Microsoft Lists](/sharepoint/control-lists).</span></span>

<span data-ttu-id="b9837-126">**組織内の *ユーザーにのみ* ウェビナーへの登録を許可するには、次のコマンドを実行します。**</span><span class="sxs-lookup"><span data-stu-id="b9837-126">**To allow *only* users in your organization to register for webinars, run:**</span></span>

```powershell
Set-CsTeamsMeetingPolicy -AllowPrivateMeetingScheduling $True
```

<span data-ttu-id="b9837-127">次に、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="b9837-127">Then, run:</span></span>

```powershell
Set-CsTeamsMeetingPolicy -WhoCanRegister EveryoneInCompany
```

<span data-ttu-id="b9837-128">**匿名ユーザーを含むすべてのユーザーがウェビナーに登録するには、次のコマンドを実行します。**</span><span class="sxs-lookup"><span data-stu-id="b9837-128">**To allow anyone, including anonymous users, to register for webinars, run:**</span></span>

```powershell
Set-CsTeamsMeetingPolicy -AllowPrivateMeetingScheduling $True
```

<span data-ttu-id="b9837-129">次に、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="b9837-129">Then, run:</span></span>

```powershell
Set-CsTeamsMeetingPolicy -WhoCanRegister Everyone
```

> [!IMPORTANT]
> <span data-ttu-id="b9837-130">会議の設定で匿名参加がオフになっている場合、匿名ユーザーはウェビナーに参加できます。</span><span class="sxs-lookup"><span data-stu-id="b9837-130">If anonymous join is turned off in meeting settings, anonymous users can't join webinars.</span></span> <span data-ttu-id="b9837-131">詳細とこの設定を有効にするには、「会議の設定」を参照[Teams。](meeting-settings-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="b9837-131">To learn more and enable this setting, see [Meeting settings in Teams](meeting-settings-in-teams.md).</span></span>

### <a name="collect-meeting-attendance"></a><span data-ttu-id="b9837-132">会議出席を収集する</span><span class="sxs-lookup"><span data-stu-id="b9837-132">Collect meeting attendance</span></span>

<span data-ttu-id="b9837-133">開催者にウェビナーの登録者と参加したユーザーを分析する場合は **、AllowEngagementReport** ポリシーを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b9837-133">If you want organizers to analyze who registered and attended webinars, you'll need to turn on the **AllowEngagementReport** policy.</span></span> <span data-ttu-id="b9837-134">これを行うには、PowerShell で次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="b9837-134">To do this, run the following command in PowerShell.</span></span>

```powershell
Set-CsTeamsMeetingPolicy -AllowEngagementReport Enabled
```

### <a name="configure-webinar-settings"></a><span data-ttu-id="b9837-135">ウェビナー設定を構成する</span><span class="sxs-lookup"><span data-stu-id="b9837-135">Configure webinar settings</span></span>

<span data-ttu-id="b9837-136">ウェビナー用に環境を有効にした後は、それ以上の管理者管理は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="b9837-136">After enabling your environment for webinars, no further admin management is required.</span></span> <span data-ttu-id="b9837-137">ポリシーは、ウェビナー開催者に表示されるオプションを制御します。</span><span class="sxs-lookup"><span data-stu-id="b9837-137">The policy controls which options show up for webinar organizers.</span></span>

## <a name="related-topics"></a><span data-ttu-id="b9837-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="b9837-138">Related topics</span></span>

- [<span data-ttu-id="b9837-139">Teams の会議ポリシー - 全般</span><span class="sxs-lookup"><span data-stu-id="b9837-139">Meeting policies in Teams - General</span></span>](meeting-policies-in-teams-general.md)
- [<span data-ttu-id="b9837-140">Set-CsTeamsMeetingPolicy のドキュメント</span><span class="sxs-lookup"><span data-stu-id="b9837-140">Set-CsTeamsMeetingPolicy documentation</span></span>](/powershell/module/skype/set-csteamsmeetingpolicy)
