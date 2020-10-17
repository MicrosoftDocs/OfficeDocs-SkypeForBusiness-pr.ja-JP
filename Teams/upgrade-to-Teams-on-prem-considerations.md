---
title: Skype for Business オンプレミス展開から Teams へのアップグレード - Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 09/16/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: Skype for Business から Teams へのアップグレード
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: cf034969c2b6ca030eede72ff358a517fafe501f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48533594"
---
# <a name="upgrade-considerations-for-organizations-with-skype-for-business-server-on-premises-mdash-for-it-administrators"></a><span data-ttu-id="cce70-103">&mdash;IT 管理者向けの Skype For Business Server がオンプレミスの組織のアップグレードに関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="cce70-103">Upgrade considerations for organizations with Skype for Business Server on-premises &mdash; for IT administrators</span></span>

<span data-ttu-id="cce70-104">この記事では、オンプレミスの Skype for Business Server を使用する組織に関するその他の考慮事項について説明します。</span><span class="sxs-lookup"><span data-stu-id="cce70-104">This article describes additional considerations for organizations with Skype for Business Server on-premises.</span></span> <span data-ttu-id="cce70-105">この記事は、IT 管理者向けのアップグレードの概念と実装を説明するいくつかの4つの部分です。</span><span class="sxs-lookup"><span data-stu-id="cce70-105">This article is the fourth of several that describe upgrade concepts and implementation for IT administrators.</span></span>  

- [<span data-ttu-id="cce70-106">概要</span><span class="sxs-lookup"><span data-stu-id="cce70-106">Overview</span></span>](upgrade-to-teams-on-prem-overview.md)
- [<span data-ttu-id="cce70-107">アップグレード方法</span><span class="sxs-lookup"><span data-stu-id="cce70-107">Upgrade methods</span></span>](upgrade-to-teams-on-prem-upgrade-methods.md)
- [<span data-ttu-id="cce70-108">アップグレードを管理するためのツール</span><span class="sxs-lookup"><span data-stu-id="cce70-108">Tools for managing your upgrade</span></span>](upgrade-to-teams-on-prem-tools.md)
- <span data-ttu-id="cce70-109">**Skype For business オンプレミスの組織に関するその他の考慮事項** (この記事)</span><span class="sxs-lookup"><span data-stu-id="cce70-109">**Additional considerations for organizations with Skype for Business on-premises** (this article)</span></span>
- [<span data-ttu-id="cce70-110">アップグレードの実装</span><span class="sxs-lookup"><span data-stu-id="cce70-110">Implementing your upgrade</span></span>](upgrade-to-teams-on-prem-implement.md)
- [<span data-ttu-id="cce70-111">公衆交換電話網 (PSTN) に関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="cce70-111">Public Switched Telephone Network (PSTN) considerations</span></span>](upgrade-to-teams-on-prem-pstn-considerations.md)

<span data-ttu-id="cce70-112">さらに、次の記事では、アップグレードの重要な概念と共存の動作について説明します。</span><span class="sxs-lookup"><span data-stu-id="cce70-112">In addition, the following articles describe important upgrade concepts and coexistence behaviors:</span></span>

- [<span data-ttu-id="cce70-113">Teams と Skype for Business の共存</span><span class="sxs-lookup"><span data-stu-id="cce70-113">Coexistence of Teams and Skype for Business</span></span>](upgrade-to-teams-on-prem-coexistence.md)
- [<span data-ttu-id="cce70-114">共存モード-参照</span><span class="sxs-lookup"><span data-stu-id="cce70-114">Coexistence modes - Reference</span></span>](migration-interop-guidance-for-teams-with-skype.md)
- [<span data-ttu-id="cce70-115">Teams のクライアント エクスペリエンスおよび共存モードへの準拠</span><span class="sxs-lookup"><span data-stu-id="cce70-115">Teams client experience and conformance to coexistence modes</span></span>](teams-client-experience-and-conformance-to-coexistence-modes.md)



## <a name="considerations-for-organizations-with-skype-for-business-server-on-premises"></a><span data-ttu-id="cce70-116">オンプレミスの Skype for Business Server を使用する組織に関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="cce70-116">Considerations for organizations with Skype for Business Server on-premises</span></span>

- <span data-ttu-id="cce70-117">Skype for Business Hybrid のセットアップは、TeamsOnly モードへの移行の前提条件です。</span><span class="sxs-lookup"><span data-stu-id="cce70-117">Setting up Skype for Business hybrid is a prerequisite to migrate to TeamsOnly mode.</span></span> <span data-ttu-id="cce70-118">ハイブリッドを使用せずにアイランド モードで Teams を使用することは可能ですが、そのユーザーが Skype for Business オンプレミスから Skype for Business Online に移行されるまで ([Move-CsUser](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud) を使用して) は、TeamsOnly モードには移行できません。</span><span class="sxs-lookup"><span data-stu-id="cce70-118">While it is possible to use Teams in Islands mode without hybrid, the transition to TeamsOnly mode cannot be made until the user is moved from Skype for Business on-premises to Skype for Business Online (using [Move-CsUser](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)).</span></span> <span data-ttu-id="cce70-119">詳細については、「[ハイブリッド接続を構成する](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-hybrid-connectivity)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cce70-119">For more information, see [Configure hybrid connectivity](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-hybrid-connectivity).</span></span>

- <span data-ttu-id="cce70-120">組織に Skype for Business Server があり、ハイブリッド接続を設定していないが、Teams を使用してチームの機能を管理したい場合は、onmicrosoft.com ドメインを持つ管理者アカウントを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cce70-120">If your organization has Skype for Business Server and you have not configured hybrid connectivity, but you still want to use Teams, to administer Teams functionality, you must use an administrative account that has an .onmicrosoft.com domain.</span></span> 

- <span data-ttu-id="cce70-121">オンプレミスの Skype for Business アカウントを所有している Teams ユーザー (つまり、Move-CsUser を使用してクラウドにまだ移行していないユーザー) は、Skype for Business ユーザーとの相互運用や、外部ユーザーとのフェデレーションを行うことができません。</span><span class="sxs-lookup"><span data-stu-id="cce70-121">Teams users who have a Skype for Business account on-premises (that is, they have not yet been moved to the cloud by using Move-CsUser) cannot interoperate with any Skype for Business users, nor can they federate with external users.</span></span> <span data-ttu-id="cce70-122">この機能は、そのユーザーがクラウドに移行した場合 (アイランド モードか TeamsOnly ユーザーとして) にのみ利用できます。</span><span class="sxs-lookup"><span data-stu-id="cce70-122">This functionality is only available once the users are moved to the cloud (either in Islands mode, or as TeamsOnly users).</span></span> 

- <span data-ttu-id="cce70-123">オンプレミスの Skype for Business アカウントを使用しているユーザーがいる場合は、テナントレベルで teams Sonly モードを割り当てることはできません。</span><span class="sxs-lookup"><span data-stu-id="cce70-123">If you have any users with Skype for Business accounts on-premises, you cannot assign TeamsOnly mode at the tenant level.</span></span> <span data-ttu-id="cce70-124">まず、オンプレミスの Skype for Business アカウントを使用しているすべてのユーザーをクラウドに移行する必要があり `Move-CsUser` ます。その後、ハイブリッドを無効にして [クラウドへの移行を完了](https://docs.microsoft.com/skypeforbusiness/hybrid/cloud-consolidation-disabling-hybrid)します。</span><span class="sxs-lookup"><span data-stu-id="cce70-124">You must first move all  users with on-premises Skype for Business accounts to the cloud using `Move-CsUser` and then [disable hybrid to complete migration to the cloud](https://docs.microsoft.com/skypeforbusiness/hybrid/cloud-consolidation-disabling-hybrid).</span></span>  <span data-ttu-id="cce70-125">`Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams` Office 365 以外の場所を参照する lyncdiscover DNS レコードが検出された場合は、テナントレベルでは動作しません。</span><span class="sxs-lookup"><span data-stu-id="cce70-125">`Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams` will not work at the tenant level if a lyncdiscover DNS record is detected that points to a location other than Office 365.</span></span>

- <span data-ttu-id="cce70-126">ユーザーが適切な Skype for Business 属性を使用して Azure AD に正しく同期されていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cce70-126">You must ensure your users are properly synchronized into Azure AD with the correct Skype for Business attributes.</span></span> <span data-ttu-id="cce70-127">これらの属性すべてには、プレフィックスとして msRTCSIP- が付きます。</span><span class="sxs-lookup"><span data-stu-id="cce70-127">These attributes are all prefixes with “msRTCSIP-”.</span></span> <span data-ttu-id="cce70-128">ユーザーが Azure AD に正しく同期されていない場合、Teams の管理ツールでそのユーザーを管理できなくなります。</span><span class="sxs-lookup"><span data-stu-id="cce70-128">If users are not synchronized properly to Azure AD, the management tools in Teams will not be able to manage these users.</span></span> <span data-ttu-id="cce70-129">(たとえば、これらの属性を正しく同期していない場合は、オンプレミスのユーザーに Teams ポリシーを割り当てることはできません)。詳細については、「 [Teams および Skype For business 用に AZURE AD Connect を構成する](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-azure-ad-connect)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cce70-129">(For example, you won’t be able to assign Teams policies to on-premises users unless you are properly syncing these attributes.) For more information, see [Configure Azure AD Connect for Teams and Skype for Business](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-azure-ad-connect).</span></span>

- <span data-ttu-id="cce70-130">ハイブリッド組織で新しい TeamsOnly ユーザーや Skype for Business Online のユーザーを作成するには、*最初にユーザーを Skype for Business Server オンプレミスで有効にしてから*、その後に、そのユーザーを Move-CsUser を使用してオンプレミスからクラウドに移行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cce70-130">To create a new TeamsOnly or Skype for Business Online user in a hybrid organization, *you must first enable the user in Skype for Business Server on-premises*, and then move the user from on-premises to the cloud using Move-CsUser.</span></span>  <span data-ttu-id="cce70-131">最初にオンプレミスでユーザーを作成することにより、残りのオンプレミスの Skype for Business ユーザーは新しく作成されたユーザーに確実にルーティングできるようになります。</span><span class="sxs-lookup"><span data-stu-id="cce70-131">Creating the user in on-premises first ensures that any other remaining on-premises Skype for Business users will be able route to the newly created user.</span></span> <span data-ttu-id="cce70-132">すべてのユーザーのオンラインへの移行が完了しているなら、最初にオンプレミスでユーザーを有効にする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="cce70-132">Once all users have been moved online, it is no longer necessary to first enable users in on-premises.</span></span>

- <span data-ttu-id="cce70-133">オンプレミスからクラウドにユーザーが移行されると、そのユーザーによって開催される会議は、-MoveToTeams スイッチが指定されているかどうかに基づいて、Skype for Business Online か Teams のいずれかに移行されます。</span><span class="sxs-lookup"><span data-stu-id="cce70-133">When a user is moved from on-premises to the cloud, meetings organized by that user are migrated to either Skype for Business Online or Teams--depending on whether or not the -MoveToTeams switch is specified.</span></span>

- <span data-ttu-id="cce70-134">オンプレミスのユーザーに対して Skype for Business クライアントで通知を表示する場合は、オンプレミスのツールセットで TeamsUpgradePolicy を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cce70-134">If you would like display notifications in the Skype for Business client for on-premises users, you must use TeamsUpgradePolicy in the on-premises toolset.</span></span> <span data-ttu-id="cce70-135">オンプレミスのユーザーに関係があるのは、NotifySfbUsers パラメーターのみです。</span><span class="sxs-lookup"><span data-stu-id="cce70-135">Only the NotifySfbUsers parameter is relevant for on-premises users.</span></span>  <span data-ttu-id="cce70-136">オンプレミスのユーザーは、TeamsUpgradePolicy のオンライン インスタンスから自分のモードを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="cce70-136">On-premises users receive their mode from the online instances of TeamsUpgradePolicy.</span></span> <span data-ttu-id="cce70-137">「[Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)」のメモを参照してください。</span><span class="sxs-lookup"><span data-stu-id="cce70-137">See the notes in [Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps).</span></span> 

>[!NOTE]
> <span data-ttu-id="cce70-138">9月3日以降に作成されたすべての新しいテナントは、組織に Skype for Business Server のオンプレミス展開が含まれていない限り2019、TeamsOnly テナントとして作成されます。</span><span class="sxs-lookup"><span data-stu-id="cce70-138">Any new tenants created after Sept 3, 2019 are created as TeamsOnly tenants unless the organization already has an on-premises deployment of Skype for Business Server.</span></span> <span data-ttu-id="cce70-139">Microsoft は DNS レコードを使って、オンプレミスの Skype for Business Server 組織を特定します。</span><span class="sxs-lookup"><span data-stu-id="cce70-139">Microsoft uses DNS records to identify on-premises Skype for Business Server organizations.</span></span> <span data-ttu-id="cce70-140">組織にパブリック DNS エントリのないオンプレミスの Skype for Business サーバーがある場合は、Microsoft サポートに連絡して、新しいテナントをダウングレードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="cce70-140">If your organization has on-premises Skype for Business Server with no public DNS entries, you will need to call Microsoft Support to have your new tenant downgraded.</span></span> 













## <a name="related-links"></a><span data-ttu-id="cce70-141">関連リンク</span><span class="sxs-lookup"><span data-stu-id="cce70-141">Related links</span></span>

[<span data-ttu-id="cce70-142">Teams を Skype for Business と一緒に使用する組織向けの移行と相互運用に関するガイダンス</span><span class="sxs-lookup"><span data-stu-id="cce70-142">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](migration-interop-guidance-for-teams-with-skype.md) 

[<span data-ttu-id="cce70-143">Skype for Business Server と Microsoft 365 または Office 365 間のハイブリッド接続を構成する</span><span class="sxs-lookup"><span data-stu-id="cce70-143">Configure hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[<span data-ttu-id="cce70-144">オンプレミスとクラウドの間でユーザーを移動する</span><span class="sxs-lookup"><span data-stu-id="cce70-144">Move users between on-premises and cloud</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[<span data-ttu-id="cce70-145">共存およびアップグレードを設定する</span><span class="sxs-lookup"><span data-stu-id="cce70-145">Setting your coexistence and upgrade settings</span></span>](setting-your-coexistence-and-upgrade-settings.md)

[<span data-ttu-id="cce70-146">Grant-CsTeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="cce70-146">Grant-CsTeamsUpgradePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[<span data-ttu-id="cce70-147">会議移行サービス (MMS) を使用する</span><span class="sxs-lookup"><span data-stu-id="cce70-147">Using the Meeting Migration Service (MMS)</span></span>](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

