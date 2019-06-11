---
title: 'Lync Server 2013: Microsoft SIP 処理言語 (MSPL) アプリケーションを critical または critical としてマークする'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Mark a Microsoft SIP Processing Language (MSPL) application as critical or not critical
ms:assetid: df68fdc6-b7e6-4f07-acdc-0cd4c2c888a1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182598(v=OCS.15)
ms:contentKeyID: 48185622
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 419a162e355434972216f0c47d79850af28cd244
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34827649"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="mark-a-microsoft-sip-processing-language-mspl-application-as-critical-or-not-critical-in-lync-server-2013"></a><span data-ttu-id="43341-102">Lync Server 2013 で Microsoft SIP 処理言語 (MSPL) アプリケーションを critical または critical としてマークする</span><span class="sxs-lookup"><span data-stu-id="43341-102">Mark a Microsoft SIP Processing Language (MSPL) application as critical or not critical in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="43341-103">_**最終更新日:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="43341-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="43341-104">Microsoft SIP 処理言語 (MSPL) サーバーアプリケーションは、Microsoft Lync 2010 API ではなく、MSPL スクリプト言語を使用するスクリプトのみのアプリケーションです。</span><span class="sxs-lookup"><span data-stu-id="43341-104">Microsoft SIP Processing Language (MSPL) server applications are script-only applications that use the MSPL scripting language instead of the Microsoft Lync 2010 API.</span></span> <span data-ttu-id="43341-105">一部の MSPL server アプリケーションは critical として指定されています。</span><span class="sxs-lookup"><span data-stu-id="43341-105">Some MSPL server applications are specified as critical.</span></span> <span data-ttu-id="43341-106">スクリプトが重要な場合は、Lync Server 2013 を起動するために、スクリプトがシステムの起動中に開始される必要があります。</span><span class="sxs-lookup"><span data-stu-id="43341-106">If a script is critical, the script must start during system startup in order for Lync Server 2013 to start.</span></span> <span data-ttu-id="43341-107">Lync Server の実行中にスクリプトが失敗した場合、サーバーはシャットダウンせず、スクリプトへのトラフィック送信が停止し、イベントログにエラーを書き込みます。</span><span class="sxs-lookup"><span data-stu-id="43341-107">If the script fails while Lync Server is running, the server does not shut down, but it stops sending traffic to the script, and it writes errors in the event log.</span></span>

<span data-ttu-id="43341-108">Lync Server コントロールパネルを使用して、Microsoft SIP 処理言語 (MSPL) サーバーアプリケーションをクリティカルとしてマークしたり、マークを解除したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="43341-108">You can use Lync Server Control Panel to mark Microsoft SIP Processing Language (MSPL) server applications as critical or unmark them.</span></span>

<span data-ttu-id="43341-109">すべてのスクリプトでこのオプションがサポートされるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="43341-109">Not all scripts support this option.</span></span> <span data-ttu-id="43341-110">たとえば、DefaultRouting スクリプトは critical とマークされているため、DefaultRouting に対してこのオプションを変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="43341-110">For example, the DefaultRouting script is marked as critical, and this option cannot be changed for DefaultRouting.</span></span>

<div>

## <a name="to-mark-or-unmark-an-mspl-server-application-as-critical"></a><span data-ttu-id="43341-111">MSPL server アプリケーションを重要としてマークまたはマーク解除するには</span><span class="sxs-lookup"><span data-stu-id="43341-111">To mark or unmark an MSPL server application as critical</span></span>

1.  <span data-ttu-id="43341-112">RTCUniversalServerAdmins グループのメンバーであるか (または同等のユーザー権限を持っている)、または CsServerAdministrator または CsAdministrator の役割に割り当てられているユーザーアカウントで、Lync Server 2013 を展開したネットワーク上のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="43341-112">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="43341-113">ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="43341-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="43341-114">Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="43341-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="43341-115">左側のナビゲーションバーで、[**トポロジ**] をクリックし、[**サーバーアプリケーション**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="43341-115">In the left navigation bar, click **Topology** and then click **Server Application**.</span></span>

4.  <span data-ttu-id="43341-116">[**サーバーアプリケーション**] ページで、必要に応じて、アプリケーションを並べ替える列見出しをクリックし、変更するサーバーアプリケーションをクリックします。</span><span class="sxs-lookup"><span data-stu-id="43341-116">On the **Server Application** page, click a column heading to sort the applications, if needed, and then click the server application that you want to modify.</span></span>

5.  <span data-ttu-id="43341-117">[**アクション**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="43341-117">Click **Action**.</span></span>

6.  <span data-ttu-id="43341-118">[**重要としてマーク**] または [重大] (スクリプトがこのオプションをサポートしている場合) を**選択**します。</span><span class="sxs-lookup"><span data-stu-id="43341-118">Click **Mark as critical** or **Unselect as critical** (that is, if the script supports this option).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="43341-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="43341-119">See Also</span></span>


[<span data-ttu-id="43341-120">Lync Server 2013 で Microsoft SIP 処理言語 (MSPL) サーバーアプリケーションを有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="43341-120">Enable or disable a Microsoft SIP Processing Language (MSPL) server application in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-a-microsoft-sip-processing-language-mspl-server-application.md)  


[<span data-ttu-id="43341-121">Lync Server 2013 での Microsoft SIP 処理言語  (MSPL) サーバー アプリケーションの表示</span><span class="sxs-lookup"><span data-stu-id="43341-121">View Microsoft SIP Processing Language (MSPL) server applications in Lync Server 2013</span></span>](lync-server-2013-view-microsoft-sip-processing-language-mspl-server-applications.md)  


[<span data-ttu-id="43341-122">Lync Server 2013 トポロジの管理</span><span class="sxs-lookup"><span data-stu-id="43341-122">Managing the Lync Server 2013 topology</span></span>](lync-server-2013-managing-the-lync-server-topology.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

