---
title: Teams でフロントライン ワーカーのシフトベースのアクセスを管理する
author: cichur
ms.author: v-cichur
ms.reviewer: aaku
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 組織内の最前線の従業員向け Teams でシフトベースのアクセスを管理する方法について学習します。
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: 437902136bf72685dabf5bd6359dd6221c7467de
ms.sourcegitcommit: fdef9b52247097e5cae64f01b6b2b710c5b203cf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/20/2021
ms.locfileid: "49909471"
---
# <a name="manage-shift-based-access-for-frontline-workers-in-teams"></a><span data-ttu-id="acf56-103">Teams でフロントライン ワーカーのシフトベースのアクセスを管理する</span><span class="sxs-lookup"><span data-stu-id="acf56-103">Manage shift-based access for Frontline Workers in Teams</span></span>

> [!IMPORTANT]
> <span data-ttu-id="acf56-104">2020 年 6 月 30 日から、Microsoft StaffHub は廃止されました。</span><span class="sxs-lookup"><span data-stu-id="acf56-104">Effective June 30, 2020, Microsoft StaffHub has been retired.</span></span> <span data-ttu-id="acf56-105">Microsoft では、StaffHub の機能を Microsoft Teams に組み込む作業に取り組んでいます。</span><span class="sxs-lookup"><span data-stu-id="acf56-105">We’re building StaffHub capabilities into Microsoft Teams.</span></span> <span data-ttu-id="acf56-106">現在、Teams にはシフト アプリのスケジュール管理機能が含まれています。今後、他の機能もロールアウトされる予定です。</span><span class="sxs-lookup"><span data-stu-id="acf56-106">Today, Teams includes the Shifts app for schedule management and additional capabilities will roll out over time.</span></span> <span data-ttu-id="acf56-107">StaffHub は、2020 年 6 月 30 日にすべてのユーザーの作業を停止しました。</span><span class="sxs-lookup"><span data-stu-id="acf56-107">StaffHub stopped working for all users on June 30, 2020.</span></span> <span data-ttu-id="acf56-108">StaffHub を開しようとすると、Teams のダウンロードを指示するメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="acf56-108">Anyone who tries to open StaffHub is shown a message directing them to download Teams.</span></span> <span data-ttu-id="acf56-109">詳細については [、Microsoft StaffHub の廃止に関するページを参照してください](microsoft-staffhub-to-be-retired.md)。</span><span class="sxs-lookup"><span data-stu-id="acf56-109">To learn more, see [Microsoft StaffHub has been retired](microsoft-staffhub-to-be-retired.md).</span></span>  

## <a name="overview"></a><span data-ttu-id="acf56-110">概要</span><span class="sxs-lookup"><span data-stu-id="acf56-110">Overview</span></span>

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

<span data-ttu-id="acf56-111">Microsoft Teams のプレゼンスは、他のユーザーに対するユーザーの現在の状態を示します。</span><span class="sxs-lookup"><span data-stu-id="acf56-111">Presence in Microsoft Teams indicates a user's current availability and status to other users.</span></span> <span data-ttu-id="acf56-112">フロントライン ワーカーのプレゼンスは、通常、1 日の勤務時間が同じではならず、他のスタッフよりも予測が難しい場合があります。</span><span class="sxs-lookup"><span data-stu-id="acf56-112">The presence of Frontline Workers is often less predictable than other staff as their working hours are typically not the same each day.</span></span> <span data-ttu-id="acf56-113">管理者は、組織内の最前線の従業員がシフトのオンとオフを示すために、シフトベースのプレゼンス状態のセットを表示する Teams を構成できます。</span><span class="sxs-lookup"><span data-stu-id="acf56-113">As an admin, you can configure Teams to show a set of shift-based presence states for the Frontline Workers in your organization to indicate when they are on and off shift.</span></span>

<span data-ttu-id="acf56-114">これらのシフトベースのプレゼンス状態は、緑色の単色のチェック マークで、シフト時のオンシフト &mdash; ![ ](../../media/flw-presence-on-shift.png)  ![ 、x ](../../media/flw-presence-off-shift.png)  ![ ](../../media/flw-presence-busy.png)  &mdash; [](../../presence-admins.md)の灰色の円、オフシフトオフシフト、単色の赤い円、取り込み中が Teams の既定のプレゼンス状態のセットとは別の状態を示します。</span><span class="sxs-lookup"><span data-stu-id="acf56-114">These shift-based presence states&mdash;![Solid green check mark, indicates On shift](../../media/flw-presence-on-shift.png) **On shift**, ![Gray circle with x, indicates Off shift](../../media/flw-presence-off-shift.png) **Off shift**, ![Solid red circle, indicates Busy](../../media/flw-presence-busy.png) **Busy**&mdash;are separate from the [default set of presence states](../../presence-admins.md) in Teams.</span></span> <span data-ttu-id="acf56-115">これら 2 セットのプレゼンス状態では、その役割に基づいて組織内のユーザーに異なるエクスペリエンスを構成できます。</span><span class="sxs-lookup"><span data-stu-id="acf56-115">With these two sets of presence states, you can configure different experiences for people in your organization based on their role.</span></span>

<span data-ttu-id="acf56-116">シフトベースのアクセスでは、Frontline Worker がシフトオフのときに Teams へのアクセスを管理できます。</span><span class="sxs-lookup"><span data-stu-id="acf56-116">With shift-based access, you can manage access to Teams when Frontline Workers are off shift.</span></span> <span data-ttu-id="acf56-117">たとえば、スケジュールされたシフトに参加していない場合に、フロントライン ワーカーが Teams を使用する前に認識する必要があるメッセージを表示する Teams を設定できます。</span><span class="sxs-lookup"><span data-stu-id="acf56-117">For example, you can set Teams to display a message that Frontline Workers must acknowledge before they can use Teams when they're not on a scheduled shift.</span></span>  

## <a name="scenario"></a><span data-ttu-id="acf56-118">シナリオ</span><span class="sxs-lookup"><span data-stu-id="acf56-118">Scenario</span></span>

<span data-ttu-id="acf56-119">組織でシフトベースのアクセスを管理する方法の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="acf56-119">Here's an example of how your organization can manage shift-based access.</span></span>

<span data-ttu-id="acf56-120">組織内に Frontline Worker がいて、マネージャーがスケジュールして承認したシフトで作業する時間に対する支払いのみを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="acf56-120">You have Frontline Workers in your organization that should only be paid for hours they work on a shift that their manager scheduled and approved.</span></span> <span data-ttu-id="acf56-121">Teams アプリの使用を含む、スケジュールされたシフトの外で作業に費やした時間に対する支払いを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="acf56-121">They shouldn't be paid for time spent working outside a scheduled shift, which includes using the Teams app.</span></span> <span data-ttu-id="acf56-122">"オフ シフト時の Teams の時間は支払い時間にカウントされません" というカスタム メッセージを設定すると、Frontline Worker がシフト外のときに Teams にアクセスしようとするときに表示されます。</span><span class="sxs-lookup"><span data-stu-id="acf56-122">You set up a custom message that says "Your time on Teams when on off shift won't count toward payable hours", which is displayed when Frontline Workers try to access Teams when off shift.</span></span> <span data-ttu-id="acf56-123">Teams の使用を選択した場合は、[この時間の支払いは行えなという理解で承諾する] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="acf56-123">If they choose to use Teams, they click **I accept** with the understanding that they won't be paid for this time.</span></span>

<span data-ttu-id="acf56-124">また、組織内に、サラリーマンやシフトを働かしない情報提供者もいます。</span><span class="sxs-lookup"><span data-stu-id="acf56-124">You also have information workers in your organization who are salaried and who don't work shifts.</span></span> <span data-ttu-id="acf56-125">Teams で既定のプレゼンス状態を使用し、フロントライン ワーカーにシフトベースのプレゼンスを提供する情報ワーカーを構成します。</span><span class="sxs-lookup"><span data-stu-id="acf56-125">You configure your information workers to use the default presence states in Teams while giving your Frontline Workers shift-based presence.</span></span>

## <a name="shift-based-presence-states"></a><span data-ttu-id="acf56-126">シフトベースのプレゼンス状態</span><span class="sxs-lookup"><span data-stu-id="acf56-126">Shift-based presence states</span></span>

<span data-ttu-id="acf56-127">シフトベースのプレゼンス状態は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="acf56-127">Here are the shift-based presence states.</span></span>

|<span data-ttu-id="acf56-128">アプリが設定</span><span class="sxs-lookup"><span data-stu-id="acf56-128">App configured</span></span> |<span data-ttu-id="acf56-129">ユーザーが設定</span><span class="sxs-lookup"><span data-stu-id="acf56-129">User configured</span></span>  |<span data-ttu-id="acf56-130">詳細情報</span><span class="sxs-lookup"><span data-stu-id="acf56-130">More information</span></span>  |
|---------|---------|---------|
|![緑色の単色のチェック マーク、シフト時を示す](../../media/flw-presence-on-shift.png) <span data-ttu-id="acf56-132">シフト時</span><span class="sxs-lookup"><span data-stu-id="acf56-132">On shift</span></span>     |         |<span data-ttu-id="acf56-133">シフトの最初に自動的に設定する</span><span class="sxs-lookup"><span data-stu-id="acf56-133">Automatically set at the start of a shift</span></span>         |
|![x を含む灰色の円はオフ シフトを示します](../../media/flw-presence-off-shift.png) <span data-ttu-id="acf56-135">オフ シフト</span><span class="sxs-lookup"><span data-stu-id="acf56-135">Off shift</span></span>     |         |<span data-ttu-id="acf56-136">シフトの最後に自動的に設定する</span><span class="sxs-lookup"><span data-stu-id="acf56-136">Automatically set at the end of a shift</span></span>         |
|![塗りつぶした赤い丸は、取り込み中を示す](../../media/flw-presence-busy.png) <span data-ttu-id="acf56-138">取り込み中</span><span class="sxs-lookup"><span data-stu-id="acf56-138">Busy</span></span>      | ![塗りつぶした赤い丸は、取り込み中を示す](../../media/flw-presence-busy.png) <span data-ttu-id="acf56-140">取り込み中</span><span class="sxs-lookup"><span data-stu-id="acf56-140">Busy</span></span>         |<span data-ttu-id="acf56-141">自動的に設定されます。</span><span class="sxs-lookup"><span data-stu-id="acf56-141">Automatically set.</span></span> <span data-ttu-id="acf56-142">また、最前線の従業員がシフトに入った場合に手動で設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="acf56-142">Can also be manually set when the Frontline Worker is on shift.</span></span>|

## <a name="off-shift-access-to-teams"></a><span data-ttu-id="acf56-143">Teams へのシフトアクセスをオフにする</span><span class="sxs-lookup"><span data-stu-id="acf56-143">Off shift access to Teams</span></span>

<span data-ttu-id="acf56-144">この機能を使用すると、Frontline Worker がシフトオフのときに Teams へのアクセスを管理できます。</span><span class="sxs-lookup"><span data-stu-id="acf56-144">This feature lets you manage access to Teams when Frontline Workers are off shift.</span></span> <span data-ttu-id="acf56-145">シフト外に Teams にアクセスする場合は、Frontline Worker にメッセージを表示する Teams を設定できます。</span><span class="sxs-lookup"><span data-stu-id="acf56-145">You can set Teams to display a message to Frontline Workers if they access Teams when off shift.</span></span> <span data-ttu-id="acf56-146">フロントライン ワーカーは、Teams を **使用する前に、[** 承諾] をクリックしてメッセージを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="acf56-146">Frontline Workers must click **I accept** to acknowledge the message before they can use Teams.</span></span>

<span data-ttu-id="acf56-147">既定のメッセージを使用したり、事前に定義されたメッセージのセットから選択したり、メッセージをカスタマイズして必要なテキストを表示することができます。</span><span class="sxs-lookup"><span data-stu-id="acf56-147">You can use the default message, choose from a set of pre-defined messages, or customize the message to display any text that you want.</span></span> <span data-ttu-id="acf56-148">既定のメッセージを次に示します。</span><span class="sxs-lookup"><span data-stu-id="acf56-148">Here's the default message:</span></span>

![既定のメッセージのスクリーンショット](../../media/shifts-presence-message.png)

<span data-ttu-id="acf56-150">また、メッセージが表示される頻度を設定し、最初のシフトの開始または最後のシフトの終了から Teams へのアクセスが制限される期間の猶予期間を設定できます。</span><span class="sxs-lookup"><span data-stu-id="acf56-150">You can also set the frequency when the message is displayed and set a grace period between when the first shift starts or last shift ends and when access to Teams is restricted.</span></span>

## <a name="manage-shift-based-access"></a><span data-ttu-id="acf56-151">シフトベースのアクセスを管理する</span><span class="sxs-lookup"><span data-stu-id="acf56-151">Manage shift-based access</span></span>

<span data-ttu-id="acf56-152">管理者はポリシーを使用して、組織内のフロントライン ワーカーのシフトベースのプレゼンスを制御します。</span><span class="sxs-lookup"><span data-stu-id="acf56-152">As an admin, you use policies to control shift-based presence for Frontline Workers in your organization.</span></span> <span data-ttu-id="acf56-153">これらのポリシーを管理するには、次の PowerShell コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="acf56-153">You manage these policies by using the following PowerShell cmdlets:</span></span>

- [<span data-ttu-id="acf56-154">New-CsTeamsShiftsPolicy</span><span class="sxs-lookup"><span data-stu-id="acf56-154">New-CsTeamsShiftsPolicy</span></span>](https://docs.microsoft.com/powershell/module/teams/new-csteamsshiftspolicy)
- [<span data-ttu-id="acf56-155">Get-CsTeamsShiftsPolicy</span><span class="sxs-lookup"><span data-stu-id="acf56-155">Get-CsTeamsShiftsPolicy</span></span>](https://docs.microsoft.com/powershell/module/teams/get-csteamsshiftspolicy)
- [<span data-ttu-id="acf56-156">Set-CsTeamsShiftsPolicy</span><span class="sxs-lookup"><span data-stu-id="acf56-156">Set-CsTeamsShiftsPolicy</span></span>](https://docs.microsoft.com/powershell/module/teams/set-csteamsshiftspolicy)
- [<span data-ttu-id="acf56-157">Grant-CsTeamsShiftsPolicy</span><span class="sxs-lookup"><span data-stu-id="acf56-157">Grant-CsTeamsShiftsPolicy</span></span>](https://docs.microsoft.com/powershell/module/teams/grant-csteamsshiftspolicy)
- [<span data-ttu-id="acf56-158">Remove-CsTeamsShiftsPolicy</span><span class="sxs-lookup"><span data-stu-id="acf56-158">Remove-CsTeamsShiftsPolicy</span></span>](https://docs.microsoft.com/powershell/module/teams/remove-csteamsshiftspolicy)

<span data-ttu-id="acf56-159">New-CsTeamsShiftsPolicyコマンドレットを使用して新しいポリシーを作成し、必要なポリシー設定を設定し、Grant-CsTeamsShiftsPolicy コマンドレットを使用してユーザーにポリシーを割り当てる。</span><span class="sxs-lookup"><span data-stu-id="acf56-159">Use the New-CsTeamsShiftsPolicy cmdlet to create a new policy, set the policy settings that you want, and then use the Grant-CsTeamsShiftsPolicy cmdlet to assign the policy to users.</span></span>

<span data-ttu-id="acf56-160">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="acf56-160">Here's some examples.</span></span> <span data-ttu-id="acf56-161">選択できる定義済みのオフシフト メッセージの一覧など、各ポリシー設定とパラメーターの詳細については [、「New-CsTeamsShiftsPolicy」](https://docs.microsoft.com/powershell/module/teams/new-csteamsshiftspolicy)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="acf56-161">For detailed information about each policy setting and parameter, including the list of predefined off shift messages that you can choose from, see [New-CsTeamsShiftsPolicy](https://docs.microsoft.com/powershell/module/teams/new-csteamsshiftspolicy).</span></span>

### <a name="example-1"></a><span data-ttu-id="acf56-162">例 1</span><span class="sxs-lookup"><span data-stu-id="acf56-162">Example 1</span></span>

<span data-ttu-id="acf56-163">この例では、"オフ Shift Teams Access の既定のメッセージ" という名前の新しいポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="acf56-163">In this example, we create a new policy named Off Shift Teams Access Default Message.</span></span> <span data-ttu-id="acf56-164">このポリシーでは、シフトベースのプレゼンスが有効になっていて、このポリシーが割り当てられているユーザーがシフト外のときに Teams にアクセスすると、既定のメッセージが毎回表示されます。</span><span class="sxs-lookup"><span data-stu-id="acf56-164">In this policy, shift-based presence is turned on and the default message is displayed every time a user who is assigned this policy accesses Teams when off shift.</span></span> <span data-ttu-id="acf56-165">ユーザーは、メッセージを受け入れる場合に Teams をオフシフトで使用し、最初のシフトの開始または最後のシフトの終了からアクセスが制限された時間が 10 分の猶予期間を使用できます。</span><span class="sxs-lookup"><span data-stu-id="acf56-165">The user can use Teams when off shift if they accept the message, and the grace period between when the first shift starts or last shift ends and when access is restricted is 10 minutes.</span></span>  

```powershell
New-CsTeamsShiftsPolicy -Identity "Off Shift Teams Access Default Message" -EnableShiftPresence $true -ShiftNoticeFrequency always -ShiftNoticeMessageType DefaultMessage -AccessType UnrestrictedAccess_TeamsApp -AccessGracePeriodMinutes 10
```

> [!NOTE]
> <span data-ttu-id="acf56-166">**ShiftNoticeMessageType パラメーター** を使用して、表示するメッセージを設定します。</span><span class="sxs-lookup"><span data-stu-id="acf56-166">Use the **ShiftNoticeMessageType** parameter to set the message that you want to display.</span></span> <span data-ttu-id="acf56-167">このパラメーターから選択できる定義済みメッセージの一覧を表示するには [、「New-CsTeamsShiftsPolicy」を参照してください](https://docs.microsoft.com/powershell/module/teams/new-csteamsshiftspolicy)。</span><span class="sxs-lookup"><span data-stu-id="acf56-167">To see a list of the pre-defined messages that you can choose from for this parameter, see [New-CsTeamsShiftsPolicy](https://docs.microsoft.com/powershell/module/teams/new-csteamsshiftspolicy).</span></span>

### <a name="example-2"></a><span data-ttu-id="acf56-168">例 2</span><span class="sxs-lookup"><span data-stu-id="acf56-168">Example 2</span></span> 

<span data-ttu-id="acf56-169">この例では、"オフ Shift Teams Access カスタム メッセージ" という名前の新しいポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="acf56-169">In this example, we create a new policy named Off Shift Teams Access Custom Message.</span></span> <span data-ttu-id="acf56-170">このポリシーでは、シフトベースのプレゼンスが有効になっていて、このポリシーが割り当てられているユーザーがシフト外のときに Teams にアクセスすると、毎回カスタム メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="acf56-170">In this policy, shift-based presence is turned on and a custom message is displayed every time a user who is assigned this policy accesses Teams when off shift.</span></span> <span data-ttu-id="acf56-171">ユーザーは、メッセージを受け入れる場合に Teams をオフシフトで使用し、最初のシフトの開始または最後のシフトの終了からアクセスが制限される時間が 15 分の猶予期間を使用できます。</span><span class="sxs-lookup"><span data-stu-id="acf56-171">The user can use Teams when off shift if they accept the message, and the grace period between when the first shift starts or last shift ends and when access is restricted is 15 minutes.</span></span>  

```powershell
New-CsTeamsShiftsPolicy -Identity "Off Shift Teams Access Custom Message" -EnableShiftPresence $true -ShiftNoticeFrequency always -ShiftNoticeMessageType CustomMessage -ShiftNoticeMessageCustom "Your time on Teams when on off shift won't count toward payable hours" -AccessType UnrestrictedAccess_TeamsApp -AccessGracePeriodMinutes 15
```

> [!NOTE]
> <span data-ttu-id="acf56-172">**ShiftNoticeMessageType パラメーター** を使用して、表示するメッセージを設定します。</span><span class="sxs-lookup"><span data-stu-id="acf56-172">Use the **ShiftNoticeMessageType** parameter to set the message that you want to display.</span></span> <span data-ttu-id="acf56-173">詳細については [、New-CsTeamsShiftsPolicy を参照してください](https://docs.microsoft.com/powershell/module/teams/new-csteamsshiftspolicy)。</span><span class="sxs-lookup"><span data-stu-id="acf56-173">To learn more, see [New-CsTeamsShiftsPolicy](https://docs.microsoft.com/powershell/module/teams/new-csteamsshiftspolicy).</span></span>

### <a name="example-3"></a><span data-ttu-id="acf56-174">例 3</span><span class="sxs-lookup"><span data-stu-id="acf56-174">Example 3</span></span>

<span data-ttu-id="acf56-175">この例では、Off Shift Teams Access Message1 という名前の新しいポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="acf56-175">In this example, we create a new policy named Off Shift Teams Access Message1.</span></span> <span data-ttu-id="acf56-176">このポリシーでは、シフトベースのプレゼンスが有効になっていて、このポリシーが割り当てられているユーザーがシフト外のときに Teams にアクセスすると、次の定義済みメッセージが毎回表示されます。</span><span class="sxs-lookup"><span data-stu-id="acf56-176">In this policy, shift-based presence is turned on and the following predefined message is displayed every time a user who is assigned this policy accesses Teams when off shift.</span></span>

  <span data-ttu-id="acf56-177">"雇用主は、非適用従業員または非勤務時間の従業員によるネットワーク、アプリケーション、システム、またはツールの使用を承認または承認していません。</span><span class="sxs-lookup"><span data-stu-id="acf56-177">"Your employer does not authorize or approve of the use of its network, applications, systems, or tools by non-exempt or hourly employees during their non-working hours.</span></span> <span data-ttu-id="acf56-178">受け入れにより、オフシフト中の Teams の使用が承認されていないことと、ユーザーが補償を受け取らなされていないことに同意したと見なされます。"</span><span class="sxs-lookup"><span data-stu-id="acf56-178">By accepting, you acknowledge that your use of Teams while off shift is not authorized and you will not be compensated."</span></span> 

<span data-ttu-id="acf56-179">ユーザーは、メッセージを受け入れる場合に Teams をオフシフトで使用し、最初のシフトの開始または最後のシフトの終了からアクセスが制限される時間が 3 分の猶予期間を使用できます。</span><span class="sxs-lookup"><span data-stu-id="acf56-179">The user can use Teams when off shift if they accept the message, and the grace period between when the first shift starts or last shift ends and when access is restricted is three minutes.</span></span>  

```powershell
New-CsTeamsShiftsPolicy -Identity "Off Shift Teams Access Message1" -EnableShiftPresence $true -ShiftNoticeFrequency always -ShiftNoticeMessageType Message1 -AccessType  UnrestrictedAccess_TeamsApp -AccessGracePeriodMinutes 3
```

> [!NOTE]
> <span data-ttu-id="acf56-180">**ShiftNoticeMessageType パラメーター** を使用して、表示するメッセージを設定します。</span><span class="sxs-lookup"><span data-stu-id="acf56-180">Use the **ShiftNoticeMessageType** parameter to set the message that you want to display.</span></span> <span data-ttu-id="acf56-181">このパラメーターから選択できる定義済みメッセージの一覧を表示するには [、「New-CsTeamsShiftsPolicy」を参照してください](https://docs.microsoft.com/powershell/module/teams/new-csteamsshiftspolicy)。</span><span class="sxs-lookup"><span data-stu-id="acf56-181">To see a list of the pre-defined messages that you can choose from for this parameter, see [New-CsTeamsShiftsPolicy](https://docs.microsoft.com/powershell/module/teams/new-csteamsshiftspolicy).</span></span>

### <a name="example-4"></a><span data-ttu-id="acf56-182">例 4</span><span class="sxs-lookup"><span data-stu-id="acf56-182">Example 4</span></span>

<span data-ttu-id="acf56-183">この例では、"オフ Shift Teams Access カスタム メッセージ" という名前のポリシーを remy@contoso.com という名前のユーザーに割り当remy@contoso.com。</span><span class="sxs-lookup"><span data-stu-id="acf56-183">In this example, we assign a policy named Off Shift Teams Access Custom Message to a user named remy@contoso.com.</span></span>

```powershell
Grant-CsTeamsShiftsPolicy -Identity remy@contoso.com -PolicyName "Off Shift Teams Access Custom Message"
```

## <a name="related-topics"></a><span data-ttu-id="acf56-184">関連項目</span><span class="sxs-lookup"><span data-stu-id="acf56-184">Related topics</span></span>

- [<span data-ttu-id="acf56-185">Teams で組織の Shifts アプリを管理する</span><span class="sxs-lookup"><span data-stu-id="acf56-185">Manage the Shifts app for your organization in Teams</span></span>](manage-the-shifts-app-for-your-organization-in-teams.md)
- [<span data-ttu-id="acf56-186">Teams での PowerShell の概要</span><span class="sxs-lookup"><span data-stu-id="acf56-186">Teams PowerShell overview</span></span>](../../teams-powershell-overview.md)
