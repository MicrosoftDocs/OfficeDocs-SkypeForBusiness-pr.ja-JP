---
title: 通話受付管理のリセット
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Reset call admission control
ms:assetid: 5873f56c-f3d6-4d73-beea-c9f37d5077f6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688064(v=OCS.15)
ms:contentKeyID: 49733658
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2140327f4c95f1f83f9720b7f14ef9650b8a7746
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42189350"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="reset-call-admission-control"></a><span data-ttu-id="e5a88-102">通話受付管理のリセット</span><span class="sxs-lookup"><span data-stu-id="e5a88-102">Reset call admission control</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e5a88-103">_**トピックの最終更新日:** 2012-10-11_</span><span class="sxs-lookup"><span data-stu-id="e5a88-103">_**Topic Last Modified:** 2012-10-11_</span></span>

<span data-ttu-id="e5a88-104">Lync server 2010 フロントエンドプールが通話受付管理 (CAC) をホストしている場合は、lync server 2010 フロントエンドプールを削除する前に、CAC ホスティングを Lync Server 2013 プールに移動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e5a88-104">If a Lync Server 2010 Front End pool is hosting call admission control (CAC), you must move CAC hosting to a Lync Server 2013 pool before you can remove the Lync Server 2010 Front End pool.</span></span>

<div>

## <a name="to-reset-cac"></a><span data-ttu-id="e5a88-105">CAC をリセットするには</span><span class="sxs-lookup"><span data-stu-id="e5a88-105">To reset CAC</span></span>

1.  <span data-ttu-id="e5a88-106">トポロジ ビルダーを開きます。</span><span class="sxs-lookup"><span data-stu-id="e5a88-106">Open Topology Builder.</span></span>

2.  <span data-ttu-id="e5a88-107">サイト ノードを右クリックし、[**プロパティの編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e5a88-107">Right-click the site node, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="e5a88-108">[**通話受付管理の設定**] で、[**通話受付管理の有効化**] が選択されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="e5a88-108">Under **Call Admission Control setting**, make sure **Enable Call Admission Control** is selected.</span></span>

4.  <span data-ttu-id="e5a88-109">[**フロントエンドプール] で通話受付管理 (cac) を実行する**には、cac をホストする Lync Server 2013 プールを選択し、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e5a88-109">Under **Front End pool to run call admission control (CAC)**, select the Lync Server 2013 pool that is to host CAC, and then click **OK**.</span></span>

5.  <span data-ttu-id="e5a88-110">トポロジを公開します。</span><span class="sxs-lookup"><span data-stu-id="e5a88-110">Publish the topology.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

