---
title: チームボイスの Contoso のケーススタディ
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 06/17/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: jowrig
search.appverid: MET150
f1.keywords:
- NOCSH
description: 多国籍企業向けの Teams の音声のケーススタディ
appliesto:
- Microsoft Teams
ms.openlocfilehash: 100889bacffdb9de722bd2e1e7295905876dab2e
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/18/2020
ms.locfileid: "44786085"
---
# <a name="contoso-case-study-teams-voice-migration-overview"></a><span data-ttu-id="d168b-103">Contoso のケーススタディ: Teams の音声移行の概要</span><span class="sxs-lookup"><span data-stu-id="d168b-103">Contoso case study: Teams voice migration overview</span></span>

<span data-ttu-id="d168b-104">この記事では、架空の多国籍企業である Contoso が、組織のチームボイスソリューションを実装する方法についてのケーススタディについて説明します。</span><span class="sxs-lookup"><span data-stu-id="d168b-104">This article introduces a case study for how a fictional multi-national corporation, Contoso, implemented a Teams voice solution for their organization.</span></span>

<span data-ttu-id="d168b-105">Contoso は、ネットワーク、id、Windows 10 Enterprise、Office 365 ProPlus、モバイルデバイス管理、情報保護、セキュリティ、Skype for Business から Teams、電話システム、電話会議へのアップグレードなどの、Microsoft 365 Enterprise を展開し、主要設計上の決定と実装の詳細を展開しています。</span><span class="sxs-lookup"><span data-stu-id="d168b-105">Contoso has deployed Microsoft 365 Enterprise and addressed major design decisions and implementation details for the following: networking, identity, Windows 10 Enterprise, Office 365 ProPlus, mobile device management, information protection, security, upgrade from Skype for Business to Teams, Phone System, and Audio Conferencing.</span></span>  

<span data-ttu-id="d168b-106">この記事では、Contoso がオンプレミスユーザーをチームに移行して、統合されたコミュニケーション、コラボレーション、および音声を実現する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d168b-106">This article focuses on how Contoso migrated their on-premises users to Teams for unified communication, collaboration, and voice.</span></span> <span data-ttu-id="d168b-107">Contoso が Microsoft のクラウドサービスを使用してデジタル変換を加速する方法についての背景情報については、「 [contoso のケーススタディの概要」](https://docs.microsoft.com/microsoft-365/enterprise/contoso-case-study?view=o365-worldwide)から始まるすべての主要な記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d168b-107">For background information about how Contoso accelerated their digital transformation by using Microsoft's cloud services, see all the core articles starting with the [Contoso case study overview](https://docs.microsoft.com/microsoft-365/enterprise/contoso-case-study?view=o365-worldwide).</span></span>

https://docs.microsoft.com/microsoft-365/enterprise/contoso-case-study?view=o365-worldwide 

<span data-ttu-id="d168b-108">主要な記事には、次の情報が記載されています。</span><span class="sxs-lookup"><span data-stu-id="d168b-108">In the core articles, you'll find information on the following:</span></span>  

- <span data-ttu-id="d168b-109">Contoso の IT インフラストラクチャのニーズ</span><span class="sxs-lookup"><span data-stu-id="d168b-109">Contoso's IT infrastructure needs</span></span>
- <span data-ttu-id="d168b-110">用</span><span class="sxs-lookup"><span data-stu-id="d168b-110">Networking</span></span>
- <span data-ttu-id="d168b-111">Identity</span><span class="sxs-lookup"><span data-stu-id="d168b-111">Identity</span></span>
- <span data-ttu-id="d168b-112">Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="d168b-112">Windows 10 Enterprise</span></span>
- <span data-ttu-id="d168b-113">Office 365 Pro Plus</span><span class="sxs-lookup"><span data-stu-id="d168b-113">Office 365 Pro Plus</span></span>
- <span data-ttu-id="d168b-114">モバイルデバイス管理</span><span class="sxs-lookup"><span data-stu-id="d168b-114">Mobile device management</span></span>
- <span data-ttu-id="d168b-115">情報の保護</span><span class="sxs-lookup"><span data-stu-id="d168b-115">Information protection</span></span>
- <span data-ttu-id="d168b-116">Microsoft 365 エンタープライズセキュリティの概要</span><span class="sxs-lookup"><span data-stu-id="d168b-116">Summary of Microsoft 365 Enterprise security</span></span>
- <span data-ttu-id="d168b-117">トップ機密プロジェクトのチーム</span><span class="sxs-lookup"><span data-stu-id="d168b-117">Team for a top-secret project</span></span>
- <span data-ttu-id="d168b-118">機密性の高いデジタル資産用の SharePoint Online サイト</span><span class="sxs-lookup"><span data-stu-id="d168b-118">SharePoint Online site for highly confidential digital assets</span></span>

<span data-ttu-id="d168b-119">アップグレードの計画については、「 [Microsoft Teams のアップグレードを開始](upgrade-start-here.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d168b-119">For information about planning an upgrade, you'll want to start with [Getting started with your Microsoft Teams upgrade](upgrade-start-here.md).</span></span>

## <a name="contoso-business-goals-for-teams"></a><span data-ttu-id="d168b-120">チーム向けの Contoso のビジネス目標</span><span class="sxs-lookup"><span data-stu-id="d168b-120">Contoso business goals for Teams</span></span>

<span data-ttu-id="d168b-121">オンプレミスのコミュニケーション、共同作業、および音声のためにチームに移行するために、Contoso は次のビジネス目標を決定しました。</span><span class="sxs-lookup"><span data-stu-id="d168b-121">To migrate their on-premises users to Teams for unified communication, collaboration, and voice, Contoso decided on the following business goals:</span></span>

- <span data-ttu-id="d168b-122">Teams の有効化</span><span class="sxs-lookup"><span data-stu-id="d168b-122">Teams enablement</span></span> 

  <span data-ttu-id="d168b-123">セキュリティで保護された内部と外部のコラボレーションを管理して有効にするための適切なポリシーを備えた、Contoso の統合されたコミュニケーションとコラボレーションチーム。</span><span class="sxs-lookup"><span data-stu-id="d168b-123">Contoso's unified communication and collaboration team enabled Teams with the correct policies to govern and enable secure internal and external collaboration.</span></span> 

- <span data-ttu-id="d168b-124">Skype for Business から Teams へのアップグレード</span><span class="sxs-lookup"><span data-stu-id="d168b-124">Skype for Business to Teams upgrade</span></span> 

  <span data-ttu-id="d168b-125">Skype for Business は Contoso 内で広く展開されました。</span><span class="sxs-lookup"><span data-stu-id="d168b-125">Skype for Business was widely deployed within Contoso.</span></span> <span data-ttu-id="d168b-126">従来のシステムから移行する必要があるため、Contoso は、Skype for Business ユーザーを Teams にアップグレードすることを決定しました。</span><span class="sxs-lookup"><span data-stu-id="d168b-126">With the need to move off legacy systems, Contoso decided to upgrade their Skype for Business users to Teams.</span></span> <span data-ttu-id="d168b-127">詳細については、「 [Contoso のケーススタディ: Teams アップグレード計画](voice-case-study-migration-plan.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d168b-127">For more information, see [Contoso case study: Teams upgrade plan](voice-case-study-migration-plan.md).</span></span>

- <span data-ttu-id="d168b-128">電話システム</span><span class="sxs-lookup"><span data-stu-id="d168b-128">Phone System</span></span>  

  <span data-ttu-id="d168b-129">エンタープライズ voip での Skype for Business は、Contoso 内で広く展開されました。</span><span class="sxs-lookup"><span data-stu-id="d168b-129">Skype for Business with enterprise voice was widely deployed within Contoso.</span></span> <span data-ttu-id="d168b-130">仲介サーバーの次ホップであったレガシシステムをオフにする必要がある場合、Contoso は Skype for Business エンタープライズボイスユーザーを電話システムに移行しました。</span><span class="sxs-lookup"><span data-stu-id="d168b-130">With the need to move off legacy systems that were the next hop for their mediation servers, Contoso migrated their Skype for Business enterprise voice users to Phone System.</span></span> <span data-ttu-id="d168b-131">Contoso サイトでは、Microsoft 通話プラン、電話システムダイレクトルーティング、または両方の組み合わせを使用しました。</span><span class="sxs-lookup"><span data-stu-id="d168b-131">Contoso sites used Microsoft Calling Plan, Phone System Direct Routing, or a combination of both.</span></span> <span data-ttu-id="d168b-132">詳細については、「 [Contoso のケーススタディ: 電話システム](voice-case-study-phone-system.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d168b-132">For more information, see [Contoso case study: Phone System](voice-case-study-phone-system.md).</span></span>

- <span data-ttu-id="d168b-133">場所に基づくルーティング</span><span class="sxs-lookup"><span data-stu-id="d168b-133">Location-Based Routing</span></span> 

  <span data-ttu-id="d168b-134">Office の所在地が電話で規制されている国の場合、Contoso は、電話システムの展開時に Skype for Business に含まれていた場所に基づくルーティングを再作成する必要がありました。</span><span class="sxs-lookup"><span data-stu-id="d168b-134">With office locations in telephony-regulated countries, Contoso needed to recreate the Location-Based Routing that was present in Skype for Business in their Phone System deployment.</span></span> <span data-ttu-id="d168b-135">詳細については、「 [Contoso のケーススタディ: 位置情報に基づくルーティング](voice-case-study-location-based-routing.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d168b-135">For more information, see [Contoso case study: Location-Based Routing](voice-case-study-location-based-routing.md).</span></span>

- <span data-ttu-id="d168b-136">緊急通話</span><span class="sxs-lookup"><span data-stu-id="d168b-136">Emergency Calling</span></span> 

  <span data-ttu-id="d168b-137">直接ルーティングが実装されている場合、Contoso は承認されたサードパーティとの緊急電話を設定します。</span><span class="sxs-lookup"><span data-stu-id="d168b-137">Where Direct Routing was implemented, Contoso set up emergency calling with approved third parties.</span></span> <span data-ttu-id="d168b-138">詳細については、「 [Contoso のケーススタディ: 緊急通話](voice-case-study-emergency-calling.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d168b-138">For more information, see [Contoso case study: Emergency Calling](voice-case-study-emergency-calling.md).</span></span>

- <span data-ttu-id="d168b-139">電話会議</span><span class="sxs-lookup"><span data-stu-id="d168b-139">Audio Conferencing</span></span> 

  <span data-ttu-id="d168b-140">Contoso は、SIP トランクでホストされていた電話会議サービス番号を PSTN プロバイダーに設定します。</span><span class="sxs-lookup"><span data-stu-id="d168b-140">Contoso set up Audio Conferencing service numbers that were hosted on their SIP trunk to their PSTN provider.</span></span> <span data-ttu-id="d168b-141">詳細については、「 [Contoso のケーススタディ: 電話会議](voice-case-study-audio-conferencing.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d168b-141">For more information, see [Contoso case study: Audio Conferencing](voice-case-study-audio-conferencing.md).</span></span> 

- <span data-ttu-id="d168b-142">ローカルメディアの最適化</span><span class="sxs-lookup"><span data-stu-id="d168b-142">Local Media Optimization</span></span> 

  <span data-ttu-id="d168b-143">Contoso は、リモートサイトで利用されていた1つの直接ルートトランクが Microsoft 電話システムにある場所で、ローカルメディア最適化を利用しました。</span><span class="sxs-lookup"><span data-stu-id="d168b-143">Contoso took advantage of Local Media Optimization in locations where they had one direct route trunk to Microsoft Phone System that was leveraged by remote sites.</span></span> <span data-ttu-id="d168b-144">詳細については、「[ローカルメディア最適化の計画](direct-routing-media-optimization.md)」および「[ローカルメディア最適化の構成](direct-routing-media-optimization-configure.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d168b-144">For more information, see [Plan for Local Media Optimization](direct-routing-media-optimization.md) and [Configure Local Media Optimization](direct-routing-media-optimization-configure.md).</span></span>

- <span data-ttu-id="d168b-145">自動応答と通話キュー</span><span class="sxs-lookup"><span data-stu-id="d168b-145">Auto Attendants and Call Queues</span></span>

  <span data-ttu-id="d168b-146">Covid-19 の結果として、Contoso は、スタッフがリモートで作業している間、受付サポートを提供することを希望していました。</span><span class="sxs-lookup"><span data-stu-id="d168b-146">As a result of Covid-19, Contoso wanted to provide receptionist support while their staff was working remotely.</span></span> <span data-ttu-id="d168b-147">Contoso は自動応答と通話キューを使って、受付者の電話番号への着信通話を管理していました。</span><span class="sxs-lookup"><span data-stu-id="d168b-147">Contoso used auto attendants and call queues to manage incoming calls to their receptionist's phone number.</span></span> <span data-ttu-id="d168b-148">詳細については、「 [Contoso のケーススタディ: 自動応答と通話キュー](voice-case-study-call-queues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d168b-148">For more information, see [Contoso case study: Auto Attendants and Call Queues](voice-case-study-call-queues.md).</span></span>  


