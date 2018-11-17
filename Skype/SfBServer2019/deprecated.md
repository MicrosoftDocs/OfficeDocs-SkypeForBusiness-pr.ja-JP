---
title: ビジネス サーバー 2019 の Skype からどのような使用されなくなりました
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: overview
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
description: '概要: これらの機能がなくなる Skype からビジネス サーバー 2019 のです。'
ms.openlocfilehash: 399c5f219ae5a088c4e7f8aa40f40344885d571e
ms.sourcegitcommit: 6ad3ce36140464319f5957652331acd6a4273f82
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2018
ms.locfileid: "26561612"
---
# <a name="whats-deprecated-from-skype-for-business-server-2019"></a><span data-ttu-id="3e9d1-103">ビジネス サーバー 2019 の Skype からどのような使用されなくなりました</span><span class="sxs-lookup"><span data-stu-id="3e9d1-103">What's deprecated from Skype for Business Server 2019</span></span>

<span data-ttu-id="3e9d1-104">ビジネス サーバー 2019 の Skype で廃止された機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="3e9d1-104">Learn about the features and functionality that are deprecated in Skype for Business Server 2019.</span></span> <span data-ttu-id="3e9d1-105">ビジネス サーバー 2019 の Skype の新機能については、[ビジネス サーバー 2019 の Skype では、何](whats-new.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3e9d1-105">For information about new features in Skype for Business Server 2019, see [What's in Skype for Business Server 2019](whats-new.md).</span></span>

<span data-ttu-id="3e9d1-106">Emphasised の機能の一部に含まれて Skype ビジネス サーバー 2019 製品の以前のバージョンとの互換性のためです。</span><span class="sxs-lookup"><span data-stu-id="3e9d1-106">Some de-emphasised features are included in Skype for Business Server 2019 for compatibility with previous product versions.</span></span>

## <a name="features-deprecated-in-skype-for-business-server-2019"></a><span data-ttu-id="3e9d1-107">ビジネス サーバー 2019 の Skype では非推奨の機能</span><span class="sxs-lookup"><span data-stu-id="3e9d1-107">Features deprecated in Skype for Business Server 2019</span></span> 

    The following features and functionality have been deprecated in Skype for Business Server 2019.

### <a name="xmpp-gateways-for-skype-for-business-server"></a><span data-ttu-id="3e9d1-108">ビジネス サーバーの Skype の XMPP ゲートウェイ</span><span class="sxs-lookup"><span data-stu-id="3e9d1-108">XMPP Gateways for Skype for Business Server</span></span>

<span data-ttu-id="3e9d1-109">ビジネス サーバー 2015 と、以前のバージョンの Skype には、エッジ サーバーとフロント エンド サーバーまたはフロント エンド プールに、XMPP ゲートウェイの拡張可能なメッセージングおよびプレゼンス プロトコル (XMPP) プロキシを構成することができました。</span><span class="sxs-lookup"><span data-stu-id="3e9d1-109">Skype for Business Server 2015 and its predecessors allowed you to configure an Extensible Messaging and Presence Protocol (XMPP) proxy on the Edge Server and an XMPP Gateway on the Front End Server or Front End pool.</span></span> <span data-ttu-id="3e9d1-110">この機能は、ビジネス サーバー 2019 の Skype で利用可能ではありません。</span><span class="sxs-lookup"><span data-stu-id="3e9d1-110">This functionality is no longer available in Skype for Business Server 2019.</span></span>

### <a name="persistent-chat-for-skype-for-business-server"></a><span data-ttu-id="3e9d1-111">Skype のビジネス サーバー用の永続的なチャット</span><span class="sxs-lookup"><span data-stu-id="3e9d1-111">Persistent Chat for Skype for Business Server</span></span>

<span data-ttu-id="3e9d1-112">永続的なチャット サーバーは、組織内の複数のユーザーをできるようにするオプションのロールは、時間の経過と共に永続化するチャット ルームの会話に参加します。</span><span class="sxs-lookup"><span data-stu-id="3e9d1-112">Persistent Chat Server is an optional role that lets multiple users in your organization participate in chat room conversations that persist over time.</span></span> <span data-ttu-id="3e9d1-113">ビジネス サーバー 2019 Skype で永続的なチャットに展開することはできません。</span><span class="sxs-lookup"><span data-stu-id="3e9d1-113">Persistent chat can't be deployed with Skype for Business Server 2019.</span></span> <span data-ttu-id="3e9d1-114">トポロジ ビルダー、およびコードからは、このサーバーの役割が削除されます。</span><span class="sxs-lookup"><span data-stu-id="3e9d1-114">This server role is removed from Topology Builder, as well as from the code.</span></span> 

<span data-ttu-id="3e9d1-115">同じ機能は、チームで使用できます。</span><span class="sxs-lookup"><span data-stu-id="3e9d1-115">The same functionality is available in Teams.</span></span> <span data-ttu-id="3e9d1-116">詳細については、[マイクロソフトのチームにビジネス用の Skype からの旅](/microsoftteams/journey-skypeforbusiness-teams)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3e9d1-116">For more information, see [Journey from Skype for Business to Microsoft Teams](/microsoftteams/journey-skypeforbusiness-teams).</span></span>

### <a name="sql-mirroring-for-skype-for-business-server"></a><span data-ttu-id="3e9d1-117">SQL が Skype のビジネス サーバーのミラーリング</span><span class="sxs-lookup"><span data-stu-id="3e9d1-117">SQL Mirroring for Skype for Business Server</span></span>

<span data-ttu-id="3e9d1-118">SQL のミラーリングを展開できません Skype でのビジネス サーバー 2019。</span><span class="sxs-lookup"><span data-stu-id="3e9d1-118">SQL Mirroring can't be deployed with Skype for Business Server 2019.</span></span> <span data-ttu-id="3e9d1-119">高可用性と災害復旧を提供するその他のオプションがサポートされていて、その中から選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3e9d1-119">Other options for providing High Availability and Disaster Recovery are still supported and you should choose from among them.</span></span> <span data-ttu-id="3e9d1-120">オプションを確認するのには[高可用性とビジネスのサーバー用の Skype での災害復旧の計画](../SfbServer/plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3e9d1-120">See [Plan for high availability and disaster recovery in Skype for Business Server](../SfbServer/plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md) to review the options.</span></span>

### <a name="in-place-upgrades"></a><span data-ttu-id="3e9d1-121">インプレース アップグレード</span><span class="sxs-lookup"><span data-stu-id="3e9d1-121">In-place upgrades</span></span> 

<span data-ttu-id="3e9d1-122">インプレース アップグレードはビジネス サーバー 2015 の Skype で利用できるが、ビジネス サーバー 2019 の Skype でサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="3e9d1-122">In-place upgrades were available in Skype for Business Server 2015 but are no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="3e9d1-123">アップグレードおよび coexistance のサポートに並べて、[ビジネス サーバー 2019 の Skype への移行](migration/migration-to-skype-for-business-server-2019.md)の詳細についてを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3e9d1-123">Side by side upgrade and coexistance is supported, see [Migration to Skype for Business Server 2019](migration/migration-to-skype-for-business-server-2019.md) for more information.</span></span>

### <a name="mobility-service-mcx"></a><span data-ttu-id="3e9d1-124">モビリティ サービス (Mcx)</span><span class="sxs-lookup"><span data-stu-id="3e9d1-124">Mobility Service (Mcx)</span></span>

<span data-ttu-id="3e9d1-125">モビリティ サービスのサポートが従来のモバイル クライアントによって使用されるがビジネス サーバー 2019 の Skype で利用可能ではありません。</span><span class="sxs-lookup"><span data-stu-id="3e9d1-125">Mobility Service support used by legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="3e9d1-126">以前、Skype のビジネス サーバー 2015 のこの発表されました。</span><span class="sxs-lookup"><span data-stu-id="3e9d1-126">This was previously announced in Skype for Business Server 2015.</span></span>

<span data-ttu-id="3e9d1-127">ビジネスのモバイル クライアントのすべての現在 Skype は、インスタント メッセージング (IM)、プレゼンス、および取引先担当者をサポートするために既にユニファイド コミュニケーション Web API (UCWA) を使用します。</span><span class="sxs-lookup"><span data-stu-id="3e9d1-127">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="3e9d1-128">Mcx を使用する従来のクライアントを持つユーザーは、現在のクライアントにアップグレードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="3e9d1-128">Users with legacy clients using Mcx will need to upgrade to a current client.</span></span>

<span data-ttu-id="3e9d1-129">詳細については、 [Skype ビジネス サーバーの移動を計画](../SfbServer/plan-your-deployment/mobility.md)し、[ビジネスの Skype のモバイル クライアントの機能の比較](../SfbServer/plan-your-deployment/clients-and-devices/mobile-feature-comparison.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3e9d1-129">For more details, see [Plan for Mobility for Skype for Business Server](../SfbServer/plan-your-deployment/mobility.md) and [Mobile client feature comparison for Skype for Business](../SfbServer/plan-your-deployment/clients-and-devices/mobile-feature-comparison.md).</span></span>

## <a name="tools"></a><span data-ttu-id="3e9d1-130">ツール</span><span class="sxs-lookup"><span data-stu-id="3e9d1-130">Tools</span></span>

<span data-ttu-id="3e9d1-131">次のツールはビジネス サーバー 2019 Skype の初期のリリースで使用できません。</span><span class="sxs-lookup"><span data-stu-id="3e9d1-131">The following tools will not be available for use at the initial release of Skype for Business Server 2019:</span></span>

- <span data-ttu-id="3e9d1-132">Skype ビジネス サーバーの容量計画の計算について</span><span class="sxs-lookup"><span data-stu-id="3e9d1-132">Skype for Business Server Capacity Planning Calculator</span></span>
- <span data-ttu-id="3e9d1-133">Skype ビジネス サーバーのデバッグ ツールの</span><span class="sxs-lookup"><span data-stu-id="3e9d1-133">Skype for Business Server Debugging Tools</span></span>
- <span data-ttu-id="3e9d1-134">Skype のビジネス サーバーのリソース キット ツールは (いくつかのツールは削除されます)</span><span class="sxs-lookup"><span data-stu-id="3e9d1-134">Skype for Business Server Resource Kit Tools (some tools will be removed)</span></span>
    - <span data-ttu-id="3e9d1-135">Call Parkometer</span><span class="sxs-lookup"><span data-stu-id="3e9d1-135">Call Parkometer</span></span>
    - <span data-ttu-id="3e9d1-136">参照ユーザー コンソール</span><span class="sxs-lookup"><span data-stu-id="3e9d1-136">Lookup user console</span></span>
    - <span data-ttu-id="3e9d1-137">割り当てられていない番号移行のお知らせ</span><span class="sxs-lookup"><span data-stu-id="3e9d1-137">Unassigned number Announcement Migration</span></span>

<span data-ttu-id="3e9d1-138">ビジネス サーバー 2019 の Skype で、次のツールがサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="3e9d1-138">The following tools are not supported with Skype for Business Server 2019:</span></span>

- <span data-ttu-id="3e9d1-139">品質方法論を呼び出す (ですが、品質のダッシュ ボードを呼び出していない)</span><span class="sxs-lookup"><span data-stu-id="3e9d1-139">Call Quality Methodology (but not Call Quality Dashboard)</span></span>
- <span data-ttu-id="3e9d1-140">Microsoft 呼び出し品質方法論のスコアカード、v1.5</span><span class="sxs-lookup"><span data-stu-id="3e9d1-140">Microsoft Call Quality Methodology Scorecard, v1.5</span></span>
- <span data-ttu-id="3e9d1-141">Skype for Business Server 2015 Planning Tool</span><span class="sxs-lookup"><span data-stu-id="3e9d1-141">Skype for Business Server 2015 Planning Tool</span></span>
- <span data-ttu-id="3e9d1-142">Skype for Business Server 2015 Stress and Performance Tool</span><span class="sxs-lookup"><span data-stu-id="3e9d1-142">Skype for Business Server 2015 Stress and Performance Tool</span></span>

### <a name="see-also"></a><span data-ttu-id="3e9d1-143">関連項目</span><span class="sxs-lookup"><span data-stu-id="3e9d1-143">See also</span></span>

[<span data-ttu-id="3e9d1-144">ビジネス サーバー 2019 の Skype の新機能</span><span class="sxs-lookup"><span data-stu-id="3e9d1-144">What's new in Skype for Business Server 2019</span></span>](whats-new.md)

[<span data-ttu-id="3e9d1-145">XMPP フェデレーションを移行します。</span><span class="sxs-lookup"><span data-stu-id="3e9d1-145">Migrating XMPP federation</span></span>](migration/migrating-xmpp-federation.md)