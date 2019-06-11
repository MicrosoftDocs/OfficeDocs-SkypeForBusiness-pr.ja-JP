---
title: 'Lync Server 2013: 既存のクライアントバージョンポリシールールを削除する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Delete an existing client version policy rule
ms:assetid: 2fe351c4-d78b-47d5-af49-d47ee5e0fe42
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ923066(v=OCS.15)
ms:contentKeyID: 50675352
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: daad18b29a9c6b124093c1770da0db9c19757b2b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833623"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-an-existing-client-version-policy-rule-in-lync-server-2013"></a><span data-ttu-id="4644d-102">Lync Server 2013 で既存のクライアントのバージョンポリシールールを削除する</span><span class="sxs-lookup"><span data-stu-id="4644d-102">Delete an existing client version policy rule in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4644d-103">_**最終更新日:** 2013-01-21_</span><span class="sxs-lookup"><span data-stu-id="4644d-103">_**Topic Last Modified:** 2013-01-21_</span></span>

<span data-ttu-id="4644d-104">クライアントのバージョンポリシーは、一連のクライアントバージョンポリシールールで構成されています。</span><span class="sxs-lookup"><span data-stu-id="4644d-104">A client version policy is made up of a set of client version policy rules.</span></span> <span data-ttu-id="4644d-105">これらのルールでは、ユーザーが特定のクライアントおよびクライアント バージョンでログオンしようとしたときに実行するアクションが定義されています。</span><span class="sxs-lookup"><span data-stu-id="4644d-105">These rules define the actions that should be taken when users attempt to log on with specific clients and client versions.</span></span> <span data-ttu-id="4644d-106">Lync Server 2013 コントロールパネルからクライアントのバージョンポリシーから個々のルールを削除することができます。</span><span class="sxs-lookup"><span data-stu-id="4644d-106">You can delete individual rules from a client version policy from Lync Server 2013 Control Panel.</span></span>

<div>

## <a name="to-delete-client-version-policy-rules-with-lync-server-control-panel"></a><span data-ttu-id="4644d-107">Lync Server コントロールパネルでクライアントのバージョンポリシールールを削除するには</span><span class="sxs-lookup"><span data-stu-id="4644d-107">To delete client version policy rules with Lync Server Control Panel</span></span>

1.  <span data-ttu-id="4644d-108">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="4644d-108">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="4644d-109">ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="4644d-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="4644d-110">Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="4644d-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="4644d-111">左側のナビゲーションバーで、[**クライアント**] をクリックし、[**クライアントバージョンポリシー** ] ナビゲーションボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="4644d-111">In the left navigation bar, click **Clients**, and then click the **Client Version Policy** navigation button.</span></span>

4.  <span data-ttu-id="4644d-112">[**クライアントのバージョンポリシー** ] ページで、削除するルールのクライアントのバージョンポリシーをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="4644d-112">On the **Client Version Policy** page, double-click the client version policy for the rule you want to delete.</span></span>

5.  <span data-ttu-id="4644d-113">[**クライアントのバージョンポリシーの編集**] ページにルールが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4644d-113">The rules appear on the **Edit Client Version Policy** page.</span></span> <span data-ttu-id="4644d-114">ルールを削除するには、ルールを選択し、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4644d-114">To delete a rule, select the rule, and then click **Remove**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

