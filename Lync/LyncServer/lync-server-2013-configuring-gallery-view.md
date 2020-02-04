---
title: 'Lync Server 2013: ギャラリービューを構成する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Gallery View
ms:assetid: 4a609178-47d8-4682-ac8d-29f882801924
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204871(v=OCS.15)
ms:contentKeyID: 48184069
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 06054e1728245c87e8bf35419d3890f4e379543a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728847"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-gallery-view-in-lync-server-2013"></a><span data-ttu-id="1ae92-102">Lync Server 2013 でギャラリービューを構成する</span><span class="sxs-lookup"><span data-stu-id="1ae92-102">Configuring Gallery View in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1ae92-103">_**最終更新日:** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="1ae92-103">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="1ae92-104">Lync Server 2013 では、会議ポリシーの [ビデオ会議] を構成します。</span><span class="sxs-lookup"><span data-stu-id="1ae92-104">In Lync Server 2013, you configure Gallery View video conferencing in conferencing policy.</span></span> <span data-ttu-id="1ae92-105">ギャラリービューは既定でオンになっています。</span><span class="sxs-lookup"><span data-stu-id="1ae92-105">Gallery View is turned on by default.</span></span> <span data-ttu-id="1ae92-106">ギャラリービューを許可しない場合、または一部のユーザーのみに許可する場合は、会議ポリシーのこの機能を無効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="1ae92-106">If you do not want to allow Gallery View, or want to allow it for only some users, you need to turn off the feature in conferencing policy.</span></span>

<span data-ttu-id="1ae92-107">会議参加者のビデオが利用できない場合は、Lync Server 2013 の新機能である高解像度の写真を展開すると、ユーザーのギャラリービューエクスペリエンスが向上します。</span><span class="sxs-lookup"><span data-stu-id="1ae92-107">When a conference participant's video is not available, the users' Gallery View experience can be enhanced if you deploy high-resolution photos, a new feature in Lync Server 2013.</span></span> <span data-ttu-id="1ae92-108">高解像度の写真は、Active Directory ドメインサービスに保存されている小型の限定された解像度の連絡先写真の代わりとなるものです。</span><span class="sxs-lookup"><span data-stu-id="1ae92-108">High-resolution photos provide an alternative to the smaller, limited resolution contact photos stored in Active Directory Domain Services.</span></span> <span data-ttu-id="1ae92-109">高解像度の写真はユーザーの Exchange 2013 メールボックスに保存されるため、Lync Server 2013 を Exchange 2013 と統合する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1ae92-109">High-resolution photos are stored in a user's Exchange 2013 mailbox, and, therefore, require you to integrate Lync Server 2013 with Exchange 2013.</span></span> <span data-ttu-id="1ae92-110">詳細については、「NextHop のブログ記事、「Exchange 2013 と Lync Server 2013 の[http://go.microsoft.com/fwlink/p/?LinkId=260987](http://go.microsoft.com/fwlink/p/?linkid=260987)統合」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1ae92-110">For details, see the NextHop blog article, "Integrating Exchange 2013 and Lync Server 2013," at [http://go.microsoft.com/fwlink/p/?LinkId=260987](http://go.microsoft.com/fwlink/p/?linkid=260987).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1ae92-111">各ブログの内容と URL は、将来予告なしに変更されることがあります。</span><span class="sxs-lookup"><span data-stu-id="1ae92-111">The content of each blog and its URL are subject to change without notice.</span></span>



</div>

<span data-ttu-id="1ae92-112">ギャラリーの表示パラメーターを表示または変更するには、Lync Server 2013 コントロールパネルを使用するか、次のいずれかのコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="1ae92-112">You can view or modify the Gallery View parameters by using Lync Server 2013 Control Panel or by using one of the following cmdlets:</span></span>

  - <span data-ttu-id="1ae92-113">**Get-CsConferencingPolicy**</span><span class="sxs-lookup"><span data-stu-id="1ae92-113">**Get-CsConferencingPolicy**</span></span>

  - <span data-ttu-id="1ae92-114">**Set-CsConferencingPolicy**</span><span class="sxs-lookup"><span data-stu-id="1ae92-114">**Set-CsConferencingPolicy**</span></span>

  - <span data-ttu-id="1ae92-115">**New-CsConferencingPolicy**</span><span class="sxs-lookup"><span data-stu-id="1ae92-115">**New-CsConferencingPolicy**</span></span>

<span data-ttu-id="1ae92-116">以下の会議ポリシー設定を使用して、ギャラリービューを構成します。</span><span class="sxs-lookup"><span data-stu-id="1ae92-116">Configure Gallery View with the following conferencing policy settings:</span></span>

  - <span data-ttu-id="1ae92-117">**AllowMultiview**   このパラメーターは、ユーザーがギャラリービューのビデオ会議を整理することを許可されているかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="1ae92-117">**AllowMultiview**   This parameter controls whether a user is allowed to organize Gallery View video conferences.</span></span> <span data-ttu-id="1ae92-118">このパラメーターは、ユーザーが作成したスケジュールされた会議と臨時の会議に適用されます。</span><span class="sxs-lookup"><span data-stu-id="1ae92-118">This parameter applies to scheduled and ad-hoc meetings created by the user.</span></span>
    
    <span data-ttu-id="1ae92-119">たとえば</span><span class="sxs-lookup"><span data-stu-id="1ae92-119">Examples:</span></span>
    
      - <span data-ttu-id="1ae92-120">ユーザー A が Lync Server 2013 プールをホームにしている場合は、このパラメーターを True に設定します。</span><span class="sxs-lookup"><span data-stu-id="1ae92-120">This parameter is set to True for User A, who is homed on a Lync Server 2013 pool.</span></span> <span data-ttu-id="1ae92-121">ユーザーによって開催された会議複数のビデオストリームの参加と受信を可能にします。</span><span class="sxs-lookup"><span data-stu-id="1ae92-121">Meetings organized by User A enable users to join and receive multiple video streams.</span></span>
    
      - <span data-ttu-id="1ae92-122">ユーザー B が Lync Server 2013 プールをホームにしている場合は、このパラメーターを False に設定します。</span><span class="sxs-lookup"><span data-stu-id="1ae92-122">This parameter is set to False for User B, who is homed on a Lync Server 2013 pool.</span></span> <span data-ttu-id="1ae92-123">ユーザー B によって開催された会議には、Lync Server 2010 によって提供されるビデオ会議エクスペリエンスに似た1つのビデオストリームがあります。</span><span class="sxs-lookup"><span data-stu-id="1ae92-123">Meetings organized by User B have a single video stream that is similar to the video conference experience provided by Lync Server 2010.</span></span>
    
    <span data-ttu-id="1ae92-124">このパラメーターは、複数のビデオストリームを許可する会議を開催できるユーザーを指定します。</span><span class="sxs-lookup"><span data-stu-id="1ae92-124">This parameter determines who can organize meetings that allow multiple video streams.</span></span> <span data-ttu-id="1ae92-125">複数のビデオストリームを許可する会議の参加者は、個別のアクセス許可に基づいて複数のビデオストリームを受信することは許可されない場合があります (EnableMultiviewJoin パラメーターの説明を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="1ae92-125">Participants in meetings that allow multiple video streams may or may not be allowed to receive multiple video streams, based on their individual permissions (see the description for the EnableMultiviewJoin parameter).</span></span>

  - <span data-ttu-id="1ae92-126">**EnableMultiviewJoin**   このパラメーターは、会議の参加者が、会議で許可されているギャラリーの表示ビデオエクスペリエンスを受け取るかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="1ae92-126">**EnableMultiviewJoin**   This parameter controls whether a participant in a meeting receives the Gallery View video experience in meetings that allow it.</span></span> <span data-ttu-id="1ae92-127">このパラメーターは、ユーザーが参加している会議でのユーザーエクスペリエンスを制御します。</span><span class="sxs-lookup"><span data-stu-id="1ae92-127">This parameter controls the user's experience in any meeting in which he or she participates.</span></span>
    
    <span data-ttu-id="1ae92-128">たとえば</span><span class="sxs-lookup"><span data-stu-id="1ae92-128">Examples:</span></span>
    
      - <span data-ttu-id="1ae92-129">ユーザー c の場合、このパラメーターは True に設定されます。ユーザー A は、会議に参加している場合、またはユーザー A が開始した場合に、複数のビデオストリームを受け取ることができます。ユーザー C は、Lync Server 2010 によって提供されるビデオ会議と同様のビデオストリームを1つ受信します。ユーザー B によって開催または開始された会議への参加。</span><span class="sxs-lookup"><span data-stu-id="1ae92-129">This parameter is set to True for User C. User C can receive multiple video streams when participating in a meeting organized or started by User A. User C receives a single video stream that is similar to the video conference experience provided by Lync Server 2010 when participating in a meeting organized or started by User B.</span></span>
    
      - <span data-ttu-id="1ae92-130">ユーザー D の場合、このパラメーターは False に設定されます。ユーザー D は、ユーザー A またはユーザー B によって開催された会議に参加しているときに、Lync Server 2010 によって提供されるビデオ会議エクスペリエンスと同様の単一のビデオストリームを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="1ae92-130">This parameter is set to False for User D. User D receives single video stream that is similar to the video conference experience provided by Lync Server 2010 when participating in any meeting organized by User A or User B.</span></span>

<span data-ttu-id="1ae92-131">次の手順では、Lync Server 管理シェルを使って、ギャラリービューのビデオ会議を有効にする例を示します。</span><span class="sxs-lookup"><span data-stu-id="1ae92-131">The following procedure is an example of using Lync Server Management Shell to enable Gallery View video conferencing.</span></span>

<div>

## <a name="to-modify-conferencing-policy-for-gallery-view-video-conferencing"></a><span data-ttu-id="1ae92-132">ギャラリービューのビデオ会議用の会議ポリシーを変更するには</span><span class="sxs-lookup"><span data-stu-id="1ae92-132">To modify conferencing policy for Gallery View video conferencing</span></span>

1.  <span data-ttu-id="1ae92-133">Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="1ae92-133">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="1ae92-134">コマンドラインで、次のコマンドレットを実行して会議ポリシーを編集します。</span><span class="sxs-lookup"><span data-stu-id="1ae92-134">At the command line, run the following cmdlet to edit conferencing policy:</span></span>
    
        Set-CsConferencingPolicy -Identity Pool01ConferencingPolicy -AllowMultiview $true -EnableMultiviewJoin $true 

</div>

</div>

<span> </span>

</div>

</div>

</div>

