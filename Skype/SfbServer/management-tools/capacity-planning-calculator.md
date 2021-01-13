---
title: Skype for Business Server の容量計画計算ツール
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: '概要: 容量計算ツールの使い方。'
ms.openlocfilehash: ca7266f5a18e21dbb964f18a791de9b8903a7f0c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802997"
---
# <a name="skype-for-business-server-capacity-planning-calculator"></a><span data-ttu-id="f1302-103">Skype for Business Server の容量計画計算ツール</span><span class="sxs-lookup"><span data-stu-id="f1302-103">Skype for Business Server Capacity Planning Calculator</span></span>
 
<span data-ttu-id="f1302-104">**概要:** 容量計算ツールの使い方。</span><span class="sxs-lookup"><span data-stu-id="f1302-104">**Summary:** How to use the Capacity Calculator Tool.</span></span>

> [!NOTE]
> <span data-ttu-id="f1302-105">この記事では、Skype for Business Server 2015 のダウンロードについて説明しますが、次の場合に適用されます。</span><span class="sxs-lookup"><span data-stu-id="f1302-105">This article references Skype for Business Server 2015 downloads, but it applies to:</span></span>
> - <span data-ttu-id="f1302-106">Skype for Business Server 2019。</span><span class="sxs-lookup"><span data-stu-id="f1302-106">Skype for Business Server 2019.</span></span>
> - <span data-ttu-id="f1302-107">Skype for Business Server 2015。</span><span class="sxs-lookup"><span data-stu-id="f1302-107">Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="f1302-108">[Skype for Business Server 2015 Capacity Calculator](https://www.microsoft.com/download/details.aspx?id=51196)と Skype for Business Server [2019 容量](https://www.microsoft.com/download/details.aspx?id=57509)計算機は[、Skype for Business Planning Tool](https://www.microsoft.com/download/details.aspx?id=50357)と展開に関するドキュメントを拡張します (Skype for Business Server[2015](../plan-your-deployment/plan-your-deployment.md)の展開を計画し[、Skype for Business Server 2019](../../SfBServer2019/plan/plan-your-deployment-2019.md)展開をそれぞれ計画してください)。</span><span class="sxs-lookup"><span data-stu-id="f1302-108">The [Skype for Business Server 2015 Capacity Calculator](https://www.microsoft.com/download/details.aspx?id=51196) and [Skype for Business Server 2019 Capacity Calculator](https://www.microsoft.com/download/details.aspx?id=57509) augment the [Skype for Business Planning Tool](https://www.microsoft.com/download/details.aspx?id=50357) and your deployment documentation ([Plan for your Skype for Business Server 2015 deployment](../plan-your-deployment/plan-your-deployment.md) and [Plan for your Skype for Business Server 2019 deployment](../../SfBServer2019/plan/plan-your-deployment-2019.md) respectively).</span></span> <span data-ttu-id="f1302-109">このガイドを確認し、計画ツールを使用して推奨トポロジを作成したら、電卓を使用します。</span><span class="sxs-lookup"><span data-stu-id="f1302-109">Use the calculator after you have reviewed the guide and created a recommended topology by using the Planning Tool.</span></span>
  
<span data-ttu-id="f1302-110">Skype for Business Server Capacity Calculator は、ユーザー数と組織が使用する通信ツールに基づいてサーバー要件を決定するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="f1302-110">The Skype for Business Server Capacity Calculator helps you determine server requirements based on the number of users and the communication tools your organization uses.</span></span> <span data-ttu-id="f1302-111">ユーザー プロファイルとユーザーに対して有効にする機能を決定した後、電卓を使用して、必要なサーバー、メモリ、帯域幅の数を決定します。</span><span class="sxs-lookup"><span data-stu-id="f1302-111">After you have determined your user profile and the functions you want to enable for your users, use the calculator to determine the number of servers, memory, and bandwidth you will need.</span></span> <span data-ttu-id="f1302-112">このバージョンの電卓では、ディスク I/O 要件に関するガイダンスは提供されません。</span><span class="sxs-lookup"><span data-stu-id="f1302-112">This version of the calculator does not provide guidance for disk I/O requirements.</span></span>
  
<span data-ttu-id="f1302-113">特定のユーザー プロファイルに関する正確で詳細な情報がある場合は、電卓のメリットが最も高い場合があります。</span><span class="sxs-lookup"><span data-stu-id="f1302-113">You can benefit most from the calculator if you have accurate, detailed information about your specific user profile.</span></span> <span data-ttu-id="f1302-114">たとえば、音声が有効なユーザーの割合、1 時間あたりのユーザーあたりの平均通話数、通話時間、および会議での同時ユーザーの割合は、サーバー要件に大きな違いを生み出す可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f1302-114">For example, the percentage of voice-enabled users, average calls per user per hour, call duration, and the percentage of concurrent users in conferences can make a huge difference in server requirements.</span></span> <span data-ttu-id="f1302-115">電卓によって作成される推奨事項の精度は、提供する情報の精度によって異なります。</span><span class="sxs-lookup"><span data-stu-id="f1302-115">The accuracy of the recommendations created by the calculator depends on the accuracy of the information that you provide.</span></span>
  
<span data-ttu-id="f1302-116">計画ツールと容量計画計算ツールを使用したら、提案された負荷と計画された負荷をシミュレートして、Skype for Business Server が適切にプロビジョニングされるのを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f1302-116">Once you have used the Planning Tool and the Capacity Planning Calculator, you should simulate your proposed and planned load to ensure that Skype for Business Server will be adequately provisioned.</span></span> <span data-ttu-id="f1302-117">シミュレートされた負荷の下でストレス テストを実行するには [、Skype for Business Server Stress and Performance Tool](https://www.microsoft.com/download/details.aspx?id=50367) で文書化されている Skype for Business Server Stress and Performance Tool を [使用します](https://technet.microsoft.com/library/mt631400.aspx)。</span><span class="sxs-lookup"><span data-stu-id="f1302-117">To perform stress testing under a simulated load, use the [Skype for Business Server Stress and Performance Tool](https://www.microsoft.com/download/details.aspx?id=50367) documented at [Skype for Business Server Stress and Performance Tool](https://technet.microsoft.com/library/mt631400.aspx).</span></span>
  
## <a name="using-the-capacity-calculator"></a><span data-ttu-id="f1302-118">容量計算機能を使用する</span><span class="sxs-lookup"><span data-stu-id="f1302-118">Using the Capacity Calculator</span></span>

<span data-ttu-id="f1302-119">電卓は、Microsoft Excel スプレッドシートです。</span><span class="sxs-lookup"><span data-stu-id="f1302-119">The calculator is a Microsoft Excel spreadsheet.</span></span> <span data-ttu-id="f1302-120">入力セルはオレンジ色になります。</span><span class="sxs-lookup"><span data-stu-id="f1302-120">Your input cells are colored orange.</span></span> <span data-ttu-id="f1302-121">既定値はセルに入力されますが (Skype for Business Server 2015 の場合、12 台のフロントエンド サーバーがある 1 つのプールに 80,000 ユーザー、16 台のフロント エンド サーバーがある 1 つのプールに 106,000 ユーザーが含まれます)、組織のニーズに合わせてこれらの値を変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f1302-121">Default values are entered in the cells (For Skype for Business Server 2015, 80,000 users in one pool with twelve Front End Servers, while for Skype for Business Server 2019, 106,000 users in one pool with sixteen Front End Servers), but you should change these values to match your organization's needs.</span></span>
  
<span data-ttu-id="f1302-122">使用モデルには、以下のセクションが含まれます。</span><span class="sxs-lookup"><span data-stu-id="f1302-122">The usage model contains the following sections.</span></span> <span data-ttu-id="f1302-123">容量の要件を計算するには、シートの上部から行を 1 行下に移動して、説明に従ってデータを入力します。</span><span class="sxs-lookup"><span data-stu-id="f1302-123">To calculate your capacity requirements, enter data as described starting at the top of the sheet and working down row by row:</span></span> 
  
 <span data-ttu-id="f1302-124">**インスタント メッセージングとプレゼンス**</span><span class="sxs-lookup"><span data-stu-id="f1302-124">**Instant Messaging and Presence**</span></span>
  
- <span data-ttu-id="f1302-125">[ **ユーザー数] に**、一度にサインインするユーザーの数を入力します。</span><span class="sxs-lookup"><span data-stu-id="f1302-125">Under **Number of Users**, type the number of users who will be signed in at once.</span></span> <span data-ttu-id="f1302-126">この数は、通常、プロビジョニングされたユーザーの総数の 80% です。</span><span class="sxs-lookup"><span data-stu-id="f1302-126">This number is typically 80% of the total number of provisioned users.</span></span> <span data-ttu-id="f1302-127">ほとんどの場合、同時ユーザーの 100% が IM とプレゼンスに対して有効になります。</span><span class="sxs-lookup"><span data-stu-id="f1302-127">In most situations, 100% of your concurrent users will be enabled for IM and Presence.</span></span> <span data-ttu-id="f1302-128">既定値は、Skype for Business Server 2015 の場合は 80,000、Skype for Business Server 2019 の場合は 106,000 ユーザーです。</span><span class="sxs-lookup"><span data-stu-id="f1302-128">The default is 80,000 for Skype for Business Server 2015, and 106,000 users for Skype for Business Server 2019.</span></span>
    
- <span data-ttu-id="f1302-129">**連絡先リストの平均連絡先数** は、システム要件の検証に使用している連絡先の数を示します。</span><span class="sxs-lookup"><span data-stu-id="f1302-129">**Average number of contacts in Contact list** indicates the number of contacts that we are using to validate your system requirements.</span></span> <span data-ttu-id="f1302-130">この数値は固定であり、変更する必要がある数値ではありません。</span><span class="sxs-lookup"><span data-stu-id="f1302-130">This number is fixed and not something you should change.</span></span>
    
  <span data-ttu-id="f1302-131">**エンタープライズ VoIP**</span><span class="sxs-lookup"><span data-stu-id="f1302-131">**Enterprise Voice**</span></span>
  
- <span data-ttu-id="f1302-132">[ **ユーザーに対して有効エンタープライズ VoIP]** に、ユーザーが有効になっているユーザーの割合をエンタープライズ VoIP。</span><span class="sxs-lookup"><span data-stu-id="f1302-132">In **Users enabled for Enterprise Voice**, type the percentage of your users enabled for Enterprise Voice.</span></span> <span data-ttu-id="f1302-133">既定値は 60% です。</span><span class="sxs-lookup"><span data-stu-id="f1302-133">The default is 60%.</span></span> 
    
- <span data-ttu-id="f1302-134">[1 時間あたりのユーザーあたりの平均通話数 **(ピーク)]** に、ピーク負荷時に平均ユーザーが参加すると予想される 1 時間あたりの通話数を入力します。</span><span class="sxs-lookup"><span data-stu-id="f1302-134">In **Average number of calls per user per hour (peak)**, type the number of calls per hour you expect the average user to participate in during times of peak load.</span></span> <span data-ttu-id="f1302-135">既定値は 4 です。</span><span class="sxs-lookup"><span data-stu-id="f1302-135">The default is 4.</span></span> 
    
- <span data-ttu-id="f1302-136">[ **メディア バイパスを使用する** 通話の割合] に、仲介サーバーをバイパスするユーザーによる通話の割合を入力します。</span><span class="sxs-lookup"><span data-stu-id="f1302-136">In **Percentage of calls that use media bypass**, type the percentage of calls placed by your users that will bypass the Mediation Server.</span></span> <span data-ttu-id="f1302-137">既定値は 65% ですが、地理的に分散している場合や、自宅で作業するユーザーの割合が多い場合は、低い値になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f1302-137">The default is 65%, but could be lower if you are spread out geographically or have a large percentage of users who work from home.</span></span>
    
- <span data-ttu-id="f1302-138">**UC-PSTN 通話に** 関係する音声ユーザーの割合に、UC-PSTN 通話である組織の通話の割合を入力します。</span><span class="sxs-lookup"><span data-stu-id="f1302-138">In **Percentage of voice users involved in UC-PSTN calls**, type the percentage of your organization's calls which are UC-PSTN phone calls.</span></span> <span data-ttu-id="f1302-139">既定値は 60% です。</span><span class="sxs-lookup"><span data-stu-id="f1302-139">The default is 60%.</span></span>
    
- <span data-ttu-id="f1302-140">**UC-UC 呼び** 出しに関与する音声ユーザーの割合は、UC-UC 通話でのみ有効になる エンタープライズ VoIPユーザーの割合を示します。</span><span class="sxs-lookup"><span data-stu-id="f1302-140">**Percentage of voice users involved in UC-UC calls** shows the percentage of users who are enabled for Enterprise Voice who will be enabled only for UC-UC calls.</span></span> <span data-ttu-id="f1302-141">この番号は、UC-PSTN 通話が有効な音声ユーザーの割合に対して入力 **した値に基づいて計算されます**。</span><span class="sxs-lookup"><span data-stu-id="f1302-141">This number is calculated based on what you input for **Percentage of voice users enabled for UC-PSTN calls**.</span></span> 
    
  <span data-ttu-id="f1302-142">**会議**</span><span class="sxs-lookup"><span data-stu-id="f1302-142">**Conferencing**</span></span>
  
- <span data-ttu-id="f1302-143">[ **同時電話会議のユーザーの** 割合] に、同時に会議に参加するユーザーの割合を入力します。</span><span class="sxs-lookup"><span data-stu-id="f1302-143">In **Percentage of users in concurrent conferences**, type the percentage of users who will be participating in conferences at the same time.</span></span> <span data-ttu-id="f1302-144">既定値は 5% です。</span><span class="sxs-lookup"><span data-stu-id="f1302-144">The default is 5%.</span></span> 
    
- <span data-ttu-id="f1302-145">[Percentage **of conferences with group IM only (no voice)**(グループ IM のみ (音声なし) の電話会議の割合) に、インスタント メッセージングのみを含み、音声を含めない電話会議の割合を入力します。</span><span class="sxs-lookup"><span data-stu-id="f1302-145">In **Percentage of conferences with group IM only (no voice)**, type the percentage of conferences that will involve instant messaging only and do not include audio.</span></span> <span data-ttu-id="f1302-146">既定値は 10% です。</span><span class="sxs-lookup"><span data-stu-id="f1302-146">The default is 10%</span></span>
    
- <span data-ttu-id="f1302-147">[ **ダイヤルイン会議を** 使用するユーザーの割合] に、ダイヤルイン会議を一度に使用する会議の参加者の割合を入力します。</span><span class="sxs-lookup"><span data-stu-id="f1302-147">In **Percentage of users using dial-in conferencing**, type the percentage of participants in conferences who will be using dial-in conferencing at one time.</span></span> <span data-ttu-id="f1302-148">既定値は 15% です。</span><span class="sxs-lookup"><span data-stu-id="f1302-148">The default is 15%.</span></span>
    
- <span data-ttu-id="f1302-149">[ **音声を使用する電話** 会議の割合] に、音声を含める会議の割合を入力します。</span><span class="sxs-lookup"><span data-stu-id="f1302-149">In **Percentage of conferences using voice**, type the percentage of conferences that will include audio.</span></span> 
    
  - <span data-ttu-id="f1302-150">音声会議の 20% に通常のビデオも含める場合は、[ビデオを含める (マルチ ビューなし **) ]** チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="f1302-150">If 20% of your voice conferences will also include regular video, select the **Including video (no Multi View)** check box.</span></span>
    
  - <span data-ttu-id="f1302-151">会議の 20% にマルチビュー ビデオも含まれる場合は、[複数表示を含める] チェック **ボックスを** オンにします。</span><span class="sxs-lookup"><span data-stu-id="f1302-151">If 20% of your conferences will also include Multi-View video, select the **Including Multi View** check box.</span></span>
    
  - <span data-ttu-id="f1302-152">音声会議の 50% にアプリケーション共有も含まれる場合は、[アプリケーション共有を含める] チェック ボックス **を** オンにします。</span><span class="sxs-lookup"><span data-stu-id="f1302-152">If 50% of your voice conferences will also include application sharing, select the **Including application sharing** check box.</span></span>
    
  - <span data-ttu-id="f1302-153">音声会議の 20% に PowerPoint プレゼンテーションなどのデータのアップロードが含まれる場合は、[Web 会議を含める] チェック ボックス **を** オンにします。</span><span class="sxs-lookup"><span data-stu-id="f1302-153">If 20% of your voice conferences include data uploads, such as PowerPoint presentations, select the **Including web conferencing** check box.</span></span>
    
  <span data-ttu-id="f1302-154">**モビリティ**</span><span class="sxs-lookup"><span data-stu-id="f1302-154">**Mobility**</span></span>
  
- <span data-ttu-id="f1302-155">[ **モビリティが有効な** ユーザーの割合] に、モバイル デバイスを使用して Skype for Business Server に接続できるユーザーの割合を入力します。</span><span class="sxs-lookup"><span data-stu-id="f1302-155">In **Percentage of users enabled for Mobility**, type the percentage of your users who will be enabled to connect to Skype for Business Server using mobile devices.</span></span> <span data-ttu-id="f1302-156">既定値は 40% です。</span><span class="sxs-lookup"><span data-stu-id="f1302-156">The default is 40%.</span></span> 
    
<span data-ttu-id="f1302-157">必要な情報を入力すると、容量計算機が要件を見積もります。</span><span class="sxs-lookup"><span data-stu-id="f1302-157">When you have entered all the necessary information, the capacity calculator estimates your requirements.</span></span> <span data-ttu-id="f1302-158">黄色のセルは、Skype for Business Server パフォーマンス ラボで実行されたテストに基づいて、CPU、メモリ、および帯域幅の要件の計算値を示します。</span><span class="sxs-lookup"><span data-stu-id="f1302-158">The yellow cells show calculated values for CPU, memory, and bandwidth requirements based on tests performed in Skype for Business Server performance labs.</span></span> <span data-ttu-id="f1302-159">数値はガイドラインとして提供され、すべてのバリエーションがテストおよび検証されるという方法ではありません。</span><span class="sxs-lookup"><span data-stu-id="f1302-159">The numbers are provided as a guideline, not every single variation is tested and validated.</span></span> <span data-ttu-id="f1302-160">次の値が計算されます。</span><span class="sxs-lookup"><span data-stu-id="f1302-160">The following values are calculated:</span></span> 
  
- <span data-ttu-id="f1302-161">**フロントエンド CPU**: テストで使用したサーバーと同じ仕様の 1 つのフロントエンド サーバーによって負荷全体が処理されている場合の CPU 使用率の割合 (この記事の最後の説明を参照)。</span><span class="sxs-lookup"><span data-stu-id="f1302-161">**Front End CPU**: Percentage of CPU usage if the entire load were being handled by one Front End Server of the same specifications as the server that was used in testing (see the description at the end of this article).</span></span>
    
- <span data-ttu-id="f1302-162">**ネットワーク (Mbps):** 対応するワークロードの帯域幅要件 (メガビット/秒 (Mbps) 単位)。</span><span class="sxs-lookup"><span data-stu-id="f1302-162">**Network in Mbps**: Bandwidth requirements in megabits per second (Mbps) for the corresponding workload.</span></span>
    
- <span data-ttu-id="f1302-163">**メモリ (GB)**: 対応するワークロードに必要なメモリ (ギガバイト (GB) 単位)。</span><span class="sxs-lookup"><span data-stu-id="f1302-163">**Memory in GB**: Memory required in gigabytes (GB) for the corresponding workload.</span></span>
    
<span data-ttu-id="f1302-164">緑色のセルには、入力した使用モデルの推奨事項が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f1302-164">The green cells show recommendations for the usage model that you entered.</span></span> 
  
- <span data-ttu-id="f1302-165">**フロント** エンド サーバーの合計 : 必要な物理サーバーの数は、デュアル プロセッサを搭載した Skype for Business Server 2015 を実行する専用サーバー、2,260 メガサイクルの 16 コア、または Intel Xeon E5-2673 v3 を搭載した Skype for Business Server 2019、デュアル プロセッサ、16 コアに基づいて行います。</span><span class="sxs-lookup"><span data-stu-id="f1302-165">**Total Front End Servers**: The number of physical servers required are based on dedicated servers running Skype for Business Server 2015 with dual processor, hex-core, with 2,260 megacycles, or Skype for Business Server 2019 with Intel Xeon E5-2673 v3, dual processor, hex-core.</span></span>
    
    <span data-ttu-id="f1302-166">ハイパースレッジを有効にすることで、オーディオ/ビデオをサポートするサーバーのパフォーマンスが向上する実証済みである点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="f1302-166">Note that enabling hyperthreading is recommended and has been proven to improve performance for servers that support audio/video.</span></span>
    
- <span data-ttu-id="f1302-167">**エッジ サーバー**: エッジ サーバーを介して通信しているすべての同時ユーザーの 30% に基づいて、必要なエッジ サーバーの数。</span><span class="sxs-lookup"><span data-stu-id="f1302-167">**Edge Servers**: The number of Edge Servers required, based on 30% of all concurrent users communicating through the Edge Servers.</span></span> <span data-ttu-id="f1302-168">このパーセンテージは電卓で変更できません。</span><span class="sxs-lookup"><span data-stu-id="f1302-168">This percentage cannot be changed in the calculator.</span></span> 
    
- <span data-ttu-id="f1302-169">**アーカイブ/通話詳細記録/Quality of Experience Services Store**: 組織で有効になっている場合、アーカイブ機能または監視機能に必要なストアの数。</span><span class="sxs-lookup"><span data-stu-id="f1302-169">**Archiving/Call Detail Recording/Quality of Experience services Store**: The number of stores required for Archiving or Monitoring features, if they are enabled in your organization.</span></span>
    
- <span data-ttu-id="f1302-170">**必要なバック エンド データベース サーバー (プールが必要)**: 選択したワークロードをサポートするために必要なバック エンド データベース サーバーの数。</span><span class="sxs-lookup"><span data-stu-id="f1302-170">**Back End Database Server Required (Pools Required)**: The number of back-end database servers required to support the selected workload.</span></span>
    
<span data-ttu-id="f1302-171">さらに、フロント エンド サーバーの合計の横の行には、計画済みのすべてのワークロードを組み合わせたサーバーとネットワークの負荷に関する詳細情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f1302-171">Additionally, in the row next to Total Front End Servers, more information is provided about the load on your servers and network for all the planned workloads combined.</span></span>
  
- <span data-ttu-id="f1302-172">**平均 CPU 負荷**: フロント エンド サーバーあたりの平均 CPU 使用率。</span><span class="sxs-lookup"><span data-stu-id="f1302-172">**Average CPU Load**: The average CPU usage per Front End server.</span></span>
    
- <span data-ttu-id="f1302-173">**ネットワーク (Mbps):** 入力した使用モデルをサポートするために必要な帯域幅割り当て。</span><span class="sxs-lookup"><span data-stu-id="f1302-173">**Network in Mbps**: The required bandwidth allocation to support the usage model that you entered.</span></span>
    
- <span data-ttu-id="f1302-174">**メモリ (GB)**: 各フロントエンド サーバーに必要なメモリ (ギガバイト単位)。</span><span class="sxs-lookup"><span data-stu-id="f1302-174">**Memory in GB**: Memory, in gigabytes, required for each Front End server.</span></span>
    
### <a name="adjusting-for-your-processors"></a><span data-ttu-id="f1302-175">プロセッサに応じた調整</span><span class="sxs-lookup"><span data-stu-id="f1302-175">Adjusting For Your Processors</span></span>

<span data-ttu-id="f1302-176">スプレッドシートのすべての CPU 使用率の数値は、各 Skype for Business Server 2015 サーバーにデュアル プロセッサ、2.26 GHz、32 GB 以上のメモリ、8 台以上の 10,000 RPM ハード ディスク ドライブ (少なくとも 72 GB の空きディスク領域を持つ 16 コア) が搭載されている前提です。</span><span class="sxs-lookup"><span data-stu-id="f1302-176">All the CPU usage figures in the spreadsheet assume that each Skype for Business Server 2015 server has a dual processor, hex-core with 2.26 GHz, at least 32 GB of memory, and 8 or more 10,000-RPM hard disk drives with at least 72 GB free disk space.</span></span> <span data-ttu-id="f1302-177">Skype for Business Server 2019 サーバーごとに、スプレッドシートのすべての CPU 使用率の数値は、各サーバーにデュアル プロセッサ、Intel Xeon E5-2673 v3 を搭載した 16 コア、少なくとも 64 GB のメモリ、72 GB 以上の空きディスク領域を持つ 10,000 RPM のハード ディスク ドライブが 8 台以上あると想定しています。</span><span class="sxs-lookup"><span data-stu-id="f1302-177">For each Skype for Business Server 2019 server, all the CPU usage figures in the spreadsheet assume that each server has a dual processor, hex-core with Intel Xeon E5-2673 v3, at least 64 GB of memory, and 8 or more 10,000-RPM hard disk drives with at least 72 GB free disk space.</span></span>
  
<span data-ttu-id="f1302-178">サーバーのプロセッサが異なる場合は、ハードウェアに合わせて数値を調整できます。</span><span class="sxs-lookup"><span data-stu-id="f1302-178">If your servers have different processors, you can adjust the figures to match your hardware.</span></span>
  
