---
title: サイトまたはユーザーのグループのダイヤルイン会議の PIN 設定を削除する
description: サイトまたはユーザーのグループのダイヤルイン会議の PIN 設定を削除します。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete dial-in conferencing PIN settings for a site or group of users
ms:assetid: 15a9faee-d024-4c0e-b2a0-fe7e7dc00589
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520955(v=OCS.15)
ms:contentKeyID: 48183498
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a40168780d5ac5f37ceb33dfaacd25b492d6307a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564253"
---
# <a name="delete-dial-in-conferencing-pin-settings-for-a-site-or-group-of-users-in-lync-server-2013"></a><span data-ttu-id="fe6dc-103">Lync Server 2013 で、サイトまたはユーザーのグループのダイヤルイン会議の PIN 設定を削除する</span><span class="sxs-lookup"><span data-stu-id="fe6dc-103">Delete dial-in conferencing PIN settings for a site or group of users in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fe6dc-104">_**トピックの最終更新日:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="fe6dc-104">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="fe6dc-105">ユーザーレベルまたはサイトレベルの PIN ポリシーを削除するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="fe6dc-105">Follow these steps to delete a user-level or a site-level PIN policy.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="fe6dc-106">グローバル PIN ポリシーを削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="fe6dc-106">You cannot delete the global PIN policy.</span></span>



</div>

<div>

## <a name="to-delete-a-user-or-site-pin-policy"></a><span data-ttu-id="fe6dc-107">ユーザーまたはサイトの PIN ポリシーを削除するには</span><span class="sxs-lookup"><span data-stu-id="fe6dc-107">To delete a user or site PIN policy</span></span>

1.  <span data-ttu-id="fe6dc-108">RTCUniversalServerAdmins グループのメンバーである (または同等のユーザー権限を持つ) ユーザー アカウント、または CsServerAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、Lync Server 2013 を展開したネットワーク内の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="fe6dc-108">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="fe6dc-109">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="fe6dc-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="fe6dc-110">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fe6dc-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="fe6dc-111">左側のナビゲーション バーで [**会議**] をクリックし、[**PIN ポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fe6dc-111">In the left navigation bar, click **Conferencing**, and then click **PIN Policy**.</span></span>

4.  <span data-ttu-id="fe6dc-112">[**PIN ポリシー**] ページの検索フィールドで、削除するポリシーの名前または名前の一部を入力します。</span><span class="sxs-lookup"><span data-stu-id="fe6dc-112">On the **PIN Policy** page, in the search field, type all or part of the name of the policy you want to delete.</span></span>

5.  <span data-ttu-id="fe6dc-113">ポリシーのリストで対象のポリシーをクリックし、[**編集**] をクリックして、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fe6dc-113">In the list of policies, click the policy that you want, click **Edit**, and then click **Delete**.</span></span>

6.  <span data-ttu-id="fe6dc-114">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fe6dc-114">Click **OK**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

