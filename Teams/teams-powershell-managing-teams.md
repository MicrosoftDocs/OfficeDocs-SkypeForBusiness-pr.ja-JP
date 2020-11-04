---
title: Microsoft Teams PowerShell を使用してチームを管理する
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
description: Teams PowerShell を使用して Microsoft Teams を管理する方法について説明します。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 09d11b2c697ba57ea161d0ce961cf5ba73794617
ms.sourcegitcommit: 3f465eb6eb46db008f2b69fc4c6bb425d432dfcc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2020
ms.locfileid: "48852178"
---
# <a name="manage-teams-with-microsoft-teams-powershell"></a><span data-ttu-id="3efc6-103">Microsoft Teams PowerShell を使用してチームを管理する</span><span class="sxs-lookup"><span data-stu-id="3efc6-103">Manage Teams with Microsoft Teams PowerShell</span></span>

<span data-ttu-id="3efc6-104">この記事では、Microsoft Teams PowerShell を使用してチームと Skype for Business を管理する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="3efc6-104">This article shows you how to use Microsoft Teams PowerShell to manage Teams and Skype for Business.</span></span> 

<span data-ttu-id="3efc6-105">このガイダンスは、 [Microsoft Teams コマンドレットリファレンス](https://docs.microsoft.com/powershell/teams/?view=teams-ps) および [Skype for business コマンドレットリファレンス](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)と組み合わせて使用してください。</span><span class="sxs-lookup"><span data-stu-id="3efc6-105">Use this guidance in conjunction with the [Microsoft Teams cmdlet reference](https://docs.microsoft.com/powershell/teams/?view=teams-ps) and [Skype for Business cmdlet reference](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps).</span></span>

## <a name="create-and-manage-teams-using-powershell"></a><span data-ttu-id="3efc6-106">PowerShell を使用してチームを作成して管理する</span><span class="sxs-lookup"><span data-stu-id="3efc6-106">Create and manage teams using PowerShell</span></span>

<span data-ttu-id="3efc6-107">チームを作成し管理するためのコマンドレットは、[Microsoft Teams PowerShell モジュール](https://www.powershellgallery.com/packages/MicrosoftTeams/)にあります。</span><span class="sxs-lookup"><span data-stu-id="3efc6-107">The cmdlets for creating and managing teams are in the [Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams/).</span></span>

<span data-ttu-id="3efc6-108">Teams は Office 365 グループによってサポートされているので、チームを作成するときにグループを作成します。</span><span class="sxs-lookup"><span data-stu-id="3efc6-108">Teams are backed by Office 365 Groups, so when you create a team, you create a group.</span></span> <span data-ttu-id="3efc6-109">コア チームとその設定を操作するためのコマンドレット (``new-team``、``get-team``、``set-team``)、チームのユーザーを管理するためのコマンドレット (``add-teamuser``、``remove-teamuser``)、およびチームのチャネルを管理するためのコマンドレット (``new-teamchannel``、``remove-teamchannel``) のセットが用意されています。</span><span class="sxs-lookup"><span data-stu-id="3efc6-109">There are a set of cmdlets provided for operating on the core team and its settings (``new-team``, ``get-team``,  ``set-team``), managing team users (``add-teamuser``, ``remove-teamuser``), as well as cmdlets for managing the channels of the team (``new-teamchannel``, ``remove-teamchannel``).</span></span> <span data-ttu-id="3efc6-110">これらのコマンドレットはすべてエンド ユーザーとして実行できますが、自分が所有している、またはメンバーであるチームのみが機能します。</span><span class="sxs-lookup"><span data-stu-id="3efc6-110">All of these cmdlets can be run as end users, but they'll work only on the teams that you own or are a member of.</span></span> <span data-ttu-id="3efc6-111">グローバル管理者または Teams サービス管理者であれば、組織内のすべてのチームに実行できます。</span><span class="sxs-lookup"><span data-stu-id="3efc6-111">If you are a Global Admin or Teams Service Administrator, you'll be able to act on all teams in your organization.</span></span>

```powershell
New-Team -Name "Contoso Marketing" -Description "Collaboration space for Contoso's Marketing department"
```

> <span data-ttu-id="3efc6-112">Microsoft Teams PowerShell モジュールのコマンドレットで使用されている **GroupId** は、Exchange PowerShell モジュールで ``Get-UnifiedGroup`` により返された **Identity** プロパティと同じです。</span><span class="sxs-lookup"><span data-stu-id="3efc6-112">The **GroupId** used in the Microsoft Teams PowerShell module cmdlets is the same as the **Identity** property returned by ``Get-UnifiedGroup`` in the Exchange PowerShell module.</span></span>

## <a name="manage-policies-via-powershell"></a><span data-ttu-id="3efc6-113">PowerShell を使用してポリシーを管理する</span><span class="sxs-lookup"><span data-stu-id="3efc6-113">Manage policies via PowerShell</span></span>

> [!NOTE]
> - <span data-ttu-id="3efc6-114">Skype for Business Online Connector は Teams PowerShell に統合されています。</span><span class="sxs-lookup"><span data-stu-id="3efc6-114">Skype for Business Online Connector is being consolidated into Teams PowerShell.</span></span> <span data-ttu-id="3efc6-115">現在、パブリックプレビューで利用できます。</span><span class="sxs-lookup"><span data-stu-id="3efc6-115">It is currently available in public preview.</span></span> <span data-ttu-id="3efc6-116">現時点では、Teams に適用される Skype for Business Online のコマンドレットは、Teams PowerShell モジュールでネイティブで利用できます。</span><span class="sxs-lookup"><span data-stu-id="3efc6-116">In time, Skype for Business Online cmdlets that apply to Teams will be natively available in the Teams PowerShell module.</span></span> <span data-ttu-id="3efc6-117">インストールの手順については、「 [Teams PowerShell のインストール](teams-powershell-install.md) 」の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3efc6-117">Installation steps are available in the [Install Teams PowerShell](teams-powershell-install.md) article.</span></span>
>
> - <span data-ttu-id="3efc6-118">Skype for Business Online に接続すると、PowerShell セッションでコマンドレットを使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="3efc6-118">The cmdlets will be available in your PowerShell session once you connect to Skype for Business Online.</span></span> <span data-ttu-id="3efc6-119">詳細については、「[Office 365 PowerShell を使用して Skype for Business Online を管理する](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3efc6-119">For more information, please see [Manage Skype for Business Online with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).</span></span>

<span data-ttu-id="3efc6-120">[Skype For business コマンドレットモジュール](https://www.microsoft.com/download/details.aspx?id=39366)でポリシーを管理するためのコマンドレットを見つけます。</span><span class="sxs-lookup"><span data-stu-id="3efc6-120">Find the cmdlets for managing policies in the [Skype for Business cmdlet module](https://www.microsoft.com/download/details.aspx?id=39366).</span></span>

<span data-ttu-id="3efc6-121">ポリシーは、個々のユーザーに細かく適用できる設定のまとまりです。</span><span class="sxs-lookup"><span data-stu-id="3efc6-121">A policy is a group of settings that can be applied granularly to individual users.</span></span> <span data-ttu-id="3efc6-122">各ポリシーの種類にはポリシーそのものの作成、表示、削除、更新を行い、これらのポリシーをユーザーに割り当てるための独自のコマンドレットのセットがあります。</span><span class="sxs-lookup"><span data-stu-id="3efc6-122">Each policy type has its own set of cmdlets for creating, viewing, deleting, and updating the policies themselves, and then assigning those policies to users.</span></span> <span data-ttu-id="3efc6-123">一般的な構成は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="3efc6-123">The general structure is:</span></span>

- <span data-ttu-id="3efc6-124">**GET** コマンド (など): Microsoft によって作成されたポリシーや、作成した ``Get-CsTeamsMeetingPolicy`` カスタムポリシーなど、組織内で割り当てることができるポリシードキュメントが返されます。</span><span class="sxs-lookup"><span data-stu-id="3efc6-124">**GET** commands (for example, ``Get-CsTeamsMeetingPolicy``): Returns the policy documents that are available for you to assign in your organization, including the policies created by Microsoft for you to use as well as the custom policies you’ve created.</span></span>
   - <span data-ttu-id="3efc6-125">組織で作成したカスタムポリシーのみを検索するには、を使用 ``-Filter "tag:*"`` します。</span><span class="sxs-lookup"><span data-stu-id="3efc6-125">To find only the custom policies you’ve created in your organization, use ``-Filter "tag:*"``.</span></span>

- <span data-ttu-id="3efc6-126">**新しい** コマンド (など ``New-CsTeamsMeetingPolicy`` ): 組織のユーザーに割り当てる新しいポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="3efc6-126">**NEW** commands (for example, ``New-CsTeamsMeetingPolicy``): Creates new policies for your organization to assign to users in your organization.</span></span> <span data-ttu-id="3efc6-127">すべてのポリシーがカスタム ポリシーの作成をサポートするわけではありません。</span><span class="sxs-lookup"><span data-stu-id="3efc6-127">Not all policies support the creation of custom policies.</span></span> <span data-ttu-id="3efc6-128">多くの場合、組織で使用するポリシーに、サポート対象の設定の組み合わせがあることを確認するためです。</span><span class="sxs-lookup"><span data-stu-id="3efc6-128">Often this is to ensure that the policies you use in your organization have a supported combination of settings.</span></span>

- <span data-ttu-id="3efc6-129">**SET** コマンド (例:) は、特定の ``Set-CsTeamsMeetingPolicy`` ポリシーの特定の値を設定します。</span><span class="sxs-lookup"><span data-stu-id="3efc6-129">**SET** commands (for example, ``Set-CsTeamsMeetingPolicy``): Sets particular values on a given policy.</span></span> <span data-ttu-id="3efc6-130">一部のポリシーでは、SET コマンドが利用できない場合や、ポリシーでカスタマイズできないパラメーターが含まれている場合があります。</span><span class="sxs-lookup"><span data-stu-id="3efc6-130">Some policies don't have SET commands available, or they contain parameters that can't be customized in the policy.</span></span> <span data-ttu-id="3efc6-131">PowerShell の説明には、カスタマイズできないパラメーターが示されます。</span><span class="sxs-lookup"><span data-stu-id="3efc6-131">The PowerShell descriptions tell you which parameters can't be customized.</span></span> 
   - <span data-ttu-id="3efc6-132">カスタム ポリシーが割り当てられていない組織内のユーザーに既定で割り当てられるポリシーを編集するには、``Set-Cs<PolicyName> -Identity Global`` を実行します。</span><span class="sxs-lookup"><span data-stu-id="3efc6-132">To edit the policy that will by default be assigned to users in your organization who do not have a custom policy assigned, run ``Set-Cs<PolicyName> -Identity Global``.</span></span>

- <span data-ttu-id="3efc6-133">コマンドの **削除** (など ``Remove-CsTeamsMeetingPolicy`` ): テナントで作成されたカスタムポリシーを削除します。</span><span class="sxs-lookup"><span data-stu-id="3efc6-133">**REMOVE** commands (for example, ``Remove-CsTeamsMeetingPolicy``): Deletes a custom policy that has been created in your tenant.</span></span> <span data-ttu-id="3efc6-134">組織内の少なくとも 1 人のユーザーに割り当てられているカスタム ポリシーを削除した場合、そのユーザーはグローバル ポリシーに戻ります。</span><span class="sxs-lookup"><span data-stu-id="3efc6-134">If you delete a custom policy that has been assigned to at least one user in your organization, that user will fall back to the global policy.</span></span>
   - <span data-ttu-id="3efc6-135">組織内のグローバルポリシーを実際に削除することはできませんが、組織内のグローバルポリシーを Microsoft が提供する既定の設定にリセットする場合は、を実行 ``Remove-Cs<PolicyName> -Identity Global`` します。</span><span class="sxs-lookup"><span data-stu-id="3efc6-135">You can’t actually remove the global policy in your organization, but if you want to reset the global policy in your organization to the Microsoft-provided default settings, run ``Remove-Cs<PolicyName> -Identity Global``.</span></span>

- <span data-ttu-id="3efc6-136">[ **GRANT** ] コマンド (例 ``Grant-CsTeamsMeetingPolicy`` :): 特定のユーザーにポリシーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="3efc6-136">**GRANT** command (for example, ``Grant-CsTeamsMeetingPolicy``): Assigns a policy to a particular user.</span></span>
   - <span data-ttu-id="3efc6-137">カスタム ポリシーの割り当てを削除し、組織の既定のポリシーにユーザーを戻すには、``Grant-Cs<PolicyName> -Identity <User Identity> -PolicyName $null`` を実行します。</span><span class="sxs-lookup"><span data-stu-id="3efc6-137">To remove a custom policy assignment and make the user fall back to the default policy in your organization, run ``Grant-Cs<PolicyName> -Identity <User Identity> -PolicyName $null``.</span></span>

> [!TIP]
> <span data-ttu-id="3efc6-138">すべてのポリシーでカスタム ポリシーの作成が許可されているわけではなく、一部のポリシーにはカスタマイズできない設定が含まれています (そのため、設定は表示できますが、``set-`` と``new-`` の間にカスタム値を設定できません)。</span><span class="sxs-lookup"><span data-stu-id="3efc6-138">Not all policies allow custom policies to be created, and some policies have settings that you can’t customize (so you can view the setting but can’t set a custom value during ``set-`` and ``new-``).</span></span> <span data-ttu-id="3efc6-139">各コマンドレットのドキュメントは、ユーザーが使用できるパラメーターかどうかを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="3efc6-139">The documentation for each cmdlet calls out whether parameters are available for use by customers.</span></span>

<span data-ttu-id="3efc6-140">共通パラメーター:</span><span class="sxs-lookup"><span data-stu-id="3efc6-140">Common parameters:</span></span>

- <span data-ttu-id="3efc6-141">**Identity** : ``Get-``、``Set-``、``New-``、``Remove-`` の場合、 **Identity** パラメーターは常に特定のポリシー インスタンスを参照します。</span><span class="sxs-lookup"><span data-stu-id="3efc6-141">**Identity** : For ``Get-``, ``Set-``, ``New-``, and ``Remove-``, the **Identity** parameter will always refer to a specific policy instance.</span></span> <span data-ttu-id="3efc6-142">``Grant`` の場合、 **Identity** パラメーターは、ポリシーが適用されている特定のユーザー オブジェクトを参照します。</span><span class="sxs-lookup"><span data-stu-id="3efc6-142">For ``Grant``, the **Identity** parameter refers to a specific user object to whom the policy is being applied.</span></span>

## <a name="manage-configurations-via-powershell"></a><span data-ttu-id="3efc6-143">PowerShell を使用した構成の管理</span><span class="sxs-lookup"><span data-stu-id="3efc6-143">Manage configurations via PowerShell</span></span>

<span data-ttu-id="3efc6-144">[Skype For business コマンドレットモジュール](https://www.microsoft.com/en-us/download/details.aspx?id=39366)で構成を管理するためのコマンドレットについて説明します。</span><span class="sxs-lookup"><span data-stu-id="3efc6-144">Find the cmdlets for managing your configuration in the [Skype for Business cmdlet module](https://www.microsoft.com/en-us/download/details.aspx?id=39366).</span></span>

<span data-ttu-id="3efc6-145">構成は、サービスに保持されている設定のバケットであり、ユーザーレベルで指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="3efc6-145">Configurations are buckets of settings maintained in the service that can't be specified at a user level.</span></span> <span data-ttu-id="3efc6-146">設定は常に組織全体に適用されます。</span><span class="sxs-lookup"><span data-stu-id="3efc6-146">Settings always apply across the whole organization.</span></span> <span data-ttu-id="3efc6-147">グローバル構成は、組織で唯一の有効な構成です。</span><span class="sxs-lookup"><span data-stu-id="3efc6-147">Your global configuration is the only effective configuration in your organization.</span></span> <span data-ttu-id="3efc6-148">各構成の種類には、次の 2 つの主なコマンドレットが用意されています。</span><span class="sxs-lookup"><span data-stu-id="3efc6-148">Each configuration type comes with two primary cmdlets:</span></span>

- <span data-ttu-id="3efc6-149">``Get-Cs<ConfigurationName>`` (例: ``Get-CsTeamsClientConfiguration``):</span><span class="sxs-lookup"><span data-stu-id="3efc6-149">``Get-Cs<ConfigurationName>`` (for example, ``Get-CsTeamsClientConfiguration``):</span></span>

- <span data-ttu-id="3efc6-150">SET コマンド (例:``Set-CsTeamsClientConfiguration`` ): その種類の構成でプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="3efc6-150">SET commands (for example, ``Set-CsTeamsClientConfiguration``): set properties in the configuration of that type.</span></span> <span data-ttu-id="3efc6-151">変更するパラメーターを指定します。</span><span class="sxs-lookup"><span data-stu-id="3efc6-151">Specify the parameters that you want to modify.</span></span>
   > <span data-ttu-id="3efc6-152">**Identity Global** の指定、または ``Get-Cs<ConfigurationName>`` | ``Set-Cs<ConfigurationName>`` の実行のいずれかの方法で変更を行っている構成を参照できます。</span><span class="sxs-lookup"><span data-stu-id="3efc6-152">You can reference the configuration that you’re modifying in one of two ways: by specifying - **Identity Global** , or by running ``Get-Cs<ConfigurationName>`` | ``Set-Cs<ConfigurationName>``.</span></span>

## <a name="what-can-each-admin-role-do"></a><span data-ttu-id="3efc6-153">管理者の役割がそれぞれできること</span><span class="sxs-lookup"><span data-stu-id="3efc6-153">What can each admin role do?</span></span>

<span data-ttu-id="3efc6-154">「 [Microsoft Teams の管理者ロールを使用](using-admin-roles.md) してチームを管理し、各 PowerShell コマンドレットを実行できる管理者ロールについて理解する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3efc6-154">Read [Use Microsoft Teams admin roles to manage Teams](using-admin-roles.md) to understand which admin roles can run each PowerShell cmdlet.</span></span>

## <a name="related-topics"></a><span data-ttu-id="3efc6-155">関連トピック</span><span class="sxs-lookup"><span data-stu-id="3efc6-155">Related topics</span></span>

[<span data-ttu-id="3efc6-156">Teams Powershell のインストール</span><span class="sxs-lookup"><span data-stu-id="3efc6-156">Installing Teams PowerShell</span></span>](teams-powershell-install.md)

[<span data-ttu-id="3efc6-157">Teams PowerShell のリリース ノート</span><span class="sxs-lookup"><span data-stu-id="3efc6-157">Teams PowerShell Release Notes</span></span>](teams-powershell-release-notes.md)

[<span data-ttu-id="3efc6-158">Teams コマンドレット リファレンス</span><span class="sxs-lookup"><span data-stu-id="3efc6-158">Teams cmdlet reference</span></span>](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[<span data-ttu-id="3efc6-159">Skype for Business コマンドレット リファレンス</span><span class="sxs-lookup"><span data-stu-id="3efc6-159">Skype for Business cmdlet reference</span></span>](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)

[<span data-ttu-id="3efc6-160">Teams 管理者ロールを使用してTeams を管理します</span><span class="sxs-lookup"><span data-stu-id="3efc6-160">Use Teams admin roles to manage Teams</span></span>](using-admin-roles.md)
