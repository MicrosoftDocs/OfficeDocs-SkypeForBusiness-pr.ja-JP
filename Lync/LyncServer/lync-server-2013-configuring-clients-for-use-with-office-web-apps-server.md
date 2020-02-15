---
title: 'Lync Server 2013: Office Web Apps サーバーで使用するためのクライアントの構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring clients for use with Office Web Apps Server
ms:assetid: e5eaead7-0b32-42fb-97eb-ca203af59a9d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205339(v=OCS.15)
ms:contentKeyID: 48185668
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9bbe3e71ca23216801582d15438590f99625ae88
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2020
ms.locfileid: "41996602"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-clients-of-lync-server-2013-for-use-with-office-web-apps-server"></a><span data-ttu-id="9c763-102">Office Web Apps サーバーで使用する Lync Server 2013 のクライアントの構成</span><span class="sxs-lookup"><span data-stu-id="9c763-102">Configuring clients of Lync Server 2013 for use with Office Web Apps Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9c763-103">_**トピックの最終更新日:** 2013-02-25_</span><span class="sxs-lookup"><span data-stu-id="9c763-103">_**Topic Last Modified:** 2013-02-25_</span></span>

<span data-ttu-id="9c763-104">ユーザーが Office Web App Server のすべての機能を使用できるようにするには、これらのユーザーを Microsoft Lync 2013 にアップグレードする必要があります。実際の PowerPoint プレゼンテーションに依存しない PowerPoint スライドをスクロールするなどの操作を、Lync 2013 のユーザーのみが行うことができます。</span><span class="sxs-lookup"><span data-stu-id="9c763-104">If you want users to experience the full capabilities of Office Web App Server then you should upgrade those users to Microsoft Lync 2013; only users of Lync 2013 will be able to do such things as scroll through PowerPoint slides independent of the actual PowerPoint presentation.</span></span> <span data-ttu-id="9c763-105">(つまり、これらのユーザーは、実際のプレゼンテーションに影響を与えることなく、いつでもプレゼンテーションの任意のスライドを見ることができます)。Lync 2013 を使用していないユーザーは、引き続きオンライン会議に参加して PowerPoint プレゼンテーションを表示することができます。ただし、これらのユーザーは、スライドを個別にスクロールすることはできません。また、スライドの切り替えを表示したり、埋め込みビデオを表示したりすることもできなくなります。</span><span class="sxs-lookup"><span data-stu-id="9c763-105">(That is, these users can look at any slide in the presentation at any time, without interfering in any way with the actual presentation.) Users who are not using Lync 2013 will still be able to join online conferences and view the PowerPoint presentation; however, they will not be able to independently scroll through the slides, nor will they be able to see slide transitions or view embedded videos.</span></span>

<span data-ttu-id="9c763-106">これらの機能は、Lync 2013 のユーザーがいつでも利用できることに注意してください。これは、PowerPoint 発表者が Microsoft Lync 2010 を実行している場合でも同様です。</span><span class="sxs-lookup"><span data-stu-id="9c763-106">Note that these capabilities will always be available to users of Lync 2013; this is true even if the PowerPoint presenter is running Microsoft Lync 2010.</span></span> <span data-ttu-id="9c763-107">PowerPoint プレゼンテーションが Lync 2010 を実行しているユーザーによってホストされている場合、lync Server 2013 は Office Web Apps サーバーと連携して、Lync 2013 ユーザーがそのプレゼンテーションの Office Web Apps サーバーバージョンを表示できるようにします。</span><span class="sxs-lookup"><span data-stu-id="9c763-107">If a PowerPoint presentation is being hosted by a user running Lync 2010, Lync Server 2013 will coordinate with Office Web Apps Server to make sure that Lync 2013 users will view the Office Web Apps Server version of that presentation.</span></span> <span data-ttu-id="9c763-108">Office Web Apps サーバーでは、Lync 2013 以外のクライアントを実行しているユーザーには PowerPoint services は提供されません。</span><span class="sxs-lookup"><span data-stu-id="9c763-108">Office Web Apps Server does not provide PowerPoint services for users running clients other than Lync 2013.</span></span> <span data-ttu-id="9c763-109">代わりに、これらのユーザーは、Microsoft Lync Server 2010 の場合と同じ方法で、会議サーバーサービスに接続し、PowerPoint プレゼンテーションを表示します。</span><span class="sxs-lookup"><span data-stu-id="9c763-109">Instead, those users connect to the Conferencing server service and view PowerPoint presentations the same way they did in Microsoft Lync Server 2010.</span></span> <span data-ttu-id="9c763-110">これは、これらのユーザーが、Lync Server 2010 で提供される制限のある機能にのみアクセスできることも意味します。</span><span class="sxs-lookup"><span data-stu-id="9c763-110">This also means that these users will only have access to the more-limited capabilities offered by Lync Server 2010.</span></span>

<span data-ttu-id="9c763-111">Office Web Apps サーバーにはクライアント構成は必要ありませんが (ユーザーを Lync 2013 にアップグレードすることはできません)、電話会議の出席者を Internet Explorer 9 にアップグレードすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="9c763-111">Although no client configuration is required for Office Web Apps Server (other than upgrading users to Lync 2013), it is recommended that conference attendees be upgrade to Internet Explorer 9.</span></span> <span data-ttu-id="9c763-112">電話会議には、Internet Explorer 8 を使用してアクセスできますが、その Web ブラウザーを使用するにはいくつかの制限があります。</span><span class="sxs-lookup"><span data-stu-id="9c763-112">Although conferences can be accessed using Internet Explorer 8, there are some limitations to using that Web browser.</span></span> <span data-ttu-id="9c763-113">たとえば、Internet Explorer 8 のユーザーは、PowerPoint のステージをユーザー設定のサイズに変更することはできません。代わりに、3つの定義済みステージサイズのうちの1つを使用するように制限されます。</span><span class="sxs-lookup"><span data-stu-id="9c763-113">For example, users of Internet Explorer 8 will not be able to resize the PowerPoint stage to a custom size; instead, they will be limited to using one of three predefined stage sizes.</span></span> <span data-ttu-id="9c763-114">同様に、Internet Explorer 8 ユーザーがメディアファイルを再生することはできません。</span><span class="sxs-lookup"><span data-stu-id="9c763-114">Likewise, Internet Explorer 8 users will not be able to play media files.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

