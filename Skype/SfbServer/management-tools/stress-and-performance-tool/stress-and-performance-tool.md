---
title: Skype for Business Server 2015 Stress and Performance Tool
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
ms.date: 4/6/2016
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: f2f7d19b-18c8-4a41-9b17-80d35b73d742
description: Skype for Business Server 2015 応力とパフォーマンスツールは、非運用環境またはテスト環境でのキャパシティの計画とパフォーマンスのチューニングの際に使用されます。
ms.openlocfilehash: d82d5ed33e6dca1303aed9f49150dd6b56fc4e1a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34299517"
---
# <a name="skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="51f67-103">Skype for Business Server 2015 Stress and Performance Tool</span><span class="sxs-lookup"><span data-stu-id="51f67-103">Skype for Business Server 2015 Stress and Performance Tool</span></span>
 
<span data-ttu-id="51f67-104">Skype for Business Server 2015 応力とパフォーマンスツールは、非運用環境またはテスト環境でのキャパシティの計画とパフォーマンスのチューニングの際に使用されます。</span><span class="sxs-lookup"><span data-stu-id="51f67-104">The Skype for Business Server 2015 Stress and Performance Tool is used during capacity planning and performance tuning in non-production or test environments.</span></span>
  
<span data-ttu-id="51f67-105">Skype for Business Server 2015 のストレスとパフォーマンスのツールには、Skype for Business Server 2015 のキャパシティ計画を簡素化するためのツールが含まれています。</span><span class="sxs-lookup"><span data-stu-id="51f67-105">The Skype for Business Server 2015 Stress and Performance Tool includes tools that will simplify your capacity planning for Skype for Business Server 2015.</span></span> <span data-ttu-id="51f67-106">Skype for Business Server 2015 のストレスとパフォーマンスツールは、次のことを行うのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="51f67-106">The Skype for Business Server 2015 Stress and Performance Tool will help you to:</span></span>
  
- <span data-ttu-id="51f67-107">Skype for Business Server のハードウェア計画を簡素化する</span><span class="sxs-lookup"><span data-stu-id="51f67-107">Simplify your hardware planning for Skype for Business Server</span></span>
    
- <span data-ttu-id="51f67-108">パフォーマンスのチューニングに関する知識とベストプラクティスの強化</span><span class="sxs-lookup"><span data-stu-id="51f67-108">Give you increased knowledge and best practices for performance tuning</span></span>
    
- <span data-ttu-id="51f67-109">Skype for Business Server の展開のパフォーマンスを測定する</span><span class="sxs-lookup"><span data-stu-id="51f67-109">Measure the performance of your Skype for Business Server deployments</span></span>
    
<span data-ttu-id="51f67-110">通常は、 [skype For Business server 2015 計画ツール](../../management-tools/planning-tool/planning-tool.md)を使用してトポロジを設計し、 [Skype for Business Server 2015 キャパシティプランニングの電卓](../../management-tools/capacity-planning-calculator.md)を使用してトポロジを絞り込みた後に、このツールを使用します。</span><span class="sxs-lookup"><span data-stu-id="51f67-110">You would typically use this tool after you use the [Skype for Business Server 2015 Planning Tool](../../management-tools/planning-tool/planning-tool.md) to design the topology, and refining the topology with the [Skype for Business Server 2015 Capacity Planning Calculator](../../management-tools/capacity-planning-calculator.md).</span></span> 

> [!NOTE]
> <span data-ttu-id="51f67-111">このツールは、Skype for Business Server 2019 では更新されません。</span><span class="sxs-lookup"><span data-stu-id="51f67-111">This tool will not be updated for Skype for Business Server 2019.</span></span>
  
## <a name="tests"></a><span data-ttu-id="51f67-112">テスト</span><span class="sxs-lookup"><span data-stu-id="51f67-112">Tests</span></span>

<span data-ttu-id="51f67-113">ストレスとパフォーマンスのツールでは、次の種類のユーザーロードをシミュレートできます。</span><span class="sxs-lookup"><span data-stu-id="51f67-113">The Stress and Performance Tool can simulate these types of user load:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="51f67-114">インスタントメッセージング (IM) とプレゼンス</span><span class="sxs-lookup"><span data-stu-id="51f67-114">Instant Messaging (IM) and presence</span></span>  <br/> |<span data-ttu-id="51f67-115">電話会議</span><span class="sxs-lookup"><span data-stu-id="51f67-115">Audio conferencing</span></span>  <br/> |
|<span data-ttu-id="51f67-116">アプリケーション共有</span><span class="sxs-lookup"><span data-stu-id="51f67-116">Application sharing</span></span>  <br/> |<span data-ttu-id="51f67-117">公衆交換電話網 (PTSN) シミュレーションなどのボイスオーバー IP (VoIP) シミュレーション</span><span class="sxs-lookup"><span data-stu-id="51f67-117">Voice over IP (VoIP), including public switched telephone network (PTSN) simulation</span></span>  <br/> |
|<span data-ttu-id="51f67-118">Web Access クライアント会議</span><span class="sxs-lookup"><span data-stu-id="51f67-118">Web Access Client conferencing</span></span>  <br/> |<span data-ttu-id="51f67-119">会議の自動応答</span><span class="sxs-lookup"><span data-stu-id="51f67-119">Conference auto attendant</span></span>  <br/> |
|<span data-ttu-id="51f67-120">応答グループ</span><span class="sxs-lookup"><span data-stu-id="51f67-120">Response Groups</span></span>  <br/> |<span data-ttu-id="51f67-121">配布リストの展開</span><span class="sxs-lookup"><span data-stu-id="51f67-121">Distribution list expansion</span></span>  <br/> |
|<span data-ttu-id="51f67-122">アドレス帳のダウンロードとアドレス帳のクエリ</span><span class="sxs-lookup"><span data-stu-id="51f67-122">Address book download and address book query</span></span>  <br/> |<span data-ttu-id="51f67-123">拡張 911 (E911) 通話と位置情報プロファイル (ダイヤルプラン)</span><span class="sxs-lookup"><span data-stu-id="51f67-123">Enhanced 911 (E911) calls and location profile (dial plan)</span></span>  <br/> |
|<span data-ttu-id="51f67-124">MultiView</span><span class="sxs-lookup"><span data-stu-id="51f67-124">MultiView</span></span>  <br/> |<span data-ttu-id="51f67-125">データの共同作業</span><span class="sxs-lookup"><span data-stu-id="51f67-125">Data collaboration</span></span>  <br/> |
|<span data-ttu-id="51f67-126">モビリティ</span><span class="sxs-lookup"><span data-stu-id="51f67-126">Mobility</span></span>  <br/> ||
   
## <a name="applications-and-files-included-with-the-skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="51f67-127">Skype for Business Server 2015 のストレスとパフォーマンスのツールに含まれているアプリケーションとファイル</span><span class="sxs-lookup"><span data-stu-id="51f67-127">Applications and files included with the Skype for Business Server 2015 Stress and Performance Tool</span></span>

<span data-ttu-id="51f67-128">これらのアプリケーションは、Skype for Business Server のストレスとパフォーマンスツールの一部です。</span><span class="sxs-lookup"><span data-stu-id="51f67-128">These applications are a part of the Skype for Business Server Stress and Performance Tool:</span></span>
  
|<span data-ttu-id="51f67-129">**ツール**</span><span class="sxs-lookup"><span data-stu-id="51f67-129">**Tool**</span></span>|<span data-ttu-id="51f67-130">**説明**</span><span class="sxs-lookup"><span data-stu-id="51f67-130">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="51f67-131">Userプロビジョニングツール .exe</span><span class="sxs-lookup"><span data-stu-id="51f67-131">UserProvisioningTool.exe</span></span>  <br/> |<span data-ttu-id="51f67-132">このツールは、ユーザーと連絡先を作成するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="51f67-132">This tool is used to create users and contacts.</span></span>  <br/> |
|<span data-ttu-id="51f67-133">UserProfileGenerator</span><span class="sxs-lookup"><span data-stu-id="51f67-133">UserProfileGenerator.exe</span></span>  <br/> |<span data-ttu-id="51f67-134">シミュレートしているユーザーロードの特性を構成するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="51f67-134">Used to configure the characteristics of the user load you're simulating.</span></span>  <br/> |
|<span data-ttu-id="51f67-135">LyncPerfTool</span><span class="sxs-lookup"><span data-stu-id="51f67-135">LyncPerfTool.exe</span></span>  <br/> |<span data-ttu-id="51f67-136">ユーザーロードをシミュレートするツール。</span><span class="sxs-lookup"><span data-stu-id="51f67-136">The tool that simulates user load.</span></span>  <br/> |
|<span data-ttu-id="51f67-137">Tmx</span><span class="sxs-lookup"><span data-stu-id="51f67-137">Default.tmx</span></span>  <br/> |<span data-ttu-id="51f67-138">Skype for Business Server 2015 Logging Tool を使用するために必要です。</span><span class="sxs-lookup"><span data-stu-id="51f67-138">Required to use the Skype for Business Server 2015 Logging Tool.</span></span>  <br/> |
|<span data-ttu-id="51f67-139">プロビジョニングスクリプトの例</span><span class="sxs-lookup"><span data-stu-id="51f67-139">Provisioning script examples</span></span>  <br/> |<span data-ttu-id="51f67-140">特定のシナリオに基づいて、ロードテストを実行するためのトポロジを構成するために使われます。</span><span class="sxs-lookup"><span data-stu-id="51f67-140">Used to configure the topology for running load tests, based on specific scenarios.</span></span> <span data-ttu-id="51f67-141">特定の環境に関連するように、これらを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="51f67-141">You'll likely need to modify them to make them relevant for your particular environment.</span></span>  <br/> |
   
## <a name="topics-in-this-section"></a><span data-ttu-id="51f67-142">このセクションのトピック</span><span class="sxs-lookup"><span data-stu-id="51f67-142">Topics in this section</span></span>

<span data-ttu-id="51f67-143">詳細情報が必要な場合は、次の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="51f67-143">You should review the following articles if you need to know more:</span></span>
  
- [<span data-ttu-id="51f67-144">Skype for Busines Stress and Performance Tool の前提条件と設定</span><span class="sxs-lookup"><span data-stu-id="51f67-144">Prerequisites and setup for the Skype for Busines Stress and Performance Tool</span></span>](prerequisites-and-setup.md)
    
- [<span data-ttu-id="51f67-145">Skype for Business Server 2015 ストレス/パフォーマンスツールのパフォーマンスシナリオ</span><span class="sxs-lookup"><span data-stu-id="51f67-145">Performance Scenarios for the Skype for Business Server 2015 Stress and Performance Tool</span></span>](scenarios.md)
    
  - [<span data-ttu-id="51f67-146">ストレスとパフォーマンスのシナリオでのロードを実行するためのトポロジのプロビジョニング</span><span class="sxs-lookup"><span data-stu-id="51f67-146">Provisioning the topology to run load in Stress and Performance scenarios</span></span>](provisioning-the-topology-to-run-load.md)
    
  - [<span data-ttu-id="51f67-147">Skype for Business Server 2015 応力とパフォーマンスツールのポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="51f67-147">Configuring policies for the Skype for Business Server 2015 Stress and Performance Tool</span></span>](configuring-policies.md)
    
- [<span data-ttu-id="51f67-148">Skype for Business Server 2015 のストレスとパフォーマンスのツールを使用する</span><span class="sxs-lookup"><span data-stu-id="51f67-148">Using the Skype for Business Server 2015 Stress and Performance Tool</span></span>](using-the-tool.md)
    
- [<span data-ttu-id="51f67-149">Skype for Business Server 2015 のストレスとパフォーマンスのツールについてよく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="51f67-149">FAQ for the Skype for Business Server 2015 Stress and Performance Tool</span></span>](faq.md)
    

