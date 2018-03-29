---
title: Skype ビジネス 2015 のサーバの負荷およびパフォーマンス ツール
ms.author: heidip
author: microsoftheidi
ms.date: 4/6/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: f2f7d19b-18c8-4a41-9b17-80d35b73d742
description: ビジネス サーバー 2015 のストレスおよびパフォーマンス ツールの Skype は、キャパシティ ・ プランニングとパフォーマンス チューニングの非運用環境またはテスト環境で実行中に使用されます。
ms.openlocfilehash: 0a0a5b17a6e45b2e8944e0e0dd4b3840fc62e102
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="e44b3-103">Skype ビジネス 2015 のサーバの負荷およびパフォーマンス ツール</span><span class="sxs-lookup"><span data-stu-id="e44b3-103">Skype for Business Server 2015 Stress and Performance Tool</span></span>
 
<span data-ttu-id="e44b3-104">ビジネス サーバー 2015 のストレスおよびパフォーマンス ツールの Skype は、キャパシティ ・ プランニングとパフォーマンス チューニングの非運用環境またはテスト環境で実行中に使用されます。</span><span class="sxs-lookup"><span data-stu-id="e44b3-104">The Skype for Business Server 2015 Stress and Performance Tool is used during capacity planning and performance tuning in non-production or test environments.</span></span>
  
<span data-ttu-id="e44b3-105">ビジネス サーバー 2015 のストレスおよびパフォーマンス ツールの Skype には、Skype のビジネス サーバー 2015 計画、容量を簡単にするツールが含まれています。</span><span class="sxs-lookup"><span data-stu-id="e44b3-105">The Skype for Business Server 2015 Stress and Performance Tool includes tools that will simplify your capacity planning for Skype for Business Server 2015.</span></span> <span data-ttu-id="e44b3-106">ビジネス サーバー 2015 のストレスおよびパフォーマンス ツールの Skype は、するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="e44b3-106">The Skype for Business Server 2015 Stress and Performance Tool will help you to:</span></span>
  
- <span data-ttu-id="e44b3-107">Skype ビジネス サーバーの計画、ハードウェアを簡略化します。</span><span class="sxs-lookup"><span data-stu-id="e44b3-107">Simplify your hardware planning for Skype for Business Server</span></span>
    
- <span data-ttu-id="e44b3-108">パフォーマンスをチューニングするための増加する知識とベスト ・ プラクティスを提供します。</span><span class="sxs-lookup"><span data-stu-id="e44b3-108">Give you increased knowledge and best practices for performance tuning</span></span>
    
- <span data-ttu-id="e44b3-109">ビジネス サーバー展開では、Skype のパフォーマンスを測定します。</span><span class="sxs-lookup"><span data-stu-id="e44b3-109">Measure the performance of your Skype for Business Server deployments</span></span>
    
<span data-ttu-id="e44b3-110">トポロジ、および[ビジネス サーバー 2015 容量計画電卓の Skype](../../management-tools/capacity-planning-calculator.md)でトポロジを調整を設計する[ビジネス サーバー 2015 計画ツールの Skype](../../management-tools/planning-tool/planning-tool.md)を使用した後に、このツールを使用するが通常です。</span><span class="sxs-lookup"><span data-stu-id="e44b3-110">You would typically use this tool after you use the [Skype for Business Server 2015 Planning Tool](../../management-tools/planning-tool/planning-tool.md) to design the topology, and refining the topology with the [Skype for Business Server 2015 Capacity Planning Calculator](../../management-tools/capacity-planning-calculator.md).</span></span> 
  
## <a name="tests"></a><span data-ttu-id="e44b3-111">テスト</span><span class="sxs-lookup"><span data-stu-id="e44b3-111">Tests</span></span>

<span data-ttu-id="e44b3-112">ストレスおよびパフォーマンス ツールは、これらの種類のユーザーの負荷をシミュレートできます。</span><span class="sxs-lookup"><span data-stu-id="e44b3-112">The Stress and Performance Tool can simulate these types of user load:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="e44b3-113">インスタント メッセージング (IM) とプレゼンス</span><span class="sxs-lookup"><span data-stu-id="e44b3-113">Instant Messaging (IM) and presence</span></span>  <br/> |<span data-ttu-id="e44b3-114">オーディオ会議</span><span class="sxs-lookup"><span data-stu-id="e44b3-114">Audio conferencing</span></span>  <br/> |
|<span data-ttu-id="e44b3-115">アプリケーション共有</span><span class="sxs-lookup"><span data-stu-id="e44b3-115">Application sharing</span></span>  <br/> |<span data-ttu-id="e44b3-116">(PTSN) のシミュレーションをボイス オーバー IP (VoIP)、公衆交換電話網を含む</span><span class="sxs-lookup"><span data-stu-id="e44b3-116">Voice over IP (VoIP), including public switched telephone network (PTSN) simulation</span></span>  <br/> |
|<span data-ttu-id="e44b3-117">Web アクセス クライアントの会議</span><span class="sxs-lookup"><span data-stu-id="e44b3-117">Web Access Client conferencing</span></span>  <br/> |<span data-ttu-id="e44b3-118">会議自動アテンダント</span><span class="sxs-lookup"><span data-stu-id="e44b3-118">Conference auto attendant</span></span>  <br/> |
|<span data-ttu-id="e44b3-119">応答グループ</span><span class="sxs-lookup"><span data-stu-id="e44b3-119">Response Groups</span></span>  <br/> |<span data-ttu-id="e44b3-120">配布リストの展開</span><span class="sxs-lookup"><span data-stu-id="e44b3-120">Distribution list expansion</span></span>  <br/> |
|<span data-ttu-id="e44b3-121">アドレス帳のダウンロードやアドレス帳のクエリ</span><span class="sxs-lookup"><span data-stu-id="e44b3-121">Address book download and address book query</span></span>  <br/> |<span data-ttu-id="e44b3-122">強化された 911 (E911) の呼び出しと場所のプロファイル (ダイヤル プラン)</span><span class="sxs-lookup"><span data-stu-id="e44b3-122">Enhanced 911 (E911) calls and location profile (dial plan)</span></span>  <br/> |
|<span data-ttu-id="e44b3-123">マルチビュー</span><span class="sxs-lookup"><span data-stu-id="e44b3-123">MultiView</span></span>  <br/> |<span data-ttu-id="e44b3-124">共同作業データ</span><span class="sxs-lookup"><span data-stu-id="e44b3-124">Data collaboration</span></span>  <br/> |
|<span data-ttu-id="e44b3-125">モビリティ</span><span class="sxs-lookup"><span data-stu-id="e44b3-125">Mobility</span></span>  <br/> ||
   
## <a name="applications-and-files-included-with-the-skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="e44b3-126">アプリケーションや、Skype ビジネス サーバー 2015 のストレスおよびパフォーマンス ツールに含まれるファイル</span><span class="sxs-lookup"><span data-stu-id="e44b3-126">Applications and files included with the Skype for Business Server 2015 Stress and Performance Tool</span></span>

<span data-ttu-id="e44b3-127">これらのアプリケーションは、ビジネス ・ サーバの負荷とパフォーマンス ツールの Skype の一部です。</span><span class="sxs-lookup"><span data-stu-id="e44b3-127">These applications are a part of the Skype for Business Server Stress and Performance Tool:</span></span>
  
|<span data-ttu-id="e44b3-128">**ツール**</span><span class="sxs-lookup"><span data-stu-id="e44b3-128">**Tool**</span></span>|<span data-ttu-id="e44b3-129">**説明**</span><span class="sxs-lookup"><span data-stu-id="e44b3-129">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="e44b3-130">UserProvisioningTool.exe</span><span class="sxs-lookup"><span data-stu-id="e44b3-130">UserProvisioningTool.exe</span></span>  <br/> |<span data-ttu-id="e44b3-131">このツールを使用して、ユーザーおよび連絡先を作成します。</span><span class="sxs-lookup"><span data-stu-id="e44b3-131">This tool is used to create users and contacts.</span></span>  <br/> |
|<span data-ttu-id="e44b3-132">UserProfileGenerator.exe</span><span class="sxs-lookup"><span data-stu-id="e44b3-132">UserProfileGenerator.exe</span></span>  <br/> |<span data-ttu-id="e44b3-133">使用をシミュレートするユーザーの負荷の特性を構成します。</span><span class="sxs-lookup"><span data-stu-id="e44b3-133">Used to configure the characteristics of the user load you're simulating.</span></span>  <br/> |
|<span data-ttu-id="e44b3-134">LyncPerfTool.exe</span><span class="sxs-lookup"><span data-stu-id="e44b3-134">LyncPerfTool.exe</span></span>  <br/> |<span data-ttu-id="e44b3-135">ユーザー ロードをシミュレートするツールです。</span><span class="sxs-lookup"><span data-stu-id="e44b3-135">The tool that simulates user load.</span></span>  <br/> |
|<span data-ttu-id="e44b3-136">Default.tmx</span><span class="sxs-lookup"><span data-stu-id="e44b3-136">Default.tmx</span></span>  <br/> |<span data-ttu-id="e44b3-137">ビジネス サーバー 2015 ログ ツールを Skype を使用する場合に必要です。</span><span class="sxs-lookup"><span data-stu-id="e44b3-137">Required to use the Skype for Business Server 2015 Logging Tool.</span></span>  <br/> |
|<span data-ttu-id="e44b3-138">スクリプトの例を提供</span><span class="sxs-lookup"><span data-stu-id="e44b3-138">Provisioning script examples</span></span>  <br/> |<span data-ttu-id="e44b3-139">特定のシナリオに基づいて、ロード テストを実行するためのトポロジを構成するために使用。</span><span class="sxs-lookup"><span data-stu-id="e44b3-139">Used to configure the topology for running load tests, based on specific scenarios.</span></span> <span data-ttu-id="e44b3-140">特定の環境に関連するようにするように変更する必要があります可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e44b3-140">You'll likely need to modify them to make them relevant for your particular environment.</span></span>  <br/> |
   
## <a name="topics-in-this-section"></a><span data-ttu-id="e44b3-141">このセクションのトピック</span><span class="sxs-lookup"><span data-stu-id="e44b3-141">Topics in this section</span></span>

<span data-ttu-id="e44b3-142">詳細を知りたい場合は、以下の資料を確認してください。</span><span class="sxs-lookup"><span data-stu-id="e44b3-142">You should review the following articles if you need to know more:</span></span>
  
- [<span data-ttu-id="e44b3-143">前提条件と、Skype のビジネス用のストレスおよびパフォーマンス ツールのセットアップ</span><span class="sxs-lookup"><span data-stu-id="e44b3-143">Prerequisites and setup for the Skype for Busines Stress and Performance Tool</span></span>](prerequisites-and-setup.md)
    
- [<span data-ttu-id="e44b3-144">ビジネス 2015 のサーバの負荷とパフォーマンス ツールの Skype のパフォーマンスのシナリオ</span><span class="sxs-lookup"><span data-stu-id="e44b3-144">Performance Scenarios for the Skype for Business Server 2015 Stress and Performance Tool</span></span>](scenarios.md)
    
  - [<span data-ttu-id="e44b3-145">ストレスおよびパフォーマンスのシナリオで負荷を実行するのにはトポロジの準備</span><span class="sxs-lookup"><span data-stu-id="e44b3-145">Provisioning the topology to run load in Stress and Performance scenarios</span></span>](provisioning-the-topology-to-run-load.md)
    
  - [<span data-ttu-id="e44b3-146">ビジネス サーバー 2015 のストレスおよびパフォーマンス ツールは、Skype のポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="e44b3-146">Configuring policies for the Skype for Business Server 2015 Stress and Performance Tool</span></span>](configuring-policies.md)
    
- [<span data-ttu-id="e44b3-147">ビジネス サーバー 2015 のストレスおよびパフォーマンス ツールは、Skype を使用します。</span><span class="sxs-lookup"><span data-stu-id="e44b3-147">Using the Skype for Business Server 2015 Stress and Performance Tool</span></span>](using-the-tool.md)
    
- [<span data-ttu-id="e44b3-148">ビジネス 2015 のサーバの負荷とパフォーマンス ツールの Skype のよく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="e44b3-148">FAQ for the Skype for Business Server 2015 Stress and Performance Tool</span></span>](faq.md)
    

