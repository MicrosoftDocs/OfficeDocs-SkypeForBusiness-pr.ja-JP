---
title: 'Lync Server 2013: 既存の Web サービス構成設定の変更'
description: 'Lync Server 2013: 既存の Web サービス構成設定を変更します。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify existing Web Service configuration settings
ms:assetid: bd9c7aa5-d31c-4fab-b31d-8baae26b1296
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182580(v=OCS.15)
ms:contentKeyID: 48185272
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 455ddf60d171fe584115d646b16f63595285a906
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566993"
---
# <a name="modify-existing-web-service-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="17453-103">Lync Server 2013 で既存の Web サービス構成設定を変更する</span><span class="sxs-lookup"><span data-stu-id="17453-103">Modify existing Web Service configuration settings in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="17453-104">_**トピックの最終更新日:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="17453-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="17453-105">[ **Web サービス** ] ページを使用して、Lync Server 2013 に関連する web サーバーと web サービスにアクセスするための認証方法を構成できます。</span><span class="sxs-lookup"><span data-stu-id="17453-105">You can use the **Web Service** page to configure the authentication methods for accessing Lync Server 2013 related web servers and Web Services.</span></span>

<span data-ttu-id="17453-106">既存の Web サービス ポリシーを変更するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="17453-106">Follow these steps to modify an existing Web Service policy.</span></span>

<div>

## <a name="to-modify-existing-web-service-configuration-settings"></a><span data-ttu-id="17453-107">既存の Web サービス構成設定を変更するには</span><span class="sxs-lookup"><span data-stu-id="17453-107">To modify existing Web service configuration settings</span></span>

1.  <span data-ttu-id="17453-108">RTCUniversalServerAdmins グループのメンバーである (または同等のユーザー権限を持つ) ユーザー アカウント、または CsServerAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、Lync Server 2013 を展開したネットワーク内の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="17453-108">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="17453-109">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="17453-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="17453-110">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="17453-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="17453-111">左側のナビゲーション バーで [**セキュリティ**] をクリックし、[**Web サービス**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="17453-111">In the left navigation bar, click **Security** and then click **Web Service**.</span></span>

4.  <span data-ttu-id="17453-112">[**Web サービス**] ページで、構成をクリックし、[**編集**] をクリックしてから、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="17453-112">On the **Web Service** page, click a configuration, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="17453-113">[**Web サービス設定の編集**] の [**Windows 認証**] で、[**ネゴシエート**]、[**統合 Windows 認証**]、または [**なし**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="17453-113">In **Edit Web Service Setting**, in **Integrated Windows authentication**, select **Negotiate**, **Integrated Windows authentication**, or **None**.</span></span>

6.  <span data-ttu-id="17453-114">クライアントの機能および環境のサポート状況に応じて、次の中から 1 つ以上選択します。</span><span class="sxs-lookup"><span data-stu-id="17453-114">Select one or more of the following depending on the capabilities of the clients and support in your environment:</span></span>
    
      - <span data-ttu-id="17453-115">[**PIN 認証を有効にする**]。PIN 番号を使用してクライアントが承認されるようにします。</span><span class="sxs-lookup"><span data-stu-id="17453-115">**Enable PIN Authentication** to enable clients to be authenticated using PIN numbers.</span></span>
    
      - <span data-ttu-id="17453-116">[**証明書認証を有効にする**]。プール内のサーバーは、クライアントに対して証明書を発行します。</span><span class="sxs-lookup"><span data-stu-id="17453-116">**Enable certificate authentication** to have the servers in the pool issue certificates to clients.</span></span>
    
      - <span data-ttu-id="17453-117">[**証明書チェーンのダウンロードを有効にする**]。認証証明書を与えられたサーバーがその証明書の証明書チェーンをダウンロードできるようにします。</span><span class="sxs-lookup"><span data-stu-id="17453-117">**Enable certificate chain download** to have servers presented with an authentication certificate download the certificate chain for that certificate.</span></span>

7.  <span data-ttu-id="17453-118">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="17453-118">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="17453-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="17453-119">See Also</span></span>


[<span data-ttu-id="17453-120">Lync Server 2013 コントロールパネルでの認証の構成</span><span class="sxs-lookup"><span data-stu-id="17453-120">Configuring authentication in the Lync Server 2013 Control Panel</span></span>](lync-server-2013-configuring-authentication-in-the-lync-server-control-panel.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

