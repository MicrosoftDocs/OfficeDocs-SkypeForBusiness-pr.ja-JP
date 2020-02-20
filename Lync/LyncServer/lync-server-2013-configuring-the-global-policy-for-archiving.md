---
title: 'Lync Server 2013: アーカイブ用のグローバルポリシーの構成'
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
ms.openlocfilehash: c31176581b1c34556a75b7fe039a06862249d397
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154279"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-the-global-policy-for-archiving-in-lync-server-2013"></a><span data-ttu-id="0cedc-102">Lync Server 2013 でのアーカイブ用のグローバルポリシーの構成</span><span class="sxs-lookup"><span data-stu-id="0cedc-102">Configuring the global policy for Archiving in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0cedc-103">_**トピックの最終更新日:** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="0cedc-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="0cedc-104">フロントエンドサーバーを展開すると、Lync Server によってアーカイブ用のグローバルポリシーが作成されます。</span><span class="sxs-lookup"><span data-stu-id="0cedc-104">When you deploy your Front End Servers, Lync Server creates a global policy for Archiving.</span></span> <span data-ttu-id="0cedc-105">既定では、グローバルポリシーでアーカイブは無効になっています。</span><span class="sxs-lookup"><span data-stu-id="0cedc-105">By default, Archiving is disabled in the global policy.</span></span> <span data-ttu-id="0cedc-106">グローバルポリシーでは、サイトポリシーまたはユーザーポリシーを設定してグローバルポリシーを上書きするか、または Microsoft Exchange 統合を使用して一部またはすべてのを展開する場合を除いて、展開全体の内部通信と外部通信のアーカイブを有効にするかどうかを制御します。ユーザー。</span><span class="sxs-lookup"><span data-stu-id="0cedc-106">The global policy controls whether archiving is enabled for internal and external communications for your entire deployment, unless you set up site or user policies, which override the global policy, or if you use Microsoft Exchange integration for some or all of your users.</span></span> <span data-ttu-id="0cedc-107">Microsoft Exchange 統合を使用する場合、グローバルポリシーは、Exchange 2013 に所属していて、メールボックスがインプレース保持に配置されているすべてのユーザーには適用されません。</span><span class="sxs-lookup"><span data-stu-id="0cedc-107">If you use Microsoft Exchange integration, the global policy does not apply to any users who are homed on Exchange 2013 and have the mailboxes put on In-Place Hold.</span></span>

<span data-ttu-id="0cedc-108">グローバルポリシー、サイトポリシー、およびユーザーポリシーの階層を含むアーカイブポリシーのしくみの詳細については、「 [Lync Server 2013](lync-server-2013-how-archiving-works.md)の計画に関するドキュメント、展開に関するドキュメント、または操作のドキュメントでのアーカイブの仕組み」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0cedc-108">For details about how Archiving policies work, including the hierarchy for global, site, and user policies, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0cedc-109">展開に対して Microsoft Exchange 統合を有効にすると、exchange 2013 に所属しているユーザーに対してアーカイブを有効にし、メールボックスをインプレース保持に設定するかどうかを Exchange のインプレース保持ポリシーで制御します。</span><span class="sxs-lookup"><span data-stu-id="0cedc-109">If you enable Microsoft Exchange integration for your deployment, Exchange In-Place Hold policies control whether archiving is enabled for the users who are homed on Exchange 2013 and have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="0cedc-110">詳細については、「展開」のドキュメントの「 <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Setting up policies For Exchange server integration using The Lync server 2013</A> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0cedc-110">For details, see <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Setting up policies for Archiving in Lync Server 2013 when using Exchange Server integration</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="0cedc-111">アーカイブを有効にするには、その前にアーカイブ構成で適切なオプションをすべて指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0cedc-111">You should specify all appropriate options in the Archiving configurations before enabling Archiving.</span></span> <span data-ttu-id="0cedc-112">詳細については、「展開」のドキュメントの「 <A href="lync-server-2013-configuring-archiving-options.md">Lync Server 2013 のアーカイブオプションの構成</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0cedc-112">For details, see <A href="lync-server-2013-configuring-archiving-options.md">Configuring Archiving options in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="to-configure-the-global-policy-for-archiving-when-using-lync-server-archiving-databases"></a><span data-ttu-id="0cedc-113">Lync Server アーカイブ データベースを使用するときにアーカイブのグローバル ポリシーを構成するには</span><span class="sxs-lookup"><span data-stu-id="0cedc-113">To configure the global policy for archiving when using Lync Server Archiving databases</span></span>

1.  <span data-ttu-id="0cedc-114">CsArchivingAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="0cedc-114">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="0cedc-115">ブラウザーウィンドウを開き、管理 URL を入力して Lync Server 2013 コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="0cedc-115">Open a browser window, and then enter the Admin URL to open the Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="0cedc-116">Lync Server 2013 コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0cedc-116">For details about the different methods you can use to start Lync Server 2013 Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="0cedc-117">左側のナビゲーション バーで、[**監視とアーカイブ**] をクリックし、[**アーカイブ ポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0cedc-117">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>

4.  <span data-ttu-id="0cedc-118">[**アーカイブ ポリシー**] ページで、[**グローバル**]、[**編集**]、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0cedc-118">On the **Archiving Policy** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="0cedc-119">[**アーカイブ ポリシーの編集 - グローバル**] で、以下の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="0cedc-119">In **Edit Archiving Policy - Global**, do the following:</span></span>
    
      - <span data-ttu-id="0cedc-120">"グローバル" という既定の名前を使用しない場合は、[**名前**] にグローバル ポリシーの新しい名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="0cedc-120">In **Name**, if you do not want to use the default name of Global, specify a new name for the global policy.</span></span>
    
      - <span data-ttu-id="0cedc-121">[**説明**] に、そのポリシーの内容に関する情報を入力します (たとえば、「\*\*<部署名> のグローバル ポリシー」など)。</span><span class="sxs-lookup"><span data-stu-id="0cedc-121">In **Description**, provide information about what the policy is (for example, Global policy for *divisionName*).</span></span>
    
      - <span data-ttu-id="0cedc-122">サイト ポリシーまたはユーザー ポリシーによって特に制御されていないすべてのサイトとユーザーの内部通信のアーカイブを制御するには、[**内部通信のアーカイブ**] チェック ボックスをオンまたはオフにします。</span><span class="sxs-lookup"><span data-stu-id="0cedc-122">To control archiving of internal communications for all sites and users not specifically controlled through a site policy or user policy, select or clear the **Archive internal communications** check box.</span></span>
    
      - <span data-ttu-id="0cedc-123">サイト ポリシーまたはユーザー ポリシーによって特に制御されていないすべてのサイトとユーザーの外部通信のアーカイブを制御するには、[**外部通信をアーカイブする**] チェック ボックスをオンまたはオフにします。</span><span class="sxs-lookup"><span data-stu-id="0cedc-123">To control archiving of external communications for all sites and users not specifically controlled through a site policy or user policy, select or clear the **Archive external communications** check box.</span></span>

6.  <span data-ttu-id="0cedc-124">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0cedc-124">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

