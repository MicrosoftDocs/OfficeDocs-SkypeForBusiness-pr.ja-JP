---
title: Teams Only モードの考慮事項
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 01/09/2019
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.reviewer: landerl
description: 管理者は、Microsoft Teams 管理センターで、Microsoft Teams 専用モードへのアップグレードを準備する方法について説明します。
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
ms.openlocfilehash: 96ff2652a326e537f200c47495496dd81ea9fd4b
ms.sourcegitcommit: 27fae90d4429e81143ea285edab9dbc19bd3c0bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/23/2020
ms.locfileid: "44854099"
---
# <a name="teams-only-mode-considerations"></a><span data-ttu-id="58695-103">Teams Only モードの考慮事項</span><span class="sxs-lookup"><span data-stu-id="58695-103">Teams Only mode considerations</span></span>

<span data-ttu-id="58695-104">Microsoft 365 または Office 365 の組織の管理者である場合、Microsoft Teams 管理センターで [チームのみ] モードにアップグレードするオプションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="58695-104">If you are an administrator in your Microsoft 365 or Office 365 organization, you will now see the option to upgrade to Teams Only mode in the Microsoft Teams admin center.</span></span> <span data-ttu-id="58695-105">この機能を使用すると、個々のユーザーまたはテナント全体のどちらかをアップグレードできます。</span><span class="sxs-lookup"><span data-stu-id="58695-105">With this functionality you can upgrade either individual users, or alternatively, the entire tenant.</span></span>  

<span data-ttu-id="58695-106">Teams 専用モードにアップグレードすると、ユーザーは1つのクライアントエクスペリエンスで microsoft Teams、チームワークのハブ、Microsoft 365 または Office 365 のハブを最大限に活用できます。</span><span class="sxs-lookup"><span data-stu-id="58695-106">Upgrading to Teams Only mode offers users the full benefits of Microsoft Teams, the hub for teamwork in Microsoft 365 or Office 365, via a single client experience.</span></span> <span data-ttu-id="58695-107">さらに、チーム専用モードのユーザーは、送信者が Skype for Business または Teams を使用しているかどうかにかかわらず、すべての通話とチャットを受け取り、相互運用およびフェデレーションサポートによる恩恵を受けることができます。</span><span class="sxs-lookup"><span data-stu-id="58695-107">Additionally, users in Teams Only mode will receive all calls and chats in Teams, regardless of whether the sender is using Skype for Business or Teams, and benefit from interop and federation support.</span></span>

<span data-ttu-id="58695-108">多くのユーザーが Microsoft Teams にアップグレードしましたが、組織のアップグレードタイムラインとユーザーエクスペリエンスに影響を与える可能性があるという考慮事項があります。</span><span class="sxs-lookup"><span data-stu-id="58695-108">While thousands of customers have successfully upgraded to Microsoft Teams, there are considerations that may influence your organization's upgrade timeline and user experience along the way.</span></span> <span data-ttu-id="58695-109">特に、アップグレードのオプションを使用しても、組織がこの変更に対応できるというわけではありません。</span><span class="sxs-lookup"><span data-stu-id="58695-109">In particular, having the option to upgrade doesn't necessarily mean your organization is ready for this change.</span></span> <span data-ttu-id="58695-110">最高のユーザー エクスペリエンスを得るために、Teams が自分たちの共同作業や通信の要件に適合してることを確認し、確実にお使いのネットワークが Teams をサポートする状態を整えて、ユーザーの準備状態計画を実施してから Teams へのユーザーのアップグレードを実行してください。</span><span class="sxs-lookup"><span data-stu-id="58695-110">For the best user experience, confirm that Teams meets your collaboration and communication requirements, make sure that your network is ready to support Teams, and implement your user readiness plan before upgrading users to Teams.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="58695-111">アップグレード計画を開始する場合は、「 [Microsoft Teams のアップグレードに](upgrade-start-here.md)ついて」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="58695-111">If you are just starting your upgrade planning, be sure to review our [Getting started with your Microsoft Teams upgrade](upgrade-start-here.md) guide.</span></span> 

<span data-ttu-id="58695-112">**共存の考慮事項**: Skype For business Online または Skype For business Server を既に使用している組織では、ニーズに合ったペースでチームを環境に導入することができます。</span><span class="sxs-lookup"><span data-stu-id="58695-112">**Coexistence considerations**: Organizations already using Skype for Business Online and/or Skype for Business Server can introduce Teams into their environment at a pace that meets their needs.</span></span> <span data-ttu-id="58695-113">組織では、必要に応じて、チームを目的に応じたユーザーのセットに段階的にロールアウトできます。また、Teams を使用するユーザーは、Skype for Business を使用するユーザーと通信することができます。</span><span class="sxs-lookup"><span data-stu-id="58695-113">Organizations can incrementally roll out Teams to a desired set of users as needed, and users who use Teams can communicate with users who use Skype for Business and vice versa.</span></span> <span data-ttu-id="58695-114">このエクスペリエンスを管理するために、管理者は、エンドユーザーのクライアントエクスペリエンス、着信チャットと通話のルーティング動作、チームまたは Skype for Business で新しい会議をスケジュールするかどうかを定義する、共存モードを使用します。</span><span class="sxs-lookup"><span data-stu-id="58695-114">To manage this experience, administrators use coexistence modes, which define the end user client experience, the routing behavior of incoming chats and calls, as well as whether new meetings are scheduled in Teams or Skype for Business.</span></span> <span data-ttu-id="58695-115">ユーザーが**Teams のみ**にアップグレードされた場合、ユーザーは他の組織のユーザーとフェデレーションを行うことができます。ただし、両方のユーザーが Teams を使用する場合に最適なエクスペリエンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="58695-115">Users can federate with users in other organizations if the user is upgraded to **Teams Only**; however, the best experience is provided when both users use Teams.</span></span> <span data-ttu-id="58695-116">Teams にアップグレードされたユーザーのみが、引き続き Skype for Business 会議に参加できます。</span><span class="sxs-lookup"><span data-stu-id="58695-116">Users who are upgraded to Teams Only can still join Skype for Business meetings.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="58695-117">共存の詳細については、「 [Microsoft Teams と Skype For business の共存と相互運用性](teams-and-skypeforbusiness-coexistence-and-interoperability.md)について」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="58695-117">For more detailed information about coexistence please refer to [Understand Microsoft Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md).</span></span> 

<span data-ttu-id="58695-118">**テナント全体の考慮事項**: 次の環境で Teams を有効にするための作業を進めています。ただし、現在のところ、Skype for Business テナントが次のいずれかの環境でホストされている場合、管理者は組織内のユーザーをアップグレードすることはできません。</span><span class="sxs-lookup"><span data-stu-id="58695-118">**Tenant-wide considerations**: We are working on enabling Teams in the following environments; however, for now, administrators shouldn't upgrade any users in their organization if their Skype for Business tenant is hosted in one of the following environments:</span></span>

 - <span data-ttu-id="58695-119">21Vianet が運営する Office 365</span><span class="sxs-lookup"><span data-stu-id="58695-119">Office 365 operated by 21Vianet</span></span>
 - <span data-ttu-id="58695-120">Office 365 ドイツ</span><span class="sxs-lookup"><span data-stu-id="58695-120">Office 365 Germany</span></span>
 - <span data-ttu-id="58695-121">Skype for Business テナントは韓国でホストされています。**また**、組織は、韓国で Teams のデータを保存する必要があります。</span><span class="sxs-lookup"><span data-stu-id="58695-121">Skype for Business tenant is hosted in South Korea **and** the organization requires Teams data to be stored in South Korea.</span></span> <span data-ttu-id="58695-122">現在、Skype for Business データを使用している組織では、チームにアップグレードした韓国のデータは、韓国のデータセンターの地域ではなく、アジアのデータセンターに保存されています。</span><span class="sxs-lookup"><span data-stu-id="58695-122">Currently, organizations with Skype for Business data stored in South Korea that upgrade to Teams will have their Teams data stored in the Asia datacenter region, not in the South Korea datacenter region.</span></span>

<span data-ttu-id="58695-123">**ユーザー固有の考慮事項**: 一部のユーザーシナリオはまだ進化し続けており、管理者が組織内の他のユーザーのアップグレード中に、特定のユーザーのアップグレードを一時的に延期することを決定する場合があります。</span><span class="sxs-lookup"><span data-stu-id="58695-123">**User-specific considerations**: Some user scenarios are still evolving, and administrators may decide to temporarily postpone the upgrade of certain users while upgrading other users in the organization.</span></span> <span data-ttu-id="58695-124">特に、プライマリデバイスが VDI ベースであるユーザーのアドレス指定のシナリオについては、引き続き取り組んでいます。</span><span class="sxs-lookup"><span data-stu-id="58695-124">In particular, we are still working on addressing scenarios for users whose primary device is VDI-based.</span></span> <span data-ttu-id="58695-125">[Microsoft 365 ロードマップ](https://www.microsoft.com/microsoft-365/roadmap)サイトでお知らせを監視してください。</span><span class="sxs-lookup"><span data-stu-id="58695-125">Please monitor the [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap) site for announcements.</span></span>

> [!NOTE]
> <span data-ttu-id="58695-126">Teams 専用モードに移行する前に、Teams をサポートしていないデバイスを置き換えるか更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="58695-126">Before you move to Teams Only mode you need to replace or update devices that don't support Teams.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="58695-127">Teams への移行は、技術的な移行よりも多くのことを**覚えておい**てください。</span><span class="sxs-lookup"><span data-stu-id="58695-127">**Remember**: The move to Teams is more than a technical migration.</span></span> <span data-ttu-id="58695-128">アップグレードが成功すると、技術的な準備とエンドユーザーの準備の両方が評価されます。</span><span class="sxs-lookup"><span data-stu-id="58695-128">A successful upgrade assesses both technical readiness and end-user readiness.</span></span> <span data-ttu-id="58695-129">Teams へのアップグレードの実装の計画の詳細については、「Skype for Business と Teams の[アップグレードのガイダンス](upgrade-framework.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="58695-129">Review our Skype for Business to Teams [upgrade guidance](upgrade-framework.md) for more information on planning an implementing your upgrade to Teams.</span></span>  
