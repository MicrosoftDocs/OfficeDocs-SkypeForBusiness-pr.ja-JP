---
title: 2019 年の PowerShell での SEFAUtil 機能の使用Skype for Business Server
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
description: '概要: 累積的な更新プログラム 1 をインストールした後、PowerShell を使用して 2019 年 Skype for Business Serverで SEFAUtil 機能を取得する方法について説明します。'
ms.openlocfilehash: fa7bccaa30b559bf694274471b1f8883e8482861
ms.sourcegitcommit: 330e60ff3549cd5cff5b52ad95dc4259e4e8de13
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/24/2021
ms.locfileid: "52629006"
---
# <a name="using-sefautil-functionality-via-powershell-in-skype-for-business-server-2019"></a><span data-ttu-id="f6fdc-103">2019 年に PowerShell 経由で SEFAUtil 機能をSkype for Business Serverする</span><span class="sxs-lookup"><span data-stu-id="f6fdc-103">Using SEFAUtil functionality via PowerShell in Skype for Business Server 2019</span></span>

<span data-ttu-id="f6fdc-104">SEFAUtil (Secondary Extension Feature Activation) を使用すると、Skype for Business Server 管理者とヘルプデスク エージェントは、Skype for Business Server ユーザーに代わって代理人呼び出し、通話転送、およびグループ通話ピックアップの設定を構成できます。</span><span class="sxs-lookup"><span data-stu-id="f6fdc-104">SEFAUtil (Secondary Extension Feature Activation) enables Skype for Business Server administrators and helpdesk agents to configure delegate-ringing, call-forwarding, and Group Call Pickup settings on behalf of a Skype for Business Server user.</span></span> <span data-ttu-id="f6fdc-105">また、このツールを使用すると、管理者は特定のユーザーに対して発行された通話ルーティング設定を照会できます。</span><span class="sxs-lookup"><span data-stu-id="f6fdc-105">This tool also allows administrators to query the call-routing settings that are published for a particular user.</span></span> <span data-ttu-id="f6fdc-106">2019 Skype for Business Server 7 月の累積的な更新プログラムをインストールすると、現在 SEFAUtil を通じてのみ管理できる次の機能も PowerShell を通じて管理できます。</span><span class="sxs-lookup"><span data-stu-id="f6fdc-106">After you install the Skype for Business Server 2019 July cumulative update, the following functionality that can currently be managed only through SEFAUtil will be also manageable through PowerShell:</span></span>

- [<span data-ttu-id="f6fdc-107">通話転送の設定</span><span class="sxs-lookup"><span data-stu-id="f6fdc-107">Call forwarding settings</span></span>](#call-forwarding-settings)
- [<span data-ttu-id="f6fdc-108">委任の設定</span><span class="sxs-lookup"><span data-stu-id="f6fdc-108">Delegation settings</span></span>](#delegation-settings)
- [<span data-ttu-id="f6fdc-109">チーム メンバーと関連する設定</span><span class="sxs-lookup"><span data-stu-id="f6fdc-109">Team members and related settings</span></span>](#team-members-and-related-settings)

## <a name="call-forwarding-settings"></a><span data-ttu-id="f6fdc-110">通話転送の設定</span><span class="sxs-lookup"><span data-stu-id="f6fdc-110">Call forwarding settings</span></span>

<span data-ttu-id="f6fdc-111">管理者は、PowerShell で次のコマンドレットを使用して、通話転送設定を変更できます。</span><span class="sxs-lookup"><span data-stu-id="f6fdc-111">Administrators can change call forwarding settings by using the following cmdlet in PowerShell:</span></span>

- `Get-CsUserCallForwardingSettings -Identity <UserIdParameter>`

<span data-ttu-id="f6fdc-112">このコマンドレットは、指定したユーザーの呼び出し転送設定をオブジェクトとして返し、同じ設定を画面に表示します。</span><span class="sxs-lookup"><span data-stu-id="f6fdc-112">This cmdlet returns the specified user’s call forwarding settings as an object and displays the same on the screen.</span></span>

- `Set-CsUserCallForwardingSettings -Identity <UserIdParameter> [Param1 <Value>] [Param2 <Value>]…`

<span data-ttu-id="f6fdc-113">このコマンドレットは、指定したユーザーの通話転送設定を変更します。</span><span class="sxs-lookup"><span data-stu-id="f6fdc-113">This cmdlet modifies the specified user’s call forwarding settings.</span></span> <span data-ttu-id="f6fdc-114">このコマンドレットは、指定したユーザーの呼び出し転送設定をオブジェクトとして返し、成功した場合は画面に同じ設定を表示します。</span><span class="sxs-lookup"><span data-stu-id="f6fdc-114">This cmdlet returns the specified user’s call forwarding settings as an object, and displays the same on the screen, in case of success.</span></span> <span data-ttu-id="f6fdc-115">エラーが発生した場合は、適切なエラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f6fdc-115">In case of failure, an appropriate error message will be shown.</span></span>

- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -DisableForwarding  [-UnansweredToVoicemail] [-UnansweredWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`
- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -DisableForwarding  [-UnansweredToOther <String>] [-UnansweredWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`

<span data-ttu-id="f6fdc-116">このコマンドレットは、ユーザーの通話転送設定を無効にします (ここでは、2 つの異なるパラメーター例を示します)。</span><span class="sxs-lookup"><span data-stu-id="f6fdc-116">This cmdlet disables the user’s call forwarding settings (we show two different parameter examples here).</span></span>

- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -EnableForwarding <String> [-Delegates <PSListModifier>] [-DelegateRingWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`

<span data-ttu-id="f6fdc-117">このコマンドレットは、ユーザーの通話転送設定を変更します。</span><span class="sxs-lookup"><span data-stu-id="f6fdc-117">This cmdlet modifies the user’s call forwarding settings.</span></span>

- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -EnableSimulRing <String> [-UnansweredToVoicemail]  [-UnansweredWaitTime <TimeSpan>] [-Delegates <PSListModifier>] [-Team <PSListModifier>] [-TeamDelegateRingWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`
- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -EnableSimulRing <String> [-UnansweredToOther <String>] [-UnansweredWaitTime <TimeSpan>] [-Delegates <PSListModifier>]  [-Team <PSListModifier>]  [-TeamDelegateRingWaitTime <TimeSpan>]  [-SettingsActiveWorkHours]`

<span data-ttu-id="f6fdc-118">このコマンドレットは、同時呼び出し設定を変更します (もう一度、2 つのパラメーター例を使用します。1 つはボイスメールに応答しない場合と、もう 1 つは他のパラメーターに応答しない場合)。</span><span class="sxs-lookup"><span data-stu-id="f6fdc-118">This cmdlet modifies the simultaneous ring settings (again, with two parameter examples, one for unanswered to voicemail and the second being unanswered to other).</span></span>

## <a name="delegation-settings"></a><span data-ttu-id="f6fdc-119">委任の設定</span><span class="sxs-lookup"><span data-stu-id="f6fdc-119">Delegation settings</span></span>

<span data-ttu-id="f6fdc-120">管理者は、PowerShell で次のコマンドレットを使用して委任設定を変更できます。</span><span class="sxs-lookup"><span data-stu-id="f6fdc-120">Administrators can change delegation settings by using the following cmdlet in PowerShell:</span></span>

- `Get-CsuserDelegates -Identity <UserIdParameter>`

<span data-ttu-id="f6fdc-121">このコマンドレットは、代理人リストのオブジェクトを返し、成功した場合に指定したユーザーの代理人リストを表示します。</span><span class="sxs-lookup"><span data-stu-id="f6fdc-121">This cmdlet returns an object of delegates list, and displays the specified user’s delegate list, in case of success.</span></span> <span data-ttu-id="f6fdc-122">エラーが発生した場合は、適切なエラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f6fdc-122">In case of failure, an appropriate error message will be shown.</span></span>

- `Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates <PSListModifier>]`

<span data-ttu-id="f6fdc-123">このコマンドレットは、指定したユーザーの委任設定を変更し、代理人リストのオブジェクトを返し、成功した場合に代理人の一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="f6fdc-123">This cmdlet modifies the specified user’s delegation settings, returns an object of delegates list, and displays the list of delegates, in case of success.</span></span> <span data-ttu-id="f6fdc-124">エラーが発生した場合は、適切なエラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f6fdc-124">In case of failure, an appropriate error message will be shown.</span></span> 

- `Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates @{add=[list]}] [-Delegates @{remove=[list]}]`

<span data-ttu-id="f6fdc-125">このコマンドレットは、代理人を追加または削除します。</span><span class="sxs-lookup"><span data-stu-id="f6fdc-125">This cmdlet adds or removes a delegate.</span></span>

- `Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates @{replace=[list]}]`

<span data-ttu-id="f6fdc-126">このコマンドレットは、代理人リストを特定の代理人に設定します。</span><span class="sxs-lookup"><span data-stu-id="f6fdc-126">This cmdlet sets a delegate list to specific delegates.</span></span>

## <a name="team-members-and-related-settings"></a><span data-ttu-id="f6fdc-127">チーム メンバーと関連する設定</span><span class="sxs-lookup"><span data-stu-id="f6fdc-127">Team members and related settings</span></span>

<span data-ttu-id="f6fdc-128">管理者は、PowerShell で次のコマンドレットを使用して、チーム メンバーと関連する設定を変更できます。</span><span class="sxs-lookup"><span data-stu-id="f6fdc-128">Administrators can change team members and related settings by using the following cmdlet in PowerShell:</span></span>

- `Get-CsUserTeamMembers -Identity <UserIdParameter>`

<span data-ttu-id="f6fdc-129">このコマンドレットは、チーム メンバーの一覧を含むオブジェクトを返し、成功した場合にオブジェクトを画面に表示します。</span><span class="sxs-lookup"><span data-stu-id="f6fdc-129">This cmdlet returns an object that contains list of team members, and displays the object on screen, in case of success.</span></span> <span data-ttu-id="f6fdc-130">エラーが発生した場合は、適切なエラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f6fdc-130">In case of failure, an appropriate error message will be shown.</span></span>

- `Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team <PSListModifier>]`

<span data-ttu-id="f6fdc-131">このコマンドレットは、指定したユーザーのチーム メンバーリストを変更し、チーム メンバーリストを含むオブジェクトを返し、成功した場合は、そのオブジェクトを画面に表示します。</span><span class="sxs-lookup"><span data-stu-id="f6fdc-131">This cmdlet modifies the specified user’s team members list, returns an object that contains the team member list and displays the object on the screen, in case of success.</span></span> <span data-ttu-id="f6fdc-132">エラーが発生した場合は、適切なエラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f6fdc-132">In case of failure, an appropriate error message will be shown.</span></span>

- `Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team @{add=[list]}] [-Team @{remove=[list]}]`

<span data-ttu-id="f6fdc-133">このコマンドレットは、チーム メンバーを追加または削除します。</span><span class="sxs-lookup"><span data-stu-id="f6fdc-133">This cmdlet adds or removes team members.</span></span>

- `Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team @{replace=[list]}]`

<span data-ttu-id="f6fdc-134">このコマンドレットは、チーム リストを特定のメンバーに設定します。</span><span class="sxs-lookup"><span data-stu-id="f6fdc-134">This cmdlet sets a team list to specific members.</span></span>

## <a name="more-information"></a><span data-ttu-id="f6fdc-135">詳細</span><span class="sxs-lookup"><span data-stu-id="f6fdc-135">More information</span></span>

<span data-ttu-id="f6fdc-136">オンプレミス展開の場合、この機能で導入されたコマンドレットを実行できるのは、次に示すアクセス レベルに従って、次のグループのメンバーのみです。</span><span class="sxs-lookup"><span data-stu-id="f6fdc-136">For on-premises deployments, the cmdlets introduced in this feature can only be run by members of the following groups, per the access level specified below:</span></span>

- <span data-ttu-id="f6fdc-137">CsAdministrator – すべてのコマンドレットの取得と設定</span><span class="sxs-lookup"><span data-stu-id="f6fdc-137">CsAdministrator – Get and Set for all cmdlets</span></span>
- <span data-ttu-id="f6fdc-138">CsVoiceAdministrator - すべてのコマンドレットの取得と設定</span><span class="sxs-lookup"><span data-stu-id="f6fdc-138">CsVoiceAdministrator - Get and Set for all cmdlets</span></span>
- <span data-ttu-id="f6fdc-139">CsHelpDesk - すべてのコマンドレットを取得する</span><span class="sxs-lookup"><span data-stu-id="f6fdc-139">CsHelpDesk - Get for all cmdlets</span></span>

<span data-ttu-id="f6fdc-140">これらの管理者ロールの詳細については[、「Create Skype for Business Server コントロール パネルの管理者」を参照してください](../SfbServer/help-topics/help-depwiz/create-skype-for-business-server-control-panel-administrators.md)。</span><span class="sxs-lookup"><span data-stu-id="f6fdc-140">For more information on these administrator roles, see [Create Skype for Business Server Control Panel Administrators](../SfbServer/help-topics/help-depwiz/create-skype-for-business-server-control-panel-administrators.md).</span></span> <span data-ttu-id="f6fdc-141">管理者は、サーバー コンピューターに直接またはリモートでログオンすることで、これらのコマンドレットにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="f6fdc-141">The administrator can access these cmdlets by directly or remotely logging on to a server computer.</span></span>
<span data-ttu-id="f6fdc-142">ハイブリッド展開の場合、Skype for Business管理者は、すべてのコマンドレットに対して Get と Set を呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="f6fdc-142">For a hybrid deployment, Skype for Business administrators should be able to call Get and Set for all cmdlets.</span></span> <span data-ttu-id="f6fdc-143">役割の完全な一覧の詳細については、「管理者の役割について [」を参照してください](/microsoft-365/admin/add-users/about-admin-roles)。</span><span class="sxs-lookup"><span data-stu-id="f6fdc-143">For more information about the full list of roles, see [About admin roles](/microsoft-365/admin/add-users/about-admin-roles).</span></span>

> [!NOTE]
> <span data-ttu-id="f6fdc-144">サーバーの自動検出を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f6fdc-144">Server auto-discovery must be enabled.</span></span> <span data-ttu-id="f6fdc-145">コマンドレットを使用するために追加のライセンス要件は導入されません。</span><span class="sxs-lookup"><span data-stu-id="f6fdc-145">No additional licensing requirements will be introduced for use of the cmdlets.</span></span>
