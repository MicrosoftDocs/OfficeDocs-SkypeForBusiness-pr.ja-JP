---
title: Teams Only モードの考慮事項
author: dearbeen
ms.author: dearbeen
manager: serdars
ms.date: 01/09/2019
ms.topic: conceptual
ms.service: msteams
ms.reviewer: dearbeen
description: チームのみのモードへのアップグレードの準備します。
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
f1keywords: ms.teamsadmincenter.orgwidesettings.teamsupgrade.upgradetoteams
MS.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: dd0bf20219b8d213c354f5fc239ae3924a0d21c0
ms.sourcegitcommit: a589b86520028d8751653386265f6ce1e066818b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/16/2019
ms.locfileid: "30649389"
---
# <a name="teams-only-mode-considerations"></a><span data-ttu-id="52152-103">Teams Only モードの考慮事項</span><span class="sxs-lookup"><span data-stu-id="52152-103">Teams Only mode considerations</span></span>

<span data-ttu-id="52152-104">管理者は、Office 365 テナントにする場合は、マイクロソフトのチームの管理センターでチームのみのモードにアップグレードするためのオプションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="52152-104">If you are an administrator on your Office 365 tenant, you will now see the option to upgrade to Teams Only mode in the Microsoft Teams admin center.</span></span> <span data-ttu-id="52152-105">この機能により、個々 のユーザー、または別の方法としては、全体のテナントをアップグレードできます。</span><span class="sxs-lookup"><span data-stu-id="52152-105">With this functionality you can upgrade either individual users, or alternatively, the entire tenant.</span></span>  

<span data-ttu-id="52152-106">チームのみのモードにアップグレードするとはユーザーがマイクロソフトのチーム、1 つのクライアント エクスペリエンスを使用して、Office 365 でチームワークのハブのメリットを十分にできます。</span><span class="sxs-lookup"><span data-stu-id="52152-106">Upgrading to Teams Only mode offers users the full benefits of Microsoft Teams, the hub for teamwork in Office 365, via a single client experience.</span></span> <span data-ttu-id="52152-107">さらに、チームのみのモードでのユーザーかどうか、送信者を使用して Skype のビジネスやチームに関係なく、チームのすべての呼び出しとのチャットが表示される、相互運用性とフェデレーションのサポートを利用します。</span><span class="sxs-lookup"><span data-stu-id="52152-107">Additionally, users in Teams Only mode will receive all calls and chats in Teams, regardless of whether the sender is using Skype for Business or Teams, and benefit from interop and federation support.</span></span>

<span data-ttu-id="52152-108">何千ものお客様がマイクロソフトのチームに正しくアップグレードされました、中には、組織のアップグレード タイムラインとユーザー エクスペリエンスに影響を及ぼす可能性の考慮事項があります。</span><span class="sxs-lookup"><span data-stu-id="52152-108">While thousands of customers have successfully upgraded to Microsoft Teams, there are considerations that may influence your organization’s upgrade timeline and user experience along the way.</span></span> <span data-ttu-id="52152-109">具体的には、アップグレードすることも、必ずしもこの変更の準備ができました。</span><span class="sxs-lookup"><span data-stu-id="52152-109">In particular, having the option to upgrade doesn’t necessarily mean your organization is ready for this change.</span></span> <span data-ttu-id="52152-110">最高のユーザー エクスペリエンスを得るために、Teams が自分たちの共同作業や通信の要件に適合してることを確認し、確実にお使いのネットワークが Teams をサポートする状態を整えて、ユーザーの準備状態計画を実施してから Teams へのユーザーのアップグレードを実行してください。</span><span class="sxs-lookup"><span data-stu-id="52152-110">For the best user experience, confirm that Teams meets your collaboration and communication requirements, make sure that your network is ready to support Teams, and implement your user readiness plan before upgrading users to Teams.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="52152-111">アップグレード計画を開始するだけで、必ず完全アップグレード ガイダンスとリソースの計画を確認します。</span><span class="sxs-lookup"><span data-stu-id="52152-111">If you are just starting your upgrade planning, be sure to review our full upgrade guidance and planning resources.</span></span> <span data-ttu-id="52152-112">[ここから開始](upgrade-introduction.md)します。</span><span class="sxs-lookup"><span data-stu-id="52152-112">[Start here](upgrade-introduction.md).</span></span> 

<span data-ttu-id="52152-113">**共存に関する考慮事項**: 組織が既にを使用してオンライン ビジネス用の Skype または Skype ビジネス サーバーは各自の環境のニーズに合ったペースでにチームを導入することができます。</span><span class="sxs-lookup"><span data-stu-id="52152-113">**Coexistence considerations**: Organizations already using Skype for Business Online and/or Skype for Business Server can introduce Teams into their environment at a pace that meets their needs.</span></span> <span data-ttu-id="52152-114">組織が段階的ロールアウト チーム目的のユーザーに、必要に応じて、チームを使用するユーザーは、Skype のビジネス、およびその逆を使用するユーザーと通信できます。</span><span class="sxs-lookup"><span data-stu-id="52152-114">Organizations can incrementally roll out Teams to a desired set of users as needed, and users who use Teams can communicate with users who use Skype for Business and vice versa.</span></span> <span data-ttu-id="52152-115">この経験、エンド ユーザー クライアントのエクスペリエンスを定義するには、管理者の使用の共存モードを管理するために着信のルーティング動作はチャットし、を呼び出すと、チームやビジネス用の Skype の新しい会議をスケジュールするかどうかと。</span><span class="sxs-lookup"><span data-stu-id="52152-115">To manage this experience, administrators use coexistence modes, which define the end user client experience, the routing behavior of incoming chats and calls, as well as whether new meetings are scheduled in Teams or Skype for Business.</span></span> <span data-ttu-id="52152-116">ユーザーがフェデレーションを行う他の組織内のユーザーと**チームのみ**に、ユーザーがアップグレードした場合はただし、両方のユーザーがチームを使用すると、最適なエクスペリエンスが提供されます。</span><span class="sxs-lookup"><span data-stu-id="52152-116">Users can federate with users in other organizations if the user is upgraded to **Teams Only**; however, the best experience is provided when both users use Teams.</span></span> <span data-ttu-id="52152-117">チームのみにアップグレードしたユーザーがビジネス ・ ミーティングの Skype に参加できます。</span><span class="sxs-lookup"><span data-stu-id="52152-117">Users who are upgraded to Teams Only can still join Skype for Business meetings.</span></span> 

> [!NOTE]
> <span data-ttu-id="52152-118">チームのみにアップグレードしたユーザーは、消費者の Skype を使用しているユーザーと通信できません。</span><span class="sxs-lookup"><span data-stu-id="52152-118">Users who are upgraded to Teams Only cannot communicate with users who are using Skype for Consumer.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="52152-119">共存に関する詳細な情報[を理解するマイクロソフトのチームと Skype ビジネスの共存と相互運用性](teams-and-skypeforbusiness-coexistence-and-interoperability.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="52152-119">For more detailed information about coexistence please refer to [Understand Microsoft Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md).</span></span> 

<span data-ttu-id="52152-120">**テナント全体に関する考慮事項**: 以下の環境でチームを有効にすることに取り組んでいますただし、ここでは、管理者、組織内のユーザーべきではないアップグレードした場合、テナントのビジネス用の Skype は以下の環境のいずれかでホストされている場合にします。</span><span class="sxs-lookup"><span data-stu-id="52152-120">**Tenant-wide considerations**: We are working on enabling Teams in the following environments; however, for now, administrators shouldn't upgrade any users in their organization if their Skype for Business tenant is hosted in one of the following environments:</span></span>

 - <span data-ttu-id="52152-121">政府コミュニティ クラウドの高</span><span class="sxs-lookup"><span data-stu-id="52152-121">Government Community Cloud High</span></span>
 - <span data-ttu-id="52152-122">政府コミュニティ クラウド DoD</span><span class="sxs-lookup"><span data-stu-id="52152-122">Government Community Cloud DoD</span></span>
 - <span data-ttu-id="52152-123">Office 365 の 21Vianet によって運営されて</span><span class="sxs-lookup"><span data-stu-id="52152-123">Office 365 operated by 21Vianet</span></span>
 - <span data-ttu-id="52152-124">Office 365 のドイツ</span><span class="sxs-lookup"><span data-stu-id="52152-124">Office 365 Germany</span></span>
 - <span data-ttu-id="52152-125">テナントのビジネス用の Skype は、(韓国)**と**組織が必要です (韓国) に格納するデータをチームでホストされています。</span><span class="sxs-lookup"><span data-stu-id="52152-125">Skype for Business tenant is hosted in South Korea **and** the organization requires Teams data to be stored in South Korea.</span></span> <span data-ttu-id="52152-126">現在、Skype でチームにアップグレードされるように (韓国) に格納されているビジネス データの場合、組織は、チームのデータ (韓国) データ センターの領域ではなく、アジアのデータ センター領域内に格納されています。</span><span class="sxs-lookup"><span data-stu-id="52152-126">Currently, organizations with Skype for Business data stored in South Korea that upgrade to Teams will have their Teams data stored in the Asia datacenter region, not in the South Korea datacenter region.</span></span>

<span data-ttu-id="52152-127">**ユーザー固有の考慮事項**: 一部のユーザー シナリオはまだ発展段階、および管理者は、組織内の他のユーザーをアップグレードするときに一時的に特定のユーザーのアップグレードを延期することができます。</span><span class="sxs-lookup"><span data-stu-id="52152-127">**User-specific considerations**: Some user scenarios are still evolving, and administrators may decide to temporarily postpone the upgrade of certain users while upgrading other users in the organization.</span></span> <span data-ttu-id="52152-128">これらのシナリオに対処することに取り組んでいますお知らせの[Office 365 のロードマップ](https://www.microsoft.com/en-us/microsoft-365/roadmap)のサイトを監視してください。</span><span class="sxs-lookup"><span data-stu-id="52152-128">We are working on addressing these scenarios; please monitor the [Office 365 Roadmap](https://www.microsoft.com/en-us/microsoft-365/roadmap) site for announcements.</span></span>

| <span data-ttu-id="52152-129">シナリオ</span><span class="sxs-lookup"><span data-stu-id="52152-129">Scenario</span></span> | <span data-ttu-id="52152-130">メモ</span><span class="sxs-lookup"><span data-stu-id="52152-130">Notes</span></span> |
|----------|-------|
|<span data-ttu-id="52152-131">ユーザーの主な作業のデバイスは、Mac、およびユーザーが Outlook の仕事仲間の可用性を確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="52152-131">User’s primary work device is a Mac, and user needs to see colleagues' availability in Outlook.</span></span> | <span data-ttu-id="52152-132">Outlook プレゼンスをチームでサポートされていませんまだ完全に Mac デバイスの。</span><span class="sxs-lookup"><span data-stu-id="52152-132">Outlook presence in Teams is not yet fully supported for Mac devices.</span></span> |
| <span data-ttu-id="52152-133">ユーザーは、顧客や別の地域での外部パートナーとのミーティングを実施して定期的にします。</span><span class="sxs-lookup"><span data-stu-id="52152-133">User is regularly conducting meetings with customers or external partners in different international regions.</span></span> | <span data-ttu-id="52152-134">IM を別の地理的な場所でのテナントが存在する外部の出席者が表示されていない**フェデレーション**会議中にチャットできます。</span><span class="sxs-lookup"><span data-stu-id="52152-134">External attendees whose tenant resides in a different geo-location don’t see IM chat while in a **federated** meeting.</span></span> <span data-ttu-id="52152-135">参加者は、匿名ユーザーとして会議にも参加できます。</span><span class="sxs-lookup"><span data-stu-id="52152-135">Participants can still join the meeting as anonymous users.</span></span> |
| <span data-ttu-id="52152-136">ユーザーは会議のブロードキャストのビジネスの Skype を実施します。</span><span class="sxs-lookup"><span data-stu-id="52152-136">User is conducting Skype for Business Broadcast meetings.</span></span> |  <span data-ttu-id="52152-137">チームのライブ (Skype のブロードキャストの交換) イベントは、既にパブリック プレビューが、このユーザーは、Skype のビジネスにまでチームのライブ イベントの全般的な可用性を維持する必要があります。</span><span class="sxs-lookup"><span data-stu-id="52152-137">While Teams live events (replacing Skype Broadcast) is already in public preview, this user may need to stay on Skype for Business until general availability of Teams live events.</span></span>
| <span data-ttu-id="52152-138">ユーザーのプライマリ ・ デバイスは、VDI ベースです。</span><span class="sxs-lookup"><span data-stu-id="52152-138">User’s primary device is VDI-based.</span></span> | |
|||

> [!IMPORTANT]
> <span data-ttu-id="52152-139">**保存**: チームへの移行は、複数の技術的な移行します。</span><span class="sxs-lookup"><span data-stu-id="52152-139">**Remember**: The move to Teams is more than a technical migration.</span></span> <span data-ttu-id="52152-140">アップグレードの成功は、新たな技術とエンド ・ ユーザーの準備の両方を評価します。</span><span class="sxs-lookup"><span data-stu-id="52152-140">A successful upgrade assesses both technical readiness and end-user readiness.</span></span> <span data-ttu-id="52152-141">チームで[ガイダンスのアップグレード](upgrade-framework.md)を実装するチームへのアップグレードの計画の詳細については、ビジネス用の Skype を確認します。</span><span class="sxs-lookup"><span data-stu-id="52152-141">Review our Skype for Business to Teams [upgrade guidance](upgrade-framework.md) for more information on planning an implementing your upgrade to Teams.</span></span>  
