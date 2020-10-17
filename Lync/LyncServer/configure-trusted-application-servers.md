---
title: 信頼されたアプリケーション サーバーを構成する
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure trusted application servers
ms:assetid: 20c3815f-3048-4940-8c0f-cdfcd0801d5d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204735(v=OCS.15)
ms:contentKeyID: 48183592
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 664adfc18709a5976465548d326d2d7f4e79c468
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48503294"
---
# <a name="configure-trusted-application-servers"></a><span data-ttu-id="dba14-102">信頼されたアプリケーション サーバーを構成する</span><span class="sxs-lookup"><span data-stu-id="dba14-102">Configure trusted application servers</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dba14-103">_**トピックの最終更新日:** 2012-10-11_</span><span class="sxs-lookup"><span data-stu-id="dba14-103">_**Topic Last Modified:** 2012-10-11_</span></span>

<span data-ttu-id="dba14-104">混在環境では、信頼されたアプリケーションサーバーを新たに作成する場合は、次ホッププールを Lync Server 2013 プールに設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dba14-104">In a mixed environment, if you create a new trusted application server, you must set the next hop pool to be a Lync Server 2013 pool.</span></span> <span data-ttu-id="dba14-105">混在環境では、ドロップダウンリストに従来の Lync Server 2010 プールと Lync Server 2013 プールの両方が表示されます。</span><span class="sxs-lookup"><span data-stu-id="dba14-105">In a mixed environment, both the legacy Lync Server 2010 pool and the Lync Server 2013 pool appear in the drop down list.</span></span> <span data-ttu-id="dba14-106">従来のプールを選択することはできません。</span><span class="sxs-lookup"><span data-stu-id="dba14-106">Selecting the legacy pool is not supported.</span></span>

<span data-ttu-id="dba14-107">**信頼されたアプリケーションサーバーを作成するときに、次ホップとして Lync Server 2013 を選択する**</span><span class="sxs-lookup"><span data-stu-id="dba14-107">**Select Lync Server 2013 as next hop when creating a Trusted application server**</span></span>

1.  <span data-ttu-id="dba14-108">トポロジ ビルダーを開きます。</span><span class="sxs-lookup"><span data-stu-id="dba14-108">Open Topology Builder.</span></span>

2.  <span data-ttu-id="dba14-109">左側のウィンドウで、[**信頼済みアプリケーション サーバー**] を右クリックし、[**新しい信頼済みアプリケーション プール**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dba14-109">In the left pane, right click **Trusted application servers** and click **New Trusted Application Pool**.</span></span>

3.  <span data-ttu-id="dba14-110">信頼済みアプリケーション プールの [**プールの FQDN**] を入力し、単一サーバーにするか複数サーバーにするかを選択します。</span><span class="sxs-lookup"><span data-stu-id="dba14-110">Enter the **Pool FQDN** of the trusted application pool and select whether it will be a single-server or multiple-server.</span></span>

4.  <span data-ttu-id="dba14-111">[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dba14-111">Click **Next**.</span></span>

5.  <span data-ttu-id="dba14-112">[ **次ホップの選択** ] ページで、リストから Lync Server 2013 フロントエンドプールを選択します。</span><span class="sxs-lookup"><span data-stu-id="dba14-112">On the **Select the next hop** page, from the list, select the Lync Server 2013 Front End pool.</span></span>

6.  <span data-ttu-id="dba14-113">[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dba14-113">Click **Finish**.</span></span>

7.  <span data-ttu-id="dba14-114">最上位の [**Lync Server**] ノードを選択し、[**操作**] メニューの [**公開**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="dba14-114">Select the top node **Lync Server** and from the **Action** menu, select **Publish**.</span></span>
    
    <span data-ttu-id="dba14-115">**信頼済みアプリケーション プール**が正しく作成されていることと、適切なフロントエンド プールに関連付けられていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="dba14-115">Verify the **Trusted Application Pool** has been created successfully and is associated with the correct Front End pool.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

