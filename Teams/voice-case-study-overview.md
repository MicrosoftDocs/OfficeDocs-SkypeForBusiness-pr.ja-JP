---
title: Teams の音声 Contoso のケース スタディ
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
description: 多国籍企業向け Teams 音声ケース スタディ
appliesto:
- Microsoft Teams
ms.openlocfilehash: 19200ec5ab1556b0f2b4fda2f389e60bc236015b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51097493"
---
# <a name="contoso-case-study-teams-voice-migration-overview"></a><span data-ttu-id="27b5d-103">Contoso のケース スタディ: Teams 音声移行の概要</span><span class="sxs-lookup"><span data-stu-id="27b5d-103">Contoso case study: Teams voice migration overview</span></span>

<span data-ttu-id="27b5d-104">この記事では、架空の多国籍企業 Contoso が組織に Teams 音声ソリューションを実装した方法について、ケース スタディについて説明します。</span><span class="sxs-lookup"><span data-stu-id="27b5d-104">This article introduces a case study for how a fictional multi-national corporation, Contoso, implemented a Teams voice solution for their organization.</span></span>

<span data-ttu-id="27b5d-105">Contoso は Microsoft 365 Enterprise を展開し、ネットワーク、ID、Windows 10 Enterprise、Office 365 ProPlus、モバイル デバイス管理、情報保護、セキュリティ、Skype for Business から Teams、電話システム、電話会議にアップグレードする主な設計決定と実装の詳細に対応しました。</span><span class="sxs-lookup"><span data-stu-id="27b5d-105">Contoso has deployed Microsoft 365 Enterprise and addressed major design decisions and implementation details for the following: networking, identity, Windows 10 Enterprise, Office 365 ProPlus, mobile device management, information protection, security, upgrade from Skype for Business to Teams, Phone System, and Audio Conferencing.</span></span>  

<span data-ttu-id="27b5d-106">この記事では、Contoso が統合コミュニケーション、コラボレーション、音声のためにオンプレミス ユーザーを Teams に移行した方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="27b5d-106">This article focuses on how Contoso migrated their on-premises users to Teams for unified communication, collaboration, and voice.</span></span> <span data-ttu-id="27b5d-107">Microsoft のクラウド サービスを使用して Contoso がデジタル変換を高速化した方法に関する背景情報については、Contoso のケース スタディの概要から始まる主要なすべての記事 [を参照してください](/microsoft-365/enterprise/contoso-case-study?view=o365-worldwide)。</span><span class="sxs-lookup"><span data-stu-id="27b5d-107">For background information about how Contoso accelerated their digital transformation by using Microsoft's cloud services, see all the core articles starting with the [Contoso case study overview](/microsoft-365/enterprise/contoso-case-study?view=o365-worldwide).</span></span>

https://docs.microsoft.com/microsoft-365/enterprise/contoso-case-study?view=o365-worldwide 

<span data-ttu-id="27b5d-108">主要な記事では、次の情報を参照できます。</span><span class="sxs-lookup"><span data-stu-id="27b5d-108">In the core articles, you'll find information on the following:</span></span>  

- <span data-ttu-id="27b5d-109">Contoso の IT インフラストラクチャのニーズ</span><span class="sxs-lookup"><span data-stu-id="27b5d-109">Contoso's IT infrastructure needs</span></span>
- <span data-ttu-id="27b5d-110">ネットワーク</span><span class="sxs-lookup"><span data-stu-id="27b5d-110">Networking</span></span>
- <span data-ttu-id="27b5d-111">Identity</span><span class="sxs-lookup"><span data-stu-id="27b5d-111">Identity</span></span>
- <span data-ttu-id="27b5d-112">Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="27b5d-112">Windows 10 Enterprise</span></span>
- <span data-ttu-id="27b5d-113">Office 365 Pro Plus</span><span class="sxs-lookup"><span data-stu-id="27b5d-113">Office 365 Pro Plus</span></span>
- <span data-ttu-id="27b5d-114">モバイル デバイス管理</span><span class="sxs-lookup"><span data-stu-id="27b5d-114">Mobile device management</span></span>
- <span data-ttu-id="27b5d-115">情報保護</span><span class="sxs-lookup"><span data-stu-id="27b5d-115">Information protection</span></span>
- <span data-ttu-id="27b5d-116">Microsoft 365 Enterprise セキュリティの概要</span><span class="sxs-lookup"><span data-stu-id="27b5d-116">Summary of Microsoft 365 Enterprise security</span></span>
- <span data-ttu-id="27b5d-117">チームで最高のプロジェクトを作成する</span><span class="sxs-lookup"><span data-stu-id="27b5d-117">Team for a top-secret project</span></span>
- <span data-ttu-id="27b5d-118">機密性の高いデジタル資産の SharePoint Online サイト</span><span class="sxs-lookup"><span data-stu-id="27b5d-118">SharePoint Online site for highly confidential digital assets</span></span>

<span data-ttu-id="27b5d-119">アップグレードの計画については、Microsoft Teams のアップグレードの概要 [から始める必要があります](upgrade-start-here.md)。</span><span class="sxs-lookup"><span data-stu-id="27b5d-119">For information about planning an upgrade, you'll want to start with [Getting started with your Microsoft Teams upgrade](upgrade-start-here.md).</span></span>

## <a name="contoso-business-goals-for-teams"></a><span data-ttu-id="27b5d-120">Teams の Contoso ビジネスの目標</span><span class="sxs-lookup"><span data-stu-id="27b5d-120">Contoso business goals for Teams</span></span>

<span data-ttu-id="27b5d-121">統合されたコミュニケーション、コラボレーション、音声のためにオンプレミス ユーザーを Teams に移行するために、Contoso は次のビジネス目標を決定しました。</span><span class="sxs-lookup"><span data-stu-id="27b5d-121">To migrate their on-premises users to Teams for unified communication, collaboration, and voice, Contoso decided on the following business goals:</span></span>

- <span data-ttu-id="27b5d-122">Teams の有効化</span><span class="sxs-lookup"><span data-stu-id="27b5d-122">Teams enablement</span></span> 

  <span data-ttu-id="27b5d-123">Contoso の統合コミュニケーションとコラボレーション チームは、適切なポリシーを使用して Teams を有効にし、内部と外部の安全なコラボレーションを制御し、有効にしました。</span><span class="sxs-lookup"><span data-stu-id="27b5d-123">Contoso's unified communication and collaboration team enabled Teams with the correct policies to govern and enable secure internal and external collaboration.</span></span> 

- <span data-ttu-id="27b5d-124">Skype for Business から Teams へのアップグレード</span><span class="sxs-lookup"><span data-stu-id="27b5d-124">Skype for Business to Teams upgrade</span></span> 

  <span data-ttu-id="27b5d-125">Skype for Business は Contoso 内に広く展開されました。</span><span class="sxs-lookup"><span data-stu-id="27b5d-125">Skype for Business was widely deployed within Contoso.</span></span> <span data-ttu-id="27b5d-126">従来のシステムから移行する必要がある場合、Contoso は Skype for Business ユーザーを Teams にアップグレードすることを決定しました。</span><span class="sxs-lookup"><span data-stu-id="27b5d-126">With the need to move off legacy systems, Contoso decided to upgrade their Skype for Business users to Teams.</span></span> <span data-ttu-id="27b5d-127">詳細については、「Contoso のケース スタディ: Teams アップグレード [プラン」を参照してください](voice-case-study-migration-plan.md)。</span><span class="sxs-lookup"><span data-stu-id="27b5d-127">For more information, see [Contoso case study: Teams upgrade plan](voice-case-study-migration-plan.md).</span></span>

- <span data-ttu-id="27b5d-128">電話システム</span><span class="sxs-lookup"><span data-stu-id="27b5d-128">Phone System</span></span>  

  <span data-ttu-id="27b5d-129">エンタープライズ ボイス付き Skype for Business は、Contoso 内に広く展開されました。</span><span class="sxs-lookup"><span data-stu-id="27b5d-129">Skype for Business with enterprise voice was widely deployed within Contoso.</span></span> <span data-ttu-id="27b5d-130">仲介サーバーの次のホップである従来のシステムから移行する必要がある場合、Contoso は Skype for Business エンタープライズ 音声ユーザーを電話システムに移行しました。</span><span class="sxs-lookup"><span data-stu-id="27b5d-130">With the need to move off legacy systems that were the next hop for their mediation servers, Contoso migrated their Skype for Business enterprise voice users to Phone System.</span></span> <span data-ttu-id="27b5d-131">Contoso サイトでは、Microsoft 通話プラン、電話システムダイレクト ルーティング、または両方の組み合わせを使用しました。</span><span class="sxs-lookup"><span data-stu-id="27b5d-131">Contoso sites used Microsoft Calling Plan, Phone System Direct Routing, or a combination of both.</span></span> <span data-ttu-id="27b5d-132">詳細については、「Contoso のケース [スタディ: 電話システム」を参照してください](voice-case-study-phone-system.md)。</span><span class="sxs-lookup"><span data-stu-id="27b5d-132">For more information, see [Contoso case study: Phone System](voice-case-study-phone-system.md).</span></span>

- <span data-ttu-id="27b5d-133">場所に基づくルーティング</span><span class="sxs-lookup"><span data-stu-id="27b5d-133">Location-Based Routing</span></span> 

  <span data-ttu-id="27b5d-134">テレフォニーが規制された国のオフィスの場所では、Contoso は電話システムの展開で Skype for Business に存在する Location-Based ルーティングを再作成する必要がありました。</span><span class="sxs-lookup"><span data-stu-id="27b5d-134">With office locations in telephony-regulated countries, Contoso needed to recreate the Location-Based Routing that was present in Skype for Business in their Phone System deployment.</span></span> <span data-ttu-id="27b5d-135">詳細については、「Contoso のケース [スタディ: Location-Based ルーティング」を参照してください](voice-case-study-location-based-routing.md)。</span><span class="sxs-lookup"><span data-stu-id="27b5d-135">For more information, see [Contoso case study: Location-Based Routing](voice-case-study-location-based-routing.md).</span></span>

- <span data-ttu-id="27b5d-136">緊急通話</span><span class="sxs-lookup"><span data-stu-id="27b5d-136">Emergency Calling</span></span> 

  <span data-ttu-id="27b5d-137">直接ルーティングが実装された場合、Contoso は承認された第三者との緊急通話を設定します。</span><span class="sxs-lookup"><span data-stu-id="27b5d-137">Where Direct Routing was implemented, Contoso set up emergency calling with approved third parties.</span></span> <span data-ttu-id="27b5d-138">詳細については、「Contoso のケース [スタディ: 緊急通話」を参照してください](voice-case-study-emergency-calling.md)。</span><span class="sxs-lookup"><span data-stu-id="27b5d-138">For more information, see [Contoso case study: Emergency Calling](voice-case-study-emergency-calling.md).</span></span>

- <span data-ttu-id="27b5d-139">電話会議</span><span class="sxs-lookup"><span data-stu-id="27b5d-139">Audio Conferencing</span></span> 

  <span data-ttu-id="27b5d-140">Contoso は、PSTN プロバイダーに SIP トランクでホストされている電話会議サービス番号を設定します。</span><span class="sxs-lookup"><span data-stu-id="27b5d-140">Contoso set up Audio Conferencing service numbers that were hosted on their SIP trunk to their PSTN provider.</span></span> <span data-ttu-id="27b5d-141">詳細については、「Contoso のケース [スタディ: 電話会議」を参照してください](voice-case-study-audio-conferencing.md)。</span><span class="sxs-lookup"><span data-stu-id="27b5d-141">For more information, see [Contoso case study: Audio Conferencing](voice-case-study-audio-conferencing.md).</span></span> 

- <span data-ttu-id="27b5d-142">ローカル メディアの最適化</span><span class="sxs-lookup"><span data-stu-id="27b5d-142">Local Media Optimization</span></span> 

  <span data-ttu-id="27b5d-143">Contoso は、リモート サイトで利用された Microsoft Phone System への直接ルート トランクが 1 つある場所で、ローカル メディア最適化を利用しました。</span><span class="sxs-lookup"><span data-stu-id="27b5d-143">Contoso took advantage of Local Media Optimization in locations where they had one direct route trunk to Microsoft Phone System that was leveraged by remote sites.</span></span> <span data-ttu-id="27b5d-144">詳細については、「ローカル メディア最適化 [の計画」](direct-routing-media-optimization.md) および「ローカル メディアの最適化 [を構成する」を参照してください](direct-routing-media-optimization-configure.md)。</span><span class="sxs-lookup"><span data-stu-id="27b5d-144">For more information, see [Plan for Local Media Optimization](direct-routing-media-optimization.md) and [Configure Local Media Optimization](direct-routing-media-optimization-configure.md).</span></span>

- <span data-ttu-id="27b5d-145">自動応答と通話キュー</span><span class="sxs-lookup"><span data-stu-id="27b5d-145">Auto Attendants and Call Queues</span></span>

  <span data-ttu-id="27b5d-146">Covid-19 の結果として、Contoso はスタッフがリモートで作業している間、受付のサポートを提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="27b5d-146">As a result of Covid-19, Contoso wanted to provide receptionist support while their staff was working remotely.</span></span> <span data-ttu-id="27b5d-147">Contoso は、受付係の電話番号への着信通話を管理するために、自動応答と通話キューを使用しました。</span><span class="sxs-lookup"><span data-stu-id="27b5d-147">Contoso used auto attendants and call queues to manage incoming calls to their receptionist's phone number.</span></span> <span data-ttu-id="27b5d-148">詳細については、「Contoso のケース [スタディ: 自動応答と通話キュー」を参照してください](voice-case-study-call-queues.md)。</span><span class="sxs-lookup"><span data-stu-id="27b5d-148">For more information, see [Contoso case study: Auto Attendants and Call Queues](voice-case-study-call-queues.md).</span></span>