---
title: Skype Room System の移行に関する考慮事項
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: df9f33b6-0360-4354-b651-bd35da533e33
description: このトピックでは、Skype for Business Server と Lync Server の複数のバージョンを持つ環境に Skype Room System を展開する方法について説明します。
ms.openlocfilehash: 30b2a4733ea2e2e42b8a879914a2e0e3c4903c8e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805787"
---
# <a name="skype-room-system-migration-considerations"></a><span data-ttu-id="fb972-103">Skype Room System の移行に関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="fb972-103">Skype Room System migration considerations</span></span>
 
<span data-ttu-id="fb972-104">このトピックでは、Skype for Business Server と Lync Server の複数のバージョンを持つ環境に Skype Room System を展開する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="fb972-104">Read this topic to learn about how to deploy Skype Room System in an environment that has multiple versions of Skype for Business Server and Lync Server.</span></span>
  
## <a name="migration-considerations"></a><span data-ttu-id="fb972-105">移行に関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="fb972-105">Migration considerations</span></span>

<span data-ttu-id="fb972-106">このセクションでは、異なるバージョンの Skype for Business Server または Lync Server を含むマルチプール環境に Skype Room System を展開する場合のガイダンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="fb972-106">This section provides guidance if you are deploying Skype Room System in a multi-pool environment that includes different versions of Skype for Business Server, or Lync Server.</span></span> 
  
<span data-ttu-id="fb972-107">Lync Server のユーザー レプリケーター (UR) コンポーネントは、Active Directory からユーザー オブジェクトを取得し、それらを Lync Server のバック エンド SQL Serverします。</span><span class="sxs-lookup"><span data-stu-id="fb972-107">The User Replicator (UR) component in Lync Server gets user objects from Active Directory and places them into the Lync Server back-end SQL Server database.</span></span> <span data-ttu-id="fb972-108">Lync Server 2013 の UR だけが Skype Room System オブジェクトを認識します。</span><span class="sxs-lookup"><span data-stu-id="fb972-108">Only the UR in Lync Server 2013 is aware of Skype Room System objects.</span></span> <span data-ttu-id="fb972-109">以前のバージョンの Lync Server および Office Communications Server の UR は、LRS オブジェクトを指定する Active Directory 属性を検出し、認識していなくためです。</span><span class="sxs-lookup"><span data-stu-id="fb972-109">The UR in previous versions of Lync Server and Office Communications Server do not detect the Active Directory attributes that designate LRS objects, and therefore was not aware of them.</span></span> 
  
<span data-ttu-id="fb972-110">Skype Room System アカウントが Lync にサインインしようとして、SRV レコードまたは DNS A レコードの検索に基づいて自動検出を実行し、それらのアカウントが以前のバージョンの Lync Server または Office Communications Server をポイントしている場合、LRS はレガシ プールから 404 Not Found 応答を受信します。</span><span class="sxs-lookup"><span data-stu-id="fb972-110">If a Skype Room System account tries to sign in to Lync , and performs auto discovery based on SRV record or DNS A record look up, and if those accounts point to a previous version of Lync Server or Office Communications Server, LRS will receive a 404 Not Found response from the legacy pool.</span></span> <span data-ttu-id="fb972-111">従来のプールでは、Skype Room System を Lync Server 2013 ホーム プールにリダイレクトできません。</span><span class="sxs-lookup"><span data-stu-id="fb972-111">The legacy pool will not be able to redirect Skype Room System to its Lync Server 2013 home pool.</span></span> 
  
<span data-ttu-id="fb972-112">この問題に対処するには、次のオプションを使用します。</span><span class="sxs-lookup"><span data-stu-id="fb972-112">You can address this problem with the following options:</span></span> 
  
- <span data-ttu-id="fb972-113">自動検出 SRV レコード (_sipinternaltls._tcp.contoso.com) を Lync Server 2013 プールの接続ポイントにします。</span><span class="sxs-lookup"><span data-stu-id="fb972-113">Point your autodiscover SRV record (_sipinternaltls._tcp.contoso.com) to Lync Server 2013 pool.</span></span>
    
- <span data-ttu-id="fb972-114">最初のオプションを使用できない場合は、LRS を手動で構成し、Skype Room System コンソール アプリケーションで直接構成して Lync Server 2013 プール アドレスを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fb972-114">If the first option isn't possible, you must manually configure LRS and provide the Lync Server 2013 pool address by directly configuring it in the Skype Room System console application.</span></span> 
    
- <span data-ttu-id="fb972-115">Skype Room System が企業ネットワークの外部に展開され、Lync エッジ サーバーが展開され、従来のプールまたはディレクターをポイントするように構成されている場合は、Lync Server 2013 プールを指すセカンダリ エッジ サーバー サイトが必要です。</span><span class="sxs-lookup"><span data-stu-id="fb972-115">If Skype Room System is deployed outside the corporate network, and a Lync Edge Server has been deployed and configured to point to a legacy pool or director, a secondary Edge Server site is required, which points to the Lync Server 2013 pool.</span></span> <span data-ttu-id="fb972-116">セカンダリ エッジ サーバーの展開の詳細については、エッジ サーバーの展開に関するドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="fb972-116">Refer to the Edge Server deployment documentation for more information about deploying a secondary Edge Server.</span></span> 
    
## <a name="skype-room-system-interoperability-with-a-lync-server-2010-pool"></a><span data-ttu-id="fb972-117">Skype Room System と Lync Server 2010 プールの相互運用性</span><span class="sxs-lookup"><span data-stu-id="fb972-117">Skype Room System Interoperability with a Lync Server 2010 Pool</span></span>

<span data-ttu-id="fb972-118">移行中に、Lync Server 2010 プールにホームを持つユーザーが会議をスケジュールし、Skype Room System アカウントを招待した場合、Skype Room System クライアントは会議への出席中に機能が制限されます。</span><span class="sxs-lookup"><span data-stu-id="fb972-118">During migration, if a user who is homed on a Lync Server 2010 pool schedules a meeting and invites the Skype Room System account, the Skype Room System client will have limited functionality while attending the meeting.</span></span> 
  
<span data-ttu-id="fb972-119">Skype Room System クライアントが、Lync Server 2010 にホームであるユーザーによって開催されたスケジュールされた電話会議に参加する場合、Skype Room System には次の会議中の制限があります。</span><span class="sxs-lookup"><span data-stu-id="fb972-119">When the Skype Room System client joins a scheduled conference call that has been organized by a user homed on Lync Server 2010, Skype Room System has the following in-meeting limitations:</span></span> 
  
- <span data-ttu-id="fb972-120">Skype Room System では、マルチビュー ビデオ ギャラリーを表示できません。</span><span class="sxs-lookup"><span data-stu-id="fb972-120">Skype Room System cannot show the multi-view video gallery.</span></span>
    
- <span data-ttu-id="fb972-121">Skype Room System クライアントが発表者の場合、参加者にビデオ ロックを適用できません。</span><span class="sxs-lookup"><span data-stu-id="fb972-121">If the Skype Room System client is the presenter, it cannot apply video lock on participants.</span></span>
    
- <span data-ttu-id="fb972-122">次の理由により、Lync Server 2013 会議ポリシーで許可されている場合でも、Skype Room System は 1080p ビデオ解像度 (受信または送信) を表示できません。</span><span class="sxs-lookup"><span data-stu-id="fb972-122">Skype Room System cannot show 1080p video resolution (inbound or outbound), even if the Lync Server 2013 conferencing policy allows it, because of the following:</span></span> 
    
  - <span data-ttu-id="fb972-123">Lync Server 2010 は、1080p の解像度をサポートしません。</span><span class="sxs-lookup"><span data-stu-id="fb972-123">Lync Server 2010 doesn't support 1080p resolution.</span></span>
    
  - <span data-ttu-id="fb972-124">Skype Room System は、ビデオの解決に関する開催者の会議ポリシーによって常に制限されます。</span><span class="sxs-lookup"><span data-stu-id="fb972-124">Skype Room System is always limited by the organizer's conferencing policy for video resolution.</span></span> <span data-ttu-id="fb972-125">したがって、Lync 2010 プールが 720p の解像度をサポートしている場合でも、開催者のポリシーでサポートされていない限り、Skype Room System では 720p の解像度を利用できない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="fb972-125">Therefore, even if the Lync 2010 pool supports 720p resolution, Skype Room System will not be able to take advantage of 720p resolution as long as organizer's policy doesn't support it.</span></span> 
    
- <span data-ttu-id="fb972-126">Lync 2013 クライアントは会議室内の LRS プレゼンスを検出し、物理的な会議室でのエコーを回避するために自身を自動ミュートします。</span><span class="sxs-lookup"><span data-stu-id="fb972-126">Lync 2013 clients detect LRS presence in the meeting room, and they auto-mute themselves to avoid echo in the physical meeting room.</span></span> <span data-ttu-id="fb972-127">この機能は、Lync Server 2010 でホストされている会議では機能しません。</span><span class="sxs-lookup"><span data-stu-id="fb972-127">This feature does not work in meetings hosted on Lync Server 2010.</span></span>
    
- <span data-ttu-id="fb972-128">Lync Server 2010 でホストされる会議のデスクトップ共有のパフォーマンスには制限があります。</span><span class="sxs-lookup"><span data-stu-id="fb972-128">There are limitations on desktop sharing performance for meetings hosted on Lync Server 2010.</span></span>
    
- <span data-ttu-id="fb972-129">ユーザーは、Skype Room System を使用して Lync 2010 でホストされているプライベート (制限付き) 会議に参加できない。</span><span class="sxs-lookup"><span data-stu-id="fb972-129">Users won't be able to join private (restricted) meetings that are hosted on Lync 2010 with Skype Room System.</span></span>
    

