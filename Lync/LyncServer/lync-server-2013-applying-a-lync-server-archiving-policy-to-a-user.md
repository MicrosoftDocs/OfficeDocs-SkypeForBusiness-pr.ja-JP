---
title: 'Lync Server 2013: Lync Server アーカイブポリシーのユーザーへの適用'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Applying a Lync Server Archiving policy to a user
ms:assetid: a23e4876-aa8d-4f49-a3bd-3696616e8290
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205143(v=OCS.15)
ms:contentKeyID: 48185024
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d8fa30d5610d3b5e890fb909628ba9d8759ecfeb
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147350"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="applying-a-lync-server-archiving-policy-to-a-user-in-lync-server-2013"></a><span data-ttu-id="3e9ad-102">Lync server 2013 のユーザーへの Lync Server アーカイブポリシーの適用</span><span class="sxs-lookup"><span data-stu-id="3e9ad-102">Applying a Lync Server Archiving policy to a user in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3e9ad-103">_**トピックの最終更新日:** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="3e9ad-103">_**Topic Last Modified:** 2012-10-10_</span></span>

<span data-ttu-id="3e9ad-104">Lync Server ユーザーポリシーを作成した後は、Lync Server 2013 に所属している特定のユーザーまたはユーザーグループに適用してから、有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="3e9ad-104">After creating a Lync Server user policy, you must apply it to specific the users or user groups that are homed on Lync Server 2013 before it can take effect.</span></span> <span data-ttu-id="3e9ad-105">特定のユーザーのユーザーポリシーの作成の詳細については、「展開」のドキュメントの「 [Lync Server 2013 でアーカイブ用のユーザーポリシーを作成および構成](lync-server-2013-creating-and-configuring-user-policies-for-archiving-in-lync-server.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3e9ad-105">For details about creating user policies for specific users, see [Creating and configuring user policies for Archiving in Lync Server 2013](lync-server-2013-creating-and-configuring-user-policies-for-archiving-in-lync-server.md) in the Deployment documentation.</span></span>

<span data-ttu-id="3e9ad-106">グローバルポリシー、サイトポリシー、およびユーザーポリシーの階層を含むアーカイブポリシーのしくみの詳細については、「計画」、「展開」、または「操作」のドキュメントの「 [Lync Server 2013 でのアーカイブの仕組み](lync-server-2013-how-archiving-works.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3e9ad-106">For details about how Archiving policies work, including the hierarchy for global, site, and user policies, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3e9ad-107">アーカイブを構成して使用するためには、まずアーカイブを展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3e9ad-107">In order to configure and use archiving, you must first deploy archiving.</span></span> <span data-ttu-id="3e9ad-108">詳細については、「展開」のドキュメントの「<A href="lync-server-2013-deploying-archiving.md">展開アーカイブ (Lync Server 2013</A> )」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3e9ad-108">For details, see <A href="lync-server-2013-deploying-archiving.md">Deploying Archiving in Lync Server 2013</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="3e9ad-109">展開に対して Microsoft Exchange 統合を有効にした場合、Exchange のインプレース保持ポリシーによって、Exchange 2013 に所属しているユーザーに対してアーカイブを有効にし、そのメールボックスをインプレース保持の対象にするかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="3e9ad-109">If you enabled Microsoft Exchange integration for your deployment, Exchange In-Place Hold policies control whether archiving is enabled for the users who are homed on Exchange 2013 and have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="3e9ad-110">詳細については、「展開」のドキュメントの「 <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Setting up policies For Exchange server integration using The Lync server 2013</A> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3e9ad-110">For details, see <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Setting up policies for Archiving in Lync Server 2013 when using Exchange Server integration</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="3e9ad-111">アーカイブを有効にするには、その前にアーカイブ構成で適切なオプションをすべて指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3e9ad-111">You should specify all appropriate options in the Archiving configurations before enabling Archiving.</span></span> <span data-ttu-id="3e9ad-112">詳細については、「展開」のドキュメントの「 <A href="lync-server-2013-configuring-archiving-options.md">Lync Server 2013 のアーカイブオプションの構成</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3e9ad-112">For details, see <A href="lync-server-2013-configuring-archiving-options.md">Configuring Archiving options in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="to-apply-a-lync-server-archiving-policy-to-a-user"></a><span data-ttu-id="3e9ad-113">Lync Server アーカイブポリシーをユーザーに適用するには</span><span class="sxs-lookup"><span data-stu-id="3e9ad-113">To apply a Lync Server archiving policy to a user</span></span>

1.  <span data-ttu-id="3e9ad-114">CsArchivingAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="3e9ad-114">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="3e9ad-115">ブラウザーウィンドウを開き、管理 URL を入力して Lync Server 2013 コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="3e9ad-115">Open a browser window, and then enter the Admin URL to open the Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="3e9ad-116">Lync Server 2013 コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3e9ad-116">For details about the different methods you can use to start Lync Server 2013 Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="3e9ad-117">左側のナビゲーション バーで [**ユーザー**] をクリックし、構成するユーザー アカウントを検索します。</span><span class="sxs-lookup"><span data-stu-id="3e9ad-117">In the left navigation bar, click **Users**, and then search for the user account that you want to configure.</span></span>

4.  <span data-ttu-id="3e9ad-118">検索結果一覧の表でユーザー アカウントをクリックし、[**編集**] をクリックして、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3e9ad-118">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="3e9ad-119">[ **Lync Server ユーザーの編集**] の [**アーカイブポリシー**] で、適用するアーカイブユーザーポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="3e9ad-119">In **Edit Lync Server user** under **Archiving policy**, select the archiving user policy that you want to apply.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3e9ad-120">[ <STRONG> &lt;自動&gt; </STRONG> ] 設定では、既定のサーバーインストールの設定が適用されます。</span><span class="sxs-lookup"><span data-stu-id="3e9ad-120">The <STRONG>&lt;Automatic&gt;</STRONG> settings apply the default server installation settings.</span></span> <span data-ttu-id="3e9ad-121">これらの設定はサーバーによって自動的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="3e9ad-121">These settings are applied automatically by the server.</span></span>

    
    </div>

6.  <span data-ttu-id="3e9ad-122">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3e9ad-122">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

