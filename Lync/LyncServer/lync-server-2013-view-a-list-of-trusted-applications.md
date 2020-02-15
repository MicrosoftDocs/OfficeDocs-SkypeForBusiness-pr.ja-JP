---
title: 'Lync Server 2013: 信頼されたアプリケーションの一覧を表示する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View a list of trusted applications
ms:assetid: f09300b3-67cf-4e70-a51a-23d62479b913
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182604(v=OCS.15)
ms:contentKeyID: 48185844
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 16f1e202c1d7e60202b76d42f0104f372213597f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007216"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-a-list-of-trusted-applications-in-lync-server-2013"></a><span data-ttu-id="1ce85-102">Lync Server 2013 で信頼されたアプリケーションの一覧を表示する</span><span class="sxs-lookup"><span data-stu-id="1ce85-102">View a list of trusted applications in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1ce85-103">_**トピックの最終更新日:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="1ce85-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="1ce85-104">Lync server 2013 コントロールパネルを使用して、Lync Server 2013 環境に展開した信頼されたアプリケーションの一覧を表示できます。</span><span class="sxs-lookup"><span data-stu-id="1ce85-104">You can use Lync Server 2013 Control Panel to view a list of the trusted applications that you have deployed in your Lync Server 2013 environment.</span></span> <span data-ttu-id="1ce85-105">信頼されたアプリケーションは、Lync Server 2013 によって信頼されている Microsoft 統合コミュニケーション Managed API (UCMA) 3.0 コア SDK に基づくアプリケーションです。</span><span class="sxs-lookup"><span data-stu-id="1ce85-105">A trusted application is an application based on Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK that is trusted by Lync Server 2013.</span></span> <span data-ttu-id="1ce85-106">この信頼関係は、次の一覧に要約されています。</span><span class="sxs-lookup"><span data-stu-id="1ce85-106">This trust relationship is summarized in the following list:</span></span>

  - <span data-ttu-id="1ce85-107">信頼されたアプリケーションは、Lync Server による認証にチャレンジされません。</span><span class="sxs-lookup"><span data-stu-id="1ce85-107">Trusted applications are not challenged for authentication by Lync Server.</span></span>

  - <span data-ttu-id="1ce85-108">信頼されたアプリケーションは、SIP トランザクション、接続、または発信ボイスオーバー Ip (VoIP) 呼び出しで Lync Server によって調整されることはありません。</span><span class="sxs-lookup"><span data-stu-id="1ce85-108">Trusted applications are not throttled by Lync Server for SIP transactions, connections or outgoing Voice over Internet Protocol (VoIP) calls.</span></span>

  - <span data-ttu-id="1ce85-109">信頼されたアプリケーションは、すべてのユーザーを偽装し、名簿に表示されることなく会議に参加できます。</span><span class="sxs-lookup"><span data-stu-id="1ce85-109">Trusted applications can impersonate any user and can join conferences without appearing in rosters.</span></span>

  - <span data-ttu-id="1ce85-110">信頼されたアプリケーションは、高い可用性と復元性を備えています。</span><span class="sxs-lookup"><span data-stu-id="1ce85-110">Trusted applications are highly available and resilient.</span></span>

<span data-ttu-id="1ce85-111">Lync Server コントロールパネルには、アプリケーションの名前、実行されているプール、および使用しているポートが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1ce85-111">In Lync Server Control Panel, you can see the name of the applications, the pool where they run, and the port they use.</span></span>

<div>

## <a name="to-view-a-list-of-trusted-applications"></a><span data-ttu-id="1ce85-112">信頼されたアプリケーションの一覧を表示するには</span><span class="sxs-lookup"><span data-stu-id="1ce85-112">To view a list of trusted applications</span></span>

1.  <span data-ttu-id="1ce85-113">CsServerAdministrator、CsAdministrator、CsHelpDesk、または CsViewOnlyAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="1ce85-113">From a user account that is assigned to the CsServerAdministrator, CsAdministrator, CsHelpDesk, or CsViewOnlyAdministrator role, log on to any computer in your internal deployment.</span></span> <span data-ttu-id="1ce85-114">Lync Server 2013 で使用できる定義済みの管理者の役割の詳細については、「 [Lync server 2013 で役割ベースのアクセス制御を計画する](lync-server-2013-planning-for-role-based-access-control.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1ce85-114">For details about the predefined administrative roles available in Lync Server 2013, see [Planning for role-based access control in Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md).</span></span>

2.  <span data-ttu-id="1ce85-115">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="1ce85-115">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="1ce85-116">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1ce85-116">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="1ce85-117">左側のナビゲーションバーで、[**トポロジ**] をクリックし、[**信頼さ**れたアプリケーション] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1ce85-117">In the left navigation bar, click **Topology** and the click **Trusted Application**.</span></span>

4.  <span data-ttu-id="1ce85-118">[**信頼さ**れたアプリケーション] ページで、必要に応じて列の見出しをクリックしてアプリケーションを並べ替えます。</span><span class="sxs-lookup"><span data-stu-id="1ce85-118">On the **Trusted Application** page, click a column heading to sort the applications, if needed.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="1ce85-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="1ce85-119">See Also</span></span>


[<span data-ttu-id="1ce85-120">Lync Server 2013 トポロジの管理</span><span class="sxs-lookup"><span data-stu-id="1ce85-120">Managing the Lync Server 2013 topology</span></span>](lync-server-2013-managing-the-lync-server-topology.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

