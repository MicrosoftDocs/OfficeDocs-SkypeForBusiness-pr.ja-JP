---
title: 新しい接続を禁止する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: ''
ms.openlocfilehash: c2df1c491384f8a248f70b67880511a2d496c173
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817456"
---
# <a name="preventing-new-connections-to-skype-for-business-server-for-server-maintenance"></a><span data-ttu-id="95d94-102">サーバーメンテナンスのための Skype for Business Server への新しい接続を禁止する</span><span class="sxs-lookup"><span data-stu-id="95d94-102">Preventing new connections to Skype for Business Server for server maintenance</span></span>


<span data-ttu-id="95d94-103">Skype for Business Server を使用すると、サービスが失われることなく、サーバーをオフラインにして (ソフトウェアやハードウェアのアップグレードを適用するなど) することができます。</span><span class="sxs-lookup"><span data-stu-id="95d94-103">Skype for Business Server enables you to take a server offline (for example, to apply software or hardware upgrades) without any loss of service to users.</span></span>

<span data-ttu-id="95d94-104">プール内のサーバーへの新しい接続または呼び出しを禁止するオプションを指定すると、このオプションを実装するとすぐに、新しい接続と通話の取得が停止されます。</span><span class="sxs-lookup"><span data-stu-id="95d94-104">When you specify the option to prevent new connections or calls to a server in a pool, it stops taking any new connections and calls as soon as you implement this option.</span></span> <span data-ttu-id="95d94-105">これらの新しい接続と通話は、プール内の他のサーバーを経由してルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="95d94-105">These new connections and calls are routed through other servers in the pool.</span></span> <span data-ttu-id="95d94-106">新しい接続を禁止しているサーバーでは、既存の接続に対するセッションは自然に終了するまで続行されます。</span><span class="sxs-lookup"><span data-stu-id="95d94-106">A server that is preventing new connections allows its sessions on existing connections to continue until they naturally end.</span></span> <span data-ttu-id="95d94-107">既存のすべてのセッションが終了したら、サーバーをオフラインにすることができます。</span><span class="sxs-lookup"><span data-stu-id="95d94-107">When all existing sessions have ended, the server is ready to be taken offline.</span></span>

<span data-ttu-id="95d94-108">フロントエンドサーバーへの新しい接続を禁止する場合、一部の Skype for Business Server の機能とサービスは、適切に動作するように DNS の負荷分散を利用します。</span><span class="sxs-lookup"><span data-stu-id="95d94-108">When you prevent new connections to a Front End Server, some Skype for Business Server features and services rely on DNS load balancing to ensure that it functions properly.</span></span> <span data-ttu-id="95d94-109">プールで DNS の負荷分散を使用していない場合、サーバーが新しい接続を妨害している期間中、これらのサービスからの接続が他のサーバーに再ルーティングされないことがあります。そのため、サーバーがオフラインになったときに、一部のセッションと通話がまし.</span><span class="sxs-lookup"><span data-stu-id="95d94-109">If you are not using DNS load balancing on the pool, connections through these services may not be re-routed to other servers during the period that the server is preventing new connections, and thus when the server is taken offline some sessions and calls may be interrupted.</span></span> <span data-ttu-id="95d94-110">このオプションが適切に動作するように、DNS の負荷分散に依存する機能は次のように動作します。</span><span class="sxs-lookup"><span data-stu-id="95d94-110">The features that rely on DNS load balancing to ensure that this option operates properly are as follows:</span></span>

  - <span data-ttu-id="95d94-111">Attendant</span><span class="sxs-lookup"><span data-stu-id="95d94-111">Attendant</span></span>

  - <span data-ttu-id="95d94-112">会議アナウンス アプリケーション</span><span class="sxs-lookup"><span data-stu-id="95d94-112">Conferencing Announcement application</span></span>

  - <span data-ttu-id="95d94-113">応答グループ アプリケーション</span><span class="sxs-lookup"><span data-stu-id="95d94-113">Response Group application</span></span>

  - <span data-ttu-id="95d94-114">アナウンス アプリケーション</span><span class="sxs-lookup"><span data-stu-id="95d94-114">Announcement application</span></span>

  - <span data-ttu-id="95d94-115">コール パーク アプリケーション</span><span class="sxs-lookup"><span data-stu-id="95d94-115">Call Park application</span></span>

<span data-ttu-id="95d94-116">DNS 負荷分散の詳細については、「[負荷分散の要件](../../plan-your-deployment/network-requirements/load-balancing.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="95d94-116">For details about DNS load balancing, see [Load balancing requirements](../../plan-your-deployment/network-requirements/load-balancing.md).</span></span>

<span data-ttu-id="95d94-117">Skype for Business Server を実行しているサーバー上のすべてのサービスの新しい接続を防止するだけでなく、個々の Skype for Business Server サービスへの新しい接続を防ぐこともできます。</span><span class="sxs-lookup"><span data-stu-id="95d94-117">In addition to preventing new connections for all services on a server running Skype for Business Server, you can also prevent new connections for individual Skype for Business Server services.</span></span> <span data-ttu-id="95d94-118">たとえば、この方法は、サーバー全体をシャットダウンする必要がない Skype for Business Server の更新プログラムを適用する必要がある場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="95d94-118">For example, this method is useful in a situation where you need to apply a Skype for Business Server update that does not require the whole server to be shut down.</span></span> <span data-ttu-id="95d94-119">1つのサービスに対する接続を禁止する場合は、サービスがグループ化され、サービスの一覧に表示されるサービスを選択する必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="95d94-119">Note that when you prevent connections for one service, you must select a service as it is grouped and displayed in the Windows list of services.</span></span> <span data-ttu-id="95d94-120">たとえば、Skype for Business Server のフロントエンドサービスと監視用のデータ収集エージェントは、別々の Skype for Business Server サービスですが、Windows services のリストで統合され、Skype for Business Server のフロントエンドとして表示されます。サービス.</span><span class="sxs-lookup"><span data-stu-id="95d94-120">For example, the Skype for Business Server Front-End service and the data collection agent for Monitoring are separate Skype for Business Server services, but in the Windows services list they are consolidated and shown as the Skype for Business Server Front End service.</span></span> <span data-ttu-id="95d94-121">Skype for Business Server のフロントエンドサービスへの新しい接続を禁止することはできますが、これらの2つの個別の Skype for Business Server サービスへの新しい接続を個別に禁止することはできません。</span><span class="sxs-lookup"><span data-stu-id="95d94-121">You can prevent new connections for the Skype for Business Server Front End service, but you cannot prevent new connections for these two individual underlying Skype for Business Server services separately.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="95d94-122">新しい接続を禁止するようにサーバーを設定してから、サーバーを再起動すると、既定では、サーバーは起動後に新しい接続の受け入れを直します。</span><span class="sxs-lookup"><span data-stu-id="95d94-122">When you set a server to prevent new connections, and then restart the server, by default the server will immediately begin accepting new connections after it starts.</span></span> <span data-ttu-id="95d94-123">これを防ぐには、サーバーを再起動する前に、手動で一時停止および再開するようにサーバーを設定します。</span><span class="sxs-lookup"><span data-stu-id="95d94-123">To prevent this, set the server to only pause and resume manually, before you restart the server.</span></span>

## <a name="to-prevent-new-connections-to-skype-for-business-server"></a><span data-ttu-id="95d94-124">Skype for Business Server への新しい接続を禁止するには</span><span class="sxs-lookup"><span data-stu-id="95d94-124">To prevent new connections to Skype for Business Server</span></span>

1.  <span data-ttu-id="95d94-125">Administrators グループのメンバーとして、ローカル コンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="95d94-125">Log on to the local computer as a member of the Administrators group.</span></span>

2.  <span data-ttu-id="95d94-126">[サービス] スナップインコンソールを開きます。 [**スタート**] をクリックし、[**すべてのプログラム**] をポイントして、[**管理ツール**] をポイントし、[**サービス**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="95d94-126">Open the Services snap-in console: Click **Start**, point to **All Programs**, point to **Administrative Tools**, and then click **Services**.</span></span>

3.  <span data-ttu-id="95d94-127">リストで、新しい接続を禁止する Skype for Business Server Windows サービスをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="95d94-127">In the list, double-click the Skype for Business Server Windows service to which you want to prevent new connections.</span></span>

4.  <span data-ttu-id="95d94-128">[プロパティ] ダイアログボックスの [**サービスの状態: 開始**] で、[**一時停止**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="95d94-128">In the Properties dialog box, under **Service status: Started**, click **Pause**.</span></span>

5.  <span data-ttu-id="95d94-129">必要に応じて、[**スタートアップの種類**] の横にある [**手動**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="95d94-129">Optionally, but recommended, next to **Startup type**, click **Manual**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="95d94-130">新しい接続を禁止するようにサーバーを設定してから、サーバーを再起動すると、既定では、サーバーは起動後に新しい接続の受け入れを直します。</span><span class="sxs-lookup"><span data-stu-id="95d94-130">When you set a server to prevent new connections, and then restart the server, by default the server will immediately begin accepting new connections after it starts.</span></span> <span data-ttu-id="95d94-131">これを防ぐには、サーバーを再起動する前に、手動で一時停止および再開するようにサーバーを設定します。</span><span class="sxs-lookup"><span data-stu-id="95d94-131">To prevent this, set the server to only pause and resume manually, before you restart the server.</span></span>
