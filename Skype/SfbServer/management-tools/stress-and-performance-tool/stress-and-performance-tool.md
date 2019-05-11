---
title: Skype for Business Server 2015 Stress and Performance Tool
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
ms.date: 4/6/2016
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: f2f7d19b-18c8-4a41-9b17-80d35b73d742
description: ビジネス サーバー 2015 のストレスおよびパフォーマンス ツールの Skype は、キャパシティ ・ プランニングとパフォーマンス チューニングの非運用環境またはテスト環境で実行中に使用されます。
ms.openlocfilehash: 7705e92c8389e0377e805bd7d8e09aee454d9160
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33904574"
---
# <a name="skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="95fbb-103">Skype for Business Server 2015 Stress and Performance Tool</span><span class="sxs-lookup"><span data-stu-id="95fbb-103">Skype for Business Server 2015 Stress and Performance Tool</span></span>
 
<span data-ttu-id="95fbb-104">ビジネス サーバー 2015 のストレスおよびパフォーマンス ツールの Skype は、キャパシティ ・ プランニングとパフォーマンス チューニングの非運用環境またはテスト環境で実行中に使用されます。</span><span class="sxs-lookup"><span data-stu-id="95fbb-104">The Skype for Business Server 2015 Stress and Performance Tool is used during capacity planning and performance tuning in non-production or test environments.</span></span>
  
<span data-ttu-id="95fbb-105">ビジネス サーバー 2015 のストレスおよびパフォーマンス ツールの Skype には、Skype のビジネス サーバー 2015 計画、容量を簡単にするツールが含まれています。</span><span class="sxs-lookup"><span data-stu-id="95fbb-105">The Skype for Business Server 2015 Stress and Performance Tool includes tools that will simplify your capacity planning for Skype for Business Server 2015.</span></span> <span data-ttu-id="95fbb-106">ビジネス サーバー 2015 のストレスおよびパフォーマンス ツールの Skype は、するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="95fbb-106">The Skype for Business Server 2015 Stress and Performance Tool will help you to:</span></span>
  
- <span data-ttu-id="95fbb-107">Skype ビジネス サーバーの計画、ハードウェアを簡略化します。</span><span class="sxs-lookup"><span data-stu-id="95fbb-107">Simplify your hardware planning for Skype for Business Server</span></span>
    
- <span data-ttu-id="95fbb-108">パフォーマンスをチューニングするための増加する知識とベスト ・ プラクティスを提供します。</span><span class="sxs-lookup"><span data-stu-id="95fbb-108">Give you increased knowledge and best practices for performance tuning</span></span>
    
- <span data-ttu-id="95fbb-109">ビジネス サーバー展開では、Skype のパフォーマンスを測定します。</span><span class="sxs-lookup"><span data-stu-id="95fbb-109">Measure the performance of your Skype for Business Server deployments</span></span>
    
<span data-ttu-id="95fbb-110">トポロジ、および[ビジネス サーバー 2015 容量計画電卓の Skype](../../management-tools/capacity-planning-calculator.md)でトポロジを調整を設計する[ビジネス サーバー 2015 計画ツールの Skype](../../management-tools/planning-tool/planning-tool.md)を使用した後に、このツールを使用するが通常です。</span><span class="sxs-lookup"><span data-stu-id="95fbb-110">You would typically use this tool after you use the [Skype for Business Server 2015 Planning Tool](../../management-tools/planning-tool/planning-tool.md) to design the topology, and refining the topology with the [Skype for Business Server 2015 Capacity Planning Calculator](../../management-tools/capacity-planning-calculator.md).</span></span> 

> [!NOTE]
> <span data-ttu-id="95fbb-111">このツールは、ビジネス サーバー 2019 の Skype は更新されません。</span><span class="sxs-lookup"><span data-stu-id="95fbb-111">This tool will not be updated for Skype for Business Server 2019.</span></span>
  
## <a name="tests"></a><span data-ttu-id="95fbb-112">テスト</span><span class="sxs-lookup"><span data-stu-id="95fbb-112">Tests</span></span>

<span data-ttu-id="95fbb-113">ストレスおよびパフォーマンス ツールは、これらの種類のユーザーの負荷をシミュレートできます。</span><span class="sxs-lookup"><span data-stu-id="95fbb-113">The Stress and Performance Tool can simulate these types of user load:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="95fbb-114">インスタント メッセージング (IM) とプレゼンス</span><span class="sxs-lookup"><span data-stu-id="95fbb-114">Instant Messaging (IM) and presence</span></span>  <br/> |<span data-ttu-id="95fbb-115">電話会議</span><span class="sxs-lookup"><span data-stu-id="95fbb-115">Audio conferencing</span></span>  <br/> |
|<span data-ttu-id="95fbb-116">アプリケーション共有</span><span class="sxs-lookup"><span data-stu-id="95fbb-116">Application sharing</span></span>  <br/> |<span data-ttu-id="95fbb-117">(PTSN) のシミュレーションをボイス オーバー IP (VoIP)、公衆交換電話網を含む</span><span class="sxs-lookup"><span data-stu-id="95fbb-117">Voice over IP (VoIP), including public switched telephone network (PTSN) simulation</span></span>  <br/> |
|<span data-ttu-id="95fbb-118">Web アクセス クライアントの会議</span><span class="sxs-lookup"><span data-stu-id="95fbb-118">Web Access Client conferencing</span></span>  <br/> |<span data-ttu-id="95fbb-119">会議自動アテンダント</span><span class="sxs-lookup"><span data-stu-id="95fbb-119">Conference auto attendant</span></span>  <br/> |
|<span data-ttu-id="95fbb-120">応答グループ</span><span class="sxs-lookup"><span data-stu-id="95fbb-120">Response Groups</span></span>  <br/> |<span data-ttu-id="95fbb-121">配布リストの展開</span><span class="sxs-lookup"><span data-stu-id="95fbb-121">Distribution list expansion</span></span>  <br/> |
|<span data-ttu-id="95fbb-122">アドレス帳のダウンロードやアドレス帳のクエリ</span><span class="sxs-lookup"><span data-stu-id="95fbb-122">Address book download and address book query</span></span>  <br/> |<span data-ttu-id="95fbb-123">強化された 911 (E911) の呼び出しと場所のプロファイル (ダイヤル プラン)</span><span class="sxs-lookup"><span data-stu-id="95fbb-123">Enhanced 911 (E911) calls and location profile (dial plan)</span></span>  <br/> |
|<span data-ttu-id="95fbb-124">マルチビュー</span><span class="sxs-lookup"><span data-stu-id="95fbb-124">MultiView</span></span>  <br/> |<span data-ttu-id="95fbb-125">共同作業データ</span><span class="sxs-lookup"><span data-stu-id="95fbb-125">Data collaboration</span></span>  <br/> |
|<span data-ttu-id="95fbb-126">モビリティ</span><span class="sxs-lookup"><span data-stu-id="95fbb-126">Mobility</span></span>  <br/> ||
   
## <a name="applications-and-files-included-with-the-skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="95fbb-127">アプリケーションや、Skype ビジネス サーバー 2015 のストレスおよびパフォーマンス ツールに含まれるファイル</span><span class="sxs-lookup"><span data-stu-id="95fbb-127">Applications and files included with the Skype for Business Server 2015 Stress and Performance Tool</span></span>

<span data-ttu-id="95fbb-128">これらのアプリケーションは、ビジネス ・ サーバの負荷とパフォーマンス ツールの Skype の一部です。</span><span class="sxs-lookup"><span data-stu-id="95fbb-128">These applications are a part of the Skype for Business Server Stress and Performance Tool:</span></span>
  
|<span data-ttu-id="95fbb-129">**ツール**</span><span class="sxs-lookup"><span data-stu-id="95fbb-129">**Tool**</span></span>|<span data-ttu-id="95fbb-130">**説明**</span><span class="sxs-lookup"><span data-stu-id="95fbb-130">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="95fbb-131">UserProvisioningTool.exe</span><span class="sxs-lookup"><span data-stu-id="95fbb-131">UserProvisioningTool.exe</span></span>  <br/> |<span data-ttu-id="95fbb-132">このツールを使用して、ユーザーおよび連絡先を作成します。</span><span class="sxs-lookup"><span data-stu-id="95fbb-132">This tool is used to create users and contacts.</span></span>  <br/> |
|<span data-ttu-id="95fbb-133">UserProfileGenerator.exe</span><span class="sxs-lookup"><span data-stu-id="95fbb-133">UserProfileGenerator.exe</span></span>  <br/> |<span data-ttu-id="95fbb-134">使用をシミュレートするユーザーの負荷の特性を構成します。</span><span class="sxs-lookup"><span data-stu-id="95fbb-134">Used to configure the characteristics of the user load you're simulating.</span></span>  <br/> |
|<span data-ttu-id="95fbb-135">LyncPerfTool.exe</span><span class="sxs-lookup"><span data-stu-id="95fbb-135">LyncPerfTool.exe</span></span>  <br/> |<span data-ttu-id="95fbb-136">ユーザー ロードをシミュレートするツールです。</span><span class="sxs-lookup"><span data-stu-id="95fbb-136">The tool that simulates user load.</span></span>  <br/> |
|<span data-ttu-id="95fbb-137">Default.tmx</span><span class="sxs-lookup"><span data-stu-id="95fbb-137">Default.tmx</span></span>  <br/> |<span data-ttu-id="95fbb-138">ビジネス サーバー 2015 ログ ツールを Skype を使用する場合に必要です。</span><span class="sxs-lookup"><span data-stu-id="95fbb-138">Required to use the Skype for Business Server 2015 Logging Tool.</span></span>  <br/> |
|<span data-ttu-id="95fbb-139">スクリプトの例を提供</span><span class="sxs-lookup"><span data-stu-id="95fbb-139">Provisioning script examples</span></span>  <br/> |<span data-ttu-id="95fbb-140">特定のシナリオに基づいて、ロード テストを実行するためのトポロジを構成するために使用。</span><span class="sxs-lookup"><span data-stu-id="95fbb-140">Used to configure the topology for running load tests, based on specific scenarios.</span></span> <span data-ttu-id="95fbb-141">特定の環境に関連するようにするように変更する必要があります可能性があります。</span><span class="sxs-lookup"><span data-stu-id="95fbb-141">You'll likely need to modify them to make them relevant for your particular environment.</span></span>  <br/> |
   
## <a name="topics-in-this-section"></a><span data-ttu-id="95fbb-142">このセクションのトピック</span><span class="sxs-lookup"><span data-stu-id="95fbb-142">Topics in this section</span></span>

<span data-ttu-id="95fbb-143">詳細を知りたい場合は、以下の資料を確認してください。</span><span class="sxs-lookup"><span data-stu-id="95fbb-143">You should review the following articles if you need to know more:</span></span>
  
- [<span data-ttu-id="95fbb-144">Skype for Busines Stress and Performance Tool の前提条件と設定</span><span class="sxs-lookup"><span data-stu-id="95fbb-144">Prerequisites and setup for the Skype for Busines Stress and Performance Tool</span></span>](prerequisites-and-setup.md)
    
- [<span data-ttu-id="95fbb-145">ビジネス 2015 のサーバの負荷とパフォーマンス ツールの Skype のパフォーマンスのシナリオ</span><span class="sxs-lookup"><span data-stu-id="95fbb-145">Performance Scenarios for the Skype for Business Server 2015 Stress and Performance Tool</span></span>](scenarios.md)
    
  - [<span data-ttu-id="95fbb-146">ストレスおよびパフォーマンスのシナリオで負荷を実行するのにはトポロジの準備</span><span class="sxs-lookup"><span data-stu-id="95fbb-146">Provisioning the topology to run load in Stress and Performance scenarios</span></span>](provisioning-the-topology-to-run-load.md)
    
  - [<span data-ttu-id="95fbb-147">ビジネス サーバー 2015 のストレスおよびパフォーマンス ツールは、Skype のポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="95fbb-147">Configuring policies for the Skype for Business Server 2015 Stress and Performance Tool</span></span>](configuring-policies.md)
    
- [<span data-ttu-id="95fbb-148">ビジネス サーバー 2015 のストレスおよびパフォーマンス ツールは、Skype を使用します。</span><span class="sxs-lookup"><span data-stu-id="95fbb-148">Using the Skype for Business Server 2015 Stress and Performance Tool</span></span>](using-the-tool.md)
    
- [<span data-ttu-id="95fbb-149">ビジネス 2015 のサーバの負荷とパフォーマンス ツールの Skype のよく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="95fbb-149">FAQ for the Skype for Business Server 2015 Stress and Performance Tool</span></span>](faq.md)
    

