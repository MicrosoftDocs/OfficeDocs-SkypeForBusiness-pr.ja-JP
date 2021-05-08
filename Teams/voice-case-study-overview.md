---
title: Teams Contoso のケース スタディ
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 06/17/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
- m365solution-voice
ms.reviewer: jowrig
search.appverid: MET150
f1.keywords:
- NOCSH
description: Teams企業向け音声ケース スタディ
appliesto:
- Microsoft Teams
ms.openlocfilehash: 19200ec5ab1556b0f2b4fda2f389e60bc236015b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51097493"
---
# <a name="contoso-case-study-teams-voice-migration-overview"></a><span data-ttu-id="10a83-103">Contoso のケース スタディ: Teams移行の概要</span><span class="sxs-lookup"><span data-stu-id="10a83-103">Contoso case study: Teams voice migration overview</span></span>

<span data-ttu-id="10a83-104">この記事では、架空の多国籍企業 Contoso が組織に対して音声ソリューションを実装Teamsケース スタディを紹介します。</span><span class="sxs-lookup"><span data-stu-id="10a83-104">This article introduces a case study for how a fictional multi-national corporation, Contoso, implemented a Teams voice solution for their organization.</span></span>

<span data-ttu-id="10a83-105">Contoso は Microsoft 365 Enterprise を展開し、ネットワーク、ID、Windows 10 Enterprise、Office 365 ProPlus、モバイル デバイス管理、情報保護、セキュリティ、Skype for Business から Teams、電話システム、電話会議へのアップグレードに関する主要な設計上の決定と実装の詳細に対処しました。</span><span class="sxs-lookup"><span data-stu-id="10a83-105">Contoso has deployed Microsoft 365 Enterprise and addressed major design decisions and implementation details for the following: networking, identity, Windows 10 Enterprise, Office 365 ProPlus, mobile device management, information protection, security, upgrade from Skype for Business to Teams, Phone System, and Audio Conferencing.</span></span>  

<span data-ttu-id="10a83-106">この記事では、Contoso がオンプレミスのユーザーを統合コミュニケーション、コラボレーション、音声Teamsに移行した方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="10a83-106">This article focuses on how Contoso migrated their on-premises users to Teams for unified communication, collaboration, and voice.</span></span> <span data-ttu-id="10a83-107">Contoso が Microsoft のクラウド サービスを使用してデジタル変革を加速した背景情報については、Contoso のケース スタディの概要から始まるすべての主要な記事 [を参照してください](/microsoft-365/enterprise/contoso-case-study?view=o365-worldwide)。</span><span class="sxs-lookup"><span data-stu-id="10a83-107">For background information about how Contoso accelerated their digital transformation by using Microsoft's cloud services, see all the core articles starting with the [Contoso case study overview](/microsoft-365/enterprise/contoso-case-study?view=o365-worldwide).</span></span>

https://docs.microsoft.com/microsoft-365/enterprise/contoso-case-study?view=o365-worldwide 

<span data-ttu-id="10a83-108">主要な記事では、次の情報を確認できます。</span><span class="sxs-lookup"><span data-stu-id="10a83-108">In the core articles, you'll find information on the following:</span></span>  

- <span data-ttu-id="10a83-109">Contoso の IT インフラストラクチャのニーズ</span><span class="sxs-lookup"><span data-stu-id="10a83-109">Contoso's IT infrastructure needs</span></span>
- <span data-ttu-id="10a83-110">ネットワーク</span><span class="sxs-lookup"><span data-stu-id="10a83-110">Networking</span></span>
- <span data-ttu-id="10a83-111">Identity</span><span class="sxs-lookup"><span data-stu-id="10a83-111">Identity</span></span>
- <span data-ttu-id="10a83-112">Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="10a83-112">Windows 10 Enterprise</span></span>
- <span data-ttu-id="10a83-113">Office 365 Pro Plus</span><span class="sxs-lookup"><span data-stu-id="10a83-113">Office 365 Pro Plus</span></span>
- <span data-ttu-id="10a83-114">モバイル デバイスの管理</span><span class="sxs-lookup"><span data-stu-id="10a83-114">Mobile device management</span></span>
- <span data-ttu-id="10a83-115">情報保護</span><span class="sxs-lookup"><span data-stu-id="10a83-115">Information protection</span></span>
- <span data-ttu-id="10a83-116">セキュリティのMicrosoft 365 Enterprise概要</span><span class="sxs-lookup"><span data-stu-id="10a83-116">Summary of Microsoft 365 Enterprise security</span></span>
- <span data-ttu-id="10a83-117">トップシークレット プロジェクトのチーム</span><span class="sxs-lookup"><span data-stu-id="10a83-117">Team for a top-secret project</span></span>
- <span data-ttu-id="10a83-118">SharePoint機密性の高いデジタル資産のオンライン サイト</span><span class="sxs-lookup"><span data-stu-id="10a83-118">SharePoint Online site for highly confidential digital assets</span></span>

<span data-ttu-id="10a83-119">アップグレードの計画については、アップグレードの概要に関するMicrosoft Teams[があります](upgrade-start-here.md)。</span><span class="sxs-lookup"><span data-stu-id="10a83-119">For information about planning an upgrade, you'll want to start with [Getting started with your Microsoft Teams upgrade](upgrade-start-here.md).</span></span>

## <a name="contoso-business-goals-for-teams"></a><span data-ttu-id="10a83-120">Contoso のビジネス目標Teams</span><span class="sxs-lookup"><span data-stu-id="10a83-120">Contoso business goals for Teams</span></span>

<span data-ttu-id="10a83-121">Contoso は、統合された通信、コラボレーション、音声Teamsにオンプレミス ユーザーを移行するために、次のビジネス目標を決定しました。</span><span class="sxs-lookup"><span data-stu-id="10a83-121">To migrate their on-premises users to Teams for unified communication, collaboration, and voice, Contoso decided on the following business goals:</span></span>

- <span data-ttu-id="10a83-122">Teams有効化</span><span class="sxs-lookup"><span data-stu-id="10a83-122">Teams enablement</span></span> 

  <span data-ttu-id="10a83-123">Contoso の統合されたコミュニケーションおよびコラボレーション チームは、Teamsおよび外部のコラボレーションを管理し、有効にする適切なポリシーを使用して統合を有効にしました。</span><span class="sxs-lookup"><span data-stu-id="10a83-123">Contoso's unified communication and collaboration team enabled Teams with the correct policies to govern and enable secure internal and external collaboration.</span></span> 

- <span data-ttu-id="10a83-124">Skype for Business から Teams へのアップグレード</span><span class="sxs-lookup"><span data-stu-id="10a83-124">Skype for Business to Teams upgrade</span></span> 

  <span data-ttu-id="10a83-125">Skype for Business Contoso 内に広く展開されました。</span><span class="sxs-lookup"><span data-stu-id="10a83-125">Skype for Business was widely deployed within Contoso.</span></span> <span data-ttu-id="10a83-126">レガシ システムから移行する必要がある場合、Contoso はユーザーを新しいシステムにSkype for BusinessアップグレードTeams。</span><span class="sxs-lookup"><span data-stu-id="10a83-126">With the need to move off legacy systems, Contoso decided to upgrade their Skype for Business users to Teams.</span></span> <span data-ttu-id="10a83-127">詳細については、「Contoso のケース[スタディ: アップグレード プランTeams参照してください](voice-case-study-migration-plan.md)。</span><span class="sxs-lookup"><span data-stu-id="10a83-127">For more information, see [Contoso case study: Teams upgrade plan](voice-case-study-migration-plan.md).</span></span>

- <span data-ttu-id="10a83-128">電話システム</span><span class="sxs-lookup"><span data-stu-id="10a83-128">Phone System</span></span>  

  <span data-ttu-id="10a83-129">Skype for Businessは、Contoso 内に広く展開されました。</span><span class="sxs-lookup"><span data-stu-id="10a83-129">Skype for Business with enterprise voice was widely deployed within Contoso.</span></span> <span data-ttu-id="10a83-130">仲介サーバーの次ホップであるレガシ システムから移行する必要がある場合、Contoso はエンタープライズ音声ユーザーをSkype for Businessに移行電話システム。</span><span class="sxs-lookup"><span data-stu-id="10a83-130">With the need to move off legacy systems that were the next hop for their mediation servers, Contoso migrated their Skype for Business enterprise voice users to Phone System.</span></span> <span data-ttu-id="10a83-131">Contoso サイトでは、Microsoft 通話プラン、電話システムルーティング、または両方の組み合わせを使用しました。</span><span class="sxs-lookup"><span data-stu-id="10a83-131">Contoso sites used Microsoft Calling Plan, Phone System Direct Routing, or a combination of both.</span></span> <span data-ttu-id="10a83-132">詳細については、「Contoso のケース[スタディ: 電話システム」 を参照してください](voice-case-study-phone-system.md)。</span><span class="sxs-lookup"><span data-stu-id="10a83-132">For more information, see [Contoso case study: Phone System](voice-case-study-phone-system.md).</span></span>

- <span data-ttu-id="10a83-133">場所に基づくルーティング</span><span class="sxs-lookup"><span data-stu-id="10a83-133">Location-Based Routing</span></span> 

  <span data-ttu-id="10a83-134">テレフォニー規制対象国のオフィスの場所では、Contoso は、Location-Based の展開で Skype for Business に存在する 電話システム ルーティングを再作成する必要がありました。</span><span class="sxs-lookup"><span data-stu-id="10a83-134">With office locations in telephony-regulated countries, Contoso needed to recreate the Location-Based Routing that was present in Skype for Business in their Phone System deployment.</span></span> <span data-ttu-id="10a83-135">詳細については、「Contoso のケース [スタディ: ルーティングのLocation-Based参照してください](voice-case-study-location-based-routing.md)。</span><span class="sxs-lookup"><span data-stu-id="10a83-135">For more information, see [Contoso case study: Location-Based Routing](voice-case-study-location-based-routing.md).</span></span>

- <span data-ttu-id="10a83-136">緊急通話</span><span class="sxs-lookup"><span data-stu-id="10a83-136">Emergency Calling</span></span> 

  <span data-ttu-id="10a83-137">直接ルーティングが実装された場所で、Contoso は承認されたサード パーティとの緊急通話を設定しました。</span><span class="sxs-lookup"><span data-stu-id="10a83-137">Where Direct Routing was implemented, Contoso set up emergency calling with approved third parties.</span></span> <span data-ttu-id="10a83-138">詳細については、「Contoso のケース [スタディ: 緊急通話」を参照してください](voice-case-study-emergency-calling.md)。</span><span class="sxs-lookup"><span data-stu-id="10a83-138">For more information, see [Contoso case study: Emergency Calling](voice-case-study-emergency-calling.md).</span></span>

- <span data-ttu-id="10a83-139">電話会議</span><span class="sxs-lookup"><span data-stu-id="10a83-139">Audio Conferencing</span></span> 

  <span data-ttu-id="10a83-140">Contoso は、SIP トランクでホストされた電話会議サービス番号を PSTN プロバイダーに設定します。</span><span class="sxs-lookup"><span data-stu-id="10a83-140">Contoso set up Audio Conferencing service numbers that were hosted on their SIP trunk to their PSTN provider.</span></span> <span data-ttu-id="10a83-141">詳細については、「Contoso のケース [スタディ: 電話会議」を参照してください](voice-case-study-audio-conferencing.md)。</span><span class="sxs-lookup"><span data-stu-id="10a83-141">For more information, see [Contoso case study: Audio Conferencing](voice-case-study-audio-conferencing.md).</span></span> 

- <span data-ttu-id="10a83-142">ローカル メディアの最適化</span><span class="sxs-lookup"><span data-stu-id="10a83-142">Local Media Optimization</span></span> 

  <span data-ttu-id="10a83-143">Contoso は、リモート サイトで利用された Microsoft 電話 システムへの 1 つの直接ルート トランクを持つ場所で、ローカル メディアの最適化を利用しました。</span><span class="sxs-lookup"><span data-stu-id="10a83-143">Contoso took advantage of Local Media Optimization in locations where they had one direct route trunk to Microsoft Phone System that was leveraged by remote sites.</span></span> <span data-ttu-id="10a83-144">詳細については、「ローカル メディアの最適化 [を計画する」](direct-routing-media-optimization.md) および「ローカル メディアの最適化 [を構成する」を参照してください](direct-routing-media-optimization-configure.md)。</span><span class="sxs-lookup"><span data-stu-id="10a83-144">For more information, see [Plan for Local Media Optimization](direct-routing-media-optimization.md) and [Configure Local Media Optimization](direct-routing-media-optimization-configure.md).</span></span>

- <span data-ttu-id="10a83-145">自動応答と通話キュー</span><span class="sxs-lookup"><span data-stu-id="10a83-145">Auto Attendants and Call Queues</span></span>

  <span data-ttu-id="10a83-146">Covid-19 の結果、Contoso はスタッフがリモートで作業している間に受付のサポートを提供したいと考えたのです。</span><span class="sxs-lookup"><span data-stu-id="10a83-146">As a result of Covid-19, Contoso wanted to provide receptionist support while their staff was working remotely.</span></span> <span data-ttu-id="10a83-147">Contoso は、自動応答と通話キューを使用して、受付の電話番号への着信通話を管理しました。</span><span class="sxs-lookup"><span data-stu-id="10a83-147">Contoso used auto attendants and call queues to manage incoming calls to their receptionist's phone number.</span></span> <span data-ttu-id="10a83-148">詳細については、「Contoso のケース [スタディ: 自動応答と通話キュー」を参照してください](voice-case-study-call-queues.md)。</span><span class="sxs-lookup"><span data-stu-id="10a83-148">For more information, see [Contoso case study: Auto Attendants and Call Queues](voice-case-study-call-queues.md).</span></span>