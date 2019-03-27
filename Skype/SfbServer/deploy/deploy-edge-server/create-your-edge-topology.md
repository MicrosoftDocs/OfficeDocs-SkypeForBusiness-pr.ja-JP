---
title: Skype のビジネス サーバーのエッジ ・ トポロジーを作成します。
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 5ea18841-afdc-4ccb-8d86-30584c1f5aca
description: '概要: は、作成、発行、およびビジネスのサーバーの Skype で、エッジ サーバーのトポロジをエクスポートする方法を説明します。'
ms.openlocfilehash: 32273f7e0cf14b4ed5be3956eb69ef66a3b06fee
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30875448"
---
# <a name="create-your-edge-topology-for-skype-for-business-server"></a><span data-ttu-id="0298f-103">Skype のビジネス サーバーのエッジ ・ トポロジーを作成します。</span><span class="sxs-lookup"><span data-stu-id="0298f-103">Create your Edge topology for Skype for Business Server</span></span>
 
<span data-ttu-id="0298f-104">**の概要:** 構築、公開、および業務サーバーの Skype で、エッジ サーバーのトポロジをエクスポートする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="0298f-104">**Summary:** Learn how to build, publish, and export your Edge Server topology in Skype for Business Server.</span></span>
  
<span data-ttu-id="0298f-105">トポロジ ビルダーとを使用して、エッジ サーバーのトポロジを構築するだけで、任意のトポロジのコンポーネントの Skype のビジネス サーバーのする必要がありますツールです。</span><span class="sxs-lookup"><span data-stu-id="0298f-105">Topology Builder is the tool you need to use to build your Edge Server topology, just as it's used for any topology component for Skype for Business Server.</span></span> <span data-ttu-id="0298f-106">以下の手順を実行する前に、少なくとも 1 つのフロント エンド プールまたは Standard Edition サーバーを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0298f-106">Before following the steps below, you will need to have set up at least one Front End pool or a Standard Edition server.</span></span>
  
<span data-ttu-id="0298f-107">この記事では、次のトピックを扱います。</span><span class="sxs-lookup"><span data-stu-id="0298f-107">We cover the following topics in this article:</span></span>
  
- <span data-ttu-id="0298f-108">エッジ サーバー トポロジを構築します。</span><span class="sxs-lookup"><span data-stu-id="0298f-108">Build your Edge Server topology</span></span>
    
- <span data-ttu-id="0298f-109">エッジ サーバー トポロジを公開する</span><span class="sxs-lookup"><span data-stu-id="0298f-109">Publish your Edge Server topology</span></span>
    
- <span data-ttu-id="0298f-110">エッジ サーバー トポロジをエクスポートする</span><span class="sxs-lookup"><span data-stu-id="0298f-110">Export your Edge Server topology</span></span>
    
  > [!NOTE]
  > <span data-ttu-id="0298f-111">以下の手順に従うには、次のドメイン グループのメンバーであるユーザーとして、下記のドメイン サーバーにログインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="0298f-111">To follow the steps below, you're going to need to log into the domain servers mentioned below as a user who's a member of the following domain groups:</span></span> 
  
- <span data-ttu-id="0298f-112">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="0298f-112">RTCUniversalServerAdmins</span></span>
    
- <span data-ttu-id="0298f-113">Domain Admins</span><span class="sxs-lookup"><span data-stu-id="0298f-113">Domain Admins</span></span>
    
## <a name="build-your-edge-server-topology"></a><span data-ttu-id="0298f-114">エッジ サーバー トポロジを構築します。</span><span class="sxs-lookup"><span data-stu-id="0298f-114">Build your Edge Server topology</span></span>

<span data-ttu-id="0298f-115">最初の配置手順では、ビジネス エッジ サーバー トポロジでは、次の 3 つのオプションのいずれかで構成されるため、Skype を構築します。</span><span class="sxs-lookup"><span data-stu-id="0298f-115">The first deployment step is building your Skype for Business Server Edge Server topology, which consists of one of three options:</span></span>
  
- <span data-ttu-id="0298f-116">1 台のエッジ サーバー</span><span class="sxs-lookup"><span data-stu-id="0298f-116">A single Edge Server</span></span>
    
- <span data-ttu-id="0298f-117">DNS 負荷分散されたエッジ プール (1 つまたは複数のサーバー)</span><span class="sxs-lookup"><span data-stu-id="0298f-117">A DNS load balanced Edge pool (one or more servers)</span></span>
    
- <span data-ttu-id="0298f-118">ハードウェア負荷分散のエッジのプール (1 つまたは複数のサーバー)</span><span class="sxs-lookup"><span data-stu-id="0298f-118">A hardware load balanced Edge pool (one or more servers)</span></span>
    
<span data-ttu-id="0298f-p102">必要なエッジが不明である場合は、以下の手順を開始する前に、「計画」のドキュメントを参照してください。不明でなければ、作業を開始します。</span><span class="sxs-lookup"><span data-stu-id="0298f-p102">If you aren't sure what you need, then before you start following these steps, it's a good time to go over the Planning documentation. Otherwise, let's begin.</span></span>
  
### <a name="defining-the-topology-for-a-single-edge-server"></a><span data-ttu-id="0298f-121">1 台のエッジ サーバーのトポロジを定義します。</span><span class="sxs-lookup"><span data-stu-id="0298f-121">Defining the topology for a single Edge Server</span></span>

1. <span data-ttu-id="0298f-122">ビジネス サーバーの Standard Edition サーバーには、Skype、Skype のビジネス サーバーのフロント エンド プールへのログオンします。</span><span class="sxs-lookup"><span data-stu-id="0298f-122">Log onto your Skype for Business Server Standard Edition server, or a Skype for Business Server Front End pool.</span></span>
    
2. <span data-ttu-id="0298f-123">**ビジネス サーバー トポロジ ビルダーの Skype**を開く、1 回。</span><span class="sxs-lookup"><span data-stu-id="0298f-123">Once there, open **Skype for Business Server Topology Builder**.</span></span>
    
3. <span data-ttu-id="0298f-124">コンソール ツリーで、エッジ サーバーを展開しようとしているサイトを展開します。</span><span class="sxs-lookup"><span data-stu-id="0298f-124">In the console tree, expand the site you're going to deploy the Edge Server to.</span></span>
    
4. <span data-ttu-id="0298f-125">**エッジ プール**を右クリックし、**新しいエッジ プール**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0298f-125">Right-click **Edge pools**, and then click **New Edge pool**.</span></span>
    
5. <span data-ttu-id="0298f-126">**プールの新しいエッジの定義**] 画面で**次へ**をクリックするでしょう。</span><span class="sxs-lookup"><span data-stu-id="0298f-126">You'll click **Next** on the **Define New Edge pool** screen.</span></span>
    
6. <span data-ttu-id="0298f-127">[**エッジ プール FQDN の定義**] 画面をエッジ サーバーを使用して、内部の完全修飾ドメイン名 (FQDN) を入力し、 **1 台のコンピューターのプール**、**次へ**完了をクリックするとします。</span><span class="sxs-lookup"><span data-stu-id="0298f-127">On the **Define the Edge pool FQDN** screen, type the internal fully qualified domain name (FQDN) that the Edge Server is going to use, and select **Single computer pool**, clicking **Next** when done.</span></span>
    
7. <span data-ttu-id="0298f-128">[**機能の選択**] 画面には、次の選択肢があります。</span><span class="sxs-lookup"><span data-stu-id="0298f-128">On the **Select features** screen, you have a choice:</span></span>
    
   - <span data-ttu-id="0298f-129">SIP アクセス サービス、ビジネス サーバーの Web 会議サービスでは、Skype、A に同じ FQDN と IP アドレスを使用すると音声ビデオ エッジ サービスです。</span><span class="sxs-lookup"><span data-stu-id="0298f-129">You may intend to use the same FQDN and IP address for your SIP Access service, your Skype for Business Server Web Conferencing service, and your A/V Edge service.</span></span> <span data-ttu-id="0298f-130">**単一の FQDN と IP アドレス チェック ボックスを使用**する」を選択 (および、注意してください以下の手順 9 に) する必要がある場合は、</span><span class="sxs-lookup"><span data-stu-id="0298f-130">If so, you need to choose the **Use a single FQDN and IP address checkbox** (and keep this in mind for Step 9 below)</span></span>
    
   - <span data-ttu-id="0298f-131">フェデレーションを有効にする計画がある場合は、[**このエッジ プールのフェデレーションを有効化 (ポート 5061)**] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="0298f-131">If you're planning to enable federation, choose the **Enable federation for this Edge pool (Port 5061)** check box.</span></span>
    
8. <span data-ttu-id="0298f-p104">[**次へ**] をクリックすると、[**IP オプション**] 画面に移動します。次のオプションが使用できます。</span><span class="sxs-lookup"><span data-stu-id="0298f-p104">Once you've clicked **Next**, you'll find yourself on the **IP Options** screen. Your options are as follows:</span></span>
    
   - <span data-ttu-id="0298f-134">内部インターフェイスで IPv4 を有効にする</span><span class="sxs-lookup"><span data-stu-id="0298f-134">Enable IPv4 on the internal interface</span></span>
    
   - <span data-ttu-id="0298f-135">内部インターフェイスで IPv6 を有効にする</span><span class="sxs-lookup"><span data-stu-id="0298f-135">Enable IPv6 on the internal interface</span></span>
    
   - <span data-ttu-id="0298f-136">外部インターフェイスで IPv4 を有効にする</span><span class="sxs-lookup"><span data-stu-id="0298f-136">Enable IPv4 on the external interface</span></span>
    
   - <span data-ttu-id="0298f-137">外部インターフェイスで IPv6 を有効にする</span><span class="sxs-lookup"><span data-stu-id="0298f-137">Enable IPv6 on the external interface</span></span>
    
   <span data-ttu-id="0298f-138">これらは、IPv4 または IPv6 アドレスを使用しているし、適用するこれらのアドレス、エッジ サーバーの内部または外部かどうか一目瞭然ですが、(このステップ 10 の点に注意する必要があります)。</span><span class="sxs-lookup"><span data-stu-id="0298f-138">These are pretty self-explanatory, whether you're using IPv4 or IPv6 addresses, and you're applying those addresses on your Edge Server internally or externally (you'll need to keep this in mind for Step 10).</span></span> <span data-ttu-id="0298f-139">外部 IP アドレスのネットワーク アドレス変換 (NAT) アドレスを使用するのには、エッジ サーバーまたはエッジ プールを構成するオプションもあります。</span><span class="sxs-lookup"><span data-stu-id="0298f-139">You also have the option of configuring your Edge Server or your Edge pool to use a network address translation (NAT) address for the external IP address.</span></span> <span data-ttu-id="0298f-140">**このエッジ プールの外部 IP アドレスが NAT によって変換**する] チェック ボックスを選択することによってこれを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="0298f-140">You can do this by choosing **The external IP address of this Edge pool is translated by NAT** check box .</span></span> <span data-ttu-id="0298f-141">[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0298f-141">Click **Next** when ready.</span></span>
    
9. <span data-ttu-id="0298f-142">[外部 FQDN] 画面の選択肢は、上記の手順 7. で行った選択内容に応じて異なります。</span><span class="sxs-lookup"><span data-stu-id="0298f-142">On the External FQDNs screen, your choices depend on the selection you made in Step 7 above.</span></span>
    
   - <span data-ttu-id="0298f-143">**単一の FQDN と IP アドレスを使う**] チェック ボックスをオンにした場合、[ **SIP アクセス**] ボックスで、1 つの外部 FQDN を入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0298f-143">If you checked the **Use a single FQDN and IP Address** check box, you need to enter your single external FQDN in the **SIP Access** box.</span></span> <span data-ttu-id="0298f-144">エッジ サービスごとに個別に接続するためにすべてを許可する別のポート番号を入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0298f-144">Then you'll need to enter different port numbers for each edge service to allow them all to connect independently.</span></span> <span data-ttu-id="0298f-145">[**SIP アクセス**] エッジ サービスには 5061、[**Web 会議**] エッジ サービスには 444、[**音声ビデオ**] エッジ サービスには 443 を指定することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="0298f-145">We recommend 5061 for the **SIP Access** Edge service, 444 for the **Web Conferencing** Edge service, and 443 for the **A/V** Edge service.</span></span> <span data-ttu-id="0298f-146">作業が完了したら [**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0298f-146">Click **Next** when done.</span></span>
    
   - <span data-ttu-id="0298f-147">場合は **、単一の FQDN と IP アドレスを使う**] チェック ボックスをチェックしていません、今すぐ必要**SIP アクセス**エッジ サービス、 **Web 会議**エッジ サービスの 3 つの外部 Fqdn を入力して、 **A/V**エッジのサービスです。</span><span class="sxs-lookup"><span data-stu-id="0298f-147">If you didn't check the **Use a single FQDN and IP Address** check box, you'll now need to enter the three external FQDNs for the **SIP Access** Edge service, the **Web Conferencing** Edge service, and the **A/V** Edge service.</span></span> <span data-ttu-id="0298f-148">作業が完了したら [**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0298f-148">Click **Next** when done.</span></span>
    
10. <span data-ttu-id="0298f-149">さて、**内部 IP アドレスを定義する**画面です。</span><span class="sxs-lookup"><span data-stu-id="0298f-149">You're now on the **Define the Internal IP address** screen.</span></span> <span data-ttu-id="0298f-150">ここには、**内部の IPv4 アドレス**と**内部の IPv6 アドレス**テキスト ボックスに、手順 8 で行った選択によっては、エッジ サーバーの IP アドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="0298f-150">Here you'll type the IP address of your Edge Server in the **Internal IPv4 address** and **Internal IPv6 address** text boxes, depending on the choices you made back in Step 8.</span></span> <span data-ttu-id="0298f-151">[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0298f-151">Click **Next** when ready.</span></span>
    
11. <span data-ttu-id="0298f-152">[**外部 IP アドレスの定義**] 画面では、以前の選択内容に応じた複数のオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="0298f-152">On the **Define the External IP address** screen, you have a few options depending on your previous choices:</span></span>
    
    - <span data-ttu-id="0298f-153">すべてのサービスに単一の FQDN を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="0298f-153">You may be using a single FQDN for all services.</span></span> <span data-ttu-id="0298f-154">場合は、 **SIP アクセス**] テキスト ボックスに、外部 IPv4 アドレスまたは IPv6 アドレス (どちらを使用している) を入力し、し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0298f-154">If so, type your external IPv4 or IPv6 address (whichever you're using) into the **SIP Access** text box, and then click **Next**.</span></span>
    
    - <span data-ttu-id="0298f-155">可能性がありますしようとして別の 3 つの Fqdn と IP を使用してサービスのアドレスです。</span><span class="sxs-lookup"><span data-stu-id="0298f-155">You may have chosen to use three separate FQDNs and IP addresses for the services.</span></span> <span data-ttu-id="0298f-156">**SIP アクセス**エッジ サービス、 **Web 会議**エッジ サービスの外部の IPv4 または IPv6 アドレスを入力する場合と**A/V**エッジのサービス、し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0298f-156">If that's the case, enter your external IPv4 or IPv6 addresses for the **SIP Access** Edge service, the **Web Conferencing** Edge service, and the **A/V** Edge service, and then click **Next**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="0298f-p111">以前に IPv6 アドレスを有効にして割り当てることを選択しなかった場合、このダイアログ ボックスは表示されません。これで問題はないため、次の手順に進みます。</span><span class="sxs-lookup"><span data-stu-id="0298f-p111">If you didn't previously choose to enable and assign IPv6 addressing, you won't see this dialog box. That's normal, just go to the next step.</span></span> 
  
12. <span data-ttu-id="0298f-159">手順 8 で NAT を使用する場合は、ここで**パブリック IP アドレス**のテキスト ボックスを含む画面が表示されます。</span><span class="sxs-lookup"><span data-stu-id="0298f-159">If you chose to use NAT back in Step 8, you'll now get a screen with a **Public IP address** textbox.</span></span> <span data-ttu-id="0298f-160">A に設定したパブリックの IPv4 または IPv6 のアドレスを入力する必要があります/nat プロトコルにより翻訳、音声ビデオ エッジ サービス</span><span class="sxs-lookup"><span data-stu-id="0298f-160">You'll need to enter the public IPv4 and/or IPv6 address you've set for the A/V Edge service, to be translated by NAT.</span></span> <span data-ttu-id="0298f-161">続いて [ **次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0298f-161">Then click **Next**.</span></span>
    
13. <span data-ttu-id="0298f-162">次に表示される画面は [**次ホップの定義**] です。</span><span class="sxs-lookup"><span data-stu-id="0298f-162">Next screen up is **Define the next hop**.</span></span> <span data-ttu-id="0298f-163">[**次ホップ プール**] ボックスで、フロント エンド プールまたはスタンドアロンのプールがありますが、内部プールの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="0298f-163">In the **Next hop pool** box, select the name of your internal pool, which might be a Front End pool or a Standalone pool.</span></span> <span data-ttu-id="0298f-164">環境内でのディレクターをした場合は、ダイレクタを選択してください。</span><span class="sxs-lookup"><span data-stu-id="0298f-164">If you have a Director in your environment, you should choose the Director.</span></span> <span data-ttu-id="0298f-165">続いて [ **次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0298f-165">Then click **Next**.</span></span>
    
14. <span data-ttu-id="0298f-166">**プールのフロント エンドの関連付け**] 画面で、[1 つまたは複数内部プール、フロント エンド プール、このエッジ サーバーと関連付けるには、Standard Edition サーバーなどを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0298f-166">On the **Associate Front End pools** screen, you'll need to specify one or more internal pools, including Front End pools and Standard Edition servers, to associate with this Edge Server.</span></span> <span data-ttu-id="0298f-167">サポートされている外部ユーザーと通信するためにこのエッジ サーバーを使用して内部のプールの名前を選択するだけです。</span><span class="sxs-lookup"><span data-stu-id="0298f-167">Just choose the names of the internal pools you want using this Edge Server to communicate with supported external users.</span></span> <span data-ttu-id="0298f-168">[ **次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0298f-168">Click **Next**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="0298f-169">ここで注意すべきものでは、内部プールまたはスタンドアロン サーバーは、既にを使用している別の Skype ビジネス エッジ サーバーの場合は、複数のアソシエーションがあることはできません。</span><span class="sxs-lookup"><span data-stu-id="0298f-169">Something to keep in mind here is, if your internal pools or standalone servers are already using a different Skype for Business Server Edge Server, they can't have multiple associations.</span></span> <span data-ttu-id="0298f-170">場合は、内部プールまたはそのような状況では、スタンドアロン サーバーを選択すると、警告が表示される、他のエッジ サーバーを紹介して、続行するかどうするかどうかを決定できますが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0298f-170">If you choose an internal pool or standalone server that's in that situation, you'll see a warning appear telling you about the other Edge Server, and you can decide whether you want to continue or not.</span></span> <span data-ttu-id="0298f-171">この新しい関連付けにさあ、他のエッジ サーバーへの接続を停止します。</span><span class="sxs-lookup"><span data-stu-id="0298f-171">If you go ahead with this new association, the connection to the other Edge Server will stop.</span></span> 
  
15. <span data-ttu-id="0298f-172">次の画面で [**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0298f-172">Click **Finish** on the next screen.</span></span>
    
16. <span data-ttu-id="0298f-173">今すぐことができますこの最新の技術を公開し、指示に従って、 [Skype ビジネス サーバー用にエッジ サーバーの展開](deploy-edge-servers.md)でここから、エッジ サーバーを展開します。</span><span class="sxs-lookup"><span data-stu-id="0298f-173">Now you'll be able to publish this updated technology, and follow the instructions in [Deploy Edge Servers in Skype for Business Server](deploy-edge-servers.md) to deploy to your Edge Server from here.</span></span>
    
### <a name="defining-the-topology-for-a-dns-load-balanced-edge-server-pool"></a><span data-ttu-id="0298f-174">負荷分散エッジ サーバー プールの DNS のトポロジを定義します。</span><span class="sxs-lookup"><span data-stu-id="0298f-174">Defining the topology for a DNS load balanced Edge Server pool</span></span>

1. <span data-ttu-id="0298f-175">ビジネス サーバーの Standard Edition サーバーには、Skype、Skype のビジネス サーバーのフロント エンド サーバーへのログオンします。</span><span class="sxs-lookup"><span data-stu-id="0298f-175">Log onto your Skype for Business Server Standard Edition server, or a Skype for Business Server Front End Server.</span></span>
    
2. <span data-ttu-id="0298f-176">**ビジネス サーバー トポロジ ビルダーの Skype**を開く、1 回。</span><span class="sxs-lookup"><span data-stu-id="0298f-176">Once there, open **Skype for Business Server Topology Builder**.</span></span>
    
3. <span data-ttu-id="0298f-177">コンソール ツリーで、エッジ サーバーを展開しようとしているサイトを展開します。</span><span class="sxs-lookup"><span data-stu-id="0298f-177">In the console tree, expand the site you're going to deploy the Edge Server to.</span></span>
    
4. <span data-ttu-id="0298f-178">**エッジ プール**を右クリックし、**新しいエッジ プール**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0298f-178">Right-click **Edge pools**, and then click **New Edge pool**.</span></span>
    
5. <span data-ttu-id="0298f-179">**プールの新しいエッジの定義**] 画面で**次へ**をクリックするでしょう。</span><span class="sxs-lookup"><span data-stu-id="0298f-179">You'll click **Next** on the **Define New Edge pool** screen.</span></span>
    
6. <span data-ttu-id="0298f-180">[**エッジ プール FQDN の定義**] 画面では、エッジ プールを使用している内部の完全修飾ドメイン名 (FQDN) を入力し、**複数コンピューターのプール**、**次へ**完了をクリックするとを選択します。</span><span class="sxs-lookup"><span data-stu-id="0298f-180">On the **Define the Edge pool FQDN** screen, type the internal fully qualified domain name (FQDN) that the Edge pool is going to use, and select **Multiple computer pool**, clicking **Next** when done.</span></span>
    
7. <span data-ttu-id="0298f-181">[**機能の選択**] 画面には、次の選択肢があります。</span><span class="sxs-lookup"><span data-stu-id="0298f-181">On the **Select features** screen, you have a choice:</span></span>
    
    - <span data-ttu-id="0298f-182">SIP アクセス サービス、ビジネス サーバー Web カンファレンス サービスでは、Skype、A に同じ FQDN と IP アドレスを使用すると音声ビデオ エッジ サービスです。</span><span class="sxs-lookup"><span data-stu-id="0298f-182">You may intend to use the same FQDN and IP address for your SIP Access service, your Skype for Business Server Web Conferencing Service, and your A/V Edge service.</span></span> <span data-ttu-id="0298f-183">**単一の FQDN と IP アドレス チェック ボックスを使用**する」を選択 (および、注意してください以下の手順 9 に) する必要がある場合は、</span><span class="sxs-lookup"><span data-stu-id="0298f-183">If so, you need to choose the **Use a single FQDN and IP address checkbox** (and keep this in mind for Step 9 below)</span></span>
    
    - <span data-ttu-id="0298f-184">フェデレーションを有効にする計画がある場合は、[**このエッジ プールのフェデレーションを有効化 (ポート 5061)**] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="0298f-184">If you're planning to enable federation, choose the **Enable federation for this Edge pool (Port 5061)** check box.</span></span>
    
8. <span data-ttu-id="0298f-p117">[**次へ**] をクリックすると、[**IP オプション**] 画面に移動します。次のオプションが使用できます。</span><span class="sxs-lookup"><span data-stu-id="0298f-p117">Once you've clicked **Next**, you'll find yourself on the **IP Options** screen. Your options are as follows:</span></span>
    
    - <span data-ttu-id="0298f-187">内部インターフェイスで IPv4 を有効にする</span><span class="sxs-lookup"><span data-stu-id="0298f-187">Enable IPv4 on the internal interface</span></span>
    
   - <span data-ttu-id="0298f-188">内部インターフェイスで IPv6 を有効にする</span><span class="sxs-lookup"><span data-stu-id="0298f-188">Enable IPv6 on the internal interface</span></span>
    
   - <span data-ttu-id="0298f-189">外部インターフェイスで IPv4 を有効にする</span><span class="sxs-lookup"><span data-stu-id="0298f-189">Enable IPv4 on the external interface</span></span>
    
   - <span data-ttu-id="0298f-190">外部インターフェイスで IPv6 を有効にする</span><span class="sxs-lookup"><span data-stu-id="0298f-190">Enable IPv6 on the external interface</span></span>
    
     <span data-ttu-id="0298f-191">これらは、IPv4 または IPv6 アドレスを使用しているし、適用するこれらのアドレス、エッジ サーバーの内部または外部かどうか一目瞭然ですが、(手順 11 に留意してくださいこの必要があります)。</span><span class="sxs-lookup"><span data-stu-id="0298f-191">These are pretty self-explanatory, whether you're using IPv4 or IPv6 addresses, and you're applying those addresses on your Edge Server internally or externally (you'll need to keep this in mind for Step 11).</span></span> <span data-ttu-id="0298f-192">外部 IP アドレスのネットワーク アドレス変換 (NAT) アドレスを使用するのには、エッジ サーバーまたはエッジ プールを構成するオプションもあります。</span><span class="sxs-lookup"><span data-stu-id="0298f-192">You also have the option of configuring your Edge Server or your Edge pool to use a network address translation (NAT) address for the external IP address.</span></span> <span data-ttu-id="0298f-193">**このエッジ プールの外部 IP アドレスが NAT によって変換**する] チェック ボックスを選択することによってこれを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="0298f-193">You can do this by choosing **The external IP address of this Edge pool is translated by NAT** check box .</span></span> <span data-ttu-id="0298f-194">[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0298f-194">Click **Next** when ready.</span></span>
    
9. <span data-ttu-id="0298f-195">[外部 FQDN] 画面の選択肢は、上記の手順 7. で行った選択内容に応じて異なります。</span><span class="sxs-lookup"><span data-stu-id="0298f-195">On the External FQDNs screen, your choices depend on the selection you made in Step 7 above.</span></span>
    
   - <span data-ttu-id="0298f-196">**単一の FQDN と IP アドレスを使う**] チェック ボックスをオンにした場合、[ **SIP アクセス**] ボックスで、1 つの外部 FQDN を入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0298f-196">If you checked the **Use a single FQDN and IP Address** check box, you need to enter your single external FQDN in the **SIP Access** box.</span></span> <span data-ttu-id="0298f-197">エッジ サービスごとに個別に接続するためにすべてを許可する別のポート番号を入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0298f-197">Then you'll need to enter different port numbers for each edge service to allow them all to connect independently.</span></span> <span data-ttu-id="0298f-198">[**SIP アクセス**] エッジ サービスには 5061、[**Web 会議**] エッジ サービスには 444、[**音声ビデオ**] エッジ サービスには 443 を指定することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="0298f-198">We recommend 5061 for the **SIP Access** Edge service, 444 for the **Web Conferencing** Edge service, and 443 for the **A/V** Edge service.</span></span> <span data-ttu-id="0298f-199">作業が完了したら [**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0298f-199">Click **Next** when done.</span></span>
    
   - <span data-ttu-id="0298f-200">場合は **、単一の FQDN と IP アドレスを使う**] チェック ボックスをチェックしていません、今すぐ必要**SIP アクセス**エッジ サービス、 **Web 会議**エッジ サービスの 3 つの外部 Fqdn を入力して、 **A/V**エッジのサービスです。</span><span class="sxs-lookup"><span data-stu-id="0298f-200">If you didn't check the **Use a single FQDN and IP Address** check box, you'll now need to enter the three external FQDNs for the **SIP Access** Edge service, the **Web Conferencing** Edge service, and the **A/V** Edge service.</span></span> <span data-ttu-id="0298f-201">作業が完了したら [**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0298f-201">Click **Next** when done.</span></span>
    
10. <span data-ttu-id="0298f-202">今すぐ**このプール内のコンピューターの定義**] 画面に達しています。</span><span class="sxs-lookup"><span data-stu-id="0298f-202">Now you've reached the **Define the computers in this pool** screen.</span></span> <span data-ttu-id="0298f-203">**[追加**] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="0298f-203">Click the **Add** button.</span></span>
    
11. <span data-ttu-id="0298f-204">さて、**内部 IP アドレスを定義する**画面です。</span><span class="sxs-lookup"><span data-stu-id="0298f-204">You're now on the **Define the Internal IP address** screen.</span></span> <span data-ttu-id="0298f-205">ここには、**内部の IPv4 アドレス**と**内部の IPv6 アドレス**テキスト ボックスに、手順 8 で行った選択によっては、エッジ サーバーの IP アドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="0298f-205">Here you'll type the IP address of your Edge Server in the **Internal IPv4 address** and **Internal IPv6 address** text boxes, depending on the choices you made back in Step 8.</span></span> <span data-ttu-id="0298f-206">[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0298f-206">Click **Next** when ready.</span></span>
    
12. <span data-ttu-id="0298f-207">[**外部 IP アドレスの定義**] 画面では、以前の選択内容に応じた複数のオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="0298f-207">On the **Define the External IP address** screen, you have a few options depending on your previous choices:</span></span>
    
    - <span data-ttu-id="0298f-208">すべてのサービスに単一の FQDN を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="0298f-208">You may be using a single FQDN for all services.</span></span> <span data-ttu-id="0298f-209">場合は、 **SIP アクセス**] テキスト ボックスに、外部 IPv4 アドレスまたは IPv6 アドレス (どちらを使用している) を入力し、し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0298f-209">If so, type your external IPv4 or IPv6 address (whichever you're using) into the **SIP Access** text box, and then click **Next**.</span></span>
    
    - <span data-ttu-id="0298f-210">可能性がありますしようとして別の 3 つの Fqdn と IP を使用してサービスのアドレスです。</span><span class="sxs-lookup"><span data-stu-id="0298f-210">You may have chosen to use three separate FQDNs and IP addresses for the services.</span></span> <span data-ttu-id="0298f-211">**SIP アクセス**エッジ サービス、 **Web 会議**エッジ サービスの外部の IPv4 または IPv6 アドレスを入力する場合と**A/V**エッジのサービス、し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0298f-211">If that's the case, enter your external IPv4 or IPv6 addresses for the **SIP Access** Edge service, the **Web Conferencing** Edge service, and the **A/V** Edge service, and then click **Next**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="0298f-p125">以前に IPv6 アドレスを有効にして割り当てることを選択しなかった場合、このダイアログ ボックスは表示されません。これで問題はないため、次の手順に進みます。</span><span class="sxs-lookup"><span data-stu-id="0298f-p125">If you didn't previously choose to enable and assign IPv6 addressing, you won't see this dialog box. That's normal, just go to the next step.</span></span> 
  
13. <span data-ttu-id="0298f-214">[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0298f-214">Click **Finish**.</span></span> <span data-ttu-id="0298f-215">**このプール内のコンピューターの定義**] ダイアログ ボックスで作成したエッジ サーバーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0298f-215">The Edge Server you just created should now be listed in the **Define the computers in this pool** dialog box.</span></span>
    
14. <span data-ttu-id="0298f-216">**このプール内のコンピューターの定義**] 画面で、[**追加**] ボタンをもう一度クリックしてをこのプール内のすべてのエッジ サーバーを追加するまで、手順 11 ~ 13 を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="0298f-216">While still on the **Define the computers in this pool** screen, click the **Add** button again and repeat steps 11 through 13 until you've added all the Edge Servers you intend to have in this pool.</span></span> <span data-ttu-id="0298f-217">作業が完了したら、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0298f-217">When this is complete, click **Next**.</span></span>
    
15. <span data-ttu-id="0298f-218">手順 8 で NAT を使用する場合は、ここで**パブリック IP アドレス**のテキスト ボックスを含む画面が表示されます。</span><span class="sxs-lookup"><span data-stu-id="0298f-218">If you chose to use NAT back in Step 8, you'll now get a screen with a **Public IP address** textbox.</span></span> <span data-ttu-id="0298f-219">A に設定したパブリックの IPv4 または IPv6 のアドレスを入力する必要があります/nat プロトコルにより翻訳、音声ビデオ エッジ サービス</span><span class="sxs-lookup"><span data-stu-id="0298f-219">You'll need to enter the public IPv4 and/or IPv6 address you've set for the A/V Edge service, to be translated by NAT.</span></span> <span data-ttu-id="0298f-220">続いて [ **次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0298f-220">Then click **Next**.</span></span>
    
16. <span data-ttu-id="0298f-221">次に表示される画面は [**次ホップの定義**] です。</span><span class="sxs-lookup"><span data-stu-id="0298f-221">Next screen up is **Define the next hop**.</span></span> <span data-ttu-id="0298f-222">[**次ホップ プール**] ボックスで、フロント エンド プールまたはスタンドアロンのプールがありますが、内部プールの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="0298f-222">In the **Next hop pool** box, select the name of your internal pool, which might be a Front End pool or a Standalone pool.</span></span> <span data-ttu-id="0298f-223">環境内でのディレクターをした場合は、ダイレクタを選択してください。</span><span class="sxs-lookup"><span data-stu-id="0298f-223">If you have a Director in your environment, you should choose the Director.</span></span> <span data-ttu-id="0298f-224">続いて [ **次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0298f-224">Then click **Next**.</span></span>
    
17. <span data-ttu-id="0298f-225">**プールのフロント エンドの関連付け**] 画面で、[1 つまたは複数内部プール、フロント エンド プール、このエッジ サーバーと関連付けるには、Standard Edition プールなどを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0298f-225">On the **Associate Front End pools** screen, you'll need to specify one or more internal pools, including Front End pools and Standard Edition pools, to associate with this Edge Server.</span></span> <span data-ttu-id="0298f-226">サポートされている外部ユーザーと通信するためにこのエッジ サーバーを使用して内部のプールの名前を選択するだけです。</span><span class="sxs-lookup"><span data-stu-id="0298f-226">Just choose the names of the internal pools you want using this Edge Server to communicate with supported external users.</span></span> <span data-ttu-id="0298f-227">[ **次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0298f-227">Click **Next**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="0298f-228">ここで注意すべきものでは、内部プールまたはスタンドアロン サーバーは、既にを使用している別の Skype ビジネス エッジ サーバーの場合は、複数のアソシエーションがあることはできません。</span><span class="sxs-lookup"><span data-stu-id="0298f-228">Something to keep in mind here is, if your internal pools or standalone servers are already using a different Skype for Business Server Edge Server, they can't have multiple associations.</span></span> <span data-ttu-id="0298f-229">場合は、内部プールまたはそのような状況では、スタンドアロン サーバーを選択すると、警告が表示される、他のエッジ サーバーを紹介して、続行するかどうするかどうかを決定できますが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0298f-229">If you choose an internal pool or standalone server that's in that situation, you'll see a warning appear telling you about the other Edge Server, and you can decide whether you want to continue or not.</span></span> <span data-ttu-id="0298f-230">この新しい関連付けにさあ、他のエッジ サーバーへの接続を停止します。</span><span class="sxs-lookup"><span data-stu-id="0298f-230">If you go ahead with this new association, the connection to the other Edge Server will stop.</span></span> 
  
18. <span data-ttu-id="0298f-231">次の画面で [**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0298f-231">Click **Finish** on the next screen.</span></span>
    
19. <span data-ttu-id="0298f-232">今すぐことができますこの最新の技術を公開し、指示に従って、 [Skype ビジネス サーバー用にエッジ サーバーの展開](deploy-edge-servers.md)でここから、エッジ サーバーを展開します。</span><span class="sxs-lookup"><span data-stu-id="0298f-232">Now you'll be able to publish this updated technology, and follow the instructions in [Deploy Edge Servers in Skype for Business Server](deploy-edge-servers.md) to deploy to your Edge Server from here.</span></span>
    
### <a name="defining-the-topology-for-a-hardware-load-balanced-edge-server-pool"></a><span data-ttu-id="0298f-233">分散されたエッジ サーバー プールのハードウェアによる負荷のトポロジを定義します。</span><span class="sxs-lookup"><span data-stu-id="0298f-233">Defining the topology for a hardware load balanced Edge Server pool</span></span>

1. <span data-ttu-id="0298f-234">ビジネス サーバーの Standard Edition サーバーには、Skype、Skype のビジネス サーバーのフロント エンド サーバーへのログオンします。</span><span class="sxs-lookup"><span data-stu-id="0298f-234">Log onto your Skype for Business Server Standard Edition server, or a Skype for Business Server Front End Server.</span></span>
    
2. <span data-ttu-id="0298f-235">**ビジネス サーバー トポロジ ビルダーの Skype**を開く、1 回。</span><span class="sxs-lookup"><span data-stu-id="0298f-235">Once there, open **Skype for Business Server Topology Builder**.</span></span>
    
3. <span data-ttu-id="0298f-236">コンソール ツリーで、エッジ サーバーを展開しようとしているサイトを展開します。</span><span class="sxs-lookup"><span data-stu-id="0298f-236">In the console tree, expand the site you're going to deploy the Edge Server to.</span></span>
    
4. <span data-ttu-id="0298f-237">**エッジ プール**を右クリックし、**新しいエッジ プール**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0298f-237">Right-click **Edge pools**, and then click **New Edge pool**.</span></span>
    
5. <span data-ttu-id="0298f-238">**プールの新しいエッジの定義**] 画面で**次へ**をクリックするでしょう。</span><span class="sxs-lookup"><span data-stu-id="0298f-238">You'll click **Next** on the **Define New Edge pool** screen.</span></span>
    
6. <span data-ttu-id="0298f-239">[**エッジ プール FQDN の定義**] 画面では、エッジ プールを使用している内部の完全修飾ドメイン名 (FQDN) を入力し、**複数コンピューターのプール**、**次へ**完了をクリックするとを選択します。</span><span class="sxs-lookup"><span data-stu-id="0298f-239">On the **Define the Edge pool FQDN** screen, type the internal fully qualified domain name (FQDN) that the Edge pool is going to use, and select **Multiple computer pool**, clicking **Next** when done.</span></span>
    
7. <span data-ttu-id="0298f-240">[**機能の選択**] 画面には、次の選択肢があります。</span><span class="sxs-lookup"><span data-stu-id="0298f-240">On the **Select features** screen, you have a choice:</span></span>
    
   - <span data-ttu-id="0298f-241">SIP アクセス サービス、ビジネス サーバー Web カンファレンス サービスでは、Skype、A に同じ FQDN と IP アドレスを使用すると音声ビデオ エッジ サービスです。</span><span class="sxs-lookup"><span data-stu-id="0298f-241">You may intend to use the same FQDN and IP address for your SIP Access service, your Skype for Business Server Web Conferencing Service, and your A/V Edge service.</span></span> <span data-ttu-id="0298f-242">**単一の FQDN と IP アドレス チェック ボックスを使用**する」を選択 (および、注意してください以下の手順 9 に) する必要がある場合は、</span><span class="sxs-lookup"><span data-stu-id="0298f-242">If so, you need to choose the **Use a single FQDN and IP address checkbox** (and keep this in mind for Step 9 below)</span></span>
    
   - <span data-ttu-id="0298f-243">フェデレーションを有効にする計画がある場合は、[**このエッジ プールのフェデレーションを有効化 (ポート 5061)**] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="0298f-243">If you're planning to enable federation, choose the **Enable federation for this Edge pool (Port 5061)** check box.</span></span>
    
8. <span data-ttu-id="0298f-p133">[**次へ**] をクリックすると、[**IP オプション**] 画面に移動します。次のオプションが使用できます。</span><span class="sxs-lookup"><span data-stu-id="0298f-p133">Once you've clicked **Next**, you'll find yourself on the **IP Options** screen. Your options are as follows:</span></span>
    
   - <span data-ttu-id="0298f-246">内部インターフェイスで IPv4 を有効にする</span><span class="sxs-lookup"><span data-stu-id="0298f-246">Enable IPv4 on the internal interface</span></span>
    
   - <span data-ttu-id="0298f-247">内部インターフェイスで IPv6 を有効にする</span><span class="sxs-lookup"><span data-stu-id="0298f-247">Enable IPv6 on the internal interface</span></span>
    
   - <span data-ttu-id="0298f-248">外部インターフェイスで IPv4 を有効にする</span><span class="sxs-lookup"><span data-stu-id="0298f-248">Enable IPv4 on the external interface</span></span>
    
   - <span data-ttu-id="0298f-249">外部インターフェイスで IPv6 を有効にする</span><span class="sxs-lookup"><span data-stu-id="0298f-249">Enable IPv6 on the external interface</span></span>
    
     <span data-ttu-id="0298f-250">これらは、IPv4 または IPv6 アドレスを使用しているし、適用するこれらのアドレス、エッジ サーバーの内部または外部かどうか一目瞭然ですが、(手順 11 に留意してくださいこの必要があります)。</span><span class="sxs-lookup"><span data-stu-id="0298f-250">These are pretty self-explanatory, whether you're using IPv4 or IPv6 addresses, and you're applying those addresses on your Edge Server internally or externally (you'll need to keep this in mind for Step 11).</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="0298f-251">オプションとは異なり、他の 2 つのトポロジ、ハードウェア ロード バランサーを使用する場合、**必要がない**オプションを選択**エッジ プールの外部 IP アドレスが NAT によって変換されます**。</span><span class="sxs-lookup"><span data-stu-id="0298f-251">Unlike the other two topology options, when using a hardware load balancer, you **MUST NOT** select the option **The external IP address of the Edge Pool is translated by NAT**.</span></span> <span data-ttu-id="0298f-252">これは**サポートされていません**。</span><span class="sxs-lookup"><span data-stu-id="0298f-252">This is **not supported**.</span></span>
  
9. <span data-ttu-id="0298f-253">[外部 FQDN] 画面の選択肢は、上記の手順 7. で行った選択内容に応じて異なります。</span><span class="sxs-lookup"><span data-stu-id="0298f-253">On the External FQDNs screen, your choices depend on the selection you made in Step 7 above.</span></span>
    
   - <span data-ttu-id="0298f-254">**単一の FQDN と IP アドレスを使う**] チェック ボックスをオンにした場合、[ **SIP アクセス**] ボックスで、1 つの外部 FQDN を入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0298f-254">If you checked the **Use a single FQDN and IP Address** check box, you need to enter your single external FQDN in the **SIP Access** box.</span></span> <span data-ttu-id="0298f-255">エッジ サービスごとに個別に接続するためにすべてを許可する別のポート番号を入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0298f-255">Then you'll need to enter different port numbers for each edge service to allow them all to connect independently.</span></span> <span data-ttu-id="0298f-256">[**SIP アクセス**] エッジ サービスには 5061、[**Web 会議**] エッジ サービスには 444、[**音声ビデオ**] エッジ サービスには 443 を指定することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="0298f-256">We recommend 5061 for the **SIP Access** Edge service, 444 for the **Web Conferencing** Edge service, and 443 for the **A/V** Edge service.</span></span> <span data-ttu-id="0298f-257">作業が完了したら [**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0298f-257">Click **Next** when done.</span></span>
    
   - <span data-ttu-id="0298f-258">場合は **、単一の FQDN と IP アドレスを使う**] チェック ボックスをチェックしていません、今すぐ必要**SIP アクセス**エッジ サービス、 **Web 会議**エッジ サービスの 3 つの外部 Fqdn を入力して、 **A/V**エッジのサービスです。</span><span class="sxs-lookup"><span data-stu-id="0298f-258">If you didn't check the **Use a single FQDN and IP Address** check box, you'll now need to enter the three external FQDNs for the **SIP Access** Edge service, the **Web Conferencing** Edge service, and the **A/V** Edge service.</span></span> <span data-ttu-id="0298f-259">作業が完了したら [**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0298f-259">Click **Next** when done.</span></span>
    
10. <span data-ttu-id="0298f-260">今すぐ**このプール内のコンピューターの定義**] 画面に達しています。</span><span class="sxs-lookup"><span data-stu-id="0298f-260">Now you've reached the **Define the computers in this pool** screen.</span></span> <span data-ttu-id="0298f-261">**[追加**] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="0298f-261">Click the **Add** button.</span></span>
    
11. <span data-ttu-id="0298f-262">さて、**内部 IP アドレスを定義する**画面です。</span><span class="sxs-lookup"><span data-stu-id="0298f-262">You're now on the **Define the Internal IP address** screen.</span></span> <span data-ttu-id="0298f-263">ここには、**内部の IPv4 アドレス**と**内部の IPv6 アドレス**テキスト ボックスに、手順 8 で行った選択によっては、エッジ サーバーの IP アドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="0298f-263">Here you'll type the IP address of your Edge Server in the **Internal IPv4 address** and **Internal IPv6 address** text boxes, depending on the choices you made back in Step 8.</span></span> <span data-ttu-id="0298f-264">[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0298f-264">Click **Next** when ready.</span></span>
    
12. <span data-ttu-id="0298f-265">[**外部 IP アドレスの定義**] 画面では、以前の選択内容に応じた複数のオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="0298f-265">On the **Define the External IP address** screen, you have a few options depending on your previous choices:</span></span>
    
    - <span data-ttu-id="0298f-266">すべてのサービスに単一の FQDN を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="0298f-266">You may be using a single FQDN for all services.</span></span> <span data-ttu-id="0298f-267">場合は、 **SIP アクセス**] テキスト ボックスに、外部 IPv4 アドレスまたは IPv6 アドレス (どちらを使用している) を入力し、し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0298f-267">If so, type your external IPv4 or IPv6 address (whichever you're using) into the **SIP Access** text box, and then click **Next**.</span></span>
    
    - <span data-ttu-id="0298f-268">可能性がありますしようとして別の 3 つの Fqdn と IP を使用してサービスのアドレスです。</span><span class="sxs-lookup"><span data-stu-id="0298f-268">You may have chosen to use three separate FQDNs and IP addresses for the services.</span></span> <span data-ttu-id="0298f-269">**SIP アクセス**エッジ サービス、 **Web 会議**エッジ サービスの外部の IPv4 または IPv6 アドレスを入力する場合と**A/V**エッジのサービス、し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0298f-269">If that's the case, enter your external IPv4 or IPv6 addresses for the **SIP Access** Edge service, the **Web Conferencing** Edge service, and the **A/V** Edge service, and then click **Next**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="0298f-p141">以前に IPv6 アドレスを有効にして割り当てることを選択しなかった場合、このダイアログ ボックスは表示されません。これで問題はないため、次の手順に進みます。</span><span class="sxs-lookup"><span data-stu-id="0298f-p141">If you didn't previously choose to enable and assign IPv6 addressing, you won't see this dialog box. That's normal, just go to the next step.</span></span> 
  
13. <span data-ttu-id="0298f-272">[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0298f-272">Click **Finish**.</span></span> <span data-ttu-id="0298f-273">**このプール内のコンピューターの定義**] ダイアログ ボックスで作成したエッジ サーバーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0298f-273">The Edge Server you just created should now be listed in the **Define the computers in this pool** dialog box.</span></span>
    
14. <span data-ttu-id="0298f-274">**このプール内のコンピューターの定義**] 画面で、[**追加**] ボタンをもう一度クリックしてをこのプール内のすべてのエッジ サーバーを追加するまで、手順 11 ~ 13 を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="0298f-274">While still on the **Define the computers in this pool** screen, click the **Add** button again and repeat steps 11 through 13 until you've added all the Edge Servers you intend to have in this pool.</span></span> <span data-ttu-id="0298f-275">作業が完了したら、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0298f-275">When this is complete, click **Next**.</span></span>
    
15. <span data-ttu-id="0298f-276">次に表示される画面は [**次ホップの定義**] です。</span><span class="sxs-lookup"><span data-stu-id="0298f-276">Next screen up is **Define the next hop**.</span></span> <span data-ttu-id="0298f-277">[**次ホップ プール**] ボックスで、フロント エンド プールまたはスタンドアロンのプールがありますが、内部プールの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="0298f-277">In the **Next hop pool** box, select the name of your internal pool, which might be a Front End pool or a Standalone pool.</span></span> <span data-ttu-id="0298f-278">環境内でのディレクターをした場合は、ダイレクタを選択してください。</span><span class="sxs-lookup"><span data-stu-id="0298f-278">If you have a Director in your environment, you should choose the Director.</span></span> <span data-ttu-id="0298f-279">続いて [ **次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0298f-279">Then click **Next**.</span></span>
    
16. <span data-ttu-id="0298f-280">**プールのフロント エンドの関連付け**] 画面で、[1 つまたは複数内部プール、フロント エンド プール、このエッジ サーバーと関連付けるには、Standard Edition プールなどを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0298f-280">On the **Associate Front End pools** screen, you'll need to specify one or more internal pools, including Front End pools and Standard Edition pools, to associate with this Edge Server.</span></span> <span data-ttu-id="0298f-281">サポートされている外部ユーザーと通信するためにこのエッジ サーバーを使用して内部のプールの名前を選択するだけです。</span><span class="sxs-lookup"><span data-stu-id="0298f-281">Just choose the names of the internal pools you want using this Edge Server to communicate with supported external users.</span></span> <span data-ttu-id="0298f-282">[ **次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0298f-282">Click **Next**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="0298f-283">ここで注意すべきものでは、内部プールまたはスタンドアロン サーバーは、既にを使用している別の Skype ビジネス エッジ サーバーの場合は、複数のアソシエーションがあることはできません。</span><span class="sxs-lookup"><span data-stu-id="0298f-283">Something to keep in mind here is, if your internal pools or standalone servers are already using a different Skype for Business Server Edge Server, they can't have multiple associations.</span></span> <span data-ttu-id="0298f-284">場合は、内部プールまたはそのような状況では、スタンドアロン サーバーを選択すると、警告が表示される、他のエッジ サーバーを紹介して、続行するかどうするかどうかを決定できますが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0298f-284">If you choose an internal pool or standalone server that's in that situation, you'll see a warning appear telling you about the other Edge Server, and you can decide whether you want to continue or not.</span></span> <span data-ttu-id="0298f-285">この新しい関連付けにさあ、他のエッジ サーバーへの接続を停止します。</span><span class="sxs-lookup"><span data-stu-id="0298f-285">If you go ahead with this new association, the connection to the other Edge Server will stop.</span></span> 
  
17. <span data-ttu-id="0298f-286">次の画面で [**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0298f-286">Click **Finish** on the next screen.</span></span>
    
18. <span data-ttu-id="0298f-287">今すぐことができますこの最新の技術を公開し、指示に従って、 [Skype ビジネス サーバー用にエッジ サーバーの展開](deploy-edge-servers.md)でここから、エッジ サーバーを展開します。</span><span class="sxs-lookup"><span data-stu-id="0298f-287">Now you'll be able to publish this updated technology, and follow the instructions in [Deploy Edge Servers in Skype for Business Server](deploy-edge-servers.md) to deploy to your Edge Server from here.</span></span>
    
## <a name="publish-your-edge-server-topology"></a><span data-ttu-id="0298f-288">エッジ サーバー トポロジを公開する</span><span class="sxs-lookup"><span data-stu-id="0298f-288">Publish your Edge Server topology</span></span>

<span data-ttu-id="0298f-289">上記の手順が終了したら後、はビジネス エッジ サーバーまたはエッジ プールのため、Skype にエクスポートすることができますが、新しいこのトポロジを公開します。</span><span class="sxs-lookup"><span data-stu-id="0298f-289">Once you've finished the steps above, it's time to publish this new topology, which will also allow you to export it to your Skype for Business Server Edge Server or Edge pool.</span></span> <span data-ttu-id="0298f-290">これらの手順に従います。</span><span class="sxs-lookup"><span data-stu-id="0298f-290">Follow these steps:</span></span>
  
1. <span data-ttu-id="0298f-291">**トポロジ ビルダー**を起動します (以前の手順でまだ起動されていない場合)。</span><span class="sxs-lookup"><span data-stu-id="0298f-291">Start **Topology Builder** (if it's not started already from the previous procedure).</span></span>
    
2. <span data-ttu-id="0298f-292">**トポロジ ビルダー**のコンソール ツリーでは、 **Skype**を右クリックし、 **Skype ビジネス サーバー トポロジ ビルダー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0298f-292">In **Topology Builder**, in the console tree, right-click **Skype for Business Server** and then click **Skype for Business Server Topology Builder**.</span></span>
    
3. <span data-ttu-id="0298f-293">ウィザードの [**ようこそ**] ページで、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0298f-293">On the **Welcome** page of the wizard, click **Next**.</span></span>
    
4. <span data-ttu-id="0298f-294">[**他のデータベースの作成**] ページで、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0298f-294">On the **Create other databases** page, click **Next**.</span></span>
    
5. <span data-ttu-id="0298f-295">状態に、データベースが正常に作成されたことが示されたら、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="0298f-295">When the status indicates that the database creation succeeded, do the following:</span></span>
    
    - <span data-ttu-id="0298f-296">ログを表示するには、[**ログの表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0298f-296">To view the log, click **View log**.</span></span>
    
    - <span data-ttu-id="0298f-297">ウィザードを閉じるには、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0298f-297">To close the wizard, click **Finish**.</span></span>
    
## <a name="export-your-edge-server-topology"></a><span data-ttu-id="0298f-298">エッジ サーバー トポロジをエクスポートする</span><span class="sxs-lookup"><span data-stu-id="0298f-298">Export your Edge Server topology</span></span>

<span data-ttu-id="0298f-299">正常に展開するには、ビジネス サーバーの展開ウィザードの Skype には、中央管理ストアのデータへのアクセスが必要があります。</span><span class="sxs-lookup"><span data-stu-id="0298f-299">To deploy successfully, the Skype for Business Server Deployment Wizard needs access to the Central Management store data.</span></span> <span data-ttu-id="0298f-300">ドメインまたはフォレスト内の内部サーバーの場合、通常、この作業は単純です。</span><span class="sxs-lookup"><span data-stu-id="0298f-300">For internal servers in your domain or forest, this typically is straightforward.</span></span> <span data-ttu-id="0298f-301">エッジ トランスポート サーバーは、ドメインの外部では、物理メディア上では通常、エッジ サーバーの場所に手動でトポロジ ファイルをエクスポートする必要があるため。</span><span class="sxs-lookup"><span data-stu-id="0298f-301">Edge Servers are outside of the domain, and so it's necessary to manually export the topology file to the Edge Server location, usually on a physical media.</span></span> <span data-ttu-id="0298f-302">このエクスポートは、次のように PowerShell を介して行われます。</span><span class="sxs-lookup"><span data-stu-id="0298f-302">This export is done via PowerShell:</span></span>
  
1. <span data-ttu-id="0298f-303">**Skype ビジネス サーバー管理シェル**を起動します。</span><span class="sxs-lookup"><span data-stu-id="0298f-303">Start the **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="0298f-304">**ビジネス サーバー管理シェルの Skype**で、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="0298f-304">In the **Skype for Business Server Management Shell**, run the following:</span></span>
    
   ```
   Export-CsConfiguration -FileName <ConfigurationFilePath.zip>
   ```

3. <span data-ttu-id="0298f-305">外部メディア (たとえば、USB ドライブまたはネットワーク共有エッジ サーバーの場所からに到達することができます) には、エクスポートされたファイルをコピーします。</span><span class="sxs-lookup"><span data-stu-id="0298f-305">Copy the exported file to external media (for example, a USB drive or network share that you can reach from the Edge Server's location).</span></span>
    

