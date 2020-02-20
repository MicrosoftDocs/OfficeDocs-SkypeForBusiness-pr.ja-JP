---
title: 'Lync Server 2013: ビデオの計画と展開'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning and deploying video
ms:assetid: dadfb7f3-dfd6-4847-b137-17dacafd7368
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205307(v=OCS.15)
ms:contentKeyID: 48185558
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d22ebee3227577edea9f937dddc510424d021dd7
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153007"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-and-deploying-video-in-lync-server-2013"></a><span data-ttu-id="092a4-102">Lync Server 2013 でのビデオの計画と展開</span><span class="sxs-lookup"><span data-stu-id="092a4-102">Planning and deploying video in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="092a4-103">_**トピックの最終更新日:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="092a4-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="092a4-104">Lync Server 2013 には、次の新しいビデオ機能が導入されています。</span><span class="sxs-lookup"><span data-stu-id="092a4-104">Lync Server 2013 introduces the following new video features:</span></span>

  - <span data-ttu-id="092a4-105">**Hd ビデオ**   ユーザーは、2者間の通話とマルチパーティの会議で、最大でフルの高品位 (HD) (1920 x 1080) の解像度を使用できます。</span><span class="sxs-lookup"><span data-stu-id="092a4-105">**HD video**   Users can experience resolutions up to full high definition (HD) (that is, 1920 x 1080) in two-party calls and multiparty conferences.</span></span>

  - <span data-ttu-id="092a4-106">**ギャラリービュー**   ビデオ会議に3人以上のユーザーがいる場合、ユーザーは会議の参加者のビデオを見ることができます。</span><span class="sxs-lookup"><span data-stu-id="092a4-106">**Gallery View**   In video conferences that have more than two people, users can see videos of participants in the conference.</span></span> <span data-ttu-id="092a4-107">会議に5人以上の参加者がいる場合、一番上の参加者のみのビデオが上の行に表示され、他の参加者に対して写真が表示されます。</span><span class="sxs-lookup"><span data-stu-id="092a4-107">If the conference has more than five participants, video of only the most active participants appears in the top row, and a photo appears for the other participants.</span></span>

  - <span data-ttu-id="092a4-108">**(264**   ビデオ) Lync 2013 クライアントのビデオをエンコードするための既定値として、264ビデオコーデックが使用されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="092a4-108">**H.264 video**   The H.264 video codec is now the default for encoding video on Lync 2013 clients.</span></span> <span data-ttu-id="092a4-109">H.264 ビデオは、より広範な解像度とフレーム レートをサポートし、ビデオののスケーラビリティを向上させます。</span><span class="sxs-lookup"><span data-stu-id="092a4-109">H.264 video supports a greater range of resolutions and frame rates, and improves video scalability.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="092a4-110">Lync Server 2013 でも、以前のバージョンの Lync との相互運用性のために VC1 コーデックがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="092a4-110">Lync Server 2013 still supports the VC1 codec for interoperability with previous versions of Lync.</span></span> <span data-ttu-id="092a4-111">新しいビデオコーデックの詳細と背景情報については、「Jeff 氏 Ertz のブログ記事、「Lync 2013 でのビデオ相互<A class=uri href="http://blog.schertz.name/2012/07/video-interoperability-in-lync-2013/">http://blog.schertz.name/2012/07/video-interoperability-in-lync-2013/</A>運用性」、「」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="092a4-111">For details and background information about the new video codec, see Jeff Schertz's Blog article, "Video Interoperability in Lync 2013," at <A class=uri href="http://blog.schertz.name/2012/07/video-interoperability-in-lync-2013/">http://blog.schertz.name/2012/07/video-interoperability-in-lync-2013/</A>.</span></span>

    
    </div>

<span data-ttu-id="092a4-112">このセクションでは、Lync Server 2013 でビデオの帯域幅を管理する方法と、ビデオ機能を構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="092a4-112">This section describes how to manage bandwidth for video in Lync Server 2013 and how to configure video features.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="092a4-113">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="092a4-113">In This Section</span></span>

  - [<span data-ttu-id="092a4-114">Lync Server 2013 でのビデオ帯域幅の構成</span><span class="sxs-lookup"><span data-stu-id="092a4-114">Configuring video bandwidth in Lync Server 2013</span></span>](lync-server-2013-configuring-video-bandwidth.md)

  - [<span data-ttu-id="092a4-115">Lync Server 2013 でのギャラリービューの構成</span><span class="sxs-lookup"><span data-stu-id="092a4-115">Configuring Gallery View in Lync Server 2013</span></span>](lync-server-2013-configuring-gallery-view.md)

  - [<span data-ttu-id="092a4-116">Lync Server 2013 のビデオサンプルシナリオの構成</span><span class="sxs-lookup"><span data-stu-id="092a4-116">Configuring video example scenarios for Lync Server 2013</span></span>](lync-server-2013-configuring-video-example-scenarios.md)

  - [<span data-ttu-id="092a4-117">Lync Server 2013 でのビデオ会議の相互運用性に関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="092a4-117">Interoperability considerations for video conferencing in Lync Server 2013</span></span>](lync-server-2013-interoperability-considerations-for-video-conferencing.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

