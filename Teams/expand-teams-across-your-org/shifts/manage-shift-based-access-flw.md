---
title: Teams での Firstline Worker のシフトベースのアクセスを管理する
author: LanaChin
ms.author: v-lanac
ms.reviewer: aaku
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 組織の Firstline Worker の Teams でシフトベースのアクセスを管理する方法について説明します。
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9ec470422e402da07171bef627d1592c73d6c12f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48514134"
---
# <a name="manage-shift-based-access-for-firstline-workers-in-teams"></a><span data-ttu-id="2b424-103">Teams での Firstline Worker のシフトベースのアクセスを管理する</span><span class="sxs-lookup"><span data-stu-id="2b424-103">Manage shift-based access for Firstline Workers in Teams</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2b424-104">2020年6月30日有効な Microsoft StaffHub は廃止されました。</span><span class="sxs-lookup"><span data-stu-id="2b424-104">Effective June 30, 2020, Microsoft StaffHub has been retired.</span></span> <span data-ttu-id="2b424-105">Microsoft では、StaffHub の機能を Microsoft Teams に組み込む作業に取り組んでいます。</span><span class="sxs-lookup"><span data-stu-id="2b424-105">We’re building StaffHub capabilities into Microsoft Teams.</span></span> <span data-ttu-id="2b424-106">現在、Teams にはシフト アプリのスケジュール管理機能が含まれています。今後、他の機能もロールアウトされる予定です。</span><span class="sxs-lookup"><span data-stu-id="2b424-106">Today, Teams includes the Shifts app for schedule management and additional capabilities will roll out over time.</span></span> <span data-ttu-id="2b424-107">2020年6月30日に、StaffHub がすべてのユーザーに対して動作を停止しました。</span><span class="sxs-lookup"><span data-stu-id="2b424-107">StaffHub stopped working for all users on June 30, 2020.</span></span> <span data-ttu-id="2b424-108">StaffHub を開こうとするユーザーには、チームをダウンロードするように指示するメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2b424-108">Anyone who tries to open StaffHub is shown a message directing them to download Teams.</span></span> <span data-ttu-id="2b424-109">詳細については、「 [Microsoft StaffHub が廃止されました](microsoft-staffhub-to-be-retired.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2b424-109">To learn more, see [Microsoft StaffHub has been retired](microsoft-staffhub-to-be-retired.md).</span></span>  

## <a name="overview"></a><span data-ttu-id="2b424-110">概要</span><span class="sxs-lookup"><span data-stu-id="2b424-110">Overview</span></span>

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

<span data-ttu-id="2b424-111">Microsoft Teams のプレゼンスは、ユーザーの現在の可用性と状態を他のユーザーに表示することを示します。</span><span class="sxs-lookup"><span data-stu-id="2b424-111">Presence in Microsoft Teams indicates a user's current availability and status to other users.</span></span> <span data-ttu-id="2b424-112">通常、Firstline Worker の存在は、他の従業員よりも、その稼働時間が毎日同じではないことが多いためです。</span><span class="sxs-lookup"><span data-stu-id="2b424-112">The presence of Firstline Workers is often less predictable than other staff as their working hours are typically not the same each day.</span></span> <span data-ttu-id="2b424-113">管理者として、チームを構成して、組織内の最初の営業員がシフトの有無を示す、シフトベースのプレゼンス状態のセットを表示することができます。</span><span class="sxs-lookup"><span data-stu-id="2b424-113">As an admin, you can configure Teams to show a set of shift-based presence states for the Firstline Workers in your organization to indicate when they are on and off shift.</span></span>

<span data-ttu-id="2b424-114">このようなシフトベースのプレゼンス状態は、緑色のチェックマーク、[シフト時のシフト]、[x の付いた灰色の円] は、[予定あり] &mdash; ![ ](../../media/flw-presence-on-shift.png) **On shift** ![ が [ ](../../media/flw-presence-off-shift.png) **Off shift** ![ ](../../media/flw-presence-busy.png) **Busy** &mdash; チーム内の[既定のプレゼンス状態](../../presence-admins.md)] とは別のものであることを示します。</span><span class="sxs-lookup"><span data-stu-id="2b424-114">These shift-based presence states&mdash;![Solid green check mark, indicates On shift](../../media/flw-presence-on-shift.png) **On shift**, ![Gray circle with x, indicates Off shift](../../media/flw-presence-off-shift.png) **Off shift**, ![Solid red circle, indicates Busy](../../media/flw-presence-busy.png) **Busy**&mdash;are separate from the [default set of presence states](../../presence-admins.md) in Teams.</span></span> <span data-ttu-id="2b424-115">この2つのプレゼンス状態のセットを使用すると、組織内のユーザーの役割に基づいて、さまざまなエクスペリエンスを構成できます。</span><span class="sxs-lookup"><span data-stu-id="2b424-115">With these two sets of presence states, you can configure different experiences for people in your organization based on their role.</span></span>

<span data-ttu-id="2b424-116">シフトベースのアクセスを使用すると、Firstline Worker がシフトをオフにしている場合にチームへのアクセスを管理できます。</span><span class="sxs-lookup"><span data-stu-id="2b424-116">With shift-based access, you can manage access to Teams when Firstline Workers are off shift.</span></span> <span data-ttu-id="2b424-117">たとえば、チームがスケジュールされたシフトを使っていないときに、チームを使用できるようにする前に、Firstline Worker が確認する必要があるというメッセージが表示されるように設定できます。</span><span class="sxs-lookup"><span data-stu-id="2b424-117">For example, you can set Teams to display a message that Firstline Workers must acknowledge before they can use Teams when they're not on a scheduled shift.</span></span>  

## <a name="scenario"></a><span data-ttu-id="2b424-118">シナリオ</span><span class="sxs-lookup"><span data-stu-id="2b424-118">Scenario</span></span>

<span data-ttu-id="2b424-119">組織でシフトベースのアクセスを管理する方法の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="2b424-119">Here's an example of how your organization can manage shift-based access.</span></span>

<span data-ttu-id="2b424-120">組織内の最初の営業担当者が、マネージャーがスケジュールされて承認したシフトで作業した時間だけ支払いを行う必要がある場合。</span><span class="sxs-lookup"><span data-stu-id="2b424-120">You have Firstline Workers in your organization that should only be paid for hours they work on a shift that their manager scheduled and approved.</span></span> <span data-ttu-id="2b424-121">スケジュールされたシフト以外での作業に費やした時間は、Teams アプリの使用も含めて支払われません。</span><span class="sxs-lookup"><span data-stu-id="2b424-121">They shouldn't be paid for time spent working outside a scheduled shift, which includes using the Teams app.</span></span> <span data-ttu-id="2b424-122">"シフトが表示されていないときにチームに時間がかかることはありません" というカスタムメッセージを設定します。これは、shift キーをオフにすると、Firstline Worker がチームにアクセスしようとしたときに表示されます。</span><span class="sxs-lookup"><span data-stu-id="2b424-122">You set up a custom message that says "Your time on Teams when on off shift won't count toward payable hours", which is displayed when Firstline Workers try to access Teams when off shift.</span></span> <span data-ttu-id="2b424-123">チームの使用を選択した場合は、[ **同意** する] をクリックすると、今回は支払いされません。</span><span class="sxs-lookup"><span data-stu-id="2b424-123">If they choose to use Teams, they click **I accept** with the understanding that they won't be paid for this time.</span></span>

<span data-ttu-id="2b424-124">また、salaried の勤務先であり、シフトが行われない組織内のインフォメーションワーカーもいます。</span><span class="sxs-lookup"><span data-stu-id="2b424-124">You also have information workers in your organization who are salaried and who don't work shifts.</span></span> <span data-ttu-id="2b424-125">Firstline Worker のシフトベースのプレゼンスを指定しながら、Teams で既定のプレゼンス状態を使用するようにインフォメーションワーカーを構成します。</span><span class="sxs-lookup"><span data-stu-id="2b424-125">You configure your information workers to use the default presence states in Teams while giving your Firstline Workers shift-based presence.</span></span>

## <a name="shift-based-presence-states"></a><span data-ttu-id="2b424-126">シフトベースのプレゼンス状態</span><span class="sxs-lookup"><span data-stu-id="2b424-126">Shift-based presence states</span></span>

<span data-ttu-id="2b424-127">シフトベースのプレゼンス状態を次に示します。</span><span class="sxs-lookup"><span data-stu-id="2b424-127">Here are the shift-based presence states.</span></span>

|<span data-ttu-id="2b424-128">アプリが設定</span><span class="sxs-lookup"><span data-stu-id="2b424-128">App configured</span></span> |<span data-ttu-id="2b424-129">ユーザーが設定</span><span class="sxs-lookup"><span data-stu-id="2b424-129">User configured</span></span>  |<span data-ttu-id="2b424-130">詳細情報</span><span class="sxs-lookup"><span data-stu-id="2b424-130">More information</span></span>  |
|---------|---------|---------|
|![緑色のチェックマーク、シフトで示される](../../media/flw-presence-on-shift.png) <span data-ttu-id="2b424-132">シフト</span><span class="sxs-lookup"><span data-stu-id="2b424-132">On shift</span></span>     |         |<span data-ttu-id="2b424-133">シフトの開始時に自動的に設定する</span><span class="sxs-lookup"><span data-stu-id="2b424-133">Automatically set at the start of a shift</span></span>         |
|![[X] の灰色の円は、shift キーをオフにします。](../../media/flw-presence-off-shift.png) <span data-ttu-id="2b424-135">シフトオフ</span><span class="sxs-lookup"><span data-stu-id="2b424-135">Off shift</span></span>     |         |<span data-ttu-id="2b424-136">シフトの終了時に自動的に設定する</span><span class="sxs-lookup"><span data-stu-id="2b424-136">Automatically set at the end of a shift</span></span>         |
|![塗りつぶした赤い丸は、取り込み中を示す](../../media/flw-presence-busy.png) <span data-ttu-id="2b424-138">取り込み中</span><span class="sxs-lookup"><span data-stu-id="2b424-138">Busy</span></span>      | ![塗りつぶした赤い丸は、取り込み中を示す](../../media/flw-presence-busy.png) <span data-ttu-id="2b424-140">取り込み中</span><span class="sxs-lookup"><span data-stu-id="2b424-140">Busy</span></span>         |<span data-ttu-id="2b424-141">自動的に設定されます。</span><span class="sxs-lookup"><span data-stu-id="2b424-141">Automatically set.</span></span> <span data-ttu-id="2b424-142">Firstline Worker がシフトになったときに手動で設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="2b424-142">Can also be manually set when the Firstline Worker is on shift.</span></span>|

## <a name="off-shift-access-to-teams"></a><span data-ttu-id="2b424-143">Shift キーを押しながら Teams にアクセス</span><span class="sxs-lookup"><span data-stu-id="2b424-143">Off shift access to Teams</span></span>

<span data-ttu-id="2b424-144">この機能を使用すると、Firstline Worker がシフトをオフにしている場合にチームへのアクセスを管理することができます。</span><span class="sxs-lookup"><span data-stu-id="2b424-144">This feature lets you manage access to Teams when Firstline Workers are off shift.</span></span> <span data-ttu-id="2b424-145">ユーザーが shift キーをオフにしたときにチームにアクセスすると、Firstline Worker にメッセージを表示するようにチームを設定することができます。</span><span class="sxs-lookup"><span data-stu-id="2b424-145">You can set Teams to display a message to Firstline Workers if they access Teams when off shift.</span></span> <span data-ttu-id="2b424-146">Firstline Worker は、チームを使用する前に、メッセージを承認するために [ **承諾** ] をクリックする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2b424-146">Firstline Workers must click **I accept** to acknowledge the message before they can use Teams.</span></span>

<span data-ttu-id="2b424-147">既定のメッセージを使用するか、あらかじめ定義された一連のメッセージから選ぶか、メッセージをカスタマイズして必要なテキストを表示することができます。</span><span class="sxs-lookup"><span data-stu-id="2b424-147">You can use the default message, choose from a set of pre-defined messages, or customize the message to display any text that you want.</span></span> <span data-ttu-id="2b424-148">既定のメッセージは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="2b424-148">Here's the default message:</span></span>

![既定のメッセージのスクリーンショット](../../media/shifts-presence-message.png)

<span data-ttu-id="2b424-150">また、メッセージが表示されるときの頻度を設定して、最初のシフトが開始または終了してから、チームへのアクセスが制限されるまでの猶予期間を設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="2b424-150">You can also set the frequency when the message is displayed and set a grace period between when the first shift starts or last shift ends and when access to Teams is restricted.</span></span>

## <a name="manage-shift-based-access"></a><span data-ttu-id="2b424-151">シフトベースのアクセスを管理する</span><span class="sxs-lookup"><span data-stu-id="2b424-151">Manage shift-based access</span></span>

<span data-ttu-id="2b424-152">管理者は、ポリシーを使って、組織内の Firstline Worker のシフトベースのプレゼンスを制御します。</span><span class="sxs-lookup"><span data-stu-id="2b424-152">As an admin, you use policies to control shift-based presence for Firstline Workers in your organization.</span></span> <span data-ttu-id="2b424-153">これらのポリシーを管理するには、次の PowerShell コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="2b424-153">You manage these policies by using the following PowerShell cmdlets:</span></span>

- [<span data-ttu-id="2b424-154">新規-CsTeamsShiftsPolicy</span><span class="sxs-lookup"><span data-stu-id="2b424-154">New-CsTeamsShiftsPolicy</span></span>](https://docs.microsoft.com/powershell/module/teams/new-csteamsshiftspolicy)
- [<span data-ttu-id="2b424-155">Get-CsTeamsShiftsPolicy</span><span class="sxs-lookup"><span data-stu-id="2b424-155">Get-CsTeamsShiftsPolicy</span></span>](https://docs.microsoft.com/powershell/module/teams/get-csteamsshiftspolicy)
- [<span data-ttu-id="2b424-156">Set-CsTeamsShiftsPolicy</span><span class="sxs-lookup"><span data-stu-id="2b424-156">Set-CsTeamsShiftsPolicy</span></span>](https://docs.microsoft.com/powershell/module/teams/set-csteamsshiftspolicy)
- [<span data-ttu-id="2b424-157">Grant-CsTeamsShiftsPolicy</span><span class="sxs-lookup"><span data-stu-id="2b424-157">Grant-CsTeamsShiftsPolicy</span></span>](https://docs.microsoft.com/powershell/module/teams/grant-csteamsshiftspolicy)
- [<span data-ttu-id="2b424-158">Remove-CsTeamsShiftsPolicy</span><span class="sxs-lookup"><span data-stu-id="2b424-158">Remove-CsTeamsShiftsPolicy</span></span>](https://docs.microsoft.com/powershell/module/teams/remove-csteamsshiftspolicy)

<span data-ttu-id="2b424-159">New-CsTeamsShiftsPolicy コマンドレットを使用して新しいポリシーを作成し、必要なポリシー設定を設定してから、Grant-CsTeamsShiftsPolicy コマンドレットを使用してユーザーにポリシーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="2b424-159">Use the New-CsTeamsShiftsPolicy cmdlet to create a new policy, set the policy settings that you want, and then use the Grant-CsTeamsShiftsPolicy cmdlet to assign the policy to users.</span></span>

<span data-ttu-id="2b424-160">いくつかの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="2b424-160">Here's some examples.</span></span> <span data-ttu-id="2b424-161">選択できる事前設定されたオフシフトメッセージの一覧など、各ポリシー設定とパラメーターの詳細については、「 [New-CsTeamsShiftsPolicy](https://docs.microsoft.com/powershell/module/teams/new-csteamsshiftspolicy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2b424-161">For detailed information about each policy setting and parameter, including the list of predefined off shift messages that you can choose from, see [New-CsTeamsShiftsPolicy](https://docs.microsoft.com/powershell/module/teams/new-csteamsshiftspolicy).</span></span>

### <a name="example-1"></a><span data-ttu-id="2b424-162">例 1</span><span class="sxs-lookup"><span data-stu-id="2b424-162">Example 1</span></span>

<span data-ttu-id="2b424-163">この例では、"Shift Teams/チームアクセスの既定のメッセージ" という名前の新しいポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="2b424-163">In this example, we create a new policy named Off Shift Teams Access Default Message.</span></span> <span data-ttu-id="2b424-164">このポリシーでは、shift ベースのプレゼンスがオンになっており、このポリシーを割り当てられたユーザーがシフトをオフにすると、チームにアクセスするたびに既定のメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2b424-164">In this policy, shift-based presence is turned on and the default message is displayed every time a user who is assigned this policy accesses Teams when off shift.</span></span> <span data-ttu-id="2b424-165">ユーザーはシフトをオフにしたときに、そのメッセージを受け取ることができます。また、最初のシフトの開始または終了の間の猶予期間と、10分間のアクセスが制限されている場合には、チームを使うことができます。</span><span class="sxs-lookup"><span data-stu-id="2b424-165">The user can use Teams when off shift if they accept the message, and the grace period between when the first shift starts or last shift ends and when access is restricted is 10 minutes.</span></span>  

```powershell
New-CsTeamsShiftsPolicy -Identity "Off Shift Teams Access Default Message" -EnableShiftPresence $true -ShiftNoticeFrequency always -ShiftNoticeMessageType DefaultMessage -AccessType UnrestrictedAccess_TeamsApp -AccessGracePeriodMinutes 10
```

> [!NOTE]
> <span data-ttu-id="2b424-166">**ShiftNoticeMessageType**パラメーターを使用して、表示するメッセージを設定します。</span><span class="sxs-lookup"><span data-stu-id="2b424-166">Use the **ShiftNoticeMessageType** parameter to set the message that you want to display.</span></span> <span data-ttu-id="2b424-167">このパラメーターに対して選ぶことができる定義済みメッセージの一覧を表示するには、「 [New-CsTeamsShiftsPolicy](https://docs.microsoft.com/powershell/module/teams/new-csteamsshiftspolicy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2b424-167">To see a list of the pre-defined messages that you can choose from for this parameter, see [New-CsTeamsShiftsPolicy](https://docs.microsoft.com/powershell/module/teams/new-csteamsshiftspolicy).</span></span>

### <a name="example-2"></a><span data-ttu-id="2b424-168">例 2</span><span class="sxs-lookup"><span data-stu-id="2b424-168">Example 2</span></span> 

<span data-ttu-id="2b424-169">この例では、"Shift Teams/チームアクセスのカスタムメッセージ" という名前の新しいポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="2b424-169">In this example, we create a new policy named Off Shift Teams Access Custom Message.</span></span> <span data-ttu-id="2b424-170">このポリシーでは、shift ベースのプレゼンスが有効になっており、このポリシーを割り当てられたユーザーがシフトをオフにすると、チームにアクセスするたびにユーザー設定のメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2b424-170">In this policy, shift-based presence is turned on and a custom message is displayed every time a user who is assigned this policy accesses Teams when off shift.</span></span> <span data-ttu-id="2b424-171">ユーザーはシフトをオフにしたときに、そのメッセージを受け取ることができます。また、最初のシフトの開始または終了の間の猶予期間と、アクセスが制限されている場合は15分となります。</span><span class="sxs-lookup"><span data-stu-id="2b424-171">The user can use Teams when off shift if they accept the message, and the grace period between when the first shift starts or last shift ends and when access is restricted is 15 minutes.</span></span>  

```powershell
New-CsTeamsShiftsPolicy -Identity "Off Shift Teams Access Custom Message" -EnableShiftPresence $true -ShiftNoticeFrequency always -ShiftNoticeMessageType CustomMessage -ShiftNoticeMessageCustom "Your time on Teams when on off shift won't count toward payable hours" -AccessType UnrestrictedAccess_TeamsApp -AccessGracePeriodMinutes 15
```

> [!NOTE]
> <span data-ttu-id="2b424-172">**ShiftNoticeMessageType**パラメーターを使用して、表示するメッセージを設定します。</span><span class="sxs-lookup"><span data-stu-id="2b424-172">Use the **ShiftNoticeMessageType** parameter to set the message that you want to display.</span></span> <span data-ttu-id="2b424-173">詳細については、「 [New-CsTeamsShiftsPolicy](https://docs.microsoft.com/powershell/module/teams/new-csteamsshiftspolicy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2b424-173">To learn more, see [New-CsTeamsShiftsPolicy](https://docs.microsoft.com/powershell/module/teams/new-csteamsshiftspolicy).</span></span>

### <a name="example-3"></a><span data-ttu-id="2b424-174">例 3</span><span class="sxs-lookup"><span data-stu-id="2b424-174">Example 3</span></span>

<span data-ttu-id="2b424-175">この例では、"Off Shift Teams" アクセス Message1 という名前の新しいポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="2b424-175">In this example, we create a new policy named Off Shift Teams Access Message1.</span></span> <span data-ttu-id="2b424-176">このポリシーでは、shift ベースのプレゼンスがオンになっており、このポリシーを割り当てられたユーザーがシフトをオフにすると、チームにアクセスするたびに、次の定義済みのメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2b424-176">In this policy, shift-based presence is turned on and the following predefined message is displayed every time a user who is assigned this policy accesses Teams when off shift.</span></span>

  <span data-ttu-id="2b424-177">"お客様のネットワーク、アプリケーション、システム、またはツールの使用に関して非免税または毎時の従業員による作業は、非稼働時間中に承認または承認されません。</span><span class="sxs-lookup"><span data-stu-id="2b424-177">"Your employer does not authorize or approve of the use of its network, applications, systems, or tools by non-exempt or hourly employees during their non-working hours.</span></span> <span data-ttu-id="2b424-178">承認を受けることで、シフトの外部でのチームの使用が許可されておらず、お客様は補償できないことが認められます。 "</span><span class="sxs-lookup"><span data-stu-id="2b424-178">By accepting, you acknowledge that your use of Teams while off shift is not authorized and you will not be compensated."</span></span> 

<span data-ttu-id="2b424-179">ユーザーはシフトをオフにしたときに、そのメッセージを受け取ることができます。また、最初のシフトの開始または終了の間の猶予期間と、3分間のアクセスが制限されている場合には、チームを使うことができます。</span><span class="sxs-lookup"><span data-stu-id="2b424-179">The user can use Teams when off shift if they accept the message, and the grace period between when the first shift starts or last shift ends and when access is restricted is three minutes.</span></span>  

```powershell
New-CsTeamsShiftsPolicy -Identity "Off Shift Teams Access Message1" -EnableShiftPresence $true -ShiftNoticeFrequency always -ShiftNoticeMessageType Message1 -AccessType  UnrestrictedAccess_TeamsApp -AccessGracePeriodMinutes 3
```

> [!NOTE]
> <span data-ttu-id="2b424-180">**ShiftNoticeMessageType**パラメーターを使用して、表示するメッセージを設定します。</span><span class="sxs-lookup"><span data-stu-id="2b424-180">Use the **ShiftNoticeMessageType** parameter to set the message that you want to display.</span></span> <span data-ttu-id="2b424-181">このパラメーターに対して選ぶことができる定義済みメッセージの一覧を表示するには、「 [New-CsTeamsShiftsPolicy](https://docs.microsoft.com/powershell/module/teams/new-csteamsshiftspolicy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2b424-181">To see a list of the pre-defined messages that you can choose from for this parameter, see [New-CsTeamsShiftsPolicy](https://docs.microsoft.com/powershell/module/teams/new-csteamsshiftspolicy).</span></span>

### <a name="example-4"></a><span data-ttu-id="2b424-182">例 4</span><span class="sxs-lookup"><span data-stu-id="2b424-182">Example 4</span></span>

<span data-ttu-id="2b424-183">この例では、remy@contoso.com という名前のユーザーへの Shift チームへのアクセスのカスタムメッセージという名前のポリシーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="2b424-183">In this example, we assign a policy named Off Shift Teams Access Custom Message to a user named remy@contoso.com.</span></span>

```powershell
Grant-CsTeamsShiftsPolicy -Identity remy@contoso.com -PolicyName "Off Shift Teams Access Custom Message"
```

## <a name="related-topics"></a><span data-ttu-id="2b424-184">関連項目</span><span class="sxs-lookup"><span data-stu-id="2b424-184">Related topics</span></span>

- [<span data-ttu-id="2b424-185">Teams で組織の Shifts アプリを管理する</span><span class="sxs-lookup"><span data-stu-id="2b424-185">Manage the Shifts app for your organization in Teams</span></span>](manage-the-shifts-app-for-your-organization-in-teams.md)
- [<span data-ttu-id="2b424-186">Teams での PowerShell の概要</span><span class="sxs-lookup"><span data-stu-id="2b424-186">Teams PowerShell overview</span></span>](../../teams-powershell-overview.md)
