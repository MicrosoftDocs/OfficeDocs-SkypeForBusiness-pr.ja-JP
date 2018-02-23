---
title: "Microsoft Teams の導入に向けて現在の Skype for Business 環境を最適化する"
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "Skype for Business から Microsoft Teams への移行を開始するためのガイダンス"
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: cb34e60e913926db1ddd6d71ea8a7d1c0d070cd2
ms.sourcegitcommit: 4b69ae91de3f82912eda3513cec65ae12e1ce2b2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2018
---
<a name="optimize-your-current-skype-for-business-environment-for-microsoft-teams"></a><span data-ttu-id="e416c-103">Microsoft Teams の導入に向けて現在の Skype for Business 環境を最適化する</span><span class="sxs-lookup"><span data-stu-id="e416c-103">Optimize your current Skype for Business environment for Microsoft Teams</span></span>
==============================================================

<span data-ttu-id="e416c-104">変更を実現するには時間がかかります。</span><span class="sxs-lookup"><span data-stu-id="e416c-104">Change takes time.</span></span> <span data-ttu-id="e416c-105">組織は、展開ライフサイクル、リソース計画、技術的な準備状況、変更管理を考慮しなければなりません。</span><span class="sxs-lookup"><span data-stu-id="e416c-105">Your organization has deployment lifecycles, resource planning, technical readiness and change management to consider.</span></span> <span data-ttu-id="e416c-106">Microsoft は、Microsoft Teams がお客様の長期的な成功の実現に合致するよう最大限の取り組みを行っています。</span><span class="sxs-lookup"><span data-stu-id="e416c-106">We are working hard to ensure Microsoft Teams meets your needs for long-term success.</span></span> <span data-ttu-id="e416c-107">弊社がこうした取り組みに注力する一方で、お客様は Teams の実装に向けた次のような準備を今すぐ開始することができます。</span><span class="sxs-lookup"><span data-stu-id="e416c-107">While we work to get things ready for you, here are a few ways you can get started with your preparations today.</span></span> <span data-ttu-id="e416c-108">このガイダンスを完了することで、組織内での Teams の実装を成功に導くことができます。</span><span class="sxs-lookup"><span data-stu-id="e416c-108">By completing this guidance, you can drive a successful Teams implementation within your organization.</span></span>

## <a name="environmental-readiness"></a><span data-ttu-id="e416c-109">環境の準備</span><span class="sxs-lookup"><span data-stu-id="e416c-109">Environmental readiness</span></span>


<span data-ttu-id="e416c-110">以下のガイダンスを使用して、Teams の実装が確実に正常に完了するようにします。</span><span class="sxs-lookup"><span data-stu-id="e416c-110">The guidance below should be used to ensure a successful and healthy Teams implementation.</span></span> <span data-ttu-id="e416c-111">このガイダンスは、Teams の展開の準備に向け、現在の Skype for Business 環境を検証する場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="e416c-111">This guidance will help validate your current Skype for Business environment to prepare for your Teams deployment.</span></span>   


### <a name="network-readiness-assessment"></a><span data-ttu-id="e416c-112">ネットワークの準備状況の評価</span><span class="sxs-lookup"><span data-stu-id="e416c-112">Network readiness assessment</span></span>


<span data-ttu-id="e416c-113">Teams などのリアルタイム通信製品を実装する前に *Network Readiness Assessment (ネットワークの準備状況の評価)* を実施する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e416c-113">You should perform a *Network Readiness Assessment* before implementing any real-time communications product such as Teams.</span></span> <span data-ttu-id="e416c-114">*Network Readiness Assessment (ネットワークの準備状況の評価)* では、ネットワーク パフォーマンス、ネットワーク計画、開く必要のあるポートやプロトコルといったその他の一般的なネットワーキング要素に焦点が当てられます。</span><span class="sxs-lookup"><span data-stu-id="e416c-114">A *Network Readiness Assessment* focuses on network performance, network planning, and other general networking aspects such as ports and protocols that must be opened.</span></span> <span data-ttu-id="e416c-115">Skype for Business などのリアルタイム通信製品を既に使用している場合でも、*Network Readiness Assessment (ネットワークの準備状況の評価)* を実施することでネットワークの準備状況を把握することができます。</span><span class="sxs-lookup"><span data-stu-id="e416c-115">Even if you are currently using a real-time communications product, such as Skype for Business, the *Network Readiness Assessment* will help validate your network readiness.</span></span>

<span data-ttu-id="e416c-116">「[Network Readiness Assessment (ネットワークの準備状況の評価)](https://go.microsoft.com/fwlink/?linkid=859069)」ガイドを入手してください。</span><span class="sxs-lookup"><span data-stu-id="e416c-116">Get the [Network Readiness Assessment](https://go.microsoft.com/fwlink/?linkid=859069) guide.</span></span>

### <a name="my-advisor"></a><span data-ttu-id="e416c-117">My Advisor</span><span class="sxs-lookup"><span data-stu-id="e416c-117">My Advisor</span></span>


<span data-ttu-id="e416c-118">導入行程全体を通して、[My Advisor](http://aka.ms/myadvisor) の実践的なガイダンスを利用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="e416c-118">Throughout your journey, we recommend the practical guidance you'll find in [My Advisor](http://aka.ms/myadvisor).</span></span> <span data-ttu-id="e416c-119">My Advisor は、運用の成功に欠かせない Teams と Skype for Business Online の計画と管理で利用できる包括的なセルフサービス ガイドおよびツールセットです。</span><span class="sxs-lookup"><span data-stu-id="e416c-119">My Advisor is a comprehensive, self-service guide and toolset for planning and managing Teams and Skype for Business Online for operational success.</span></span>


### <a name="quality-assessment"></a><span data-ttu-id="e416c-120">品質評価</span><span class="sxs-lookup"><span data-stu-id="e416c-120">Quality assessment</span></span>


<span data-ttu-id="e416c-121">ユーザーを Teams の使用に関与させる前に、現在の Skype for Business の展開がリアルタイム メディアとしての品質基準を満たしているかどうかを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e416c-121">Before you start onboarding your users to Teams, make sure that your current Skype for Business deployment meets the quality bar when it comes to real-time media.</span></span> <span data-ttu-id="e416c-122">通話品質ダッシュボード (CQD) を使用して、使用量の監視や品質傾向の特定を行い、通話分析を使用してトラブルシューティングや個々の通話の品質インジケータの確認を行います。</span><span class="sxs-lookup"><span data-stu-id="e416c-122">Use Call Quality Dashboard (CQD) to monitor usage and identify quality trends and Call Analytics to troubleshoot or look at quality indicators of individual calls.</span></span>

<span data-ttu-id="e416c-123">通話品質ダッシュボードを使用してメディア品質を調査する方法については、「[CQD videos (CQD ビデオ)](https://www.skypeoperationsframework.com/Academy?SOFTrainings=Leverage%20the%20Investigate%20Media%20Quality%20using%20CQD%20Videos)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="e416c-123">Watch the [CQD videos](https://www.skypeoperationsframework.com/Academy?SOFTrainings=Leverage%20the%20Investigate%20Media%20Quality%20using%20CQD%20Videos) for guidance on how to use Call Quality Dashboard to investigate media quality.</span></span>

<span data-ttu-id="e416c-124">通話分析について詳しくは、「[Skype for Business Call Analytics (Skype for Business の通話分析)](https://support.office.com/article/Set-up-Skype-for-Business-Call-Analytics-fbf7247a-84ae-46cc-9204-2c45b1c734cd)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="e416c-124">To learn more about Call Analytics, go to [Skype for Business Call Analytics](https://support.office.com/article/Set-up-Skype-for-Business-Call-Analytics-fbf7247a-84ae-46cc-9204-2c45b1c734cd).</span></span>

### <a name="quality-champion-role"></a><span data-ttu-id="e416c-125">品質チャンピオンの役割</span><span class="sxs-lookup"><span data-stu-id="e416c-125">Quality champion role</span></span>


<span data-ttu-id="e416c-126">組織は、品質チャンピオンの役割を担うユーザーまたはグループを特定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e416c-126">Organizations should identify a person, or group of people, for the role of Quality Champion.</span></span> <span data-ttu-id="e416c-127">品質チャンピオンは、使用量に照らし合わせて品質メトリックスを確認し、品質の傾向や向上が必要な領域を特定します。</span><span class="sxs-lookup"><span data-stu-id="e416c-127">The quality champion reviews quality metrics against usage, identifying quality trends and areas for improvement.</span></span>

<span data-ttu-id="e416c-128">品質チャンピオンは通話品質に関連する問題が発生したときに頼りになる存在です。また、現在の使用量や品質傾向を確認し、実施項目を特定することで品質の問題を識別する領域の専門家 (SME) としての役割を持ちます。</span><span class="sxs-lookup"><span data-stu-id="e416c-128">The quality champion is the go-to person for any call quality related issues and should act as the subject matter expert (SME) for the identification of quality issues by reviewing ongoing usage and quality trends and identifying action items.</span></span> <span data-ttu-id="e416c-129">品質チャンピオンは対応チームと協力して修復アクションを促し、その進捗状況や未解決案件を運営委員会に報告します。</span><span class="sxs-lookup"><span data-stu-id="e416c-129">The quality champion should work with the respective teams to drive remediation actions, reporting to a steering committee on the progress and open issues.</span></span> <span data-ttu-id="e416c-130">通常、品質チャンピオンに最適な候補はカスタマー サービスの所有者です。</span><span class="sxs-lookup"><span data-stu-id="e416c-130">The best candidate for the quality champion is typically the customer service owner.</span></span> <span data-ttu-id="e416c-131">組織の規模や複雑さによっては、ユーザー エクスペリエンスに対して情熱を持ち、動向を特定する能力のあるユーザーならば誰でも品質チャンピオンとしての役割を担うことができます。この場合、品質チャンピオンは、修復を促すため、他のチームの協力を可能にする適切なスポンサーシップによってサポートされます。</span><span class="sxs-lookup"><span data-stu-id="e416c-131">Depending on the organization size and complexity, any person who is passionate about user experience and has the skills to identify trends can act as a quality champion, supported by the right level of sponsorship to work with other teams to drive remediation.</span></span>

<span data-ttu-id="e416c-132">品質チャンピオンの概念と品質レビューのツールや手法については、「[Manage a quality and reliable service delivery workshop (高品質および高信頼のサービスを提供するためのワークショップを管理する)](https://go.microsoft.com/fwlink/?linkid=859071)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="e416c-132">Get information on the quality champion concept and the quality review tools and techniques from [Manage a quality and reliable service delivery workshop](https://go.microsoft.com/fwlink/?linkid=859071).</span></span>

## <a name="environmental-dependencies"></a><span data-ttu-id="e416c-133">環境の依存関係</span><span class="sxs-lookup"><span data-stu-id="e416c-133">Environmental dependencies</span></span>


<span data-ttu-id="e416c-134">Teams は、複数の Office 365 サービスの組み合わせを使用するため、これらのサービスの適切な実装と運用に依存します。</span><span class="sxs-lookup"><span data-stu-id="e416c-134">Teams combines multiple Office 365 services and is therefore dependent on the correct implementation and operation of these services.</span></span> <span data-ttu-id="e416c-135">該当するサービスには、SharePoint Online、Exchange Online、OneDrive for Business が含まれます。ただし、それらに限定されません。</span><span class="sxs-lookup"><span data-stu-id="e416c-135">These services include but are not limited to SharePoint Online, Exchange Online, and OneDrive for Business.</span></span>

<span data-ttu-id="e416c-136">これらのサービスは、すべてが必要なわけではありませんが、実装することを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="e416c-136">While not all services are required it is highly recommended to implement them.</span></span> <span data-ttu-id="e416c-137">実装しないサービスがあると、Teams が組織に提供できる機能に影響が及びます。</span><span class="sxs-lookup"><span data-stu-id="e416c-137">If you choose to not implement certain services, this will impact the functionality that Teams can offer your organization.</span></span> <span data-ttu-id="e416c-138">たとえば、SharePoint Online を実装する必要はありませんが、Teams はグループでのファイル共有などの特定の機能で SharePoint Online に依存します。</span><span class="sxs-lookup"><span data-stu-id="e416c-138">For example, while you are not required to implement SharePoint Online, Teams does rely on SharePoint Online for certain functionality such as file sharing in groups.</span></span> <span data-ttu-id="e416c-139">SharePoint Online を実装しないと、クライアントを介して提供される機能に影響が及びます。</span><span class="sxs-lookup"><span data-stu-id="e416c-139">Not implementing SharePoint Online will affect functionality offered through the client.</span></span>

<span data-ttu-id="e416c-140">要件の詳細については、次の記事をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="e416c-140">Go to the following articles to learn about the requirements:</span></span>
- [<span data-ttu-id="e416c-141">Office 365 グループと Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e416c-141">Office 365 groups and Microsoft Teams </span></span>](Office-365-groups.md)
- [<span data-ttu-id="e416c-142">Microsoft Teams との SharePoint Online と OneDrive for Business の連携</span><span class="sxs-lookup"><span data-stu-id="e416c-142">How SharePoint Online and OneDrive for Business interact with Microsoft Teams</span></span>](SharePoint-OneDrive-interact.md) 
- [<span data-ttu-id="e416c-143">Exchange と Teams の連携</span><span class="sxs-lookup"><span data-stu-id="e416c-143">How Exchange and Teams interact </span></span>](Exchange-Teams-interact.md)



