---
title: 信頼されたアプリケーション サーバーを構成する
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure trusted application servers
ms:assetid: 47a9e72e-566c-4c23-bec2-760a3098a974
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204865(v=OCS.15)
ms:contentKeyID: 48184056
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0474e3e75998e43965bd57ef4ed1f67ef8058a0b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48503274"
---
# <a name="configure-trusted-application-servers"></a><span data-ttu-id="188a6-102">信頼されたアプリケーション サーバーを構成する</span><span class="sxs-lookup"><span data-stu-id="188a6-102">Configure trusted application servers</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="188a6-103">_**トピックの最終更新日:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="188a6-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="188a6-104">混在環境では、従来の Office Communications Server トポロジを Lync Server 2013 とマージした後で、新しい信頼されたアプリケーションサーバーを作成した後、トポロジビルダーを使用して新しい信頼されたアプリケーションサーバーを定義する場合は、次ホッププールを Lync Server 2013 プールに設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="188a6-104">In a mixed environment, if you create a new trusted application server after merging the legacy Office Communications Server topology with Lync Server 2013, and you define a new trusted application server using Topology Builder, you must set the next hop pool to be a Lync Server 2013 pool.</span></span> <span data-ttu-id="188a6-105">マージされた環境では、従来の Office Communications Server プールと Lync Server 2013 プールの両方がドロップダウンリストに表示されます。</span><span class="sxs-lookup"><span data-stu-id="188a6-105">In a merged environment, both the legacy Office Communications Server pool and the Lync Server 2013 pool appear in the drop down list.</span></span> <span data-ttu-id="188a6-106">従来のプールの選択はサポートされていません\*\*。</span><span class="sxs-lookup"><span data-stu-id="188a6-106">Selecting the legacy pool is *not* supported.</span></span>

<div>

## <a name="to-select-lync-server-2013-as-next-hop-when-creating-a-trusted-application-server"></a><span data-ttu-id="188a6-107">信頼されたアプリケーションサーバーの作成時に Lync Server 2013 を次ホップとして選択するには</span><span class="sxs-lookup"><span data-stu-id="188a6-107">To select Lync Server 2013 as next hop when creating a Trusted application server</span></span>

1.  <span data-ttu-id="188a6-108">トポロジ ビルダーで既存のトポロジを開きます。</span><span class="sxs-lookup"><span data-stu-id="188a6-108">Open an existing topology in Topology Builder.</span></span>

2.  <span data-ttu-id="188a6-109">左側のウィンドウで、[**信頼済みアプリケーション サーバー**] を右クリックし、[**新しい信頼済みアプリケーション プール**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="188a6-109">In the left pane, right click **Trusted application servers** and click **New Trusted Application Pool**.</span></span>

3.  <span data-ttu-id="188a6-110">信頼済みアプリケーション プールの [**プールの FQDN**] を入力し、単一サーバーの展開にするか複数サーバーの展開にするかを選択します。</span><span class="sxs-lookup"><span data-stu-id="188a6-110">Enter the **Pool FQDN** of the trusted application pool and select whether it will be a single-server or multiple-server deployment.</span></span>

4.  <span data-ttu-id="188a6-111">[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="188a6-111">Click **Next**.</span></span>

5.  <span data-ttu-id="188a6-112">[ **次ホップの選択** ] ページで、リストから Lync Server 2013 フロントエンドプールを選択します。</span><span class="sxs-lookup"><span data-stu-id="188a6-112">On the **Select the next hop** page, from the list, select the Lync Server 2013 Front End pool.</span></span>
    
    <span data-ttu-id="188a6-113">![[信頼されたアプリケーションプールの新規定義] ダイアログ](images/JJ204865.ecfe2bb8-758b-4b36-8146-573005c4ab09(OCS.15).jpg "[信頼されたアプリケーションプールの新規定義] ダイアログ")</span><span class="sxs-lookup"><span data-stu-id="188a6-113">![Define New Trusted Application Pool dialog](images/JJ204865.ecfe2bb8-758b-4b36-8146-573005c4ab09(OCS.15).jpg "Define New Trusted Application Pool dialog")</span></span>  

6.  <span data-ttu-id="188a6-114">[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="188a6-114">Click **Finish**.</span></span>

7.  <span data-ttu-id="188a6-115">上位ノードの [**Lync Server**] を選択し、[**操作**] ウィンドウで [**公開**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="188a6-115">Select the top node **Lync Server** and from the **Actions** pane, select **Publish**.</span></span>

8.  <span data-ttu-id="188a6-116">[**信頼済みアプリケーション プール**] が正常に作成され、適切なフロントエンド プールに関連付けられたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="188a6-116">Verify the **Trusted Application Pool** was created successfully and is associated with the correct Front End pool.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

