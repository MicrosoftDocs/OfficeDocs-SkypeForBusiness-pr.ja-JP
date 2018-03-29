---
title: Skype for Business 2015 でのサーバーのメモリ容量制限の監視
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 1/31/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1697ea71-6fcf-480d-b4e9-cd79f94d247e
description: '概要: ビジネス サーバー 2015 の Skype のサーバー メモリ容量の制限を監視する方法を説明します。'
ms.openlocfilehash: df05cdf43a7f09f49760f9671c900d6a9ea992b1
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="monitor-for-server-memory-capacity-limits-in-skype-for-business-server-2015"></a><span data-ttu-id="381bd-103">Skype for Business 2015 でのサーバーのメモリ容量制限の監視</span><span class="sxs-lookup"><span data-stu-id="381bd-103">Monitor for server memory capacity limits in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="381bd-104">**の概要:**ビジネス サーバー 2015 の Skype のサーバー メモリ容量の制限を監視する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="381bd-104">**Summary:** Learn how to monitor for server memory capacity limits in Skype for Business Server 2015.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="381bd-105">キャパシティ ・ プランニングを参照するこのトピックの情報は、Lync 2010 モバイル クライアントやモバイル サービス (Mcx) にのみ関係します。</span><span class="sxs-lookup"><span data-stu-id="381bd-105">The information in this topic that refers to Capacity Planning pertains only to Lync 2010 Mobile clients and the Mobility Service (Mcx).</span></span> <span data-ttu-id="381bd-106">キャパシティ ・ プランニングのユニファイド コミュニケーション Web API (UCWA)、Lync 2013 のモバイル クライアントで使用されているは、Lync Server 2013、計画ツールによって提供されます。</span><span class="sxs-lookup"><span data-stu-id="381bd-106">Capacity Planning for the Unified Communications Web API (UCWA), used by the Lync 2013 Mobile clients, is provided by the Lync Server 2013, Planning Tool.</span></span> 
  
<span data-ttu-id="381bd-107">モビリティの 2 つのパフォーマンス カウンターを使用しての現在の使用状況を判断し、ビジネス サーバー 2015 モビリティ サービスの (Mcx)、同様に UCWA のメモリ使用量を監視して、Skype の容量の計画を支援することができます。</span><span class="sxs-lookup"><span data-stu-id="381bd-107">Two mobility performance counters can help you to determine your current usage and help you plan capacity for the Skype for Business Server 2015 Mobility Service (Mcx), as well as to monitor memory usage for UCWA.</span></span> <span data-ttu-id="381bd-108">UCWA、 **LS:WEB - UCWA**は、カウンターのカテゴリです。</span><span class="sxs-lookup"><span data-stu-id="381bd-108">For UCWA, the counter category is **LS:WEB - UCWA**.</span></span> <span data-ttu-id="381bd-109">モビリティ サービス (Mcx) は、カウンターは、 **LS:WEB のモバイル通信サービス**」カテゴリの下。</span><span class="sxs-lookup"><span data-stu-id="381bd-109">For the Mobility Service (Mcx), the counters are under the category **LS:WEB - Mobile Communication Service**.</span></span> <span data-ttu-id="381bd-110">カウンターを監視するのには次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="381bd-110">The counters to monitor are:</span></span>
  
- <span data-ttu-id="381bd-111">**Currently Active Session Count with Active Presence Subscriptions**。これは、UCWA または Mobility Service (Mcx) 経由で登録されたエンドポイントのうち、アクティブなプレゼンス サブスクリプションを持つエンドポイントの現在数 (常時接続されたモバイル ユーザーの数) です。</span><span class="sxs-lookup"><span data-stu-id="381bd-111">**Currently Active Session Count with Active Presence Subscriptions**, which is the current number of endpoints registered through UCWA or the Mobility Service (Mcx) that have active presence subscriptions (number of always-connected mobile users)</span></span>
    
- <span data-ttu-id="381bd-112">**Currently Active Session Count**。これは、UCWA または Mobility Service 経由で登録されたエンドポイントの現在数です。</span><span class="sxs-lookup"><span data-stu-id="381bd-112">**Currently Active Session Count**, which is the current number of endpoints registered through UCWA or the Mobility Service</span></span>
    
<span data-ttu-id="381bd-113">時間の経過とともに**アクティブなプレゼンス サブスクリプションの現在アクティブなセッションの数**と**現在アクティブなセッションの数**との差が小さい場合は、つまり、ほとんどのモバイル デバイス ユーザーが、アプリなど、常に接続されているデバイスまたはNokia モバイル デバイス (Mcx のみ)。</span><span class="sxs-lookup"><span data-stu-id="381bd-113">If the difference between **Currently Active Session Count with Active Presence Subscriptions** and **Currently Active Session Count** is small over time, this means that most mobile device users have an always-connected device, such as an Android or Nokia mobile device (for Mcx only).</span></span> <span data-ttu-id="381bd-114">UCWA 常に接続されているデバイスには、Lync 2013 のモバイル クライアントを実行している Apple と Android のデバイス)。</span><span class="sxs-lookup"><span data-stu-id="381bd-114">UCWA always-connected devices include Apple and Android devices running Lync 2013 Mobile clients).</span></span> <span data-ttu-id="381bd-115">**現在アクティブなセッションの数**が**アクティブなプレゼンス サブスクリプションの現在アクティブなセッションの数**よりも多くの場合より多くのユーザーで、Apple iOS デバイスまたは Windows Phone の下にあるなど、バック グラウンドのエンドポイント デバイスを使用している、このことを示します。Mcx。</span><span class="sxs-lookup"><span data-stu-id="381bd-115">If **Currently Active Session Count** is much higher than **Currently Active Session Count with Active Presence Subscriptions**, this indicates that more users are using a background endpoint device, such as an Apple iOS device or Windows Phone under Mcx.</span></span> <span data-ttu-id="381bd-116">(Windows Phone は次のように登録する Lync 2013 のモバイル クライアントからのみ) です。</span><span class="sxs-lookup"><span data-stu-id="381bd-116">(Windows Phone is the only Lync 2013 Mobile client that will register as this).</span></span>
  
<span data-ttu-id="381bd-117">予想される使用率、容量計画の結果、および継続的な監視に基づいて、**アクティブなプレゼンス サブスクリプションの現在アクティブなセッションの数**と**現在アクティブなセッションの数**のパフォーマンス カウンターの制限を設定する必要があります。モビリティ サービスおよびその他のフロント エンド サーバーのカウンターです。</span><span class="sxs-lookup"><span data-stu-id="381bd-117">You should set a limit on the **Currently Active Session Count with Active Presence Subscriptions** and **Currently Active Session Count** performance counters based on your expected usage, capacity planning results, and ongoing monitoring of Mobility Service and other Front End Server counters.</span></span> <span data-ttu-id="381bd-118">設定する制限を使用すると、サーバーの処理能力を評価し、容量を超えた場合にアラートを生成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="381bd-118">The limits you set should enable you to evaluate server capacity and raise alerts when capacity is exceeded.</span></span>
  
<span data-ttu-id="381bd-119">適切な制限を確認するのには、モビリティ サービスのフロント エンド サーバー上で利用可能なメモリの量を決定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="381bd-119">To determine the appropriate limits, you need to first determine how much memory is available on the Front End Server for the Mobility Service.</span></span> <span data-ttu-id="381bd-120">カウンターを監視し、次の式に従って、追加容量の計画が必要な時期を確認します。</span><span class="sxs-lookup"><span data-stu-id="381bd-120">Monitor the counters to determine when you need to plan for extra capacity, according to the following formula:</span></span>
  
<span data-ttu-id="381bd-121">Mcx モビリティ サービス (MB) で使用されているメモリの合計 = 164 + (400 + 134)/1024 ***プレゼンス サブスクリプションがアクティブで現在アクティブなセッションの数**+ 400/1024 * (**現在アクティブなセッションの数** - **での現在アクティブなセッション数アクティブなプレゼンス サブスクリプション**)</span><span class="sxs-lookup"><span data-stu-id="381bd-121">Total memory used by the Mcx Mobility Service (MB) = 164 + (400 + 134) / 1024 * **Currently Active Session Count with Active Presence Subscriptions** + 400 / 1024 * ( **Currently Active Session Count** - **Currently Active Session Count with Active Presence Subscriptions**)</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="381bd-122">Microsoft Lync Server 2010 の容量電卓は、スプレッドシートのすべてのビジネスのサーバーでは、CPU、メモリ、およびハード ディスク ドライブを含む Skype の要件を決定する、プランナーを使用する数式が表示されます。</span><span class="sxs-lookup"><span data-stu-id="381bd-122">The Microsoft Lync Server 2010 Capacity Calculator is a spreadsheet that is prepopulated with all of the formulas that enable a planner to determine what the requirements will be for the Skype for Business servers, including CPU, memory, and hard drive.</span></span> <span data-ttu-id="381bd-123">[スプレッドシートとの関連ドキュメントをダウンロードする](https://go.microsoft.com/fwlink/p/?LinkID=212657)ことができます。</span><span class="sxs-lookup"><span data-stu-id="381bd-123">You can [download the spreadsheet and an associated document](https://go.microsoft.com/fwlink/p/?LinkID=212657).</span></span> 
  
<span data-ttu-id="381bd-124">フロント エンド サーバーには、フェールオーバーの状況で移動サービスをサポートするために利用可能な十分なメモリが必要があります。</span><span class="sxs-lookup"><span data-stu-id="381bd-124">The Front End Server needs enough available memory to support the Mobility Service in failover situations.</span></span> <span data-ttu-id="381bd-125">**\Available Mbytes**カウンターを使用するかを使用するモバイル サービスを期待するメモリ容量を計画するため、前述の式を使用して、フロント エンド サーバー上で現在利用可能なメモリを監視できます。</span><span class="sxs-lookup"><span data-stu-id="381bd-125">You can monitor the current available memory on the Front End Server by using the **Memory\Available Mbytes** counter, or by using the equation mentioned earlier, to plan for the amount of memory that you expect the Mobility Service to use.</span></span>
  
<span data-ttu-id="381bd-126">移動ユーザーの数を計画する際に、フロント エンド サーバー上の利用できるメモリ量が 1,500 MB よりも小さい場合は、モビリティ サービスをサポートするためにより多くのハードウェアを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="381bd-126">If the amount of memory available on the Front End Server is lower than 1,500 MB when you plan for the expected number of mobility users, you need to add more hardware to support the Mobility Service.</span></span> <span data-ttu-id="381bd-127">詳細については、操作マニュアルの[ビジネス サーバー 2015 の Skype でのパフォーマンスのモニターの移動](monitor-mobility-performance.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="381bd-127">For more details, see [Monitor mobility for performance in Skype for Business Server 2015](monitor-mobility-performance.md) in the Operations documentation.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="381bd-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="381bd-128">See also</span></span>

#### 

[<span data-ttu-id="381bd-129">モビリティ ビジネス サーバー 2015 の Skype でのパフォーマンスを監視します。</span><span class="sxs-lookup"><span data-stu-id="381bd-129">Monitor mobility for performance in Skype for Business Server 2015</span></span>](monitor-mobility-performance.md)

