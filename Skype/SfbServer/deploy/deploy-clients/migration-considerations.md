---
title: Skype Room System の移行に関する考慮事項
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: davgroom
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: df9f33b6-0360-4354-b651-bd35da533e33
description: このトピックでは、複数のバージョンの Skype for Business Server および Lync Server を使用している環境に Skype Room システムを展開する方法について説明します。
ms.openlocfilehash: f5da7f92c7ab947d5e6d68c19823d227f8ae3ca3
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2019
ms.locfileid: "36234210"
---
# <a name="skype-room-system-migration-considerations"></a><span data-ttu-id="77068-103">Skype Room System の移行に関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="77068-103">Skype Room System migration considerations</span></span>
 
<span data-ttu-id="77068-104">このトピックでは、複数のバージョンの Skype for Business Server および Lync Server を使用している環境に Skype Room システムを展開する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="77068-104">Read this topic to learn about how to deploy Skype Room System in an environment that has multiple versions of Skype for Business Server and Lync Server.</span></span>
  
## <a name="migration-considerations"></a><span data-ttu-id="77068-105">移行に関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="77068-105">Migration considerations</span></span>

<span data-ttu-id="77068-106">このセクションでは、さまざまなバージョンの Skype for Business Server (Lync Server) を含むマルチプール環境に Skype Room システムを展開する場合のガイダンスを示します。</span><span class="sxs-lookup"><span data-stu-id="77068-106">This section provides guidance if you are deploying Skype Room System in a multi-pool environment that includes different versions of Skype for Business Server, or Lync Server.</span></span> 
  
<span data-ttu-id="77068-107">Lync Server のユーザー レプリケーター (UR) コンポーネントは、Active Directory からユーザー オブジェクトを取得し、それを Lync Server のバックエンドである SQL Server データベースに登録します。</span><span class="sxs-lookup"><span data-stu-id="77068-107">The User Replicator (UR) component in Lync Server gets user objects from Active Directory and places them into the Lync Server back-end SQL Server database.</span></span> <span data-ttu-id="77068-108">Lync Server 2013 の UR のみが、Skype Room System オブジェクトを認識しています。</span><span class="sxs-lookup"><span data-stu-id="77068-108">Only the UR in Lync Server 2013 is aware of Skype Room System objects.</span></span> <span data-ttu-id="77068-109">前のバージョンの Lync Server および Office Communications Server の UR は、LRS オブジェクトを指定する Active Directory 属性を検出しないため、認識もできません。</span><span class="sxs-lookup"><span data-stu-id="77068-109">The UR in previous versions of Lync Server and Office Communications Server do not detect the Active Directory attributes that designate LRS objects, and therefore was not aware of them.</span></span> 
  
<span data-ttu-id="77068-110">Skype Room System アカウントが Lync にサインインしようとして、SRV レコードまたは DNS A レコードに基づいて自動検出を実行していて、それらのアカウントが以前のバージョンの Lync Server または Office Communications Server をポイントしている場合、LRS はから404が見つかりませんでした。 従来のプール。</span><span class="sxs-lookup"><span data-stu-id="77068-110">If a Skype Room System account tries to sign in to Lync , and performs auto discovery based on SRV record or DNS A record look up, and if those accounts point to a previous version of Lync Server or Office Communications Server, LRS will receive a 404 Not Found response from the legacy pool.</span></span> <span data-ttu-id="77068-111">従来のプールでは、Skype Room システムを Lync Server 2013 ホームプールにリダイレクトすることはできません。</span><span class="sxs-lookup"><span data-stu-id="77068-111">The legacy pool will not be able to redirect Skype Room System to its Lync Server 2013 home pool.</span></span> 
  
<span data-ttu-id="77068-112">この問題は、次の方法で対応できます。</span><span class="sxs-lookup"><span data-stu-id="77068-112">You can address this problem with the following options:</span></span> 
  
- <span data-ttu-id="77068-113">自動検出 SRV レコード (_sipinternaltls._tcp.contoso.com) で Lync Server 2013 プールを参照させる。</span><span class="sxs-lookup"><span data-stu-id="77068-113">Point your autodiscover SRV record (_sipinternaltls._tcp.contoso.com) to Lync Server 2013 pool.</span></span>
    
- <span data-ttu-id="77068-114">最初のオプションが利用できない場合は、LRS を手動で構成して、Lync Server 2013 プールアドレスを提供する必要があります。 Skype Room System コンソールアプリケーションで直接構成します。</span><span class="sxs-lookup"><span data-stu-id="77068-114">If the first option isn't possible, you must manually configure LRS and provide the Lync Server 2013 pool address by directly configuring it in the Skype Room System console application.</span></span> 
    
- <span data-ttu-id="77068-115">Skype Room System が企業ネットワークの外部に展開されていて、Lync Edge サーバーが展開されて、従来のプールまたはディレクターをポイントするように構成されている場合は、Lync Server 2013 プールを参照するセカンダリエッジサーバーサイトが必要です。</span><span class="sxs-lookup"><span data-stu-id="77068-115">If Skype Room System is deployed outside the corporate network, and a Lync Edge Server has been deployed and configured to point to a legacy pool or director, a secondary Edge Server site is required, which points to the Lync Server 2013 pool.</span></span> <span data-ttu-id="77068-116">2 台目の Edge Server の展開に関する情報は、Edge Server の展開に関するドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="77068-116">Refer to the Edge Server deployment documentation for more information about deploying a secondary Edge Server.</span></span> 
    
## <a name="skype-room-system-interoperability-with-a-lync-server-2010-pool"></a><span data-ttu-id="77068-117">Lync Server 2010 プールを使った Skype Room System の相互運用性</span><span class="sxs-lookup"><span data-stu-id="77068-117">Skype Room System Interoperability with a Lync Server 2010 Pool</span></span>

<span data-ttu-id="77068-118">移行中に、Lync Server 2010 プールをホームにしているユーザーが会議をスケジュールし、Skype Room System アカウントを招待した場合、Skype Room System クライアントは、会議に出席するときに制限された機能を持つことになります。</span><span class="sxs-lookup"><span data-stu-id="77068-118">During migration, if a user who is homed on a Lync Server 2010 pool schedules a meeting and invites the Skype Room System account, the Skype Room System client will have limited functionality while attending the meeting.</span></span> 
  
<span data-ttu-id="77068-119">Skype Room System クライアントが、Lync Server 2010 を使っているユーザーによって開催されたスケジュールされた電話会議に参加すると、Skype Room System には以下の会議の制限があります。</span><span class="sxs-lookup"><span data-stu-id="77068-119">When the Skype Room System client joins a scheduled conference call that has been organized by a user homed on Lync Server 2010, Skype Room System has the following in-meeting limitations:</span></span> 
  
- <span data-ttu-id="77068-120">Skype Room System では、マルチビュービデオギャラリーを表示できません。</span><span class="sxs-lookup"><span data-stu-id="77068-120">Skype Room System cannot show the multi-view video gallery.</span></span>
    
- <span data-ttu-id="77068-121">Skype Room System クライアントが発表者である場合、参加者にビデオロックを適用することはできません。</span><span class="sxs-lookup"><span data-stu-id="77068-121">If the Skype Room System client is the presenter, it cannot apply video lock on participants.</span></span>
    
- <span data-ttu-id="77068-122">Lync Server 2013 会議ポリシーで許可されている場合でも、次の理由により、1080p のビデオ解像度 (受信または送信) を表示できません。</span><span class="sxs-lookup"><span data-stu-id="77068-122">Skype Room System cannot show 1080p video resolution (inbound or outbound), even if the Lync Server 2013 conferencing policy allows it, because of the following:</span></span> 
    
  - <span data-ttu-id="77068-123">Lync Server 2010 は、1080p の解像度をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="77068-123">Lync Server 2010 doesn't support 1080p resolution.</span></span>
    
  - <span data-ttu-id="77068-124">Skype Room System は、ビデオ解像度の開催者の会議ポリシーによって常に制限されています。</span><span class="sxs-lookup"><span data-stu-id="77068-124">Skype Room System is always limited by the organizer's conferencing policy for video resolution.</span></span> <span data-ttu-id="77068-125">したがって、Lync 2010 プールが720p の解像度をサポートしている場合でも、開催者のポリシーでサポートされていない限り、Skype Room システムは720p の解像度を利用することはできません。</span><span class="sxs-lookup"><span data-stu-id="77068-125">Therefore, even if the Lync 2010 pool supports 720p resolution, Skype Room System will not be able to take advantage of 720p resolution as long as organizer's policy doesn't support it.</span></span> 
    
- <span data-ttu-id="77068-p105">Lync 2013 クライアントは、会議室の LRS プレゼンスを検出し、自動ミュートにより実際の会議室のエコーを回避します。この機能は、Lync Server 2010 でホストされている会議では動作しません。</span><span class="sxs-lookup"><span data-stu-id="77068-p105">Lync 2013 clients detect LRS presence in the meeting room, and they auto-mute themselves to avoid echo in the physical meeting room. This feature does not work in meetings hosted on Lync Server 2010.</span></span>
    
- <span data-ttu-id="77068-128">Lync Server 2010 でホストされている会議では、デスクトップ共有のパフォーマンスに制限が生じます。</span><span class="sxs-lookup"><span data-stu-id="77068-128">There are limitations on desktop sharing performance for meetings hosted on Lync Server 2010.</span></span>
    
- <span data-ttu-id="77068-129">ユーザーは、Skype Room System で Lync 2010 上でホストされているプライベート (制限された) 会議に参加することはできません。</span><span class="sxs-lookup"><span data-stu-id="77068-129">Users won't be able to join private (restricted) meetings that are hosted on Lync 2010 with Skype Room System.</span></span>
    

