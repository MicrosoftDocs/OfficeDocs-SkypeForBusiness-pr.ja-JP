---
title: 'Lync Server 2013: 新しい会議機能'
description: 'Lync Server 2013: 新しい会議機能。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New conferencing features
ms:assetid: feeb81e8-1424-408c-a440-886aa0fb133c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413085(v=OCS.15)
ms:contentKeyID: 48185966
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 832d1fdf916c3e97dc7eca7fc1378fe7cfa7c086
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48578993"
---
# <a name="new-conferencing-features-in-lync-server-2013"></a><span data-ttu-id="c37d4-103">Lync Server 2013 の新しい会議機能</span><span class="sxs-lookup"><span data-stu-id="c37d4-103">New conferencing features in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c37d4-104">_**トピックの最終更新日:** 2012-11-08_</span><span class="sxs-lookup"><span data-stu-id="c37d4-104">_**Topic Last Modified:** 2012-11-08_</span></span>

<span data-ttu-id="c37d4-105">Lync Server 2013 には、次の一覧に示すように、会議を強化するいくつかの新機能が導入されています。</span><span class="sxs-lookup"><span data-stu-id="c37d4-105">Lync Server 2013 introduces several new features that enhance conferencing, as described in the following list.</span></span>

  - <span data-ttu-id="c37d4-106">**Join Launcher**</span><span class="sxs-lookup"><span data-stu-id="c37d4-106">**Join Launcher**</span></span>
    
    <span data-ttu-id="c37d4-107">Lync Server 2013 は、クライアントを起動する前に各会議を検証するための参加起動ツールを更新し、次のクライアントで会議を開くためのサポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="c37d4-107">Lync Server 2013 updates the Join launcher to validate each meeting before launching a client, and to provide support for opening a meeting in the following clients:</span></span>
    
      - <span data-ttu-id="c37d4-108">Windows Phone 7</span><span class="sxs-lookup"><span data-stu-id="c37d4-108">Windows Phone 7</span></span>
    
      - <span data-ttu-id="c37d4-109">Android デバイス</span><span class="sxs-lookup"><span data-stu-id="c37d4-109">Android devices</span></span>
    
      - <span data-ttu-id="c37d4-110">Apple iOS デバイス</span><span class="sxs-lookup"><span data-stu-id="c37d4-110">Apple iOS devices</span></span>
    
      - <span data-ttu-id="c37d4-111">Windows 8</span><span class="sxs-lookup"><span data-stu-id="c37d4-111">Windows 8</span></span>
    
      - <span data-ttu-id="c37d4-112">Internet Explorer 10</span><span class="sxs-lookup"><span data-stu-id="c37d4-112">Internet Explorer 10</span></span>

  - <span data-ttu-id="c37d4-113">**更新された PowerPoint 共有**</span><span class="sxs-lookup"><span data-stu-id="c37d4-113">**Updated PowerPoint Sharing**</span></span>
    
    <span data-ttu-id="c37d4-114">Lync Server 2013 は、Office Web Apps および Office Web Apps サーバー (以前の WAC サーバー) を使用して PowerPoint プレゼンテーションを処理するようになりました。</span><span class="sxs-lookup"><span data-stu-id="c37d4-114">Lync Server 2013 now uses Office Web Apps and the Office Web Apps Server (formerly known as WAC Server) to handle PowerPoint presentations.</span></span> <span data-ttu-id="c37d4-115">Office Web Apps サーバーを使用すると、より高解像度の表示が可能になり、PowerPoint の機能のサポートが向上します。より多くの種類のモバイルデバイス (Lync Server 2013 は標準の DHTML と JavaScript を使用して PowerPoint プレゼンテーションをブロードキャストします)、および適切な権限を持つユーザーは、プレゼンテーション自体とは別に PowerPoint プレゼンテーションをスクロールできます</span><span class="sxs-lookup"><span data-stu-id="c37d4-115">The use of Office Web Apps Server allows for higher-resolution displays and better support for PowerPoint capabilities, access to more types of mobile devices (Lync Server 2013 uses standard DHTML and JavaScript to broadcast PowerPoint presentations), and the ability for users with the appropriate privileges to scroll through a PowerPoint presentation independent of the presentation itself.</span></span>

  - <span data-ttu-id="c37d4-116">**ギャラリー ビューおよび HD ビデオ会議**</span><span class="sxs-lookup"><span data-stu-id="c37d4-116">**Gallery View and HD Video Conferencing**</span></span>
    
    <span data-ttu-id="c37d4-117">ビデオ会議では、ユーザーは最大 5 人の会議参加者のビデオを同時に見ることができます。</span><span class="sxs-lookup"><span data-stu-id="c37d4-117">In video conferences, users can see videos of up to five conference participants at the same time.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c37d4-p102">ギャラリー ビューは会議の参加者が最大 75 人の場合に採用されます。しかし、会議の参加者が 75 人を超えるとシングル ビューに戻ります。</span><span class="sxs-lookup"><span data-stu-id="c37d4-p102">Gallery View is experienced in conferences with up to 75 participants. When the conference gets larger than 75 participants, the experience reverts to single view.</span></span>

    
    </div>

  - <span data-ttu-id="c37d4-120">**HD ビデオ**</span><span class="sxs-lookup"><span data-stu-id="c37d4-120">**HD Video**</span></span>
    
    <span data-ttu-id="c37d4-121">2 パーティの通話およびマルチパーティ会議では、ユーザーに最大 HD 1080P の解像度で表示されます。</span><span class="sxs-lookup"><span data-stu-id="c37d4-121">Users can experience resolutions up to HD 1080P in two-party calls and multiparty conferences.</span></span>

  - <span data-ttu-id="c37d4-122">**発表者のみのビデオ モード**</span><span class="sxs-lookup"><span data-stu-id="c37d4-122">**Presenter Only Video Mode**</span></span>
    
    <span data-ttu-id="c37d4-p103">発表者は、発表者からのビデオだけが表示されるように会議を構成できます。このモードでは、複数のビデオ ストリームが使用可能で、異なるソースにロックしている大規模な会議の場合に、注意をそらすものを排除できます。このモードは、会議デバイスによってキャプチャおよび提供されるビデオにも適用されます。</span><span class="sxs-lookup"><span data-stu-id="c37d4-p103">Presenters can configure the conference so that only the video from the presenter is shown. This mode prevents distractions in large conferences when multiple video streams are available and locking to different sources. This mode also applies to video captured and provided by conferencing devices.</span></span>

  - <span data-ttu-id="c37d4-126">**ビデオ スポットライト**</span><span class="sxs-lookup"><span data-stu-id="c37d4-126">**Video Spotlight**</span></span>
    
    <span data-ttu-id="c37d4-p104">発表者は、ビデオ ソースである選択された参加者のビデオだけが会議の全員に表示されるように、会議を構成できます。このモードは、パノラマ ビデオのために会議デバイスによってキャプチャおよび提供されるビデオにも適用されます。</span><span class="sxs-lookup"><span data-stu-id="c37d4-p104">Presenters can configure the conference so that only the video from a selected participant who is a video source is seen by everyone in the conference. This mode also applies to video captured and provided by conferencing devices for panoramic video.</span></span>

  - <span data-ttu-id="c37d4-129">**エンタープライズ VoIP を使用しないユーザーのダイヤルアウト会議**</span><span class="sxs-lookup"><span data-stu-id="c37d4-129">**Dial-out Conferencing for non-Enterprise Voice users**</span></span>
    
    <span data-ttu-id="c37d4-130">Lync Server 2013 は、エンタープライズ Voip が有効になっていない参加者が、会議会議からのダイヤルアウト呼び出しを開始できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="c37d4-130">Lync Server 2013 now allows participants that are not Enterprise Voice enabled to initiate dial-out calls from a meeting conference.</span></span> <span data-ttu-id="c37d4-131">この機能は管理者が構成できます。</span><span class="sxs-lookup"><span data-stu-id="c37d4-131">This feature is configurable by the administrator.</span></span>

  - <span data-ttu-id="c37d4-132">**アーカイブ**</span><span class="sxs-lookup"><span data-stu-id="c37d4-132">**Archiving**</span></span>
    
    <span data-ttu-id="c37d4-133">会議中に共有されているすべてのドキュメントは、Exchange Server の統合がアーカイブで有効になっている場合は、Exchange 2013 のデータストレージにアーカイブされます。</span><span class="sxs-lookup"><span data-stu-id="c37d4-133">Any document that is shared during a conference is archived into Exchange 2013 data storage if Exchange Server integration is enabled with Archiving.</span></span> <span data-ttu-id="c37d4-134">これには、PowerPoint プレゼンテーション、添付ファイル、ホワイトボード、投票が含まれます。</span><span class="sxs-lookup"><span data-stu-id="c37d4-134">This includes PowerPoint presentations, attachments, whiteboards and polls.</span></span>

  - <span data-ttu-id="c37d4-135">**会議の招待のカスタマイズ**</span><span class="sxs-lookup"><span data-stu-id="c37d4-135">**Meeting Invite Customization**</span></span>
    
    <span data-ttu-id="c37d4-136">管理者は、Lync Server コントロールパネルまたは Lync Server 管理シェルを使用して、オンライン会議の電子メールの招待状をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="c37d4-136">Administrators can customize email invitations for online meetings using Lync Server Control Panel or Lync Server Management Shell.</span></span> <span data-ttu-id="c37d4-137">カスタマイズには、ロゴの URL、ヘルプのテキスト、法的テキスト、およびフッターのテキストが含まれます。</span><span class="sxs-lookup"><span data-stu-id="c37d4-137">Customizations can include URLs for logos, help text, legal text, and footer text.</span></span> <span data-ttu-id="c37d4-138">次回以降のすべての招待状にカスタマイズが反映されます。</span><span class="sxs-lookup"><span data-stu-id="c37d4-138">All subsequent invitations will include the customizations.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="c37d4-139">関連項目</span><span class="sxs-lookup"><span data-stu-id="c37d4-139">See Also</span></span>


[<span data-ttu-id="c37d4-140">Lync Server 2013 での会議の計画</span><span class="sxs-lookup"><span data-stu-id="c37d4-140">Planning for conferencing in Lync Server 2013</span></span>](lync-server-2013-planning-for-conferencing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

