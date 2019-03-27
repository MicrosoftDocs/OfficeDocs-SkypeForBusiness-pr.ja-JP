---
title: チーム PowerShell の概要
ms.reviewer: ''
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/06/2018
ms.topic: conceptual
ms.service: msteams
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
description: PowerShell のコントロールを使用して、マイクロソフトのチームを管理するために説明します。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 497aeba1e339e3c079de9eb4a23182e8f727f278
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30897204"
---
# <a name="teams-powershell-overview"></a><span data-ttu-id="21b58-103">チーム PowerShell の概要</span><span class="sxs-lookup"><span data-stu-id="21b58-103">Teams PowerShell Overview</span></span>

<span data-ttu-id="21b58-104">マイクロソフトのチームでは、マイクロソフトのチーム管理センター、PowerShell のコントロール、およびグラフの Api を通じて製品を管理する IT 管理者のためのツールの豊富なセットがあります。</span><span class="sxs-lookup"><span data-stu-id="21b58-104">Microsoft Teams has a rich set of tools for IT admins to manage the product through the Microsoft Teams admin center, PowerShell controls, and Graph APIs.</span></span> <span data-ttu-id="21b58-105">このガイドでは、当社の PowerShell コマンドレットを使用して、IT 管理者を構成する方法について説明し、さらにドキュメントへのポインターを提供します。</span><span class="sxs-lookup"><span data-stu-id="21b58-105">This guide explains how we structure our PowerShell cmdlets for IT admins to use, and provides pointers to further documentation.</span></span> <span data-ttu-id="21b58-106">さまざまなチームの管理者のロールに別のコマンドレットへのアクセスがあることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="21b58-106">Note that different Teams admin roles have access to different cmdlets.</span></span> <span data-ttu-id="21b58-107">詳細については、[チームを管理する管理者の役割を使用してマイクロソフトのチーム](using-admin-roles.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="21b58-107">For more information, see [Use Microsoft Teams admin roles to manage Teams](using-admin-roles.md).</span></span>

## <a name="which-modules-do-you-need-to-use"></a><span data-ttu-id="21b58-108">モジュールを使用するのには必要ですか。</span><span class="sxs-lookup"><span data-stu-id="21b58-108">Which modules do you need to use?</span></span>

<span data-ttu-id="21b58-109">PowerShell の 2 つの異なるモジュールには、チームを管理するための PowerShell コントロールです。</span><span class="sxs-lookup"><span data-stu-id="21b58-109">The PowerShell controls for managing Teams are in two different PowerShell modules:</span></span> 
- <span data-ttu-id="21b58-110">[マイクロソフト チームの PowerShell モジュール](https://www.powershellgallery.com/packages/MicrosoftTeams/0.9.5)(パブリック プレビュー): すべてのコマンドレット作成し、チームを管理する必要がありますにはが、チームの PowerShell モジュールに含まれています。</span><span class="sxs-lookup"><span data-stu-id="21b58-110">[Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams/0.9.5) (public preview): The Teams PowerShell module contains all the cmdlets you need to create and manage teams.</span></span>  
- <span data-ttu-id="21b58-111">[ビジネスの PowerShell モジュールの Skype](https://www.microsoft.com/en-us/download/details.aspx?id=39366): ビジネスの PowerShell モジュールの「Skype にには、ポリシー、構成、およびその他のチームのツールを管理するためのコマンドレットにはが含まれています。</span><span class="sxs-lookup"><span data-stu-id="21b58-111">[Skype for Business PowerShell module](https://www.microsoft.com/en-us/download/details.aspx?id=39366): The Skype for Business PowerShell module contains the cmdlets to manage policies, configurations, and other Teams tools.</span></span> 

<span data-ttu-id="21b58-112">PowerShell のコントロールのリファレンス ドキュメントが送信されます、調査しているコマンドレットがどのモジュールに含まれています。</span><span class="sxs-lookup"><span data-stu-id="21b58-112">The reference documentation for the PowerShell controls will tell you which module contains the cmdlet you're investigating.</span></span> <span data-ttu-id="21b58-113">(最終的には、2 つのモジュール結合されます。)</span><span class="sxs-lookup"><span data-stu-id="21b58-113">(Eventually, the two modules will be combined.)</span></span>

## <a name="what-can-each-admin-role-do"></a><span data-ttu-id="21b58-114">できます各管理者の役割は何ですか。</span><span class="sxs-lookup"><span data-stu-id="21b58-114">What can each admin role do?</span></span>

<span data-ttu-id="21b58-115">PowerShell コマンドレットの別の管理者の役割が利用できるようになりますを理解する[チームを管理する管理者の役割を使用してマイクロソフトのチーム](using-admin-roles.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="21b58-115">Read [Use Microsoft Teams admin roles to manage Teams](using-admin-roles.md) to understand which PowerShell cmdlets different admin roles will be able to leverage.</span></span>

## <a name="creating-and-managing-teams-via-powershell"></a><span data-ttu-id="21b58-116">作成して、PowerShell を使用してチームを管理します。</span><span class="sxs-lookup"><span data-stu-id="21b58-116">Creating and managing teams via PowerShell</span></span>

<span data-ttu-id="21b58-117">[マイクロソフト チームの PowerShell モジュール](https://www.powershellgallery.com/packages/MicrosoftTeams/0.9.3)では、コマンドレットを作成して、チームを管理するのです。</span><span class="sxs-lookup"><span data-stu-id="21b58-117">The cmdlets for creating and managing teams are in the [Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams/0.9.3).</span></span> 

<span data-ttu-id="21b58-118">チームによって支えられて O365 グループでは、これとチームを作成する、グループを作成します。</span><span class="sxs-lookup"><span data-stu-id="21b58-118">Teams are backed by O365 Groups, so when you create a team, you create a group.</span></span> <span data-ttu-id="21b58-119">コア ・ チームとその設定を操作するために用意されているコマンドレットのセットがある (``new-team``、 ``get-team``、 ``set-teamfunsettings``、 ``set-teammessagingsettings``、 ``set-teamguestsettings``、 ``set-teammembersettings``)、チームのユーザーを管理する (``add-teamuser``、 ``remove-teamuser``)、およびチームのチャネルを管理するためのコマンドレット (``new-teamchannel``, ``remove-teamchannel``).</span><span class="sxs-lookup"><span data-stu-id="21b58-119">There are a set of cmdlets provided for operating on the core team and its settings (``new-team``, ``get-team``, ``set-teamfunsettings``, ``set-teammessagingsettings``, ``set-teamguestsettings``, ``set-teammembersettings``), managing team users (``add-teamuser``, ``remove-teamuser``), as well as cmdlets for managing the channels of the team (``new-teamchannel``, ``remove-teamchannel``).</span></span> <span data-ttu-id="21b58-120">エンド ・ ユーザーとして実行できるすべてのこれらのコマンドレットが所有する、またはのメンバーをチームにのみ動作します。</span><span class="sxs-lookup"><span data-stu-id="21b58-120">All of these cmdlets can be run as end users, but they'll work only on the teams that you own or are a member of.</span></span> <span data-ttu-id="21b58-121">場合は、グローバル管理者またはチームのサービス管理者は、組織内のすべてのチームを操作することができます。</span><span class="sxs-lookup"><span data-stu-id="21b58-121">If you are a Global Admin or Teams Service Administrator, you'll be able to act on all teams in your organization.</span></span>

> <span data-ttu-id="21b58-122">マイクロソフト チームの PowerShell モジュールのコマンドレットで使用されている**グループ Id**は、 **Identity**プロパティによって返される``Get-UnifiedGroup``Exchange PowerShell モジュールにします。</span><span class="sxs-lookup"><span data-stu-id="21b58-122">The **GroupId** used in the Microsoft Teams PowerShell module cmdlets is the same as the **Identity** property returned by ``Get-UnifiedGroup`` in the Exchange PowerShell module.</span></span>

## <a name="managing-policies-via-powershell"></a><span data-ttu-id="21b58-123">PowerShell を使用してポリシーの管理</span><span class="sxs-lookup"><span data-stu-id="21b58-123">Managing policies via PowerShell</span></span>

<span data-ttu-id="21b58-124">ポリシーを管理するためのコマンドレットは、[コマンドレットのビジネス モジュールの Skype](https://www.microsoft.com/en-us/download/details.aspx?id=39366)では。</span><span class="sxs-lookup"><span data-stu-id="21b58-124">The cmdlets for managing policies are in the [Skype for Business cmdlet module](https://www.microsoft.com/en-us/download/details.aspx?id=39366).</span></span>

<span data-ttu-id="21b58-125">ポリシーは、個々 のユーザーに細かく適用できる設定のグループです。</span><span class="sxs-lookup"><span data-stu-id="21b58-125">A policy is a group of settings that can be applied granularly to individual users.</span></span> <span data-ttu-id="21b58-126">各ポリシーの種類には、コマンドレットを作成、表示、削除、および自体には、ポリシーの更新およびユーザーにこれらのポリシーを割り当てるのための独自のセットがあります。</span><span class="sxs-lookup"><span data-stu-id="21b58-126">Each policy type has its own set of cmdlets for creating, viewing, deleting, and updating the policies themselves, and then assigning those policies to users.</span></span> <span data-ttu-id="21b58-127">一般的な構造は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="21b58-127">The general structure is:</span></span>

- <span data-ttu-id="21b58-128">GET コマンド (たとえば、 ``Get-CsTeamsMeetingPolicy``): 組織のポリシーを使用する Microsoft によって作成されると作成したカスタム ポリシーの両方を割り当てることで利用可能なポリシーのドキュメントを返します。</span><span class="sxs-lookup"><span data-stu-id="21b58-128">GET commands (for example, ``Get-CsTeamsMeetingPolicy``):  return the policy documents that are available for you to assign in your organization, both the policies created by Microsoft for you to use and the custom policies you’ve created.</span></span>
   > <span data-ttu-id="21b58-129">使用することができます、組織で作成したカスタム ポリシーのみを検索する場合は、 ``-Filter "tag:*"``。</span><span class="sxs-lookup"><span data-stu-id="21b58-129">If you want to find only the custom policies you’ve created in your organization, you can use ``-Filter "tag:*"``.</span></span>

- <span data-ttu-id="21b58-130">新しいコマンド (たとえば、 ``New-CsTeamsMeetingPolicy``): を使用して見ることが、組織内のユーザーに割り当てられる利用可能な組織の新しいポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="21b58-130">NEW commands (for example, ``New-CsTeamsMeetingPolicy``): let you create new policies for your organization that are then available to be assigned to users in your organization.</span></span> <span data-ttu-id="21b58-131">一部のポリシーは、カスタム ポリシーの作成をサポートします。</span><span class="sxs-lookup"><span data-stu-id="21b58-131">Not all policies support the creation of custom policies.</span></span> <span data-ttu-id="21b58-132">多くの場合これは、組織内で使用するポリシーは、サポートされている設定の組み合わせであることを確認すること。</span><span class="sxs-lookup"><span data-stu-id="21b58-132">Often this is to ensure that the policies you use in your organization have a supported combination of settings.</span></span>

- <span data-ttu-id="21b58-133">一連のコマンド (たとえば、 ``Set-CsTeamsMeetingPolicy``): 指定されたポリシーの特定の値を設定することができます。</span><span class="sxs-lookup"><span data-stu-id="21b58-133">SET commands (for example, ``Set-CsTeamsMeetingPolicy``): lets you set particular values on a given policy.</span></span> <span data-ttu-id="21b58-134">いくつかのポリシー設定のコマンドが使用可能なしたりしないでポリシーの設定を変更できないパラメーターが含まれています。</span><span class="sxs-lookup"><span data-stu-id="21b58-134">Some policies do not have set commands available, or contain parameters that cannot be customized in the policy.</span></span> <span data-ttu-id="21b58-135">PowerShell のそれぞれの説明は、どのパラメーターをカスタマイズすることはできませんを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="21b58-135">Each PowerShell description will call out which parameters cannot be customized.</span></span> 
   > <span data-ttu-id="21b58-136">既定で割り当てられる割り当てられているカスタム ポリシーがない、組織内のユーザーにポリシーを編集するのには次のように実行します。 ``Set-Cs<PolicyName> -Identity Global``。</span><span class="sxs-lookup"><span data-stu-id="21b58-136">To edit the policy that will by default be assigned to users in your organization who do not have a custom policy assigned, run ``Set-Cs<PolicyName> -Identity Global``.</span></span>

- <span data-ttu-id="21b58-137">削除] コマンド (たとえば、 ``Remove-CsTeamsMeetingPolicy``): テナントで作成されたカスタム ポリシーを削除するのには、このコマンドレットを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="21b58-137">REMOVE commands (for example, ``Remove-CsTeamsMeetingPolicy``): you can use this cmdlet to delete a custom policy that has been created in your tenant.</span></span> <span data-ttu-id="21b58-138">場合は、組織内の少なくとも 1 つのユーザーに割り当てられているカスタム ポリシーを削除すると、そのユーザーはグローバル ポリシーをクリアテキストです。</span><span class="sxs-lookup"><span data-stu-id="21b58-138">If you delete a custom policy that has been assigned to at least one user in your organization, that user will fall back to the global policy.</span></span>
   > <span data-ttu-id="21b58-139">実際には、組織のグローバル ポリシーを削除できませんが、実行することがマイクロソフトから提供された既定の設定を組織内のグローバル ポリシーをリセットする場合は、 ``Remove-Cs<PolicyName> -Identity Global``。</span><span class="sxs-lookup"><span data-stu-id="21b58-139">You can’t actually remove the global policy in your organization, but if you want to reset the global policy in your organization to the Microsoft-provided default settings, you can run ``Remove-Cs<PolicyName> -Identity Global``.</span></span>

- <span data-ttu-id="21b58-140">GRANT コマンド (たとえば、 ``Grant-CsTeamsMeetingPolicy``): 特定のユーザーにポリシーを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="21b58-140">GRANT command (for example, ``Grant-CsTeamsMeetingPolicy``): lets you assign a policy to a particular user.</span></span>
   > <span data-ttu-id="21b58-141">実行するカスタム ポリシーの割り当てを削除して、組織内の既定のポリシーにユーザーを``Grant-Cs<PolicyName> -Identity <User Identity> -PolicyName $null``。</span><span class="sxs-lookup"><span data-stu-id="21b58-141">To remove a custom policy assignment and make the user fall back to the default policy in your organization, run ``Grant-Cs<PolicyName> -Identity <User Identity> -PolicyName $null``.</span></span>

> [!TIP]
> <span data-ttu-id="21b58-142">すべてのポリシーを作成するには、カスタム ポリシーを許可する、およびいくつかのポリシー設定でカスタマイズすることはできません (設定を表示することができますが、中にカスタム値を設定することはできませんので``set-``と``new-``)。</span><span class="sxs-lookup"><span data-stu-id="21b58-142">Not all policies allow custom policies to be created, and some policies have settings that you can’t customize (so you can view the setting but can’t set a custom value during ``set-`` and ``new-``).</span></span> <span data-ttu-id="21b58-143">パラメーターが顧客によって使用可能な場合は、特定のコマンドレットのドキュメント呼び出します。</span><span class="sxs-lookup"><span data-stu-id="21b58-143">The documentation of the specific cmdlet will call out if parameters are not available for use by customers.</span></span>

<span data-ttu-id="21b58-144">共通のパラメーター:</span><span class="sxs-lookup"><span data-stu-id="21b58-144">Common parameters:</span></span>

- <span data-ttu-id="21b58-145">**Id**: の``Get-``、 ``Set-``、 ``New-``、および``Remove-``、 **Id**パラメーターは常に特定のポリシーのインスタンスを参照してください。</span><span class="sxs-lookup"><span data-stu-id="21b58-145">**Identity**: For ``Get-``, ``Set-``, ``New-``, and ``Remove-``, the **Identity** parameter will always refer to a specific policy instance.</span></span> <span data-ttu-id="21b58-146">``Grant``、 **Id**パラメーターは、ポリシーの適用先の特定のユーザー オブジェクトを参照します。</span><span class="sxs-lookup"><span data-stu-id="21b58-146">For ``Grant``, the **Identity** parameter refers to a specific user object to whom the policy is being applied.</span></span>

<!--more info here?-->

## <a name="managing-configurations-via-powershell"></a><span data-ttu-id="21b58-147">PowerShell を使用して構成を管理します。</span><span class="sxs-lookup"><span data-stu-id="21b58-147">Managing configurations via PowerShell</span></span>

<span data-ttu-id="21b58-148">構成を管理するためのコマンドレットは、[コマンドレットのビジネス モジュールの Skype](https://www.microsoft.com/en-us/download/details.aspx?id=39366)では。</span><span class="sxs-lookup"><span data-stu-id="21b58-148">The cmdlets for managing your configuration are in the [Skype for Business cmdlet module](https://www.microsoft.com/en-us/download/details.aspx?id=39366).</span></span>

<span data-ttu-id="21b58-149">構成は、ユーザー レベルで指定することはできませんが、サービスで保持されている設定のバケットです。</span><span class="sxs-lookup"><span data-stu-id="21b58-149">Configurations are buckets of settings maintained in the service that cannot be specified at a user level.</span></span> <span data-ttu-id="21b58-150">設定は、組織全体で常に適用されます。</span><span class="sxs-lookup"><span data-stu-id="21b58-150">Settings always apply across the whole organization.</span></span> <span data-ttu-id="21b58-151">グローバル設定は、組織内で唯一の効果的な構成です。</span><span class="sxs-lookup"><span data-stu-id="21b58-151">Your global configuration is the only effective configuration in your organization.</span></span> <span data-ttu-id="21b58-152">構成タイプごとに主な 2 つのコマンドレットではあります。</span><span class="sxs-lookup"><span data-stu-id="21b58-152">Each configuration type comes with two primary cmdlets:</span></span>

- <span data-ttu-id="21b58-153">``Get-Cs<ConfigurationName>``(たとえば、 ``Get-CsTeamsClientConfiguration``)。</span><span class="sxs-lookup"><span data-stu-id="21b58-153">``Get-Cs<ConfigurationName>`` (for example, ``Get-CsTeamsClientConfiguration``):</span></span> 

- <span data-ttu-id="21b58-154">一連のコマンド (たとえば、 ``Set-CsTeamsClientConfiguration``): その種類の構成のプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="21b58-154">SET commands (for example, ``Set-CsTeamsClientConfiguration``): set properties in the configuration of that type.</span></span> <span data-ttu-id="21b58-155">変更するパラメーターを指定します。</span><span class="sxs-lookup"><span data-stu-id="21b58-155">Specify the parameters that you want to modify.</span></span>
   > <span data-ttu-id="21b58-156">2 つの方法のいずれかに変更する構成を参照することができます: を指定する -**ユーザーのグローバル**、または実行によって``Get-Cs<ConfigurationName>``  |  ``Set-Cs<ConfigurationName>``。</span><span class="sxs-lookup"><span data-stu-id="21b58-156">You can reference the configuration that you’re modifying in one of two ways: by specifying -**Identity Global**, or by running ``Get-Cs<ConfigurationName>`` | ``Set-Cs<ConfigurationName>``.</span></span>

## <a name="other-powershell-tools"></a><span data-ttu-id="21b58-157">他の PowerShell ツール</span><span class="sxs-lookup"><span data-stu-id="21b58-157">Other PowerShell tools</span></span>

<span data-ttu-id="21b58-158">マイクロソフトのチームとの[マイクロソフトのチームのコマンドレットのリファレンス](https://docs.microsoft.com/powershell/teams/?view=teams-ps)と Skype の[で、各ポリシーの設定の詳細な説明を含む、ビジネス用の Skype を管理するための PowerShell のすべてのコントロールを使用する方法の詳細な手順を表示します。ビジネス コマンドレット参照](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="21b58-158">You can find detailed instructions on how to use all PowerShell controls for managing Microsoft Teams and Skype for Business, including detailed descriptions of the settings in each policy, in the [Microsoft Teams cmdlet reference](https://docs.microsoft.com/powershell/teams/?view=teams-ps) and [Skype for Business cmdlet reference](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps).</span></span>

## <a name="learn-more"></a><span data-ttu-id="21b58-159">詳細情報</span><span class="sxs-lookup"><span data-stu-id="21b58-159">Learn more</span></span>

- [<span data-ttu-id="21b58-160">Microsoft Teams コマンドレット リファレンス</span><span class="sxs-lookup"><span data-stu-id="21b58-160">Microsoft Teams cmdlet reference</span></span>](https://docs.microsoft.com/powershell/teams/?view=teams-ps)
- [<span data-ttu-id="21b58-161">Skype ビジネス コマンドレット参照</span><span class="sxs-lookup"><span data-stu-id="21b58-161">Skype for Business cmdlet reference</span></span>](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)
- [<span data-ttu-id="21b58-162">Microsoft Teams の管理者ロールを使用して Teams を管理する</span><span class="sxs-lookup"><span data-stu-id="21b58-162">Use Microsoft Teams admin roles to manage Teams</span></span>](using-admin-roles.md)
