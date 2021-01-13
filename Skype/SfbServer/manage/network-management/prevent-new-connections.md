---
title: 新しい接続の防止
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: ''
ms.openlocfilehash: 3f2ca560f934f5b907d05a1f768a0cadd8435f2a
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823467"
---
# <a name="preventing-new-connections-to-skype-for-business-server-for-server-maintenance"></a><span data-ttu-id="b5f05-102">サーバーメンテナンスのために Skype for Business Server への新しい接続を防止する</span><span class="sxs-lookup"><span data-stu-id="b5f05-102">Preventing new connections to Skype for Business Server for server maintenance</span></span>


<span data-ttu-id="b5f05-103">Skype for Business Server を使用すると、ユーザーにサービスを失わずにサーバーをオフラインにできます (ソフトウェアやハードウェアのアップグレードを適用する場合など)。</span><span class="sxs-lookup"><span data-stu-id="b5f05-103">Skype for Business Server enables you to take a server offline (for example, to apply software or hardware upgrades) without any loss of service to users.</span></span>

<span data-ttu-id="b5f05-p101">プール内でサーバーへの新規接続および呼び出しを禁止するオプションを指定した場合、このオプションを実装するとすぐに新規接続および呼び出しを受け付けなくなります。これら新規の接続および呼び出しは、プール内の他のサーバーを介してルーティングされます。新規接続を禁止しているサーバーでは、既存の接続上のセッションは自然に終了するまで続行することができます。既存のセッションがすべて終了すると、サーバーをオフラインにすることができます。</span><span class="sxs-lookup"><span data-stu-id="b5f05-p101">When you specify the option to prevent new connections or calls to a server in a pool, it stops taking any new connections and calls as soon as you implement this option. These new connections and calls are routed through other servers in the pool. A server that is preventing new connections allows its sessions on existing connections to continue until they naturally end. When all existing sessions have ended, the server is ready to be taken offline.</span></span>

<span data-ttu-id="b5f05-108">フロント エンド サーバーへの新しい接続を防ぐ場合、Skype for Business Server の一部の機能とサービスは DNS 負荷分散に依存して正しく機能します。</span><span class="sxs-lookup"><span data-stu-id="b5f05-108">When you prevent new connections to a Front End Server, some Skype for Business Server features and services rely on DNS load balancing to ensure that it functions properly.</span></span> <span data-ttu-id="b5f05-109">プール内で DNS 負荷分散を使用していない場合、サーバーが新規接続を禁止している間、これらのサービスを介する接続はその他のサーバーに再ルーティングされない可能性があり、結果、サーバーがオフラインになる時、一部のセッションおよび通話が中断される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b5f05-109">If you are not using DNS load balancing on the pool, connections through these services may not be re-routed to other servers during the period that the server is preventing new connections, and thus when the server is taken offline some sessions and calls may be interrupted.</span></span> <span data-ttu-id="b5f05-110">このオプションを確実に正しく動作させるために DNS 負荷分散を使用する機能は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="b5f05-110">The features that rely on DNS load balancing to ensure that this option operates properly are as follows:</span></span>

  - <span data-ttu-id="b5f05-111">Attendant</span><span class="sxs-lookup"><span data-stu-id="b5f05-111">Attendant</span></span>

  - <span data-ttu-id="b5f05-112">会議アナウンス アプリケーション</span><span class="sxs-lookup"><span data-stu-id="b5f05-112">Conferencing Announcement application</span></span>

  - <span data-ttu-id="b5f05-113">応答グループ アプリケーション</span><span class="sxs-lookup"><span data-stu-id="b5f05-113">Response Group application</span></span>

  - <span data-ttu-id="b5f05-114">アナウンス アプリケーション</span><span class="sxs-lookup"><span data-stu-id="b5f05-114">Announcement application</span></span>

  - <span data-ttu-id="b5f05-115">コール パーク アプリケーション</span><span class="sxs-lookup"><span data-stu-id="b5f05-115">Call Park application</span></span>

<span data-ttu-id="b5f05-116">DNS 負荷分散の詳細については、「負荷分散の要件 [」を参照してください](../../plan-your-deployment/network-requirements/load-balancing.md)。</span><span class="sxs-lookup"><span data-stu-id="b5f05-116">For details about DNS load balancing, see [Load balancing requirements](../../plan-your-deployment/network-requirements/load-balancing.md).</span></span>

<span data-ttu-id="b5f05-117">Skype for Business Server を実行しているサーバー上のすべてのサービスに対して新しい接続を防止できるだけでなく、個々の Skype for Business Server サービスに対する新しい接続を防止することもできます。</span><span class="sxs-lookup"><span data-stu-id="b5f05-117">In addition to preventing new connections for all services on a server running Skype for Business Server, you can also prevent new connections for individual Skype for Business Server services.</span></span> <span data-ttu-id="b5f05-118">たとえば、このメソッドは、サーバー全体のシャットダウンを必要としない Skype for Business Server 更新プログラムを適用する必要がある場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="b5f05-118">For example, this method is useful in a situation where you need to apply a Skype for Business Server update that does not require the whole server to be shut down.</span></span> <span data-ttu-id="b5f05-119">1 つのサービスに対して接続を禁止する場合、Windows のサービス一覧でグループ化され、表示されるサービスを選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b5f05-119">Note that when you prevent connections for one service, you must select a service as it is grouped and displayed in the Windows list of services.</span></span> <span data-ttu-id="b5f05-120">たとえば、Skype for Business Server Front-End サービスと監視用のデータ収集エージェントは個別の Skype for Business Server サービスですが、Windows サービスの一覧では、これらは統合され、Skype for Business Server フロントエンド サービスとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="b5f05-120">For example, the Skype for Business Server Front-End service and the data collection agent for Monitoring are separate Skype for Business Server services, but in the Windows services list they are consolidated and shown as the Skype for Business Server Front End service.</span></span> <span data-ttu-id="b5f05-121">Skype for Business Server フロント エンド サービスの新しい接続を防止できますが、これら 2 つの個別の基礎となる Skype for Business Server サービスに対する新しい接続を個別に防止することはできません。</span><span class="sxs-lookup"><span data-stu-id="b5f05-121">You can prevent new connections for the Skype for Business Server Front End service, but you cannot prevent new connections for these two individual underlying Skype for Business Server services separately.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b5f05-p104">新規接続を禁止するようにサーバーを設定しても、その後にサーバーを再起動すると、既定では、起動後すぐに新規接続の受け入れが開始されます。これを回避するために、サーバーを一時停止するだけに留め、サーバーを再起動する前に手動で再開します。</span><span class="sxs-lookup"><span data-stu-id="b5f05-p104">When you set a server to prevent new connections, and then restart the server, by default the server will immediately begin accepting new connections after it starts. To prevent this, set the server to only pause and resume manually, before you restart the server.</span></span>

## <a name="to-prevent-new-connections-to-skype-for-business-server"></a><span data-ttu-id="b5f05-124">Skype for Business Server への新しい接続を防止するには</span><span class="sxs-lookup"><span data-stu-id="b5f05-124">To prevent new connections to Skype for Business Server</span></span>

1.  <span data-ttu-id="b5f05-125">Administrators グループのメンバーとして、ローカル コンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="b5f05-125">Log on to the local computer as a member of the Administrators group.</span></span>

2.  <span data-ttu-id="b5f05-126">サービス スナップイン コンソールを開きます **。[スタート**]ボタンをクリックし、[すべてのプログラム] をポイントし、[管理ツール] をポイントして、[サービス] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="b5f05-126">Open the Services snap-in console: Click **Start**, point to **All Programs**, point to **Administrative Tools**, and then click **Services**.</span></span>

3.  <span data-ttu-id="b5f05-127">一覧で、新しい接続を防止する Skype for Business Server Windows サービスをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="b5f05-127">In the list, double-click the Skype for Business Server Windows service to which you want to prevent new connections.</span></span>

4.  <span data-ttu-id="b5f05-128">[プロパティ] ダイアログ ボックスの [**サービスの状態: 開始**] で、[**一時停止**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b5f05-128">In the Properties dialog box, under **Service status: Started**, click **Pause**.</span></span>

5.  <span data-ttu-id="b5f05-129">オプションですが、[**スタートアップの種類**] の横の [**手動**] をクリックすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="b5f05-129">Optionally, but recommended, next to **Startup type**, click **Manual**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="b5f05-p105">新規接続を禁止するようにサーバーを設定しても、その後にサーバーを再起動すると、既定では、起動後すぐに新規接続の受け入れが開始されます。これを回避するために、サーバーを一時停止するだけに留め、サーバーを再起動する前に手動で再開します。</span><span class="sxs-lookup"><span data-stu-id="b5f05-p105">When you set a server to prevent new connections, and then restart the server, by default the server will immediately begin accepting new connections after it starts. To prevent this, set the server to only pause and resume manually, before you restart the server.</span></span>
