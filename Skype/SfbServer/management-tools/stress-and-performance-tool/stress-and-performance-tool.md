---
title: Skype for Business Server 2015 Stress and Performance Tool
ms.reviewer: ''
ms.author: v-cichur
author: cichur
ms.date: 4/6/2016
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: f2f7d19b-18c8-4a41-9b17-80d35b73d742
description: Skype for Business Server 2015 Stress and Performance Tool は、非稼働環境またはテスト環境での容量計画とパフォーマンスチューニングの間に使用されます。
ms.openlocfilehash: 551e4e5f985fc18439a4f277685034e86c7cdfb6
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814927"
---
# <a name="skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="1ce02-103">Skype for Business Server 2015 Stress and Performance Tool</span><span class="sxs-lookup"><span data-stu-id="1ce02-103">Skype for Business Server 2015 Stress and Performance Tool</span></span>
 
<span data-ttu-id="1ce02-104">Skype for Business Server 2015 Stress and Performance Tool は、非稼働環境またはテスト環境での容量計画とパフォーマンスチューニングの際に使用されます。</span><span class="sxs-lookup"><span data-stu-id="1ce02-104">The Skype for Business Server 2015 Stress and Performance Tool is used during capacity planning and performance tuning in non-production or test environments.</span></span>
  
<span data-ttu-id="1ce02-105">Skype for Business Server 2015 Stress and Performance Tool には、Skype for Business Server 2015 の容量計画を簡素化するツールが含まれています。</span><span class="sxs-lookup"><span data-stu-id="1ce02-105">The Skype for Business Server 2015 Stress and Performance Tool includes tools that will simplify your capacity planning for Skype for Business Server 2015.</span></span> <span data-ttu-id="1ce02-106">Skype for Business Server 2015 Stress and Performance Tool は、次の場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="1ce02-106">The Skype for Business Server 2015 Stress and Performance Tool will help you to:</span></span>
  
- <span data-ttu-id="1ce02-107">Skype for Business Server のハードウェア計画を簡素化する</span><span class="sxs-lookup"><span data-stu-id="1ce02-107">Simplify your hardware planning for Skype for Business Server</span></span>
    
- <span data-ttu-id="1ce02-108">パフォーマンスのチューニングに関する知識とベスト プラクティスを向上させる</span><span class="sxs-lookup"><span data-stu-id="1ce02-108">Give you increased knowledge and best practices for performance tuning</span></span>
    
- <span data-ttu-id="1ce02-109">Skype for Business Server 展開のパフォーマンスを測定する</span><span class="sxs-lookup"><span data-stu-id="1ce02-109">Measure the performance of your Skype for Business Server deployments</span></span>
    
<span data-ttu-id="1ce02-110">このツールは、通常 [、Skype for Business Server 2015 Planning Tool](../../management-tools/planning-tool/planning-tool.md) を使用してトポロジを設計し [、Skype for Business Server 2015 Capacity Planning Calculator](../../management-tools/capacity-planning-calculator.md)を使用してトポロジを絞り込む場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="1ce02-110">You would typically use this tool after you use the [Skype for Business Server 2015 Planning Tool](../../management-tools/planning-tool/planning-tool.md) to design the topology, and refining the topology with the [Skype for Business Server 2015 Capacity Planning Calculator](../../management-tools/capacity-planning-calculator.md).</span></span> 

> [!NOTE]
> <span data-ttu-id="1ce02-111">このツールは、Skype for Business Server 2019 では更新されません。</span><span class="sxs-lookup"><span data-stu-id="1ce02-111">This tool will not be updated for Skype for Business Server 2019.</span></span>
  
## <a name="tests"></a><span data-ttu-id="1ce02-112">テスト</span><span class="sxs-lookup"><span data-stu-id="1ce02-112">Tests</span></span>

<span data-ttu-id="1ce02-113">Stress and Performance Tool は、次の種類のユーザー負荷をシミュレートできます。</span><span class="sxs-lookup"><span data-stu-id="1ce02-113">The Stress and Performance Tool can simulate these types of user load:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="1ce02-114">インスタント メッセージング (IM) とプレゼンス</span><span class="sxs-lookup"><span data-stu-id="1ce02-114">Instant Messaging (IM) and presence</span></span>  <br/> |<span data-ttu-id="1ce02-115">電話会議</span><span class="sxs-lookup"><span data-stu-id="1ce02-115">Audio conferencing</span></span>  <br/> |
|<span data-ttu-id="1ce02-116">アプリケーション共有</span><span class="sxs-lookup"><span data-stu-id="1ce02-116">Application sharing</span></span>  <br/> |<span data-ttu-id="1ce02-117">公衆交換電話網 (PTSN) シミュレーションを含むボイス オーバー IP (VoIP)</span><span class="sxs-lookup"><span data-stu-id="1ce02-117">Voice over IP (VoIP), including public switched telephone network (PTSN) simulation</span></span>  <br/> |
|<span data-ttu-id="1ce02-118">Web Access クライアント会議</span><span class="sxs-lookup"><span data-stu-id="1ce02-118">Web Access Client conferencing</span></span>  <br/> |<span data-ttu-id="1ce02-119">会議自動応答</span><span class="sxs-lookup"><span data-stu-id="1ce02-119">Conference auto attendant</span></span>  <br/> |
|<span data-ttu-id="1ce02-120">応答グループ</span><span class="sxs-lookup"><span data-stu-id="1ce02-120">Response Groups</span></span>  <br/> |<span data-ttu-id="1ce02-121">配布リストの展開</span><span class="sxs-lookup"><span data-stu-id="1ce02-121">Distribution list expansion</span></span>  <br/> |
|<span data-ttu-id="1ce02-122">アドレス帳のダウンロードとアドレス帳のクエリ</span><span class="sxs-lookup"><span data-stu-id="1ce02-122">Address book download and address book query</span></span>  <br/> |<span data-ttu-id="1ce02-123">拡張 911 (E911) 通話と場所プロファイル (ダイヤル プラン)</span><span class="sxs-lookup"><span data-stu-id="1ce02-123">Enhanced 911 (E911) calls and location profile (dial plan)</span></span>  <br/> |
|<span data-ttu-id="1ce02-124">MultiView</span><span class="sxs-lookup"><span data-stu-id="1ce02-124">MultiView</span></span>  <br/> |<span data-ttu-id="1ce02-125">データ コラボレーション</span><span class="sxs-lookup"><span data-stu-id="1ce02-125">Data collaboration</span></span>  <br/> |
|<span data-ttu-id="1ce02-126">モビリティ</span><span class="sxs-lookup"><span data-stu-id="1ce02-126">Mobility</span></span>  <br/> ||
   
## <a name="applications-and-files-included-with-the-skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="1ce02-127">Skype for Business Server 2015 Stress and Performance Tool に含まれるアプリケーションとファイル</span><span class="sxs-lookup"><span data-stu-id="1ce02-127">Applications and files included with the Skype for Business Server 2015 Stress and Performance Tool</span></span>

<span data-ttu-id="1ce02-128">これらのアプリケーションは、Skype for Business Server Stress and Performance Tool の一部です。</span><span class="sxs-lookup"><span data-stu-id="1ce02-128">These applications are a part of the Skype for Business Server Stress and Performance Tool:</span></span>
  
|<span data-ttu-id="1ce02-129">**ツール**</span><span class="sxs-lookup"><span data-stu-id="1ce02-129">**Tool**</span></span>|<span data-ttu-id="1ce02-130">**説明**</span><span class="sxs-lookup"><span data-stu-id="1ce02-130">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="1ce02-131">UserProvisioningTool.exe</span><span class="sxs-lookup"><span data-stu-id="1ce02-131">UserProvisioningTool.exe</span></span>  <br/> |<span data-ttu-id="1ce02-132">このツールは、ユーザーと連絡先を作成するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="1ce02-132">This tool is used to create users and contacts.</span></span>  <br/> |
|<span data-ttu-id="1ce02-133">UserProfileGenerator.exe</span><span class="sxs-lookup"><span data-stu-id="1ce02-133">UserProfileGenerator.exe</span></span>  <br/> |<span data-ttu-id="1ce02-134">シミュレートするユーザー負荷の特性を構成するために使用します。</span><span class="sxs-lookup"><span data-stu-id="1ce02-134">Used to configure the characteristics of the user load you're simulating.</span></span>  <br/> |
|<span data-ttu-id="1ce02-135">LyncPerfTool.exe</span><span class="sxs-lookup"><span data-stu-id="1ce02-135">LyncPerfTool.exe</span></span>  <br/> |<span data-ttu-id="1ce02-136">ユーザーの負荷をシミュレートするツール。</span><span class="sxs-lookup"><span data-stu-id="1ce02-136">The tool that simulates user load.</span></span>  <br/> |
|<span data-ttu-id="1ce02-137">Default.tmx</span><span class="sxs-lookup"><span data-stu-id="1ce02-137">Default.tmx</span></span>  <br/> |<span data-ttu-id="1ce02-138">Skype for Business Server 2015 ログ ツールを使用するために必要です。</span><span class="sxs-lookup"><span data-stu-id="1ce02-138">Required to use the Skype for Business Server 2015 Logging Tool.</span></span>  <br/> |
|<span data-ttu-id="1ce02-139">プロビジョニング スクリプトの例</span><span class="sxs-lookup"><span data-stu-id="1ce02-139">Provisioning script examples</span></span>  <br/> |<span data-ttu-id="1ce02-140">特定のシナリオに基づいて負荷テストを実行するトポロジを構成するために使用します。</span><span class="sxs-lookup"><span data-stu-id="1ce02-140">Used to configure the topology for running load tests, based on specific scenarios.</span></span> <span data-ttu-id="1ce02-141">特定の環境に関連付けられているものに変更する必要がある可能性があります。</span><span class="sxs-lookup"><span data-stu-id="1ce02-141">You'll likely need to modify them to make them relevant for your particular environment.</span></span>  <br/> |
   
## <a name="topics-in-this-section"></a><span data-ttu-id="1ce02-142">このセクションのトピック</span><span class="sxs-lookup"><span data-stu-id="1ce02-142">Topics in this section</span></span>

<span data-ttu-id="1ce02-143">詳細を知る必要がある場合は、次の記事を確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1ce02-143">You should review the following articles if you need to know more:</span></span>
  
- [<span data-ttu-id="1ce02-144">Skype for Busines Stress and Performance Tool の前提条件とセットアップ</span><span class="sxs-lookup"><span data-stu-id="1ce02-144">Prerequisites and setup for the Skype for Busines Stress and Performance Tool</span></span>](prerequisites-and-setup.md)
    
- [<span data-ttu-id="1ce02-145">Skype for Business Server 2015 Stress and Performance Tool のパフォーマンス シナリオ</span><span class="sxs-lookup"><span data-stu-id="1ce02-145">Performance Scenarios for the Skype for Business Server 2015 Stress and Performance Tool</span></span>](scenarios.md)
    
  - [<span data-ttu-id="1ce02-146">ストレスとパフォーマンスのシナリオで負荷を実行するトポロジのプロビジョニング</span><span class="sxs-lookup"><span data-stu-id="1ce02-146">Provisioning the topology to run load in Stress and Performance scenarios</span></span>](provisioning-the-topology-to-run-load.md)
    
  - [<span data-ttu-id="1ce02-147">Skype for Business Server 2015 Stress and Performance Tool のポリシーの構成</span><span class="sxs-lookup"><span data-stu-id="1ce02-147">Configuring policies for the Skype for Business Server 2015 Stress and Performance Tool</span></span>](configuring-policies.md)
    
- [<span data-ttu-id="1ce02-148">Skype for Business Server 2015 Stress and Performance Tool の使用</span><span class="sxs-lookup"><span data-stu-id="1ce02-148">Using the Skype for Business Server 2015 Stress and Performance Tool</span></span>](using-the-tool.md)
    
- [<span data-ttu-id="1ce02-149">Skype for Business Server 2015 Stress and Performance Tool の FAQ</span><span class="sxs-lookup"><span data-stu-id="1ce02-149">FAQ for the Skype for Business Server 2015 Stress and Performance Tool</span></span>](faq.md)
    

