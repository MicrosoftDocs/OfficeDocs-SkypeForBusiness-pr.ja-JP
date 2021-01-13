---
title: Teams Only モードの考慮事項
author: cichur
ms.author: v-cichur
manager: serdars
ms.date: 01/09/2019
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.reviewer: landerl
description: 管理者は、Microsoft Teams 管理センターで Microsoft Teams のみモードにアップグレードする準備をする方法について説明します。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- ms.teamsadmincenter.orgwidesettings.teamsupgrade.upgradetoteams
- seo-marvel-apr2020
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 86c27d8619a436c6a77ab435cfcb2cc4133befe0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802377"
---
# <a name="teams-only-mode-considerations"></a><span data-ttu-id="1567d-103">Teams Only モードの考慮事項</span><span class="sxs-lookup"><span data-stu-id="1567d-103">Teams Only mode considerations</span></span>

<span data-ttu-id="1567d-104">Microsoft 365 または Office 365 組織の管理者の場合、Microsoft Teams 管理センターで Teams のみモードにアップグレードするオプションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1567d-104">If you are an administrator in your Microsoft 365 or Office 365 organization, you will now see the option to upgrade to Teams Only mode in the Microsoft Teams admin center.</span></span> <span data-ttu-id="1567d-105">この機能を使用すると、個々のユーザー、またはテナント全体をアップグレードできます。</span><span class="sxs-lookup"><span data-stu-id="1567d-105">With this functionality you can upgrade either individual users, or alternatively, the entire tenant.</span></span>  

<span data-ttu-id="1567d-106">Teams のみモードにアップグレードすると、単一のクライアント エクスペリエンスを介して Microsoft 365 または Office 365 のチームワークのハブである Microsoft Teams の完全な利点がユーザーに提供されます。</span><span class="sxs-lookup"><span data-stu-id="1567d-106">Upgrading to Teams Only mode offers users the full benefits of Microsoft Teams, the hub for teamwork in Microsoft 365 or Office 365, via a single client experience.</span></span> <span data-ttu-id="1567d-107">さらに、Teams Only モードのユーザーは、送信者が Skype for Business または Teams を使用しているかどうかに関係なく、Teams のすべての通話とチャットを受信し、相互運用とフェデレーションのサポートを利用できます。</span><span class="sxs-lookup"><span data-stu-id="1567d-107">Additionally, users in Teams Only mode will receive all calls and chats in Teams, regardless of whether the sender is using Skype for Business or Teams, and benefit from interop and federation support.</span></span>

<span data-ttu-id="1567d-108">何千ものユーザーが Microsoft Teams へのアップグレードに成功している間、組織のアップグレード タイムラインとユーザー エクスペリエンスに影響を与える可能性がある考慮事項があります。</span><span class="sxs-lookup"><span data-stu-id="1567d-108">While thousands of customers have successfully upgraded to Microsoft Teams, there are considerations that may influence your organization's upgrade timeline and user experience along the way.</span></span> <span data-ttu-id="1567d-109">特に、アップグレードするオプションを選択しても、必ずしも組織がこの変更の準備ができているとは限りません。</span><span class="sxs-lookup"><span data-stu-id="1567d-109">In particular, having the option to upgrade doesn't necessarily mean your organization is ready for this change.</span></span> <span data-ttu-id="1567d-110">最高のユーザー エクスペリエンスを得るために、Teams が自分たちの共同作業や通信の要件に適合してることを確認し、確実にお使いのネットワークが Teams をサポートする状態を整えて、ユーザーの準備状態計画を実施してから Teams へのユーザーのアップグレードを実行してください。</span><span class="sxs-lookup"><span data-stu-id="1567d-110">For the best user experience, confirm that Teams meets your collaboration and communication requirements, make sure that your network is ready to support Teams, and implement your user readiness plan before upgrading users to Teams.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="1567d-111">アップグレード計画を開始する場合は、Microsoft Teams アップグレード ガイドの使用を開始する [方法を確認](upgrade-start-here.md) してください。</span><span class="sxs-lookup"><span data-stu-id="1567d-111">If you are just starting your upgrade planning, be sure to review our [Getting started with your Microsoft Teams upgrade](upgrade-start-here.md) guide.</span></span> 

<span data-ttu-id="1567d-112">**共存に関** する考慮事項: Skype for Business Online または Skype for Business Server を既に使用している組織は、自分のニーズに合ったペースで Teams を環境に導入できます。</span><span class="sxs-lookup"><span data-stu-id="1567d-112">**Coexistence considerations**: Organizations already using Skype for Business Online and/or Skype for Business Server can introduce Teams into their environment at a pace that meets their needs.</span></span> <span data-ttu-id="1567d-113">組織は必要に応じて、Teams を目的のユーザー セットに段階的に展開でき、Teams を使用するユーザーは Skype for Business を使用するユーザーと通信でき、その逆も可能です。</span><span class="sxs-lookup"><span data-stu-id="1567d-113">Organizations can incrementally roll out Teams to a desired set of users as needed, and users who use Teams can communicate with users who use Skype for Business and vice versa.</span></span> <span data-ttu-id="1567d-114">このエクスペリエンスを管理するために、管理者は共存モードを使用します。このモードでは、エンド ユーザー のクライアント エクスペリエンス、着信チャットと通話のルーティング動作、および新しい会議が Teams または Skype for Business でスケジュールされるかどうかが定義されます。</span><span class="sxs-lookup"><span data-stu-id="1567d-114">To manage this experience, administrators use coexistence modes, which define the end user client experience, the routing behavior of incoming chats and calls, as well as whether new meetings are scheduled in Teams or Skype for Business.</span></span> <span data-ttu-id="1567d-115">ユーザーが Teams にのみアップグレードされた場合、ユーザーは他の組織のユーザーと **フェデレーションできます**。ただし、両方のユーザーが Teams を使用する場合に最適なエクスペリエンスが提供されます。</span><span class="sxs-lookup"><span data-stu-id="1567d-115">Users can federate with users in other organizations if the user is upgraded to **Teams Only**; however, the best experience is provided when both users use Teams.</span></span> <span data-ttu-id="1567d-116">Teams にのみアップグレードされたユーザーは、引き続き Skype for Business 会議に参加できます。</span><span class="sxs-lookup"><span data-stu-id="1567d-116">Users who are upgraded to Teams Only can still join Skype for Business meetings.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="1567d-117">共存の詳細については [、「Microsoft Teams](teams-and-skypeforbusiness-coexistence-and-interoperability.md)と Skype for Business の共存と相互運用性について」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1567d-117">For more detailed information about coexistence, please refer to [Understand Microsoft Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md).</span></span> <span data-ttu-id="1567d-118">Teams と Skype (コンシューマー) の詳細については、Teams と Skype の相互運用 [性を参照してください](teams-skype-interop.md)。</span><span class="sxs-lookup"><span data-stu-id="1567d-118">For more information about Teams and Skype (Consumer), see [Teams and Skype interoperability](teams-skype-interop.md).</span></span>

<span data-ttu-id="1567d-119">**テナント全体の考慮事項**: 次の環境で Teams を有効にするための取り組みです。ただし、現在のところ、Skype for Business テナントが次のいずれかの環境でホストされている場合、管理者は組織内のユーザーをアップグレードしないでください。</span><span class="sxs-lookup"><span data-stu-id="1567d-119">**Tenant-wide considerations**: We are working on enabling Teams in the following environments; however, for now, administrators shouldn't upgrade any users in their organization if their Skype for Business tenant is hosted in one of the following environments:</span></span>

 - <span data-ttu-id="1567d-120">Office 365 (21Vianet が運営)</span><span class="sxs-lookup"><span data-stu-id="1567d-120">Office 365 operated by 21Vianet</span></span>
 - <span data-ttu-id="1567d-121">Office 365 Germany</span><span class="sxs-lookup"><span data-stu-id="1567d-121">Office 365 Germany</span></span>
 - <span data-ttu-id="1567d-122">Skype for Business テナントは韓国で **ホストされ、** 組織では Teams データを韓国に保存する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1567d-122">Skype for Business tenant is hosted in South Korea **and** the organization requires Teams data to be stored in South Korea.</span></span> <span data-ttu-id="1567d-123">現在、Teams にアップグレードする Skype for Business データが韓国に保存されている組織は、Teams データを韓国のデータセンター領域ではなく、アジア データセンター地域に保存します。</span><span class="sxs-lookup"><span data-stu-id="1567d-123">Currently, organizations with Skype for Business data stored in South Korea that upgrade to Teams will have their Teams data stored in the Asia datacenter region, not in the South Korea datacenter region.</span></span>

<span data-ttu-id="1567d-124">**ユーザー固有の** 考慮事項: 一部のユーザー シナリオは引き続き進化しており、管理者は組織内の他のユーザーをアップグレードする際に、特定のユーザーのアップグレードを一時的に延期する場合があります。</span><span class="sxs-lookup"><span data-stu-id="1567d-124">**User-specific considerations**: Some user scenarios are still evolving, and administrators may decide to temporarily postpone the upgrade of certain users while upgrading other users in the organization.</span></span> <span data-ttu-id="1567d-125">特に、プライマリ デバイスが VDI ベースのユーザー向けシナリオの対応に引き続き取り組み中です。</span><span class="sxs-lookup"><span data-stu-id="1567d-125">In particular, we are still working on addressing scenarios for users whose primary device is VDI-based.</span></span> <span data-ttu-id="1567d-126">お知らせ [については、Microsoft 365 ロードマップ](https://www.microsoft.com/microsoft-365/roadmap) サイトを監視してください。</span><span class="sxs-lookup"><span data-stu-id="1567d-126">Please monitor the [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap) site for announcements.</span></span>

> [!NOTE]
> <span data-ttu-id="1567d-127">Teams のみモードに移行する前に、Teams をサポートしないデバイスを交換または更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1567d-127">Before you move to Teams Only mode you need to replace or update devices that don't support Teams.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="1567d-128">**注意**: Teams への移行は、技術的な移行以上の機能です。</span><span class="sxs-lookup"><span data-stu-id="1567d-128">**Remember**: The move to Teams is more than a technical migration.</span></span> <span data-ttu-id="1567d-129">アップグレードが成功すると、技術的な準備とエンド ユーザーの準備の両方が評価されます。</span><span class="sxs-lookup"><span data-stu-id="1567d-129">A successful upgrade assesses both technical readiness and end-user readiness.</span></span> <span data-ttu-id="1567d-130">Teams へのアップグレードの実装の計画の詳細については、Skype for Business から [Teams](upgrade-framework.md) へのアップグレードに関するガイダンスを参照してください。</span><span class="sxs-lookup"><span data-stu-id="1567d-130">Review our Skype for Business to Teams [upgrade guidance](upgrade-framework.md) for more information on planning an implementing your upgrade to Teams.</span></span>  
