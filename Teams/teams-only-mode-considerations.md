---
title: Teams Only モードの考慮事項
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 01/09/2019
ms.topic: conceptual
ms.service: msteams
ms.reviewer: dearbeen
description: Microsoft Teams 専用モードへのアップグレードを準備する
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
f1keywords: ms.teamsadmincenter.orgwidesettings.teamsupgrade.upgradetoteams
MS.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0c33f1cc4b508149ae42b79e956e1f08d44579bc
ms.sourcegitcommit: 349df7248c168e629bc1bb633187e39a37b17ba5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/23/2019
ms.locfileid: "34422004"
---
# <a name="teams-only-mode-considerations"></a><span data-ttu-id="052fb-103">Teams Only モードの考慮事項</span><span class="sxs-lookup"><span data-stu-id="052fb-103">Teams Only mode considerations</span></span>

<span data-ttu-id="052fb-104">Office 365 テナントの管理者である場合は、Microsoft Teams 管理センターで [チームのみ] モードにアップグレードするオプションが表示されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="052fb-104">If you are an administrator on your Office 365 tenant, you will now see the option to upgrade to Teams Only mode in the Microsoft Teams admin center.</span></span> <span data-ttu-id="052fb-105">この機能を使用すると、個々のユーザーまたはテナント全体のどちらかをアップグレードできます。</span><span class="sxs-lookup"><span data-stu-id="052fb-105">With this functionality you can upgrade either individual users, or alternatively, the entire tenant.</span></span>  

<span data-ttu-id="052fb-106">Teams 専用モードにアップグレードすると、ユーザーは1つのクライアントエクスペリエンスで、Office 365 のチームワークのハブである Microsoft Teams のすべてのメリットを享受できます。</span><span class="sxs-lookup"><span data-stu-id="052fb-106">Upgrading to Teams Only mode offers users the full benefits of Microsoft Teams, the hub for teamwork in Office 365, via a single client experience.</span></span> <span data-ttu-id="052fb-107">さらに、チーム専用モードのユーザーは、送信者が Skype for Business または Teams を使用しているかどうかにかかわらず、すべての通話とチャットを受け取り、相互運用およびフェデレーションサポートによる恩恵を受けることができます。</span><span class="sxs-lookup"><span data-stu-id="052fb-107">Additionally, users in Teams Only mode will receive all calls and chats in Teams, regardless of whether the sender is using Skype for Business or Teams, and benefit from interop and federation support.</span></span>

<span data-ttu-id="052fb-108">多くのユーザーが Microsoft Teams にアップグレードしましたが、組織のアップグレードタイムラインとユーザーエクスペリエンスに影響を与える可能性があるという考慮事項があります。</span><span class="sxs-lookup"><span data-stu-id="052fb-108">While thousands of customers have successfully upgraded to Microsoft Teams, there are considerations that may influence your organization’s upgrade timeline and user experience along the way.</span></span> <span data-ttu-id="052fb-109">特に、アップグレードのオプションを使用しても、組織がこの変更に対応できるというわけではありません。</span><span class="sxs-lookup"><span data-stu-id="052fb-109">In particular, having the option to upgrade doesn’t necessarily mean your organization is ready for this change.</span></span> <span data-ttu-id="052fb-110">最高のユーザー エクスペリエンスを得るために、Teams が自分たちの共同作業や通信の要件に適合してることを確認し、確実にお使いのネットワークが Teams をサポートする状態を整えて、ユーザーの準備状態計画を実施してから Teams へのユーザーのアップグレードを実行してください。</span><span class="sxs-lookup"><span data-stu-id="052fb-110">For the best user experience, confirm that Teams meets your collaboration and communication requirements, make sure that your network is ready to support Teams, and implement your user readiness plan before upgrading users to Teams.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="052fb-111">アップグレード計画を開始するだけの場合は、完全なアップグレードガイダンスと計画リソースを確認してください。</span><span class="sxs-lookup"><span data-stu-id="052fb-111">If you are just starting your upgrade planning, be sure to review our full upgrade guidance and planning resources.</span></span> <span data-ttu-id="052fb-112">[ここから始め](upgrade-start-here.md)ます。</span><span class="sxs-lookup"><span data-stu-id="052fb-112">[Start here](upgrade-start-here.md).</span></span> 

<span data-ttu-id="052fb-113">**共存の考慮事項**: Skype For business Online または Skype For business Server を既に使用している組織では、ニーズに合ったペースでチームを環境に導入することができます。</span><span class="sxs-lookup"><span data-stu-id="052fb-113">**Coexistence considerations**: Organizations already using Skype for Business Online and/or Skype for Business Server can introduce Teams into their environment at a pace that meets their needs.</span></span> <span data-ttu-id="052fb-114">組織では、必要に応じて、チームを目的に応じたユーザーのセットに段階的にロールアウトできます。また、Teams を使用するユーザーは、Skype for Business を使用するユーザーと通信することができます。</span><span class="sxs-lookup"><span data-stu-id="052fb-114">Organizations can incrementally roll out Teams to a desired set of users as needed, and users who use Teams can communicate with users who use Skype for Business and vice versa.</span></span> <span data-ttu-id="052fb-115">このエクスペリエンスを管理するために、管理者は、エンドユーザーのクライアントエクスペリエンス、着信チャットと通話のルーティング動作、チームまたは Skype for Business で新しい会議をスケジュールするかどうかを定義する、共存モードを使用します。</span><span class="sxs-lookup"><span data-stu-id="052fb-115">To manage this experience, administrators use coexistence modes, which define the end user client experience, the routing behavior of incoming chats and calls, as well as whether new meetings are scheduled in Teams or Skype for Business.</span></span> <span data-ttu-id="052fb-116">ユーザーが**Teams のみ**にアップグレードされた場合、ユーザーは他の組織のユーザーとフェデレーションを行うことができます。ただし、両方のユーザーが Teams を使用する場合に最適なエクスペリエンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="052fb-116">Users can federate with users in other organizations if the user is upgraded to **Teams Only**; however, the best experience is provided when both users use Teams.</span></span> <span data-ttu-id="052fb-117">Teams にアップグレードされたユーザーのみが、引き続き Skype for Business 会議に参加できます。</span><span class="sxs-lookup"><span data-stu-id="052fb-117">Users who are upgraded to Teams Only can still join Skype for Business meetings.</span></span> 

> [!NOTE]
> <span data-ttu-id="052fb-118">Teams にアップグレードされたユーザーのみが、Skype for Consumer を使っているユーザーと通信することはできません。</span><span class="sxs-lookup"><span data-stu-id="052fb-118">Users who are upgraded to Teams Only cannot communicate with users who are using Skype for Consumer.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="052fb-119">共存の詳細については、「 [Microsoft Teams と Skype For business の共存と相互運用性](teams-and-skypeforbusiness-coexistence-and-interoperability.md)について」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="052fb-119">For more detailed information about coexistence please refer to [Understand Microsoft Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md).</span></span> 

<span data-ttu-id="052fb-120">**テナント全体の考慮事項**: 次の環境で Teams を有効にするための作業を進めています。ただし、現在のところ、Skype for Business テナントが次のいずれかの環境でホストされている場合、管理者は組織内のユーザーをアップグレードすることはできません。</span><span class="sxs-lookup"><span data-stu-id="052fb-120">**Tenant-wide considerations**: We are working on enabling Teams in the following environments; however, for now, administrators shouldn't upgrade any users in their organization if their Skype for Business tenant is hosted in one of the following environments:</span></span>

 - <span data-ttu-id="052fb-121">行政機関向けコミュニティクラウド高</span><span class="sxs-lookup"><span data-stu-id="052fb-121">Government Community Cloud High</span></span>
 - <span data-ttu-id="052fb-122">行政機関向けコミュニティクラウド DoD</span><span class="sxs-lookup"><span data-stu-id="052fb-122">Government Community Cloud DoD</span></span>
 - <span data-ttu-id="052fb-123">21Vianet が運営する Office 365</span><span class="sxs-lookup"><span data-stu-id="052fb-123">Office 365 operated by 21Vianet</span></span>
 - <span data-ttu-id="052fb-124">Office 365 ドイツ</span><span class="sxs-lookup"><span data-stu-id="052fb-124">Office 365 Germany</span></span>
 - <span data-ttu-id="052fb-125">Skype for Business テナントは韓国でホストされています。**また**、組織は、韓国で Teams のデータを保存する必要があります。</span><span class="sxs-lookup"><span data-stu-id="052fb-125">Skype for Business tenant is hosted in South Korea **and** the organization requires Teams data to be stored in South Korea.</span></span> <span data-ttu-id="052fb-126">現在、Skype for Business データを使用している組織では、チームにアップグレードした韓国のデータは、韓国のデータセンターの地域ではなく、アジアのデータセンターに保存されています。</span><span class="sxs-lookup"><span data-stu-id="052fb-126">Currently, organizations with Skype for Business data stored in South Korea that upgrade to Teams will have their Teams data stored in the Asia datacenter region, not in the South Korea datacenter region.</span></span>

<span data-ttu-id="052fb-127">**ユーザー固有の考慮事項**: 一部のユーザーシナリオはまだ進化し続けており、管理者が組織内の他のユーザーのアップグレード中に、特定のユーザーのアップグレードを一時的に延期することを決定する場合があります。</span><span class="sxs-lookup"><span data-stu-id="052fb-127">**User-specific considerations**: Some user scenarios are still evolving, and administrators may decide to temporarily postpone the upgrade of certain users while upgrading other users in the organization.</span></span> <span data-ttu-id="052fb-128">ここでは、これらのシナリオの解決に取り組んでいます。[Office 365 ロードマップ](https://www.microsoft.com/en-us/microsoft-365/roadmap)サイトでお知らせを監視してください。</span><span class="sxs-lookup"><span data-stu-id="052fb-128">We are working on addressing these scenarios; please monitor the [Office 365 Roadmap](https://www.microsoft.com/en-us/microsoft-365/roadmap) site for announcements.</span></span>

| <span data-ttu-id="052fb-129">シナリオ</span><span class="sxs-lookup"><span data-stu-id="052fb-129">Scenario</span></span> | <span data-ttu-id="052fb-130">ノート</span><span class="sxs-lookup"><span data-stu-id="052fb-130">Notes</span></span> |
|----------|-------|
|<span data-ttu-id="052fb-131">ユーザーのプライマリ作業デバイスは Mac であり、ユーザーは Outlook で仕事仲間の空き時間情報を表示する必要があります。</span><span class="sxs-lookup"><span data-stu-id="052fb-131">User’s primary work device is a Mac, and user needs to see colleagues' availability in Outlook.</span></span> | <span data-ttu-id="052fb-132">Teams での Outlook のプレゼンスは、Mac デバイスではまだ完全にサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="052fb-132">Outlook presence in Teams is not yet fully supported for Mac devices.</span></span> |
| <span data-ttu-id="052fb-133">ユーザーは、さまざまなインターナショナル地域で顧客や外部パートナーとの会議を定期的に開催しています。</span><span class="sxs-lookup"><span data-stu-id="052fb-133">User is regularly conducting meetings with customers or external partners in different international regions.</span></span> | <span data-ttu-id="052fb-134">テナントが別の地理的な場所に存在する外部の出席者は、**フェデレーション**された会議で IM チャットが表示されません。</span><span class="sxs-lookup"><span data-stu-id="052fb-134">External attendees whose tenant resides in a different geo-location don’t see IM chat while in a **federated** meeting.</span></span> <span data-ttu-id="052fb-135">参加者は、引き続き匿名ユーザーとして会議に参加できます。</span><span class="sxs-lookup"><span data-stu-id="052fb-135">Participants can still join the meeting as anonymous users.</span></span> |
| <span data-ttu-id="052fb-136">ユーザーが Skype for Business ブロードキャスト会議を実施しています。</span><span class="sxs-lookup"><span data-stu-id="052fb-136">User is conducting Skype for Business Broadcast meetings.</span></span> |  <span data-ttu-id="052fb-137">Teams のライブイベント (Skype ブロードキャストの置き換え) は既にパブリックプレビューになっていますが、このユーザーは Teams のライブイベントの一般的な利用を許可するまで、Skype for Business を使い続ける必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="052fb-137">While Teams live events (replacing Skype Broadcast) is already in public preview, this user may need to stay on Skype for Business until general availability of Teams live events.</span></span>
| <span data-ttu-id="052fb-138">ユーザーのプライマリデバイスは VDI ベースです。</span><span class="sxs-lookup"><span data-stu-id="052fb-138">User’s primary device is VDI-based.</span></span> | |
|||

> [!IMPORTANT]
> <span data-ttu-id="052fb-139">Teams への移行は、技術的な移行よりも多くのことを**覚えておい**てください。</span><span class="sxs-lookup"><span data-stu-id="052fb-139">**Remember**: The move to Teams is more than a technical migration.</span></span> <span data-ttu-id="052fb-140">アップグレードが成功すると、技術的な準備とエンドユーザーの準備の両方が評価されます。</span><span class="sxs-lookup"><span data-stu-id="052fb-140">A successful upgrade assesses both technical readiness and end-user readiness.</span></span> <span data-ttu-id="052fb-141">Teams へのアップグレードの実装の計画の詳細については、「Skype for Business と Teams の[アップグレードのガイダンス](upgrade-framework.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="052fb-141">Review our Skype for Business to Teams [upgrade guidance](upgrade-framework.md) for more information on planning an implementing your upgrade to Teams.</span></span>  
