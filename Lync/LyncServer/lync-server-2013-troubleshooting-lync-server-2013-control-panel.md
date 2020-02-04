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
ms.openlocfilehash: ff82a1e63a064d0053fc77614d6a9b5fa818c23e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745017"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="troubleshooting-lync-server-2013-control-panel"></a><span data-ttu-id="f779b-102">Lync Server 2013 コントロールパネルのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="f779b-102">Troubleshooting Lync Server 2013 Control Panel</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f779b-103">_**最終更新日:** 2016-07-28_</span><span class="sxs-lookup"><span data-stu-id="f779b-103">_**Topic Last Modified:** 2016-07-28_</span></span>

<span data-ttu-id="f779b-104">このトピックでは、Lync Server 2013 コントロールパネルへのアクセスのトラブルシューティングに役立つ情報と手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="f779b-104">This topic provides information and procedures that can help you troubleshoot access to Lync Server 2013 Control Panel.</span></span>

<div>

## <a name="internet-browser-requirements"></a><span data-ttu-id="f779b-105">インターネットブラウザーの要件</span><span class="sxs-lookup"><span data-stu-id="f779b-105">Internet Browser Requirements</span></span>

<span data-ttu-id="f779b-106">Lync Server コントロールパネルでは、Microsoft Silverlight ブラウザープラグインバージョン4.0.50524.0 または最新バージョンがインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="f779b-106">Lync Server Control Panel requires that Microsoft Silverlight browser plug-in version 4.0.50524.0 or latest version is installed.</span></span> <span data-ttu-id="f779b-107">Silverlight がインストールされていない場合、または以前のバージョンがインストールされている場合は、メッセージの指示に従って必要なバージョンをインストールします。</span><span class="sxs-lookup"><span data-stu-id="f779b-107">If Silverlight is not installed or if an earlier version is installed, follow the instructions in the message to install the required version.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f779b-108">Lync Server コントロールパネルのその他のソフトウェア要件は、Lync Server コントロールパネルとその他のすべての Lync Server 2013 管理ツールをインストールできるオペレーティングシステムに関連しています。</span><span class="sxs-lookup"><span data-stu-id="f779b-108">Other software requirements for Lync Server Control Panel pertain to the operating system on which Lync Server Control Panel and all other Lync Server 2013 administrative tools can be installed.</span></span> <span data-ttu-id="f779b-109">詳細については、サポートドキュメントの「 <A href="lync-server-2013-server-and-tools-operating-system-support.md">Lync server 2013 でのサーバーとツールのオペレーティングシステムのサポート</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f779b-109">For details, see <A href="lync-server-2013-server-and-tools-operating-system-support.md">Server and tools operating system support in Lync Server 2013</A> in the Supportability documentation.</span></span>



</div>

<span data-ttu-id="f779b-110">セキュリティ上の理由により、インターネットブラウザーで Silverlight のインストールがブロックされている場合は、[Lync Server] コントロールパネルを開くための Uniform Resource Locator (URL) を信頼済みサイトの一覧に追加します。</span><span class="sxs-lookup"><span data-stu-id="f779b-110">If your Internet browser blocks installation of Silverlight due to security considerations, add the Uniform Resource Locator (URL) that opens Lync Server Control Panel to the list of trusted sites.</span></span> <span data-ttu-id="f779b-111">Internet Explorer の [セキュリティ設定] で、[ **ActiveX コントロールとプラグインの実行**] が [**有効**] に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="f779b-111">In Internet Explorer security settings, ensure that **Run ActiveX controls and plug-ins** is set to **Enabled**.</span></span> <span data-ttu-id="f779b-112">詳細について[http://go.microsoft.com/fwlink/p/?linkId=214060](http://go.microsoft.com/fwlink/p/?linkid=214060)は、を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f779b-112">For details, see [http://go.microsoft.com/fwlink/p/?linkId=214060](http://go.microsoft.com/fwlink/p/?linkid=214060).</span></span> <span data-ttu-id="f779b-113">さらに、ブラウザーが SSL 3.0 を使用するように構成されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="f779b-113">Furthermore, ensure that the browser is configured to use SSL 3.0.</span></span>

<span data-ttu-id="f779b-114">インターネットブラウザーがプロキシサーバーを使用するように構成されている場合は、内部サイトとして自動的に検出されるサイトのプロキシサーバーを経由しないようにブラウザーが構成されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="f779b-114">If the Internet browser is configured to use a proxy server, verify that the browser is configured to bypass the proxy server for sites that are automatically detected as internal sites.</span></span> <span data-ttu-id="f779b-115">または、プロキシサーバーの構成設定で、ブラウザーの例外リストにアドレスを追加します。</span><span class="sxs-lookup"><span data-stu-id="f779b-115">Or, add the address to the browser's exception list in the proxy server configuration settings.</span></span>

</div>

<div>

## <a name="dns-record-and-certificate-requirements-for-the-administrative-access-url"></a><span data-ttu-id="f779b-116">管理アクセス URL の DNS レコードと証明書の要件</span><span class="sxs-lookup"><span data-stu-id="f779b-116">DNS Record and Certificate Requirements for the Administrative Access URL</span></span>

<span data-ttu-id="f779b-117">Lync Server コントロールパネルにアクセスするための単純な URL を構成している場合は、その管理アクセス URL を使用するために必要な静的ドメインネームシステム (DNS) のリソースレコードと証明書も構成していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="f779b-117">If you configured a simple URL to access Lync Server Control Panel, ensure that you also configured the static Domain Name System (DNS) host (A) resource record and certificate necessary to use that administrative access URL.</span></span> <span data-ttu-id="f779b-118">ベース URL をいつでも変更する場合は、適切な DNS レコードと証明書に変更が反映されていることを確認します。また、各ディレクターとフロントエンドサーバー上のユーザーがこの変更を登録*するように*します。</span><span class="sxs-lookup"><span data-stu-id="f779b-118">If you change the base URL at any time, ensure that the change is reflected in the appropriate DNS record and certificate and that you run the *Enable-CsComputer* on each Director and Front End Server to register the change.</span></span> <span data-ttu-id="f779b-119">詳細については、計画ドキュメントの次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f779b-119">For details, see the following topics in the Planning documentation:</span></span>

  - [<span data-ttu-id="f779b-120">Lync Server 2013 での簡単な URL の計画</span><span class="sxs-lookup"><span data-stu-id="f779b-120">Planning for simple URLs in Lync Server 2013</span></span>](lync-server-2013-planning-for-simple-urls.md)

  - [<span data-ttu-id="f779b-121">Lync Server 2013 の簡易 URL の DNS 要件</span><span class="sxs-lookup"><span data-stu-id="f779b-121">DNS requirements for simple URLs in Lync Server 2013</span></span>](lync-server-2013-dns-requirements-for-simple-urls.md)

  - [<span data-ttu-id="f779b-122">Lync Server 2013 の内部サーバーに対する証明書要件</span><span class="sxs-lookup"><span data-stu-id="f779b-122">Certificate requirements for internal servers in Lync Server 2013</span></span>](lync-server-2013-certificate-requirements-for-internal-servers.md)

<span data-ttu-id="f779b-123">管理アクセス URL を構成するための詳しい手順については、展開ドキュメントの「 [Lync Server 2013 での単純な url の編集または構成](lync-server-2013-edit-or-configure-simple-urls.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f779b-123">For step-by-step procedures to configure the administrative access URL, see [Edit or configure simple URLs in Lync Server 2013](lync-server-2013-edit-or-configure-simple-urls.md) in the Deployment documentation.</span></span>

</div>

<div>

## <a name="internet-information-services-iis-requirements"></a><span data-ttu-id="f779b-124">インターネットインフォメーションサービス (IIS) の要件</span><span class="sxs-lookup"><span data-stu-id="f779b-124">Internet Information Services (IIS) Requirements</span></span>

<span data-ttu-id="f779b-125">Lync Server コントロールパネルは、インターネットインフォメーションサービス (IIS) を必要とする、Lync Server 2013 のコンポーネントの1つです。</span><span class="sxs-lookup"><span data-stu-id="f779b-125">Lync Server Control Panel is one of the components of Lync Server 2013 that requires Internet Information Services (IIS).</span></span> <span data-ttu-id="f779b-126">特に、HTTP リダイレクションと Windows 認証機能が有効であり、World Wide Web 発行サービス (W3SVC) が実行されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="f779b-126">In particular, ensure that HTTP redirection and Windows authentication features are enabled, and that the World Wide Web Publishing Service (W3SVC) is running.</span></span>

<div>

## <a name="world-wide-publishing-service-windows-service-dependency"></a><span data-ttu-id="f779b-127">World Wide 発行サービス (Windows サービス) の依存関係</span><span class="sxs-lookup"><span data-stu-id="f779b-127">World Wide Publishing Service (Windows Service) Dependency</span></span>

<span data-ttu-id="f779b-128">World Wide Web 発行サービスが停止すると、Lync Server コントロールパネルにアクセスできなくなります。</span><span class="sxs-lookup"><span data-stu-id="f779b-128">When the World Wide Web Publishing Service is stopped, you cannot access Lync Server Control Panel.</span></span> <span data-ttu-id="f779b-129">Windows Services Microsoft 管理コンソール (MMC) を使用してサービスを再起動することができます。</span><span class="sxs-lookup"><span data-stu-id="f779b-129">You can restart the service by using the Windows Services Microsoft Management Console (MMC).</span></span>

<span data-ttu-id="f779b-130">**World Wide Web 発行サービスを開始するには**</span><span class="sxs-lookup"><span data-stu-id="f779b-130">**To start the World Wide Web Publishing Service**</span></span>

1.  <span data-ttu-id="f779b-131">World Wide Web 発行サービスがインターネットインフォメーションサービス (IIS) の一部としてインストールされているコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="f779b-131">Log on to the computer where the World Wide Web Publishing Service is installed as part of Internet Information Services (IIS).</span></span>

2.  <span data-ttu-id="f779b-132">[**スタート**] をクリックし、[**管理ツール**] をクリックして、[**サービス**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f779b-132">Click **Start**, click **Administrative Tools**, and then click **Services**.</span></span>

3.  <span data-ttu-id="f779b-133">[ **World Wide Web 発行サービス**] を右クリックし、[**開始**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f779b-133">Right-click **World Wide Web Publishing Service**, and then click **Start**.</span></span>

</div>

<div>

## <a name="application-pool-mode"></a><span data-ttu-id="f779b-134">アプリケーションプールモード</span><span class="sxs-lookup"><span data-stu-id="f779b-134">Application Pool Mode</span></span>

<span data-ttu-id="f779b-135">CsManagementAppPool アプリケーションプールがプロセスモデル id としてネットワークサービスアカウントを使用できるように IIS を構成します。</span><span class="sxs-lookup"><span data-stu-id="f779b-135">Configure IIS so that the CsManagementAppPool application pool uses the Network Service account as its process model identity.</span></span>

</div>

</div>

<div>

## <a name="user-rights-and-permissions"></a><span data-ttu-id="f779b-136">ユーザー権利と権限</span><span class="sxs-lookup"><span data-stu-id="f779b-136">User Rights and Permissions</span></span>

<span data-ttu-id="f779b-137">CsAdministrator グループのメンバーであるドメインアカウントを使用するか、ユーザー権利と権限を委任しているアカウントを使用して、Lync Server コントロールパネルにサインインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f779b-137">You must sign in to Lync Server Control Panel either by using a domain account that is a member of the CsAdministrator group or by using an account to which you have delegated user rights and permissions.</span></span> <span data-ttu-id="f779b-138">ローカルコンピューターアカウントを使用して、Lync Server コントロールパネルにサインインすることはできません。</span><span class="sxs-lookup"><span data-stu-id="f779b-138">You cannot sign in to Lync Server Control Panel by using a local machine account.</span></span> <span data-ttu-id="f779b-139">ロールベースのアクセス制御 (RBAC) による管理タスクの委任について詳しくは、計画ドキュメントの「 [Lync Server 2013 での役割ベースのアクセス制御の計画](lync-server-2013-planning-for-role-based-access-control.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="f779b-139">For details about delegating administrative tasks through role-based access control (RBAC), see [Planning for role-based access control in Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md) in the Planning documentation.</span></span>

<span data-ttu-id="f779b-140">簡単な URL を使用して Lync Server コントロールパネルにアクセスする場合は、web サーバーが RTCUniversalServerAdmins グループと RTCUniversalUserAdmins グループに追加されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="f779b-140">If you use a simple URL to access Lync Server Control Panel, ensure that web servers are added to the RTCUniversalServerAdmins and RTCUniversalUserAdmins groups.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f779b-141">関連項目</span><span class="sxs-lookup"><span data-stu-id="f779b-141">See Also</span></span>


[<span data-ttu-id="f779b-142">Lync Server 2013 管理ツール</span><span class="sxs-lookup"><span data-stu-id="f779b-142">Lync Server 2013 administrative tools</span></span>](lync-server-2013-lync-server-administrative-tools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

