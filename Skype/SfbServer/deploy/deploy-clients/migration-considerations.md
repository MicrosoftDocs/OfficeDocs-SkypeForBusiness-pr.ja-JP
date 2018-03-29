---
title: Skype Room System の移行に関する考慮事項
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/4/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: df9f33b6-0360-4354-b651-bd35da533e33
description: ビジネス サーバーと Lync Server の複数のバージョンの Skype を持つ環境で Skype ルームのシステムを展開する方法の詳細については、このトピックを参照してください。
ms.openlocfilehash: f71c6557a8b9a98f712541c4424ba57a49536164
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="skype-room-system-migration-considerations"></a><span data-ttu-id="28887-103">Skype Room System の移行に関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="28887-103">Skype Room System migration considerations</span></span>
 
<span data-ttu-id="28887-104">ビジネス サーバーと Lync Server の複数のバージョンの Skype を持つ環境で Skype ルームのシステムを展開する方法の詳細については、このトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="28887-104">Read this topic to learn about how to deploy Skype Room System in an environment that has multiple versions of Skype for Business Server and Lync Server.</span></span>
  
## <a name="migration-considerations"></a><span data-ttu-id="28887-105">移行に関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="28887-105">Migration considerations</span></span>

<span data-ttu-id="28887-106">このセクションでは、ビジネス サーバー、Lync Server では、Office 通信 Server 2007 の R2 の Skype のバージョンを含む複数のプール環境で Skype ルームのシステムを導入する場合のガイダンスを示します。</span><span class="sxs-lookup"><span data-stu-id="28887-106">This section provides guidance if you are deploying Skype Room System in a multi-pool environment that includes different versions of Skype for Business Server, Lync Server, or Office Communications Server 2007 R2.</span></span> 
  
<span data-ttu-id="28887-107">Lync Server のユーザー レプリケーター (UR) コンポーネントは、Active Directory からユーザー オブジェクトを取得し、それを Lync Server のバックエンドである SQL Server データベースに登録します。</span><span class="sxs-lookup"><span data-stu-id="28887-107">The User Replicator (UR) component in Lync Server gets user objects from Active Directory and places them into the Lync Server back-end SQL Server database.</span></span> <span data-ttu-id="28887-108">Skype ルームのシステム オブジェクトへの対応、Lync Server 2013 で UR のみです。</span><span class="sxs-lookup"><span data-stu-id="28887-108">Only the UR in Lync Server 2013 is aware of Skype Room System objects.</span></span> <span data-ttu-id="28887-109">前のバージョンの Lync Server および Office Communications Server の UR は、LRS オブジェクトを指定する Active Directory 属性を検出しないため、認識もできません。</span><span class="sxs-lookup"><span data-stu-id="28887-109">The UR in previous versions of Lync Server and Office Communications Server do not detect the Active Directory attributes that designate LRS objects, and therefore was not aware of them.</span></span> 
  
<span data-ttu-id="28887-110">Skype ルーム システム アカウントが Lync にサインインしようとすると、SRV レコード、または、DNS の A レコードの検索に基づく自動検出を実行し、それらのアカウントが Lync Server または Office Communications Server の以前のバージョンを指す場合、LRS は応答が 404 見つかりませんから 従来のプールです。</span><span class="sxs-lookup"><span data-stu-id="28887-110">If a Skype Room System account tries to sign in to Lync , and performs auto discovery based on SRV record or DNS A record look up, and if those accounts point to a previous version of Lync Server or Office Communications Server, LRS will receive a 404 Not Found response from the legacy pool.</span></span> <span data-ttu-id="28887-111">従来のプールは Skype ルームのシステムを Lync Server 2013 のホーム プールにリダイレクトすることができません。</span><span class="sxs-lookup"><span data-stu-id="28887-111">The legacy pool will not be able to redirect Skype Room System to its Lync Server 2013 home pool.</span></span> 
  
<span data-ttu-id="28887-112">この問題は、次の方法で対応できます。</span><span class="sxs-lookup"><span data-stu-id="28887-112">You can address this problem with the following options:</span></span> 
  
- <span data-ttu-id="28887-113">自動検出 SRV レコード (_sipinternaltls._tcp.contoso.com) で Lync Server 2013 プールを参照させる。</span><span class="sxs-lookup"><span data-stu-id="28887-113">Point your autodiscover SRV record (_sipinternaltls._tcp.contoso.com) to Lync Server 2013 pool.</span></span>
    
- <span data-ttu-id="28887-114">最初のオプションが使用できない場合は、LRS を構成して Skype ルーム システムのコンソール アプリケーションで直接構成することによって、Lync Server 2013 プールのアドレスを提供する手動でする必要があります。</span><span class="sxs-lookup"><span data-stu-id="28887-114">If the first option isn't possible, you must manually configure LRS and provide the Lync Server 2013 pool address by directly configuring it in the Skype Room System console application.</span></span> 
    
- <span data-ttu-id="28887-115">Skype ルーム システムは、企業ネットワークの外部展開し、Lync エッジ サーバーを展開し、従来のプールまたはディレクターを指すように構成されている、エッジ サーバーのセカンダリ サイトが必要な場合は、Lync Server 2013 プールを指します。</span><span class="sxs-lookup"><span data-stu-id="28887-115">If Skype Room System is deployed outside the corporate network, and a Lync Edge Server has been deployed and configured to point to a legacy pool or director, a secondary Edge Server site is required, which points to the Lync Server 2013 pool.</span></span> <span data-ttu-id="28887-116">2 台目の Edge Server の展開に関する情報は、Edge Server の展開に関するドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="28887-116">Refer to the Edge Server deployment documentation for more information about deploying a secondary Edge Server.</span></span> 
    
## <a name="skype-room-system-interoperability-with-a-lync-server-2010-pool"></a><span data-ttu-id="28887-117">Lync Server 2010 プールで Skype ルーム システムの相互運用性</span><span class="sxs-lookup"><span data-stu-id="28887-117">Skype Room System Interoperability with a Lync Server 2010 Pool</span></span>

<span data-ttu-id="28887-118">移行中に、Lync Server 2010 プール上のホーム ユーザーは、会議をスケジュールし、Skype ルーム システム アカウントへの招待の場合 Skype ルーム システムのクライアントの機能が制限、ミーティングへの参加中に。</span><span class="sxs-lookup"><span data-stu-id="28887-118">During migration, if a user who is homed on a Lync Server 2010 pool schedules a meeting and invites the Skype Room System account, the Skype Room System client will have limited functionality while attending the meeting.</span></span> 
  
<span data-ttu-id="28887-119">Skype ルーム システム クライアント別に整理しているスケジュールされた電話会議に参加するときは、ユーザーが Lync Server 2010 のホーム、Skype ルームのシステムには次の会議での制限。</span><span class="sxs-lookup"><span data-stu-id="28887-119">When the Skype Room System client joins a scheduled conference call that has been organized by a user homed on Lync Server 2010, Skype Room System has the following in-meeting limitations:</span></span> 
  
- <span data-ttu-id="28887-120">Skype ルーム システムは、複数のビューのビデオ ギャラリーを表示できません。</span><span class="sxs-lookup"><span data-stu-id="28887-120">Skype Room System cannot show the multi-view video gallery.</span></span>
    
- <span data-ttu-id="28887-121">Skype ルーム システムのクライアントが発表者の場合は、参加者のビデオのロックに適用できません。</span><span class="sxs-lookup"><span data-stu-id="28887-121">If the Skype Room System client is the presenter, it cannot apply video lock on participants.</span></span>
    
- <span data-ttu-id="28887-122">Skype ルーム システムは、場合でも、Lync Server 2013 の会議ポリシーは、次の理由により、1080 p ビデオの解像度 (受信または発信) を表示できません。</span><span class="sxs-lookup"><span data-stu-id="28887-122">Skype Room System cannot show 1080p video resolution (inbound or outbound), even if the Lync Server 2013 conferencing policy allows it, because of the following:</span></span> 
    
  - <span data-ttu-id="28887-123">Lync Server 2010 では、1080 p の解像度をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="28887-123">Lync Server 2010 doesn't support 1080p resolution.</span></span>
    
  - <span data-ttu-id="28887-124">Skype ルーム システムは、ビデオの解像度の開催者の会議のポリシーが常に制限されます。</span><span class="sxs-lookup"><span data-stu-id="28887-124">Skype Room System is always limited by the organizer's conferencing policy for video resolution.</span></span> <span data-ttu-id="28887-125">したがって、Lync 2010 のプールでは、720 p の解像度をサポートする場合でも Skype ルーム システムできなく主催者のポリシーをサポートしていない限り、720 p の解像度を利用します。</span><span class="sxs-lookup"><span data-stu-id="28887-125">Therefore, even if the Lync 2010 pool supports 720p resolution, Skype Room System will not be able to take advantage of 720p resolution as long as organizer's policy doesn't support it.</span></span> 
    
- <span data-ttu-id="28887-p105">Lync 2013 クライアントは、会議室の LRS プレゼンスを検出し、自動ミュートにより実際の会議室のエコーを回避します。この機能は、Lync Server 2010 でホストされている会議では動作しません。</span><span class="sxs-lookup"><span data-stu-id="28887-p105">Lync 2013 clients detect LRS presence in the meeting room, and they auto-mute themselves to avoid echo in the physical meeting room. This feature does not work in meetings hosted on Lync Server 2010.</span></span>
    
- <span data-ttu-id="28887-128">Lync Server 2010 でホストされている会議では、デスクトップ共有のパフォーマンスに制限が生じます。</span><span class="sxs-lookup"><span data-stu-id="28887-128">There are limitations on desktop sharing performance for meetings hosted on Lync Server 2010.</span></span>
    
- <span data-ttu-id="28887-129">ユーザーはプライベート (制限された) 会議でホストされている Skype ルームのシステムと Lync 2010 に参加することはできません。</span><span class="sxs-lookup"><span data-stu-id="28887-129">Users won't be able to join private (restricted) meetings that are hosted on Lync 2010 with Skype Room System.</span></span>
    

