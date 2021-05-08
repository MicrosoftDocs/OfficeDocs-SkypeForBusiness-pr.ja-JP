---
title: Teams で Frontline Worker のシフトベースのアクセスを管理する
author: cichur
ms.author: v-cichur
ms.reviewer: aaku
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 組織内の Frontline Worker 向け Teamsにシフトベースのアクセスを管理する方法について学習します。
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: c69f5678b2a3884f52dd3dc676fce21e2ee67f4f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51092545"
---
# <a name="manage-shift-based-access-for-frontline-workers-in-teams"></a><span data-ttu-id="dc027-103">Teams で Frontline Worker のシフトベースのアクセスを管理する</span><span class="sxs-lookup"><span data-stu-id="dc027-103">Manage shift-based access for Frontline Workers in Teams</span></span>

> [!IMPORTANT]
> <span data-ttu-id="dc027-104">2020 年 6 月 30 日をもって、Microsoft Staffhub は廃止されました。</span><span class="sxs-lookup"><span data-stu-id="dc027-104">Effective June 30, 2020, Microsoft StaffHub has been retired.</span></span> <span data-ttu-id="dc027-105">Microsoft では、StaffHub の機能を Microsoft Teams に組み込む作業に取り組んでいます。</span><span class="sxs-lookup"><span data-stu-id="dc027-105">We’re building StaffHub capabilities into Microsoft Teams.</span></span> <span data-ttu-id="dc027-106">現在、Teams にはシフト アプリのスケジュール管理機能が含まれています。今後、他の機能もロールアウトされる予定です。</span><span class="sxs-lookup"><span data-stu-id="dc027-106">Today, Teams includes the Shifts app for schedule management and additional capabilities will roll out over time.</span></span> <span data-ttu-id="dc027-107">StaffHub は 2020 年 6 月 30 日をもって、すべてのユーザーがご利用できなくなりました。</span><span class="sxs-lookup"><span data-stu-id="dc027-107">StaffHub stopped working for all users on June 30, 2020.</span></span> <span data-ttu-id="dc027-108">ユーザーが StaffHub を開くと、Teams をダウンロードするように求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="dc027-108">Anyone who tries to open StaffHub is shown a message directing them to download Teams.</span></span> <span data-ttu-id="dc027-109">詳細については、「[Microsoft StaffHub は廃止されました](microsoft-staffhub-to-be-retired.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dc027-109">To learn more, see [Microsoft StaffHub has been retired](microsoft-staffhub-to-be-retired.md).</span></span>  

## <a name="overview"></a><span data-ttu-id="dc027-110">概要</span><span class="sxs-lookup"><span data-stu-id="dc027-110">Overview</span></span>

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

<span data-ttu-id="dc027-111">[プレゼンス] Microsoft Teamsユーザーの現在の可用性と他のユーザーへの状態を示します。</span><span class="sxs-lookup"><span data-stu-id="dc027-111">Presence in Microsoft Teams indicates a user's current availability and status to other users.</span></span> <span data-ttu-id="dc027-112">フロントライン ワーカーの存在は、通常は毎日同じではならず、他のスタッフよりも予測が難しい場合があります。</span><span class="sxs-lookup"><span data-stu-id="dc027-112">The presence of Frontline Workers is often less predictable than other staff as their working hours are typically not the same each day.</span></span> <span data-ttu-id="dc027-113">管理者は、組織内の Frontline Worker のシフトベースのプレゼンス状態のセットを表示して、シフトのオンとオフを示す Teams を構成できます。</span><span class="sxs-lookup"><span data-stu-id="dc027-113">As an admin, you can configure Teams to show a set of shift-based presence states for the Frontline Workers in your organization to indicate when they are on and off shift.</span></span>

<span data-ttu-id="dc027-114">これらのシフトベースのプレゼンス状態緑色のチェック マークは、シフト時、灰色の円 x を示し、オフシフトオフシフト、実線の赤い円を示し、取り込み中が &mdash; ![ ](../../media/flw-presence-on-shift.png)  ![ ](../../media/flw-presence-off-shift.png)  ![ ](../../media/flw-presence-busy.png)  &mdash; Teams[](../../presence-admins.md)の既定のプレゼンス状態のセットとは別の状態を示します。</span><span class="sxs-lookup"><span data-stu-id="dc027-114">These shift-based presence states&mdash;![Solid green check mark, indicates On shift](../../media/flw-presence-on-shift.png) **On shift**, ![Gray circle with x, indicates Off shift](../../media/flw-presence-off-shift.png) **Off shift**, ![Solid red circle, indicates Busy](../../media/flw-presence-busy.png) **Busy**&mdash;are separate from the [default set of presence states](../../presence-admins.md) in Teams.</span></span> <span data-ttu-id="dc027-115">これら 2 つのプレゼンス状態のセットでは、その役割に基づいて組織内のユーザーに対して異なるエクスペリエンスを構成できます。</span><span class="sxs-lookup"><span data-stu-id="dc027-115">With these two sets of presence states, you can configure different experiences for people in your organization based on their role.</span></span>

<span data-ttu-id="dc027-116">シフトベースのアクセスでは、Frontline Worker がシフト外のTeamsへのアクセスを管理できます。</span><span class="sxs-lookup"><span data-stu-id="dc027-116">With shift-based access, you can manage access to Teams when Frontline Workers are off shift.</span></span> <span data-ttu-id="dc027-117">たとえば、スケジュールされたシフトに移動していない場合に Teams を使用する前に、Frontline Worker が確認する必要があるメッセージを表示する Teams を設定できます。</span><span class="sxs-lookup"><span data-stu-id="dc027-117">For example, you can set Teams to display a message that Frontline Workers must acknowledge before they can use Teams when they're not on a scheduled shift.</span></span>  

## <a name="scenario"></a><span data-ttu-id="dc027-118">シナリオ</span><span class="sxs-lookup"><span data-stu-id="dc027-118">Scenario</span></span>

<span data-ttu-id="dc027-119">組織でシフトベースのアクセスを管理する方法の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="dc027-119">Here's an example of how your organization can manage shift-based access.</span></span>

<span data-ttu-id="dc027-120">組織内に Frontline Worker がいて、マネージャーがスケジュールして承認したシフトで作業する時間に対してのみ支払う必要があります。</span><span class="sxs-lookup"><span data-stu-id="dc027-120">You have Frontline Workers in your organization that should only be paid for hours they work on a shift that their manager scheduled and approved.</span></span> <span data-ttu-id="dc027-121">スケジュールされたシフトの外で作業に費やされた時間に対して支払いを受けてはならない。これには、スケジュールされたアプリの使用Teamsがあります。</span><span class="sxs-lookup"><span data-stu-id="dc027-121">They shouldn't be paid for time spent working outside a scheduled shift, which includes using the Teams app.</span></span> <span data-ttu-id="dc027-122">"シフトオフ時の Teams の時間は未払い時間にカウントされません" というカスタム メッセージを設定すると、Frontline Worker がシフトをオフにするときに Teams にアクセスしようとするときに表示されます。</span><span class="sxs-lookup"><span data-stu-id="dc027-122">You set up a custom message that says "Your time on Teams when on off shift won't count toward payable hours", which is displayed when Frontline Workers try to access Teams when off shift.</span></span> <span data-ttu-id="dc027-123">ユーザーがアプリを使用Teams、この時間の支払いを受け取らないという理解を得て [同意する] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dc027-123">If they choose to use Teams, they click **I accept** with the understanding that they won't be paid for this time.</span></span>

<span data-ttu-id="dc027-124">また、組織内に、サラリーマンであり、シフトを使用しない情報ワーカーもいます。</span><span class="sxs-lookup"><span data-stu-id="dc027-124">You also have information workers in your organization who are salaried and who don't work shifts.</span></span> <span data-ttu-id="dc027-125">フロントライン ワーカーにシフトベースのプレゼンスを提供しながら、Teams の既定のプレゼンス状態を使用する情報ワーカーを構成します。</span><span class="sxs-lookup"><span data-stu-id="dc027-125">You configure your information workers to use the default presence states in Teams while giving your Frontline Workers shift-based presence.</span></span>

## <a name="shift-based-presence-states"></a><span data-ttu-id="dc027-126">シフトベースのプレゼンス状態</span><span class="sxs-lookup"><span data-stu-id="dc027-126">Shift-based presence states</span></span>

<span data-ttu-id="dc027-127">シフトベースのプレゼンス状態を次に示します。</span><span class="sxs-lookup"><span data-stu-id="dc027-127">Here are the shift-based presence states.</span></span>

|<span data-ttu-id="dc027-128">アプリが設定</span><span class="sxs-lookup"><span data-stu-id="dc027-128">App configured</span></span> |<span data-ttu-id="dc027-129">ユーザーが設定</span><span class="sxs-lookup"><span data-stu-id="dc027-129">User configured</span></span>  |<span data-ttu-id="dc027-130">詳細情報</span><span class="sxs-lookup"><span data-stu-id="dc027-130">More information</span></span>  |
|---------|---------|---------|
|![緑色の単色のチェック マーク、シフト時を示します。](../../media/flw-presence-on-shift.png) <span data-ttu-id="dc027-132">シフト時</span><span class="sxs-lookup"><span data-stu-id="dc027-132">On shift</span></span>     |         |<span data-ttu-id="dc027-133">シフトの開始時に自動的に設定する</span><span class="sxs-lookup"><span data-stu-id="dc027-133">Automatically set at the start of a shift</span></span>         |
|![x を含む灰色の円、オフ シフトを示します。](../../media/flw-presence-off-shift.png) <span data-ttu-id="dc027-135">シフトをオフにする</span><span class="sxs-lookup"><span data-stu-id="dc027-135">Off shift</span></span>     |         |<span data-ttu-id="dc027-136">シフトの最後に自動的に設定する</span><span class="sxs-lookup"><span data-stu-id="dc027-136">Automatically set at the end of a shift</span></span>         |
|![塗りつぶした赤い丸は、取り込み中を示す](../../media/flw-presence-busy.png) <span data-ttu-id="dc027-138">取り込み中</span><span class="sxs-lookup"><span data-stu-id="dc027-138">Busy</span></span>      | ![塗りつぶした赤い丸は、取り込み中を示す](../../media/flw-presence-busy.png) <span data-ttu-id="dc027-140">取り込み中</span><span class="sxs-lookup"><span data-stu-id="dc027-140">Busy</span></span>         |<span data-ttu-id="dc027-141">自動的に設定されます。</span><span class="sxs-lookup"><span data-stu-id="dc027-141">Automatically set.</span></span> <span data-ttu-id="dc027-142">Frontline Worker がシフト時に手動で設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="dc027-142">Can also be manually set when the Frontline Worker is on shift.</span></span>|

## <a name="off-shift-access-to-teams"></a><span data-ttu-id="dc027-143">シフトをオフにし、Teams</span><span class="sxs-lookup"><span data-stu-id="dc027-143">Off shift access to Teams</span></span>

<span data-ttu-id="dc027-144">この機能を使用すると、Frontline worker がシフトTeamsにアクセスするユーザーを管理できます。</span><span class="sxs-lookup"><span data-stu-id="dc027-144">This feature lets you manage access to Teams when Frontline Workers are off shift.</span></span> <span data-ttu-id="dc027-145">シフトをオフにTeamsにアクセスする場合は、Frontline Worker にメッセージを表示Teamsを設定できます。</span><span class="sxs-lookup"><span data-stu-id="dc027-145">You can set Teams to display a message to Frontline Workers if they access Teams when off shift.</span></span> <span data-ttu-id="dc027-146">Frontline Worker は、[同意 **する] を** クリックしてメッセージを確認してから、そのメッセージを使用Teams。</span><span class="sxs-lookup"><span data-stu-id="dc027-146">Frontline Workers must click **I accept** to acknowledge the message before they can use Teams.</span></span>

<span data-ttu-id="dc027-147">既定のメッセージを使用したり、一連の定義済みメッセージから選択したり、メッセージをカスタマイズして必要なテキストを表示することができます。</span><span class="sxs-lookup"><span data-stu-id="dc027-147">You can use the default message, choose from a set of pre-defined messages, or customize the message to display any text that you want.</span></span> <span data-ttu-id="dc027-148">既定のメッセージを次に示します。</span><span class="sxs-lookup"><span data-stu-id="dc027-148">Here's the default message:</span></span>

![既定のメッセージのスクリーンショット](../../media/shifts-presence-message.png)

<span data-ttu-id="dc027-150">また、メッセージが表示される頻度を設定し、最初のシフトの開始または最後のシフトの終了と、メッセージへのアクセスが制限されているTeams設定できます。</span><span class="sxs-lookup"><span data-stu-id="dc027-150">You can also set the frequency when the message is displayed and set a grace period between when the first shift starts or last shift ends and when access to Teams is restricted.</span></span>

## <a name="manage-shift-based-access"></a><span data-ttu-id="dc027-151">シフトベースのアクセスを管理する</span><span class="sxs-lookup"><span data-stu-id="dc027-151">Manage shift-based access</span></span>

<span data-ttu-id="dc027-152">管理者は、ポリシーを使用して、組織内の Frontline Worker のシフトベースのプレゼンスを制御します。</span><span class="sxs-lookup"><span data-stu-id="dc027-152">As an admin, you use policies to control shift-based presence for Frontline Workers in your organization.</span></span> <span data-ttu-id="dc027-153">これらのポリシーは、次の PowerShell コマンドレットを使用して管理します。</span><span class="sxs-lookup"><span data-stu-id="dc027-153">You manage these policies by using the following PowerShell cmdlets:</span></span>

- [<span data-ttu-id="dc027-154">New-CsTeamsShiftsPolicy</span><span class="sxs-lookup"><span data-stu-id="dc027-154">New-CsTeamsShiftsPolicy</span></span>](/powershell/module/teams/new-csteamsshiftspolicy)
- [<span data-ttu-id="dc027-155">Get-CsTeamsShiftsPolicy</span><span class="sxs-lookup"><span data-stu-id="dc027-155">Get-CsTeamsShiftsPolicy</span></span>](/powershell/module/teams/get-csteamsshiftspolicy)
- [<span data-ttu-id="dc027-156">Set-CsTeamsShiftsPolicy</span><span class="sxs-lookup"><span data-stu-id="dc027-156">Set-CsTeamsShiftsPolicy</span></span>](/powershell/module/teams/set-csteamsshiftspolicy)
- [<span data-ttu-id="dc027-157">Grant-CsTeamsShiftsPolicy</span><span class="sxs-lookup"><span data-stu-id="dc027-157">Grant-CsTeamsShiftsPolicy</span></span>](/powershell/module/teams/grant-csteamsshiftspolicy)
- [<span data-ttu-id="dc027-158">Remove-CsTeamsShiftsPolicy</span><span class="sxs-lookup"><span data-stu-id="dc027-158">Remove-CsTeamsShiftsPolicy</span></span>](/powershell/module/teams/remove-csteamsshiftspolicy)

<span data-ttu-id="dc027-159">New-CsTeamsShiftsPolicy コマンドレットを使用して新しいポリシーを作成し、必要なポリシー設定を設定した後、Grant-CsTeamsShiftsPolicy コマンドレットを使用してポリシーをユーザーに割り当てします。</span><span class="sxs-lookup"><span data-stu-id="dc027-159">Use the New-CsTeamsShiftsPolicy cmdlet to create a new policy, set the policy settings that you want, and then use the Grant-CsTeamsShiftsPolicy cmdlet to assign the policy to users.</span></span>

<span data-ttu-id="dc027-160">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="dc027-160">Here's some examples.</span></span> <span data-ttu-id="dc027-161">選択できる定義済みのオフ シフト メッセージの一覧など、各ポリシー設定とパラメーターの詳細については [、「New-CsTeamsShiftsPolicy」](/powershell/module/teams/new-csteamsshiftspolicy)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dc027-161">For detailed information about each policy setting and parameter, including the list of predefined off shift messages that you can choose from, see [New-CsTeamsShiftsPolicy](/powershell/module/teams/new-csteamsshiftspolicy).</span></span>

### <a name="example-1"></a><span data-ttu-id="dc027-162">例 1</span><span class="sxs-lookup"><span data-stu-id="dc027-162">Example 1</span></span>

<span data-ttu-id="dc027-163">この例では、既定のメッセージにアクセスするために、Shift キーをオフにしたという名前Teamsポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="dc027-163">In this example, we create a new policy named Off Shift Teams Access Default Message.</span></span> <span data-ttu-id="dc027-164">このポリシーでは、シフトベースのプレゼンスが有効になっていて、このポリシーが割り当てられているユーザーがシフトをオフにするときに、そのポリシーにアクセスTeamsメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="dc027-164">In this policy, shift-based presence is turned on and the default message is displayed every time a user who is assigned this policy accesses Teams when off shift.</span></span> <span data-ttu-id="dc027-165">ユーザーは、メッセージを受け入れる場合はシフトをオフにするときに Teams を使用できます。最初のシフトが開始または最後のシフトが終了し、アクセスが制限されている場合の猶予期間は 10 分です。</span><span class="sxs-lookup"><span data-stu-id="dc027-165">The user can use Teams when off shift if they accept the message, and the grace period between when the first shift starts or last shift ends and when access is restricted is 10 minutes.</span></span>  

```powershell
New-CsTeamsShiftsPolicy -Identity "Off Shift Teams Access Default Message" -EnableShiftPresence $true -ShiftNoticeFrequency always -ShiftNoticeMessageType DefaultMessage -AccessType UnrestrictedAccess_TeamsApp -AccessGracePeriodMinutes 10
```

> [!NOTE]
> <span data-ttu-id="dc027-166">**ShiftNoticeMessageType パラメーターを使用** して、表示するメッセージを設定します。</span><span class="sxs-lookup"><span data-stu-id="dc027-166">Use the **ShiftNoticeMessageType** parameter to set the message that you want to display.</span></span> <span data-ttu-id="dc027-167">このパラメーターに対して選択できる定義済みのメッセージの一覧を表示するには [、New-CsTeamsShiftsPolicy を参照してください](/powershell/module/teams/new-csteamsshiftspolicy)。</span><span class="sxs-lookup"><span data-stu-id="dc027-167">To see a list of the pre-defined messages that you can choose from for this parameter, see [New-CsTeamsShiftsPolicy](/powershell/module/teams/new-csteamsshiftspolicy).</span></span>

### <a name="example-2"></a><span data-ttu-id="dc027-168">例 2</span><span class="sxs-lookup"><span data-stu-id="dc027-168">Example 2</span></span> 

<span data-ttu-id="dc027-169">この例では、"Shift オフ" という名前の新しいポリシーを作成し、Teams メッセージにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="dc027-169">In this example, we create a new policy named Off Shift Teams Access Custom Message.</span></span> <span data-ttu-id="dc027-170">このポリシーでは、シフトベースのプレゼンスが有効になっていて、このポリシーが割り当てられているユーザーがシフトをオフにすると、そのポリシーにアクセスTeamsメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="dc027-170">In this policy, shift-based presence is turned on and a custom message is displayed every time a user who is assigned this policy accesses Teams when off shift.</span></span> <span data-ttu-id="dc027-171">ユーザーは、メッセージを受け入れる場合は Teams をシフト外に使用し、最初のシフトが開始または最後のシフトが終了し、アクセスが制限されている場合の猶予期間は 15 分です。</span><span class="sxs-lookup"><span data-stu-id="dc027-171">The user can use Teams when off shift if they accept the message, and the grace period between when the first shift starts or last shift ends and when access is restricted is 15 minutes.</span></span>  

```powershell
New-CsTeamsShiftsPolicy -Identity "Off Shift Teams Access Custom Message" -EnableShiftPresence $true -ShiftNoticeFrequency always -ShiftNoticeMessageType CustomMessage -ShiftNoticeMessageCustom "Your time on Teams when on off shift won't count toward payable hours" -AccessType UnrestrictedAccess_TeamsApp -AccessGracePeriodMinutes 15
```

> [!NOTE]
> <span data-ttu-id="dc027-172">**ShiftNoticeMessageType パラメーターを使用** して、表示するメッセージを設定します。</span><span class="sxs-lookup"><span data-stu-id="dc027-172">Use the **ShiftNoticeMessageType** parameter to set the message that you want to display.</span></span> <span data-ttu-id="dc027-173">詳細については [、New-CsTeamsShiftsPolicy に関するページを参照してください](/powershell/module/teams/new-csteamsshiftspolicy)。</span><span class="sxs-lookup"><span data-stu-id="dc027-173">To learn more, see [New-CsTeamsShiftsPolicy](/powershell/module/teams/new-csteamsshiftspolicy).</span></span>

### <a name="example-3"></a><span data-ttu-id="dc027-174">例 3</span><span class="sxs-lookup"><span data-stu-id="dc027-174">Example 3</span></span>

<span data-ttu-id="dc027-175">この例では、Off Shift という名前の新しいポリシーを作成し、Access Message1 Teams作成します。</span><span class="sxs-lookup"><span data-stu-id="dc027-175">In this example, we create a new policy named Off Shift Teams Access Message1.</span></span> <span data-ttu-id="dc027-176">このポリシーでは、シフトベースのプレゼンスが有効になっていて、このポリシーが割り当てられているユーザーがシフトをオフにすると、そのポリシーにアクセスTeams次の定義済みメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="dc027-176">In this policy, shift-based presence is turned on and the following predefined message is displayed every time a user who is assigned this policy accesses Teams when off shift.</span></span>

  <span data-ttu-id="dc027-177">"雇用主は、非勤務時間中に、非免除または時間給の従業員によるネットワーク、アプリケーション、システム、またはツールの使用を承認または承認していません。</span><span class="sxs-lookup"><span data-stu-id="dc027-177">"Your employer does not authorize or approve of the use of its network, applications, systems, or tools by non-exempt or hourly employees during their non-working hours.</span></span> <span data-ttu-id="dc027-178">これを受け入れて、シフト外のTeamsの使用が承認されていないこと、および補正されていないことを確認します。"</span><span class="sxs-lookup"><span data-stu-id="dc027-178">By accepting, you acknowledge that your use of Teams while off shift is not authorized and you will not be compensated."</span></span> 

<span data-ttu-id="dc027-179">ユーザーは、メッセージを受け入れる場合はシフトをオフにするときに Teams を使用できます。また、最初のシフトが開始または最後のシフトが終了し、アクセスが制限されている場合の猶予期間は 3 分です。</span><span class="sxs-lookup"><span data-stu-id="dc027-179">The user can use Teams when off shift if they accept the message, and the grace period between when the first shift starts or last shift ends and when access is restricted is three minutes.</span></span>  

```powershell
New-CsTeamsShiftsPolicy -Identity "Off Shift Teams Access Message1" -EnableShiftPresence $true -ShiftNoticeFrequency always -ShiftNoticeMessageType Message1 -AccessType  UnrestrictedAccess_TeamsApp -AccessGracePeriodMinutes 3
```

> [!NOTE]
> <span data-ttu-id="dc027-180">**ShiftNoticeMessageType パラメーターを使用** して、表示するメッセージを設定します。</span><span class="sxs-lookup"><span data-stu-id="dc027-180">Use the **ShiftNoticeMessageType** parameter to set the message that you want to display.</span></span> <span data-ttu-id="dc027-181">このパラメーターに対して選択できる定義済みのメッセージの一覧を表示するには [、New-CsTeamsShiftsPolicy を参照してください](/powershell/module/teams/new-csteamsshiftspolicy)。</span><span class="sxs-lookup"><span data-stu-id="dc027-181">To see a list of the pre-defined messages that you can choose from for this parameter, see [New-CsTeamsShiftsPolicy](/powershell/module/teams/new-csteamsshiftspolicy).</span></span>

### <a name="example-4"></a><span data-ttu-id="dc027-182">例 4</span><span class="sxs-lookup"><span data-stu-id="dc027-182">Example 4</span></span>

<span data-ttu-id="dc027-183">この例では、Off Shift という名前のポリシーを割り当Teams Access Custom Message を、remy@contoso.com という名前のユーザーに割り当 remy@contoso.com。</span><span class="sxs-lookup"><span data-stu-id="dc027-183">In this example, we assign a policy named Off Shift Teams Access Custom Message to a user named remy@contoso.com.</span></span>

```powershell
Grant-CsTeamsShiftsPolicy -Identity remy@contoso.com -PolicyName "Off Shift Teams Access Custom Message"
```

## <a name="related-topics"></a><span data-ttu-id="dc027-184">関連トピック</span><span class="sxs-lookup"><span data-stu-id="dc027-184">Related topics</span></span>

- [<span data-ttu-id="dc027-185">Teams で組織の Shifts アプリを管理する</span><span class="sxs-lookup"><span data-stu-id="dc027-185">Manage the Shifts app for your organization in Teams</span></span>](manage-the-shifts-app-for-your-organization-in-teams.md)
- [<span data-ttu-id="dc027-186">Teams での PowerShell の概要</span><span class="sxs-lookup"><span data-stu-id="dc027-186">Teams PowerShell overview</span></span>](../../teams-powershell-overview.md)