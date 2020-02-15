---
title: Lync Server 2010 プールの現在のユーザーを表示する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View current users in Lync Server 2010 pool
ms:assetid: c0986800-8ee4-4d50-9e9c-39f7c4e67bed
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721870(v=OCS.15)
ms:contentKeyID: 49733804
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fadc7b822fe1bdd04c170031407fe0441bfdc2f1
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036185"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-current-users-in-lync-server-2010-pool"></a><span data-ttu-id="a58c1-102">Lync Server 2010 プールの現在のユーザーを表示する</span><span class="sxs-lookup"><span data-stu-id="a58c1-102">View current users in Lync Server 2010 pool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a58c1-103">_**トピックの最終更新日:** 2012-09-26_</span><span class="sxs-lookup"><span data-stu-id="a58c1-103">_**Topic Last Modified:** 2012-09-26_</span></span>

<span data-ttu-id="a58c1-104">プール間でユーザーを移動するさまざまな方法を学習する前に、まず、従来の Lync Server 2010 プールに存在するユーザーを特定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a58c1-104">Prior to learning the various ways you can move users between pools, we must first determine what users exist in the legacy Lync Server 2010 pool.</span></span> <span data-ttu-id="a58c1-105">以下の図では、レジストラープール列は、従来の Lync Server 2010 プールに対して構成されている6人のユーザーを識別します。</span><span class="sxs-lookup"><span data-stu-id="a58c1-105">In the image below, the Registrar pool column identifies six users who are configured for the legacy Lync Server 2010 pool.</span></span> <span data-ttu-id="a58c1-106">これは、Lync Server 2013 プールに移動するテストユーザーです。</span><span class="sxs-lookup"><span data-stu-id="a58c1-106">These are the test users we will move to the Lync Server 2013 pool.</span></span>

<span data-ttu-id="a58c1-107">**Lync Server 2010 プールのユーザーの一覧を表示するには**</span><span class="sxs-lookup"><span data-stu-id="a58c1-107">**To see the list of users in the Lync Server 2010 pool**</span></span>

1.  <span data-ttu-id="a58c1-108">RTCUniversalServerAdmins グループのメンバーであるアカウント、または CsAdministrator または CsUserAdministrator 管理者ロールのメンバーであるアカウントを使用して、Lync Server 2010 フロントエンドサーバーにログオンします。</span><span class="sxs-lookup"><span data-stu-id="a58c1-108">Log on to the Lync Server 2010 Front End Server with an account that is a member of the RTCUniversalServerAdmins group or a member of the CsAdministrator or CsUserAdministrator administrative role.</span></span>

2.  <span data-ttu-id="a58c1-109">[**Lync Server コントロール パネル**] を開きます。</span><span class="sxs-lookup"><span data-stu-id="a58c1-109">Open **Lync Server Control Panel**.</span></span>

3.  <span data-ttu-id="a58c1-110">[**ユーザー**]、[検索]、[**ユーザー検索**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="a58c1-110">Click **Users**, click Search, and then click **Find**.</span></span>

<span data-ttu-id="a58c1-111">**Lync Server 15 コントロール パネル**</span><span class="sxs-lookup"><span data-stu-id="a58c1-111">**The Lync Server 15 Control Panel**</span></span>

<span data-ttu-id="a58c1-112">![Lync Server コントロールパネル、[ユーザーの移動] ダイアログ](images/JJ721870.a2bce284-0392-4db3-9bb2-9f12699738e7(OCS.15).jpg "Lync Server コントロールパネル、[ユーザーの移動] ダイアログ")</span><span class="sxs-lookup"><span data-stu-id="a58c1-112">![Lync Server Control Panel, Move User dialog](images/JJ721870.a2bce284-0392-4db3-9bb2-9f12699738e7(OCS.15).jpg "Lync Server Control Panel, Move User dialog")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

