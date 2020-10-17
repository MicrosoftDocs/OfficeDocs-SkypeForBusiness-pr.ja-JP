---
title: Lync Server 2013 の容量計画の計算機
description: Lync Server 2013 容量計画の計算機。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using the Lync Server 2013 capacity planning calculator
ms:assetid: e86c1f05-1393-408a-9549-6001572ec50d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362852(v=OCS.15)
ms:contentKeyID: 56280894
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9f78019c98cf280f38249ac52cd063cede5319af
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565143"
---
# <a name="using-the-capacity-planning-calculator-for-lync-server-2013"></a><span data-ttu-id="be2f5-103">Lync Server 2013 の容量計画の計算機の使用</span><span class="sxs-lookup"><span data-stu-id="be2f5-103">Using the capacity planning calculator for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="be2f5-104">_**トピックの最終更新日:** 2013-11-21_</span><span class="sxs-lookup"><span data-stu-id="be2f5-104">_**Topic Last Modified:** 2013-11-21_</span></span>

<span data-ttu-id="be2f5-105">Microsoft® Lync™ Server 2013 の容量計画の計算機は、でダウンロードでき <https://www.microsoft.com/download/details.aspx?id=36828> ます。</span><span class="sxs-lookup"><span data-stu-id="be2f5-105">The Microsoft® Lync™ Server 2013 capacity planning calculator is available for download at <https://www.microsoft.com/download/details.aspx?id=36828>.</span></span> <span data-ttu-id="be2f5-106">これは、組織で有効になっているユーザーと通信モダリティの数に基づいてサーバーの要件を決定するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="be2f5-106">It is designed to assist you in determining server requirements based on numbers of users and communication modalities that are enabled at your organization.</span></span> <span data-ttu-id="be2f5-107">組織のプロファイルを入力すると、電卓にはトポロジの計画に役立つ推奨事項が表示されます。</span><span class="sxs-lookup"><span data-stu-id="be2f5-107">You enter your organization’s profile, and the calculator provides recommendations that help you plan your topology.</span></span>

<span data-ttu-id="be2f5-108">計算機によって作成された推奨事項は、計画のためにのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="be2f5-108">The recommendations created by the calculator are for planning purposes only.</span></span> <span data-ttu-id="be2f5-109">実際の負荷シミュレーションは、Lync Server 2013 が適切にプロビジョニングされていることを確認するために必要です。</span><span class="sxs-lookup"><span data-stu-id="be2f5-109">Actual load simulation is required to ensure that Lync Server 2013 is adequately provisioned.</span></span> <span data-ttu-id="be2f5-110">シミュレートされた負荷の下でストレステストを実行するには、 [Lync Server 2013 ストレスおよびパフォーマンスツール](https://go.microsoft.com/fwlink/?linkid=282724)を使用します。</span><span class="sxs-lookup"><span data-stu-id="be2f5-110">To perform stress testing under a simulated load, use the [Lync Server 2013 Stress and Performance Tool](https://go.microsoft.com/fwlink/?linkid=282724).</span></span>

<span data-ttu-id="be2f5-111">ユーザーに対して有効にするユーザープロファイルとモダリティを決定したら、計算機を使用して、必要なサーバー、メモリ、および帯域幅を計画します。</span><span class="sxs-lookup"><span data-stu-id="be2f5-111">After you have determined your user profile and the modalities that you want to enable for your users, it is time to use the calculator to plan the number of servers, memory, and bandwidth that you need.</span></span> <span data-ttu-id="be2f5-112">この電卓のバージョンでは、ディスク i/o の要件についてのガイダンスは提供されていません。</span><span class="sxs-lookup"><span data-stu-id="be2f5-112">This version of the calculator does not provide guidance for disk I/O requirements.</span></span>

<span data-ttu-id="be2f5-113">この電卓は、 [Microsoft Lync server](https://go.microsoft.com/fwlink/?linkid=282725) と [microsoft lync server](lync-server-2013-planning.md)を補完します。</span><span class="sxs-lookup"><span data-stu-id="be2f5-113">This calculator complements the [Microsoft Lync Server](https://go.microsoft.com/fwlink/?linkid=282725) and [Microsoft Lync Server](lync-server-2013-planning.md).</span></span> <span data-ttu-id="be2f5-114">ガイドを確認し、計画ツールを使用して推奨されるトポロジを作成したら、電卓を使用します。</span><span class="sxs-lookup"><span data-stu-id="be2f5-114">Use the calculator after you have reviewed the guide and created a recommended topology by using the Planning Tool.</span></span>

<span data-ttu-id="be2f5-115">特定のユーザープロファイルに関する詳細情報を正確に把握している場合は、計算機を使用すると便利です。</span><span class="sxs-lookup"><span data-stu-id="be2f5-115">You can benefit most from the calculator if you have accurate, detailed information about your specific user profile.</span></span> <span data-ttu-id="be2f5-116">たとえば、音声が有効なユーザーの割合、1時間あたりの平均通話、通話時間、会議での同時ユーザー数の割合は、サーバーの要件に大きな違いを持たせることができます。</span><span class="sxs-lookup"><span data-stu-id="be2f5-116">For example, the percentage of voice-enabled users, average calls per user per hour, call duration, and the percentage of concurrent users in conferences can make a huge difference in server requirements.</span></span> <span data-ttu-id="be2f5-117">計算機によって作成された推奨事項の精度は、提供する情報の正確性によって決まります。</span><span class="sxs-lookup"><span data-stu-id="be2f5-117">The accuracy of the recommendations created by the calculator depends on the accuracy of the information that you provide.</span></span>

<div>

## <a name="using-the-capacity-calculator"></a><span data-ttu-id="be2f5-118">容量計算機の使用</span><span class="sxs-lookup"><span data-stu-id="be2f5-118">Using the Capacity Calculator</span></span>

<span data-ttu-id="be2f5-119">電卓は、Microsoft Excel®スプレッドシートです。</span><span class="sxs-lookup"><span data-stu-id="be2f5-119">The calculator is a Microsoft Excel® spreadsheet.</span></span> <span data-ttu-id="be2f5-120">オレンジ色のセルは入力用です。</span><span class="sxs-lookup"><span data-stu-id="be2f5-120">Orange-colored cells are for input from you.</span></span> <span data-ttu-id="be2f5-121">既定値が入力されます (1 つのプールのユーザーが12台のフロントエンドサーバーで8万ユーザー)。ただし、組織のニーズに応じてこれらの値を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="be2f5-121">Default values are entered (80,000 users in one pool with twelve Front End Servers), but you can change these values according to your organization’s needs.</span></span>

<span data-ttu-id="be2f5-122">利用状況モデルには、以下のセクションが含まれています。</span><span class="sxs-lookup"><span data-stu-id="be2f5-122">The usage model contains the following sections.</span></span> <span data-ttu-id="be2f5-123">容量の要件を計算するには、以下の説明に従ってデータを入力します。</span><span class="sxs-lookup"><span data-stu-id="be2f5-123">To calculate your capacity requirements, enter data as described:</span></span>

<span data-ttu-id="be2f5-124">**インスタント メッセージングとプレゼンス**</span><span class="sxs-lookup"><span data-stu-id="be2f5-124">**Instant Messaging and Presence**</span></span>

  - <span data-ttu-id="be2f5-125">[ユーザー数] に、同時にサインインするユーザーの数を入力します。</span><span class="sxs-lookup"><span data-stu-id="be2f5-125">Under Number of Users, type the number of users who will be concurrently signed in.</span></span> <span data-ttu-id="be2f5-126">この数値は、通常、プロビジョニングされたユーザーの総数の80% です。</span><span class="sxs-lookup"><span data-stu-id="be2f5-126">This number is typically 80% of the total number of provisioned users.</span></span> <span data-ttu-id="be2f5-127">ほとんどの場合、同時ユーザーの100% が IM とプレゼンスに対して有効になります。</span><span class="sxs-lookup"><span data-stu-id="be2f5-127">In most situations, 100% of your concurrent users will be enabled for IM and Presence.</span></span> <span data-ttu-id="be2f5-128">既定値は8万です。</span><span class="sxs-lookup"><span data-stu-id="be2f5-128">The default is 80,000.</span></span>

  - <span data-ttu-id="be2f5-129">連絡先リスト内の平均連絡先数は、システム要件の検証に使用している連絡先の数を示します。</span><span class="sxs-lookup"><span data-stu-id="be2f5-129">Average number of contacts in Contact list indicates the number of contacts that we are using to validate your system requirements.</span></span> <span data-ttu-id="be2f5-130">この数値は変更できません。</span><span class="sxs-lookup"><span data-stu-id="be2f5-130">This number is not changeable.</span></span>

<span data-ttu-id="be2f5-131">**エンタープライズ VoIP**</span><span class="sxs-lookup"><span data-stu-id="be2f5-131">**Enterprise Voice**</span></span>

  - <span data-ttu-id="be2f5-132">[エンタープライズ Voip が有効なユーザー] で、エンタープライズ Voip が有効になっているユーザーの割合を入力します。</span><span class="sxs-lookup"><span data-stu-id="be2f5-132">In Users enabled for Enterprise Voice, type the percentage of your users who are enabled for Enterprise Voice.</span></span> <span data-ttu-id="be2f5-133">既定値は60% です。</span><span class="sxs-lookup"><span data-stu-id="be2f5-133">The default is 60%.</span></span>

  - <span data-ttu-id="be2f5-134">[1 時間あたりの平均通話数 (ピーク時)] で、ピーク負荷が発生した時間帯に、平均的なユーザーが参加することが予想される1時間あたりの通話数を入力します。</span><span class="sxs-lookup"><span data-stu-id="be2f5-134">In Average number of calls per user per hour (peak), type the number of calls per hour that you expect the average user to participate in during times of peak load.</span></span> <span data-ttu-id="be2f5-135">既定値は 4 です。</span><span class="sxs-lookup"><span data-stu-id="be2f5-135">The default is 4.</span></span>

  - <span data-ttu-id="be2f5-136">[メディアバイパスを使用する通話の割合] で、ユーザーが仲介サーバーをバイパスする通話の割合を入力します。</span><span class="sxs-lookup"><span data-stu-id="be2f5-136">In Percentage of calls that use media bypass, type the percentage of calls placed by your users that will bypass the Mediation Server.</span></span> <span data-ttu-id="be2f5-137">既定値は65% です。</span><span class="sxs-lookup"><span data-stu-id="be2f5-137">The default is 65%.</span></span>

  - <span data-ttu-id="be2f5-138">[UC PSTN 通話に参加している音声ユーザーの割合] で、組織の着信のうち、UC PSTN 電話での通話の割合を入力します。</span><span class="sxs-lookup"><span data-stu-id="be2f5-138">In Percentage of voice users involved in UC-PSTN calls, type the percentage of your organization’s calls which are UC-PSTN phone calls.</span></span> <span data-ttu-id="be2f5-139">既定値は60% です。</span><span class="sxs-lookup"><span data-stu-id="be2f5-139">The default is 60%</span></span>

  - <span data-ttu-id="be2f5-140">[UC-UC 通話に参加している音声ユーザーの割合 (%) によって、エンタープライズ Voip が有効になっているユーザーの割合が UC uc 呼び出しに対してのみ有効になっていることが示されます。</span><span class="sxs-lookup"><span data-stu-id="be2f5-140">In Percentage of voice users involved in UC-UC calls shows the percentage of users who are enabled for Enterprise Voice who will be enabled only for UC-UC calls.</span></span> <span data-ttu-id="be2f5-141">この数値は、UC 通話に対して有効になっている音声ユーザーのパーセンテージに対して入力した値に基づいて計算されます。</span><span class="sxs-lookup"><span data-stu-id="be2f5-141">This number is calculated based on what you input for Percentage of voice users enabled for UC-PSTN calls.</span></span>

<span data-ttu-id="be2f5-142">**会議**</span><span class="sxs-lookup"><span data-stu-id="be2f5-142">**Conferencing**</span></span>

  - <span data-ttu-id="be2f5-143">同時電話会議のユーザー数の割合に、電話会議に同時に参加するユーザーの割合を入力します。</span><span class="sxs-lookup"><span data-stu-id="be2f5-143">In Percentage of users in concurrent conferences, type the percentage of users who will be concurrently participating in conferences.</span></span> <span data-ttu-id="be2f5-144">既定値は5% です。</span><span class="sxs-lookup"><span data-stu-id="be2f5-144">The default is 5%.</span></span>

  - <span data-ttu-id="be2f5-145">[グループ IM のみの会議のパーセンテージ (音声なし)] で、会議がインスタントメッセージングにのみ関与する電話会議の割合を入力します。つまり、オーディオコンポーネントは含まれていません。</span><span class="sxs-lookup"><span data-stu-id="be2f5-145">In Percentage of conferences with group IM only (no voice), type the percentage of conferences whose conferences will involve instant messaging only; that is, that do not include an audio component.</span></span> <span data-ttu-id="be2f5-146">既定値は10% です。</span><span class="sxs-lookup"><span data-stu-id="be2f5-146">The default is 10%</span></span>

  - <span data-ttu-id="be2f5-147">[ダイヤルイン会議を使用しているユーザーの割合] で、ダイヤルイン会議を使用する会議の同時参加者数の割合を入力します。</span><span class="sxs-lookup"><span data-stu-id="be2f5-147">In Percentage of users using dial-in conferencing, type the percentage of concurrent participants in conferences who will be using dial-in conferencing.</span></span> <span data-ttu-id="be2f5-148">既定値は15% です。</span><span class="sxs-lookup"><span data-stu-id="be2f5-148">The default is 15%.</span></span>

  - <span data-ttu-id="be2f5-149">[音声を使用する電話会議の割合] で、オーディオコンポーネントを含む電話会議の割合を入力します。</span><span class="sxs-lookup"><span data-stu-id="be2f5-149">In Percentage of conferences using voice, type the percentage of conferences that will include an audio component.</span></span>
    
      - <span data-ttu-id="be2f5-150">音声会議の20% が通常のビデオも含まれる場合は、[ビデオを含む (マルチビューを使用しない)] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="be2f5-150">If 20% of your voice conferences will also include regular video, select the Including video (no Multi View) check box.</span></span>
    
      - <span data-ttu-id="be2f5-151">電話会議の20% がマルチビュービデオも含まれている場合は、[マルチビューを含める] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="be2f5-151">If 20% of your conferences will also include Multi-View video, select the Including Multi View check box.</span></span>
    
      - <span data-ttu-id="be2f5-152">音声会議の50% がアプリケーション共有も含まれる場合は、[アプリケーション共有を含める] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="be2f5-152">If 50% of your voice conferences will also include application sharing, select the Including application sharing check box.</span></span>
    
      - <span data-ttu-id="be2f5-153">音声会議の20% が、Microsoft PowerPoint®プレゼンテーションなどのデータアップロードを含んでいる場合は、[web 会議を含める] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="be2f5-153">If 20% of your voice conferences include data uploads, such as Microsoft PowerPoint® presentations, select the Including web conferencing check box.</span></span>

<span data-ttu-id="be2f5-154">**モビリティ**</span><span class="sxs-lookup"><span data-stu-id="be2f5-154">**Mobility**</span></span>

  - <span data-ttu-id="be2f5-155">[モビリティが有効なユーザー数の割合] で、モバイルデバイスを使用して Lync Server への接続を有効にするユーザーの割合を入力します。</span><span class="sxs-lookup"><span data-stu-id="be2f5-155">In Percentage of users enabled for Mobility, type the percentage of your users who will be enabled to connect to Lync Server using mobile devices.</span></span> <span data-ttu-id="be2f5-156">既定値は40% です。</span><span class="sxs-lookup"><span data-stu-id="be2f5-156">The default is 40%.</span></span>

<span data-ttu-id="be2f5-157">必要な情報をすべて入力したら、容量計算機が要件を予測します。</span><span class="sxs-lookup"><span data-stu-id="be2f5-157">When you have entered all the necessary information, the capacity calculator estimates your requirements.</span></span> <span data-ttu-id="be2f5-158">黄色のセルには、Lync Server 2013 パフォーマンスラボで実行されたテストに基づいた CPU、メモリ、および帯域幅の要件の計算値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="be2f5-158">The yellow cells show calculated values for CPU, memory, and bandwidth requirements based on tests performed in Lync Server 2013 performance labs.</span></span> <span data-ttu-id="be2f5-159">この番号はガイドラインとして提供されており、すべてのバリエーションがテストおよび検証されるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="be2f5-159">The numbers are provided as a guideline, not every single variation is tested and validated.</span></span> <span data-ttu-id="be2f5-160">次の値が計算されます。</span><span class="sxs-lookup"><span data-stu-id="be2f5-160">The following values are calculated:</span></span>

  - <span data-ttu-id="be2f5-161">フロントエンド CPU: 負荷全体が、Microsoft のテストで使用したサーバーと同じ仕様の1台のフロントエンドサーバーによって処理された場合の CPU 使用率の割合。</span><span class="sxs-lookup"><span data-stu-id="be2f5-161">Front End CPU: Percentage of CPU usage if the entire load were being handled by one Front End Server of the same specifications as the server that was used in Microsoft testing.</span></span>

  - <span data-ttu-id="be2f5-162">[ネットワーク (Mbps)]: 対応するワークロードの帯域幅要件 (メガビット/秒 (Mbps))。</span><span class="sxs-lookup"><span data-stu-id="be2f5-162">Network in Mbps: Bandwidth requirements in megabits per second (Mbps) for the corresponding workload.</span></span>

  - <span data-ttu-id="be2f5-163">GB 単位のメモリ: 対応するワークロードに必要なメモリ (gb)。</span><span class="sxs-lookup"><span data-stu-id="be2f5-163">Memory in GB: Memory required in gigabytes (GB) for the corresponding workload.</span></span>

<span data-ttu-id="be2f5-164">緑色のセルには、入力した使用モデルの推奨事項が表示されます。</span><span class="sxs-lookup"><span data-stu-id="be2f5-164">The green cells show recommendations for the usage model that you entered.</span></span>

  - <span data-ttu-id="be2f5-165">フロントエンドサーバーの合計: 必要な物理サーバーの数は、Lync Server 2013 を実行している専用サーバー (16 ビットコア、2260メガサイクル) に基づいています。</span><span class="sxs-lookup"><span data-stu-id="be2f5-165">Total Front End Servers: The number of physical servers required are based on dedicated servers running Lync Server 2013 with dual processor, hex-core, with 2,260 megacycles.</span></span>

  - <span data-ttu-id="be2f5-166">ハイパースレッディングを有効にすることをお勧めします。また、音声/ビデオをサポートするサーバーのパフォーマンスを向上させることが実証されています。</span><span class="sxs-lookup"><span data-stu-id="be2f5-166">Note that enabling hyperthreading is recommended and has been proven to improve performance for servers that support audio/video.</span></span>

  - <span data-ttu-id="be2f5-167">エッジサーバー: エッジサーバーを介して通信するすべての同時ユーザーの30% に基づいて、必要なエッジサーバーの数。</span><span class="sxs-lookup"><span data-stu-id="be2f5-167">Edge Servers: The number of Edge Servers required, based on 30% of all concurrent users communicating through the Edge Servers.</span></span> <span data-ttu-id="be2f5-168">このパーセンテージは、電卓では変更できません。</span><span class="sxs-lookup"><span data-stu-id="be2f5-168">This percentage cannot be changed in the calculator.</span></span>

  - <span data-ttu-id="be2f5-169">アーカイブ/通話詳細記録/qoe (Quality of Experience) サービスストア: 組織内で有効になっている場合は、アーカイブまたは監視機能に必要なストアの数。</span><span class="sxs-lookup"><span data-stu-id="be2f5-169">Archiving/Call Detail Recording/Quality of Experience services Store: The number of stores required for Archiving or Monitoring features, if they are enabled in your organization.</span></span>

  - <span data-ttu-id="be2f5-170">必要なバックエンドデータベースサーバー (プールが必要): 選択したワークロードをサポートするために必要なバックエンドデータベースサーバーの数。</span><span class="sxs-lookup"><span data-stu-id="be2f5-170">Back End Database Server Required (Pools Required): The number of back-end database servers required to support the selected workload.</span></span>

<span data-ttu-id="be2f5-171">さらに、[フロントエンドサーバーの合計] の横の行には、予定されているすべてのワークロードを組み合わせたサーバーとネットワークの負荷に関する詳細情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="be2f5-171">Additionally, in the row next to Total Front End Servers, more information is provided about the load on your servers and network for all the planned workloads combined.</span></span>

  - <span data-ttu-id="be2f5-172">平均 CPU 負荷: フロントエンドサーバーあたりの平均 CPU 使用率。</span><span class="sxs-lookup"><span data-stu-id="be2f5-172">Average CPU Load: The average CPU usage per Front End server.</span></span>

  - <span data-ttu-id="be2f5-173">[ネットワーク (Mbps)]: 入力した使用モデルをサポートするために必要な帯域幅割り当て。</span><span class="sxs-lookup"><span data-stu-id="be2f5-173">Network in Mbps: The required bandwidth allocation to support the usage model that you entered.</span></span>

  - <span data-ttu-id="be2f5-174">GB 単位のメモリ: 各フロントエンドサーバーに必要なメモリ (ギガバイト単位)。</span><span class="sxs-lookup"><span data-stu-id="be2f5-174">Memory in GB: Memory, in gigabytes, required for each Front End server.</span></span>

</div>

<div>

## <a name="adjusting-for-your-processors"></a><span data-ttu-id="be2f5-175">プロセッサに応じた調整</span><span class="sxs-lookup"><span data-stu-id="be2f5-175">Adjusting For Your Processors</span></span>

<span data-ttu-id="be2f5-176">スプレッドシートの CPU 使用率の図では、各サーバーが 2.26 GHz のデュアルプロセッサ、少なくとも 32 GB のメモリ、および少なくとも 72 GB のディスクの空き容量を持つ8台以上の 1万 RPM のハードディスクドライブを使用していることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="be2f5-176">All the CPU usage figures in the spreadsheet assume that each server has a dual processor, hex-core with 2.26 GHz, at least 32 GB of memory, and 8 or more 10,000-RPM hard disk drives with at least 72 GB free disk space.</span></span>

<span data-ttu-id="be2f5-177">サーバーに別のプロセッサが搭載されている場合は、ハードウェアに合わせて図を調整することができます。</span><span class="sxs-lookup"><span data-stu-id="be2f5-177">If your servers have different processors, you can adjust the figures to match your hardware.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

