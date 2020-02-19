---
title: 'Lync Server 2013: ディレクターのテスト'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test the Director
ms:assetid: 9627a7e2-28cc-429c-b79b-7c7a27573bb7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398767(v=OCS.15)
ms:contentKeyID: 48184856
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: da8fbb19ac08886c7603d3b1d60ae3946f7bde32
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141603"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="test-the-director-in-lync-server-2013"></a><span data-ttu-id="e5202-102">Lync Server 2013 でのディレクターのテスト</span><span class="sxs-lookup"><span data-stu-id="e5202-102">Test the Director in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e5202-103">_**トピックの最終更新日:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="e5202-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="e5202-104">この段階ではディレクターまたはディレクタープールが構成されていますが、ドメインネームシステム (DNS) SRV エントリは、プールまたは Standard Edition サーバーを使用してログオンするためにクライアントをポイントします。</span><span class="sxs-lookup"><span data-stu-id="e5202-104">At this stage, you have a Director or Director pool configured, but your Domain Name System (DNS) SRV entries still point clients to log on by using a pool or Standard Edition server.</span></span> <span data-ttu-id="e5202-105">Lync 2013 クライアントがディレクターを使用して自動的にログオンするように DNS レコードを変更する前に、手動でディレクターをポイントしてクライアントをテストします。</span><span class="sxs-lookup"><span data-stu-id="e5202-105">Before changing the DNS record to make Lync 2013 clients log on automatically by using the Director, test a client by manually pointing it to the Director.</span></span>

<div>

## <a name="to-test-the-deployment"></a><span data-ttu-id="e5202-106">展開をテストするには</span><span class="sxs-lookup"><span data-stu-id="e5202-106">To test the deployment</span></span>

1.  <span data-ttu-id="e5202-107">**Csadministrator**グループの一部であるドメインアカウントを使用して、Lync Server コントロールパネルがインストールされているコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="e5202-107">Log on to the computer on which you have the Lync Server Control Panel installed with a domain account that is part of the **CSAdministrator** group.</span></span>

2.  <span data-ttu-id="e5202-108">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="e5202-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="e5202-109">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e5202-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="e5202-110">ナビゲーションウィンドウで、[**トポロジ**] をクリックし、[**状態**] 列に、ディレクターまたはディレクタープール用の矢印 (![緑色の矢印](images/Gg398767.2263cdb7-7e60-457a-a528-a3a082bd051b(OCS.15).jpg "緑の矢印付きのサーバーアイコン")が表示されているサーバーアイコン) が付いた緑色のサーバーがあることを確認します。</span><span class="sxs-lookup"><span data-stu-id="e5202-110">In the navigation pane, click **Topology**, and in the **Status** column confirm that there is a green server with an arrow (that is, ![Server icon with green arrow](images/Gg398767.2263cdb7-7e60-457a-a528-a3a082bd051b(OCS.15).jpg "Server icon with green arrow")) for your Director or Director pool.</span></span>

4.  <span data-ttu-id="e5202-111">Lync Server 2013 クライアントがインストールされている2台のクライアントコンピューターを接続し、Lync Server 2013 で有効になっている別のユーザーアカウントを使用して各コンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="e5202-111">Connect two client computers that have the Lync Server 2013 client installed and log on with a different user account enabled for Lync Server 2013 to each computer.</span></span>

5.  <span data-ttu-id="e5202-112">いずれかのクライアントコンピューターで [**オプション**] メニューをクリックし、[**個人用**設定] グループを選択して、[**詳細**設定]、[**手動構成**] の順にクリックし、[**内部サーバー名または IP アドレス**] に新しいディレクターまたはディレクタープールの完全修飾ドメイン名 (FQDN) を設定します。</span><span class="sxs-lookup"><span data-stu-id="e5202-112">On one of the client computers, click the **Options** menu, select the **Personal** settings group, click **Advanced**, click **Manual Configuration**, and then set the **Internal Server name or IP address** to the fully qualified domain name (FQDN) of the new Director or Director pool.</span></span>

6.  <span data-ttu-id="e5202-113">両方のクライアントにログオンし、ディレクターを使用してログオンしたクライアントが正常にログオンできること、またはその他のユーザーのプレゼンス状態を表示して、インスタントメッセージを交換できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="e5202-113">Log on to both clients and verify that the client logging on by using the Director is able to log on successfully, see the presence status of the other user, and that they can exchange instant messages.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

