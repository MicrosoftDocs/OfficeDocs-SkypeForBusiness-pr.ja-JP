---
title: Skype for Business Server でのエッジ展開の検証
ms.reviewer: ''
ms.author: v-cichur
author: cichur
audience: ITPro
manager: serdars
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 69837f86-d141-4884-a4ca-c7e7463afaad
description: '概要: エッジ サーバーまたはエッジ サーバー プールの展開が Skype for Business Server で動作しているのを確認する方法について説明します。'
ms.openlocfilehash: 1da2bed1bc9df7cb118d47c2b27e190546838e1b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804357"
---
# <a name="validate-your-edge-deployment-in-skype-for-business-server"></a><span data-ttu-id="fa923-103">Skype for Business Server でのエッジ展開の検証</span><span class="sxs-lookup"><span data-stu-id="fa923-103">Validate your Edge deployment in Skype for Business Server</span></span>
 
<span data-ttu-id="fa923-104">**概要:** エッジ サーバーまたはエッジ サーバー プールの展開が Skype for Business Server で動作しているのを確認する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="fa923-104">**Summary:** Learn how to verify that your deployment of Edge Server or Edge Server pool is working in Skype for Business Server.</span></span>
  
<span data-ttu-id="fa923-105">エッジ サーバーまたはエッジ サーバー プールを展開したら、正常に動作しているかどうか確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fa923-105">Once you've deployed your Edge Server or Edge Server pool, you need to know if it's working properly.</span></span> <span data-ttu-id="fa923-106">ここでは、エッジ環境が内部サーバーに接続されていることを確認するのに役立ついくつかの情報と、外部ユーザーがエッジを介して Skype for Business Server 環境に接続できる方法を示します。</span><span class="sxs-lookup"><span data-stu-id="fa923-106">Here are a couple of things that can help with confirming your Edge environment is connected to your internal servers, and also that your external users can connect to your Skype for Business Server environment through your Edge.</span></span>
  
## <a name="verify-connectivity-between-your-internal-servers-and-your-edge-servers"></a><span data-ttu-id="fa923-107">内部サーバーとエッジ サーバー間の接続を確認する</span><span class="sxs-lookup"><span data-stu-id="fa923-107">Verify connectivity between your internal servers and your Edge servers</span></span>

<span data-ttu-id="fa923-108">エッジ サーバーがインストールされている場合は、エッジ サーバーまたはエッジ サーバー プールで接続の検証が自動的に行われますが、この確認は Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="fa923-108">While validation of connectivity is done automatically in Edge Server or Edge Server pool when the Edge Servers are installed, you can still confirm this for yourself with Windows PowerShell.</span></span> <span data-ttu-id="fa923-109">Get-CsManagementStoreReplicationStatus 中央管理ストアを持つ内部サーバー、または Skype for Business Server コア コンポーネント (OcsCore.msi) がインストールされているドメインに参加しているコンピューターで、OcsCore.msi コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="fa923-109">Run the Get-CsManagementStoreReplicationStatus cmdlet on the internal server which has the Central Management store, or any domain joined computer on which Skype for Business Server Core Components (OcsCore.msi) are installed.</span></span>
  
<span data-ttu-id="fa923-110">このコマンドを実行した最初の結果では、レプリケーションに対して True ではなく False 状態が返される場合があります。</span><span class="sxs-lookup"><span data-stu-id="fa923-110">The initial result of running this command may give a False status, rather than True, for replication.</span></span> <span data-ttu-id="fa923-111">その場合は、次のコマンドレットInvoke-CsManagementStoreReplicationします。</span><span class="sxs-lookup"><span data-stu-id="fa923-111">If that happens run the Invoke-CsManagementStoreReplication cmdlet.</span></span> <span data-ttu-id="fa923-112">レプリケーションを完了してから、このコマンドレットを再度実行Get-CsManagementStoreReplicationStatusします。</span><span class="sxs-lookup"><span data-stu-id="fa923-112">Give it some time to complete the replication, and then run the Get-CsManagementStoreReplicationStatus cmdlet again.</span></span>
  
## <a name="verify-connectivity-for-your-external-users"></a><span data-ttu-id="fa923-113">外部ユーザーの接続を確認する</span><span class="sxs-lookup"><span data-stu-id="fa923-113">Verify connectivity for your external users</span></span>

<span data-ttu-id="fa923-114">エッジ サーバーの構成を確認し、エッジ サーバーのシナリオに合った適切なメッセージを接続、送信、受信する機能を確認するための最適なツールがあります。</span><span class="sxs-lookup"><span data-stu-id="fa923-114">We do have a great tool for confirming your Edge Server configuration, and the ability to connect, send and receive the correct messages for Edge Server scenarios.</span></span> <span data-ttu-id="fa923-115">リモート接続テスト [サイトです](https://testconnectivity.microsoft.com/)。</span><span class="sxs-lookup"><span data-stu-id="fa923-115">It's the [Remote Connectivity Anaylzer site](https://testconnectivity.microsoft.com/).</span></span> <span data-ttu-id="fa923-116">これは、Microsoft サポートによって管理および管理されているサイトです。</span><span class="sxs-lookup"><span data-stu-id="fa923-116">This is a site that's managed and maintained by Microsoft Support.</span></span> <span data-ttu-id="fa923-117">このツールを使用するには、Web サイトを参照し、指示に従って適切なシナリオを選択します。</span><span class="sxs-lookup"><span data-stu-id="fa923-117">To use this tool, browse to the website and follow the instructions to choose the right scenario for you.</span></span>
  
### <a name="things-to-consider-when-testing-external-user-connectivity"></a><span data-ttu-id="fa923-118">外部ユーザー接続をテストする際の考慮すべき点</span><span class="sxs-lookup"><span data-stu-id="fa923-118">Things to consider when testing external user connectivity</span></span>

<span data-ttu-id="fa923-119">外部ユーザー アクセスのテストには、組織がサポートする各種類の内部ユーザーを含める必要があります。内部ユーザーには、次の一部またはすべてが含まれます。</span><span class="sxs-lookup"><span data-stu-id="fa923-119">Any test for external user access needs to include each type of internal user your organization supports, which could include any or all of the following:</span></span>
  
- <span data-ttu-id="fa923-120">少なくとも 1 つのフェデレーション ドメインのユーザー (すべてテストすることをお勧めします)。</span><span class="sxs-lookup"><span data-stu-id="fa923-120">Users from at least one federated domain (we do recommend testing them all though).</span></span>
    
- <span data-ttu-id="fa923-121">匿名ユーザー。</span><span class="sxs-lookup"><span data-stu-id="fa923-121">Anonymous users.</span></span>
    
- <span data-ttu-id="fa923-122">組織内で、リモートで Skype for Business にログインしているが、VPN を使用していないユーザー。</span><span class="sxs-lookup"><span data-stu-id="fa923-122">Users in your organization who are logged into Skype for Business remotely, but aren't using VPN.</span></span>
    
<span data-ttu-id="fa923-123">これらのテストによって、エッジ サーバーが次のかどうかが判断されます。</span><span class="sxs-lookup"><span data-stu-id="fa923-123">These tests will determine whether your Edge Server is:</span></span>
  
- <span data-ttu-id="fa923-124">ネットワーク外から telnet クライアントを使用して必要なポートをリッスンする。</span><span class="sxs-lookup"><span data-stu-id="fa923-124">Listening on the necessary ports by using a telnet client from outside your network.</span></span>
    
  - <span data-ttu-id="fa923-125">例: telnet sip.contoso.com 443</span><span class="sxs-lookup"><span data-stu-id="fa923-125">For example: telnet sip.contoso.com 443</span></span>
    
  - <span data-ttu-id="fa923-126">展開に応じて、エッジ サーバーまたはエッジ サーバー プールで使用しているポートで、前のテストを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fa923-126">You should perform the preceding test on the ports you're using on your Edge Server or Edge Server pool, depending on your deployment.</span></span>
    
- <span data-ttu-id="fa923-127">正確な外部 DNS 解決を実行する。</span><span class="sxs-lookup"><span data-stu-id="fa923-127">Performing accurate external DNS resolution.</span></span>
    
  - <span data-ttu-id="fa923-128">ネットワークの外部から、エッジ サーバーまたはエッジ サーバー プールの各外部 FQDN に ping を実行します。</span><span class="sxs-lookup"><span data-stu-id="fa923-128">From outside your network, ping each of the external FQDNs of your Edge Server or Edge Server pool.</span></span> <span data-ttu-id="fa923-129">ping が失敗した場合でも、IP アドレスが表示され、以前に割り当てた IP アドレスを比較できます。</span><span class="sxs-lookup"><span data-stu-id="fa923-129">Even if the ping fails, you'll see the IP addresses, which you can compare the IP addresses you've previously assigned.</span></span>
    

