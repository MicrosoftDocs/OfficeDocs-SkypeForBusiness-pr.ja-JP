---
title: Skype for Business Server の容量計画の計算機
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
ms.date: 2/1/2018
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: bc4d93b1-0c38-4bf8-8b65-692ff3e2446d
description: '概要: 容量計算ツールの使用方法について説明します。'
ms.openlocfilehash: 1bb1c9cde82c1f2d6e487c3bc28520b630d59210
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42031081"
---
# <a name="skype-for-business-server-capacity-planning-calculator"></a><span data-ttu-id="e9acb-103">Skype for Business Server の容量計画の計算機</span><span class="sxs-lookup"><span data-stu-id="e9acb-103">Skype for Business Server Capacity Planning Calculator</span></span>
 
<span data-ttu-id="e9acb-104">**概要:** 容量計算ツールの使用方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="e9acb-104">**Summary:** How to use the Capacity Calculator Tool.</span></span>

> [!NOTE]
> <span data-ttu-id="e9acb-105">この記事では、Skype for Business Server 2015 ダウンロードを参照していますが、次の項目に適用されます。</span><span class="sxs-lookup"><span data-stu-id="e9acb-105">This article references Skype for Business Server 2015 downloads, but it applies to:</span></span>
> - <span data-ttu-id="e9acb-106">Skype for Business Server 2019。</span><span class="sxs-lookup"><span data-stu-id="e9acb-106">Skype for Business Server 2019.</span></span>
> - <span data-ttu-id="e9acb-107">Skype for Business Server 2015。</span><span class="sxs-lookup"><span data-stu-id="e9acb-107">Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="e9acb-108">Skype for [Business server 2015 Capacity calculator](https://www.microsoft.com/download/details.aspx?id=51196) and [skype for Business Server 2019 capacity Calculator](https://www.microsoft.com/download/details.aspx?id=57509)は、Skype For business の[計画ツール](https://www.microsoft.com/download/details.aspx?id=50357)と展開に関するドキュメント (それぞれ、skype for Business[2015 server の展開を計画](../plan-your-deployment/plan-your-deployment.md)し、skype for business [server の 2019](../../SfBServer2019/plan/plan-your-deployment-2019.md)の展開を計画する) を強化します。</span><span class="sxs-lookup"><span data-stu-id="e9acb-108">The [Skype for Business Server 2015 Capacity Calculator](https://www.microsoft.com/download/details.aspx?id=51196) and [Skype for Business Server 2019 Capacity Calculator](https://www.microsoft.com/download/details.aspx?id=57509) augment the [Skype for Business Planning Tool](https://www.microsoft.com/download/details.aspx?id=50357) and your deployment documentation ([Plan for your Skype for Business Server 2015 deployment](../plan-your-deployment/plan-your-deployment.md) and [Plan for your Skype for Business Server 2019 deployment](../../SfBServer2019/plan/plan-your-deployment-2019.md) respectively).</span></span> <span data-ttu-id="e9acb-109">ガイドを確認し、計画ツールを使用して推奨されるトポロジを作成したら、電卓を使用します。</span><span class="sxs-lookup"><span data-stu-id="e9acb-109">Use the calculator after you have reviewed the guide and created a recommended topology by using the Planning Tool.</span></span>
  
<span data-ttu-id="e9acb-110">Skype for Business Server の容量計算ツールを使用すると、ユーザー数と組織が使用する通信ツールに基づいて、サーバーの要件を決定できます。</span><span class="sxs-lookup"><span data-stu-id="e9acb-110">The Skype for Business Server Capacity Calculator helps you determine server requirements based on the number of users and the communication tools your organization uses.</span></span> <span data-ttu-id="e9acb-111">ユーザーに対して有効にするユーザープロファイルと機能を決定したら、電卓を使用して、必要なサーバー、メモリ、および帯域幅の数を決定します。</span><span class="sxs-lookup"><span data-stu-id="e9acb-111">After you have determined your user profile and the functions you want to enable for your users, use the calculator to determine the number of servers, memory, and bandwidth you will need.</span></span> <span data-ttu-id="e9acb-112">この電卓のバージョンでは、ディスク i/o の要件についてのガイダンスは提供されていません。</span><span class="sxs-lookup"><span data-stu-id="e9acb-112">This version of the calculator does not provide guidance for disk I/O requirements.</span></span>
  
<span data-ttu-id="e9acb-113">特定のユーザープロファイルに関する詳細情報を正確に把握している場合は、計算機を使用すると便利です。</span><span class="sxs-lookup"><span data-stu-id="e9acb-113">You can benefit most from the calculator if you have accurate, detailed information about your specific user profile.</span></span> <span data-ttu-id="e9acb-114">たとえば、音声が有効なユーザーの割合、1時間あたりの平均通話、通話時間、会議での同時ユーザー数の割合は、サーバーの要件に大きな違いを持たせることができます。</span><span class="sxs-lookup"><span data-stu-id="e9acb-114">For example, the percentage of voice-enabled users, average calls per user per hour, call duration, and the percentage of concurrent users in conferences can make a huge difference in server requirements.</span></span> <span data-ttu-id="e9acb-115">計算機によって作成された推奨事項の精度は、提供する情報の正確性によって決まります。</span><span class="sxs-lookup"><span data-stu-id="e9acb-115">The accuracy of the recommendations created by the calculator depends on the accuracy of the information that you provide.</span></span>
  
<span data-ttu-id="e9acb-116">計画ツールと処理能力計画の計算機を使用した後は、提案および計画された負荷をシミュレートして、Skype for Business Server が適切にプロビジョニングされるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e9acb-116">Once you have used the Planning Tool and the Capacity Planning Calculator, you should simulate your proposed and planned load to ensure that Skype for Business Server will be adequately provisioned.</span></span> <span data-ttu-id="e9acb-117">シミュレートされた負荷の下でストレステストを実行するには、skype for business Server のストレスおよび[パフォーマンスツール](https://technet.microsoft.com/library/mt631400.aspx)で文書化された[Skype for Business server のストレスおよびパフォーマンスツール](https://www.microsoft.com/download/details.aspx?id=50367)を使用します。</span><span class="sxs-lookup"><span data-stu-id="e9acb-117">To perform stress testing under a simulated load, use the [Skype for Business Server Stress and Performance Tool](https://www.microsoft.com/download/details.aspx?id=50367) documented at [Skype for Business Server Stress and Performance Tool](https://technet.microsoft.com/library/mt631400.aspx).</span></span>
  
## <a name="using-the-capacity-calculator"></a><span data-ttu-id="e9acb-118">容量計算機の使用</span><span class="sxs-lookup"><span data-stu-id="e9acb-118">Using the Capacity Calculator</span></span>

<span data-ttu-id="e9acb-119">電卓は、Microsoft Excel スプレッドシートです。</span><span class="sxs-lookup"><span data-stu-id="e9acb-119">The calculator is a Microsoft Excel spreadsheet.</span></span> <span data-ttu-id="e9acb-120">入力セルはオレンジ色で塗りつぶされます。</span><span class="sxs-lookup"><span data-stu-id="e9acb-120">Your input cells are colored orange.</span></span> <span data-ttu-id="e9acb-121">セルには既定値が入力されています (Skype for Business Server 2015、8万ユーザーは12個のフロントエンドサーバーを使用し、1つのプール内の1つのプールでは、フロントエンドサーバーが16台 106000 2019 の場合)、これらの値を次のように変更する必要があります。組織のニーズに対応します。</span><span class="sxs-lookup"><span data-stu-id="e9acb-121">Default values are entered in the cells (For Skype for Business Server 2015, 80,000 users in one pool with twelve Front End Servers, while for Skype for Business Server 2019, 106,000 users in one pool with sixteen Front End Servers), but you should change these values to match your organization's needs.</span></span>
  
<span data-ttu-id="e9acb-122">利用状況モデルには、以下のセクションが含まれています。</span><span class="sxs-lookup"><span data-stu-id="e9acb-122">The usage model contains the following sections.</span></span> <span data-ttu-id="e9acb-123">容量の要件を計算するには、次の説明に従って、データを入力します。</span><span class="sxs-lookup"><span data-stu-id="e9acb-123">To calculate your capacity requirements, enter data as described starting at the top of the sheet and working down row by row:</span></span> 
  
 <span data-ttu-id="e9acb-124">**インスタント メッセージングとプレゼンス**</span><span class="sxs-lookup"><span data-stu-id="e9acb-124">**Instant Messaging and Presence**</span></span>
  
- <span data-ttu-id="e9acb-125">[**ユーザー数**] に、一度にサインインするユーザーの数を入力します。</span><span class="sxs-lookup"><span data-stu-id="e9acb-125">Under **Number of Users**, type the number of users who will be signed in at once.</span></span> <span data-ttu-id="e9acb-126">この数値は、通常、プロビジョニングされたユーザーの総数の80% です。</span><span class="sxs-lookup"><span data-stu-id="e9acb-126">This number is typically 80% of the total number of provisioned users.</span></span> <span data-ttu-id="e9acb-127">ほとんどの場合、同時ユーザーの100% が IM とプレゼンスに対して有効になります。</span><span class="sxs-lookup"><span data-stu-id="e9acb-127">In most situations, 100% of your concurrent users will be enabled for IM and Presence.</span></span> <span data-ttu-id="e9acb-128">既定では、Skype for business Server 2015 の場合は8万、Skype for Business 2019 Server の場合は106000ユーザーが使用されます。</span><span class="sxs-lookup"><span data-stu-id="e9acb-128">The default is 80,000 for Skype for Business Server 2015, and 106,000 users for Skype for Business Server 2019.</span></span>
    
- <span data-ttu-id="e9acb-129">**連絡先リスト内の平均連絡先数**は、システム要件の検証に使用している連絡先の数を示します。</span><span class="sxs-lookup"><span data-stu-id="e9acb-129">**Average number of contacts in Contact list** indicates the number of contacts that we are using to validate your system requirements.</span></span> <span data-ttu-id="e9acb-130">この数は固定されており、変更する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="e9acb-130">This number is fixed and not something you should change.</span></span>
    
  <span data-ttu-id="e9acb-131">**エンタープライズ VoIP**</span><span class="sxs-lookup"><span data-stu-id="e9acb-131">**Enterprise Voice**</span></span>
  
- <span data-ttu-id="e9acb-132">[**エンタープライズ voip が有効なユーザー**] で、エンタープライズ voip が有効になっているユーザーの割合を入力します。</span><span class="sxs-lookup"><span data-stu-id="e9acb-132">In **Users enabled for Enterprise Voice**, type the percentage of your users enabled for Enterprise Voice.</span></span> <span data-ttu-id="e9acb-133">既定値は60% です。</span><span class="sxs-lookup"><span data-stu-id="e9acb-133">The default is 60%.</span></span> 
    
- <span data-ttu-id="e9acb-134">[1 時間あたり**の平均通話数 (ピーク時)**] で、ピーク負荷が発生した時間帯に、平均的なユーザーが参加すると予想される通話の数を入力します。</span><span class="sxs-lookup"><span data-stu-id="e9acb-134">In **Average number of calls per user per hour (peak)**, type the number of calls per hour you expect the average user to participate in during times of peak load.</span></span> <span data-ttu-id="e9acb-135">既定値は 4 です。</span><span class="sxs-lookup"><span data-stu-id="e9acb-135">The default is 4.</span></span> 
    
- <span data-ttu-id="e9acb-136">[**メディアバイパスを使用する通話の割合**] で、ユーザーが仲介サーバーをバイパスする通話の割合を入力します。</span><span class="sxs-lookup"><span data-stu-id="e9acb-136">In **Percentage of calls that use media bypass**, type the percentage of calls placed by your users that will bypass the Mediation Server.</span></span> <span data-ttu-id="e9acb-137">既定値は65% ですが、地理的に分散している場合や、自宅から働くユーザーの割合が大きい場合は、より低い値になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e9acb-137">The default is 65%, but could be lower if you are spread out geographically or have a large percentage of users who work from home.</span></span>
    
- <span data-ttu-id="e9acb-138">[ **UC pstn 通話に参加している音声ユーザーの割合**] で、組織の着信のうち、uc pstn 電話での通話の割合を入力します。</span><span class="sxs-lookup"><span data-stu-id="e9acb-138">In **Percentage of voice users involved in UC-PSTN calls**, type the percentage of your organization's calls which are UC-PSTN phone calls.</span></span> <span data-ttu-id="e9acb-139">既定値は60% です。</span><span class="sxs-lookup"><span data-stu-id="e9acb-139">The default is 60%.</span></span>
    
- <span data-ttu-id="e9acb-140">Uc **-uc 通話に参加している音声ユーザーの割合**は、エンタープライズ voip が有効になっているユーザーのパーセンテージを示しています。これは、uc uc 呼び出しに対してのみ有効になります。</span><span class="sxs-lookup"><span data-stu-id="e9acb-140">**Percentage of voice users involved in UC-UC calls** shows the percentage of users who are enabled for Enterprise Voice who will be enabled only for UC-UC calls.</span></span> <span data-ttu-id="e9acb-141">この数値は、 **UC 通話に対して有効になっている音声ユーザーのパーセンテージ**に対して入力した値に基づいて計算されます。</span><span class="sxs-lookup"><span data-stu-id="e9acb-141">This number is calculated based on what you input for **Percentage of voice users enabled for UC-PSTN calls**.</span></span> 
    
  <span data-ttu-id="e9acb-142">**会議**</span><span class="sxs-lookup"><span data-stu-id="e9acb-142">**Conferencing**</span></span>
  
- <span data-ttu-id="e9acb-143">**同時電話会議のユーザー数の割合**に、会議に参加するユーザーの割合を同時に入力します。</span><span class="sxs-lookup"><span data-stu-id="e9acb-143">In **Percentage of users in concurrent conferences**, type the percentage of users who will be participating in conferences at the same time.</span></span> <span data-ttu-id="e9acb-144">既定値は5% です。</span><span class="sxs-lookup"><span data-stu-id="e9acb-144">The default is 5%.</span></span> 
    
- <span data-ttu-id="e9acb-145">[**グループ IM のみの電話会議の割合] (音声)** で、インスタントメッセージングのみを含む電話会議の割合を入力します。また、音声は含まれません。</span><span class="sxs-lookup"><span data-stu-id="e9acb-145">In **Percentage of conferences with group IM only (no voice)**, type the percentage of conferences that will involve instant messaging only and do not include audio.</span></span> <span data-ttu-id="e9acb-146">既定値は10% です。</span><span class="sxs-lookup"><span data-stu-id="e9acb-146">The default is 10%</span></span>
    
- <span data-ttu-id="e9acb-147">[**ダイヤルイン会議を使用しているユーザーの割合**] に、ダイヤルイン会議を一度に使用する会議の参加者の割合を入力します。</span><span class="sxs-lookup"><span data-stu-id="e9acb-147">In **Percentage of users using dial-in conferencing**, type the percentage of participants in conferences who will be using dial-in conferencing at one time.</span></span> <span data-ttu-id="e9acb-148">既定値は15% です。</span><span class="sxs-lookup"><span data-stu-id="e9acb-148">The default is 15%.</span></span>
    
- <span data-ttu-id="e9acb-149">[**音声を使用する電話会議の割合**] で、音声を含める電話会議の割合を入力します。</span><span class="sxs-lookup"><span data-stu-id="e9acb-149">In **Percentage of conferences using voice**, type the percentage of conferences that will include audio.</span></span> 
    
  - <span data-ttu-id="e9acb-150">音声会議の20% が通常のビデオも含まれる場合は、[**ビデオを含む (マルチビュー**を使用しない)] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="e9acb-150">If 20% of your voice conferences will also include regular video, select the **Including video (no Multi View)** check box.</span></span>
    
  - <span data-ttu-id="e9acb-151">電話会議の20% がマルチビュービデオも含まれている場合は、[**マルチ**ビューを含める] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="e9acb-151">If 20% of your conferences will also include Multi-View video, select the **Including Multi View** check box.</span></span>
    
  - <span data-ttu-id="e9acb-152">音声会議の50% がアプリケーション共有も含まれる場合は、[**アプリケーション共有**を含める] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="e9acb-152">If 50% of your voice conferences will also include application sharing, select the **Including application sharing** check box.</span></span>
    
  - <span data-ttu-id="e9acb-153">音声会議の20% が PowerPoint プレゼンテーションなどのデータのアップロードを含んでいる場合は、[ **web 会議を含める**] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="e9acb-153">If 20% of your voice conferences include data uploads, such as PowerPoint presentations, select the **Including web conferencing** check box.</span></span>
    
  <span data-ttu-id="e9acb-154">**モビリティ**</span><span class="sxs-lookup"><span data-stu-id="e9acb-154">**Mobility**</span></span>
  
- <span data-ttu-id="e9acb-155">[**モビリティが有効なユーザー数の割合**] で、モバイルデバイスを使用して Skype For business Server への接続を有効にするユーザーの割合を入力します。</span><span class="sxs-lookup"><span data-stu-id="e9acb-155">In **Percentage of users enabled for Mobility**, type the percentage of your users who will be enabled to connect to Skype for Business Server using mobile devices.</span></span> <span data-ttu-id="e9acb-156">既定値は40% です。</span><span class="sxs-lookup"><span data-stu-id="e9acb-156">The default is 40%.</span></span> 
    
<span data-ttu-id="e9acb-157">必要な情報をすべて入力したら、容量計算機が要件を予測します。</span><span class="sxs-lookup"><span data-stu-id="e9acb-157">When you have entered all the necessary information, the capacity calculator estimates your requirements.</span></span> <span data-ttu-id="e9acb-158">黄色のセルには、Skype for Business Server パフォーマンスラボで実行されたテストに基づいた CPU、メモリ、および帯域幅の要件の計算値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e9acb-158">The yellow cells show calculated values for CPU, memory, and bandwidth requirements based on tests performed in Skype for Business Server performance labs.</span></span> <span data-ttu-id="e9acb-159">この番号はガイドラインとして提供されており、すべてのバリエーションがテストおよび検証されるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="e9acb-159">The numbers are provided as a guideline, not every single variation is tested and validated.</span></span> <span data-ttu-id="e9acb-160">次の値が計算されます。</span><span class="sxs-lookup"><span data-stu-id="e9acb-160">The following values are calculated:</span></span> 
  
- <span data-ttu-id="e9acb-161">**フロントエンド cpu**: 負荷全体が、テストで使用したサーバーと同じ仕様の1台のフロントエンドサーバーによって処理されていた場合の cpu 使用率の割合 (この記事の最後にある説明を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="e9acb-161">**Front End CPU**: Percentage of CPU usage if the entire load were being handled by one Front End Server of the same specifications as the server that was used in testing (see the description at the end of this article).</span></span>
    
- <span data-ttu-id="e9acb-162">[**ネットワーク (mbps**)]: 対応するワークロードの帯域幅要件 (メガビット/秒 (mbps))。</span><span class="sxs-lookup"><span data-stu-id="e9acb-162">**Network in Mbps**: Bandwidth requirements in megabits per second (Mbps) for the corresponding workload.</span></span>
    
- <span data-ttu-id="e9acb-163">**Gb 単位のメモリ**: 対応するワークロードに必要なメモリ (gb)。</span><span class="sxs-lookup"><span data-stu-id="e9acb-163">**Memory in GB**: Memory required in gigabytes (GB) for the corresponding workload.</span></span>
    
<span data-ttu-id="e9acb-164">緑色のセルには、入力した使用モデルの推奨事項が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e9acb-164">The green cells show recommendations for the usage model that you entered.</span></span> 
  
- <span data-ttu-id="e9acb-165">**フロントエンドサーバーの総数**: 必要な物理サーバーの数は、Skype For business server 2015 を実行している専用サーバー (デュアルプロセッサ、16ビット、2260メガサイクル、または Skype For business server 2019、Intel Xeon E5-2673 v3、デュアルプロセッサ、16ビットコア) に基づいています。</span><span class="sxs-lookup"><span data-stu-id="e9acb-165">**Total Front End Servers**: The number of physical servers required are based on dedicated servers running Skype for Business Server 2015 with dual processor, hex-core, with 2,260 megacycles, or Skype for Business Server 2019 with Intel Xeon E5-2673 v3, dual processor, hex-core.</span></span>
    
    <span data-ttu-id="e9acb-166">ハイパースレッディングを有効にすることをお勧めします。また、音声/ビデオをサポートするサーバーのパフォーマンスを向上させることが実証されています。</span><span class="sxs-lookup"><span data-stu-id="e9acb-166">Note that enabling hyperthreading is recommended and has been proven to improve performance for servers that support audio/video.</span></span>
    
- <span data-ttu-id="e9acb-167">**エッジサーバー**: エッジサーバーを介して通信するすべての同時ユーザーの30% に基づいて、必要なエッジサーバーの数。</span><span class="sxs-lookup"><span data-stu-id="e9acb-167">**Edge Servers**: The number of Edge Servers required, based on 30% of all concurrent users communicating through the Edge Servers.</span></span> <span data-ttu-id="e9acb-168">このパーセンテージは、電卓では変更できません。</span><span class="sxs-lookup"><span data-stu-id="e9acb-168">This percentage cannot be changed in the calculator.</span></span> 
    
- <span data-ttu-id="e9acb-169">**アーカイブ/通話詳細記録/qoe (Quality Of Experience) サービスストア**: 組織内で有効になっている場合は、アーカイブまたは監視機能に必要なストアの数。</span><span class="sxs-lookup"><span data-stu-id="e9acb-169">**Archiving/Call Detail Recording/Quality of Experience services Store**: The number of stores required for Archiving or Monitoring features, if they are enabled in your organization.</span></span>
    
- <span data-ttu-id="e9acb-170">**必要なバックエンドデータベースサーバー (プールが必要)**: 選択したワークロードをサポートするために必要なバックエンドデータベースサーバーの数。</span><span class="sxs-lookup"><span data-stu-id="e9acb-170">**Back End Database Server Required (Pools Required)**: The number of back-end database servers required to support the selected workload.</span></span>
    
<span data-ttu-id="e9acb-171">さらに、[フロントエンドサーバーの合計] の横の行には、予定されているすべてのワークロードを組み合わせたサーバーとネットワークの負荷に関する詳細情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e9acb-171">Additionally, in the row next to Total Front End Servers, more information is provided about the load on your servers and network for all the planned workloads combined.</span></span>
  
- <span data-ttu-id="e9acb-172">**平均 Cpu 負荷**: フロントエンドサーバーあたりの平均 cpu 使用率。</span><span class="sxs-lookup"><span data-stu-id="e9acb-172">**Average CPU Load**: The average CPU usage per Front End server.</span></span>
    
- <span data-ttu-id="e9acb-173">**[ネットワーク (Mbps**)]: 入力した使用モデルをサポートするために必要な帯域幅割り当て。</span><span class="sxs-lookup"><span data-stu-id="e9acb-173">**Network in Mbps**: The required bandwidth allocation to support the usage model that you entered.</span></span>
    
- <span data-ttu-id="e9acb-174">**Gb 単位のメモリ**: 各フロントエンドサーバーに必要なメモリ (ギガバイト単位)。</span><span class="sxs-lookup"><span data-stu-id="e9acb-174">**Memory in GB**: Memory, in gigabytes, required for each Front End server.</span></span>
    
### <a name="adjusting-for-your-processors"></a><span data-ttu-id="e9acb-175">プロセッサに応じた調整</span><span class="sxs-lookup"><span data-stu-id="e9acb-175">Adjusting For Your Processors</span></span>

<span data-ttu-id="e9acb-176">スプレッドシートの CPU 使用率の図では、各 Skype for Business Server 2015 サーバーに、2.26 GHz のデュアルプロセッサ、16 GB 32 以上のメモリ、および少なくとも 72 GB の空きディスク領域を持つ8台以上の 1万 RPM のハードディスクドライブがあることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="e9acb-176">All the CPU usage figures in the spreadsheet assume that each Skype for Business Server 2015 server has a dual processor, hex-core with 2.26 GHz, at least 32 GB of memory, and 8 or more 10,000-RPM hard disk drives with at least 72 GB free disk space.</span></span> <span data-ttu-id="e9acb-177">Skype for Business Server 2019 サーバーごとに、スプレッドシートの CPU 使用率の図は、各サーバーがデュアルプロセッサ、16進コア、2673 v3、少なくとも 64 GB のメモリ、および少なくとも 72 GB のディスク s を持つ8台以上の 1万 RPM のハードディスクドライブを使用していることを前提としています。きれ.</span><span class="sxs-lookup"><span data-stu-id="e9acb-177">For each Skype for Business Server 2019 server, all the CPU usage figures in the spreadsheet assume that each server has a dual processor, hex-core with Intel Xeon E5-2673 v3, at least 64 GB of memory, and 8 or more 10,000-RPM hard disk drives with at least 72 GB free disk space.</span></span>
  
<span data-ttu-id="e9acb-178">サーバーに別のプロセッサが搭載されている場合は、ハードウェアに合わせて図を調整することができます。</span><span class="sxs-lookup"><span data-stu-id="e9acb-178">If your servers have different processors, you can adjust the figures to match your hardware.</span></span>
  
