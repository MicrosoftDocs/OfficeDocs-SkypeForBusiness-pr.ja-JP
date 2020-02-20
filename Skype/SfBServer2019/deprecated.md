---
title: Skype for Business Server 2019 で廃止された機能
ms.reviewer: ''
ms.author: v-lanac
author: LanaChin
manager: serdars
audience: ITPro
ms.topic: overview
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: '概要: これらの機能は、Skype for Business Server 2019 から削除されました。'
ms.openlocfilehash: 40a202f802ec8ac1a0f880f92ad9cf59ce68a627
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42125220"
---
# <a name="whats-deprecated-from-skype-for-business-server-2019"></a><span data-ttu-id="05859-103">Skype for Business Server 2019 で廃止された機能</span><span class="sxs-lookup"><span data-stu-id="05859-103">What's deprecated from Skype for Business Server 2019</span></span>

<span data-ttu-id="05859-104">Skype for Business Server 2019 で廃止された機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="05859-104">Learn about the features and functionality that are deprecated in Skype for Business Server 2019.</span></span> <span data-ttu-id="05859-105">Skype for business Server 2019 の新機能の詳細については、「 [skype For Business server 2019 の内容](whats-new.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="05859-105">For information about new features in Skype for Business Server 2019, see [What's in Skype for Business Server 2019](whats-new.md).</span></span>

<span data-ttu-id="05859-106">以前の製品バージョンとの互換性のために、いくつかの重要な機能が Skype for Business Server 2019 に含まれています。</span><span class="sxs-lookup"><span data-stu-id="05859-106">Some de-emphasized features are included in Skype for Business Server 2019 for compatibility with previous product versions.</span></span>

## <a name="features-deprecated-in-skype-for-business-server-2019"></a><span data-ttu-id="05859-107">Skype for Business Server 2019 で廃止された機能</span><span class="sxs-lookup"><span data-stu-id="05859-107">Features deprecated in Skype for Business Server 2019</span></span> 

    The following features and functionality have been deprecated in Skype for Business Server 2019.

### <a name="xmpp-gateways-for-skype-for-business-server"></a><span data-ttu-id="05859-108">Skype for business Server 用の XMPP ゲートウェイ</span><span class="sxs-lookup"><span data-stu-id="05859-108">XMPP Gateways for Skype for Business Server</span></span>

<span data-ttu-id="05859-109">Skype for Business Server 2015 とその先行機能により、エッジサーバー上に拡張可能なメッセージングとプレゼンスプロトコル (XMPP) プロキシを構成し、フロントエンドサーバーまたはフロントエンドプールに XMPP ゲートウェイを構成することができました。</span><span class="sxs-lookup"><span data-stu-id="05859-109">Skype for Business Server 2015 and its predecessors allowed you to configure an Extensible Messaging and Presence Protocol (XMPP) proxy on the Edge Server and an XMPP Gateway on the Front End Server or Front End pool.</span></span> <span data-ttu-id="05859-110">この機能は、Skype for Business Server 2019 では使用できなくなりました。</span><span class="sxs-lookup"><span data-stu-id="05859-110">This functionality is no longer available in Skype for Business Server 2019.</span></span>

### <a name="persistent-chat-for-skype-for-business-server"></a><span data-ttu-id="05859-111">Skype for Business Server の常設チャット</span><span class="sxs-lookup"><span data-stu-id="05859-111">Persistent Chat for Skype for Business Server</span></span>

<span data-ttu-id="05859-112">常設チャットサーバーは、組織内の複数のユーザーが時間の経過と共に持続するチャットルームの会話に参加できるようにするオプションの役割です。</span><span class="sxs-lookup"><span data-stu-id="05859-112">Persistent Chat Server is an optional role that lets multiple users in your organization participate in chat room conversations that persist over time.</span></span> <span data-ttu-id="05859-113">常設チャットは、Skype for Business Server 2019 では展開できません。</span><span class="sxs-lookup"><span data-stu-id="05859-113">Persistent chat can't be deployed with Skype for Business Server 2019.</span></span> <span data-ttu-id="05859-114">このサーバーの役割は、トポロジビルダー、およびコードから削除されます。</span><span class="sxs-lookup"><span data-stu-id="05859-114">This server role is removed from Topology Builder, as well as from the code.</span></span> 

<span data-ttu-id="05859-115">Teams でも同じ機能を使用できます。</span><span class="sxs-lookup"><span data-stu-id="05859-115">The same functionality is available in Teams.</span></span> <span data-ttu-id="05859-116">詳細については、「 [Microsoft Teams のアップグレードの概要](/microsoftteams/upgrade-start-here)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="05859-116">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span>

### <a name="sql-mirroring-for-skype-for-business-server"></a><span data-ttu-id="05859-117">Skype for Business Server の SQL ミラーリング</span><span class="sxs-lookup"><span data-stu-id="05859-117">SQL Mirroring for Skype for Business Server</span></span>

<span data-ttu-id="05859-118">SQL ミラーリングは、Skype for Business Server 2019 では展開できません。</span><span class="sxs-lookup"><span data-stu-id="05859-118">SQL Mirroring can't be deployed with Skype for Business Server 2019.</span></span> <span data-ttu-id="05859-119">高可用性と障害復旧を提供するその他のオプションもサポートされていますが、それらの中から選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="05859-119">Other options for providing High Availability and Disaster Recovery are still supported and you should choose from among them.</span></span> <span data-ttu-id="05859-120">オプションを確認するには、「 [Plan for high availability and disaster recovery In Skype For Business Server](../SfbServer/plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="05859-120">See [Plan for high availability and disaster recovery in Skype for Business Server](../SfbServer/plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md) to review the options.</span></span>

### <a name="in-place-upgrades"></a><span data-ttu-id="05859-121">一括アップグレード</span><span class="sxs-lookup"><span data-stu-id="05859-121">In-place upgrades</span></span> 

<span data-ttu-id="05859-122">一括アップグレードは Skype for business Server 2015 で利用できましたが、Skype for Business Server 2019 ではサポートされなくなりました。</span><span class="sxs-lookup"><span data-stu-id="05859-122">In-place upgrades were available in Skype for Business Server 2015 but are no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="05859-123">サイドバイサイドアップグレードと共存使用はサポートされています。詳細については、「 [Skype for business Server 2019 への移行](migration/migration-to-skype-for-business-server-2019.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="05859-123">Side by side upgrade and coexistance is supported, see [Migration to Skype for Business Server 2019](migration/migration-to-skype-for-business-server-2019.md) for more information.</span></span>

### <a name="mobility-service-mcx"></a><span data-ttu-id="05859-124">Mobility Service (Mcx)</span><span class="sxs-lookup"><span data-stu-id="05859-124">Mobility Service (Mcx)</span></span>

<span data-ttu-id="05859-125">従来のモバイルクライアントで使用されていた Mobility Service のサポートは、Skype for Business Server 2019 では利用できなくなりました。</span><span class="sxs-lookup"><span data-stu-id="05859-125">Mobility Service support used by legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="05859-126">これは Skype for Business Server 2015 で既に発表されています。</span><span class="sxs-lookup"><span data-stu-id="05859-126">This was previously announced in Skype for Business Server 2015.</span></span>

<span data-ttu-id="05859-127">現在の Skype for Business mobile クライアントはすべて、既に統合コミュニケーション Web API (UCWA) を使用して、インスタントメッセージング (IM)、プレゼンス、および連絡先をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="05859-127">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="05859-128">Mcx を使用しているレガシクライアントを使用しているユーザーは、現在のクライアントにアップグレードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="05859-128">Users with legacy clients using Mcx will need to upgrade to a current client.</span></span>

<span data-ttu-id="05859-129">詳細については、「skype for business [Server のプランを計画](../SfbServer/plan-your-deployment/mobility.md)する」および「skype for Business[のモバイルクライアント機能の比較](../SfbServer/plan-your-deployment/clients-and-devices/mobile-feature-comparison.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="05859-129">For more details, see [Plan for Mobility for Skype for Business Server](../SfbServer/plan-your-deployment/mobility.md) and [Mobile client feature comparison for Skype for Business](../SfbServer/plan-your-deployment/clients-and-devices/mobile-feature-comparison.md).</span></span>

## <a name="tools"></a><span data-ttu-id="05859-130">ツール</span><span class="sxs-lookup"><span data-stu-id="05859-130">Tools</span></span>

<span data-ttu-id="05859-131">次のツールは、Skype for Business Server 2019 の最初のリリースでは使用できません。</span><span class="sxs-lookup"><span data-stu-id="05859-131">The following tools will not be available for use at the initial release of Skype for Business Server 2019:</span></span>

- <span data-ttu-id="05859-132">Skype for Business Server の容量計画の計算機</span><span class="sxs-lookup"><span data-stu-id="05859-132">Skype for Business Server Capacity Planning Calculator</span></span>
- <span data-ttu-id="05859-133">Skype for Business Server デバッグツール</span><span class="sxs-lookup"><span data-stu-id="05859-133">Skype for Business Server Debugging Tools</span></span>
- <span data-ttu-id="05859-134">Skype for Business Server リソースキットツール (一部のツールは削除されます)</span><span class="sxs-lookup"><span data-stu-id="05859-134">Skype for Business Server Resource Kit Tools (some tools will be removed)</span></span>
    - <span data-ttu-id="05859-135">コール Par・メータ計</span><span class="sxs-lookup"><span data-stu-id="05859-135">Call Parkometer</span></span>
    - <span data-ttu-id="05859-136">参照ユーザーコンソール</span><span class="sxs-lookup"><span data-stu-id="05859-136">Lookup user console</span></span>
    - <span data-ttu-id="05859-137">割り当てられていない番号アナウンスの移行</span><span class="sxs-lookup"><span data-stu-id="05859-137">Unassigned number Announcement Migration</span></span>

<span data-ttu-id="05859-138">次のツールは、Skype for Business Server 2019 ではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="05859-138">The following tools are not supported with Skype for Business Server 2019:</span></span>

- <span data-ttu-id="05859-139">通話品質の方法論 (通話品質ダッシュボードではない)</span><span class="sxs-lookup"><span data-stu-id="05859-139">Call Quality Methodology (but not Call Quality Dashboard)</span></span>
- <span data-ttu-id="05859-140">Microsoft 通話品質の方法スコアカード、v2.0</span><span class="sxs-lookup"><span data-stu-id="05859-140">Microsoft Call Quality Methodology Scorecard, v1.5</span></span>
- <span data-ttu-id="05859-141">Skype for Business Server 2015 計画ツール</span><span class="sxs-lookup"><span data-stu-id="05859-141">Skype for Business Server 2015 Planning Tool</span></span>
- <span data-ttu-id="05859-142">Skype for Business Server 2015 ストレスおよびパフォーマンスツール</span><span class="sxs-lookup"><span data-stu-id="05859-142">Skype for Business Server 2015 Stress and Performance Tool</span></span>

### <a name="see-also"></a><span data-ttu-id="05859-143">関連項目</span><span class="sxs-lookup"><span data-stu-id="05859-143">See also</span></span>

[<span data-ttu-id="05859-144">Skype for Business Server 2019 の新機能</span><span class="sxs-lookup"><span data-stu-id="05859-144">What's new in Skype for Business Server 2019</span></span>](whats-new.md)

[<span data-ttu-id="05859-145">XMPP フェデレーションの移行</span><span class="sxs-lookup"><span data-stu-id="05859-145">Migrating XMPP federation</span></span>](migration/migrating-xmpp-federation.md)
