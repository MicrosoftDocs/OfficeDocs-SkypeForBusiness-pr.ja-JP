---
title: 新しい接続を防止します。
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: ''
ms.openlocfilehash: bc9b4a1e7d6e17f09643ff14ac0e69261c326922
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32199021"
---
# <a name="preventing-new-connections-to-skype-for-business-server-for-server-maintenance"></a><span data-ttu-id="db6b4-102">サーバー メンテナンスのためサーバーのビジネスの Skype への新しい接続を防止します。</span><span class="sxs-lookup"><span data-stu-id="db6b4-102">Preventing new connections to Skype for Business Server for server maintenance</span></span>


<span data-ttu-id="db6b4-103">ビジネス サーバーの Skype では、ユーザーにサービスを損なうことがなく (たとえば、ソフトウェアまたはハードウェアのアップグレードを適用する場合) サーバーをオフラインにできます。</span><span class="sxs-lookup"><span data-stu-id="db6b4-103">Skype for Business Server enables you to take a server offline (for example, to apply software or hardware upgrades) without any loss of service to users.</span></span>

<span data-ttu-id="db6b4-104">新しい接続またはプール内のサーバーへの呼び出しを防止するオプションを指定すると、このオプションを実装するとすぐに、すべての新しい接続および呼び出しを実行を停止します。</span><span class="sxs-lookup"><span data-stu-id="db6b4-104">When you specify the option to prevent new connections or calls to a server in a pool, it stops taking any new connections and calls as soon as you implement this option.</span></span> <span data-ttu-id="db6b4-105">これらの新しい接続および呼び出しは、プール内の他のサーバーを通してルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="db6b4-105">These new connections and calls are routed through other servers in the pool.</span></span> <span data-ttu-id="db6b4-106">新しい接続を妨げているサーバーでは、必然的に終了するまで続行するのには既存の接続上のセッションを許可します。</span><span class="sxs-lookup"><span data-stu-id="db6b4-106">A server that is preventing new connections allows its sessions on existing connections to continue until they naturally end.</span></span> <span data-ttu-id="db6b4-107">すべての既存のセッションが終了すると、サーバーが、オフラインにする準備ができました。</span><span class="sxs-lookup"><span data-stu-id="db6b4-107">When all existing sessions have ended, the server is ready to be taken offline.</span></span>

<span data-ttu-id="db6b4-108">サーバーをフロント エンド サーバーへの新しい接続を禁止すると、Business Server の機能およびサービスのいくつかの Skype は、DNS の負荷分散が正しく機能していることを確認するに依存します。</span><span class="sxs-lookup"><span data-stu-id="db6b4-108">When you prevent new connections to a Front End Server, some Skype for Business Server features and services rely on DNS load balancing to ensure that it functions properly.</span></span> <span data-ttu-id="db6b4-109">DNS での負荷分散プールを使用しない場合は、これらのサービス経由で接続できない可能性があります他のサーバーへの再ルーティング サーバーが、新しい接続を拒否されている期間中にこのようにすると、サーバーがオフラインといくつかのセッションや呼び出しがあります中断されました。</span><span class="sxs-lookup"><span data-stu-id="db6b4-109">If you are not using DNS load balancing on the pool, connections through these services may not be re-routed to other servers during the period that the server is preventing new connections, and thus when the server is taken offline some sessions and calls may be interrupted.</span></span> <span data-ttu-id="db6b4-110">このオプションが正常に動作することを確認するのには DNS のロードバランシングを利用する機能は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="db6b4-110">The features that rely on DNS load balancing to ensure that this option operates properly are as follows:</span></span>

  - <span data-ttu-id="db6b4-111">Attendant</span><span class="sxs-lookup"><span data-stu-id="db6b4-111">Attendant</span></span>

  - <span data-ttu-id="db6b4-112">会議アナウンス アプリケーション</span><span class="sxs-lookup"><span data-stu-id="db6b4-112">Conferencing Announcement application</span></span>

  - <span data-ttu-id="db6b4-113">応答グループ アプリケーション</span><span class="sxs-lookup"><span data-stu-id="db6b4-113">Response Group application</span></span>

  - <span data-ttu-id="db6b4-114">アナウンス アプリケーション</span><span class="sxs-lookup"><span data-stu-id="db6b4-114">Announcement application</span></span>

  - <span data-ttu-id="db6b4-115">コール パーク アプリケーション</span><span class="sxs-lookup"><span data-stu-id="db6b4-115">Call Park application</span></span>

<span data-ttu-id="db6b4-116">詳細については、DNS の負荷分散は、[ロード バランシングの要件](../../plan-your-deployment/network-requirements/load-balancing.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="db6b4-116">For details about DNS load balancing, see [Load balancing requirements](../../plan-your-deployment/network-requirements/load-balancing.md).</span></span>

<span data-ttu-id="db6b4-117">ビジネス サーバーの Skype を実行するサーバー上のすべてのサービスの新しい接続を防ぐだけでなくビジネス サーバー サービスの個別の Skype の新しい接続も防止できます。</span><span class="sxs-lookup"><span data-stu-id="db6b4-117">In addition to preventing new connections for all services on a server running Skype for Business Server, you can also prevent new connections for individual Skype for Business Server services.</span></span> <span data-ttu-id="db6b4-118">たとえば、このメソッドは、サーバー全体をシャット ダウンを必要としないビジネス サーバー更新のため、Skype を適用する必要がある場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="db6b4-118">For example, this method is useful in a situation where you need to apply a Skype for Business Server update that does not require the whole server to be shut down.</span></span> <span data-ttu-id="db6b4-119">1 つのサービスに対して接続を禁止するとする必要がありますサービスを選択する、グループ化およびサービスの Windows の一覧に表示される注意してください。</span><span class="sxs-lookup"><span data-stu-id="db6b4-119">Note that when you prevent connections for one service, you must select a service as it is grouped and displayed in the Windows list of services.</span></span> <span data-ttu-id="db6b4-120">たとえば、ビジネス サーバーのフロント エンド サービスの Skype とデータ収集エージェントの監視をビジネスのサーバー サービスでは、別の Skype が Windows サービスの一覧で、統合、ビジネス サーバーのフロント エンドとして、Skype 表示サービスです。</span><span class="sxs-lookup"><span data-stu-id="db6b4-120">For example, the Skype for Business Server Front-End service and the data collection agent for Monitoring are separate Skype for Business Server services, but in the Windows services list they are consolidated and shown as the Skype for Business Server Front End service.</span></span> <span data-ttu-id="db6b4-121">ビジネス サーバーのフロント エンド サービスでは、Skype の新しい接続を防ぐことができますが、個別のビジネス サービスのこれら 2 つそれぞれ基になる Skype の新しい接続を防ぐことはできません。</span><span class="sxs-lookup"><span data-stu-id="db6b4-121">You can prevent new connections for the Skype for Business Server Front End service, but you cannot prevent new connections for these two individual underlying Skype for Business Server services separately.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="db6b4-122">、新しい接続を防止し、サーバーを再起動するサーバーを設定すると、既定でサーバーがすぐに開始後は、新しい接続を受け入れることです。</span><span class="sxs-lookup"><span data-stu-id="db6b4-122">When you set a server to prevent new connections, and then restart the server, by default the server will immediately begin accepting new connections after it starts.</span></span> <span data-ttu-id="db6b4-123">これを防止するには、のみを一時停止し、サーバーを再起動する前に手動で再開するサーバーを設定します。</span><span class="sxs-lookup"><span data-stu-id="db6b4-123">To prevent this, set the server to only pause and resume manually, before you restart the server.</span></span>

## <a name="to-prevent-new-connections-to-skype-for-business-server"></a><span data-ttu-id="db6b4-124">Skype をビジネスのサーバー用の新しい接続を禁止するには</span><span class="sxs-lookup"><span data-stu-id="db6b4-124">To prevent new connections to Skype for Business Server</span></span>

1.  <span data-ttu-id="db6b4-125">Administrators グループのメンバーとして、ローカル コンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="db6b4-125">Log on to the local computer as a member of the Administrators group.</span></span>

2.  <span data-ttu-id="db6b4-126">サービス スナップイン コンソールを開きます。 [**スタート**] ボタン**すべてのプログラム**] をポイント、 **[管理ツール**] をポイント、し、[**サービス**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="db6b4-126">Open the Services snap-in console: Click **Start**, point to **All Programs**, point to **Administrative Tools**, and then click **Services**.</span></span>

3.  <span data-ttu-id="db6b4-127">一覧で、新しい接続を防止する Windows サーバーのビジネス サービスの Skype をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="db6b4-127">In the list, double-click the Skype for Business Server Windows service to which you want to prevent new connections.</span></span>

4.  <span data-ttu-id="db6b4-128">プロパティ] ダイアログ ボックスで [**サービスの状態: 開始**、[**一時停止**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="db6b4-128">In the Properties dialog box, under **Service status: Started**, click **Pause**.</span></span>

5.  <span data-ttu-id="db6b4-129">必要に応じて、推奨、**スタートアップの種類**] の横をクリックして**手動**です。</span><span class="sxs-lookup"><span data-stu-id="db6b4-129">Optionally, but recommended, next to **Startup type**, click **Manual**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="db6b4-130">、新しい接続を防止し、サーバーを再起動するサーバーを設定すると、既定でサーバーがすぐに開始後は、新しい接続を受け入れることです。</span><span class="sxs-lookup"><span data-stu-id="db6b4-130">When you set a server to prevent new connections, and then restart the server, by default the server will immediately begin accepting new connections after it starts.</span></span> <span data-ttu-id="db6b4-131">これを防止するには、のみを一時停止し、サーバーを再起動する前に手動で再開するサーバーを設定します。</span><span class="sxs-lookup"><span data-stu-id="db6b4-131">To prevent this, set the server to only pause and resume manually, before you restart the server.</span></span>
