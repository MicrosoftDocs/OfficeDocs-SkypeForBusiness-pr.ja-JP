---
title: 信頼済みアプリケーション サーバーの構成
ms.reviewer: ''
ms.author: kenwith
author: kenwith
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
ms.openlocfilehash: 92e7f2c808e9ea5a3e8dfbf3010715c86e02596e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728947"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-trusted-application-servers"></a><span data-ttu-id="d2417-102">信頼済みアプリケーション サーバーの構成</span><span class="sxs-lookup"><span data-stu-id="d2417-102">Configure trusted application servers</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d2417-103">_**最終更新日:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="d2417-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="d2417-104">混在環境では、従来の Office Communications Server トポロジを Lync Server 2013 と統合した後に新しい信頼できるアプリケーションサーバーを作成し、トポロジビルダーを使用して新しい信頼されたアプリケーションサーバーを定義する場合は、次のホッププールをに設定する必要があります。Lync Server 2013 プール。</span><span class="sxs-lookup"><span data-stu-id="d2417-104">In a mixed environment, if you create a new trusted application server after merging the legacy Office Communications Server topology with Lync Server 2013, and you define a new trusted application server using Topology Builder, you must set the next hop pool to be a Lync Server 2013 pool.</span></span> <span data-ttu-id="d2417-105">統合された環境では、従来の Office Communications Server プールと Lync Server 2013 プールの両方がドロップダウンリストに表示されます。</span><span class="sxs-lookup"><span data-stu-id="d2417-105">In a merged environment, both the legacy Office Communications Server pool and the Lync Server 2013 pool appear in the drop down list.</span></span> <span data-ttu-id="d2417-106">従来のプールの選択はサポートされて*いません*。</span><span class="sxs-lookup"><span data-stu-id="d2417-106">Selecting the legacy pool is *not* supported.</span></span>

<div>

## <a name="to-select-lync-server-2013-as-next-hop-when-creating-a-trusted-application-server"></a><span data-ttu-id="d2417-107">信頼されているアプリケーションサーバーを作成するときに、次ホップとして Lync Server 2013 を選ぶには</span><span class="sxs-lookup"><span data-stu-id="d2417-107">To select Lync Server 2013 as next hop when creating a Trusted application server</span></span>

1.  <span data-ttu-id="d2417-108">トポロジビルダーで既存のトポロジを開きます。</span><span class="sxs-lookup"><span data-stu-id="d2417-108">Open an existing topology in Topology Builder.</span></span>

2.  <span data-ttu-id="d2417-109">左側のウィンドウで、[**信頼されたアプリケーションサーバー** ] を右クリックし、[**新しい信頼できるアプリケーションプール**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d2417-109">In the left pane, right click **Trusted application servers** and click **New Trusted Application Pool**.</span></span>

3.  <span data-ttu-id="d2417-110">信頼されているアプリケーションプールの**プール FQDN**を入力し、単一サーバー展開と複数サーバーのどちらの展開にするかを選択します。</span><span class="sxs-lookup"><span data-stu-id="d2417-110">Enter the **Pool FQDN** of the trusted application pool and select whether it will be a single-server or multiple-server deployment.</span></span>

4.  <span data-ttu-id="d2417-111">[ **次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d2417-111">Click **Next**.</span></span>

5.  <span data-ttu-id="d2417-112">**[次ホップの選択**] ページで、一覧から Lync Server 2013 フロントエンドプールを選びます。</span><span class="sxs-lookup"><span data-stu-id="d2417-112">On the **Select the next hop** page, from the list, select the Lync Server 2013 Front End pool.</span></span>
    
    <span data-ttu-id="d2417-113">![[新しい信頼されたアプリケーションプールの定義] ダイアログ](images/JJ204865.ecfe2bb8-758b-4b36-8146-573005c4ab09(OCS.15).jpg "[新しい信頼されたアプリケーションプールの定義] ダイアログ")</span><span class="sxs-lookup"><span data-stu-id="d2417-113">![Define New Trusted Application Pool dialog](images/JJ204865.ecfe2bb8-758b-4b36-8146-573005c4ab09(OCS.15).jpg "Define New Trusted Application Pool dialog")</span></span>  

6.  <span data-ttu-id="d2417-114">[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d2417-114">Click **Finish**.</span></span>

7.  <span data-ttu-id="d2417-115">トップノードの**Lync サーバー**を選択し、[**操作**] ウィンドウで [**発行**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="d2417-115">Select the top node **Lync Server** and from the **Actions** pane, select **Publish**.</span></span>

8.  <span data-ttu-id="d2417-116">信頼された**アプリケーションプール**が正常に作成され、正しいフロントエンドプールに関連付けられていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="d2417-116">Verify the **Trusted Application Pool** was created successfully and is associated with the correct Front End pool.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

