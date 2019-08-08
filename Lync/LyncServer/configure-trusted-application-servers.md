---
title: 信頼済みアプリケーション サーバーの構成
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
TOCTitle: Configure trusted application servers
ms:assetid: 20c3815f-3048-4940-8c0f-cdfcd0801d5d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204735(v=OCS.15)
ms:contentKeyID: 48183592
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cab126429fc5ec77a2308fdc1e1f8965fdfccb5b
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233184"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-trusted-application-servers"></a><span data-ttu-id="97285-102">信頼済みアプリケーション サーバーの構成</span><span class="sxs-lookup"><span data-stu-id="97285-102">Configure trusted application servers</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="97285-103">_**最終更新日:** 2012-10-11_</span><span class="sxs-lookup"><span data-stu-id="97285-103">_**Topic Last Modified:** 2012-10-11_</span></span>

<span data-ttu-id="97285-104">混在環境では、新しい信頼できるアプリケーションサーバーを作成する場合は、次ホッププールを Lync Server 2013 プールとして設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="97285-104">In a mixed environment, if you create a new trusted application server, you must set the next hop pool to be a Lync Server 2013 pool.</span></span> <span data-ttu-id="97285-105">混在環境では、従来の Lync Server 2010 プールと Lync Server 2013 プールの両方がドロップダウンリストに表示されます。</span><span class="sxs-lookup"><span data-stu-id="97285-105">In a mixed environment, both the legacy Lync Server 2010 pool and the Lync Server 2013 pool appear in the drop down list.</span></span> <span data-ttu-id="97285-106">従来のプールの選択はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="97285-106">Selecting the legacy pool is not supported.</span></span>

<span data-ttu-id="97285-107">**信頼できるアプリケーションサーバーを作成するときに、[Lync Server 2013 (次ホップ)] を選択します。**</span><span class="sxs-lookup"><span data-stu-id="97285-107">**Select Lync Server 2013 as next hop when creating a Trusted application server**</span></span>

1.  <span data-ttu-id="97285-108">トポロジビルダーを開きます。</span><span class="sxs-lookup"><span data-stu-id="97285-108">Open Topology Builder.</span></span>

2.  <span data-ttu-id="97285-109">左側のウィンドウで、[**信頼されたアプリケーションサーバー** ] を右クリックし、[**新しい信頼できるアプリケーションプール**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="97285-109">In the left pane, right click **Trusted application servers** and click **New Trusted Application Pool**.</span></span>

3.  <span data-ttu-id="97285-110">信頼されているアプリケーションプールの**プール FQDN**を入力し、それが単一サーバーか複数サーバーかを選択します。</span><span class="sxs-lookup"><span data-stu-id="97285-110">Enter the **Pool FQDN** of the trusted application pool and select whether it will be a single-server or multiple-server.</span></span>

4.  <span data-ttu-id="97285-111">[ **次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="97285-111">Click **Next**.</span></span>

5.  <span data-ttu-id="97285-112">**[次ホップの選択**] ページで、一覧から Lync Server 2013 フロントエンドプールを選びます。</span><span class="sxs-lookup"><span data-stu-id="97285-112">On the **Select the next hop** page, from the list, select the Lync Server 2013 Front End pool.</span></span>

6.  <span data-ttu-id="97285-113">[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="97285-113">Click **Finish**.</span></span>

7.  <span data-ttu-id="97285-114">トップノードの**Lync サーバー**を選択し、[**操作**] メニューの [**発行**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="97285-114">Select the top node **Lync Server** and from the **Action** menu, select **Publish**.</span></span>
    
    <span data-ttu-id="97285-115">信頼された**アプリケーションプール**が正常に作成され、正しいフロントエンドプールに関連付けられていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="97285-115">Verify the **Trusted Application Pool** has been created successfully and is associated with the correct Front End pool.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

