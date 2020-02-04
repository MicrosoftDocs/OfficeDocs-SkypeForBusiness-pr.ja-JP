---
title: Lync Server 2013 キャパシティプランニング電卓
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
ms.openlocfilehash: 26abf069d7c1686fe8abb804d6de4508ba6333fe
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742367"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-the-capacity-planning-calculator-for-lync-server-2013"></a><span data-ttu-id="c4ab4-102">Lync Server 2013 のキャパシティプランニング電卓を使用する</span><span class="sxs-lookup"><span data-stu-id="c4ab4-102">Using the capacity planning calculator for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c4ab4-103">_**最終更新日:** 2013-11-21_</span><span class="sxs-lookup"><span data-stu-id="c4ab4-103">_**Topic Last Modified:** 2013-11-21_</span></span>

<span data-ttu-id="c4ab4-104">Microsoft® Lync™ Server 2013 キャパシティプランニングの電卓は、から<http://www.microsoft.com/en-us/download/details.aspx?id=36828>ダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="c4ab4-104">The Microsoft® Lync™ Server 2013 capacity planning calculator is available for download at <http://www.microsoft.com/en-us/download/details.aspx?id=36828>.</span></span> <span data-ttu-id="c4ab4-105">組織で有効になっているユーザーと通信モダリティの数に基づいてサーバー要件を決定するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="c4ab4-105">It is designed to assist you in determining server requirements based on numbers of users and communication modalities that are enabled at your organization.</span></span> <span data-ttu-id="c4ab4-106">組織のプロファイルを入力します。電卓には、トポロジの計画に役立つ推奨事項が記載されています。</span><span class="sxs-lookup"><span data-stu-id="c4ab4-106">You enter your organization’s profile, and the calculator provides recommendations that help you plan your topology.</span></span>

<span data-ttu-id="c4ab4-107">電卓によって作成された推奨事項は、計画用です。</span><span class="sxs-lookup"><span data-stu-id="c4ab4-107">The recommendations created by the calculator are for planning purposes only.</span></span> <span data-ttu-id="c4ab4-108">Lync Server 2013 が適切にプロビジョニングされていることを確認するには、実際の負荷シミュレーションが必要です。</span><span class="sxs-lookup"><span data-stu-id="c4ab4-108">Actual load simulation is required to ensure that Lync Server 2013 is adequately provisioned.</span></span> <span data-ttu-id="c4ab4-109">シミュレートされたロードの下でストレステストを実行するには、 [Lync Server 2013 応力とパフォーマンスツール](http://go.microsoft.com/fwlink/?linkid=282724)を使用します。</span><span class="sxs-lookup"><span data-stu-id="c4ab4-109">To perform stress testing under a simulated load, use the [Lync Server 2013 Stress and Performance Tool](http://go.microsoft.com/fwlink/?linkid=282724).</span></span>

<span data-ttu-id="c4ab4-110">ユーザーに対して有効にするユーザープロファイルとモダリティを決定したら、計算機を使って、必要なサーバー、メモリ、帯域幅の数を計画します。</span><span class="sxs-lookup"><span data-stu-id="c4ab4-110">After you have determined your user profile and the modalities that you want to enable for your users, it is time to use the calculator to plan the number of servers, memory, and bandwidth that you need.</span></span> <span data-ttu-id="c4ab4-111">計算機のこのバージョンでは、ディスク I/O 要件に対するガイダンスは提供しません。</span><span class="sxs-lookup"><span data-stu-id="c4ab4-111">This version of the calculator does not provide guidance for disk I/O requirements.</span></span>

<span data-ttu-id="c4ab4-112">この電卓は、 [Microsoft Lync server](http://go.microsoft.com/fwlink/?linkid=282725)と[microsoft lync server](lync-server-2013-planning.md)を補完します。</span><span class="sxs-lookup"><span data-stu-id="c4ab4-112">This calculator complements the [Microsoft Lync Server](http://go.microsoft.com/fwlink/?linkid=282725) and [Microsoft Lync Server](lync-server-2013-planning.md).</span></span> <span data-ttu-id="c4ab4-113">この計算機は、ガイドをよくお読みになり、計画ツールを使って推奨のトポロジを作成後に使用してください。</span><span class="sxs-lookup"><span data-stu-id="c4ab4-113">Use the calculator after you have reviewed the guide and created a recommended topology by using the Planning Tool.</span></span>

<span data-ttu-id="c4ab4-p105">特定のユーザー プロファイルに関する正確な詳細情報があれば、計算機を最大限に活用できます。たとえば、音声対応ユーザーの割合、1 時間あたりの各ユーザーの平均通話数、通話時間、会議での同時ユーザーの割合によって、サーバー要件が大幅に変わる可能性があります。計算機によって作成される推奨事項の精度は、提供する情報の精度によって変わります。</span><span class="sxs-lookup"><span data-stu-id="c4ab4-p105">You can benefit most from the calculator if you have accurate, detailed information about your specific user profile. For example, the percentage of voice-enabled users, average calls per user per hour, call duration, and the percentage of concurrent users in conferences can make a huge difference in server requirements. The accuracy of the recommendations created by the calculator depends on the accuracy of the information that you provide.</span></span>

<div>

## <a name="using-the-capacity-calculator"></a><span data-ttu-id="c4ab4-117">容量計算機の使用</span><span class="sxs-lookup"><span data-stu-id="c4ab4-117">Using the Capacity Calculator</span></span>

<span data-ttu-id="c4ab4-118">電卓は、Microsoft Excel®スプレッドシートです。</span><span class="sxs-lookup"><span data-stu-id="c4ab4-118">The calculator is a Microsoft Excel® spreadsheet.</span></span> <span data-ttu-id="c4ab4-119">オレンジ色のセルは、入力用のものです。</span><span class="sxs-lookup"><span data-stu-id="c4ab4-119">Orange-colored cells are for input from you.</span></span> <span data-ttu-id="c4ab4-120">既定値は、入力されています (1 つのプールに12個のフロントエンドサーバーがある場合は8万ユーザー)。ただし、組織のニーズに応じてこれらの値を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="c4ab4-120">Default values are entered (80,000 users in one pool with twelve Front End Servers), but you can change these values according to your organization’s needs.</span></span>

<span data-ttu-id="c4ab4-121">使用モデルには次のセクションが含まれます。</span><span class="sxs-lookup"><span data-stu-id="c4ab4-121">The usage model contains the following sections.</span></span> <span data-ttu-id="c4ab4-122">キャパシティ要件を計算するには、以下のようにデータを入力します。</span><span class="sxs-lookup"><span data-stu-id="c4ab4-122">To calculate your capacity requirements, enter data as described:</span></span>

<span data-ttu-id="c4ab4-123">**インスタント メッセージングとプレゼンス**</span><span class="sxs-lookup"><span data-stu-id="c4ab4-123">**Instant Messaging and Presence**</span></span>

  - <span data-ttu-id="c4ab4-124">[ユーザー数] で、同時にサインインされるユーザーの数を入力します。</span><span class="sxs-lookup"><span data-stu-id="c4ab4-124">Under Number of Users, type the number of users who will be concurrently signed in.</span></span> <span data-ttu-id="c4ab4-125">この数は通常はプロビジョニングされたユーザーの総数の 80% です。</span><span class="sxs-lookup"><span data-stu-id="c4ab4-125">This number is typically 80% of the total number of provisioned users.</span></span> <span data-ttu-id="c4ab4-126">ほとんどの場合、同時ユーザーの 100% で IM とプレゼンスが有効です。</span><span class="sxs-lookup"><span data-stu-id="c4ab4-126">In most situations, 100% of your concurrent users will be enabled for IM and Presence.</span></span> <span data-ttu-id="c4ab4-127">既定値は 80,000 です。</span><span class="sxs-lookup"><span data-stu-id="c4ab4-127">The default is 80,000.</span></span>

  - <span data-ttu-id="c4ab4-128">[連絡先リストの平均連絡先数] は、システム要件の検証に使用している連絡先の数を示します。</span><span class="sxs-lookup"><span data-stu-id="c4ab4-128">Average number of contacts in Contact list indicates the number of contacts that we are using to validate your system requirements.</span></span> <span data-ttu-id="c4ab4-129">この番号は変更できません。</span><span class="sxs-lookup"><span data-stu-id="c4ab4-129">This number is not changeable.</span></span>

<span data-ttu-id="c4ab4-130">**エンタープライズ VoIP**</span><span class="sxs-lookup"><span data-stu-id="c4ab4-130">**Enterprise Voice**</span></span>

  - <span data-ttu-id="c4ab4-131">[エンタープライズ Voip を有効にする] に、エンタープライズ Voip を有効にしているユーザーのパーセンテージを入力します。</span><span class="sxs-lookup"><span data-stu-id="c4ab4-131">In Users enabled for Enterprise Voice, type the percentage of your users who are enabled for Enterprise Voice.</span></span> <span data-ttu-id="c4ab4-132">既定値は 60% です。</span><span class="sxs-lookup"><span data-stu-id="c4ab4-132">The default is 60%.</span></span>

  - <span data-ttu-id="c4ab4-133">1ユーザーあたりの平均通話回数 (ピーク時) には、負荷がピーク時に平均的なユーザーが参加すると予想される通話の回数を入力します。</span><span class="sxs-lookup"><span data-stu-id="c4ab4-133">In Average number of calls per user per hour (peak), type the number of calls per hour that you expect the average user to participate in during times of peak load.</span></span> <span data-ttu-id="c4ab4-134">既定値は 4 です。</span><span class="sxs-lookup"><span data-stu-id="c4ab4-134">The default is 4.</span></span>

  - <span data-ttu-id="c4ab4-135">[Percentage of calls that use media bypass (メディア バイパスを使用する通話の割合)] に、仲介サーバーをバイパスするユーザーによる発信の割合を入力します。</span><span class="sxs-lookup"><span data-stu-id="c4ab4-135">In Percentage of calls that use media bypass, type the percentage of calls placed by your users that will bypass the Mediation Server.</span></span> <span data-ttu-id="c4ab4-136">既定値は65% です。</span><span class="sxs-lookup"><span data-stu-id="c4ab4-136">The default is 65%.</span></span>

  - <span data-ttu-id="c4ab4-137">[Percentage of voice users involved in UC-PSTN calls (UC-PSTN 通話に含まれる音声ユーザーの割合)] に、UC-PSTN 電話による組織の通話の割合を入力します。</span><span class="sxs-lookup"><span data-stu-id="c4ab4-137">In Percentage of voice users involved in UC-PSTN calls, type the percentage of your organization’s calls which are UC-PSTN phone calls.</span></span> <span data-ttu-id="c4ab4-138">既定値は60%</span><span class="sxs-lookup"><span data-stu-id="c4ab4-138">The default is 60%</span></span>

  - <span data-ttu-id="c4ab4-139">[UC-UC 通話に参加している音声ユーザーの割合 (%): エンタープライズ Voip を有効にしているユーザーのうち、UC 限定の通話のみを有効にする割合を示します。</span><span class="sxs-lookup"><span data-stu-id="c4ab4-139">In Percentage of voice users involved in UC-UC calls shows the percentage of users who are enabled for Enterprise Voice who will be enabled only for UC-UC calls.</span></span> <span data-ttu-id="c4ab4-140">この数値は、[Percentage of voice users enabled for UC-PSTN calls (UC-PSTN 通話が有効な音声ユーザーの割合)] の入力値に基づいて計算されます。</span><span class="sxs-lookup"><span data-stu-id="c4ab4-140">This number is calculated based on what you input for Percentage of voice users enabled for UC-PSTN calls.</span></span>

<span data-ttu-id="c4ab4-141">**会議**</span><span class="sxs-lookup"><span data-stu-id="c4ab4-141">**Conferencing**</span></span>

  - <span data-ttu-id="c4ab4-142">同時会議のユーザーの割合で、会議に同時に参加するユーザーのパーセンテージを入力します。</span><span class="sxs-lookup"><span data-stu-id="c4ab4-142">In Percentage of users in concurrent conferences, type the percentage of users who will be concurrently participating in conferences.</span></span> <span data-ttu-id="c4ab4-143">既定値は 5% です。</span><span class="sxs-lookup"><span data-stu-id="c4ab4-143">The default is 5%.</span></span>

  - <span data-ttu-id="c4ab4-144">[グループ IM のみを使用した会議の割合] (音声なし) の会議の割合を入力します。会議には、インスタントメッセージのみが含まれます。つまり、オーディオコンポーネントは含まれません。</span><span class="sxs-lookup"><span data-stu-id="c4ab4-144">In Percentage of conferences with group IM only (no voice), type the percentage of conferences whose conferences will involve instant messaging only; that is, that do not include an audio component.</span></span> <span data-ttu-id="c4ab4-145">既定値は 10% です。</span><span class="sxs-lookup"><span data-stu-id="c4ab4-145">The default is 10%</span></span>

  - <span data-ttu-id="c4ab4-146">[ダイヤルイン会議を使っているユーザーの割合] で、ダイヤルイン会議を使用する会議の同時参加者の割合を入力します。</span><span class="sxs-lookup"><span data-stu-id="c4ab4-146">In Percentage of users using dial-in conferencing, type the percentage of concurrent participants in conferences who will be using dial-in conferencing.</span></span> <span data-ttu-id="c4ab4-147">既定値は 15% です。</span><span class="sxs-lookup"><span data-stu-id="c4ab4-147">The default is 15%.</span></span>

  - <span data-ttu-id="c4ab4-148">[音声を使用した会議の割合] に、オーディオコンポーネントを追加する会議の割合を入力します。</span><span class="sxs-lookup"><span data-stu-id="c4ab4-148">In Percentage of conferences using voice, type the percentage of conferences that will include an audio component.</span></span>
    
      - <span data-ttu-id="c4ab4-149">20% の音声会議に通常のビデオも含まれる場合は、[Including video (no Multi View) (ビデオを含む (マルチビューなし))] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="c4ab4-149">If 20% of your voice conferences will also include regular video, select the Including video (no Multi View) check box.</span></span>
    
      - <span data-ttu-id="c4ab4-150">20% の会議にマルチビュー ビデオも含まれる場合は、[Including Multi View (マルチビューを含む)] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="c4ab4-150">If 20% of your conferences will also include Multi-View video, select the Including Multi View check box.</span></span>
    
      - <span data-ttu-id="c4ab4-151">50% の音声会議にアプリケーション共有も含まれる場合は、[Including application sharing (アプリケーション共有を含む)] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="c4ab4-151">If 50% of your voice conferences will also include application sharing, select the Including application sharing check box.</span></span>
    
      - <span data-ttu-id="c4ab4-152">音声会議の20% には、Microsoft PowerPoint®プレゼンテーションなどのデータのアップロードが含まれている場合、[web 会議を含める] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="c4ab4-152">If 20% of your voice conferences include data uploads, such as Microsoft PowerPoint® presentations, select the Including web conferencing check box.</span></span>

<span data-ttu-id="c4ab4-153">**モビリティ**</span><span class="sxs-lookup"><span data-stu-id="c4ab4-153">**Mobility**</span></span>

  - <span data-ttu-id="c4ab4-154">[モビリティに対応しているユーザーの割合] に、モバイルデバイスを使用して Lync Server に接続できるユーザーのパーセンテージを入力します。</span><span class="sxs-lookup"><span data-stu-id="c4ab4-154">In Percentage of users enabled for Mobility, type the percentage of your users who will be enabled to connect to Lync Server using mobile devices.</span></span> <span data-ttu-id="c4ab4-155">既定値は 40% です。</span><span class="sxs-lookup"><span data-stu-id="c4ab4-155">The default is 40%.</span></span>

<span data-ttu-id="c4ab4-156">必要な情報をすべて入力すると、容量計算機によって要件が見積られます。</span><span class="sxs-lookup"><span data-stu-id="c4ab4-156">When you have entered all the necessary information, the capacity calculator estimates your requirements.</span></span> <span data-ttu-id="c4ab4-157">黄色のセルには、Lync Server 2013 パフォーマンスラボで実行されたテストに基づいた CPU、メモリ、帯域幅の要件の計算値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c4ab4-157">The yellow cells show calculated values for CPU, memory, and bandwidth requirements based on tests performed in Lync Server 2013 performance labs.</span></span> <span data-ttu-id="c4ab4-158">この数値はガイドラインとして提供されるもので、すべてのバリエーションを逐一テスト、検証したわけではありません。</span><span class="sxs-lookup"><span data-stu-id="c4ab4-158">The numbers are provided as a guideline, not every single variation is tested and validated.</span></span> <span data-ttu-id="c4ab4-159">次の値が計算されます。</span><span class="sxs-lookup"><span data-stu-id="c4ab4-159">The following values are calculated:</span></span>

  - <span data-ttu-id="c4ab4-160">[フロントエンド CPU]: 負荷全体が、Microsoft テストで使用されたサーバーと同じ仕様の1台のフロントエンドサーバーによって処理された場合の CPU 使用率。</span><span class="sxs-lookup"><span data-stu-id="c4ab4-160">Front End CPU: Percentage of CPU usage if the entire load were being handled by one Front End Server of the same specifications as the server that was used in Microsoft testing.</span></span>

  - <span data-ttu-id="c4ab4-161">[ネットワーク (Mbps)]: 対応するワークロードの帯域幅要件 (メガビット/秒 (Mbps) 単位) です。</span><span class="sxs-lookup"><span data-stu-id="c4ab4-161">Network in Mbps: Bandwidth requirements in megabits per second (Mbps) for the corresponding workload.</span></span>

  - <span data-ttu-id="c4ab4-162">[メモリ (GB)]: 対応するワークロードで必要なメモリ (ギガバイト (GB) 単位) です。</span><span class="sxs-lookup"><span data-stu-id="c4ab4-162">Memory in GB: Memory required in gigabytes (GB) for the corresponding workload.</span></span>

<span data-ttu-id="c4ab4-163">緑色のセルには、入力した使用モデルの推奨事項が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c4ab4-163">The green cells show recommendations for the usage model that you entered.</span></span>

  - <span data-ttu-id="c4ab4-164">フロントエンドサーバーの合計: 必要な物理サーバーの数は、デュアルプロセッサと2260メガビットコアを搭載した、Lync Server 2013 を実行している専用サーバーに基づいています。</span><span class="sxs-lookup"><span data-stu-id="c4ab4-164">Total Front End Servers: The number of physical servers required are based on dedicated servers running Lync Server 2013 with dual processor, hex-core, with 2,260 megacycles.</span></span>

  - <span data-ttu-id="c4ab4-165">ハイパースレッドを有効にすると、音声/ビデオをサポートするサーバーのパフォーマンスが上がることがわかっているのでお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c4ab4-165">Note that enabling hyperthreading is recommended and has been proven to improve performance for servers that support audio/video.</span></span>

  - <span data-ttu-id="c4ab4-166">[エッジ サーバー]: すべての同時ユーザーの 30% がエッジ サーバー経由で通信するという前提に基づいた、必要なエッジ サーバー数です。</span><span class="sxs-lookup"><span data-stu-id="c4ab4-166">Edge Servers: The number of Edge Servers required, based on 30% of all concurrent users communicating through the Edge Servers.</span></span> <span data-ttu-id="c4ab4-167">この割合を計算機で変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="c4ab4-167">This percentage cannot be changed in the calculator.</span></span>

  - <span data-ttu-id="c4ab4-168">[アーカイブ/通話詳細記録/ Quality of Experience (QoE) のサービス ストア]: アーカイブ機能や監視機能に必要なストア数です (組織で有効な場合)。</span><span class="sxs-lookup"><span data-stu-id="c4ab4-168">Archiving/Call Detail Recording/Quality of Experience services Store: The number of stores required for Archiving or Monitoring features, if they are enabled in your organization.</span></span>

  - <span data-ttu-id="c4ab4-169">[必要なバックエンド データベース サーバー (必要なプール)]: 選択したワークロードのサポートに必要なバックエンド データベース サーバーの数です。</span><span class="sxs-lookup"><span data-stu-id="c4ab4-169">Back End Database Server Required (Pools Required): The number of back-end database servers required to support the selected workload.</span></span>

<span data-ttu-id="c4ab4-170">また、フロントエンド サーバーの合計の次の行には、計画したすべてのワークロードを組み合わせた場合の、サーバーとネットワークへの負荷に関する詳細情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c4ab4-170">Additionally, in the row next to Total Front End Servers, more information is provided about the load on your servers and network for all the planned workloads combined.</span></span>

  - <span data-ttu-id="c4ab4-171">[CPU の平均負荷]: フロントエンド サーバーあたりの平均 CPU 使用率です。</span><span class="sxs-lookup"><span data-stu-id="c4ab4-171">Average CPU Load: The average CPU usage per Front End server.</span></span>

  - <span data-ttu-id="c4ab4-172">[ネットワーク (Mbps)]: 入力した使用モデルのサポートに必要な帯域幅割り当てです。</span><span class="sxs-lookup"><span data-stu-id="c4ab4-172">Network in Mbps: The required bandwidth allocation to support the usage model that you entered.</span></span>

  - <span data-ttu-id="c4ab4-173">[メモリ (GB)]: 各フロントエンド サーバーで必要なメモリ (ギガバイト単位) です。</span><span class="sxs-lookup"><span data-stu-id="c4ab4-173">Memory in GB: Memory, in gigabytes, required for each Front End server.</span></span>

</div>

<div>

## <a name="adjusting-for-your-processors"></a><span data-ttu-id="c4ab4-174">プロセッサに応じた調整</span><span class="sxs-lookup"><span data-stu-id="c4ab4-174">Adjusting For Your Processors</span></span>

<span data-ttu-id="c4ab4-175">スプレッドシートの CPU 使用率の数値はすべて、各サーバーにデュアル プロセッサ、2.26 GHz の 6 コア、32 GB 以上のメモリ、8 台以上の 10,000-RPM ハード ディスク ドライブ (72 GB 以上の空きディスク容量あり) が搭載されていることを前提とします。</span><span class="sxs-lookup"><span data-stu-id="c4ab4-175">All the CPU usage figures in the spreadsheet assume that each server has a dual processor, hex-core with 2.26 GHz, at least 32 GB of memory, and 8 or more 10,000-RPM hard disk drives with at least 72 GB free disk space.</span></span>

<span data-ttu-id="c4ab4-176">サーバーにこの仕様とは異なるプロセッサが搭載されている場合は、数値を調整してご使用のハードウェアに合わせることができます。</span><span class="sxs-lookup"><span data-stu-id="c4ab4-176">If your servers have different processors, you can adjust the figures to match your hardware.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

