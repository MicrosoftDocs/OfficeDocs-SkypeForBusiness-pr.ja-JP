---
title: Skype for Business Server での Edge の展開を検証する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
audience: ITPro
manager: serdars
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 69837f86-d141-4884-a4ca-c7e7463afaad
description: '概要: エッジサーバーまたはエッジサーバープールの展開が Skype for Business Server で動作していることを確認する方法について説明します。'
ms.openlocfilehash: 57994e4583a3424fc680c8dfb220aeb11668c6fc
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233875"
---
# <a name="validate-your-edge-deployment-in-skype-for-business-server"></a><span data-ttu-id="e6c26-103">Skype for Business Server での Edge の展開を検証する</span><span class="sxs-lookup"><span data-stu-id="e6c26-103">Validate your Edge deployment in Skype for Business Server</span></span>
 
<span data-ttu-id="e6c26-104">**概要:** エッジサーバーまたはエッジサーバープールの展開が Skype for Business Server で動作していることを確認する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="e6c26-104">**Summary:** Learn how to verify that your deployment of Edge Server or Edge Server pool is working in Skype for Business Server.</span></span>
  
<span data-ttu-id="e6c26-105">エッジサーバーまたはエッジサーバープールを展開したら、正常に動作しているかどうかを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e6c26-105">Once you've deployed your Edge Server or Edge Server pool, you need to know if it's working properly.</span></span> <span data-ttu-id="e6c26-106">ここでは、Edge 環境が内部サーバーに接続されていることを確認するために役立ついくつかの方法について説明します。また、外部ユーザーは、Edge 経由で Skype for Business Server 環境に接続することもできます。</span><span class="sxs-lookup"><span data-stu-id="e6c26-106">Here are a couple of things that can help with confirming your Edge environment is connected to your internal servers, and also that your external users can connect to your Skype for Business Server environment through your Edge.</span></span>
  
## <a name="verify-connectivity-between-your-internal-servers-and-your-edge-servers"></a><span data-ttu-id="e6c26-107">内部サーバーとエッジ サーバーの間の接続を検証する</span><span class="sxs-lookup"><span data-stu-id="e6c26-107">Verify connectivity between your internal servers and your Edge servers</span></span>

<span data-ttu-id="e6c26-108">エッジサーバーがインストールされているときに接続の検証がエッジサーバーまたはエッジサーバープールで自動的に行われる場合は、Windows PowerShell を使用してこれを確認することができます。</span><span class="sxs-lookup"><span data-stu-id="e6c26-108">While validation of connectivity is done automatically in Edge Server or Edge Server pool when the Edge Servers are installed, you can still confirm this for yourself with Windows PowerShell.</span></span> <span data-ttu-id="e6c26-109">中央管理ストア、または Skype for Business Server Core Components (OcsCore) がインストールされている任意のドメインに参加しているコンピューターで、CsManagementStoreReplicationStatus コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="e6c26-109">Run the Get-CsManagementStoreReplicationStatus cmdlet on the internal server which has the Central Management store, or any domain joined computer on which Skype for Business Server Core Components (OcsCore.msi) are installed.</span></span>
  
<span data-ttu-id="e6c26-p103">このコマンドを実行した最初の結果では、レプリケーションに対して、状態が True ではなく False と示される場合があります。その場合は Invoke-CsManagementStoreReplication コマンドレットを実行し、レプリケーションが完了するまでしばらく待ってから、再び Get-CsManagementStoreReplicationStatus コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="e6c26-p103">The initial result of running this command may give a False status, rather than True, for replication. If that happens run the Invoke-CsManagementStoreReplication cmdlet. Give it some time to complete the replication, and then run the Get-CsManagementStoreReplicationStatus cmdlet again.</span></span>
  
## <a name="verify-connectivity-for-your-external-users"></a><span data-ttu-id="e6c26-113">外部ユーザーの接続を検証する</span><span class="sxs-lookup"><span data-stu-id="e6c26-113">Verify connectivity for your external users</span></span>

<span data-ttu-id="e6c26-114">エッジサーバーの構成を確認するための優れたツールが用意されています。また、エッジサーバーのシナリオについて、適切なメッセージの接続、送受信、受信を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="e6c26-114">We do have a great tool for confirming your Edge Server configuration, and the ability to connect, send and receive the correct messages for Edge Server scenarios.</span></span> <span data-ttu-id="e6c26-115">これは、[リモート接続 Anaylzer サイト](https://testconnectivity.microsoft.com/)です。</span><span class="sxs-lookup"><span data-stu-id="e6c26-115">It's the [Remote Connectivity Anaylzer site](https://testconnectivity.microsoft.com/).</span></span> <span data-ttu-id="e6c26-116">このサイトは Microsoft サポートにより管理および維持されています。</span><span class="sxs-lookup"><span data-stu-id="e6c26-116">This is a site that's managed and maintained by Microsoft Support.</span></span> <span data-ttu-id="e6c26-117">このツールを使用するには、上記の Web サイトにアクセスし、適切なシナリオを選択するための指示に従います。</span><span class="sxs-lookup"><span data-stu-id="e6c26-117">To use this tool, browse to the website and follow the instructions to choose the right scenario for you.</span></span>
  
### <a name="things-to-consider-when-testing-external-user-connectivity"></a><span data-ttu-id="e6c26-118">外部ユーザーの接続をテストする際の考慮事項</span><span class="sxs-lookup"><span data-stu-id="e6c26-118">Things to consider when testing external user connectivity</span></span>

<span data-ttu-id="e6c26-119">外部ユーザー アクセスのテストには、次のいずれかまたはすべてなど、組織がサポートしている各内部ユーザー タイプを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="e6c26-119">Any test for external user access needs to include each type of internal user your organization supports, which could include any or all of the following:</span></span>
  
- <span data-ttu-id="e6c26-120">少なくとも 1 つのフェデレーション ドメインのユーザー (ただしすべてのユーザーのテストは推奨しません)。</span><span class="sxs-lookup"><span data-stu-id="e6c26-120">Users from at least one federated domain (we do recommend testing them all though).</span></span>
    
- <span data-ttu-id="e6c26-121">匿名ユーザー。</span><span class="sxs-lookup"><span data-stu-id="e6c26-121">Anonymous users.</span></span>
    
- <span data-ttu-id="e6c26-122">リモートで Skype for Business にログインしているが、VPN を使用していない組織内のユーザー。</span><span class="sxs-lookup"><span data-stu-id="e6c26-122">Users in your organization who are logged into Skype for Business remotely, but aren't using VPN.</span></span>
    
<span data-ttu-id="e6c26-123">これらのテストによって、エッジサーバーが次のどちらであるかが判別されます。</span><span class="sxs-lookup"><span data-stu-id="e6c26-123">These tests will determine whether your Edge Server is:</span></span>
  
- <span data-ttu-id="e6c26-124">ネットワーク外から telnet クライアントを使用して必要なポートをリッスンする。</span><span class="sxs-lookup"><span data-stu-id="e6c26-124">Listening on the necessary ports by using a telnet client from outside your network.</span></span>
    
  - <span data-ttu-id="e6c26-125">例: telnet sip.contoso.com 443</span><span class="sxs-lookup"><span data-stu-id="e6c26-125">For example: telnet sip.contoso.com 443</span></span>
    
  - <span data-ttu-id="e6c26-126">展開に応じて、エッジサーバーまたはエッジサーバープールで使用しているポートに対して、前のテストを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e6c26-126">You should perform the preceding test on the ports you're using on your Edge Server or Edge Server pool, depending on your deployment.</span></span>
    
- <span data-ttu-id="e6c26-127">正確な外部 DNS 解決を実行する。</span><span class="sxs-lookup"><span data-stu-id="e6c26-127">Performing accurate external DNS resolution.</span></span>
    
  - <span data-ttu-id="e6c26-128">ネットワークの外部から、エッジサーバーまたはエッジサーバープールの外部 Fqdn をそれぞれ ping します。</span><span class="sxs-lookup"><span data-stu-id="e6c26-128">From outside your network, ping each of the external FQDNs of your Edge Server or Edge Server pool.</span></span> <span data-ttu-id="e6c26-129">Ping に失敗した場合でも、IP アドレスが表示されます。これにより、以前に割り当てた IP アドレスを比較できます。</span><span class="sxs-lookup"><span data-stu-id="e6c26-129">Even if the ping fails, you'll see the IP addresses, which you can compare the IP addresses you've previously assigned.</span></span>
    

