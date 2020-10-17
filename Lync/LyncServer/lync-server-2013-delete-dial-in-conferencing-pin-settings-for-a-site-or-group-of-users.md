---
title: サイトまたはユーザーのグループのダイヤルイン会議の PIN 設定を削除する
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
ms.openlocfilehash: c217f86d9f453199ce55571bf2d2b674e7f0ff93
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48525594"
---
# <a name="delete-dial-in-conferencing-pin-settings-for-a-site-or-group-of-users-in-lync-server-2013"></a><span data-ttu-id="634cf-102">Lync Server 2013 で、サイトまたはユーザーのグループのダイヤルイン会議の PIN 設定を削除する</span><span class="sxs-lookup"><span data-stu-id="634cf-102">Delete dial-in conferencing PIN settings for a site or group of users in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="634cf-103">_**トピックの最終更新日:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="634cf-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="634cf-104">ユーザーレベルまたはサイトレベルの PIN ポリシーを削除するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="634cf-104">Follow these steps to delete a user-level or a site-level PIN policy.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="634cf-105">グローバル PIN ポリシーを削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="634cf-105">You cannot delete the global PIN policy.</span></span>



</div>

<div>

## <a name="to-delete-a-user-or-site-pin-policy"></a><span data-ttu-id="634cf-106">ユーザーまたはサイトの PIN ポリシーを削除するには</span><span class="sxs-lookup"><span data-stu-id="634cf-106">To delete a user or site PIN policy</span></span>

1.  <span data-ttu-id="634cf-107">RTCUniversalServerAdmins グループのメンバーである (または同等のユーザー権限を持つ) ユーザー アカウント、または CsServerAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、Lync Server 2013 を展開したネットワーク内の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="634cf-107">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="634cf-108">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="634cf-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="634cf-109">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="634cf-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="634cf-110">左側のナビゲーション バーで [**会議**] をクリックし、[**PIN ポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="634cf-110">In the left navigation bar, click **Conferencing**, and then click **PIN Policy**.</span></span>

4.  <span data-ttu-id="634cf-111">[**PIN ポリシー**] ページの検索フィールドで、削除するポリシーの名前または名前の一部を入力します。</span><span class="sxs-lookup"><span data-stu-id="634cf-111">On the **PIN Policy** page, in the search field, type all or part of the name of the policy you want to delete.</span></span>

5.  <span data-ttu-id="634cf-112">ポリシーのリストで対象のポリシーをクリックし、[**編集**] をクリックして、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="634cf-112">In the list of policies, click the policy that you want, click **Edit**, and then click **Delete**.</span></span>

6.  <span data-ttu-id="634cf-113">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="634cf-113">Click **OK**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

