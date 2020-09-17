---
title: Skype for Business オンプレミス展開から Teams へのアップグレード - Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 10/22/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: Skype for Business から Teams へのアップグレード
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 887ab004ae913ee2171f1894bd5fc4a44845881f
ms.sourcegitcommit: b07938c0b6edafacaeaaef205a1be00c4c1693ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/16/2020
ms.locfileid: "47940724"
---
# <a name="implement-your-upgrade-from-skype-for-business-to-teams-mdash-for-it-administrators"></a><span data-ttu-id="d7d31-103">Skype for Business から &mdash; IT 管理者向けの Teams にアップグレードを実装する</span><span class="sxs-lookup"><span data-stu-id="d7d31-103">Implement your upgrade from Skype for Business to Teams &mdash; for IT administrators</span></span>

<span data-ttu-id="d7d31-104">この記事では、アップグレードを実装する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d7d31-104">This article describes how to implement your upgrade.</span></span> <span data-ttu-id="d7d31-105">この記事では、IT 管理者向けのアップグレードの概念と実装について説明します。</span><span class="sxs-lookup"><span data-stu-id="d7d31-105">This article is the fifth of several that describe upgrade concepts and implementation for IT administrators.</span></span>  

- [<span data-ttu-id="d7d31-106">概要</span><span class="sxs-lookup"><span data-stu-id="d7d31-106">Overview</span></span>](upgrade-to-teams-on-prem-overview.md)
- [<span data-ttu-id="d7d31-107">アップグレード方法</span><span class="sxs-lookup"><span data-stu-id="d7d31-107">Upgrade methods</span></span>](upgrade-to-teams-on-prem-upgrade-methods.md)
- [<span data-ttu-id="d7d31-108">アップグレードを管理するためのツール</span><span class="sxs-lookup"><span data-stu-id="d7d31-108">Tools for managing your upgrade</span></span>](upgrade-to-teams-on-prem-tools.md)
- [<span data-ttu-id="d7d31-109">Skype for Business オンプレミスの組織に関するその他の考慮事項</span><span class="sxs-lookup"><span data-stu-id="d7d31-109">Additional considerations for organizations with Skype for Business on-premises</span></span>](upgrade-to-teams-on-prem-considerations.md)
- <span data-ttu-id="d7d31-110">**アップグレードを実装する** (この記事)</span><span class="sxs-lookup"><span data-stu-id="d7d31-110">**Implement your upgrade** (this article)</span></span>
- [<span data-ttu-id="d7d31-111">公衆交換電話網 (PSTN) に関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="d7d31-111">Public Switched Telephone Network (PSTN) considerations</span></span>](upgrade-to-teams-on-prem-pstn-considerations.md)

<span data-ttu-id="d7d31-112">さらに、次の記事では、アップグレードの重要な概念と共存の動作について説明します。</span><span class="sxs-lookup"><span data-stu-id="d7d31-112">In addition, the following articles describe important upgrade concepts and coexistence behaviors:</span></span>

- [<span data-ttu-id="d7d31-113">Teams と Skype for Business の共存</span><span class="sxs-lookup"><span data-stu-id="d7d31-113">Coexistence of Teams and Skype for Business</span></span>](upgrade-to-teams-on-prem-coexistence.md)
- [<span data-ttu-id="d7d31-114">共存モード-参照</span><span class="sxs-lookup"><span data-stu-id="d7d31-114">Coexistence modes - Reference</span></span>](migration-interop-guidance-for-teams-with-skype.md)
- [<span data-ttu-id="d7d31-115">Teams のクライアント エクスペリエンスおよび共存モードへの準拠</span><span class="sxs-lookup"><span data-stu-id="d7d31-115">Teams client experience and conformance to coexistence modes</span></span>](teams-client-experience-and-conformance-to-coexistence-modes.md)

## <a name="upgrade-options"></a><span data-ttu-id="d7d31-116">アップグレード方法</span><span class="sxs-lookup"><span data-stu-id="d7d31-116">Upgrade options</span></span>

<span data-ttu-id="d7d31-117">このセクションでは、次のアップグレードオプションのいずれかを使用してアップグレードを実装する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d7d31-117">This section describes how to implement your upgrade by using one of the following upgrade options:</span></span>

- [<span data-ttu-id="d7d31-118">機能のアップグレード (孤島モードを使用)</span><span class="sxs-lookup"><span data-stu-id="d7d31-118">Overlapping capabilities upgrade (using Islands mode)</span></span>](#overlapping-capabilities-upgrade-using-islands-mode)
- [<span data-ttu-id="d7d31-119">Teams の使用を開始していない組織の select 機能アップグレード</span><span class="sxs-lookup"><span data-stu-id="d7d31-119">A select capabilities upgrade for an organization that has not yet started using Teams</span></span>](#a-select-capabilities-upgrade-for-an-organization-that-has-not-yet-started-using-teams)
- [<span data-ttu-id="d7d31-120">既に孤島モードで Teams を使用している組織の select 機能アップグレード</span><span class="sxs-lookup"><span data-stu-id="d7d31-120">A select capabilities upgrade for an organization that is already using Teams in Islands mode</span></span>](#a-select-capabilities-upgrade-for-an-organization-that-is-already-using-teams-in-islands-mode)

<span data-ttu-id="d7d31-121">オプションに関する詳細情報が必要な場合は、 [アップグレード方法](upgrade-to-teams-on-prem-upgrade-methods.md)が既読であることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="d7d31-121">If you need more information about the options, make sure you have already read [Upgrade methods](upgrade-to-teams-on-prem-upgrade-methods.md).</span></span>

## <a name="overlapping-capabilities-upgrade-using-islands-mode"></a><span data-ttu-id="d7d31-122">機能のアップグレード (孤島モードを使用)</span><span class="sxs-lookup"><span data-stu-id="d7d31-122">Overlapping capabilities upgrade (using Islands mode)</span></span>

<span data-ttu-id="d7d31-123">重複機能のアップグレードオプションの場合:</span><span class="sxs-lookup"><span data-stu-id="d7d31-123">For the overlapping capabilities upgrade option:</span></span>

- <span data-ttu-id="d7d31-124">組織全体の迅速なアップグレードを行うことができる場合は、このオプションを検討します。</span><span class="sxs-lookup"><span data-stu-id="d7d31-124">Consider this option if you can do a fast upgrade for your overall organization.</span></span>  <span data-ttu-id="d7d31-125">エンドユーザーが両方のクライアントを実行しても混乱する可能性があるため、ユーザーが両方のクライアントを実行するために必要な時間を最小限に抑えることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d7d31-125">Since there is potential risk of confusion for end users with running both clients, it’s best if you can minimize the time period during which users must run both clients.</span></span> <span data-ttu-id="d7d31-126">管理者は、両方のクライアントを実行することをユーザーに周知する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d7d31-126">You should ensure your users know to run both clients.</span></span>

- <span data-ttu-id="d7d31-127">このオプションは、既定のモデルであり、Microsoft 365 または Office 365 ライセンスを割り当てることを除いて、管理者による操作を必要としません。</span><span class="sxs-lookup"><span data-stu-id="d7d31-127">This option is the out-of-the box model, and doesn’t require administrator action to get started with Teams except to assign the Microsoft 365 or Office 365 license.</span></span> <span data-ttu-id="d7d31-128">ユーザーが既に Skype for Business Online を使用している場合は、このモデルを既に使用している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d7d31-128">If your users already have Skype for Business Online, you may already be in this model.</span></span>

- <span data-ttu-id="d7d31-129">機能のオーバーラップモードの使用を終了して、TeamsOnly に移動することは難しい場合があります。</span><span class="sxs-lookup"><span data-stu-id="d7d31-129">It can be challenging getting out of overlapping capabilities mode and moving to TeamsOnly.</span></span> <span data-ttu-id="d7d31-130">アップグレード済みのユーザーは Teams でのみ通信するため、そのユーザーと通信する組織内の他のユーザーはすべて Teams を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d7d31-130">Because upgraded users only communicate via Teams, any other user in the organization communicating with that user must be using Teams.</span></span>  <span data-ttu-id="d7d31-131">Teams を使用し始めていないユーザーがいる場合、メッセージを受け取れない可能性が生じます。</span><span class="sxs-lookup"><span data-stu-id="d7d31-131">If you have users that have not started using Teams, they will be exposed to missing messages.</span></span> <span data-ttu-id="d7d31-132">さらに、そのようなユーザーには、オンラインの TeamsOnly ユーザーが Skype for Business に表示されません。</span><span class="sxs-lookup"><span data-stu-id="d7d31-132">Furthermore, they won’t see the TeamsOnly users online in Skype for Business.</span></span> <span data-ttu-id="d7d31-133">一部の組織では、テナントのグローバルポリシーを使用してテナント全体のアップグレードを実行します。ただし、これを回避するには、事前の計画と、すべてのユーザーがアップグレードの準備ができているまで待機する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d7d31-133">Some organizations choose to do a tenant-wide upgrade using the Tenant global policy to avoid this, however that requires upfront planning as well as waiting until all users are ready to be upgraded.</span></span>


## <a name="a-select-capabilities-upgrade-for-an-organization-that-has-not-yet-started-using-teams"></a><span data-ttu-id="d7d31-134">Teams の使用を開始していない組織の select 機能アップグレード</span><span class="sxs-lookup"><span data-stu-id="d7d31-134">A select capabilities upgrade for an organization that has not yet started using Teams</span></span>

<span data-ttu-id="d7d31-135">Teams のアクティブなユーザーが 1 人もいない組織の場合、最初のステップとして、テナント全体に対する TeamsUpgradePolicy の既定のポリシーを、Skype for Business のモードの 1 つ (SfbWithTeamsCollab など) に設定します。</span><span class="sxs-lookup"><span data-stu-id="d7d31-135">If your organization does not yet have any active users in Teams, the first step is to set the default tenant-wide policy for TeamsUpgradePolicy to one of the Skype for Business modes, for example, SfbWithTeamsCollab.</span></span>  <span data-ttu-id="d7d31-136">Teams を使用し始めていないユーザーは、動作の違いに気付きません。</span><span class="sxs-lookup"><span data-stu-id="d7d31-136">Users who have not yet started using Teams won’t notice any difference in behavior.</span></span> <span data-ttu-id="d7d31-137">それでも、テナント レベルでこのポリシーを設定すると、TeamsOnly モードへのユーザーのアップグレードを開始でき、さらに、アップグレード済みユーザーはまだアップグレードしていないユーザーとの通信を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="d7d31-137">However, setting this policy at the tenant level makes it possible to start upgrading users to TeamsOnly mode, and ensures that the upgraded users can still communicate with non-upgraded users.</span></span>  <span data-ttu-id="d7d31-138">パイロット ユーザーを特定したら、それらのユーザーを TeamsOnly にアップグレードできます。</span><span class="sxs-lookup"><span data-stu-id="d7d31-138">Once you have identified your pilot users you can upgrade them to TeamsOnly.</span></span>  <span data-ttu-id="d7d31-139">そのユーザーがオンプレミスの場合は、Move-CsUser を使用します。</span><span class="sxs-lookup"><span data-stu-id="d7d31-139">If they are on-premises, use Move-CsUser.</span></span> <span data-ttu-id="d7d31-140">オンラインになっている場合は、CsTeamsUpgradePolicy を使用してチームメンバーのみを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="d7d31-140">If they are online, simply assign them TeamsOnly mode by using Grant-CsTeamsUpgradePolicy.</span></span> <span data-ttu-id="d7d31-141">既定で、これらのユーザーによってスケジュールされている Skype for Business 会議は、Teams に移行されます。</span><span class="sxs-lookup"><span data-stu-id="d7d31-141">By default, any Skype for Business meetings scheduled by these users will be migrated to Teams.</span></span>

<span data-ttu-id="d7d31-142">主なコマンドを次に示します。</span><span class="sxs-lookup"><span data-stu-id="d7d31-142">Following are the key commands:</span></span>

1. <span data-ttu-id="d7d31-143">次のようにして、テナント全体の既定値をモードの SfbWithTeamsCollab に設定します。</span><span class="sxs-lookup"><span data-stu-id="d7d31-143">Set the tenant-wide default to mode SfbWithTeamsCollab as follows:</span></span>

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -PolicyName SfbWithTeamsCollab -Global
   ```

2. <span data-ttu-id="d7d31-144">パイロットユーザーを teams にアップグレードするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="d7d31-144">Upgrade the pilot users to TeamsOnly as follows:</span></span>

   - <span data-ttu-id="d7d31-145">オンラインのユーザーの場合:</span><span class="sxs-lookup"><span data-stu-id="d7d31-145">For a user who is online:</span></span>

     ```PowerShell
     Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $username 
     ```

   - <span data-ttu-id="d7d31-146">オンプレミスのユーザーの場合:</span><span class="sxs-lookup"><span data-stu-id="d7d31-146">For a user who is on-premises:</span></span>

     ```PowerShell
     Move-CsUser -identity $user -Target sipfed.online.lync.com -MoveToTeams -credential $cred 
     ```

<span data-ttu-id="d7d31-147">メモ</span><span class="sxs-lookup"><span data-stu-id="d7d31-147">Notes</span></span>
 
- <span data-ttu-id="d7d31-148">テナント全体のポリシーを SfbWithTeamsCollab に設定する代わりに、SfbWithTeamsCollabAndMeetings に設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="d7d31-148">Instead of setting the tenant-wide policy to SfbWithTeamsCollab, you could set it to SfbWithTeamsCollabAndMeetings.</span></span> <span data-ttu-id="d7d31-149">そのようにすると、すべてのユーザーが新しい会議すべてを Teams でスケジュールするようになります。</span><span class="sxs-lookup"><span data-stu-id="d7d31-149">This causes all users to schedule all new meetings in Teams.</span></span>
- <span data-ttu-id="d7d31-150">`Move-CsUser` は、オンプレミスツールのコマンドレットです。</span><span class="sxs-lookup"><span data-stu-id="d7d31-150">`Move-CsUser` is a cmdlet in the on-premises tools.</span></span> <span data-ttu-id="d7d31-151">このスイッチを使用するには、 `MoveToTeams` CU8 以降の skype For Business server 2019 または skype For Business server 2015 が必要です。</span><span class="sxs-lookup"><span data-stu-id="d7d31-151">The `MoveToTeams` switch requires Skype for Business Server 2019 or Skype for Business Server 2015 with CU8 or later.</span></span> <span data-ttu-id="d7d31-152">以前のバージョンを使用している場合は、最初にユーザーを Skype for Business Online に移行してから、そのユーザーに TeamsOnly モードを付与できます。</span><span class="sxs-lookup"><span data-stu-id="d7d31-152">If you are using a prior version, you can first move the user to Skype for Business Online, and then grant TeamsOnly mode to that user.</span></span>
- <span data-ttu-id="d7d31-153">既定で、TeamsOnly モードへのアップグレードや SfbWithTeamsCollabAndMeetings モードの割り当てを実行すると、Skype for Business 会議は Teams に移行されます。</span><span class="sxs-lookup"><span data-stu-id="d7d31-153">By default, Skype for Business meetings are migrated to Teams when upgrading to TeamsOnly mode or when assigning SfbWithTeamsCollabAndMeetings mode.</span></span>  

<span data-ttu-id="d7d31-154">次の図は、Teams の使用を前に使用していない組織の選択機能アップグレードの概念フェーズを示しています。</span><span class="sxs-lookup"><span data-stu-id="d7d31-154">The diagram below shows the conceptual phases of select capabilities upgrade for an organization with no prior usage of Teams.</span></span> <span data-ttu-id="d7d31-155">バーの高さは、ユーザー数を表します。</span><span class="sxs-lookup"><span data-stu-id="d7d31-155">The height of the bars represents number of users.</span></span> <span data-ttu-id="d7d31-156">アップグレードのどのフェーズでも、すべてのユーザーが相互に通信できます。</span><span class="sxs-lookup"><span data-stu-id="d7d31-156">During any phase of the upgrade, all users can communicate with each other.</span></span>  <span data-ttu-id="d7d31-157">Skype for Business ユーザーは TeamsOnly ユーザーと相互運用を使用して通信します。逆の場合も同様です。</span><span class="sxs-lookup"><span data-stu-id="d7d31-157">Skype for Business users communicate with TeamsOnly users using Interop, and vice versa.</span></span> <span data-ttu-id="d7d31-158">島々モードのユーザーは、両方のクライアントを確実に実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d7d31-158">Users in Islands mode must be sure to run both clients.</span></span>

![チームを以前に使用していない、選択された機能アップグレードを示す図](media/teams-upgrade-1.png)


## <a name="a-select-capabilities-upgrade-for-an-organization-that-is-already-using-teams-in-islands-mode"></a><span data-ttu-id="d7d31-160">既に孤島モードで Teams を使用している組織の select 機能アップグレード</span><span class="sxs-lookup"><span data-stu-id="d7d31-160">A select capabilities upgrade for an organization that is already using Teams in Islands mode</span></span>

<span data-ttu-id="d7d31-161">組織内の一部のユーザーが Teams をアイランド モードでアクティブに使用している場合、既存のユーザーから機能を削除することは望ましくない場合があります。</span><span class="sxs-lookup"><span data-stu-id="d7d31-161">If some users in your organization are actively using Teams in Islands mode, you probably do not want to remove functionality from existing users.</span></span> <span data-ttu-id="d7d31-162">その場合、テナント全体のポリシーを変更する前に、もう 1 つステップが必要になります。</span><span class="sxs-lookup"><span data-stu-id="d7d31-162">Therefore, an extra step is required before changing the tenant-wide policy.</span></span> <span data-ttu-id="d7d31-163">この問題の解決策は、テナント全体のポリシーを SfbWithTeamsCollab に設定する前に、既存のアクティブな Teams ユーザーをアイランド モードで grandfather 化することです。</span><span class="sxs-lookup"><span data-stu-id="d7d31-163">The solution is to “grandfather” these existing active Teams users into Islands mode, before setting the tenant-wide policy to SfbWithTeamsCollab.</span></span>  <span data-ttu-id="d7d31-164">これが完了したら、上述のように展開を実行できます。ただし、TeamsOnly に移行する 2 グループのユーザーが存在することになります。つまり、Teams でアクティブだったユーザーはアイランド モードになり、残りのユーザーは SfbWithTeamsCollab モードになります。</span><span class="sxs-lookup"><span data-stu-id="d7d31-164">Once you’ve done that, you can proceed with deployment as above, however, you’ll have two groups of users who are moving to TeamsOnly:  the users who were active in Teams will be in Islands mode, and the remaining users will be in SfbWithTeamsCollab mode.</span></span> <span data-ttu-id="d7d31-165">管理者は、これらのユーザーを TeamsOnly モードに段階的に移行できます。</span><span class="sxs-lookup"><span data-stu-id="d7d31-165">You can progressively move these users to TeamsOnly mode.</span></span>

1. <span data-ttu-id="d7d31-166">Teams でアクティブなユーザーを見つけるには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="d7d31-166">Find users who are active in Teams as follows:</span></span>

   1. <span data-ttu-id="d7d31-167">Microsoft 365 管理センターの左側のナビゲーションで、[レポート]、[使用状況] の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="d7d31-167">From the Microsoft 365 admin center, in the left-hand navigation, go to Reports, and then Usage.</span></span> 
   2. <span data-ttu-id="d7d31-168">[レポートの選択] ドロップダウンで、[Microsoft Teams]、[ユーザー アクティビティ] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="d7d31-168">In the “Select a report” dropdown, choose Microsoft Teams, and then User Activity.</span></span> <span data-ttu-id="d7d31-169">このようにすると、Teams でアクティブになっているユーザーのエクスポート可能なテーブルが提供されます。</span><span class="sxs-lookup"><span data-stu-id="d7d31-169">This will provide an exportable table of users who have been active in Teams.</span></span> 
   3. <span data-ttu-id="d7d31-170">[エクスポート] をクリックして、Excel を開き、フィルタリングして、Teams でアクティブなユーザーのみを表示します。</span><span class="sxs-lookup"><span data-stu-id="d7d31-170">Click Export, open Excel, and filter to show only the users who are active in Teams.</span></span>

2. <span data-ttu-id="d7d31-171">ステップ 1 で見つかったアクティブな Teams ユーザーそれぞれに対して、リモート PowerShell でアイランド モードを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="d7d31-171">For each active Teams user found in step 1, assign them Islands mode in remote PowerShell.</span></span> <span data-ttu-id="d7d31-172">これで次のステップに進むことができます。ユーザー エクスペリエンスは変更されません。</span><span class="sxs-lookup"><span data-stu-id="d7d31-172">This allows you to go to the next step, and ensures you don’t change the user experience.</span></span>  

   ```PowerShell
   $users=get-content “C:\MyPath\users.txt” 
    foreach ($user in $users){ 
    Grant-CsTeamsUpgradePolicy -identity $user -PolicyName Islands} 
   ```

3. <span data-ttu-id="d7d31-173">テナント全体のポリシーを SfbWithTeamsCollab に設定します。</span><span class="sxs-lookup"><span data-stu-id="d7d31-173">Set the tenant-wide policy to SfbWithTeamsCollab:</span></span>

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -Global -PolicyName SfbWithTeamsCollab 
   ```

4. <span data-ttu-id="d7d31-174">選択したユーザーを TeamsOnly モードにアップグレードします。</span><span class="sxs-lookup"><span data-stu-id="d7d31-174">Upgrade selected users to TeamsOnly mode.</span></span> <span data-ttu-id="d7d31-175">ユーザーがアイランド モードの場合に生じる可能性のある混乱を最小限に抑えるため、アイランド モードのユーザーを優先的にまずアップグレードすることが望ましい場合もありますが、アイランド モードのユーザーと SfbWithTeamsCollab モードのユーザーのどちらをアップグレードするかは管理者が選択できます。</span><span class="sxs-lookup"><span data-stu-id="d7d31-175">You can choose to upgrade either users in Islands mode or SfbWithTeamsCollab mode, although you might want to prioritize upgrading the users in Islands mode first to minimize the potential for confusion that can arise when users are in Islands mode.</span></span>   

   <span data-ttu-id="d7d31-176">Skype for Business Online に所属しているユーザーの場合:</span><span class="sxs-lookup"><span data-stu-id="d7d31-176">For users homed in Skype for Business Online:</span></span>  

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName UpgradeToTeams 
   ```

   <span data-ttu-id="d7d31-177">Skype for Business Server オンプレミスに所属しているユーザーの場合:</span><span class="sxs-lookup"><span data-stu-id="d7d31-177">For users homed in Skype for Business Server on-premises:</span></span>  

   ```PowerShell
   Move-CsUser -Identity $user -Target sipfed.online.lync.com -MoveToTeams -credential $cred 
   ```

<span data-ttu-id="d7d31-178">次の図は、アクティブな孤島ユーザーが開始時にある select 機能移行の概念フェーズを示しています。</span><span class="sxs-lookup"><span data-stu-id="d7d31-178">The diagram below shows the conceptual phases of a select capabilities transition in which there are active Islands users at the start.</span></span> <span data-ttu-id="d7d31-179">バーの高さは、ユーザー数を表します。</span><span class="sxs-lookup"><span data-stu-id="d7d31-179">The height of the bars represents the number of users.</span></span> <span data-ttu-id="d7d31-180">アップグレードのどのフェーズでも、すべてのユーザーが相互に通信できます。</span><span class="sxs-lookup"><span data-stu-id="d7d31-180">During any phase of the upgrade, all users can communicate with each other.</span></span>  <span data-ttu-id="d7d31-181">Skype for Business ユーザーは TeamsOnly ユーザーと相互運用を使用して通信します。逆の場合も同様です。</span><span class="sxs-lookup"><span data-stu-id="d7d31-181">Skype for Business users communicate with TeamsOnly users using interop, and vice versa.</span></span> 


![島々モードでアクティブなユーザーとの選択機能のアップグレードを示す図](media/teams-upgrade-2.png)

   



## <a name="related-links"></a><span data-ttu-id="d7d31-183">関連リンク</span><span class="sxs-lookup"><span data-stu-id="d7d31-183">Related links</span></span>

[<span data-ttu-id="d7d31-184">Teams を Skype for Business と一緒に使用する組織向けの移行と相互運用に関するガイダンス</span><span class="sxs-lookup"><span data-stu-id="d7d31-184">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](migration-interop-guidance-for-teams-with-skype.md) 

[<span data-ttu-id="d7d31-185">Skype for Business Server と Microsoft 365 または Office 365 間のハイブリッド接続を構成する</span><span class="sxs-lookup"><span data-stu-id="d7d31-185">Configure hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[<span data-ttu-id="d7d31-186">オンプレミスとクラウドの間でユーザーを移動する</span><span class="sxs-lookup"><span data-stu-id="d7d31-186">Move users between on-premises and cloud</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[<span data-ttu-id="d7d31-187">共存およびアップグレードを設定する</span><span class="sxs-lookup"><span data-stu-id="d7d31-187">Setting your coexistence and upgrade settings</span></span>](setting-your-coexistence-and-upgrade-settings.md)

[<span data-ttu-id="d7d31-188">Grant-CsTeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="d7d31-188">Grant-CsTeamsUpgradePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[<span data-ttu-id="d7d31-189">会議移行サービス (MMS) を使用する</span><span class="sxs-lookup"><span data-stu-id="d7d31-189">Using the Meeting Migration Service (MMS)</span></span>](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

