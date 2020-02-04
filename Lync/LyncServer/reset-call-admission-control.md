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
ms.openlocfilehash: 6956b1a871a4a0a5c7e758d2890a58989f5ac8a2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726997"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="reset-call-admission-control"></a><span data-ttu-id="a5d36-102">通話受付管理のリセット</span><span class="sxs-lookup"><span data-stu-id="a5d36-102">Reset call admission control</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a5d36-103">_**最終更新日:** 2012-10-11_</span><span class="sxs-lookup"><span data-stu-id="a5d36-103">_**Topic Last Modified:** 2012-10-11_</span></span>

<span data-ttu-id="a5d36-104">Lync Server 2010 フロントエンドプールが通話受付制御 (CAC) をホストしている場合は、lync server 2010 フロントエンドプールを削除する前に、CAC ホスティングを Lync Server 2013 プールに移動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a5d36-104">If a Lync Server 2010 Front End pool is hosting call admission control (CAC), you must move CAC hosting to a Lync Server 2013 pool before you can remove the Lync Server 2010 Front End pool.</span></span>

<div>

## <a name="to-reset-cac"></a><span data-ttu-id="a5d36-105">CAC をリセットするには</span><span class="sxs-lookup"><span data-stu-id="a5d36-105">To reset CAC</span></span>

1.  <span data-ttu-id="a5d36-106">トポロジビルダーを開きます。</span><span class="sxs-lookup"><span data-stu-id="a5d36-106">Open Topology Builder.</span></span>

2.  <span data-ttu-id="a5d36-107">サイトノードを右クリックし、[プロパティの**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a5d36-107">Right-click the site node, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="a5d36-108">「**通話受付制御の設定**」で、「**通話受付制御を有効にする**」が選択されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="a5d36-108">Under **Call Admission Control setting**, make sure **Enable Call Admission Control** is selected.</span></span>

4.  <span data-ttu-id="a5d36-109">[**フロントエンドプール] で、通話受付制御 (cac) を実行する**には、cac をホストする Lync Server 2013 プールを選び、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a5d36-109">Under **Front End pool to run call admission control (CAC)**, select the Lync Server 2013 pool that is to host CAC, and then click **OK**.</span></span>

5.  <span data-ttu-id="a5d36-110">トポロジを公開します。</span><span class="sxs-lookup"><span data-stu-id="a5d36-110">Publish the topology.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

