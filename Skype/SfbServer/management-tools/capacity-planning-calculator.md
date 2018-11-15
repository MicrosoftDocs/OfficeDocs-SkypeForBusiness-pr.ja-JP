---
title: Skype ビジネス サーバーの容量計画の計算について
ms.author: heidip
author: microsoftheidi
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: bc4d93b1-0c38-4bf8-8b65-692ff3e2446d
description: '概要: 容量計算機の使用方法'
ms.openlocfilehash: c55c42942ef14d7ec1904fb8b43340d6a2babb50
ms.sourcegitcommit: 30620021ceba916a505437ab641a23393f55827a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/15/2018
ms.locfileid: "26533414"
---
# <a name="skype-for-business-server-capacity-planning-calculator"></a><span data-ttu-id="a6773-103">Skype ビジネス サーバーの容量計画の計算について</span><span class="sxs-lookup"><span data-stu-id="a6773-103">Skype for Business Server Capacity Planning Calculator</span></span>
 
<span data-ttu-id="a6773-104">**概要:** 容量計算機の使用方法</span><span class="sxs-lookup"><span data-stu-id="a6773-104">**Summary:** How to use the Capacity Calculator Tool.</span></span>

> [!NOTE]
> <span data-ttu-id="a6773-105">この資料は、ビジネス サーバー 2015 のダウンロード、Skype を参照しますに適用されます。</span><span class="sxs-lookup"><span data-stu-id="a6773-105">This article references Skype for Business Server 2015 downloads, but it applies to:</span></span>
> - <span data-ttu-id="a6773-106">ビジネス サーバー 2019 の Skype です。</span><span class="sxs-lookup"><span data-stu-id="a6773-106">Skype for Business Server 2019.</span></span>
> - <span data-ttu-id="a6773-107">ビジネス サーバー 2015 の Skype です。</span><span class="sxs-lookup"><span data-stu-id="a6773-107">Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="a6773-108">[ビジネス サーバー 2015 の容量の計算の Skype](https://www.microsoft.com/en-us/download/details.aspx?id=51196)と[Skype](https://www.microsoft.com/en-in/download/details.aspx?id=57510)ビジネス サーバー 2019 の容量の計算には、 [Skype](https://www.microsoft.com/en-us/download/details.aspx?id=50357)と展開に関するドキュメント ([、Skype をビジネスのための計画を強化します。サーバー 2015年配置](../plan-your-deployment/plan-your-deployment.md) [、Skype をビジネス サーバー 2019 の展開の計画](../../SfBServer2019/plan/plan-your-deployment-2019.md)とそれぞれ)。</span><span class="sxs-lookup"><span data-stu-id="a6773-108">The [Skype for Business Server 2015 Capacity Calculator](https://www.microsoft.com/en-us/download/details.aspx?id=51196) and [Skype for Business Server 2019 Capacity Calculator](https://www.microsoft.com/en-in/download/details.aspx?id=57510) augment the [Skype for Business Planning Tool](https://www.microsoft.com/en-us/download/details.aspx?id=50357) and your deployment documentation ([Plan for your Skype for Business Server 2015 deployment](../plan-your-deployment/plan-your-deployment.md) and [Plan for your Skype for Business Server 2019 deployment](../../SfBServer2019/plan/plan-your-deployment-2019.md) respectively).</span></span> <span data-ttu-id="a6773-109">この計算機は、ガイドをよくお読みになり、計画ツールを使って推奨のトポロジを作成後に使用してください。</span><span class="sxs-lookup"><span data-stu-id="a6773-109">Use the calculator after you have reviewed the guide and created a recommended topology by using the Planning Tool.</span></span>
  
<span data-ttu-id="a6773-110">ビジネス サーバーの容量の計算に役立ちますの Skype ユーザーと組織を使用してコミュニケーション ツールの数に基づいて、サーバーの要件を決定します。</span><span class="sxs-lookup"><span data-stu-id="a6773-110">The Skype for Business Server Capacity Calculator helps you determine server requirements based on the number of users and the communication tools your organization uses.</span></span> <span data-ttu-id="a6773-111">ユーザー プロファイルとユーザーに対して有効にしたい機能が決定したら、この計算機を使って必要とするサーバー、メモリ、帯域幅数を決定します。</span><span class="sxs-lookup"><span data-stu-id="a6773-111">After you have determined your user profile and the functions you want to enable for your users, use the calculator to determine the number of servers, memory, and bandwidth you will need.</span></span> <span data-ttu-id="a6773-112">計算機のこのバージョンでは、ディスク I/O 要件に対するガイダンスは提供しません。</span><span class="sxs-lookup"><span data-stu-id="a6773-112">This version of the calculator does not provide guidance for disk I/O requirements.</span></span>
  
<span data-ttu-id="a6773-p103">特定のユーザー プロファイルに関する正確な詳細情報があれば、計算機を最大限に活用できます。たとえば、音声対応ユーザーの割合、1 時間あたりの各ユーザーの平均通話数、通話時間、会議での同時ユーザーの割合によって、サーバー要件が大幅に変わる可能性があります。計算機によって作成される推奨事項の精度は、提供する情報の精度によって変わります。</span><span class="sxs-lookup"><span data-stu-id="a6773-p103">You can benefit most from the calculator if you have accurate, detailed information about your specific user profile. For example, the percentage of voice-enabled users, average calls per user per hour, call duration, and the percentage of concurrent users in conferences can make a huge difference in server requirements. The accuracy of the recommendations created by the calculator depends on the accuracy of the information that you provide.</span></span>
  
<span data-ttu-id="a6773-116">計画ツールおよび容量計画の電卓を使用した後は、Skype ビジネス サーバーが適切に準備することを確認するのには、提案や計画的な負荷をシミュレートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a6773-116">Once you have used the Planning Tool and the Capacity Planning Calculator, you should simulate your proposed and planned load to ensure that Skype for Business Server will be adequately provisioned.</span></span> <span data-ttu-id="a6773-117">負荷のシミュレートされた負荷の下でテストを実行するには、 [Skype](https://technet.microsoft.com/en-us/library/mt631400.aspx)に記載されている[Skype](https://www.microsoft.com/en-us/download/details.aspx?id=50367)を使用します。</span><span class="sxs-lookup"><span data-stu-id="a6773-117">To perform stress testing under a simulated load, use the [Skype for Business Server Stress and Performance Tool](https://www.microsoft.com/en-us/download/details.aspx?id=50367) documented at [Skype for Business Server Stress and Performance Tool](https://technet.microsoft.com/en-us/library/mt631400.aspx).</span></span>
  
## <a name="using-the-capacity-calculator"></a><span data-ttu-id="a6773-118">容量計算機の使用</span><span class="sxs-lookup"><span data-stu-id="a6773-118">Using the Capacity Calculator</span></span>

<span data-ttu-id="a6773-119">計算機は Microsoft Excel のスプレッドシートです。</span><span class="sxs-lookup"><span data-stu-id="a6773-119">The calculator is a Microsoft Excel spreadsheet.</span></span> <span data-ttu-id="a6773-120">オレンジ色のセルが入力用です。</span><span class="sxs-lookup"><span data-stu-id="a6773-120">Your input cells are colored orange.</span></span> <span data-ttu-id="a6773-121">(の Skype ビジネス サーバー 2015、Skype のビジネス サーバー 2019、16 個のフロント エンド サーバーと 1 つのプール内の 106,000 のユーザーの中に、12 個のフロント エンド サーバーと 1 つのプール内に 80,000 ユーザー用)、セルの既定値が入力されますが、これらの値を変更する必要があります。組織のニーズに一致します。</span><span class="sxs-lookup"><span data-stu-id="a6773-121">Default values are entered in the cells (For Skype for Business Server 2015, 80,000 users in one pool with twelve Front End Servers, while for Skype for Business Server 2019, 106,000 users in one pool with sixteen Front End Servers), but you should change these values to match your organization's needs.</span></span>
  
<span data-ttu-id="a6773-p106">使用モデルには次のセクションが含まれます。容量要件を計算するには、次のように、シートの上から下に行ごとに順番にデータを入力していきます。</span><span class="sxs-lookup"><span data-stu-id="a6773-p106">The usage model contains the following sections. To calculate your capacity requirements, enter data as described starting at the top of the sheet and working down row by row:</span></span> 
  
 <span data-ttu-id="a6773-124">**インスタント メッセージングとプレゼンス**</span><span class="sxs-lookup"><span data-stu-id="a6773-124">**Instant Messaging and Presence**</span></span>
  
- <span data-ttu-id="a6773-125">[**ユーザー数**] に、同時にサインインできるユーザー数を入力します。</span><span class="sxs-lookup"><span data-stu-id="a6773-125">Under **Number of Users**, type the number of users who will be signed in at once.</span></span> <span data-ttu-id="a6773-126">この数は通常はプロビジョニングされたユーザーの総数の 80% です。</span><span class="sxs-lookup"><span data-stu-id="a6773-126">This number is typically 80% of the total number of provisioned users.</span></span> <span data-ttu-id="a6773-127">ほとんどの場合、同時ユーザーの 100% で IM とプレゼンスが有効です。</span><span class="sxs-lookup"><span data-stu-id="a6773-127">In most situations, 100% of your concurrent users will be enabled for IM and Presence.</span></span> <span data-ttu-id="a6773-128">80,000 ビジネス サーバー 2015 年の Skype と Skype のビジネス サーバー 2019 の 106,000 のユーザーは、既定では。</span><span class="sxs-lookup"><span data-stu-id="a6773-128">The default is 80,000 for Skype for Business Server 2015, and 106,000 users for Skype for Business Server 2019.</span></span>
    
- <span data-ttu-id="a6773-p108">[**連絡先リストの平均連絡先数**] は、システム要件の検証に使用している連絡先の数を示します。この数は固定で、変更できません。</span><span class="sxs-lookup"><span data-stu-id="a6773-p108">**Average number of contacts in Contact list** indicates the number of contacts that we are using to validate your system requirements. This number is fixed and not something you should change.</span></span>
    
  <span data-ttu-id="a6773-131">**エンタープライズ VoIP**</span><span class="sxs-lookup"><span data-stu-id="a6773-131">**Enterprise Voice**</span></span>
  
- <span data-ttu-id="a6773-p109">[**Users enabled for Enterprise Voice (エンタープライズ VoIP が有効なユーザー)**] に、エンタープライズ VoIP が有効なユーザーの割合を入力します。既定値は 60% です。</span><span class="sxs-lookup"><span data-stu-id="a6773-p109">In **Users enabled for Enterprise Voice**, type the percentage of your users enabled for Enterprise Voice. The default is 60%.</span></span> 
    
- <span data-ttu-id="a6773-p110">[**Average number of calls per user per hour (peak) (1 時間あたりのユーザーごとの平均通話数 (ピーク時))**] に、負荷のピーク時に平均的なユーザーが参加すると思われる 1 時間あたりの通話数を入力します。既定値は 4 です。</span><span class="sxs-lookup"><span data-stu-id="a6773-p110">In **Average number of calls per user per hour (peak)**, type the number of calls per hour you expect the average user to participate in during times of peak load. The default is 4.</span></span> 
    
- <span data-ttu-id="a6773-p111">[**Percentage of calls that use media bypass (メディア バイパスを使用する通話の割合)**] に、仲介サーバーをバイパスするユーザーによる発信の割合を入力します。既定値は 65% ですが、地理的に拡大するあるいは家から作業するユーザーのパーセンテージが大きい場合は、値を下げてもかまいません。</span><span class="sxs-lookup"><span data-stu-id="a6773-p111">In **Percentage of calls that use media bypass**, type the percentage of calls placed by your users that will bypass the Mediation Server. The default is 65%, but could be lower if you are spread out geographically or have a large percentage of users who work from home.</span></span>
    
- <span data-ttu-id="a6773-138">**UC PSTN の呼び出しに関連する音声のユーザーの割合**、UC PSTN 電話をかけるには、組織の呼び出しの割合を入力します。</span><span class="sxs-lookup"><span data-stu-id="a6773-138">In **Percentage of voice users involved in UC-PSTN calls**, type the percentage of your organization's calls which are UC-PSTN phone calls.</span></span> <span data-ttu-id="a6773-139">既定値は 60% です。</span><span class="sxs-lookup"><span data-stu-id="a6773-139">The default is 60%.</span></span>
    
- <span data-ttu-id="a6773-p113">[**Percentage of voice users involved in UC-UC calls (UC-PSTN 通話に含まれる音声ユーザーの割合)**] は、UC-UC 通話のみが有効な、エンタープライズ VoIP 対応ユーザーの割合を示しています。この数値は、[**Percentage of voice users enabled for UC-PSTN calls (UC-PSTN 通話が有効な音声ユーザーの割合)**] の入力値に基づいて計算されます。</span><span class="sxs-lookup"><span data-stu-id="a6773-p113">**Percentage of voice users involved in UC-UC calls** shows the percentage of users who are enabled for Enterprise Voice who will be enabled only for UC-UC calls. This number is calculated based on what you input for **Percentage of voice users enabled for UC-PSTN calls**.</span></span> 
    
  <span data-ttu-id="a6773-142">**会議**</span><span class="sxs-lookup"><span data-stu-id="a6773-142">**Conferencing**</span></span>
  
- <span data-ttu-id="a6773-p114">[**Percentage of users in concurrent conferences (同時会議のユーザーの割合)**] に、会議に同時参加するユーザーの割合を入力します。既定値は 5% です。</span><span class="sxs-lookup"><span data-stu-id="a6773-p114">In **Percentage of users in concurrent conferences**, type the percentage of users who will be participating in conferences at the same time. The default is 5%.</span></span> 
    
- <span data-ttu-id="a6773-p115">[**Percentage of conferences with group IM only (no voice) (グループ IM のみ (音声なし) の会議の割合)**] に、インスタント メッセージングのみを必要とし、音声を使用しない会議の割合を入力します。既定値は 10% です。</span><span class="sxs-lookup"><span data-stu-id="a6773-p115">In **Percentage of conferences with group IM only (no voice)**, type the percentage of conferences that will involve instant messaging only and do not include audio. The default is 10%</span></span>
    
- <span data-ttu-id="a6773-p116">[**Percentage of users using dial-in conferencing (ダイヤルイン会議を使用するユーザーの割合)**] に、ダイヤルイン会議を使用する会議への同時参加者の割合を入力します。既定値は 15% です。</span><span class="sxs-lookup"><span data-stu-id="a6773-p116">In **Percentage of users using dial-in conferencing**, type the percentage of participants in conferences who will be using dial-in conferencing at one time. The default is 15%.</span></span>
    
- <span data-ttu-id="a6773-149">[**Percentage of conferences using voice (音声を使用する会議の割合)**] に、音声を使用しない会議の割合を入力します。</span><span class="sxs-lookup"><span data-stu-id="a6773-149">In **Percentage of conferences using voice**, type the percentage of conferences that will include audio.</span></span> 
    
  - <span data-ttu-id="a6773-150">20% の音声会議に通常のビデオも含まれる場合は、[**Including video (no Multi View) (ビデオを含む (マルチビューなし))**] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="a6773-150">If 20% of your voice conferences will also include regular video, select the **Including video (no Multi View)** check box.</span></span>
    
  - <span data-ttu-id="a6773-151">20% の会議にマルチビュー ビデオも含まれる場合は、[**Including Multi View (マルチビューを含む)**] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="a6773-151">If 20% of your conferences will also include Multi-View video, select the **Including Multi View** check box.</span></span>
    
  - <span data-ttu-id="a6773-152">音声会議の 50% には、アプリケーションの共有も含まれている場合は、**アプリケーションの共有を含む**] チェック ボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="a6773-152">If 50% of your voice conferences will also include application sharing, select the **Including application sharing** check box.</span></span>
    
  - <span data-ttu-id="a6773-153">20% の音声会議にデータのアップロード (PowerPoint のプレゼンテーションなど) が含まれる場合は、[**Including web conferencing (Web 会議を含む)**] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="a6773-153">If 20% of your voice conferences include data uploads, such as PowerPoint presentations, select the **Including web conferencing** check box.</span></span>
    
  <span data-ttu-id="a6773-154">**モビリティ**</span><span class="sxs-lookup"><span data-stu-id="a6773-154">**Mobility**</span></span>
  
- <span data-ttu-id="a6773-155">**移動が有効なユーザーの割合**Skype のモバイル デバイスを使用してビジネスのサーバーに接続するときに使用するユーザーの割合を入力します。</span><span class="sxs-lookup"><span data-stu-id="a6773-155">In **Percentage of users enabled for Mobility**, type the percentage of your users who will be enabled to connect to Skype for Business Server using mobile devices.</span></span> <span data-ttu-id="a6773-156">既定値は 40% です。</span><span class="sxs-lookup"><span data-stu-id="a6773-156">The default is 40%.</span></span> 
    
<span data-ttu-id="a6773-157">必要な情報をすべて入力すると、容量計算機によって要件が見積られます。</span><span class="sxs-lookup"><span data-stu-id="a6773-157">When you have entered all the necessary information, the capacity calculator estimates your requirements.</span></span> <span data-ttu-id="a6773-158">黄色のセルでは、CPU、メモリ、およびビジネスのサーバー パフォーマンス ラボの Skype で実行されるテストに基づく必要な帯域幅の計算値を表示します。</span><span class="sxs-lookup"><span data-stu-id="a6773-158">The yellow cells show calculated values for CPU, memory, and bandwidth requirements based on tests performed in Skype for Business Server performance labs.</span></span> <span data-ttu-id="a6773-159">この数値はガイドラインとして提供されるもので、すべてのバリエーションを逐一テスト、検証したわけではありません。</span><span class="sxs-lookup"><span data-stu-id="a6773-159">The numbers are provided as a guideline, not every single variation is tested and validated.</span></span> <span data-ttu-id="a6773-160">次の値が計算されます。</span><span class="sxs-lookup"><span data-stu-id="a6773-160">The following values are calculated:</span></span> 
  
- <span data-ttu-id="a6773-161">[**フロントエンド CPU**]: 全体の負荷が、テストで使用されたサーバーと同じ仕様のフロントエンド サーバーによって処理された場合の CPU 使用率の割合です (詳細は、本記事の最後を参照)。</span><span class="sxs-lookup"><span data-stu-id="a6773-161">**Front End CPU**: Percentage of CPU usage if the entire load were being handled by one Front End Server of the same specifications as the server that was used in testing (see the description at the end of this article).</span></span>
    
- <span data-ttu-id="a6773-162">[**ネットワーク (Mbps)**]: 対応するワークロードの帯域幅要件 (メガビット/秒 (Mbps) 単位) です。</span><span class="sxs-lookup"><span data-stu-id="a6773-162">**Network in Mbps**: Bandwidth requirements in megabits per second (Mbps) for the corresponding workload.</span></span>
    
- <span data-ttu-id="a6773-163">[**メモリ (GB)**]: 対応するワークロードで必要なメモリ (ギガバイト (GB) 単位) です。</span><span class="sxs-lookup"><span data-stu-id="a6773-163">**Memory in GB**: Memory required in gigabytes (GB) for the corresponding workload.</span></span>
    
<span data-ttu-id="a6773-164">緑色のセルには、入力した使用モデルの推奨事項が表示されます。</span><span class="sxs-lookup"><span data-stu-id="a6773-164">The green cells show recommendations for the usage model that you entered.</span></span> 
  
- <span data-ttu-id="a6773-165">**合計のフロント エンド サーバー**: デュアル ・ プロセッサを搭載、ビジネス サーバー 2015 の Skype を実行している専用のサーバーに基づく必要な物理サーバーの数 16 進数のコア、2,260 メガサイクル、またはビジネス サーバー 2019 の Skype でインテル Xeon E5-2673 v3、デュアルでプロセッサ、16 進数の中核となります。</span><span class="sxs-lookup"><span data-stu-id="a6773-165">**Total Front End Servers**: The number of physical servers required are based on dedicated servers running Skype for Business Server 2015 with dual processor, hex-core, with 2,260 megacycles, or Skype for Business Server 2019 with Intel Xeon E5-2673 v3, dual processor, hex-core.</span></span>
    
    <span data-ttu-id="a6773-166">ハイパースレッドを有効にすると、音声/ビデオをサポートするサーバーのパフォーマンスが上がることがわかっているのでお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a6773-166">Note that enabling hyperthreading is recommended and has been proven to improve performance for servers that support audio/video.</span></span>
    
- <span data-ttu-id="a6773-p119">[**エッジ サーバー**]: すべての同時ユーザーの 30% がエッジ サーバー経由で通信するという前提に基づいた、必要なエッジ サーバー数です。この割合を計算機で変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="a6773-p119">**Edge Servers**: The number of Edge Servers required, based on 30% of all concurrent users communicating through the Edge Servers. This percentage cannot be changed in the calculator.</span></span> 
    
- <span data-ttu-id="a6773-169">[**アーカイブ/通話詳細記録/ Quality of Experience (QoE) のサービス ストア**]: アーカイブ機能や監視機能に必要なストア数です (組織で有効な場合)。</span><span class="sxs-lookup"><span data-stu-id="a6773-169">**Archiving/Call Detail Recording/Quality of Experience services Store**: The number of stores required for Archiving or Monitoring features, if they are enabled in your organization.</span></span>
    
- <span data-ttu-id="a6773-170">[**必要なバックエンド データベース サーバー (必要なプール)**]: 選択したワークロードのサポートに必要なバックエンド データベース サーバーの数です。</span><span class="sxs-lookup"><span data-stu-id="a6773-170">**Back End Database Server Required (Pools Required)**: The number of back-end database servers required to support the selected workload.</span></span>
    
<span data-ttu-id="a6773-171">また、フロントエンド サーバーの合計の次の行には、計画したすべてのワークロードを組み合わせた場合の、サーバーとネットワークへの負荷に関する詳細情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="a6773-171">Additionally, in the row next to Total Front End Servers, more information is provided about the load on your servers and network for all the planned workloads combined.</span></span>
  
- <span data-ttu-id="a6773-172">[**CPU の平均負荷**]: フロントエンド サーバーあたりの平均 CPU 使用率です。</span><span class="sxs-lookup"><span data-stu-id="a6773-172">**Average CPU Load**: The average CPU usage per Front End server.</span></span>
    
- <span data-ttu-id="a6773-173">[**ネットワーク (Mbps)**]: 入力した使用モデルのサポートに必要な帯域幅割り当てです。</span><span class="sxs-lookup"><span data-stu-id="a6773-173">**Network in Mbps**: The required bandwidth allocation to support the usage model that you entered.</span></span>
    
- <span data-ttu-id="a6773-174">[**メモリ (GB)**]: 各フロントエンド サーバーで必要なメモリ (ギガバイト単位) です。</span><span class="sxs-lookup"><span data-stu-id="a6773-174">**Memory in GB**: Memory, in gigabytes, required for each Front End server.</span></span>
    
### <a name="adjusting-for-your-processors"></a><span data-ttu-id="a6773-175">プロセッサに応じた調整</span><span class="sxs-lookup"><span data-stu-id="a6773-175">Adjusting For Your Processors</span></span>

<span data-ttu-id="a6773-176">スプレッドシートで CPU 使用率の図を想定しています、ビジネス サーバー 2015 サーバーの各 Skype 2.26 GHz、32 GB 以上のメモリを 16 進数のコア、デュアル プロセッサがあり、8 個または複数の 10,000 RPM のハード ディスク ドライブで 72 GB 以上の空きディスク領域をすべてです。</span><span class="sxs-lookup"><span data-stu-id="a6773-176">All the CPU usage figures in the spreadsheet assume that each Skype for Business Server 2015 server has a dual processor, hex-core with 2.26 GHz, at least 32 GB of memory, and 8 or more 10,000-RPM hard disk drives with at least 72 GB free disk space.</span></span> <span data-ttu-id="a6773-177">各 Skype ビジネス サーバー 2019 サーバー用には、スプレッドシートの CPU 使用率の図は、各サーバーは、デュアル プロセッサ、インテル Xeon E5-2673 v3 では、少なくとも 64 GB のメモリを 16 進数のコアを 8 個または複数の 10,000 RPM のハード ディスク ドライブで 72 GB 以上の空きを想定していますすべてのディスク sペースです。</span><span class="sxs-lookup"><span data-stu-id="a6773-177">For each Skype for Business Server 2019 server, all the CPU usage figures in the spreadsheet assume that each server has a dual processor, hex-core with Intel Xeon E5-2673 v3, at least 64 GB of memory, and 8 or more 10,000-RPM hard disk drives with at least 72 GB free disk space.</span></span>
  
<span data-ttu-id="a6773-178">サーバーにこの仕様とは異なるプロセッサが搭載されている場合は、数値を調整してご使用のハードウェアに合わせることができます。</span><span class="sxs-lookup"><span data-stu-id="a6773-178">If your servers have different processors, you can adjust the figures to match your hardware.</span></span>
  
