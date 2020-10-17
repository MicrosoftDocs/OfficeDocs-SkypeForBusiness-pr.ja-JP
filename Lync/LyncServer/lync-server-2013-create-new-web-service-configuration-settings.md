---
title: 'Lync Server 2013: 新しい Web サービス構成設定の作成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create new Web Service configuration settings
ms:assetid: f3f04d81-8a1f-427f-bd0f-fb659024e096
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182605(v=OCS.15)
ms:contentKeyID: 48185801
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2d44e86ad1d587bd3dddb921cdeea3ed2a65ea26
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48515574"
---
# <a name="create-new-web-service-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="49ad6-102">Lync Server 2013 で新しい Web サービス構成設定を作成する</span><span class="sxs-lookup"><span data-stu-id="49ad6-102">Create new Web Service configuration settings in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="49ad6-103">_**トピックの最終更新日:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="49ad6-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="49ad6-104">[ **Web サービス** ] ページを使用して、Lync Server 2013 に関連する web サーバーと web サービスにアクセスするための認証方法を構成できます。</span><span class="sxs-lookup"><span data-stu-id="49ad6-104">You can use the **Web Service** page to configure the authentication methods for accessing Lync Server 2013 related web servers and Web Services.</span></span>

<span data-ttu-id="49ad6-105">以下の手順に従って新しい Web サービス ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="49ad6-105">Follow these steps to create a new Web Service policy.</span></span>

<div>

## <a name="to-create-new-web-service-configuration-settings"></a><span data-ttu-id="49ad6-106">新しい web サービス構成設定を作成するには</span><span class="sxs-lookup"><span data-stu-id="49ad6-106">To create new web service configuration settings</span></span>

1.  <span data-ttu-id="49ad6-107">RTCUniversalServerAdmins グループのメンバーである (または同等のユーザー権限を持つ) ユーザー アカウント、または CsServerAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、Lync Server 2013 を展開したネットワーク内の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="49ad6-107">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="49ad6-108">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="49ad6-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="49ad6-109">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="49ad6-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="49ad6-110">左側のナビゲーション バーで [**セキュリティ**] をクリックし、[**Web サービス**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="49ad6-110">In the left navigation bar, click **Security** and then click **Web Service**.</span></span>

4.  <span data-ttu-id="49ad6-111">[**Web サービス**] ページで、[**新規作成**] をクリックし、次のいずれかを実行します。</span><span class="sxs-lookup"><span data-stu-id="49ad6-111">On the **Web Service** page, click **New**, and then do one of the following:</span></span>
    
      - <span data-ttu-id="49ad6-p102">サイトの Web サービスを構成するには、[**サイト構成**] をクリックします。 [**サイトの選択**] で、Web サービス ポリシーを適用するサイトをクリックし、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="49ad6-p102">To configure the Web Service for a site, click **Site configuration**. In **Select a Site**, click the site to which the Web Service policy will be applied a site and click **OK**.</span></span>
    
      - <span data-ttu-id="49ad6-p103">プールの Web サービスを構成するには、[**プール構成**] をクリックします。 [**サービスの選択**] で、Web サービス ポリシーを適用するサービスをクリックし、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="49ad6-p103">To configure the Web Service for a pool, click **Pool configuration**. In **Select a Service**, click the service to which the Web Service policy will be applied and click **OK**.</span></span>

5.  <span data-ttu-id="49ad6-116">[**新規 Web サービス設定**] の [**統合 Windows 認証**] で、[**ネゴシエート**]、[**統合 Windows 認証**]、または [**なし**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="49ad6-116">In **New Web Service Setting**, in **Integrated Windows authentication**, select **Negotiate**, **Integrated Windows authentication**, or **None**.</span></span>

6.  <span data-ttu-id="49ad6-117">クライアントの機能および環境のサポート状況に応じて、次の中から 1 つ以上選択します。</span><span class="sxs-lookup"><span data-stu-id="49ad6-117">Select one or more of the following depending on the capabilities of the clients and support in your environment:</span></span>
    
      - <span data-ttu-id="49ad6-118">[**PIN 認証を有効にする**]。PIN 番号を使用してクライアントが承認されるようにします。</span><span class="sxs-lookup"><span data-stu-id="49ad6-118">**Enable PIN Authentication** to enable clients to be authenticated using PIN numbers.</span></span>
    
      - <span data-ttu-id="49ad6-119">[**証明書認証を有効にする**]。プール内のサーバーは、クライアントに対して証明書を発行します。</span><span class="sxs-lookup"><span data-stu-id="49ad6-119">**Enable certificate authentication** to have the servers in the pool issue certificates to clients.</span></span>
    
      - <span data-ttu-id="49ad6-120">[**証明書チェーンのダウンロードを有効にする**]。認証証明書を与えられたサーバーがその証明書の証明書チェーンをダウンロードできるようにします。</span><span class="sxs-lookup"><span data-stu-id="49ad6-120">**Enable certificate chain download** to have servers presented with an authentication certificate download the certificate chain for that certificate.</span></span>

7.  <span data-ttu-id="49ad6-121">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="49ad6-121">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

