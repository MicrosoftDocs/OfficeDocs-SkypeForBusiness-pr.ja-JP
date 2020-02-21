---
title: 'Lync Server 2013: 新しいボイスメール機能'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New voice mail feature
ms:assetid: 84d13238-67ef-42cc-801a-2d8147ba3b7f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688117(v=OCS.15)
ms:contentKeyID: 49733715
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f82c1994f49d6284d26e7677ab7f940f88fab9ac
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42216653"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="new-voice-mail-feature-in-lync-server-2013"></a><span data-ttu-id="de0d0-102">Lync Server 2013 の新しいボイスメール機能</span><span class="sxs-lookup"><span data-stu-id="de0d0-102">New voice mail feature in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="de0d0-103">_**トピックの最終更新日:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="de0d0-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="de0d0-104">Lync Server 2013 ボイスメールを管理するための拡張機能であるボイスメールエスケープが導入されています。</span><span class="sxs-lookup"><span data-stu-id="de0d0-104">Lync Server 2013 introduces Voice mail Escape, an enhancement for managing voice mail.</span></span> <span data-ttu-id="de0d0-105">この新しい機能は、呼び出しがボイス メールにルーティングされたことを検出し、ユーザーが呼び出しに応える機会のないまま、呼び出しがすぐにユーザーの携帯電話のボイス メールにルーティングされないようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="de0d0-105">This new feature can detect when a call has been routed to voice mail, and prevent the call from being immediately routed to the user’s mobile phone voice mail without giving the user the opportunity to answer the call.</span></span> <span data-ttu-id="de0d0-106">このようなシナリオは、ユーザーが携帯電話の同時呼び出しを有効にしていて、携帯電話がオフ、電池切れ、または圏外になっていると発生します。</span><span class="sxs-lookup"><span data-stu-id="de0d0-106">This scenario occurs when the user enables simultaneous ringing to their mobile phone, and their mobile phone is turned off, out of battery, or out of range.</span></span> <span data-ttu-id="de0d0-107">ボイス メールのエスケープは、呼び出しがユーザーの携帯電話ボイス メールによってすぐに応答されたことを検出し、携帯電話ボイス メールに対する呼び出しを切断します。</span><span class="sxs-lookup"><span data-stu-id="de0d0-107">Voicemail Escape detects that the call was immediately answered by the user’s mobile phone voice mail, and disconnects the call to the mobile phone voice mail.</span></span> <span data-ttu-id="de0d0-108">呼び出しはユーザーの他のエンドポイントで呼び出しを続けて、ユーザーが呼び出しに応えられるようにします。</span><span class="sxs-lookup"><span data-stu-id="de0d0-108">The call continues to ring on the user’s other endpoints giving the user the opportunity to answer the call.</span></span> <span data-ttu-id="de0d0-109">ユーザーが呼び出しに応えない場合、呼び出しは会社のボイス メールにルーティング されます。</span><span class="sxs-lookup"><span data-stu-id="de0d0-109">If the user does not answer the call, then the call is routed to the corporate voice mail.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="de0d0-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="de0d0-110">See Also</span></span>


[<span data-ttu-id="de0d0-111">Lync Server 2013 でのボイスメールエスケープの構成</span><span class="sxs-lookup"><span data-stu-id="de0d0-111">Configuring voice mail escape in Lync Server 2013</span></span>](lync-server-2013-configuring-voice-mail-escape.md)  


[<span data-ttu-id="de0d0-112">Lync Server 2013 の新しいエンタープライズ Voip 機能</span><span class="sxs-lookup"><span data-stu-id="de0d0-112">New Enterprise Voice features in Lync Server 2013</span></span>](lync-server-2013-new-enterprise-voice-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

