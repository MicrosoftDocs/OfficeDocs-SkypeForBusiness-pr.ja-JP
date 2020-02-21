---
title: 'Lync Server 2013: Microsoft SIP 処理言語 (MSPL) アプリケーションを重要または重要ではないとしてマークする'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Mark a Microsoft SIP Processing Language (MSPL) application as critical or not critical
ms:assetid: df68fdc6-b7e6-4f07-acdc-0cd4c2c888a1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182598(v=OCS.15)
ms:contentKeyID: 48185622
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 31b0b4e532cf79a659dfe2b216815953ab24caf1
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42185350"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="mark-a-microsoft-sip-processing-language-mspl-application-as-critical-or-not-critical-in-lync-server-2013"></a><span data-ttu-id="9ecbc-102">Lync Server 2013 で、Microsoft SIP 処理言語 (MSPL) アプリケーションを重要または重要ではないとしてマークする</span><span class="sxs-lookup"><span data-stu-id="9ecbc-102">Mark a Microsoft SIP Processing Language (MSPL) application as critical or not critical in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9ecbc-103">_**トピックの最終更新日:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="9ecbc-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="9ecbc-104">Microsoft SIP 処理言語 (MSPL) サーバーアプリケーションは、Microsoft Lync 2010 API の代わりに MSPL スクリプト言語を使用するスクリプトのみのアプリケーションです。</span><span class="sxs-lookup"><span data-stu-id="9ecbc-104">Microsoft SIP Processing Language (MSPL) server applications are script-only applications that use the MSPL scripting language instead of the Microsoft Lync 2010 API.</span></span> <span data-ttu-id="9ecbc-105">一部の MSPL サーバーアプリケーションは、重要として指定されています。</span><span class="sxs-lookup"><span data-stu-id="9ecbc-105">Some MSPL server applications are specified as critical.</span></span> <span data-ttu-id="9ecbc-106">スクリプトが重要である場合、Lync Server 2013 を開始するために、スクリプトはシステム起動時に開始する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9ecbc-106">If a script is critical, the script must start during system startup in order for Lync Server 2013 to start.</span></span> <span data-ttu-id="9ecbc-107">Lync Server の実行中にスクリプトが失敗した場合、サーバーはシャットダウンされませんが、スクリプトへのトラフィックの送信が停止し、エラーがイベントログに記録されます。</span><span class="sxs-lookup"><span data-stu-id="9ecbc-107">If the script fails while Lync Server is running, the server does not shut down, but it stops sending traffic to the script, and it writes errors in the event log.</span></span>

<span data-ttu-id="9ecbc-108">Lync Server コントロールパネルを使用して、Microsoft SIP 処理言語 (MSPL) サーバーアプリケーションを重要としてマークしたり、アンマークしたりすることができます。</span><span class="sxs-lookup"><span data-stu-id="9ecbc-108">You can use Lync Server Control Panel to mark Microsoft SIP Processing Language (MSPL) server applications as critical or unmark them.</span></span>

<span data-ttu-id="9ecbc-109">すべてのスクリプトがこのオプションをサポートするわけではありません。</span><span class="sxs-lookup"><span data-stu-id="9ecbc-109">Not all scripts support this option.</span></span> <span data-ttu-id="9ecbc-110">たとえば、DefaultRouting スクリプトは critical としてマークされており、このオプションを DefaultRouting に対して変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="9ecbc-110">For example, the DefaultRouting script is marked as critical, and this option cannot be changed for DefaultRouting.</span></span>

<div>

## <a name="to-mark-or-unmark-an-mspl-server-application-as-critical"></a><span data-ttu-id="9ecbc-111">MSPL サーバーアプリケーションを重要としてマークまたはマークを解除するには</span><span class="sxs-lookup"><span data-stu-id="9ecbc-111">To mark or unmark an MSPL server application as critical</span></span>

1.  <span data-ttu-id="9ecbc-112">RTCUniversalServerAdmins グループのメンバーである (または同等のユーザー権限を持つ) ユーザー アカウント、または CsServerAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、Lync Server 2013 を展開したネットワーク内の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="9ecbc-112">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="9ecbc-113">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="9ecbc-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="9ecbc-114">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9ecbc-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="9ecbc-115">左側のナビゲーション バーで [**トポロジ**] をクリックし、[**サーバー アプリケーション**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9ecbc-115">In the left navigation bar, click **Topology** and then click **Server Application**.</span></span>

4.  <span data-ttu-id="9ecbc-116">[**サーバー アプリケーション**] ページで、必要があれば列見出しをクリックしてアプリケーションを並べ替えてから、変更するサーバー アプリケーションをクリックします。</span><span class="sxs-lookup"><span data-stu-id="9ecbc-116">On the **Server Application** page, click a column heading to sort the applications, if needed, and then click the server application that you want to modify.</span></span>

5.  <span data-ttu-id="9ecbc-117">[**アクション**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9ecbc-117">Click **Action**.</span></span>

6.  <span data-ttu-id="9ecbc-118">[重要とし**てマーク**] をクリックするか、[重大] (スクリプトがこのオプションをサポートしている場合) を**選択**します。</span><span class="sxs-lookup"><span data-stu-id="9ecbc-118">Click **Mark as critical** or **Unselect as critical** (that is, if the script supports this option).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="9ecbc-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="9ecbc-119">See Also</span></span>


[<span data-ttu-id="9ecbc-120">Lync Server 2013 で Microsoft SIP 処理言語 (MSPL) サーバーアプリケーションを有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="9ecbc-120">Enable or disable a Microsoft SIP Processing Language (MSPL) server application in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-a-microsoft-sip-processing-language-mspl-server-application.md)  


[<span data-ttu-id="9ecbc-121">Lync Server 2013 での Microsoft SIP 処理言語 (MSPL) サーバーアプリケーションの表示</span><span class="sxs-lookup"><span data-stu-id="9ecbc-121">View Microsoft SIP Processing Language (MSPL) server applications in Lync Server 2013</span></span>](lync-server-2013-view-microsoft-sip-processing-language-mspl-server-applications.md)  


[<span data-ttu-id="9ecbc-122">Lync Server 2013 トポロジの管理</span><span class="sxs-lookup"><span data-stu-id="9ecbc-122">Managing the Lync Server 2013 topology</span></span>](lync-server-2013-managing-the-lync-server-topology.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

