---
title: 'Lync Server 2013: 既存のクライアントバージョンポリシールールを削除する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete an existing client version policy rule
ms:assetid: 2fe351c4-d78b-47d5-af49-d47ee5e0fe42
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ923066(v=OCS.15)
ms:contentKeyID: 50675352
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0fce0da6ece0d34c7cf41eac43d472e85c117817
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48501574"
---
# <a name="delete-an-existing-client-version-policy-rule-in-lync-server-2013"></a><span data-ttu-id="e8ee9-102">Lync Server 2013 の既存のクライアントバージョンポリシールールを削除する</span><span class="sxs-lookup"><span data-stu-id="e8ee9-102">Delete an existing client version policy rule in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e8ee9-103">_**トピックの最終更新日:** 2013-01-21_</span><span class="sxs-lookup"><span data-stu-id="e8ee9-103">_**Topic Last Modified:** 2013-01-21_</span></span>

<span data-ttu-id="e8ee9-104">クライアントバージョンポリシーは、一連のクライアントバージョンポリシールールで構成されています。</span><span class="sxs-lookup"><span data-stu-id="e8ee9-104">A client version policy is made up of a set of client version policy rules.</span></span> <span data-ttu-id="e8ee9-105">これらのルールでは、ユーザーが特定のクライアントおよびクライアント バージョンでログオンしようとしたときに実行するアクションが定義されています。</span><span class="sxs-lookup"><span data-stu-id="e8ee9-105">These rules define the actions that should be taken when users attempt to log on with specific clients and client versions.</span></span> <span data-ttu-id="e8ee9-106">Lync Server 2013 コントロールパネルから、クライアントバージョンポリシーから個々のルールを削除することができます。</span><span class="sxs-lookup"><span data-stu-id="e8ee9-106">You can delete individual rules from a client version policy from Lync Server 2013 Control Panel.</span></span>

<div>

## <a name="to-delete-client-version-policy-rules-with-lync-server-control-panel"></a><span data-ttu-id="e8ee9-107">Lync Server コントロールパネルを使用してクライアントバージョンポリシールールを削除するには</span><span class="sxs-lookup"><span data-stu-id="e8ee9-107">To delete client version policy rules with Lync Server Control Panel</span></span>

1.  <span data-ttu-id="e8ee9-108">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="e8ee9-108">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="e8ee9-109">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="e8ee9-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="e8ee9-110">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e8ee9-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="e8ee9-111">左側のナビゲーションバーで [ **クライアント**] をクリックし、[ **クライアントバージョンポリシー** ] ナビゲーションボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="e8ee9-111">In the left navigation bar, click **Clients**, and then click the **Client Version Policy** navigation button.</span></span>

4.  <span data-ttu-id="e8ee9-112">[ **クライアントバージョンポリシー** ] ページで、削除するルールのクライアントバージョンポリシーをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="e8ee9-112">On the **Client Version Policy** page, double-click the client version policy for the rule you want to delete.</span></span>

5.  <span data-ttu-id="e8ee9-113">ルールは [ **クライアントバージョンポリシーの編集** ] ページに表示されます。</span><span class="sxs-lookup"><span data-stu-id="e8ee9-113">The rules appear on the **Edit Client Version Policy** page.</span></span> <span data-ttu-id="e8ee9-114">ルールを削除するには、ルールを選択し、[ **削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e8ee9-114">To delete a rule, select the rule, and then click **Remove**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

