---
title: Office Communications Server 2007 R2 Edge サーバーへの接続を承認する
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
TOCTitle: Authorize connection to Office Communications Server 2007 R2 Edge Server
ms:assetid: 14f6798a-28d6-4b3d-8734-942192e1bbf5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204702(v=OCS.15)
ms:contentKeyID: 48183493
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 04bc5d92b45f65c864da046951ce7ebd42155ed2
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2019
ms.locfileid: "36232927"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="authorize-connection-to-office-communications-server-2007-r2-edge-server"></a><span data-ttu-id="3619f-102">Office Communications Server 2007 R2 Edge サーバーへの接続を承認する</span><span class="sxs-lookup"><span data-stu-id="3619f-102">Authorize connection to Office Communications Server 2007 R2 Edge Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3619f-103">_**最終更新日:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="3619f-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="3619f-104">パイロットプールの各 Lync Server 2013 フロントエンドサーバーまたは Standard Edition サーバーの場合、Office Communications Server 2007 R2 Edge Server への接続が許可されている内部サーバーの一覧を更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3619f-104">For each Lync Server 2013 Front End Server or Standard Edition server in your pilot pool, you must update the list of internal servers that are authorized to connect to the Office Communications Server 2007 R2 Edge Server.</span></span> <span data-ttu-id="3619f-105">これらの更新プログラムがないと、従来のエッジサーバーを使用して参加しているユーザーの外部オーディオ/ビジュアル (A/V) 会議が機能しなくなります。</span><span class="sxs-lookup"><span data-stu-id="3619f-105">Without these updates, external audio/visual (A/V) conferencing for users joining by using the legacy Edge Server will not work.</span></span>

<div>

## <a name="to-authorize-connection-to-office-communications-server-2007-r2-edge-server"></a><span data-ttu-id="3619f-106">Office Communications Server 2007 R2 Edge サーバーへの接続を承認するには</span><span class="sxs-lookup"><span data-stu-id="3619f-106">To Authorize Connection to Office Communications Server 2007 R2 Edge Server</span></span>

1.  <span data-ttu-id="3619f-107">Office Communications Server 2007 R2 Edge サーバーから、[**管理ツール**] グループから [コンピューターの**管理**] スナップインを開きます。</span><span class="sxs-lookup"><span data-stu-id="3619f-107">From the Office Communications Server 2007 R2 Edge Server, from the **Administrative Tools** group, open the **Computer Management** snap-in.</span></span>

2.  <span data-ttu-id="3619f-108">コンソールツリーで、[**サービスとアプリケーション**] を展開します。</span><span class="sxs-lookup"><span data-stu-id="3619f-108">In the console tree, expand **Services and Applications**.</span></span>

3.  <span data-ttu-id="3619f-109">**Office Communications Server 2007 R2**を右クリックし、[**プロパティ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3619f-109">Right-click **Office Communications Server 2007 R2**, and then click **Properties**.</span></span>

4.  <span data-ttu-id="3619f-110">[**内部**] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="3619f-110">Click the **Internal** tab.</span></span>

5.  <span data-ttu-id="3619f-111">[**サーバーの追加**] の [**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3619f-111">Under **Add Server**, click **Add**.</span></span>

6.  <span data-ttu-id="3619f-112">[ **Office Communications Server の追加**] ダイアログボックスで、必要な情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="3619f-112">In the **Add Office Communications Server** dialog box, enter the appropriate information:</span></span>
    
      - <span data-ttu-id="3619f-113">各 Lync Server 2013 フロントエンドサーバーまたは標準エディションサーバー、および Lync Server 2013 プールの完全修飾ドメイン名 (FQDN) を指定します。</span><span class="sxs-lookup"><span data-stu-id="3619f-113">Specify the fully qualified domain name (FQDN) of each Lync Server 2013 Front End Server or Standard Edition server, and Lync Server 2013 pool.</span></span>
    
      - <span data-ttu-id="3619f-114">次ホップのコンピューターを FQDN で指定するプールで静的ルートを構成している場合は、Lync Server 2013 ディレクターの FQDN を指定します。</span><span class="sxs-lookup"><span data-stu-id="3619f-114">Specify the FQDN of the Lync Server 2013 Director if you configured a static route on the pool that specifies the next hop computer by its FQDN.</span></span>

7.  <span data-ttu-id="3619f-115">各 Lync Server 2013、フロントエンドサーバー、Standard Edition server、プール、およびディレクターのエントリを追加したら、[**適用**] をクリックし、[ **OK** ] をクリックしてプロパティページを閉じます。</span><span class="sxs-lookup"><span data-stu-id="3619f-115">After you have added an entry for each Lync Server 2013, Front End Server, Standard Edition server, pool, and Director, click **Apply** and then click **OK** to close the Properties page.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

