---
title: Skype for Business Server 2019 での PowerShell での SEFAUtil 機能の使用に関するサポート
ms.reviewer: rogupta
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.date: 07/22/2019
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
description: '概要: 累積的な更新プログラム1をインストールした後、PowerShell を使用して Skype for Business Server 2019 の SEFAUtil 機能を入手する方法について説明します。'
ms.openlocfilehash: 6652e3b76a31ac4b315c70498ac2b01d4467b70e
ms.sourcegitcommit: dc151bf4454ddec20db5cd133a42a67599c08d64
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/11/2019
ms.locfileid: "36838100"
---
# <a name="using-sefautil-functionality-via-powershell-in-skype-for-business-server-2019"></a><span data-ttu-id="e643f-103">Skype for Business Server 2019 の PowerShell 経由で SEFAUtil 機能を使用する</span><span class="sxs-lookup"><span data-stu-id="e643f-103">Using SEFAUtil functionality via PowerShell in Skype for Business Server 2019</span></span>

<span data-ttu-id="e643f-104">SEFAUtil (セカンダリ拡張機能のアクティブ化) では、skype for business Server の管理者およびヘルプデスクエージェントは、Skype for Business Server ユーザーの代わりに、代理人の呼び出し、着信の転送、グループ通話のピックアップの設定を構成できます。</span><span class="sxs-lookup"><span data-stu-id="e643f-104">SEFAUtil (Secondary Extension Feature Activation) enables Skype for Business Server administrators and helpdesk agents to configure delegate-ringing, call-forwarding, and Group Call Pickup settings on behalf of a Skype for Business Server user.</span></span> <span data-ttu-id="e643f-105">また、管理者は特定のユーザー向けに公開されているコール ルーティング設定のクエリを実行できます。</span><span class="sxs-lookup"><span data-stu-id="e643f-105">This tool also allows administrators to query the call-routing settings that are published for a particular user.</span></span> <span data-ttu-id="e643f-106">Skype for Business Server 2019 年7月の累積更新プログラムをインストールした後、SEFAUtil を使用してのみ現在管理できる次の機能は、PowerShell を使用して管理することもできます。</span><span class="sxs-lookup"><span data-stu-id="e643f-106">After you install the Skype for Business Server 2019 July cumulative update, the following functionality that can currently be managed only through SEFAUtil will be also manageable through PowerShell:</span></span>

- [<span data-ttu-id="e643f-107">着信の転送設定</span><span class="sxs-lookup"><span data-stu-id="e643f-107">Call forwarding settings</span></span>](#call-forwarding-settings)
- [<span data-ttu-id="e643f-108">委任の設定</span><span class="sxs-lookup"><span data-stu-id="e643f-108">Delegation settings</span></span>](#delegation-settings)
- [<span data-ttu-id="e643f-109">チームメンバーと関連する設定</span><span class="sxs-lookup"><span data-stu-id="e643f-109">Team members and related settings</span></span>](#team-members-and-related-settings)

## <a name="call-forwarding-settings"></a><span data-ttu-id="e643f-110">着信の転送設定</span><span class="sxs-lookup"><span data-stu-id="e643f-110">Call forwarding settings</span></span>

<span data-ttu-id="e643f-111">管理者は、PowerShell の次のコマンドレットを使用して、着信の転送設定を変更できます。</span><span class="sxs-lookup"><span data-stu-id="e643f-111">Administrators can change call forwarding settings by using the following cmdlet in PowerShell:</span></span>

- `Get-CsUserCallForwardingSettings -Identity <UserIdParameter>`

<span data-ttu-id="e643f-112">このコマンドレットは、指定したユーザーの着信の転送設定をオブジェクトとして返し、画面でも同じように表示します。</span><span class="sxs-lookup"><span data-stu-id="e643f-112">This cmdlet returns the specified user’s call forwarding settings as an object and displays the same on the screen.</span></span>

- `Set-CsUserCallForwardingSettings -Identity <UserIdParameter> [Param1 <Value>] [Param2 <Value>]…`

<span data-ttu-id="e643f-113">このコマンドレットは、指定したユーザーの着信の転送設定を変更します。</span><span class="sxs-lookup"><span data-stu-id="e643f-113">This cmdlet modifies the specified user’s call forwarding settings.</span></span> <span data-ttu-id="e643f-114">このコマンドレットは、指定したユーザーの着信の転送設定をオブジェクトとして返し、正常に完了した場合は画面にも表示します。</span><span class="sxs-lookup"><span data-stu-id="e643f-114">This cmdlet returns the specified user’s call forwarding settings as an object, and displays the same on the screen, in case of success.</span></span> <span data-ttu-id="e643f-115">エラーが発生した場合は、適切なエラーメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e643f-115">In case of failure, an appropriate error message will be shown.</span></span>

- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -DisableForwarding  [-UnansweredToVoicemail] [-UnansweredWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`
- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -DisableForwarding  [-UnansweredToOther <String>] [-UnansweredWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`

<span data-ttu-id="e643f-116">このコマンドレットでは、ユーザーの着信の転送設定を無効にします (ここでは、2つの異なるパラメーターの例を示します)。</span><span class="sxs-lookup"><span data-stu-id="e643f-116">This cmdlet disables the user’s call forwarding settings (we show two different parameter examples here).</span></span>

- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -EnableForwarding <String> [-Delegates <PSListModifier>] [-DelegateRingWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`

<span data-ttu-id="e643f-117">このコマンドレットは、ユーザーの着信の転送設定を変更します。</span><span class="sxs-lookup"><span data-stu-id="e643f-117">This cmdlet modifies the user’s call forwarding settings.</span></span>

- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -EnableSimulRing <String> [-UnansweredToVoicemail]  [-UnansweredWaitTime <TimeSpan>] [-Delegates <PSListModifier>] [-Team <PSListModifier>] [-TeamDelegateRingWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`
- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -EnableSimulRing <String> [-UnansweredToOther <String>] [-UnansweredWaitTime <TimeSpan>] [-Delegates <PSListModifier>]  [-Team <PSListModifier>]  [-TeamDelegateRingWaitTime <TimeSpan>]  [-SettingsActiveWorkHours]`

<span data-ttu-id="e643f-118">このコマンドレットは、SimulRing の設定を変更します (1 つはボイスメールに不在着信し、2番目のパラメーターには応答しません)。</span><span class="sxs-lookup"><span data-stu-id="e643f-118">This cmdlet modifies the SimulRing settings (again, with two parameter examples, one for unanswered to voicemail and the second being unanswered to other).</span></span>

## <a name="delegation-settings"></a><span data-ttu-id="e643f-119">委任の設定</span><span class="sxs-lookup"><span data-stu-id="e643f-119">Delegation settings</span></span>

<span data-ttu-id="e643f-120">管理者は、PowerShell の次のコマンドレットを使用して、委任設定を変更できます。</span><span class="sxs-lookup"><span data-stu-id="e643f-120">Administrators can change delegation settings by using the following cmdlet in PowerShell:</span></span>

- `Get-CsuserDelegates -Identity <UserIdParameter>`

<span data-ttu-id="e643f-121">このコマンドレットは、デリゲートリストのオブジェクトを返し、指定したユーザーのデリゲートリストを、成功した場合に表示します。</span><span class="sxs-lookup"><span data-stu-id="e643f-121">This cmdlet returns an object of delegates list, and displays the specified user’s delegate list, in case of success.</span></span> <span data-ttu-id="e643f-122">エラーが発生した場合は、適切なエラーメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e643f-122">In case of failure, an appropriate error message will be shown.</span></span>

- `Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates <PSListModifier>]`

<span data-ttu-id="e643f-123">このコマンドレットは、指定したユーザーの委任設定を変更し、デリゲートリストのオブジェクトを返し、成功した場合は代理人のリストを表示します。</span><span class="sxs-lookup"><span data-stu-id="e643f-123">This cmdlet modifies the specified user’s delegation settings, returns an object of delegates list and displays the list of delegates, in case of success.</span></span> <span data-ttu-id="e643f-124">エラーが発生した場合は、適切なエラーメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e643f-124">In case of failure, an appropriate error message will be shown.</span></span> 

- `Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates @{add=[list]}] [-Delegates @{remove=[list]}]`

<span data-ttu-id="e643f-125">このコマンドレットはデリゲートを追加または削除します。</span><span class="sxs-lookup"><span data-stu-id="e643f-125">This cmdlet adds or removes a delegate.</span></span>

- `Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates @{replace=[list]}]`

<span data-ttu-id="e643f-126">このコマンドレットは、特定のデリゲートに委任リストを設定します。</span><span class="sxs-lookup"><span data-stu-id="e643f-126">This cmdlet sets a delegate list to specific delegates.</span></span>

## <a name="team-members-and-related-settings"></a><span data-ttu-id="e643f-127">チームメンバーと関連する設定</span><span class="sxs-lookup"><span data-stu-id="e643f-127">Team members and related settings</span></span>

<span data-ttu-id="e643f-128">管理者は、PowerShell の次のコマンドレットを使用して、チームメンバーと関連する設定を変更できます。</span><span class="sxs-lookup"><span data-stu-id="e643f-128">Administrators can change team members and related settings by using the following cmdlet in PowerShell:</span></span>

- `Get-CsUserTeamMembers -Identity <UserIdParameter>`

<span data-ttu-id="e643f-129">このコマンドレットは、チームメンバーの一覧が含まれているオブジェクトを返し、成功した場合はそのオブジェクトを画面上に表示します。</span><span class="sxs-lookup"><span data-stu-id="e643f-129">This cmdlet returns an object that contains list of team members, and displays the object on screen, in case of success.</span></span> <span data-ttu-id="e643f-130">エラーが発生した場合は、適切なエラーメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e643f-130">In case of failure, an appropriate error message will be shown.</span></span>

- `Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team <PSListModifier>]`

<span data-ttu-id="e643f-131">このコマンドレットは、指定したユーザーのチームメンバーリストを変更し、成功した場合は、チームメンバーリストを含むオブジェクトを返し、そのオブジェクトを画面に表示します。</span><span class="sxs-lookup"><span data-stu-id="e643f-131">This cmdlet modifies the specified user’s team members list, returns an object that contains the team member list and displays the object on the screen, in case of success.</span></span> <span data-ttu-id="e643f-132">エラーが発生した場合は、適切なエラーメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e643f-132">In case of failure, an appropriate error message will be shown.</span></span>

- `Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team @{add=[list]}] [-Team @{remove=[list]}]`

<span data-ttu-id="e643f-133">このコマンドレットは、チームメンバーを追加または削除します。</span><span class="sxs-lookup"><span data-stu-id="e643f-133">This cmdlet adds or removes team members.</span></span>

- `Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team @{replace=[list]}]`

<span data-ttu-id="e643f-134">このコマンドレットは、チームリストを特定のメンバーに設定します。</span><span class="sxs-lookup"><span data-stu-id="e643f-134">This cmdlet sets a team list to specific members.</span></span>

## <a name="more-information"></a><span data-ttu-id="e643f-135">詳細情報</span><span class="sxs-lookup"><span data-stu-id="e643f-135">More information</span></span>

<span data-ttu-id="e643f-136">オンプレミス展開の場合、この機能で導入されたコマンドレットは、次のように指定されたアクセスレベルごとに、次のグループのメンバーのみが実行できます。</span><span class="sxs-lookup"><span data-stu-id="e643f-136">For on-premises deployments, the cmdlets introduced in this feature can only be run by members of the following groups, per the access level specified below:</span></span>

- <span data-ttu-id="e643f-137">CsAdministrator –すべてのコマンドレットの取得と設定</span><span class="sxs-lookup"><span data-stu-id="e643f-137">CsAdministrator – Get and Set for all cmdlets</span></span>
- <span data-ttu-id="e643f-138">CsVoiceAdministrator-すべてのコマンドレットの取得と設定</span><span class="sxs-lookup"><span data-stu-id="e643f-138">CsVoiceAdministrator - Get and Set for all cmdlets</span></span>
- <span data-ttu-id="e643f-139">CsHelpDesk-すべてのコマンドレットの取得</span><span class="sxs-lookup"><span data-stu-id="e643f-139">CsHelpDesk - Get for all cmdlets</span></span>

<span data-ttu-id="e643f-140">これらの管理者ロールの詳細については、「 [Skype For Business Server コントロールパネル管理者の作成](../SfbServer/help-topics/help-depwiz/create-skype-for-business-server-control-panel-administrators.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e643f-140">For more information on these administrator roles, see [Create Skype for Business Server Control Panel Administrators](../SfbServer/help-topics/help-depwiz/create-skype-for-business-server-control-panel-administrators.md).</span></span> <span data-ttu-id="e643f-141">管理者は、これらのコマンドレットに直接、またはリモートでサーバーコンピューターにログオンしてアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="e643f-141">The administrator can access these cmdlets by directly or remotely logging on to a server computer.</span></span>
<span data-ttu-id="e643f-142">ハイブリッド展開の場合、Skype for Business の管理者はすべてのコマンドレットの Get と Set を呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="e643f-142">For a hybrid deployment, Skype for Business administrators should be able to call Get and Set for all cmdlets.</span></span> <span data-ttu-id="e643f-143">ロールの完全なリストの詳細については、「 [Office 365 管理者ロールについ](https://docs.microsoft.com/en-us/office365/admin/add-users/about-admin-roles)て」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e643f-143">For more information about the full list of roles, see [About Office 365 admin roles](https://docs.microsoft.com/en-us/office365/admin/add-users/about-admin-roles)</span></span>

> [!NOTE]
> <span data-ttu-id="e643f-144">サーバーの自動検出を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e643f-144">Server auto-discovery must be enabled.</span></span> <span data-ttu-id="e643f-145">コマンドレットを使用するために、追加のライセンス要件はありません。</span><span class="sxs-lookup"><span data-stu-id="e643f-145">No additional licensing requirements will be introduced for use of the cmdlets.</span></span>
