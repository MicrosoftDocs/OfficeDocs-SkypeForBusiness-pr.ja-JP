---
title: 'Lync Server 2013: Microsoft SIP 処理言語 (MSPL) サーバーアプリケーションを有効または無効にする'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable or disable a Microsoft SIP Processing Language (MSPL) server application
ms:assetid: b20af38d-224a-4459-991d-0b7eabb3ca7c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182573(v=OCS.15)
ms:contentKeyID: 48185145
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 12fb1160742898b65b14ea17bc10a9c6ed56c780
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736207"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-a-microsoft-sip-processing-language-mspl-server-application-in-lync-server-2013"></a><span data-ttu-id="9c4d3-102">Lync Server 2013 で Microsoft SIP 処理言語 (MSPL) サーバーアプリケーションを有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="9c4d3-102">Enable or disable a Microsoft SIP Processing Language (MSPL) server application in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9c4d3-103">_**最終更新日:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="9c4d3-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="9c4d3-104">Lync Server コントロールパネルを使用して、Lync Server 2013 環境で実行されている Microsoft SIP 処理言語 (MSPL) サーバーアプリケーションを有効または無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="9c4d3-104">You can use Lync Server Control Panel to enable or disable Microsoft SIP Processing Language (MSPL) server applications that run in your Lync Server 2013 environment.</span></span> <span data-ttu-id="9c4d3-105">これらのアプリケーションは、Microsoft Lync 2013 Preview API ではなく、スクリプト言語を使用するスクリプトのみのアプリケーションです。</span><span class="sxs-lookup"><span data-stu-id="9c4d3-105">These applications are script-only applications that use a scripting language instead of the Microsoft Lync 2013 Preview API.</span></span>

<span data-ttu-id="9c4d3-106">すべてのスクリプトを有効または無効にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="9c4d3-106">Not all scripts can be enabled or disabled.</span></span> <span data-ttu-id="9c4d3-107">たとえば、DefaultRouting スクリプトは有効であり、DefaultRouting の場合はこのオプションを変更できません。</span><span class="sxs-lookup"><span data-stu-id="9c4d3-107">For instance, the DefaultRouting script is enabled and this option cannot be changed for DefaultRouting.</span></span>

<div>

## <a name="to-enable-or-disable-an-mspl-server-application"></a><span data-ttu-id="9c4d3-108">MSPL server アプリケーションを有効または無効にするには</span><span class="sxs-lookup"><span data-stu-id="9c4d3-108">To enable or disable an MSPL server application</span></span>

1.  <span data-ttu-id="9c4d3-109">RTCUniversalServerAdmins グループのメンバーであるか (または同等のユーザー権限を持っている)、または CsServerAdministrator または CsAdministrator の役割に割り当てられているユーザーアカウントで、Lync Server 2013 を展開したネットワーク上のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="9c4d3-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="9c4d3-110">ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="9c4d3-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="9c4d3-111">Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="9c4d3-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="9c4d3-112">左側のナビゲーションバーで、[**トポロジ**] をクリックし、[**サーバーアプリケーション**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9c4d3-112">In the left navigation bar, click **Topology** and then click **Server Application**.</span></span>

4.  <span data-ttu-id="9c4d3-113">[**サーバーアプリケーション**] ページで、必要に応じて、アプリケーションを並べ替える列見出しをクリックし、変更するサーバーアプリケーションをクリックします。</span><span class="sxs-lookup"><span data-stu-id="9c4d3-113">On the **Server Application** page, click a column heading to sort the applications, if needed, and then click the server application that you want to modify.</span></span>

5.  <span data-ttu-id="9c4d3-114">[**アクション**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9c4d3-114">Click **Action**.</span></span>

6.  <span data-ttu-id="9c4d3-115">[**アプリケーションの有効化**] または [**アプリケーションの無効化**] をクリックします (スクリプトでこのオプションがサポートされている場合)。</span><span class="sxs-lookup"><span data-stu-id="9c4d3-115">Click **Enable application** or **Disable application** (that is, if the script supports this option).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="9c4d3-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="9c4d3-116">See Also</span></span>


[<span data-ttu-id="9c4d3-117">Lync Server 2013 で Microsoft SIP 処理言語 (MSPL) アプリケーションを critical または critical としてマークする</span><span class="sxs-lookup"><span data-stu-id="9c4d3-117">Mark a Microsoft SIP Processing Language (MSPL) application as critical or not critical in Lync Server 2013</span></span>](lync-server-2013-mark-a-microsoft-sip-processing-language-mspl-application-as-critical-or-not-critical.md)  


[<span data-ttu-id="9c4d3-118">Lync Server 2013 での Microsoft SIP 処理言語  (MSPL) サーバー アプリケーションの表示</span><span class="sxs-lookup"><span data-stu-id="9c4d3-118">View Microsoft SIP Processing Language (MSPL) server applications in Lync Server 2013</span></span>](lync-server-2013-view-microsoft-sip-processing-language-mspl-server-applications.md)  


[<span data-ttu-id="9c4d3-119">Lync Server 2013 トポロジの管理</span><span class="sxs-lookup"><span data-stu-id="9c4d3-119">Managing the Lync Server 2013 topology</span></span>](lync-server-2013-managing-the-lync-server-topology.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

