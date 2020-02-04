---
title: パイロット プールとレガシ プールの共存の確認
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Verify pilot pool coexistence with legacy pool
ms:assetid: 597d0fa6-ca04-4521-b1c2-72d7f35ecd08
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204914(v=OCS.15)
ms:contentKeyID: 48184209
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7585970a53ffd94959653555dad8a02724ba2f03
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730887"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-pilot-pool-coexistence-with-legacy-pool"></a><span data-ttu-id="89c98-102">パイロット プールとレガシ プールの共存の確認</span><span class="sxs-lookup"><span data-stu-id="89c98-102">Verify pilot pool coexistence with legacy pool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="89c98-103">_**最終更新日:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="89c98-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<div>

## <a name="verify-the-pool-in-office-communications-server-2007-r2-administrative-tool"></a><span data-ttu-id="89c98-104">Office Communications Server 2007 R2 管理ツールでプールを確認する</span><span class="sxs-lookup"><span data-stu-id="89c98-104">Verify the Pool in Office Communications Server 2007 R2 Administrative Tool</span></span>

1.  <span data-ttu-id="89c98-105">Office Communications Server 2007 R2 管理ツールを開きます。</span><span class="sxs-lookup"><span data-stu-id="89c98-105">Open the Office Communications Server 2007 R2 administrative tool.</span></span>

2.  <span data-ttu-id="89c98-106">[**フォレスト**] ノードを展開し、 **Standard Edition サーバー**または [**エンタープライズプール**] ノードを展開して、プールまたはサーバー名を展開します。</span><span class="sxs-lookup"><span data-stu-id="89c98-106">Expand the **Forest** node, expand the **Standard Edition Servers** or **Enterprise pools** node, and then expand the pool or server name.</span></span>

3.  <span data-ttu-id="89c98-107">Office Communications Server 2007 R2 サービスがプールで実行されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="89c98-107">Ensure that the Office Communications Server 2007 R2 services are running on the pool.</span></span>
    
    <span data-ttu-id="89c98-108">![Office Communications Server 2007 R2 管理コンソール](images/JJ721906.76897b6d-f433-47d2-930d-0816fc30a3c2(OCS.15).jpg "Office Communications Server 2007 R2 管理コンソール")</span><span class="sxs-lookup"><span data-stu-id="89c98-108">![Office Communications Server 2007 R2 Admin Console](images/JJ721906.76897b6d-f433-47d2-930d-0816fc30a3c2(OCS.15).jpg "Office Communications Server 2007 R2 Admin Console")</span></span>  

</div>

<div>

## <a name="verify-the-pilot-pool-in-lync-server-2013-control-panel"></a><span data-ttu-id="89c98-109">Lync Server 2013 コントロールパネルでパイロットプールを確認する</span><span class="sxs-lookup"><span data-stu-id="89c98-109">Verify the Pilot Pool in Lync Server 2013 Control Panel</span></span>

1.  <span data-ttu-id="89c98-110">CsAdministrator ロールのメンバーであるユーザーアカウントから、Lync Server 2013 フロントエンドサーバーにログオンします。</span><span class="sxs-lookup"><span data-stu-id="89c98-110">From a user account that is a member of the CsAdministrator role, log on to the Lync Server 2013 Front End server.</span></span>

2.  <span data-ttu-id="89c98-111">ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="89c98-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="89c98-112">Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="89c98-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="89c98-113">[**トポロジ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="89c98-113">Click **Topology**.</span></span>

4.  <span data-ttu-id="89c98-114">展開したサーバーがパイロットプールに存在することを確認します。</span><span class="sxs-lookup"><span data-stu-id="89c98-114">Verify that the servers you deployed are present in your pilot pool.</span></span>
    
    <span data-ttu-id="89c98-115">![Lync Server コントロールパネルのトポロジページ](images/JJ204914.a3d1ba5f-c1a7-45e8-b9a5-7cb07b01af8c(OCS.15).jpg "Lync Server コントロールパネルのトポロジページ")</span><span class="sxs-lookup"><span data-stu-id="89c98-115">![Lync Server Control Panel Topology page](images/JJ204914.a3d1ba5f-c1a7-45e8-b9a5-7cb07b01af8c(OCS.15).jpg "Lync Server Control Panel Topology page")</span></span>  

</div>

<div>

## <a name="verify-lync-server-2013-services-have-started"></a><span data-ttu-id="89c98-116">Lync Server 2013 サービスが開始されたことを確認する</span><span class="sxs-lookup"><span data-stu-id="89c98-116">Verify Lync Server 2013 services have started</span></span>

1.  <span data-ttu-id="89c98-117">Lync Server 2013 フロントエンドサーバーで、[**管理ツール**] グループから [**サービス**] アプレットを開きます。</span><span class="sxs-lookup"><span data-stu-id="89c98-117">On the Lync Server 2013 Front End Server, open the **Services** applet from the **Administrative Tools** group.</span></span>

2.  <span data-ttu-id="89c98-118">表示されているサービスが、次の図のリストと一致することを確認します。</span><span class="sxs-lookup"><span data-stu-id="89c98-118">Verify that the services listed match the list in the following figure.</span></span>
    
    <span data-ttu-id="89c98-119">![Lync サービスが開始されたことを示す [サービス] ページ](images/JJ204914.fd35d54a-2ab6-4c09-b5e9-fd5bf10f6f51(OCS.15).jpg "Lync サービスが開始されたことを示す [サービス] ページ")</span><span class="sxs-lookup"><span data-stu-id="89c98-119">![Services page showing Lync services started](images/JJ204914.fd35d54a-2ab6-4c09-b5e9-fd5bf10f6f51(OCS.15).jpg "Services page showing Lync services started")</span></span>  

</div>

</div>

<span> </span>

</div>

</div>

</div>

