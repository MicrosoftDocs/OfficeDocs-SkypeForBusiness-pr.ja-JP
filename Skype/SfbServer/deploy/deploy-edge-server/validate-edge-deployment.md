---
title: Skype for Business Server 2015 でのエッジ展開の検証
ms.author: heidip
author: microsoftheidi
ms.date: 2/23/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 69837f86-d141-4884-a4ca-c7e7463afaad
description: '概要: は、Skype のビジネス サーバー 2015 のエッジ サーバーまたはエッジ サーバー プールの展開が機能していることを確認する方法を説明します。'
ms.openlocfilehash: b8adc5e8d652607156d0136671b1f149fbfe27b4
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="validate-your-edge-deployment-in-skype-for-business-server-2015"></a><span data-ttu-id="26c31-103">Skype for Business Server 2015 でのエッジ展開の検証</span><span class="sxs-lookup"><span data-stu-id="26c31-103">Validate your Edge deployment in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="26c31-104">**の概要:** ビジネス サーバー 2015 の Skype でエッジ サーバーまたはエッジ サーバー プールの展開が機能していることを確認する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="26c31-104">**Summary:** Learn how to verify that your deployment of Edge Server or Edge Server pool is working in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="26c31-105">エッジ サーバーまたはエッジ サーバー プールを展開して、正しく動作しているかを把握する必要があります。</span><span class="sxs-lookup"><span data-stu-id="26c31-105">Once you've deployed your Edge Server or Edge Server pool, you need to know if it's working properly.</span></span> <span data-ttu-id="26c31-106">エッジ環境に接続されていることを確認するのに役立ついくつかをここでは、内部のサーバーに、外部ユーザー経由で接続できるサーバー 2015 のビジネス環境について、Skype、エッジです。</span><span class="sxs-lookup"><span data-stu-id="26c31-106">Here are a couple of things that can help with confirming your Edge environment is connected to your internal servers, and also that your external users can connect to your Skype for Business Server 2015 environment through your Edge.</span></span>
  
## <a name="verify-connectivity-between-your-internal-servers-and-your-edge-servers"></a><span data-ttu-id="26c31-107">内部サーバーとエッジ サーバーの間の接続を検証する</span><span class="sxs-lookup"><span data-stu-id="26c31-107">Verify connectivity between your internal servers and your Edge servers</span></span>

<span data-ttu-id="26c31-108">接続の検証は、エッジ トランスポート サーバーがインストールされている場合も、エッジ サーバーまたはエッジ サーバー プールに自動的に行われます、中にも確認できます自分用の Windows PowerShell にします。</span><span class="sxs-lookup"><span data-stu-id="26c31-108">While validation of connectivity is done automatically in Edge Server or Edge Server pool when the Edge Servers are installed, you can still confirm this for yourself with Windows PowerShell.</span></span> <span data-ttu-id="26c31-109">保存、一元管理があるか、ビジネス サーバー 2015 のコア ・ コンポーネント (OcsCore.msi) は、Skype 上の任意のドメイン結合されたコンピューターがインストールされている内部サーバー上には、Get CsManagementStoreReplicationStatus コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="26c31-109">Run the Get-CsManagementStoreReplicationStatus cmdlet on the internal server which has the Central Management store, or any domain joined computer on which Skype for Business Server 2015 Core Components (OcsCore.msi) are installed.</span></span>
  
<span data-ttu-id="26c31-p103">このコマンドを実行した最初の結果では、レプリケーションに対して、状態が True ではなく False と示される場合があります。その場合は Invoke-CsManagementStoreReplication コマンドレットを実行し、レプリケーションが完了するまでしばらく待ってから、再び Get-CsManagementStoreReplicationStatus コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="26c31-p103">The initial result of running this command may give a False status, rather than True, for replication. If that happens run the Invoke-CsManagementStoreReplication cmdlet. Give it some time to complete the replication, and then run the Get-CsManagementStoreReplicationStatus cmdlet again.</span></span>
  
## <a name="verify-connectivity-for-your-external-users"></a><span data-ttu-id="26c31-113">外部ユーザーの接続を検証する</span><span class="sxs-lookup"><span data-stu-id="26c31-113">Verify connectivity for your external users</span></span>

<span data-ttu-id="26c31-114">エッジ サーバーの構成と接続、送信、およびエッジ サーバーのシナリオで適切なメッセージを受信することを確認するための優れたツールあります。</span><span class="sxs-lookup"><span data-stu-id="26c31-114">We do have a great tool for confirming your Edge Server configuration, and the ability to connect, send and receive the correct messages for Edge Server scenarios.</span></span> <span data-ttu-id="26c31-115">これは、[リモート接続 Anaylzer サイト](https://testconnectivity.microsoft.com/)です。</span><span class="sxs-lookup"><span data-stu-id="26c31-115">It's the [Remote Connectivity Anaylzer site](https://testconnectivity.microsoft.com/).</span></span> <span data-ttu-id="26c31-116">このサイトは Microsoft サポートにより管理および維持されています。</span><span class="sxs-lookup"><span data-stu-id="26c31-116">This is a site that's managed and maintained by Microsoft Support.</span></span> <span data-ttu-id="26c31-117">このツールを使用するには、上記の Web サイトにアクセスし、適切なシナリオを選択するための指示に従います。</span><span class="sxs-lookup"><span data-stu-id="26c31-117">To use this tool, browse to the website and follow the instructions to choose the right scenario for you.</span></span>
  
### <a name="things-to-consider-when-testing-external-user-connectivity"></a><span data-ttu-id="26c31-118">外部ユーザーの接続をテストする際の考慮事項</span><span class="sxs-lookup"><span data-stu-id="26c31-118">Things to consider when testing external user connectivity</span></span>

<span data-ttu-id="26c31-119">外部ユーザー アクセスのテストには、次のいずれかまたはすべてなど、組織がサポートしている各内部ユーザー タイプを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="26c31-119">Any test for external user access needs to include each type of internal user your organization supports, which could include any or all of the following:</span></span>
  
- <span data-ttu-id="26c31-120">少なくとも 1 つのフェデレーション ドメインのユーザー (ただしすべてのユーザーのテストは推奨しません)。</span><span class="sxs-lookup"><span data-stu-id="26c31-120">Users from at least one federated domain (we do recommend testing them all though).</span></span>
    
- <span data-ttu-id="26c31-121">匿名ユーザー。</span><span class="sxs-lookup"><span data-stu-id="26c31-121">Anonymous users.</span></span>
    
- <span data-ttu-id="26c31-122">ユーザー、組織内にビジネス用の Skype、リモートでログに記録されますが、VPN を使用していません。</span><span class="sxs-lookup"><span data-stu-id="26c31-122">Users in your organization who are logged into Skype for Business remotely, but aren't using VPN.</span></span>
    
<span data-ttu-id="26c31-123">これらのテストには、エッジ サーバーがあるかどうかが決まります。</span><span class="sxs-lookup"><span data-stu-id="26c31-123">These tests will determine whether your Edge Server is:</span></span>
  
- <span data-ttu-id="26c31-124">ネットワーク外から telnet クライアントを使用して必要なポートをリッスンする。</span><span class="sxs-lookup"><span data-stu-id="26c31-124">Listening on the necessary ports by using a telnet client from outside your network.</span></span>
    
  - <span data-ttu-id="26c31-125">例: telnet sip.contoso.com 443</span><span class="sxs-lookup"><span data-stu-id="26c31-125">For example: telnet sip.contoso.com 443</span></span>
    
  - <span data-ttu-id="26c31-126">配置に基づいて、エッジ サーバーまたはエッジ サーバーのプールで使用するポートで上記のテストを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="26c31-126">You should perform the preceding test on the ports you're using on your Edge Server or Edge Server pool, depending on your deployment.</span></span>
    
- <span data-ttu-id="26c31-127">正確な外部 DNS 解決を実行する。</span><span class="sxs-lookup"><span data-stu-id="26c31-127">Performing accurate external DNS resolution.</span></span>
    
  - <span data-ttu-id="26c31-128">ネットワーク外の外部エッジ サーバーまたはエッジ サーバー プールの Fqdn を ping します。</span><span class="sxs-lookup"><span data-stu-id="26c31-128">From outside your network, ping each of the external FQDNs of your Edge Server or Edge Server pool.</span></span> <span data-ttu-id="26c31-129">Ping が失敗した場合でも、以前に割り当てた IP アドレスを比較することができる IP アドレスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="26c31-129">Even if the ping fails, you'll see the IP addresses, which you can compare the IP addresses you've previously assigned.</span></span>
    

