---
title: 'Lync Server 2013: ディレクターでのサービスの開始'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Start services on the Director
ms:assetid: 095b13e1-e788-4b80-93fa-5c5e7498678b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398146(v=OCS.15)
ms:contentKeyID: 48183351
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dc8536008f2b9bf4b66b1d4a1f9e9577835adb03
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142533"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="start-services-on-the-director-in-lync-server-2013"></a><span data-ttu-id="ad809-102">Lync Server 2013 でディレクターのサービスを開始する</span><span class="sxs-lookup"><span data-stu-id="ad809-102">Start services on the Director in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ad809-103">_**トピックの最終更新日:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="ad809-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="ad809-104">ローカル構成ストアをインストールし、Lync Server コンポーネントをインストールして、ディレクターで証明書を構成した後、サーバー上で Lync Server サービスを開始する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ad809-104">After you install the Local Configuration Store, install the Lync Server Components, and configure certificates on a Director, you must start the Lync Server services on the server.</span></span> <span data-ttu-id="ad809-105">以下の手順を使用して、展開内の各ディレクターでサービスを開始できます。</span><span class="sxs-lookup"><span data-stu-id="ad809-105">You can use the following procedure to start services on each Director in your deployment.</span></span>

<div>

## <a name="to-start-services-on-a-director"></a><span data-ttu-id="ad809-106">ディレクターでサービスを開始するには</span><span class="sxs-lookup"><span data-stu-id="ad809-106">To start services on a Director</span></span>

1.  <span data-ttu-id="ad809-107">Lync Server 展開ウィザードの [ **Lync server 2013** ] ページで、[**ステップ 4: サービスの開始**] の横にある [**実行**] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="ad809-107">In the Lync Server Deployment Wizard, on the **Lync Server 2013** page, click the **Run** button next to **Step 4: Start Services**.</span></span>

2.  <span data-ttu-id="ad809-108">[**サービスの開始**] ページで、[**次**へ] をクリックして、サーバー上の Lync Server サービスを開始します。</span><span class="sxs-lookup"><span data-stu-id="ad809-108">On the **Start Services** page, click **Next** to start the Lync Server services on the server.</span></span>

3.  <span data-ttu-id="ad809-109">すべてのサービスが正常に開始されたら、[**コマンドの実行**] ページで [**終了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ad809-109">On the **Executing Commands** page, after all services have started successfully, click **Finish**.</span></span>

4.  <span data-ttu-id="ad809-110">[**ステップ 4: サービスの開始**] の下にある [**サービスの状態 (オプション)**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ad809-110">Below **Step 4: Start Services**, click **Services Status (Optional)**.</span></span>

5.  <span data-ttu-id="ad809-111">サーバーの**サービス**Microsoft 管理コンソール (MMC) で、すべての Lync server 2013 サービスが実行されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="ad809-111">In the **Services** Microsoft Management Console (MMC) on the server, verify that all of the Lync Server 2013 services are running.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

