---
title: 'Lync Server 2013: アーカイブのグローバルポリシーを構成する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring the global policy for Archiving
ms:assetid: 58341d6b-c3ff-4dd9-b1c7-0048f33861ca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204906(v=OCS.15)
ms:contentKeyID: 48184192
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c14cbb69ce620498e1d804483f97c47da37e8522
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734667"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-the-global-policy-for-archiving-in-lync-server-2013"></a><span data-ttu-id="7f00a-102">Lync Server 2013 でアーカイブ用のグローバルポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="7f00a-102">Configuring the global policy for Archiving in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7f00a-103">_**最終更新日:** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="7f00a-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="7f00a-104">フロントエンドサーバーを展開すると、Lync Server によってアーカイブ用のグローバルポリシーが作成されます。</span><span class="sxs-lookup"><span data-stu-id="7f00a-104">When you deploy your Front End Servers, Lync Server creates a global policy for Archiving.</span></span> <span data-ttu-id="7f00a-105">既定では、アーカイブはグローバルポリシーで無効になっています。</span><span class="sxs-lookup"><span data-stu-id="7f00a-105">By default, Archiving is disabled in the global policy.</span></span> <span data-ttu-id="7f00a-106">グローバルポリシーは、サイトまたはユーザーのポリシーをセットアップしてグローバルポリシーを上書きするか、または Microsoft Exchange の統合を使用しているかどうかにかかわらず、展開全体の内部と外部の通信でアーカイブを有効にするかどうかを制御します。ユーザー。</span><span class="sxs-lookup"><span data-stu-id="7f00a-106">The global policy controls whether archiving is enabled for internal and external communications for your entire deployment, unless you set up site or user policies, which override the global policy, or if you use Microsoft Exchange integration for some or all of your users.</span></span> <span data-ttu-id="7f00a-107">Microsoft Exchange 統合を使用している場合、グローバルポリシーは、Exchange 2013 を使用していて、メールボックスがインプレースホールドに配置されているユーザーには適用されません。</span><span class="sxs-lookup"><span data-stu-id="7f00a-107">If you use Microsoft Exchange integration, the global policy does not apply to any users who are homed on Exchange 2013 and have the mailboxes put on In-Place Hold.</span></span>

<span data-ttu-id="7f00a-108">グローバル、サイト、ユーザーのポリシーの階層など、アーカイブポリシーの動作について詳しくは、「 [Lync Server 2013 でのアーカイブのしくみ](lync-server-2013-how-archiving-works.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="7f00a-108">For details about how Archiving policies work, including the hierarchy for global, site, and user policies, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7f00a-109">展開で Microsoft Exchange の統合を有効にした場合、exchange 2013 を使っているユーザーに対してアーカイブが有効になっていて、メールボックスがインプレースホールドに配置されているかどうかを Exchange のインプレースホールドポリシーで制御します。</span><span class="sxs-lookup"><span data-stu-id="7f00a-109">If you enable Microsoft Exchange integration for your deployment, Exchange In-Place Hold policies control whether archiving is enabled for the users who are homed on Exchange 2013 and have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="7f00a-110">詳細については、展開ドキュメントで<A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Exchange Server との統合を使用する場合の「Lync server 2013 でアーカイブするためのポリシーを設定する</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7f00a-110">For details, see <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Setting up policies for Archiving in Lync Server 2013 when using Exchange Server integration</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="7f00a-111">アーカイブを有効にする前に、アーカイブ構成ですべての適切なオプションを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7f00a-111">You should specify all appropriate options in the Archiving configurations before enabling Archiving.</span></span> <span data-ttu-id="7f00a-112">詳細については、展開ドキュメントの「 <A href="lync-server-2013-configuring-archiving-options.md">Lync Server 2013 でアーカイブオプションを構成する</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7f00a-112">For details, see <A href="lync-server-2013-configuring-archiving-options.md">Configuring Archiving options in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="to-configure-the-global-policy-for-archiving-when-using-lync-server-archiving-databases"></a><span data-ttu-id="7f00a-113">Lync Server アーカイブデータベースを使用するときに、アーカイブ用のグローバルポリシーを構成するには</span><span class="sxs-lookup"><span data-stu-id="7f00a-113">To configure the global policy for archiving when using Lync Server Archiving databases</span></span>

1.  <span data-ttu-id="7f00a-114">CsArchivingAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="7f00a-114">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="7f00a-115">ブラウザーウィンドウを開き、管理 URL を入力して Lync Server 2013 コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="7f00a-115">Open a browser window, and then enter the Admin URL to open the Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="7f00a-116">Lync Server 2013 コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="7f00a-116">For details about the different methods you can use to start Lync Server 2013 Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="7f00a-117">左側のナビゲーション バーで、[**監視とアーカイブ**] をクリックし、[**アーカイブ ポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7f00a-117">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>

4.  <span data-ttu-id="7f00a-118">[**アーカイブ ポリシー**] ページで、[**グローバル**]、[**編集**]、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7f00a-118">On the **Archiving Policy** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="7f00a-119">[**アーカイブ ポリシーの編集 - グローバル**] で、以下の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="7f00a-119">In **Edit Archiving Policy - Global**, do the following:</span></span>
    
      - <span data-ttu-id="7f00a-120">"グローバル" という既定の名前を使用しない場合は、[**名前**] にグローバル ポリシーの新しい名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="7f00a-120">In **Name**, if you do not want to use the default name of Global, specify a new name for the global policy.</span></span>
    
      - <span data-ttu-id="7f00a-121">[**説明**] に、そのポリシーの内容に関する情報を入力します (たとえば、「\*\*<部署名> のグローバル ポリシー」など)。</span><span class="sxs-lookup"><span data-stu-id="7f00a-121">In **Description**, provide information about what the policy is (for example, Global policy for *divisionName*).</span></span>
    
      - <span data-ttu-id="7f00a-122">サイト ポリシーまたはユーザー ポリシーによって特に制御されていないすべてのサイトとユーザーの内部通信のアーカイブを制御するには、[**内部通信のアーカイブ**] チェック ボックスをオンまたはオフにします。</span><span class="sxs-lookup"><span data-stu-id="7f00a-122">To control archiving of internal communications for all sites and users not specifically controlled through a site policy or user policy, select or clear the **Archive internal communications** check box.</span></span>
    
      - <span data-ttu-id="7f00a-123">サイト ポリシーまたはユーザー ポリシーによって特に制御されていないすべてのサイトとユーザーの外部通信のアーカイブを制御するには、[**外部通信をアーカイブする**] チェック ボックスをオンまたはオフにします。</span><span class="sxs-lookup"><span data-stu-id="7f00a-123">To control archiving of external communications for all sites and users not specifically controlled through a site policy or user policy, select or clear the **Archive external communications** check box.</span></span>

6.  <span data-ttu-id="7f00a-124">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7f00a-124">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

