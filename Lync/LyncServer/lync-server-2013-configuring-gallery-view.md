---
title: 'Lync Server 2013: ギャラリービューの構成'
description: 'Lync Server 2013: ギャラリービューを構成しています。'
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
ms.openlocfilehash: 2aec2f1e3c7bff9a3736f40584a29880978b9daa
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575923"
---
# <a name="configuring-gallery-view-in-lync-server-2013"></a><span data-ttu-id="a62c2-103">Lync Server 2013 でのギャラリービューの構成</span><span class="sxs-lookup"><span data-stu-id="a62c2-103">Configuring Gallery View in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a62c2-104">_**トピックの最終更新日:** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="a62c2-104">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="a62c2-105">Lync Server 2013 では、[会議ポリシー] でギャラリービューのビデオ会議を構成します。</span><span class="sxs-lookup"><span data-stu-id="a62c2-105">In Lync Server 2013, you configure Gallery View video conferencing in conferencing policy.</span></span> <span data-ttu-id="a62c2-106">ギャラリー ビューは既定で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="a62c2-106">Gallery View is turned on by default.</span></span> <span data-ttu-id="a62c2-107">ギャラリー ビューを許可しない場合、または一部のユーザーにのみ許可する場合は、会議ポリシーを使用して機能を無効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a62c2-107">If you do not want to allow Gallery View, or want to allow it for only some users, you need to turn off the feature in conferencing policy.</span></span>

<span data-ttu-id="a62c2-108">会議参加者のビデオが利用できない場合、Lync Server 2013 の新機能である高解像度の写真を展開すると、ユーザーのギャラリービューの機能が強化されます。</span><span class="sxs-lookup"><span data-stu-id="a62c2-108">When a conference participant's video is not available, the users' Gallery View experience can be enhanced if you deploy high-resolution photos, a new feature in Lync Server 2013.</span></span> <span data-ttu-id="a62c2-109">高解像度の写真は、Active Directory ドメインサービスに保存されている、小さくて制限のある解像度の写真に代わる手段として使用できます。</span><span class="sxs-lookup"><span data-stu-id="a62c2-109">High-resolution photos provide an alternative to the smaller, limited resolution contact photos stored in Active Directory Domain Services.</span></span> <span data-ttu-id="a62c2-110">高解像度写真はユーザーの Exchange 2013 メールボックスに格納されるため、Lync Server 2013 と Exchange 2013 を統合する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a62c2-110">High-resolution photos are stored in a user's Exchange 2013 mailbox, and, therefore, require you to integrate Lync Server 2013 with Exchange 2013.</span></span> <span data-ttu-id="a62c2-111">詳細については、NextHop のブログ記事「Exchange 2013 と Lync Server 2013 の統合」を参照してください [https://go.microsoft.com/fwlink/p/?LinkId=260987](https://go.microsoft.com/fwlink/p/?linkid=260987) 。</span><span class="sxs-lookup"><span data-stu-id="a62c2-111">For details, see the NextHop blog article, "Integrating Exchange 2013 and Lync Server 2013," at [https://go.microsoft.com/fwlink/p/?LinkId=260987](https://go.microsoft.com/fwlink/p/?linkid=260987).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a62c2-112">各ブログのコンテンツおよびその URL は予告なしに変更されることがあります。</span><span class="sxs-lookup"><span data-stu-id="a62c2-112">The content of each blog and its URL are subject to change without notice.</span></span>



</div>

<span data-ttu-id="a62c2-113">ギャラリービューのパラメーターを表示または変更するには、Lync Server 2013 コントロールパネルを使用するか、または次のいずれかのコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="a62c2-113">You can view or modify the Gallery View parameters by using Lync Server 2013 Control Panel or by using one of the following cmdlets:</span></span>

  - <span data-ttu-id="a62c2-114">**Get-CsConferencingPolicy**</span><span class="sxs-lookup"><span data-stu-id="a62c2-114">**Get-CsConferencingPolicy**</span></span>

  - <span data-ttu-id="a62c2-115">**Get-csconferencingpolicy**</span><span class="sxs-lookup"><span data-stu-id="a62c2-115">**Set-CsConferencingPolicy**</span></span>

  - <span data-ttu-id="a62c2-116">**Get-csconferencingpolicy**</span><span class="sxs-lookup"><span data-stu-id="a62c2-116">**New-CsConferencingPolicy**</span></span>

<span data-ttu-id="a62c2-117">次の会議ポリシー設定を使用してギャラリー ビューを構成します。</span><span class="sxs-lookup"><span data-stu-id="a62c2-117">Configure Gallery View with the following conferencing policy settings:</span></span>

  - <span data-ttu-id="a62c2-118">**AllowMultiview**    このパラメーターは、ギャラリービューのビデオ会議をユーザーが整理できるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="a62c2-118">**AllowMultiview**   This parameter controls whether a user is allowed to organize Gallery View video conferences.</span></span> <span data-ttu-id="a62c2-119">このパラメーターは、ユーザーによって作成されたケジュール済みの会議および臨時の会議に適用されます。</span><span class="sxs-lookup"><span data-stu-id="a62c2-119">This parameter applies to scheduled and ad-hoc meetings created by the user.</span></span>
    
    <span data-ttu-id="a62c2-120">例:</span><span class="sxs-lookup"><span data-stu-id="a62c2-120">Examples:</span></span>
    
      - <span data-ttu-id="a62c2-121">このパラメーターは、ユーザー A が Lync Server 2013 プールに所属している場合は True に設定されます。</span><span class="sxs-lookup"><span data-stu-id="a62c2-121">This parameter is set to True for User A, who is homed on a Lync Server 2013 pool.</span></span> <span data-ttu-id="a62c2-122">ユーザー A が開催する会議では、ユーザーは会議に参加し複数のビデオ ストリームを受信できます。</span><span class="sxs-lookup"><span data-stu-id="a62c2-122">Meetings organized by User A enable users to join and receive multiple video streams.</span></span>
    
      - <span data-ttu-id="a62c2-123">このパラメーターは、ユーザー B が Lync Server 2013 プールに所属している場合は False に設定されます。</span><span class="sxs-lookup"><span data-stu-id="a62c2-123">This parameter is set to False for User B, who is homed on a Lync Server 2013 pool.</span></span> <span data-ttu-id="a62c2-124">ユーザー B によって開催された会議には、Lync Server 2010 によって提供されるビデオ会議のような単一のビデオストリームがあります。</span><span class="sxs-lookup"><span data-stu-id="a62c2-124">Meetings organized by User B have a single video stream that is similar to the video conference experience provided by Lync Server 2010.</span></span>
    
    <span data-ttu-id="a62c2-p106">このパラメーターにより、複数のビデオ ストリームが許可される会議を開催できるユーザーが決定します。複数のビデオ ストリームが許可される会議の参加者は、個々のアクセス許可に応じて、複数のビデオ ストリームを受信できたりできなかったりします (EnableMultiviewJoin パラメーターの説明を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="a62c2-p106">This parameter determines who can organize meetings that allow multiple video streams. Participants in meetings that allow multiple video streams may or may not be allowed to receive multiple video streams, based on their individual permissions (see the description for the EnableMultiviewJoin parameter).</span></span>

  - <span data-ttu-id="a62c2-127">**EnableMultiviewJoin**    このパラメーターは、会議の参加者が、許可する会議でのギャラリービューのビデオを受信するかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="a62c2-127">**EnableMultiviewJoin**   This parameter controls whether a participant in a meeting receives the Gallery View video experience in meetings that allow it.</span></span> <span data-ttu-id="a62c2-128">このパラメーターは、ユーザーが参加する会議でのユーザー エクスペリエンスを管理します。</span><span class="sxs-lookup"><span data-stu-id="a62c2-128">This parameter controls the user's experience in any meeting in which he or she participates.</span></span>
    
    <span data-ttu-id="a62c2-129">例:</span><span class="sxs-lookup"><span data-stu-id="a62c2-129">Examples:</span></span>
    
      - <span data-ttu-id="a62c2-130">ユーザー c の場合、このパラメーターは True に設定されます。ユーザー c は、開催された会議に参加している場合、またはユーザー B が開始した会議に参加している場合、複数のビデオストリームを受信できます。ユーザー C は、会議に参加した、またはユーザー B が開始したときに、Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="a62c2-130">This parameter is set to True for User C. User C can receive multiple video streams when participating in a meeting organized or started by User A. User C receives a single video stream that is similar to the video conference experience provided by Lync Server 2010 when participating in a meeting organized or started by User B.</span></span>
    
      - <span data-ttu-id="a62c2-131">User d では、このパラメーターは False に設定されています。ユーザー A またはユーザー B が開催した会議に参加するときに、Lync Server 2010 によって提供されるビデオ会議の場合と同様のビデオストリームが1つずつ受信されます。</span><span class="sxs-lookup"><span data-stu-id="a62c2-131">This parameter is set to False for User D. User D receives single video stream that is similar to the video conference experience provided by Lync Server 2010 when participating in any meeting organized by User A or User B.</span></span>

<span data-ttu-id="a62c2-132">次の手順では、Lync Server 管理シェルを使用してギャラリービューのビデオ会議を有効にする例を示します。</span><span class="sxs-lookup"><span data-stu-id="a62c2-132">The following procedure is an example of using Lync Server Management Shell to enable Gallery View video conferencing.</span></span>

<div>

## <a name="to-modify-conferencing-policy-for-gallery-view-video-conferencing"></a><span data-ttu-id="a62c2-133">ギャラリー ビューのビデオ会議用の会議ポリシーを変更するには</span><span class="sxs-lookup"><span data-stu-id="a62c2-133">To modify conferencing policy for Gallery View video conferencing</span></span>

1.  <span data-ttu-id="a62c2-134">Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="a62c2-134">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="a62c2-135">コマンド ラインで次のコマンドレットを実行して、会議ポリシーを編集します。</span><span class="sxs-lookup"><span data-stu-id="a62c2-135">At the command line, run the following cmdlet to edit conferencing policy:</span></span>
    
        Set-CsConferencingPolicy -Identity Pool01ConferencingPolicy -AllowMultiview $true -EnableMultiviewJoin $true 

</div>

</div>

<span> </span>

</div>

</div>

</div>

