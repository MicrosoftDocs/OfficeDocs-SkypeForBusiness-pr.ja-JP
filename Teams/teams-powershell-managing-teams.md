---
title: PowerShell Teamsを使用Microsoft Teams管理する
ms.reviewer: brandber
author: brandber
ms.author: brandber
manager: kojiko
ms.date: 06/30/2020
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: PowerShell を使用してMicrosoft Teams管理Teams説明します。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 71f68c813a1379c29cf64ad732eb5da1ffe4d188
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2021
ms.locfileid: "52238973"
---
# <a name="manage-teams-with-microsoft-teams-powershell"></a><span data-ttu-id="137d3-103">PowerShell Teamsを使用Microsoft Teams管理する</span><span class="sxs-lookup"><span data-stu-id="137d3-103">Manage Teams with Microsoft Teams PowerShell</span></span>

<span data-ttu-id="137d3-104">この記事では、PowerShell を使用してMicrosoft Teams管理する方法Teams説明Skype for Business。</span><span class="sxs-lookup"><span data-stu-id="137d3-104">This article shows you how to use Microsoft Teams PowerShell to manage Teams and Skype for Business.</span></span> 

<span data-ttu-id="137d3-105">このガイダンスと、Microsoft Teams コマンドレット リファレンスと組み合わせて[Skype for Business](/powershell/teams/?view=teams-ps)[を使用します](/powershell/skype/intro?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="137d3-105">Use this guidance in conjunction with the [Microsoft Teams cmdlet reference](/powershell/teams/?view=teams-ps) and [Skype for Business cmdlet reference](/powershell/skype/intro?view=skype-ps).</span></span>

## <a name="create-and-manage-teams-using-powershell"></a><span data-ttu-id="137d3-106">PowerShell を使用してチームを作成および管理する</span><span class="sxs-lookup"><span data-stu-id="137d3-106">Create and manage teams using PowerShell</span></span>

<span data-ttu-id="137d3-107">チームを作成し管理するためのコマンドレットは、[Microsoft Teams PowerShell モジュール](https://www.powershellgallery.com/packages/MicrosoftTeams/)にあります。</span><span class="sxs-lookup"><span data-stu-id="137d3-107">The cmdlets for creating and managing teams are in the [Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams/).</span></span>

<span data-ttu-id="137d3-108">TeamsグループによってOffice 365されるので、チームを作成するときにグループを作成します。</span><span class="sxs-lookup"><span data-stu-id="137d3-108">Teams are backed by Office 365 Groups, so when you create a team, you create a group.</span></span> <span data-ttu-id="137d3-109">コア チームとその設定を操作するためのコマンドレット (``new-team``、``get-team``、``set-team``)、チームのユーザーを管理するためのコマンドレット (``add-teamuser``、``remove-teamuser``)、およびチームのチャネルを管理するためのコマンドレット (``new-teamchannel``、``remove-teamchannel``) のセットが用意されています。</span><span class="sxs-lookup"><span data-stu-id="137d3-109">There are a set of cmdlets provided for operating on the core team and its settings (``new-team``, ``get-team``,  ``set-team``), managing team users (``add-teamuser``, ``remove-teamuser``), as well as cmdlets for managing the channels of the team (``new-teamchannel``, ``remove-teamchannel``).</span></span> <span data-ttu-id="137d3-110">これらのコマンドレットはすべてエンド ユーザーとして実行できますが、自分が所有している、またはメンバーであるチームのみが機能します。</span><span class="sxs-lookup"><span data-stu-id="137d3-110">All of these cmdlets can be run as end users, but they'll work only on the teams that you own or are a member of.</span></span> <span data-ttu-id="137d3-111">グローバル管理者または管理者Teams、組織内のすべてのチームに対して行動できます。</span><span class="sxs-lookup"><span data-stu-id="137d3-111">If you are a Global Admin or Teams Administrator, you'll be able to act on all teams in your organization.</span></span>

```powershell
New-Team -DisplayName "Contoso Marketing" -Description "Collaboration space for Contoso's Marketing department"
```

> <span data-ttu-id="137d3-112">Microsoft Teams PowerShell モジュールのコマンドレットで使用されている **GroupId** は、Exchange PowerShell モジュールで ``Get-UnifiedGroup`` により返された **Identity** プロパティと同じです。</span><span class="sxs-lookup"><span data-stu-id="137d3-112">The **GroupId** used in the Microsoft Teams PowerShell module cmdlets is the same as the **Identity** property returned by ``Get-UnifiedGroup`` in the Exchange PowerShell module.</span></span>

## <a name="manage-policies-via-powershell"></a><span data-ttu-id="137d3-113">PowerShell を使用してポリシーを管理する</span><span class="sxs-lookup"><span data-stu-id="137d3-113">Manage policies via PowerShell</span></span>

> [!NOTE]
> - <span data-ttu-id="137d3-114">Skype for Businessオンライン コネクタは、PowerShell Teams統合されています。</span><span class="sxs-lookup"><span data-stu-id="137d3-114">Skype for Business Online Connector is being consolidated into Teams PowerShell.</span></span> <span data-ttu-id="137d3-115">現在、パブリック プレビューで使用できます。</span><span class="sxs-lookup"><span data-stu-id="137d3-115">It is currently available in public preview.</span></span> <span data-ttu-id="137d3-116">その後、Skype for Businessに適用される Teams Online コマンドレットは、PowerShell モジュールでネイティブTeams使用できます。</span><span class="sxs-lookup"><span data-stu-id="137d3-116">In time, Skype for Business Online cmdlets that apply to Teams will be natively available in the Teams PowerShell module.</span></span> <span data-ttu-id="137d3-117">インストール手順については[、PowerShell のインストールに関するTeams記事を参照](teams-powershell-install.md)してください。</span><span class="sxs-lookup"><span data-stu-id="137d3-117">Installation steps are available in the [Install Teams PowerShell](teams-powershell-install.md) article.</span></span>
>
> - <span data-ttu-id="137d3-118">Skype for Business Online に接続すると、PowerShell セッションでコマンドレットを使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="137d3-118">The cmdlets will be available in your PowerShell session once you connect to Skype for Business Online.</span></span> <span data-ttu-id="137d3-119">詳細については、「[Office 365 PowerShell を使用して Skype for Business Online を管理する](/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="137d3-119">For more information, please see [Manage Skype for Business Online with Office 365 PowerShell](/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).</span></span>

<span data-ttu-id="137d3-120">Skype for Business コマンドレット モジュールでポリシーを[管理するためのコマンドレットを探します](/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell)。</span><span class="sxs-lookup"><span data-stu-id="137d3-120">Find the cmdlets for managing policies in the [Skype for Business cmdlet module](/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell).</span></span>

<span data-ttu-id="137d3-121">ポリシーは、個々のユーザーに細かく適用できる設定のまとまりです。</span><span class="sxs-lookup"><span data-stu-id="137d3-121">A policy is a group of settings that can be applied granularly to individual users.</span></span> <span data-ttu-id="137d3-122">各ポリシーの種類にはポリシーそのものの作成、表示、削除、更新を行い、これらのポリシーをユーザーに割り当てるための独自のコマンドレットのセットがあります。</span><span class="sxs-lookup"><span data-stu-id="137d3-122">Each policy type has its own set of cmdlets for creating, viewing, deleting, and updating the policies themselves, and then assigning those policies to users.</span></span> <span data-ttu-id="137d3-123">一般的な構成は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="137d3-123">The general structure is:</span></span>

- <span data-ttu-id="137d3-124">**GET** コマンド (例: ): 使用する Microsoft によって作成されたポリシーや、作成したカスタム ポリシーなど、組織内で割り当て可能なポリシー ドキュメントを返します。 ``Get-CsTeamsMeetingPolicy``</span><span class="sxs-lookup"><span data-stu-id="137d3-124">**GET** commands (for example, ``Get-CsTeamsMeetingPolicy``): Returns the policy documents that are available for you to assign in your organization, including the policies created by Microsoft for you to use as well as the custom policies you’ve created.</span></span>
   - <span data-ttu-id="137d3-125">組織で作成したカスタム ポリシーのみを検索するには、 を使用します ``-Filter "tag:*"`` 。</span><span class="sxs-lookup"><span data-stu-id="137d3-125">To find only the custom policies you’ve created in your organization, use ``-Filter "tag:*"``.</span></span>

- <span data-ttu-id="137d3-126">**新** しいコマンド (例: ): 組織内のユーザーに割り当てる組織の新しい ``New-CsTeamsMeetingPolicy`` ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="137d3-126">**NEW** commands (for example, ``New-CsTeamsMeetingPolicy``): Creates new policies for your organization to assign to users in your organization.</span></span> <span data-ttu-id="137d3-127">すべてのポリシーがカスタム ポリシーの作成をサポートするわけではありません。</span><span class="sxs-lookup"><span data-stu-id="137d3-127">Not all policies support the creation of custom policies.</span></span> <span data-ttu-id="137d3-128">多くの場合、組織で使用するポリシーに、サポート対象の設定の組み合わせがあることを確認するためです。</span><span class="sxs-lookup"><span data-stu-id="137d3-128">Often this is to ensure that the policies you use in your organization have a supported combination of settings.</span></span>

- <span data-ttu-id="137d3-129">**SET** コマンド (例: ``Set-CsTeamsMeetingPolicy`` ): 特定のポリシーの特定の値を設定します。</span><span class="sxs-lookup"><span data-stu-id="137d3-129">**SET** commands (for example, ``Set-CsTeamsMeetingPolicy``): Sets particular values on a given policy.</span></span> <span data-ttu-id="137d3-130">一部のポリシーには、SET コマンドを使用できないか、ポリシーでカスタマイズできないパラメーターが含まれています。</span><span class="sxs-lookup"><span data-stu-id="137d3-130">Some policies don't have SET commands available, or they contain parameters that can't be customized in the policy.</span></span> <span data-ttu-id="137d3-131">PowerShell の説明では、カスタマイズできないパラメーターが示されます。</span><span class="sxs-lookup"><span data-stu-id="137d3-131">The PowerShell descriptions tell you which parameters can't be customized.</span></span> 
   - <span data-ttu-id="137d3-132">カスタム ポリシーが割り当てられていない組織内のユーザーに既定で割り当てられるポリシーを編集するには、``Set-Cs<PolicyName> -Identity Global`` を実行します。</span><span class="sxs-lookup"><span data-stu-id="137d3-132">To edit the policy that will by default be assigned to users in your organization who do not have a custom policy assigned, run ``Set-Cs<PolicyName> -Identity Global``.</span></span>

- <span data-ttu-id="137d3-133">**REMOVE** コマンド (例: ): テナントに作成されたカスタム ``Remove-CsTeamsMeetingPolicy`` ポリシーを削除します。</span><span class="sxs-lookup"><span data-stu-id="137d3-133">**REMOVE** commands (for example, ``Remove-CsTeamsMeetingPolicy``): Deletes a custom policy that has been created in your tenant.</span></span> <span data-ttu-id="137d3-134">組織内の少なくとも 1 人のユーザーに割り当てられているカスタム ポリシーを削除した場合、そのユーザーはグローバル ポリシーに戻ります。</span><span class="sxs-lookup"><span data-stu-id="137d3-134">If you delete a custom policy that has been assigned to at least one user in your organization, that user will fall back to the global policy.</span></span>
   - <span data-ttu-id="137d3-135">組織のグローバル ポリシーを実際に削除する必要がありますが、組織のグローバル ポリシーを Microsoft が提供する既定の設定にリセットする場合は、 を実行します ``Remove-Cs<PolicyName> -Identity Global`` 。</span><span class="sxs-lookup"><span data-stu-id="137d3-135">You can’t actually remove the global policy in your organization, but if you want to reset the global policy in your organization to the Microsoft-provided default settings, run ``Remove-Cs<PolicyName> -Identity Global``.</span></span>

- <span data-ttu-id="137d3-136">**GRANT** コマンド (例 ``Grant-CsTeamsMeetingPolicy`` : ): 特定のユーザーにポリシーを割り当てる。</span><span class="sxs-lookup"><span data-stu-id="137d3-136">**GRANT** command (for example, ``Grant-CsTeamsMeetingPolicy``): Assigns a policy to a particular user.</span></span>
   - <span data-ttu-id="137d3-137">カスタム ポリシーの割り当てを削除し、組織の既定のポリシーにユーザーを戻すには、``Grant-Cs<PolicyName> -Identity <User Identity> -PolicyName $null`` を実行します。</span><span class="sxs-lookup"><span data-stu-id="137d3-137">To remove a custom policy assignment and make the user fall back to the default policy in your organization, run ``Grant-Cs<PolicyName> -Identity <User Identity> -PolicyName $null``.</span></span>

> [!TIP]
> <span data-ttu-id="137d3-138">すべてのポリシーでカスタム ポリシーの作成が許可されているわけではなく、一部のポリシーにはカスタマイズできない設定が含まれています (そのため、設定は表示できますが、``set-`` と``new-`` の間にカスタム値を設定できません)。</span><span class="sxs-lookup"><span data-stu-id="137d3-138">Not all policies allow custom policies to be created, and some policies have settings that you can’t customize (so you can view the setting but can’t set a custom value during ``set-`` and ``new-``).</span></span> <span data-ttu-id="137d3-139">各コマンドレットのドキュメントでは、顧客がパラメーターを使用できるかどうかが示されています。</span><span class="sxs-lookup"><span data-stu-id="137d3-139">The documentation for each cmdlet calls out whether parameters are available for use by customers.</span></span>

<span data-ttu-id="137d3-140">共通パラメーター:</span><span class="sxs-lookup"><span data-stu-id="137d3-140">Common parameters:</span></span>

- <span data-ttu-id="137d3-141">**Identity**: ``Get-``、``Set-``、``New-``、``Remove-`` の場合、**Identity** パラメーターは常に特定のポリシー インスタンスを参照します。</span><span class="sxs-lookup"><span data-stu-id="137d3-141">**Identity**: For ``Get-``, ``Set-``, ``New-``, and ``Remove-``, the **Identity** parameter will always refer to a specific policy instance.</span></span> <span data-ttu-id="137d3-142">``Grant`` の場合、**Identity** パラメーターは、ポリシーが適用されている特定のユーザー オブジェクトを参照します。</span><span class="sxs-lookup"><span data-stu-id="137d3-142">For ``Grant``, the **Identity** parameter refers to a specific user object to whom the policy is being applied.</span></span>

## <a name="manage-configurations-via-powershell"></a><span data-ttu-id="137d3-143">PowerShell を使用して構成を管理する</span><span class="sxs-lookup"><span data-stu-id="137d3-143">Manage configurations via PowerShell</span></span>

<span data-ttu-id="137d3-144">構成を管理するためのコマンドレットについては、Skype for Business コマンドレット[モジュールを参照してください](/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell)。</span><span class="sxs-lookup"><span data-stu-id="137d3-144">Find the cmdlets for managing your configuration in the [Skype for Business cmdlet module](/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell).</span></span>

<span data-ttu-id="137d3-145">構成は、ユーザー レベルで指定できない、サービスで保持される設定のバケットです。</span><span class="sxs-lookup"><span data-stu-id="137d3-145">Configurations are buckets of settings maintained in the service that can't be specified at a user level.</span></span> <span data-ttu-id="137d3-146">設定は常に組織全体に適用されます。</span><span class="sxs-lookup"><span data-stu-id="137d3-146">Settings always apply across the whole organization.</span></span> <span data-ttu-id="137d3-147">グローバル構成は、組織で唯一の有効な構成です。</span><span class="sxs-lookup"><span data-stu-id="137d3-147">Your global configuration is the only effective configuration in your organization.</span></span> <span data-ttu-id="137d3-148">各構成の種類には、次の 2 つの主なコマンドレットが用意されています。</span><span class="sxs-lookup"><span data-stu-id="137d3-148">Each configuration type comes with two primary cmdlets:</span></span>

- <span data-ttu-id="137d3-149">``Get-Cs<ConfigurationName>`` (例: ``Get-CsTeamsClientConfiguration``):</span><span class="sxs-lookup"><span data-stu-id="137d3-149">``Get-Cs<ConfigurationName>`` (for example, ``Get-CsTeamsClientConfiguration``):</span></span>

- <span data-ttu-id="137d3-150">SET コマンド (例:``Set-CsTeamsClientConfiguration`` ): その種類の構成でプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="137d3-150">SET commands (for example, ``Set-CsTeamsClientConfiguration``): set properties in the configuration of that type.</span></span> <span data-ttu-id="137d3-151">変更するパラメーターを指定します。</span><span class="sxs-lookup"><span data-stu-id="137d3-151">Specify the parameters that you want to modify.</span></span>
   > <span data-ttu-id="137d3-152">**Identity Global** の指定、または ``Get-Cs<ConfigurationName>`` | ``Set-Cs<ConfigurationName>`` の実行のいずれかの方法で変更を行っている構成を参照できます。</span><span class="sxs-lookup"><span data-stu-id="137d3-152">You can reference the configuration that you’re modifying in one of two ways: by specifying -**Identity Global**, or by running ``Get-Cs<ConfigurationName>`` | ``Set-Cs<ConfigurationName>``.</span></span>

## <a name="what-can-each-admin-role-do"></a><span data-ttu-id="137d3-153">管理者の役割がそれぞれできること</span><span class="sxs-lookup"><span data-stu-id="137d3-153">What can each admin role do?</span></span>

<span data-ttu-id="137d3-154">各 PowerShell[コマンドレットMicrosoft Teams実行できる管理者ロールを](using-admin-roles.md)Teams管理者ロールを使用して管理する方法に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="137d3-154">Read [Use Microsoft Teams admin roles to manage Teams](using-admin-roles.md) to understand which admin roles can run each PowerShell cmdlet.</span></span>

## <a name="related-topics"></a><span data-ttu-id="137d3-155">関連トピック</span><span class="sxs-lookup"><span data-stu-id="137d3-155">Related topics</span></span>

[<span data-ttu-id="137d3-156">Teams Powershell のインストール</span><span class="sxs-lookup"><span data-stu-id="137d3-156">Installing Teams PowerShell</span></span>](teams-powershell-install.md)

[<span data-ttu-id="137d3-157">Teams PowerShell のリリース ノート</span><span class="sxs-lookup"><span data-stu-id="137d3-157">Teams PowerShell Release Notes</span></span>](teams-powershell-release-notes.md)

[<span data-ttu-id="137d3-158">Teams コマンドレット リファレンス</span><span class="sxs-lookup"><span data-stu-id="137d3-158">Teams cmdlet reference</span></span>](/powershell/teams/?view=teams-ps)

[<span data-ttu-id="137d3-159">Skype for Business コマンドレット リファレンス</span><span class="sxs-lookup"><span data-stu-id="137d3-159">Skype for Business cmdlet reference</span></span>](/powershell/skype/intro?view=skype-ps)

[<span data-ttu-id="137d3-160">Teams 管理者ロールを使用してTeams を管理します</span><span class="sxs-lookup"><span data-stu-id="137d3-160">Use Teams admin roles to manage Teams</span></span>](using-admin-roles.md)