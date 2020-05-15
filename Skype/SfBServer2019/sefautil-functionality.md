---
title: Skype for Business Server 2019 での PowerShell での SEFAUtil 機能の使用のサポート
ms.reviewer: rogupta
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.date: 07/22/2019
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: '概要: 累積的な更新プログラム1をインストールした後、PowerShell を使用して Skype for Business Server 2019 の SEFAUtil 機能を取得する方法について説明します。'
ms.openlocfilehash: 24040a3da5dc2549996463078a55324f3fc03657
ms.sourcegitcommit: 000515147632c6278bcda4505a1038014dda8e2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2020
ms.locfileid: "44232568"
---
# <a name="using-sefautil-functionality-via-powershell-in-skype-for-business-server-2019"></a><span data-ttu-id="504dc-103">Skype for Business Server 2019 での PowerShell による SEFAUtil 機能の使用</span><span class="sxs-lookup"><span data-stu-id="504dc-103">Using SEFAUtil functionality via PowerShell in Skype for Business Server 2019</span></span>

<span data-ttu-id="504dc-104">SEFAUtil (セカンダリ拡張機能のアクティブ化) を使用すると、Skype for business Server の管理者とヘルプデスク担当者は、Skype for Business Server ユーザーに代わって、代理人の呼び出し、着信の転送、グループ通話ピックアップの設定を構成できます。</span><span class="sxs-lookup"><span data-stu-id="504dc-104">SEFAUtil (Secondary Extension Feature Activation) enables Skype for Business Server administrators and helpdesk agents to configure delegate-ringing, call-forwarding, and Group Call Pickup settings on behalf of a Skype for Business Server user.</span></span> <span data-ttu-id="504dc-105">また、このツールを使用すると、管理者は特定のユーザーに対して公開されている呼び出しルーティング設定を照会することができます。</span><span class="sxs-lookup"><span data-stu-id="504dc-105">This tool also allows administrators to query the call-routing settings that are published for a particular user.</span></span> <span data-ttu-id="504dc-106">Skype for Business Server 2019 7 月の累積的な更新プログラムをインストールした後は、SEFAUtil を使用してのみ管理できる次の機能も、PowerShell を使用して管理することができます。</span><span class="sxs-lookup"><span data-stu-id="504dc-106">After you install the Skype for Business Server 2019 July cumulative update, the following functionality that can currently be managed only through SEFAUtil will be also manageable through PowerShell:</span></span>

- [<span data-ttu-id="504dc-107">着信の転送設定</span><span class="sxs-lookup"><span data-stu-id="504dc-107">Call forwarding settings</span></span>](#call-forwarding-settings)
- [<span data-ttu-id="504dc-108">委任の設定</span><span class="sxs-lookup"><span data-stu-id="504dc-108">Delegation settings</span></span>](#delegation-settings)
- [<span data-ttu-id="504dc-109">チームメンバーおよび関連する設定</span><span class="sxs-lookup"><span data-stu-id="504dc-109">Team members and related settings</span></span>](#team-members-and-related-settings)

## <a name="call-forwarding-settings"></a><span data-ttu-id="504dc-110">着信の転送設定</span><span class="sxs-lookup"><span data-stu-id="504dc-110">Call forwarding settings</span></span>

<span data-ttu-id="504dc-111">管理者は、PowerShell で次のコマンドレットを使用して、着信転送の設定を変更できます。</span><span class="sxs-lookup"><span data-stu-id="504dc-111">Administrators can change call forwarding settings by using the following cmdlet in PowerShell:</span></span>

- `Get-CsUserCallForwardingSettings -Identity <UserIdParameter>`

<span data-ttu-id="504dc-112">このコマンドレットは、指定されたユーザーの着信の転送設定をオブジェクトとして返し、画面に同じように表示します。</span><span class="sxs-lookup"><span data-stu-id="504dc-112">This cmdlet returns the specified user’s call forwarding settings as an object and displays the same on the screen.</span></span>

- `Set-CsUserCallForwardingSettings -Identity <UserIdParameter> [Param1 <Value>] [Param2 <Value>]…`

<span data-ttu-id="504dc-113">このコマンドレットは、指定したユーザーの着信転送設定を変更します。</span><span class="sxs-lookup"><span data-stu-id="504dc-113">This cmdlet modifies the specified user’s call forwarding settings.</span></span> <span data-ttu-id="504dc-114">このコマンドレットは、指定されたユーザーの着信の転送設定をオブジェクトとして返し、成功した場合には画面にも同じように表示します。</span><span class="sxs-lookup"><span data-stu-id="504dc-114">This cmdlet returns the specified user’s call forwarding settings as an object, and displays the same on the screen, in case of success.</span></span> <span data-ttu-id="504dc-115">障害が発生した場合は、適切なエラーメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="504dc-115">In case of failure, an appropriate error message will be shown.</span></span>

- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -DisableForwarding  [-UnansweredToVoicemail] [-UnansweredWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`
- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -DisableForwarding  [-UnansweredToOther <String>] [-UnansweredWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`

<span data-ttu-id="504dc-116">このコマンドレットは、ユーザーの着信転送設定を無効にします (ここでは2つの異なるパラメーターの例を示します)。</span><span class="sxs-lookup"><span data-stu-id="504dc-116">This cmdlet disables the user’s call forwarding settings (we show two different parameter examples here).</span></span>

- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -EnableForwarding <String> [-Delegates <PSListModifier>] [-DelegateRingWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`

<span data-ttu-id="504dc-117">このコマンドレットは、ユーザーの着信転送設定を変更します。</span><span class="sxs-lookup"><span data-stu-id="504dc-117">This cmdlet modifies the user’s call forwarding settings.</span></span>

- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -EnableSimulRing <String> [-UnansweredToVoicemail]  [-UnansweredWaitTime <TimeSpan>] [-Delegates <PSListModifier>] [-Team <PSListModifier>] [-TeamDelegateRingWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`
- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -EnableSimulRing <String> [-UnansweredToOther <String>] [-UnansweredWaitTime <TimeSpan>] [-Delegates <PSListModifier>]  [-Team <PSListModifier>]  [-TeamDelegateRingWaitTime <TimeSpan>]  [-SettingsActiveWorkHours]`

<span data-ttu-id="504dc-118">このコマンドレットでは、切り替わりの設定を変更します (2 つのパラメーター例があります。1つはボイスメールに応答しないため、もう一方には応答しません)。</span><span class="sxs-lookup"><span data-stu-id="504dc-118">This cmdlet modifies the SimulRing settings (again, with two parameter examples, one for unanswered to voicemail and the second being unanswered to other).</span></span>

## <a name="delegation-settings"></a><span data-ttu-id="504dc-119">委任の設定</span><span class="sxs-lookup"><span data-stu-id="504dc-119">Delegation settings</span></span>

<span data-ttu-id="504dc-120">管理者は、PowerShell で次のコマンドレットを使用して委任設定を変更できます。</span><span class="sxs-lookup"><span data-stu-id="504dc-120">Administrators can change delegation settings by using the following cmdlet in PowerShell:</span></span>

- `Get-CsuserDelegates -Identity <UserIdParameter>`

<span data-ttu-id="504dc-121">このコマンドレットは、デリゲートリストのオブジェクトを返し、指定されたユーザーの委任リストを表示します (成功した場合)。</span><span class="sxs-lookup"><span data-stu-id="504dc-121">This cmdlet returns an object of delegates list, and displays the specified user’s delegate list, in case of success.</span></span> <span data-ttu-id="504dc-122">障害が発生した場合は、適切なエラーメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="504dc-122">In case of failure, an appropriate error message will be shown.</span></span>

- `Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates <PSListModifier>]`

<span data-ttu-id="504dc-123">このコマンドレットは、指定したユーザーの委任設定を変更して、代理人の一覧を返し、代理人の一覧を表示します (成功した場合)。</span><span class="sxs-lookup"><span data-stu-id="504dc-123">This cmdlet modifies the specified user’s delegation settings, returns an object of delegates list and displays the list of delegates, in case of success.</span></span> <span data-ttu-id="504dc-124">障害が発生した場合は、適切なエラーメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="504dc-124">In case of failure, an appropriate error message will be shown.</span></span> 

- `Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates @{add=[list]}] [-Delegates @{remove=[list]}]`

<span data-ttu-id="504dc-125">このコマンドレットは、代理人を追加または削除します。</span><span class="sxs-lookup"><span data-stu-id="504dc-125">This cmdlet adds or removes a delegate.</span></span>

- `Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates @{replace=[list]}]`

<span data-ttu-id="504dc-126">このコマンドレットは、代理人の一覧を特定の代理人に設定します。</span><span class="sxs-lookup"><span data-stu-id="504dc-126">This cmdlet sets a delegate list to specific delegates.</span></span>

## <a name="team-members-and-related-settings"></a><span data-ttu-id="504dc-127">チームメンバーおよび関連する設定</span><span class="sxs-lookup"><span data-stu-id="504dc-127">Team members and related settings</span></span>

<span data-ttu-id="504dc-128">管理者は、PowerShell で次のコマンドレットを使用して、チームメンバーおよび関連する設定を変更できます。</span><span class="sxs-lookup"><span data-stu-id="504dc-128">Administrators can change team members and related settings by using the following cmdlet in PowerShell:</span></span>

- `Get-CsUserTeamMembers -Identity <UserIdParameter>`

<span data-ttu-id="504dc-129">このコマンドレットは、チームメンバーのリストを含むオブジェクトを取得し、成功した場合はそのオブジェクトを画面に表示します。</span><span class="sxs-lookup"><span data-stu-id="504dc-129">This cmdlet returns an object that contains list of team members, and displays the object on screen, in case of success.</span></span> <span data-ttu-id="504dc-130">障害が発生した場合は、適切なエラーメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="504dc-130">In case of failure, an appropriate error message will be shown.</span></span>

- `Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team <PSListModifier>]`

<span data-ttu-id="504dc-131">このコマンドレットは、指定したユーザーのチームメンバーリストを変更し、チームメンバーリストを含むオブジェクトを返し、成功した場合はそのオブジェクトを画面に表示します。</span><span class="sxs-lookup"><span data-stu-id="504dc-131">This cmdlet modifies the specified user’s team members list, returns an object that contains the team member list and displays the object on the screen, in case of success.</span></span> <span data-ttu-id="504dc-132">障害が発生した場合は、適切なエラーメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="504dc-132">In case of failure, an appropriate error message will be shown.</span></span>

- `Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team @{add=[list]}] [-Team @{remove=[list]}]`

<span data-ttu-id="504dc-133">このコマンドレットは、チームメンバーを追加または削除します。</span><span class="sxs-lookup"><span data-stu-id="504dc-133">This cmdlet adds or removes team members.</span></span>

- `Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team @{replace=[list]}]`

<span data-ttu-id="504dc-134">このコマンドレットは、チームリストを特定のメンバーに設定します。</span><span class="sxs-lookup"><span data-stu-id="504dc-134">This cmdlet sets a team list to specific members.</span></span>

## <a name="more-information"></a><span data-ttu-id="504dc-135">More information</span><span class="sxs-lookup"><span data-stu-id="504dc-135">More information</span></span>

<span data-ttu-id="504dc-136">オンプレミス展開の場合、この機能で導入されたコマンドレットは、次のグループのメンバーのみが実行できます。以下に指定するアクセスレベルごとに、</span><span class="sxs-lookup"><span data-stu-id="504dc-136">For on-premises deployments, the cmdlets introduced in this feature can only be run by members of the following groups, per the access level specified below:</span></span>

- <span data-ttu-id="504dc-137">CsAdministrator –すべてのコマンドレットの取得と設定</span><span class="sxs-lookup"><span data-stu-id="504dc-137">CsAdministrator – Get and Set for all cmdlets</span></span>
- <span data-ttu-id="504dc-138">CsVoiceAdministrator-すべてのコマンドレットの取得と設定</span><span class="sxs-lookup"><span data-stu-id="504dc-138">CsVoiceAdministrator - Get and Set for all cmdlets</span></span>
- <span data-ttu-id="504dc-139">CsHelpDesk-すべてのコマンドレットの取得</span><span class="sxs-lookup"><span data-stu-id="504dc-139">CsHelpDesk - Get for all cmdlets</span></span>

<span data-ttu-id="504dc-140">これらの管理者ロールの詳細については、「 [Skype For Business Server コントロールパネル管理者の作成](../SfbServer/help-topics/help-depwiz/create-skype-for-business-server-control-panel-administrators.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="504dc-140">For more information on these administrator roles, see [Create Skype for Business Server Control Panel Administrators](../SfbServer/help-topics/help-depwiz/create-skype-for-business-server-control-panel-administrators.md).</span></span> <span data-ttu-id="504dc-141">管理者は、サーバーコンピューターに直接またはリモートでログオンして、これらのコマンドレットにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="504dc-141">The administrator can access these cmdlets by directly or remotely logging on to a server computer.</span></span>
<span data-ttu-id="504dc-142">ハイブリッド展開の場合、Skype for Business 管理者は Get を呼び出してすべてのコマンドレットに設定できます。</span><span class="sxs-lookup"><span data-stu-id="504dc-142">For a hybrid deployment, Skype for Business administrators should be able to call Get and Set for all cmdlets.</span></span> <span data-ttu-id="504dc-143">役割の完全な一覧の詳細については、「[管理者の役割につい](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)て」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="504dc-143">For more information about the full list of roles, see [About admin roles](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)</span></span>

> [!NOTE]
> <span data-ttu-id="504dc-144">サーバーの自動検出を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="504dc-144">Server auto-discovery must be enabled.</span></span> <span data-ttu-id="504dc-145">コマンドレットを使用するために、追加のライセンス要件は導入されていません。</span><span class="sxs-lookup"><span data-stu-id="504dc-145">No additional licensing requirements will be introduced for use of the cmdlets.</span></span>
