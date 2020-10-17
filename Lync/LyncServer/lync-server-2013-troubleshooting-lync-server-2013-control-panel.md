---
title: 'Lync Server 2013: Lync Server 2013 コントロールパネルのトラブルシューティング'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Troubleshooting Lync Server 2013 Control Panel
ms:assetid: 54e7ab57-34ce-4a07-bcc9-643379eb4eb7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg195689(v=OCS.15)
ms:contentKeyID: 48184145
ms.date: 07/28/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b7da23bc56d18b1b5e6235551f7b99cc15e658fc
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48535934"
---
# <a name="troubleshooting-lync-server-2013-control-panel"></a><span data-ttu-id="ac905-102">Lync Server 2013 コントロール パネルのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="ac905-102">Troubleshooting Lync Server 2013 Control Panel</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ac905-103">_**トピックの最終更新日:** 2016-07-28_</span><span class="sxs-lookup"><span data-stu-id="ac905-103">_**Topic Last Modified:** 2016-07-28_</span></span>

<span data-ttu-id="ac905-104">このトピックでは、Lync Server 2013 コントロールパネルへのアクセスのトラブルシューティングに役立つ情報と手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="ac905-104">This topic provides information and procedures that can help you troubleshoot access to Lync Server 2013 Control Panel.</span></span>

<div>

## <a name="internet-browser-requirements"></a><span data-ttu-id="ac905-105">インターネット ブラウザーの要件</span><span class="sxs-lookup"><span data-stu-id="ac905-105">Internet Browser Requirements</span></span>

<span data-ttu-id="ac905-106">Lync Server コントロールパネルでは、Microsoft Silverlight ブラウザープラグインバージョン4.0.50524.0 または最新バージョンがインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="ac905-106">Lync Server Control Panel requires that Microsoft Silverlight browser plug-in version 4.0.50524.0 or latest version is installed.</span></span> <span data-ttu-id="ac905-107">Silverlight がインストールされていない場合、または以前のバージョンがインストールされている場合は、メッセージの指示に従って必要なバージョンをインストールします。</span><span class="sxs-lookup"><span data-stu-id="ac905-107">If Silverlight is not installed or if an earlier version is installed, follow the instructions in the message to install the required version.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ac905-108">Lync server コントロールパネルの他のソフトウェア要件は、Lync Server コントロールパネルとその他のすべての Lync Server 2013 管理ツールをインストールできるオペレーティングシステムに関連しています。</span><span class="sxs-lookup"><span data-stu-id="ac905-108">Other software requirements for Lync Server Control Panel pertain to the operating system on which Lync Server Control Panel and all other Lync Server 2013 administrative tools can be installed.</span></span> <span data-ttu-id="ac905-109">詳細については、「サポート」のドキュメントの「 <A href="lync-server-2013-server-and-tools-operating-system-support.md">Lync server 2013 でのサーバーとツールのオペレーティングシステムのサポート</A> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ac905-109">For details, see <A href="lync-server-2013-server-and-tools-operating-system-support.md">Server and tools operating system support in Lync Server 2013</A> in the Supportability documentation.</span></span>



</div>

<span data-ttu-id="ac905-110">セキュリティ上の理由から、インターネットブラウザーが Silverlight のインストールをブロックする場合は、Lync Server コントロールパネルを開く URL (Uniform Resource Locator) を信頼済みサイトの一覧に追加します。</span><span class="sxs-lookup"><span data-stu-id="ac905-110">If your Internet browser blocks installation of Silverlight due to security considerations, add the Uniform Resource Locator (URL) that opens Lync Server Control Panel to the list of trusted sites.</span></span> <span data-ttu-id="ac905-111">Internet Explorer のセキュリティ設定で、[**ActiveX コントロールとプラグインの実行**] が [**有効にする**] に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="ac905-111">In Internet Explorer security settings, ensure that **Run ActiveX controls and plug-ins** is set to **Enabled**.</span></span> <span data-ttu-id="ac905-112">詳細については、「」を参照してください [https://go.microsoft.com/fwlink/p/?linkId=214060](https://go.microsoft.com/fwlink/p/?linkid=214060) 。</span><span class="sxs-lookup"><span data-stu-id="ac905-112">For details, see [https://go.microsoft.com/fwlink/p/?linkId=214060](https://go.microsoft.com/fwlink/p/?linkid=214060).</span></span> <span data-ttu-id="ac905-113">また、ブラウザーが SSL 3.0 を使用するように構成されていることも確認してください。</span><span class="sxs-lookup"><span data-stu-id="ac905-113">Furthermore, ensure that the browser is configured to use SSL 3.0.</span></span>

<span data-ttu-id="ac905-p104">インターネット ブラウザーがプロキシ サーバーを使用するように構成されている場合、内部サイトとして自動検出されたサイトにはプロキシ サーバーを使用しない構成になっていることを確認します。または、プロキシ サーバーの構成設定で、アドレスをブラウザーの例外リストに追加します。</span><span class="sxs-lookup"><span data-stu-id="ac905-p104">If the Internet browser is configured to use a proxy server, verify that the browser is configured to bypass the proxy server for sites that are automatically detected as internal sites. Or, add the address to the browser's exception list in the proxy server configuration settings.</span></span>

</div>

<div>

## <a name="dns-record-and-certificate-requirements-for-the-administrative-access-url"></a><span data-ttu-id="ac905-116">管理アクセス URL の DNS レコードおよび証明書の要件</span><span class="sxs-lookup"><span data-stu-id="ac905-116">DNS Record and Certificate Requirements for the Administrative Access URL</span></span>

<span data-ttu-id="ac905-117">Lync Server コントロールパネルにアクセスするための簡単な URL を構成した場合は、その管理アクセス URL を使用するために必要な静的ドメインネームシステム (DNS) ホスト (A) リソースレコードと証明書も構成してください。</span><span class="sxs-lookup"><span data-stu-id="ac905-117">If you configured a simple URL to access Lync Server Control Panel, ensure that you also configured the static Domain Name System (DNS) host (A) resource record and certificate necessary to use that administrative access URL.</span></span> <span data-ttu-id="ac905-118">ベース URL をいつでも変更する場合は、変更が適切な DNS レコードと証明書に反映されていることと、各ディレクターおよびフロントエンドサーバーで、 *CsComputer* を実行して変更を登録していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="ac905-118">If you change the base URL at any time, ensure that the change is reflected in the appropriate DNS record and certificate and that you run the *Enable-CsComputer* on each Director and Front End Server to register the change.</span></span> <span data-ttu-id="ac905-119">詳細については、「計画」のドキュメントの以下のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ac905-119">For details, see the following topics in the Planning documentation:</span></span>

  - [<span data-ttu-id="ac905-120">Lync Server 2013 での簡単な Url の計画</span><span class="sxs-lookup"><span data-stu-id="ac905-120">Planning for simple URLs in Lync Server 2013</span></span>](lync-server-2013-planning-for-simple-urls.md)

  - [<span data-ttu-id="ac905-121">Lync Server 2013 の簡易 Url の DNS 要件</span><span class="sxs-lookup"><span data-stu-id="ac905-121">DNS requirements for simple URLs in Lync Server 2013</span></span>](lync-server-2013-dns-requirements-for-simple-urls.md)

  - [<span data-ttu-id="ac905-122">Lync Server 2013 の内部サーバーの証明書要件</span><span class="sxs-lookup"><span data-stu-id="ac905-122">Certificate requirements for internal servers in Lync Server 2013</span></span>](lync-server-2013-certificate-requirements-for-internal-servers.md)

<span data-ttu-id="ac905-123">管理アクセス URL を構成するための詳しい手順については、「展開」のドキュメントの「 [Edit or configure Simple URLs In Lync Server 2013](lync-server-2013-edit-or-configure-simple-urls.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ac905-123">For step-by-step procedures to configure the administrative access URL, see [Edit or configure simple URLs in Lync Server 2013](lync-server-2013-edit-or-configure-simple-urls.md) in the Deployment documentation.</span></span>

</div>

<div>

## <a name="internet-information-services-iis-requirements"></a><span data-ttu-id="ac905-124">インターネット インフォメーション サービス (IIS) の要件</span><span class="sxs-lookup"><span data-stu-id="ac905-124">Internet Information Services (IIS) Requirements</span></span>

<span data-ttu-id="ac905-125">Lync Server コントロールパネルは、インターネットインフォメーションサービス (IIS) を必要とする Lync Server 2013 のコンポーネントの1つです。</span><span class="sxs-lookup"><span data-stu-id="ac905-125">Lync Server Control Panel is one of the components of Lync Server 2013 that requires Internet Information Services (IIS).</span></span> <span data-ttu-id="ac905-126">特に、HTTP リダイレクト機能と Windows 認証機能が有効になっていること、および World Wide Web 発行サービス (W3SVC) が実行されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="ac905-126">In particular, ensure that HTTP redirection and Windows authentication features are enabled, and that the World Wide Web Publishing Service (W3SVC) is running.</span></span>

<div>

## <a name="world-wide-publishing-service-windows-service-dependency"></a><span data-ttu-id="ac905-127">World Wide Web 発行サービス (Windows サービス) への依存</span><span class="sxs-lookup"><span data-stu-id="ac905-127">World Wide Publishing Service (Windows Service) Dependency</span></span>

<span data-ttu-id="ac905-128">World Wide Web Publishing Service を停止すると、Lync Server コントロールパネルにアクセスできなくなります。</span><span class="sxs-lookup"><span data-stu-id="ac905-128">When the World Wide Web Publishing Service is stopped, you cannot access Lync Server Control Panel.</span></span> <span data-ttu-id="ac905-129">サービスを再起動するには、Windows サービス Microsoft 管理コンソール (MMC) を使用します。</span><span class="sxs-lookup"><span data-stu-id="ac905-129">You can restart the service by using the Windows Services Microsoft Management Console (MMC).</span></span>

<span data-ttu-id="ac905-130">**World Wide Web 発行サービスを開始するには**</span><span class="sxs-lookup"><span data-stu-id="ac905-130">**To start the World Wide Web Publishing Service**</span></span>

1.  <span data-ttu-id="ac905-131">World Wide Web Publishing Service がインストールされているコンピューターに、インターネットインフォメーションサービス (IIS) の一部としてログオンします。</span><span class="sxs-lookup"><span data-stu-id="ac905-131">Log on to the computer where the World Wide Web Publishing Service is installed as part of Internet Information Services (IIS).</span></span>

2.  <span data-ttu-id="ac905-132">[**スタート**] ボタンをクリックし、[**管理ツール**] をクリックして、[**サービス**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ac905-132">Click **Start**, click **Administrative Tools**, and then click **Services**.</span></span>

3.  <span data-ttu-id="ac905-133">[**World Wide Web 発行サービス**] を右クリックし、[**開始**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ac905-133">Right-click **World Wide Web Publishing Service**, and then click **Start**.</span></span>

</div>

<div>

## <a name="application-pool-mode"></a><span data-ttu-id="ac905-134">アプリケーション プール モード</span><span class="sxs-lookup"><span data-stu-id="ac905-134">Application Pool Mode</span></span>

<span data-ttu-id="ac905-135">CsManagementAppPool アプリケーション プールがネットワーク サービス アカウントをプロセス モデル ID として使用するように IIS を構成します。</span><span class="sxs-lookup"><span data-stu-id="ac905-135">Configure IIS so that the CsManagementAppPool application pool uses the Network Service account as its process model identity.</span></span>

</div>

</div>

<div>

## <a name="user-rights-and-permissions"></a><span data-ttu-id="ac905-136">ユーザー権限およびアクセス許可</span><span class="sxs-lookup"><span data-stu-id="ac905-136">User Rights and Permissions</span></span>

<span data-ttu-id="ac905-137">Lync Server コントロールパネルにサインインするには、CsAdministrator グループのメンバーであるドメインアカウントを使用するか、委任されたユーザー権限とアクセス許可を持つアカウントを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ac905-137">You must sign in to Lync Server Control Panel either by using a domain account that is a member of the CsAdministrator group or by using an account to which you have delegated user rights and permissions.</span></span> <span data-ttu-id="ac905-138">ローカルコンピューターのアカウントを使用して Lync Server コントロールパネルにサインインすることはできません。</span><span class="sxs-lookup"><span data-stu-id="ac905-138">You cannot sign in to Lync Server Control Panel by using a local machine account.</span></span> <span data-ttu-id="ac905-139">役割ベースのアクセス制御 (RBAC) による管理タスクの委任の詳細については、「計画」のドキュメントの「 [Lync Server 2013 での役割ベースのアクセス制御の計画](lync-server-2013-planning-for-role-based-access-control.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ac905-139">For details about delegating administrative tasks through role-based access control (RBAC), see [Planning for role-based access control in Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md) in the Planning documentation.</span></span>

<span data-ttu-id="ac905-140">簡単な URL を使用して Lync Server コントロールパネルにアクセスする場合は、web サーバーが RTCUniversalServerAdmins および RTCUniversalUserAdmins グループに追加されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="ac905-140">If you use a simple URL to access Lync Server Control Panel, ensure that web servers are added to the RTCUniversalServerAdmins and RTCUniversalUserAdmins groups.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ac905-141">関連項目</span><span class="sxs-lookup"><span data-stu-id="ac905-141">See Also</span></span>


[<span data-ttu-id="ac905-142">Lync Server 2013 管理ツール</span><span class="sxs-lookup"><span data-stu-id="ac905-142">Lync Server 2013 administrative tools</span></span>](lync-server-2013-lync-server-administrative-tools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

