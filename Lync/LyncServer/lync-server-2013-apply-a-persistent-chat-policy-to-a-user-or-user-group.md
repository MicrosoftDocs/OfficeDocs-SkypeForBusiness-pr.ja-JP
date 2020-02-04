---
title: 'Lync Server 2013: 常設チャット ポリシーをユーザーまたはユーザー グループに適用する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Apply a Persistent Chat policy to a user or user group
ms:assetid: 809ef4e0-8d42-4feb-b7c0-3995f39867a7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205038(v=OCS.15)
ms:contentKeyID: 48184652
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 726fe9a5fa20a52f770cd5bab475de5731562989
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737627"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="apply-a-persistent-chat-policy-to-a-user-or-user-group-in-lync-server-2013"></a><span data-ttu-id="51e09-102">Lync Server 2013 で常設チャット ポリシーをユーザーまたはユーザー グループに適用する</span><span class="sxs-lookup"><span data-stu-id="51e09-102">Apply a Persistent Chat policy to a user or user group in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="51e09-103">_**最終更新日:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="51e09-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="51e09-104">ユーザーが Lync Server 2013 用に有効になっている場合は、常設チャットサーバーで有効または無効にするために、特定のユーザーに適切なポリシーを適用することができます。</span><span class="sxs-lookup"><span data-stu-id="51e09-104">If a user has been enabled for Lync Server 2013, you can apply appropriate policies to specific users to enable or disable them for Persistent Chat Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="51e09-105">常設チャットサーバーを構成して使用するには、最初にトポロジビルダーを使用して、トポロジに常設チャットサーバーサポートを追加してから、トポロジを発行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="51e09-105">To configure and use Persistent Chat Server, you must first use Topology Builder to add Persistent Chat Server support to the topology, and then publish the topology.</span></span> <span data-ttu-id="51e09-106">詳細については、展開ドキュメントの「 <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Lync server 2013 での展開への常設チャットサーバーの追加</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="51e09-106">For details, see <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Adding Persistent Chat Server to your deployment in Lync Server 2013</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="51e09-107">常設チャットサーバーの構成設定を構成するには、展開ドキュメントの「 <A href="lync-server-2013-configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool.md">Lync server 2013 で常設チャットサーバーのオプションをグローバルまたは常設チャットサーバープールに構成</A>する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="51e09-107">To configure Persistent Chat Server configuration settings, see <A href="lync-server-2013-configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool.md">Configure Persistent Chat Server options globally or for Persistent Chat Server pool in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<span data-ttu-id="51e09-108">このトピックの手順を使用して、以前に作成した常設チャットのユーザーポリシーを1つ以上のユーザーアカウントまたはユーザーグループに適用します。</span><span class="sxs-lookup"><span data-stu-id="51e09-108">Use the procedure in this topic to apply a previously created Persistent Chat user policy to one or more user accounts or user groups.</span></span>

<div>

## <a name="to-apply-a-persistent-chat-user-policy-to-a-user-account"></a><span data-ttu-id="51e09-109">常設チャットのユーザーポリシーをユーザーアカウントに適用するには</span><span class="sxs-lookup"><span data-stu-id="51e09-109">To apply a Persistent Chat user policy to a user account</span></span>

1.  <span data-ttu-id="51e09-110">CsPersistentChatAdministrator、CsAdministrator、または CsUserAdministrator の役割に割り当てられているユーザーから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="51e09-110">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="51e09-111">[**スタート**] メニューから [Lync Server コントロールパネル] を選択するか、ブラウザーウィンドウを開き、管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="51e09-111">From the **Start** menu, select the Lync Server Control Panel or open a browser window, and then enter the Admin URL.</span></span> <span data-ttu-id="51e09-112">Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="51e09-112">For details about the different methods that you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="51e09-113">左側のナビゲーション バーで [**ユーザー**] をクリックし、構成するユーザー アカウントを検索します。</span><span class="sxs-lookup"><span data-stu-id="51e09-113">In the left navigation bar, click **Users**, and then search on the user account that you want to configure.</span></span>

4.  <span data-ttu-id="51e09-114">検索結果一覧の表でユーザー アカウントをクリックし、[**編集**] をクリックして、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="51e09-114">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="51e09-115">[**常設チャットポリシー**] の [ **Lync Server ユーザーの編集**] で、適用する常設チャットのユーザーポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="51e09-115">In **Edit Lync Server User** under **Persistent Chat policy**, select the Persistent Chat user policy that you want to apply.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="51e09-116"><STRONG> &lt;自動&gt; </STRONG>設定では、既定の有効なポリシーが適用されます。</span><span class="sxs-lookup"><span data-stu-id="51e09-116">The <STRONG>&lt;Automatic&gt;</STRONG> settings apply the default effective policy.</span></span> <span data-ttu-id="51e09-117">これらの設定はサーバーにより自動的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="51e09-117">These settings are applied automatically by the server.</span></span>

    
    </div>

6.  <span data-ttu-id="51e09-118">[**コミット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="51e09-118">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

