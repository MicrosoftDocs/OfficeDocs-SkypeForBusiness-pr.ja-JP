---
title: Skype for Business Server 2019 で廃止される機能
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
audience: ITPro
ms.topic: overview
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
description: '概要: これらの機能は、Skype for Business Server 2019 から削除されました。'
ms.openlocfilehash: 9fd6ddc28a3b75b8d4c411aa7909516d4b5c0ab8
ms.sourcegitcommit: d4248fefd706616bd3ccc5b510a6696303fa88e1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2019
ms.locfileid: "35418362"
---
# <a name="whats-deprecated-from-skype-for-business-server-2019"></a><span data-ttu-id="38283-103">Skype for Business Server 2019 で廃止される機能</span><span class="sxs-lookup"><span data-stu-id="38283-103">What's deprecated from Skype for Business Server 2019</span></span>

<span data-ttu-id="38283-104">Skype for Business Server 2019 で廃止された機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="38283-104">Learn about the features and functionality that are deprecated in Skype for Business Server 2019.</span></span> <span data-ttu-id="38283-105">Skype for Business Server 2019 の新機能の詳細については、「Skype for business [server 2019](whats-new.md)の機能」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="38283-105">For information about new features in Skype for Business Server 2019, see [What's in Skype for Business Server 2019](whats-new.md).</span></span>

<span data-ttu-id="38283-106">以前の製品バージョンとの互換性を確保するために、いくつかの強調機能が Skype for Business Server 2019 に含まれています。</span><span class="sxs-lookup"><span data-stu-id="38283-106">Some de-emphasized features are included in Skype for Business Server 2019 for compatibility with previous product versions.</span></span>

## <a name="features-deprecated-in-skype-for-business-server-2019"></a><span data-ttu-id="38283-107">Skype for Business Server 2019 で廃止された機能</span><span class="sxs-lookup"><span data-stu-id="38283-107">Features deprecated in Skype for Business Server 2019</span></span> 

    The following features and functionality have been deprecated in Skype for Business Server 2019.

### <a name="xmpp-gateways-for-skype-for-business-server"></a><span data-ttu-id="38283-108">Skype for Business Server 用 XMPP ゲートウェイ</span><span class="sxs-lookup"><span data-stu-id="38283-108">XMPP Gateways for Skype for Business Server</span></span>

<span data-ttu-id="38283-109">Skype for Business Server 2015 とその先行機能を使用すると、エッジサーバー上の拡張メッセージングとプレゼンスプロトコル (XMPP) プロキシ、およびフロントエンドサーバーまたはフロントエンドプールの XMPP ゲートウェイを構成することができます。</span><span class="sxs-lookup"><span data-stu-id="38283-109">Skype for Business Server 2015 and its predecessors allowed you to configure an Extensible Messaging and Presence Protocol (XMPP) proxy on the Edge Server and an XMPP Gateway on the Front End Server or Front End pool.</span></span> <span data-ttu-id="38283-110">この機能は、Skype for Business Server 2019 では利用できなくなりました。</span><span class="sxs-lookup"><span data-stu-id="38283-110">This functionality is no longer available in Skype for Business Server 2019.</span></span>

### <a name="persistent-chat-for-skype-for-business-server"></a><span data-ttu-id="38283-111">Skype for Business Server の常設チャット</span><span class="sxs-lookup"><span data-stu-id="38283-111">Persistent Chat for Skype for Business Server</span></span>

<span data-ttu-id="38283-112">常設チャットサーバーは、組織内の複数のユーザーが、時間を経て持続するチャットルームの会話に参加できるようにする、オプションの役割です。</span><span class="sxs-lookup"><span data-stu-id="38283-112">Persistent Chat Server is an optional role that lets multiple users in your organization participate in chat room conversations that persist over time.</span></span> <span data-ttu-id="38283-113">常設チャットを Skype for Business Server 2019 で展開することはできません。</span><span class="sxs-lookup"><span data-stu-id="38283-113">Persistent chat can't be deployed with Skype for Business Server 2019.</span></span> <span data-ttu-id="38283-114">このサーバーロールは、コードからではなく、トポロジビルダーからも削除されます。</span><span class="sxs-lookup"><span data-stu-id="38283-114">This server role is removed from Topology Builder, as well as from the code.</span></span> 

<span data-ttu-id="38283-115">Teams でも同じ機能を使用できます。</span><span class="sxs-lookup"><span data-stu-id="38283-115">The same functionality is available in Teams.</span></span> <span data-ttu-id="38283-116">詳細については、「 [Microsoft Teams のアップグレードの](/microsoftteams/upgrade-start-here)概要」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="38283-116">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span>

### <a name="sql-mirroring-for-skype-for-business-server"></a><span data-ttu-id="38283-117">Skype for Business Server の SQL ミラーリング</span><span class="sxs-lookup"><span data-stu-id="38283-117">SQL Mirroring for Skype for Business Server</span></span>

<span data-ttu-id="38283-118">SQL ミラーリングは、Skype for Business Server 2019 と共に展開することはできません。</span><span class="sxs-lookup"><span data-stu-id="38283-118">SQL Mirroring can't be deployed with Skype for Business Server 2019.</span></span> <span data-ttu-id="38283-119">高可用性と障害回復を実現するその他のオプションもサポートされていますが、それらの中から選択することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="38283-119">Other options for providing High Availability and Disaster Recovery are still supported and you should choose from among them.</span></span> <span data-ttu-id="38283-120">オプションを確認するには、「 [Skype For Business Server で高可用性と障害回復を計画](../SfbServer/plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="38283-120">See [Plan for high availability and disaster recovery in Skype for Business Server](../SfbServer/plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md) to review the options.</span></span>

### <a name="in-place-upgrades"></a><span data-ttu-id="38283-121">インプレースアップグレード</span><span class="sxs-lookup"><span data-stu-id="38283-121">In-place upgrades</span></span> 

<span data-ttu-id="38283-122">インプレースアップグレードは、Skype for Business Server 2015 で使用できましたが、Skype for Business Server 2019 ではサポートされなくなりました。</span><span class="sxs-lookup"><span data-stu-id="38283-122">In-place upgrades were available in Skype for Business Server 2015 but are no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="38283-123">サイドバイサイドアップグレードと coexistance 使用はサポートされています。詳細については、「 [Skype For Business Server 2019 への移行](migration/migration-to-skype-for-business-server-2019.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="38283-123">Side by side upgrade and coexistance is supported, see [Migration to Skype for Business Server 2019](migration/migration-to-skype-for-business-server-2019.md) for more information.</span></span>

### <a name="mobility-service-mcx"></a><span data-ttu-id="38283-124">モビリティーサービス (Mcx)</span><span class="sxs-lookup"><span data-stu-id="38283-124">Mobility Service (Mcx)</span></span>

<span data-ttu-id="38283-125">従来のモバイルクライアントで使用されているモバイルサービスのサポートは、Skype for Business Server 2019 では利用できなくなりました。</span><span class="sxs-lookup"><span data-stu-id="38283-125">Mobility Service support used by legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="38283-126">これは、Skype for Business Server 2015 で以前に発表されました。</span><span class="sxs-lookup"><span data-stu-id="38283-126">This was previously announced in Skype for Business Server 2015.</span></span>

<span data-ttu-id="38283-127">現在のすべての Skype for Business のモバイルクライアントでは、インスタントメッセージング (IM)、プレゼンス、連絡先をサポートするために、既にユニファイドコミュニケーション Web API (UCWA) を使用しています。</span><span class="sxs-lookup"><span data-stu-id="38283-127">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="38283-128">Mcx を使用するレガシクライアントを使っているユーザーは、現在のクライアントにアップグレードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="38283-128">Users with legacy clients using Mcx will need to upgrade to a current client.</span></span>

<span data-ttu-id="38283-129">詳細については、「skype for business [Server のモビリティの計画](../SfbServer/plan-your-deployment/mobility.md)」および「 [skype For business のモバイルクライアント機能の比較](../SfbServer/plan-your-deployment/clients-and-devices/mobile-feature-comparison.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="38283-129">For more details, see [Plan for Mobility for Skype for Business Server](../SfbServer/plan-your-deployment/mobility.md) and [Mobile client feature comparison for Skype for Business](../SfbServer/plan-your-deployment/clients-and-devices/mobile-feature-comparison.md).</span></span>

## <a name="tools"></a><span data-ttu-id="38283-130">ツール</span><span class="sxs-lookup"><span data-stu-id="38283-130">Tools</span></span>

<span data-ttu-id="38283-131">以下のツールは、Skype for Business Server 2019 の最初のリリースでは使用できません。</span><span class="sxs-lookup"><span data-stu-id="38283-131">The following tools will not be available for use at the initial release of Skype for Business Server 2019:</span></span>

- <span data-ttu-id="38283-132">Skype for Business Server の容量計画計算ツール</span><span class="sxs-lookup"><span data-stu-id="38283-132">Skype for Business Server Capacity Planning Calculator</span></span>
- <span data-ttu-id="38283-133">Skype for Business Server のデバッグツール</span><span class="sxs-lookup"><span data-stu-id="38283-133">Skype for Business Server Debugging Tools</span></span>
- <span data-ttu-id="38283-134">Skype for Business Server リソースキットツール (一部のツールは削除されます)</span><span class="sxs-lookup"><span data-stu-id="38283-134">Skype for Business Server Resource Kit Tools (some tools will be removed)</span></span>
    - <span data-ttu-id="38283-135">Call Parkometer</span><span class="sxs-lookup"><span data-stu-id="38283-135">Call Parkometer</span></span>
    - <span data-ttu-id="38283-136">ユーザーコンソールを参照する</span><span class="sxs-lookup"><span data-stu-id="38283-136">Lookup user console</span></span>
    - <span data-ttu-id="38283-137">未割り当ての番号の移行</span><span class="sxs-lookup"><span data-stu-id="38283-137">Unassigned number Announcement Migration</span></span>

<span data-ttu-id="38283-138">以下のツールは、Skype for Business Server 2019 ではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="38283-138">The following tools are not supported with Skype for Business Server 2019:</span></span>

- <span data-ttu-id="38283-139">通話品質の方法 (通話品質ダッシュボードではありません)</span><span class="sxs-lookup"><span data-stu-id="38283-139">Call Quality Methodology (but not Call Quality Dashboard)</span></span>
- <span data-ttu-id="38283-140">Microsoft 通話品質の方法スコアカード、v 1.5</span><span class="sxs-lookup"><span data-stu-id="38283-140">Microsoft Call Quality Methodology Scorecard, v1.5</span></span>
- <span data-ttu-id="38283-141">Skype for Business Server 2015 計画ツール</span><span class="sxs-lookup"><span data-stu-id="38283-141">Skype for Business Server 2015 Planning Tool</span></span>
- <span data-ttu-id="38283-142">Skype for Business Server 2015 Stress and Performance Tool</span><span class="sxs-lookup"><span data-stu-id="38283-142">Skype for Business Server 2015 Stress and Performance Tool</span></span>

### <a name="see-also"></a><span data-ttu-id="38283-143">関連項目</span><span class="sxs-lookup"><span data-stu-id="38283-143">See also</span></span>

[<span data-ttu-id="38283-144">Skype for Business Server 2019 の新機能</span><span class="sxs-lookup"><span data-stu-id="38283-144">What's new in Skype for Business Server 2019</span></span>](whats-new.md)

[<span data-ttu-id="38283-145">XMPP フェデレーションの移行</span><span class="sxs-lookup"><span data-stu-id="38283-145">Migrating XMPP federation</span></span>](migration/migrating-xmpp-federation.md)
