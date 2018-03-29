---
title: Skype for Business Server 2015 の容量計画の計算機
ms.author: heidip
author: microsoftheidi
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: bc4d93b1-0c38-4bf8-8b65-692ff3e2446d
description: '容量の電卓ツールを使用する概要: 方法です。'
ms.openlocfilehash: 5d94dab15b104703efc76b227e6e9dd1286f9955
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="skype-for-business-server-2015-capacity-planning-calculator"></a><span data-ttu-id="c6645-103">Skype for Business Server 2015 の容量計画の計算機</span><span class="sxs-lookup"><span data-stu-id="c6645-103">Skype for Business Server 2015 Capacity Planning Calculator</span></span>
 
<span data-ttu-id="c6645-104">**概要:** 容量計算機の使用方法</span><span class="sxs-lookup"><span data-stu-id="c6645-104">**Summary:** How to use the Capacity Calculator Tool.</span></span>
  
<span data-ttu-id="c6645-105">[ビジネス サーバー 2015 の容量の計算の Skype](https://www.microsoft.com/en-us/download/details.aspx?id=51196)は、 [Skype ビジネス 2015年計画ツール](https://www.microsoft.com/en-us/download/details.aspx?id=50357)と[、Skype をビジネス サーバー 2015 の展開計画](https://technet.microsoft.com/en-us/library/dn951427)のドキュメントを補強します。</span><span class="sxs-lookup"><span data-stu-id="c6645-105">[Skype for Business Server 2015 Capacity Calculator](https://www.microsoft.com/en-us/download/details.aspx?id=51196) augments the [Skype for Business 2015 Planning Tool](https://www.microsoft.com/en-us/download/details.aspx?id=50357) and the documentation at [Plan for your Skype for Business Server 2015 deployment](https://technet.microsoft.com/en-us/library/dn951427).</span></span> <span data-ttu-id="c6645-106">この計算機は、ガイドをよくお読みになり、計画ツールを使って推奨のトポロジを作成後に使用してください。</span><span class="sxs-lookup"><span data-stu-id="c6645-106">Use the calculator after you have reviewed the guide and created a recommended topology by using the Planning Tool.</span></span>
  
<span data-ttu-id="c6645-107">ビジネス サーバー 2015 の容量の計算に役立ちますの Skype ユーザーと組織を使用してコミュニケーション ツールの数に基づいて、サーバーの要件を決定します。</span><span class="sxs-lookup"><span data-stu-id="c6645-107">The Skype for Business Server 2015 Capacity Calculator helps you determine server requirements based on the number of users and the communication tools your organization uses.</span></span> <span data-ttu-id="c6645-108">ユーザー プロファイルとユーザーに対して有効にしたい機能が決定したら、この計算機を使って必要とするサーバー、メモリ、帯域幅数を決定します。</span><span class="sxs-lookup"><span data-stu-id="c6645-108">After you have determined your user profile and the functions you want to enable for your users, use the calculator to determine the number of servers, memory, and bandwidth you will need.</span></span> <span data-ttu-id="c6645-109">計算機のこのバージョンでは、ディスク I/O 要件に対するガイダンスは提供しません。</span><span class="sxs-lookup"><span data-stu-id="c6645-109">This version of the calculator does not provide guidance for disk I/O requirements.</span></span>
  
<span data-ttu-id="c6645-p103">特定のユーザー プロファイルに関する正確な詳細情報があれば、計算機を最大限に活用できます。たとえば、音声対応ユーザーの割合、1 時間あたりの各ユーザーの平均通話数、通話時間、会議での同時ユーザーの割合によって、サーバー要件が大幅に変わる可能性があります。計算機によって作成される推奨事項の精度は、提供する情報の精度によって変わります。</span><span class="sxs-lookup"><span data-stu-id="c6645-p103">You can benefit most from the calculator if you have accurate, detailed information about your specific user profile. For example, the percentage of voice-enabled users, average calls per user per hour, call duration, and the percentage of concurrent users in conferences can make a huge difference in server requirements. The accuracy of the recommendations created by the calculator depends on the accuracy of the information that you provide.</span></span>
  
<span data-ttu-id="c6645-113">計画ツールおよび容量計画の電卓を使用したビジネス サーバー 2015 の Skype を十分に備えがあることを確認するのには、提案や計画的な負荷をシミュレートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c6645-113">Once you have used the Planning Tool and the Capacity Planning Calculator, you should simulate your proposed and planned load to ensure that Skype for Business Server 2015 will be adequately provisioned.</span></span> <span data-ttu-id="c6645-114">負荷のシミュレートされた負荷の下でテストを実行するには、[ビジネス サーバー 2015 のストレスおよびパフォーマンス ツールの Skype](https://technet.microsoft.com/en-us/library/mt631400.aspx) [Skype ビジネス サーバー 2015 のストレスおよびパフォーマンス ツール](https://www.microsoft.com/en-us/download/details.aspx?id=50367)を使用します。</span><span class="sxs-lookup"><span data-stu-id="c6645-114">To perform stress testing under a simulated load, use the [Skype for Business Server 2015 Stress and Performance Tool](https://www.microsoft.com/en-us/download/details.aspx?id=50367) documented at [Skype for Business Server 2015 Stress and Performance Tool](https://technet.microsoft.com/en-us/library/mt631400.aspx).</span></span>
  
## <a name="using-the-capacity-calculator"></a><span data-ttu-id="c6645-115">容量計算機の使用</span><span class="sxs-lookup"><span data-stu-id="c6645-115">Using the Capacity Calculator</span></span>

<span data-ttu-id="c6645-116">計算機は Microsoft Excel のスプレッドシートです。</span><span class="sxs-lookup"><span data-stu-id="c6645-116">The calculator is a Microsoft Excel spreadsheet.</span></span> <span data-ttu-id="c6645-117">オレンジ色のセルが入力用です。</span><span class="sxs-lookup"><span data-stu-id="c6645-117">Your input cells are colored orange.</span></span> <span data-ttu-id="c6645-118">(80,000 ユーザーなど 12 個のフロント エンド サーバーと 1 つのプールで) セルに既定値を入力しますが、組織のニーズに合わせてこれらの値を変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c6645-118">Default values are entered in the cells (such as 80,000 users in one pool with twelve Front End Servers), but you should change these values to match your organization's needs.</span></span> 
  
<span data-ttu-id="c6645-p106">使用モデルには次のセクションが含まれます。容量要件を計算するには、次のように、シートの上から下に行ごとに順番にデータを入力していきます。</span><span class="sxs-lookup"><span data-stu-id="c6645-p106">The usage model contains the following sections. To calculate your capacity requirements, enter data as described starting at the top of the sheet and working down row by row:</span></span> 
  
 <span data-ttu-id="c6645-121">**インスタント メッセージングとプレゼンス**</span><span class="sxs-lookup"><span data-stu-id="c6645-121">**Instant Messaging and Presence**</span></span>
  
- <span data-ttu-id="c6645-p107">[**ユーザー数**] に、同時にサインインできるユーザー数を入力します。この数は通常はプロビジョニングされたユーザーの総数の 80% です。ほとんどの場合、同時ユーザーの 100% で IM とプレゼンスが有効です。既定値は 80,000 です。</span><span class="sxs-lookup"><span data-stu-id="c6645-p107">Under **Number of Users**, type the number of users who will be signed in at once. This number is typically 80% of the total number of provisioned users. In most situations, 100% of your concurrent users will be enabled for IM and Presence. The default is 80,000.</span></span>
    
- <span data-ttu-id="c6645-p108">[**連絡先リストの平均連絡先数**] は、システム要件の検証に使用している連絡先の数を示します。この数は固定で、変更できません。</span><span class="sxs-lookup"><span data-stu-id="c6645-p108">**Average number of contacts in Contact list** indicates the number of contacts that we are using to validate your system requirements. This number is fixed and not something you should change.</span></span>
    
 <span data-ttu-id="c6645-128">**エンタープライズ VoIP**</span><span class="sxs-lookup"><span data-stu-id="c6645-128">**Enterprise Voice**</span></span>
  
- <span data-ttu-id="c6645-p109">[**Users enabled for Enterprise Voice (エンタープライズ VoIP が有効なユーザー)**] に、エンタープライズ VoIP が有効なユーザーの割合を入力します。既定値は 60% です。</span><span class="sxs-lookup"><span data-stu-id="c6645-p109">In **Users enabled for Enterprise Voice**, type the percentage of your users enabled for Enterprise Voice. The default is 60%.</span></span> 
    
- <span data-ttu-id="c6645-p110">[**Average number of calls per user per hour (peak) (1 時間あたりのユーザーごとの平均通話数 (ピーク時))**] に、負荷のピーク時に平均的なユーザーが参加すると思われる 1 時間あたりの通話数を入力します。既定値は 4 です。</span><span class="sxs-lookup"><span data-stu-id="c6645-p110">In **Average number of calls per user per hour (peak)**, type the number of calls per hour you expect the average user to participate in during times of peak load. The default is 4.</span></span> 
    
- <span data-ttu-id="c6645-p111">[**Percentage of calls that use media bypass (メディア バイパスを使用する通話の割合)**] に、仲介サーバーをバイパスするユーザーによる発信の割合を入力します。既定値は 65% ですが、地理的に拡大するあるいは家から作業するユーザーのパーセンテージが大きい場合は、値を下げてもかまいません。</span><span class="sxs-lookup"><span data-stu-id="c6645-p111">In **Percentage of calls that use media bypass**, type the percentage of calls placed by your users that will bypass the Mediation Server. The default is 65%, but could be lower if you are spread out geographically or have a large percentage of users who work from home.</span></span>
    
- <span data-ttu-id="c6645-135">**UC PSTN の呼び出しに関連する音声のユーザーの割合**、UC PSTN 電話をかけるには、組織の呼び出しの割合を入力します。</span><span class="sxs-lookup"><span data-stu-id="c6645-135">In **Percentage of voice users involved in UC-PSTN calls**, type the percentage of your organization's calls which are UC-PSTN phone calls.</span></span> <span data-ttu-id="c6645-136">既定値は 60% です。</span><span class="sxs-lookup"><span data-stu-id="c6645-136">The default is 60%.</span></span>
    
- <span data-ttu-id="c6645-p113">[**Percentage of voice users involved in UC-UC calls (UC-PSTN 通話に含まれる音声ユーザーの割合)**] は、UC-UC 通話のみが有効な、エンタープライズ VoIP 対応ユーザーの割合を示しています。この数値は、[**Percentage of voice users enabled for UC-PSTN calls (UC-PSTN 通話が有効な音声ユーザーの割合)**] の入力値に基づいて計算されます。</span><span class="sxs-lookup"><span data-stu-id="c6645-p113">**Percentage of voice users involved in UC-UC calls** shows the percentage of users who are enabled for Enterprise Voice who will be enabled only for UC-UC calls. This number is calculated based on what you input for **Percentage of voice users enabled for UC-PSTN calls**.</span></span> 
    
 <span data-ttu-id="c6645-139">**会議**</span><span class="sxs-lookup"><span data-stu-id="c6645-139">**Conferencing**</span></span>
  
- <span data-ttu-id="c6645-p114">[**Percentage of users in concurrent conferences (同時会議のユーザーの割合)**] に、会議に同時参加するユーザーの割合を入力します。既定値は 5% です。</span><span class="sxs-lookup"><span data-stu-id="c6645-p114">In **Percentage of users in concurrent conferences**, type the percentage of users who will be participating in conferences at the same time. The default is 5%.</span></span> 
    
- <span data-ttu-id="c6645-p115">[**Percentage of conferences with group IM only (no voice) (グループ IM のみ (音声なし) の会議の割合)**] に、インスタント メッセージングのみを必要とし、音声を使用しない会議の割合を入力します。既定値は 10% です。</span><span class="sxs-lookup"><span data-stu-id="c6645-p115">In **Percentage of conferences with group IM only (no voice)**, type the percentage of conferences that will involve instant messaging only and do not include audio. The default is 10%</span></span>
    
- <span data-ttu-id="c6645-p116">[**Percentage of users using dial-in conferencing (ダイヤルイン会議を使用するユーザーの割合)**] に、ダイヤルイン会議を使用する会議への同時参加者の割合を入力します。既定値は 15% です。</span><span class="sxs-lookup"><span data-stu-id="c6645-p116">In **Percentage of users using dial-in conferencing**, type the percentage of participants in conferences who will be using dial-in conferencing at one time. The default is 15%.</span></span>
    
- <span data-ttu-id="c6645-146">[**Percentage of conferences using voice (音声を使用する会議の割合)**] に、音声を使用しない会議の割合を入力します。</span><span class="sxs-lookup"><span data-stu-id="c6645-146">In **Percentage of conferences using voice**, type the percentage of conferences that will include audio.</span></span> 
    
  - <span data-ttu-id="c6645-147">20% の音声会議に通常のビデオも含まれる場合は、[**Including video (no Multi View) (ビデオを含む (マルチビューなし))**] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="c6645-147">If 20% of your voice conferences will also include regular video, select the **Including video (no Multi View)** check box.</span></span>
    
  - <span data-ttu-id="c6645-148">20% の会議にマルチビュー ビデオも含まれる場合は、[**Including Multi View (マルチビューを含む)**] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="c6645-148">If 20% of your conferences will also include Multi-View video, select the **Including Multi View** check box.</span></span>
    
  - <span data-ttu-id="c6645-149">音声会議の 50% には、アプリケーションの共有も含まれている場合は、**アプリケーションの共有を含む**] チェック ボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="c6645-149">If 50% of your voice conferences will also include application sharing, select the **Including application sharing** check box.</span></span>
    
  - <span data-ttu-id="c6645-150">20% の音声会議にデータのアップロード (PowerPoint のプレゼンテーションなど) が含まれる場合は、[**Including web conferencing (Web 会議を含む)**] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="c6645-150">If 20% of your voice conferences include data uploads, such as PowerPoint presentations, select the **Including web conferencing** check box.</span></span>
    
 <span data-ttu-id="c6645-151">**モビリティ**</span><span class="sxs-lookup"><span data-stu-id="c6645-151">**Mobility**</span></span>
  
- <span data-ttu-id="c6645-152">**移動が有効なユーザーの割合**Skype のモバイル デバイスを使用してビジネスのサーバーに接続するときに使用するユーザーの割合を入力します。</span><span class="sxs-lookup"><span data-stu-id="c6645-152">In **Percentage of users enabled for Mobility**, type the percentage of your users who will be enabled to connect to Skype for Business Server using mobile devices.</span></span> <span data-ttu-id="c6645-153">既定値は 40% です。</span><span class="sxs-lookup"><span data-stu-id="c6645-153">The default is 40%.</span></span> 
    
<span data-ttu-id="c6645-154">必要な情報をすべて入力すると、容量計算機によって要件が見積られます。</span><span class="sxs-lookup"><span data-stu-id="c6645-154">When you have entered all the necessary information, the capacity calculator estimates your requirements.</span></span> <span data-ttu-id="c6645-155">黄色のセルでは、CPU、メモリ、およびビジネスのサーバー パフォーマンス ラボの Skype で実行されるテストに基づく必要な帯域幅の計算値を表示します。</span><span class="sxs-lookup"><span data-stu-id="c6645-155">The yellow cells show calculated values for CPU, memory, and bandwidth requirements based on tests performed in Skype for Business Server performance labs.</span></span> <span data-ttu-id="c6645-156">この数値はガイドラインとして提供されるもので、すべてのバリエーションを逐一テスト、検証したわけではありません。</span><span class="sxs-lookup"><span data-stu-id="c6645-156">The numbers are provided as a guideline, not every single variation is tested and validated.</span></span> <span data-ttu-id="c6645-157">次の値が計算されます。</span><span class="sxs-lookup"><span data-stu-id="c6645-157">The following values are calculated:</span></span> 
  
- <span data-ttu-id="c6645-158">[**フロントエンド CPU**]: 全体の負荷が、テストで使用されたサーバーと同じ仕様のフロントエンド サーバーによって処理された場合の CPU 使用率の割合です (詳細は、本記事の最後を参照)。</span><span class="sxs-lookup"><span data-stu-id="c6645-158">**Front End CPU**: Percentage of CPU usage if the entire load were being handled by one Front End Server of the same specifications as the server that was used in testing (see the description at the end of this article).</span></span>
    
- <span data-ttu-id="c6645-159">[**ネットワーク (Mbps)**]: 対応するワークロードの帯域幅要件 (メガビット/秒 (Mbps) 単位) です。</span><span class="sxs-lookup"><span data-stu-id="c6645-159">**Network in Mbps**: Bandwidth requirements in megabits per second (Mbps) for the corresponding workload.</span></span>
    
- <span data-ttu-id="c6645-160">[**メモリ (GB)**]: 対応するワークロードで必要なメモリ (ギガバイト (GB) 単位) です。</span><span class="sxs-lookup"><span data-stu-id="c6645-160">**Memory in GB**: Memory required in gigabytes (GB) for the corresponding workload.</span></span>
    
<span data-ttu-id="c6645-161">緑色のセルには、入力した使用モデルの推奨事項が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c6645-161">The green cells show recommendations for the usage model that you entered.</span></span> 
  
- <span data-ttu-id="c6645-162">[**フロントエンド サーバーの合計**]: 必要な物理サーバーの数は、Skype for Business Server 2015 を実行する専用サーバー (デュアル プロセッサ、6 コア、2,260 メガサイクル) に基づきます。</span><span class="sxs-lookup"><span data-stu-id="c6645-162">**Total Front End Servers**: The number of physical servers required are based on dedicated servers running Skype for Business Server 2015 with dual processor, hex-core, with 2,260 megacycles.</span></span>
    
    <span data-ttu-id="c6645-163">ハイパースレッドを有効にすると、音声/ビデオをサポートするサーバーのパフォーマンスが上がることがわかっているのでお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c6645-163">Note that enabling hyperthreading is recommended and has been proven to improve performance for servers that support audio/video.</span></span>
    
- <span data-ttu-id="c6645-p119">[**エッジ サーバー**]: すべての同時ユーザーの 30% がエッジ サーバー経由で通信するという前提に基づいた、必要なエッジ サーバー数です。この割合を計算機で変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="c6645-p119">**Edge Servers**: The number of Edge Servers required, based on 30% of all concurrent users communicating through the Edge Servers. This percentage cannot be changed in the calculator.</span></span> 
    
- <span data-ttu-id="c6645-166">[**アーカイブ/通話詳細記録/ Quality of Experience (QoE) のサービス ストア**]: アーカイブ機能や監視機能に必要なストア数です (組織で有効な場合)。</span><span class="sxs-lookup"><span data-stu-id="c6645-166">**Archiving/Call Detail Recording/Quality of Experience services Store**: The number of stores required for Archiving or Monitoring features, if they are enabled in your organization.</span></span>
    
- <span data-ttu-id="c6645-167">[**必要なバックエンド データベース サーバー (必要なプール)**]: 選択したワークロードのサポートに必要なバックエンド データベース サーバーの数です。</span><span class="sxs-lookup"><span data-stu-id="c6645-167">**Back End Database Server Required (Pools Required)**: The number of back-end database servers required to support the selected workload.</span></span>
    
<span data-ttu-id="c6645-168">また、フロントエンド サーバーの合計の次の行には、計画したすべてのワークロードを組み合わせた場合の、サーバーとネットワークへの負荷に関する詳細情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c6645-168">Additionally, in the row next to Total Front End Servers, more information is provided about the load on your servers and network for all the planned workloads combined.</span></span>
  
- <span data-ttu-id="c6645-169">[**CPU の平均負荷**]: フロントエンド サーバーあたりの平均 CPU 使用率です。</span><span class="sxs-lookup"><span data-stu-id="c6645-169">**Average CPU Load**: The average CPU usage per Front End server.</span></span>
    
- <span data-ttu-id="c6645-170">[**ネットワーク (Mbps)**]: 入力した使用モデルのサポートに必要な帯域幅割り当てです。</span><span class="sxs-lookup"><span data-stu-id="c6645-170">**Network in Mbps**: The required bandwidth allocation to support the usage model that you entered.</span></span>
    
- <span data-ttu-id="c6645-171">[**メモリ (GB)**]: 各フロントエンド サーバーで必要なメモリ (ギガバイト単位) です。</span><span class="sxs-lookup"><span data-stu-id="c6645-171">**Memory in GB**: Memory, in gigabytes, required for each Front End server.</span></span>
    
### <a name="adjusting-for-your-processors"></a><span data-ttu-id="c6645-172">プロセッサに応じた調整</span><span class="sxs-lookup"><span data-stu-id="c6645-172">Adjusting For Your Processors</span></span>

<span data-ttu-id="c6645-173">スプレッドシートの CPU 使用率の数値はすべて、各サーバーにデュアル プロセッサ、2.26 GHz の 6 コア、32 GB 以上のメモリ、8 台以上の 10,000-RPM ハード ディスク ドライブ (72 GB 以上の空きディスク容量あり) が搭載されていることを前提とします。</span><span class="sxs-lookup"><span data-stu-id="c6645-173">All the CPU usage figures in the spreadsheet assume that each server has a dual processor, hex-core with 2.26 GHz, at least 32 GB of memory, and 8 or more 10,000-RPM hard disk drives with at least 72 GB free disk space.</span></span> 
  
<span data-ttu-id="c6645-174">サーバーにこの仕様とは異なるプロセッサが搭載されている場合は、数値を調整してご使用のハードウェアに合わせることができます。</span><span class="sxs-lookup"><span data-stu-id="c6645-174">If your servers have different processors, you can adjust the figures to match your hardware.</span></span>
  

