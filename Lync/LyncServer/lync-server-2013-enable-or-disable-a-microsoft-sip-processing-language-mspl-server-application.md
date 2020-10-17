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
ms.openlocfilehash: 98dce0363a031a2d56c7d8a7cc479452f4fb0382
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48528634"
---
# <a name="enable-or-disable-a-microsoft-sip-processing-language-mspl-server-application-in-lync-server-2013"></a><span data-ttu-id="1dccd-102">Lync Server 2013 で Microsoft SIP 処理言語 (MSPL) サーバーアプリケーションを有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="1dccd-102">Enable or disable a Microsoft SIP Processing Language (MSPL) server application in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1dccd-103">_**トピックの最終更新日:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="1dccd-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="1dccd-104">Lync server コントロールパネルを使用して、Lync Server 2013 環境で実行する Microsoft SIP 処理言語 (MSPL) サーバーアプリケーションを有効または無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="1dccd-104">You can use Lync Server Control Panel to enable or disable Microsoft SIP Processing Language (MSPL) server applications that run in your Lync Server 2013 environment.</span></span> <span data-ttu-id="1dccd-105">これらのアプリケーションは、Microsoft Lync 2013 Preview API ではなくスクリプト言語を使用する、スクリプトのみのアプリケーションです。</span><span class="sxs-lookup"><span data-stu-id="1dccd-105">These applications are script-only applications that use a scripting language instead of the Microsoft Lync 2013 Preview API.</span></span>

<span data-ttu-id="1dccd-p102">すべてのスクリプトを有効または無効にできるわけではありません。 たとえば、DefaultRouting スクリプトが有効ですが、このオプションでは DefaultRouting を変更できません。</span><span class="sxs-lookup"><span data-stu-id="1dccd-p102">Not all scripts can be enabled or disabled. For instance, the DefaultRouting script is enabled and this option cannot be changed for DefaultRouting.</span></span>

<div>

## <a name="to-enable-or-disable-an-mspl-server-application"></a><span data-ttu-id="1dccd-108">MSPL サーバー アプリケーションを有効または無効にするには</span><span class="sxs-lookup"><span data-stu-id="1dccd-108">To enable or disable an MSPL server application</span></span>

1.  <span data-ttu-id="1dccd-109">RTCUniversalServerAdmins グループのメンバーである (または同等のユーザー権限を持つ) ユーザー アカウント、または CsServerAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、Lync Server 2013 を展開したネットワーク内の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="1dccd-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="1dccd-110">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="1dccd-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="1dccd-111">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1dccd-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="1dccd-112">左側のナビゲーション バーで [**トポロジ**] をクリックし、[**サーバー アプリケーション**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1dccd-112">In the left navigation bar, click **Topology** and then click **Server Application**.</span></span>

4.  <span data-ttu-id="1dccd-113">[**サーバー アプリケーション**] ページで、必要があれば列見出しをクリックしてアプリケーションを並べ替えてから、変更するサーバー アプリケーションをクリックします。</span><span class="sxs-lookup"><span data-stu-id="1dccd-113">On the **Server Application** page, click a column heading to sort the applications, if needed, and then click the server application that you want to modify.</span></span>

5.  <span data-ttu-id="1dccd-114">[**アクション**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1dccd-114">Click **Action**.</span></span>

6.  <span data-ttu-id="1dccd-115">[**アプリケーションを有効にする**] または [**アプリケーションを無効にする**] をクリックします (スクリプトがこのオプションをサポートする場合に実行できます)。</span><span class="sxs-lookup"><span data-stu-id="1dccd-115">Click **Enable application** or **Disable application** (that is, if the script supports this option).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="1dccd-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="1dccd-116">See Also</span></span>


[<span data-ttu-id="1dccd-117">Lync Server 2013 で、Microsoft SIP 処理言語 (MSPL) アプリケーションを重要または重要ではないとしてマークする</span><span class="sxs-lookup"><span data-stu-id="1dccd-117">Mark a Microsoft SIP Processing Language (MSPL) application as critical or not critical in Lync Server 2013</span></span>](lync-server-2013-mark-a-microsoft-sip-processing-language-mspl-application-as-critical-or-not-critical.md)  


[<span data-ttu-id="1dccd-118">Lync Server 2013 での Microsoft SIP 処理言語 (MSPL) サーバーアプリケーションの表示</span><span class="sxs-lookup"><span data-stu-id="1dccd-118">View Microsoft SIP Processing Language (MSPL) server applications in Lync Server 2013</span></span>](lync-server-2013-view-microsoft-sip-processing-language-mspl-server-applications.md)  


[<span data-ttu-id="1dccd-119">Lync Server 2013 トポロジの管理</span><span class="sxs-lookup"><span data-stu-id="1dccd-119">Managing the Lync Server 2013 topology</span></span>](lync-server-2013-managing-the-lync-server-topology.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

