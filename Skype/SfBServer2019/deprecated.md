---
title: Skype for Business Server 2019 で廃止された機能
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: overview
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: '概要: これらの機能は Skype for Business Server 2019 から削除されました。'
ms.openlocfilehash: 5c5914493d7e2f4da4fd72d6acf7ff2b979d8e88
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49808727"
---
# <a name="whats-deprecated-from-skype-for-business-server-2019"></a><span data-ttu-id="be505-103">Skype for Business Server 2019 で廃止された機能</span><span class="sxs-lookup"><span data-stu-id="be505-103">What's deprecated from Skype for Business Server 2019</span></span>

<span data-ttu-id="be505-104">Skype for Business Server 2019 で廃止された機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="be505-104">Learn about the features and functionality that are deprecated in Skype for Business Server 2019.</span></span> <span data-ttu-id="be505-105">Skype for Business Server 2019 の新機能の詳細については [、「Skype for Business Server 2019](whats-new.md)の機能」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="be505-105">For information about new features in Skype for Business Server 2019, see [What's in Skype for Business Server 2019](whats-new.md).</span></span>

<span data-ttu-id="be505-106">Skype for Business Server 2019 には、以前の製品バージョンとの互換性のために、重視されていない機能がいくつか含まれています。</span><span class="sxs-lookup"><span data-stu-id="be505-106">Some de-emphasized features are included in Skype for Business Server 2019 for compatibility with previous product versions.</span></span>

## <a name="features-deprecated-in-skype-for-business-server-2019"></a><span data-ttu-id="be505-107">Skype for Business Server 2019 で廃止された機能</span><span class="sxs-lookup"><span data-stu-id="be505-107">Features deprecated in Skype for Business Server 2019</span></span> 

    The following features and functionality have been deprecated in Skype for Business Server 2019.

### <a name="xmpp-gateways-for-skype-for-business-server"></a><span data-ttu-id="be505-108">XMPP Gateways for Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="be505-108">XMPP Gateways for Skype for Business Server</span></span>

<span data-ttu-id="be505-109">Skype for Business Server 2015 とその先行タスクでは、エッジ サーバー上の XMPP (Extensible Messaging and Presence Protocol) プロキシと、フロントエンド サーバーまたはフロントエンド プール上の XMPP ゲートウェイを構成できます。</span><span class="sxs-lookup"><span data-stu-id="be505-109">Skype for Business Server 2015 and its predecessors allowed you to configure an Extensible Messaging and Presence Protocol (XMPP) proxy on the Edge Server and an XMPP Gateway on the Front End Server or Front End pool.</span></span> <span data-ttu-id="be505-110">この機能は、Skype for Business Server 2019 では使用できなくなりました。</span><span class="sxs-lookup"><span data-stu-id="be505-110">This functionality is no longer available in Skype for Business Server 2019.</span></span>

### <a name="persistent-chat-for-skype-for-business-server"></a><span data-ttu-id="be505-111">Skype for Business Server の常設チャット</span><span class="sxs-lookup"><span data-stu-id="be505-111">Persistent Chat for Skype for Business Server</span></span>

<span data-ttu-id="be505-112">常設チャット サーバーはオプションの役割で、組織内の複数のユーザーがチャット ルームの会話に参加できます。チャット ルームの会話は、時間の長い間持続します。</span><span class="sxs-lookup"><span data-stu-id="be505-112">Persistent Chat Server is an optional role that lets multiple users in your organization participate in chat room conversations that persist over time.</span></span> <span data-ttu-id="be505-113">常設チャットは Skype for Business Server 2019 では展開できません。</span><span class="sxs-lookup"><span data-stu-id="be505-113">Persistent chat can't be deployed with Skype for Business Server 2019.</span></span> <span data-ttu-id="be505-114">このサーバーの役割は、トポロジ ビルダーおよびコードから削除されます。</span><span class="sxs-lookup"><span data-stu-id="be505-114">This server role is removed from Topology Builder, as well as from the code.</span></span> 

<span data-ttu-id="be505-115">Teams でも同じ機能を使用できます。</span><span class="sxs-lookup"><span data-stu-id="be505-115">The same functionality is available in Teams.</span></span> <span data-ttu-id="be505-116">詳細については、「Microsoft Teams のアップグレード [の開始」を参照してください](/microsoftteams/upgrade-start-here)。</span><span class="sxs-lookup"><span data-stu-id="be505-116">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span>

### <a name="sql-mirroring-for-skype-for-business-server"></a><span data-ttu-id="be505-117">SQL Skype for Business Server のミラーリング</span><span class="sxs-lookup"><span data-stu-id="be505-117">SQL Mirroring for Skype for Business Server</span></span>

<span data-ttu-id="be505-118">SQL Skype for Business Server 2019 ではミラーリングを展開できません。</span><span class="sxs-lookup"><span data-stu-id="be505-118">SQL Mirroring can't be deployed with Skype for Business Server 2019.</span></span> <span data-ttu-id="be505-119">高可用性と障害復旧を提供するためのその他のオプションも引き続きサポートされ、その中から選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="be505-119">Other options for providing High Availability and Disaster Recovery are still supported and you should choose from among them.</span></span> <span data-ttu-id="be505-120">オプション [を確認するには、「Plan for high availability and disaster recovery in Skype for Business Server」](../SfbServer/plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="be505-120">See [Plan for high availability and disaster recovery in Skype for Business Server](../SfbServer/plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md) to review the options.</span></span>

### <a name="in-place-upgrades"></a><span data-ttu-id="be505-121">一括アップグレード</span><span class="sxs-lookup"><span data-stu-id="be505-121">In-place upgrades</span></span> 

<span data-ttu-id="be505-122">一時アップグレードは Skype for Business Server 2015 で利用できますが、Skype for Business Server 2019 ではサポートされなくなりました。</span><span class="sxs-lookup"><span data-stu-id="be505-122">In-place upgrades were available in Skype for Business Server 2015 but are no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="be505-123">サイド バイ サイド アップグレードと共存がサポートされています。詳細については [、「Skype for Business Server 2019](migration/migration-to-skype-for-business-server-2019.md) への移行」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="be505-123">Side by side upgrade and coexistance is supported, see [Migration to Skype for Business Server 2019](migration/migration-to-skype-for-business-server-2019.md) for more information.</span></span>

### <a name="mobility-service-mcx"></a><span data-ttu-id="be505-124">Mobility Service (Mcx)</span><span class="sxs-lookup"><span data-stu-id="be505-124">Mobility Service (Mcx)</span></span>

<span data-ttu-id="be505-125">従来のモバイル クライアントで使用される Mobility Service のサポートは、Skype for Business Server 2019 では使用できなくなりました。</span><span class="sxs-lookup"><span data-stu-id="be505-125">Mobility Service support used by legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="be505-126">これは、Skype for Business Server 2015 で以前に発表されました。</span><span class="sxs-lookup"><span data-stu-id="be505-126">This was previously announced in Skype for Business Server 2015.</span></span>

<span data-ttu-id="be505-127">現在のすべての Skype for Business モバイル クライアントはUnified Communications Web API (UCWA) を使用して、インスタント メッセージング (IM)、プレゼンス、および連絡先をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="be505-127">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="be505-128">Mcx を使用するレガシ クライアントを持つユーザーは、現在のクライアントにアップグレードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="be505-128">Users with legacy clients using Mcx will need to upgrade to a current client.</span></span>

<span data-ttu-id="be505-129">詳細については [、「Plan for Mobility for Skype for Business Server](../SfbServer/plan-your-deployment/mobility.md) and Mobile client feature comparison for Skype for Business 」を [参照してください](../SfbServer/plan-your-deployment/clients-and-devices/mobile-feature-comparison.md)。</span><span class="sxs-lookup"><span data-stu-id="be505-129">For more details, see [Plan for Mobility for Skype for Business Server](../SfbServer/plan-your-deployment/mobility.md) and [Mobile client feature comparison for Skype for Business](../SfbServer/plan-your-deployment/clients-and-devices/mobile-feature-comparison.md).</span></span>

## <a name="tools"></a><span data-ttu-id="be505-130">ツール</span><span class="sxs-lookup"><span data-stu-id="be505-130">Tools</span></span>

<span data-ttu-id="be505-131">次のツールは、Skype for Business Server 2019 の最初のリリースでは使用できません。</span><span class="sxs-lookup"><span data-stu-id="be505-131">The following tools will not be available for use at the initial release of Skype for Business Server 2019:</span></span>

- <span data-ttu-id="be505-132">Skype for Business Server の容量計画計算ツール</span><span class="sxs-lookup"><span data-stu-id="be505-132">Skype for Business Server Capacity Planning Calculator</span></span>
- <span data-ttu-id="be505-133">Skype for Business Server デバッグ ツール</span><span class="sxs-lookup"><span data-stu-id="be505-133">Skype for Business Server Debugging Tools</span></span>
- <span data-ttu-id="be505-134">Skype for Business Server リソース キット ツール (一部のツールは削除されます)</span><span class="sxs-lookup"><span data-stu-id="be505-134">Skype for Business Server Resource Kit Tools (some tools will be removed)</span></span>
    - <span data-ttu-id="be505-135">Call Parkometer</span><span class="sxs-lookup"><span data-stu-id="be505-135">Call Parkometer</span></span>
    - <span data-ttu-id="be505-136">ユーザー コンソールを参照する</span><span class="sxs-lookup"><span data-stu-id="be505-136">Lookup user console</span></span>
    - <span data-ttu-id="be505-137">割り当てられていない番号のアナウンスの移行</span><span class="sxs-lookup"><span data-stu-id="be505-137">Unassigned number Announcement Migration</span></span>

<span data-ttu-id="be505-138">次のツールは、Skype for Business Server 2019 ではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="be505-138">The following tools are not supported with Skype for Business Server 2019:</span></span>

- <span data-ttu-id="be505-139">通話品質の方法論 (通話品質ダッシュボードではない)</span><span class="sxs-lookup"><span data-stu-id="be505-139">Call Quality Methodology (but not Call Quality Dashboard)</span></span>
- <span data-ttu-id="be505-140">Microsoft Call Quality Methodology Scorecard、v1.5</span><span class="sxs-lookup"><span data-stu-id="be505-140">Microsoft Call Quality Methodology Scorecard, v1.5</span></span>
- <span data-ttu-id="be505-141">Skype for Business Server 2015 計画ツール</span><span class="sxs-lookup"><span data-stu-id="be505-141">Skype for Business Server 2015 Planning Tool</span></span>
- <span data-ttu-id="be505-142">Skype for Business Server 2015 Stress and Performance Tool</span><span class="sxs-lookup"><span data-stu-id="be505-142">Skype for Business Server 2015 Stress and Performance Tool</span></span>

### <a name="see-also"></a><span data-ttu-id="be505-143">関連項目</span><span class="sxs-lookup"><span data-stu-id="be505-143">See also</span></span>

[<span data-ttu-id="be505-144">Skype for Business Server 2019 の新機能</span><span class="sxs-lookup"><span data-stu-id="be505-144">What's new in Skype for Business Server 2019</span></span>](whats-new.md)

[<span data-ttu-id="be505-145">XMPP フェデレーションの移行</span><span class="sxs-lookup"><span data-stu-id="be505-145">Migrating XMPP federation</span></span>](migration/migrating-xmpp-federation.md)
