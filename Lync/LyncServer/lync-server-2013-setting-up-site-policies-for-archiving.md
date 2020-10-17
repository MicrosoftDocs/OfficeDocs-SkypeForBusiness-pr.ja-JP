---
title: 'Lync Server 2013: アーカイブ用のサイトポリシーのセットアップ'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up site policies for Archiving
ms:assetid: dc2ea206-8b9c-44dd-a479-efb217593c89
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205325(v=OCS.15)
ms:contentKeyID: 48185613
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 33e5ac47b0bd8c7668fa929fbc5f712ad8d396af
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48521794"
---
# <a name="setting-up-site-policies-for-archiving-in-lync-server-2013"></a><span data-ttu-id="e84fb-102">Lync Server 2013 でのアーカイブ用のサイトポリシーのセットアップ</span><span class="sxs-lookup"><span data-stu-id="e84fb-102">Setting up site policies for Archiving in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e84fb-103">_**トピックの最終更新日:** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="e84fb-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="e84fb-104">特定のサイトのアーカイブを有効または無効にするには、各サイトのアーカイブポリシーを作成して構成します。</span><span class="sxs-lookup"><span data-stu-id="e84fb-104">You can enable or disable Archiving for specific sites by creating and configuring an Archiving policy for each of those sites.</span></span> <span data-ttu-id="e84fb-105">サイトポリシーはグローバルポリシーより優先されますが、ユーザーポリシーはサイトポリシーより優先されます。</span><span class="sxs-lookup"><span data-stu-id="e84fb-105">A site policy overrides the global policy, but user policies override site policies.</span></span> <span data-ttu-id="e84fb-106">アーカイブポリシーは、Microsoft Exchange 統合を使用していない場合、または Microsoft Exchange 統合を使用しているが、Exchange 2013 を使用しておらず、メールボックスを In-Place 保持に配置するユーザーがいる場合にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="e84fb-106">Archiving policies only apply if you do not use Microsoft Exchange integration or, if you do use Microsoft Exchange integration, but have some users who are not homed on Exchange 2013 and have their mailboxes put on In-Place Hold.</span></span>

<span data-ttu-id="e84fb-107">グローバルポリシー、サイトポリシー、およびユーザーポリシーの階層を含むアーカイブポリシーのしくみの詳細については、「 [Lync Server 2013](lync-server-2013-how-archiving-works.md) の計画に関するドキュメント、展開に関するドキュメント、または操作のドキュメントでのアーカイブの仕組み」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e84fb-107">For details about how Archiving policies work, including the hierarchy for global, site, and user policies, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e84fb-108">展開に対して Microsoft Exchange 統合を有効にした場合は、exchange 2013 に所属しているユーザーに対してアーカイブを有効にし、メールボックスを In-Place ホールドにするかどうかを Exchange In-Place 保持ポリシーで制御します。</span><span class="sxs-lookup"><span data-stu-id="e84fb-108">If you enable Microsoft Exchange integration for your deployment, Exchange In-Place Hold policies control whether archiving is enabled for the users who are homed on Exchange 2013 and have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="e84fb-109">詳細については、「展開」のドキュメントの「 <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Setting up policies For Exchange server integration using The Lync server 2013</A> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e84fb-109">For details, see <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Setting up policies for Archiving in Lync Server 2013 when using Exchange Server integration</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="e84fb-110">アーカイブ ポリシーで内部または外部の通信のアーカイブを有効にする前に、アーカイブ構成のすべてのオプションを適切に指定してください。</span><span class="sxs-lookup"><span data-stu-id="e84fb-110">You should specify all appropriate options in the Archiving configurations before enabling Archiving of internal or external communications in the Archiving policies.</span></span> <span data-ttu-id="e84fb-111">詳細については、「展開」のドキュメントの「 <A href="lync-server-2013-configuring-archiving-options.md">Lync Server 2013 のアーカイブオプションの構成</A> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e84fb-111">For details, see <A href="lync-server-2013-configuring-archiving-options.md">Configuring Archiving options in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="to-create-an-archiving-policy-for-a-site"></a><span data-ttu-id="e84fb-112">サイトのアーカイブポリシーを作成するには</span><span class="sxs-lookup"><span data-stu-id="e84fb-112">To create an archiving policy for a site</span></span>

1.  <span data-ttu-id="e84fb-113">CsArchivingAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="e84fb-113">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="e84fb-114">ブラウザーウィンドウを開き、管理 URL を入力して Lync Server 2013 コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="e84fb-114">Open a browser window, and then enter the Admin URL to open the Lync Server 2013 Control Panel.</span></span>

3.  <span data-ttu-id="e84fb-115">左側のナビゲーション バーで、[**監視とアーカイブ**] をクリックし、[**アーカイブ ポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e84fb-115">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>
    
    <span data-ttu-id="e84fb-116">グローバルポリシー、サイトポリシー、およびユーザーポリシーの階層を含むアーカイブポリシーのしくみの詳細については、「 [Lync Server 2013](lync-server-2013-how-archiving-works.md) の計画に関するドキュメント、展開に関するドキュメント、または操作のドキュメントでのアーカイブの仕組み」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e84fb-116">For details about how Archiving policies work, including the hierarchy for global, site, and user policies, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) Planning documentation, Deployment documentation, or Operations documentation.</span></span>

4.  <span data-ttu-id="e84fb-117">[**新規作成**] をクリックし、[**サイト ポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e84fb-117">Click **New**, and then click **Site policy**.</span></span>

5.  <span data-ttu-id="e84fb-118">[ **サイトの選択**] で、ポリシーを適用するサイトをクリックします。</span><span class="sxs-lookup"><span data-stu-id="e84fb-118">In **Select a site**, click the site to which the policy is to be applied.</span></span>

6.  <span data-ttu-id="e84fb-119">**[新しいアーカイブ ポリシー]** で、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="e84fb-119">In **New Archiving Policy**, do the following:</span></span>
    
      - <span data-ttu-id="e84fb-120">[ **名前**] で、サイトポリシーの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="e84fb-120">In **Name**, specify the name for the site policy.</span></span>
    
      - <span data-ttu-id="e84fb-121">[ **説明**] に、サイトポリシーの内容に関する情報を入力します (例: Redmond のサイトポリシー)。</span><span class="sxs-lookup"><span data-stu-id="e84fb-121">In **Description**, provide information about what the site policy is (for example, site policy for Redmond).</span></span>
    
      - <span data-ttu-id="e84fb-122">指定したサイトの内部通信のアーカイブを制御するには、[ **内部通信をアーカイブ** する] チェックボックスをオンまたはオフにします。</span><span class="sxs-lookup"><span data-stu-id="e84fb-122">To control archiving of internal communications for the specified site, select or clear the **Archive internal communications** check box.</span></span>
    
      - <span data-ttu-id="e84fb-123">指定したサイトの外部通信のアーカイブを制御するには、[ **外部通信をアーカイブ** する] チェックボックスをオンまたはオフにします。</span><span class="sxs-lookup"><span data-stu-id="e84fb-123">To control archiving of external communications for the specified site, select or clear the **Archive external communications** check box.</span></span>

7.  <span data-ttu-id="e84fb-124">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e84fb-124">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

