---
title: Lync Server へのサーバーメンテナンスのための新しい接続を禁止する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Prevent new connections to Lync Server for server maintenance
ms:assetid: 22b27adf-a590-43bd-9306-a5789ae108d7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520964(v=OCS.15)
ms:contentKeyID: 48183625
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 06516c3d47a9ec5e491a5a16098dfae334ff4f4e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42139078"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="prevent-new-connections-to-lync-server-2013-for-server-maintenance"></a><span data-ttu-id="ad79f-102">サーバーメンテナンスのための Lync Server 2013 への新しい接続を禁止する</span><span class="sxs-lookup"><span data-stu-id="ad79f-102">Prevent new connections to Lync Server 2013 for server maintenance</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ad79f-103">_**トピックの最終更新日:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="ad79f-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="ad79f-104">Lync Server を使用すると、ユーザーにサービスを損失することなく、サーバーをオフラインにすることができます (たとえば、ソフトウェアまたはハードウェアのアップグレードを適用することができます)。</span><span class="sxs-lookup"><span data-stu-id="ad79f-104">Lync Server enables you to take a server offline (for example, to apply software or hardware upgrades) without any loss of service to users.</span></span>

<span data-ttu-id="ad79f-p101">プール内でサーバーへの新規接続および呼び出しを禁止するオプションを指定した場合、このオプションを実装するとすぐに新規接続および呼び出しを受け付けなくなります。これら新規の接続および呼び出しは、プール内の他のサーバーを介してルーティングされます。新規接続を禁止しているサーバーでは、既存の接続上のセッションは自然に終了するまで続行することができます。既存のセッションがすべて終了すると、サーバーをオフラインにすることができます。</span><span class="sxs-lookup"><span data-stu-id="ad79f-p101">When you specify the option to prevent new connections or calls to a server in a pool, it stops taking any new connections and calls as soon as you implement this option. These new connections and calls are routed through other servers in the pool. A server that is preventing new connections allows its sessions on existing connections to continue until they naturally end. When all existing sessions have ended, the server is ready to be taken offline.</span></span>

<span data-ttu-id="ad79f-109">フロントエンドサーバーへの新しい接続を禁止する場合、一部の Lync Server の機能およびサービスは、DNS 負荷分散を使用して正しく機能することを確認します。</span><span class="sxs-lookup"><span data-stu-id="ad79f-109">When you prevent new connections to a Front End Server, some Lync Server features and services rely on DNS load balancing to ensure that it functions properly.</span></span> <span data-ttu-id="ad79f-110">プール内で DNS 負荷分散を使用していない場合、サーバーが新規接続を禁止している間、これらのサービスを介する接続はその他のサーバーに再ルーティングされない可能性があり、結果、サーバーがオフラインになる時、一部のセッションおよび通話が中断される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ad79f-110">If you are not using DNS load balancing on the pool, connections through these services may not be re-routed to other servers during the period that the server is preventing new connections, and thus when the server is taken offline some sessions and calls may be interrupted.</span></span> <span data-ttu-id="ad79f-111">このオプションを確実に正しく動作させるために DNS 負荷分散を使用する機能は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="ad79f-111">The features that rely on DNS load balancing to ensure that this option operates properly are as follows:</span></span>

  - <span data-ttu-id="ad79f-112">Um</span><span class="sxs-lookup"><span data-stu-id="ad79f-112">Attendant</span></span>

  - <span data-ttu-id="ad79f-113">会議アナウンス アプリケーション</span><span class="sxs-lookup"><span data-stu-id="ad79f-113">Conferencing Announcement application</span></span>

  - <span data-ttu-id="ad79f-114">応答グループ アプリケーション</span><span class="sxs-lookup"><span data-stu-id="ad79f-114">Response Group application</span></span>

  - <span data-ttu-id="ad79f-115">アナウンス アプリケーション</span><span class="sxs-lookup"><span data-stu-id="ad79f-115">Announcement application</span></span>

  - <span data-ttu-id="ad79f-116">コール パーク アプリケーション</span><span class="sxs-lookup"><span data-stu-id="ad79f-116">Call Park application</span></span>

<span data-ttu-id="ad79f-117">DNS 負荷分散の詳細については、「計画」のドキュメントの「 [dns load balancing In Lync Server 2013](lync-server-2013-dns-load-balancing.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ad79f-117">For details about DNS load balancing, see [DNS load balancing in Lync Server 2013](lync-server-2013-dns-load-balancing.md) in the Planning documentation.</span></span>

<span data-ttu-id="ad79f-118">Lync Server を実行しているサーバー上のすべてのサービスの新しい接続を禁止することに加えて、個々の Lync Server サービスの新しい接続を禁止することもできます。</span><span class="sxs-lookup"><span data-stu-id="ad79f-118">In addition to preventing new connections for all services on a server running Lync Server, you can also prevent new connections for individual Lync Server services.</span></span> <span data-ttu-id="ad79f-119">たとえば、このメソッドは、サーバー全体をシャットダウンする必要がない Lync Server 更新プログラムを適用する必要がある場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="ad79f-119">For example, this method is useful in a situation where you need to apply a Lync Server update that does not require the whole server to be shut down.</span></span> <span data-ttu-id="ad79f-120">1 つのサービスに対して接続を禁止する場合、Windows のサービス一覧でグループ化され、表示されるサービスを選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ad79f-120">Note that when you prevent connections for one service, you must select a service as it is grouped and displayed in the Windows list of services.</span></span> <span data-ttu-id="ad79f-121">たとえば、Lync server フロントエンドサービスと監視用のデータ収集エージェントは別個の Lync Server サービスですが、Windows サービスのリストで統合され、Lync Server フロントエンドサービスとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="ad79f-121">For example, the Lync Server Front-End service and the data collection agent for Monitoring are separate Lync Server services, but in the Windows services list they are consolidated and shown as the Lync Server Front End service.</span></span> <span data-ttu-id="ad79f-122">Lync Server フロントエンドサービスの新しい接続を禁止することはできますが、これら2つの基本的な Lync Server サービスの新しい接続を個別に禁止することはできません。</span><span class="sxs-lookup"><span data-stu-id="ad79f-122">You can prevent new connections for the Lync Server Front End service, but you cannot prevent new connections for these two individual underlying Lync Server services separately.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="ad79f-p104">新規接続を禁止するようにサーバーを設定しても、その後にサーバーを再起動すると、既定では、起動後すぐに新規接続の受け入れが開始されます。これを回避するために、サーバーを一時停止するだけに留め、サーバーを再起動する前に手動で再開します。</span><span class="sxs-lookup"><span data-stu-id="ad79f-p104">When you set a server to prevent new connections, and then restart the server, by default the server will immediately begin accepting new connections after it starts. To prevent this, set the server to only pause and resume manually, before you restart the server.</span></span>



</div>

<div>

## <a name="to-prevent-new-connections-to-lync-server"></a><span data-ttu-id="ad79f-125">Lync Server への新しい接続を禁止するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="ad79f-125">To prevent new connections to Lync Server:</span></span>

1.  <span data-ttu-id="ad79f-126">Administrators グループのメンバーとして、ローカル コンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="ad79f-126">Log on to the local computer as a member of the Administrators group.</span></span>

2.  <span data-ttu-id="ad79f-127">[サービス] スナップインコンソールを開きます。 [**スタート**] をクリックし、[**すべてのプログラム**] をポイントします。次に、[**管理ツール**] をポイントし、[**サービス**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ad79f-127">Open the Services snap-in console: Click **Start**, point to **All Programs**, point to **Administrative Tools**, and then click **Services**.</span></span>

3.  <span data-ttu-id="ad79f-128">一覧で、新規接続を禁止する Lync Server Windows サービスをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="ad79f-128">In the list, double-click the Lync Server Windows service to which you want to prevent new connections.</span></span>

4.  <span data-ttu-id="ad79f-129">[プロパティ] ダイアログ ボックスの [**サービスの状態: 開始**] で、[**一時停止**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ad79f-129">In the Properties dialog box, under **Service status: Started**, click **Pause**.</span></span>

5.  <span data-ttu-id="ad79f-130">オプションですが、[**スタートアップの種類**] の横の [**手動**] をクリックすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ad79f-130">Optionally, but recommended, next to **Startup type**, click **Manual**.</span></span>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="ad79f-p105">新規接続を禁止するようにサーバーを設定しても、その後にサーバーを再起動すると、既定では、起動後すぐに新規接続の受け入れが開始されます。これを回避するために、サーバーを一時停止するだけに留め、サーバーを再起動する前に手動で再開します。</span><span class="sxs-lookup"><span data-stu-id="ad79f-p105">When you set a server to prevent new connections, and then restart the server, by default the server will immediately begin accepting new connections after it starts. To prevent this, set the server to only pause and resume manually, before you restart the server.</span></span>

    
    </div>

6.  <span data-ttu-id="ad79f-133">終了したら、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ad79f-133">When you are finished, click **OK**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

