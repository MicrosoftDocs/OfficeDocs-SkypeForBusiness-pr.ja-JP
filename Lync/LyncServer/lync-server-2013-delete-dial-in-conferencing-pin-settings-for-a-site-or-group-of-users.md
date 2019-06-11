---
title: サイトまたはユーザーグループのダイヤルイン会議の PIN 設定を削除する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Delete dial-in conferencing PIN settings for a site or group of users
ms:assetid: 15a9faee-d024-4c0e-b2a0-fe7e7dc00589
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520955(v=OCS.15)
ms:contentKeyID: 48183498
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 488970df9e85bdbf8e3f2d8cbe21965eaf3c621c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833608"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-dial-in-conferencing-pin-settings-for-a-site-or-group-of-users-in-lync-server-2013"></a><span data-ttu-id="1689d-102">Lync Server 2013 でサイトまたはユーザーのグループのダイヤルイン会議の PIN 設定を削除する</span><span class="sxs-lookup"><span data-stu-id="1689d-102">Delete dial-in conferencing PIN settings for a site or group of users in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1689d-103">_**最終更新日:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="1689d-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="1689d-104">次の手順に従って、ユーザーレベルまたはサイトレベルの PIN ポリシーを削除します。</span><span class="sxs-lookup"><span data-stu-id="1689d-104">Follow these steps to delete a user-level or a site-level PIN policy.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="1689d-105">グローバル PIN ポリシーを削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="1689d-105">You cannot delete the global PIN policy.</span></span>



</div>

<div>

## <a name="to-delete-a-user-or-site-pin-policy"></a><span data-ttu-id="1689d-106">ユーザーまたはサイトの PIN ポリシーを削除するには</span><span class="sxs-lookup"><span data-stu-id="1689d-106">To delete a user or site PIN policy</span></span>

1.  <span data-ttu-id="1689d-107">RTCUniversalServerAdmins グループのメンバーであるか (または同等のユーザー権限を持っている)、または CsServerAdministrator または CsAdministrator の役割に割り当てられているユーザーアカウントで、Lync Server 2013 を展開したネットワーク上のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="1689d-107">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="1689d-108">ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="1689d-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="1689d-109">Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="1689d-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="1689d-110">左側のナビゲーション バーで [**会議**]、[**PIN ポリシー**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="1689d-110">In the left navigation bar, click **Conferencing**, and then click **PIN Policy**.</span></span>

4.  <span data-ttu-id="1689d-111">[ **PIN のポリシー** ] ページの [検索] フィールドに、削除するポリシーの名前のすべてまたは一部を入力します。</span><span class="sxs-lookup"><span data-stu-id="1689d-111">On the **PIN Policy** page, in the search field, type all or part of the name of the policy you want to delete.</span></span>

5.  <span data-ttu-id="1689d-112">ポリシーのリストで対象のポリシーをクリックし、[**編集**] をクリックして、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1689d-112">In the list of policies, click the policy that you want, click **Edit**, and then click **Delete**.</span></span>

6.  <span data-ttu-id="1689d-113">[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1689d-113">Click **OK**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

