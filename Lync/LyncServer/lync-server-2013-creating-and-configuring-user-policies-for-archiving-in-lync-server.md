---
title: Lync Server でアーカイブ用のユーザーポリシーを作成および構成する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Creating and configuring user policies for Archiving in Lync Server
ms:assetid: 5af0e605-3563-4d6f-a3c6-511d204a3165
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204923(v=OCS.15)
ms:contentKeyID: 48184234
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3adccda55d1ae033acf52d64b093e73fe81dad10
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833764"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="creating-and-configuring-user-policies-for-archiving-in-lync-server-2013"></a><span data-ttu-id="58ce4-102">Lync Server 2013 でアーカイブ用のユーザーポリシーを作成および構成する</span><span class="sxs-lookup"><span data-stu-id="58ce4-102">Creating and configuring user policies for Archiving in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="58ce4-103">_**最終更新日:** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="58ce4-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="58ce4-104">Lync Server を使用している特定のユーザーに対してアーカイブを有効または無効にするには、まずユーザーポリシーを作成してから、1つ以上のユーザーまたはユーザーグループにポリシーを適用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="58ce4-104">To enable or disable Archiving for specific users homed on Lync Server, you must first create a user policy and then apply the policy to one or more users or user groups.</span></span> <span data-ttu-id="58ce4-105">特定のユーザーとユーザーグループにユーザーポリシーを適用する方法の詳細については、「展開ドキュメントの[Lync server 2013 でユーザーに Lync server のアーカイブポリシーを適用](lync-server-2013-applying-a-lync-server-archiving-policy-to-a-user.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="58ce4-105">For details about applying user policies to specific users and user groups, see [Applying a Lync Server Archiving policy to a user in Lync Server 2013](lync-server-2013-applying-a-lync-server-archiving-policy-to-a-user.md) in the Deployment documentation.</span></span>

<span data-ttu-id="58ce4-106">グローバル、サイト、ユーザーのポリシーの階層など、アーカイブポリシーの動作について詳しくは、「計画のドキュメントでの[Lync Server 2013 でのアーカイブの動作](lync-server-2013-how-archiving-works.md)」をご覧ください。展開ドキュメント、または運用マニュアルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="58ce4-106">For details about how Archiving policies work, including the hierarchy for global, site, and user policies, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, in the Deployment documentation, or in the Operations documentation.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="58ce4-107">展開に対して Microsoft Exchange の統合を有効にしている場合、Exchange 2013 を使っているユーザーに対してアーカイブが有効になっているかどうか、およびそのメールボックスがインプレースホールドに組み込まれているかどうかを Exchange のインプレースホールドポリシーで制御します。</span><span class="sxs-lookup"><span data-stu-id="58ce4-107">If you enabled Microsoft Exchange integration for your deployment, Exchange In-Place Hold policies control whether archiving is enabled for the users who are homed on Exchange 2013 and have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="58ce4-108">詳細については、展開ドキュメントで<A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Exchange Server との統合を使用する場合の「Lync server 2013 でアーカイブするためのポリシーを設定する</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="58ce4-108">For details, see <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Setting up policies for Archiving in Lync Server 2013 when using Exchange Server integration</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="58ce4-109">アーカイブを有効にする前に、アーカイブ構成ですべての適切なオプションを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="58ce4-109">You should specify all appropriate options in the Archiving configurations before enabling Archiving.</span></span> <span data-ttu-id="58ce4-110">詳細については、展開ドキュメントの「 <A href="lync-server-2013-configuring-archiving-options.md">Lync Server 2013 でアーカイブオプションを構成する</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="58ce4-110">For details, see <A href="lync-server-2013-configuring-archiving-options.md">Configuring Archiving options in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="to-configure-an-archiving-policy-for-users-homed-on-lync-server"></a><span data-ttu-id="58ce4-111">Lync Server を使用しているユーザーのアーカイブポリシーを構成するには</span><span class="sxs-lookup"><span data-stu-id="58ce4-111">To configure an archiving policy for users homed on Lync Server</span></span>

1.  <span data-ttu-id="58ce4-112">CsArchivingAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="58ce4-112">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="58ce4-113">ブラウザーウィンドウを開き、管理 URL を入力して Lync Server 2013 コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="58ce4-113">Open a browser window, and then enter the Admin URL to open the Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="58ce4-114">Lync Server 2013 コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="58ce4-114">For details about the different methods that you can use to start Lync Server 2013 Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="58ce4-115">左側のナビゲーション バーで、[**監視とアーカイブ**] をクリックし、[**アーカイブ ポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="58ce4-115">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>

4.  <span data-ttu-id="58ce4-116">[**新規**] をクリックし、[**ユーザー ポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="58ce4-116">Click **New**, and then click **User policy**.</span></span>

5.  <span data-ttu-id="58ce4-117">[**新しいアーカイブ ポリシー**] で、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="58ce4-117">In **New Archiving Policy**, do the following:</span></span>
    
      - <span data-ttu-id="58ce4-118">[**名前**] にユーザー ポリシーの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="58ce4-118">In **Name**, specify the name for the user policy.</span></span>
    
      - <span data-ttu-id="58ce4-119">[**説明**] に、ユーザー ポリシーの内容に関する情報を入力します (「法務部門のユーザー ポリシー」など)。</span><span class="sxs-lookup"><span data-stu-id="58ce4-119">In **Description**, provide information about what the user policy is (for example, user policy for legal department).</span></span>
    
      - <span data-ttu-id="58ce4-120">ユーザー ポリシーの内部通信のアーカイブを制御するには、[**内部通信をアーカイブする**] チェック ボックスをオンまたはオフにします。</span><span class="sxs-lookup"><span data-stu-id="58ce4-120">To control archiving of internal communications for the user policy, select or clear the **Archive internal communications** check box.</span></span>
    
      - <span data-ttu-id="58ce4-121">ユーザー ポリシーの外部通信のアーカイブを制御するには、[**外部通信をアーカイブする**] チェック ボックスをオンまたはオフにします。</span><span class="sxs-lookup"><span data-stu-id="58ce4-121">To control archiving of external communications for the user policy, select or clear the **Archive external communications** check box.</span></span>

6.  <span data-ttu-id="58ce4-122">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="58ce4-122">Click **Commit**.</span></span>

<span data-ttu-id="58ce4-123">ユーザー ポリシーは、そのポリシーを割り当てたユーザーにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="58ce4-123">A user policy applies only to users to whom you assign the policy.</span></span> <span data-ttu-id="58ce4-124">特定のユーザーへのユーザーポリシーの適用の詳細については、「展開ドキュメントの[Lync server 2013 でユーザーに Lync server のアーカイブポリシーを適用](lync-server-2013-applying-a-lync-server-archiving-policy-to-a-user.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="58ce4-124">For details about applying a user policy to specific users, see [Applying a Lync Server Archiving policy to a user in Lync Server 2013](lync-server-2013-applying-a-lync-server-archiving-policy-to-a-user.md) in the Deployment documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

