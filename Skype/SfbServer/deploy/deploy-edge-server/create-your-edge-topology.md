---
title: Skype for Business Server のエッジ トポロジを作成する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 5ea18841-afdc-4ccb-8d86-30584c1f5aca
description: '概要: Skype for Business Server でエッジ サーバー トポロジを構築、公開、エクスポートする方法について学習します。'
ms.openlocfilehash: 8dff318b5d198eb1e8d59ef465bf648125f31327
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804397"
---
# <a name="create-your-edge-topology-for-skype-for-business-server"></a><span data-ttu-id="d5632-103">Skype for Business Server のエッジ トポロジを作成する</span><span class="sxs-lookup"><span data-stu-id="d5632-103">Create your Edge topology for Skype for Business Server</span></span>
 
<span data-ttu-id="d5632-104">**概要:** Skype for Business Server でエッジ サーバー トポロジを構築、公開、エクスポートする方法について学習します。</span><span class="sxs-lookup"><span data-stu-id="d5632-104">**Summary:** Learn how to build, publish, and export your Edge Server topology in Skype for Business Server.</span></span>
  
<span data-ttu-id="d5632-105">トポロジ ビルダーは、Skype for Business Server のトポロジ コンポーネントで使用されるのと同様に、エッジ サーバー トポロジの構築に使用する必要があるツールです。</span><span class="sxs-lookup"><span data-stu-id="d5632-105">Topology Builder is the tool you need to use to build your Edge Server topology, just as it's used for any topology component for Skype for Business Server.</span></span> <span data-ttu-id="d5632-106">以下の手順を実行する前に、少なくとも 1 つのフロントエンド プールまたは Standard Edition サーバーをセットアップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d5632-106">Before following the steps below, you will need to have set up at least one Front End pool or a Standard Edition server.</span></span>
  
<span data-ttu-id="d5632-107">この記事では、次のトピックについて説明します。</span><span class="sxs-lookup"><span data-stu-id="d5632-107">We cover the following topics in this article:</span></span>
  
- <span data-ttu-id="d5632-108">エッジ サーバー トポロジを構築する</span><span class="sxs-lookup"><span data-stu-id="d5632-108">Build your Edge Server topology</span></span>
    
- <span data-ttu-id="d5632-109">エッジ サーバー トポロジの公開</span><span class="sxs-lookup"><span data-stu-id="d5632-109">Publish your Edge Server topology</span></span>
    
- <span data-ttu-id="d5632-110">エッジ サーバー トポロジをエクスポートする</span><span class="sxs-lookup"><span data-stu-id="d5632-110">Export your Edge Server topology</span></span>
    
  > [!NOTE]
  > <span data-ttu-id="d5632-111">以下の手順を実行するには、次に示すドメイン サーバーに、次のドメイン グループのメンバーであるユーザーとしてログインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d5632-111">To follow the steps below, you're going to need to log into the domain servers mentioned below as a user who's a member of the following domain groups:</span></span> 
  
- <span data-ttu-id="d5632-112">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="d5632-112">RTCUniversalServerAdmins</span></span>
    
- <span data-ttu-id="d5632-113">Domain Admins</span><span class="sxs-lookup"><span data-stu-id="d5632-113">Domain Admins</span></span>
    
## <a name="build-your-edge-server-topology"></a><span data-ttu-id="d5632-114">エッジ サーバー トポロジを構築する</span><span class="sxs-lookup"><span data-stu-id="d5632-114">Build your Edge Server topology</span></span>

<span data-ttu-id="d5632-115">最初の展開手順は、次の 3 つのオプションから構成される Skype for Business Server エッジ サーバー トポロジの構築です。</span><span class="sxs-lookup"><span data-stu-id="d5632-115">The first deployment step is building your Skype for Business Server Edge Server topology, which consists of one of three options:</span></span>
  
- <span data-ttu-id="d5632-116">単一のエッジ サーバー</span><span class="sxs-lookup"><span data-stu-id="d5632-116">A single Edge Server</span></span>
    
- <span data-ttu-id="d5632-117">DNS 負荷分散エッジ プール (1 つ以上のサーバー)</span><span class="sxs-lookup"><span data-stu-id="d5632-117">A DNS load balanced Edge pool (one or more servers)</span></span>
    
- <span data-ttu-id="d5632-118">ハードウェア負荷分散エッジ プール (1 つ以上のサーバー)</span><span class="sxs-lookup"><span data-stu-id="d5632-118">A hardware load balanced Edge pool (one or more servers)</span></span>
    
<span data-ttu-id="d5632-119">必要な情報が分からない場合は、次の手順を実行する前に、「計画」のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d5632-119">If you aren't sure what you need, then before you start following these steps, it's a good time to go over the Planning documentation.</span></span> <span data-ttu-id="d5632-120">それ以外の場合は、始めましょう。</span><span class="sxs-lookup"><span data-stu-id="d5632-120">Otherwise, let's begin.</span></span>
  
### <a name="defining-the-topology-for-a-single-edge-server"></a><span data-ttu-id="d5632-121">単一のエッジ サーバーのトポロジの定義</span><span class="sxs-lookup"><span data-stu-id="d5632-121">Defining the topology for a single Edge Server</span></span>

1. <span data-ttu-id="d5632-122">Skype for Business Server Standard Edition サーバーまたは Skype for Business Server フロントエンド プールにログオンします。</span><span class="sxs-lookup"><span data-stu-id="d5632-122">Log onto your Skype for Business Server Standard Edition server, or a Skype for Business Server Front End pool.</span></span>
    
2. <span data-ttu-id="d5632-123">その後 **、Skype for Business Server トポロジ ビルダーを開きます**。</span><span class="sxs-lookup"><span data-stu-id="d5632-123">Once there, open **Skype for Business Server Topology Builder**.</span></span>
    
3. <span data-ttu-id="d5632-124">コンソール ツリーで、エッジ サーバーの展開先のサイトを展開します。</span><span class="sxs-lookup"><span data-stu-id="d5632-124">In the console tree, expand the site you're going to deploy the Edge Server to.</span></span>
    
4. <span data-ttu-id="d5632-125">[エッジ プール **] を右クリックし**、[新しいエッジ プール] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="d5632-125">Right-click **Edge pools**, and then click **New Edge pool**.</span></span>
    
5. <span data-ttu-id="d5632-126">[新しいエッジ プール **の** 定義] **画面で [次へ] をクリック** します。</span><span class="sxs-lookup"><span data-stu-id="d5632-126">You'll click **Next** on the **Define New Edge pool** screen.</span></span>
    
6. <span data-ttu-id="d5632-127">[エッジ プール **の FQDN** の定義] 画面で、エッジ サーバーが使用する内部完全修飾ドメイン名 (FQDN) を入力し、[単一コンピュータープール] を選択し、完了したら [次へ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d5632-127">On the **Define the Edge pool FQDN** screen, type the internal fully qualified domain name (FQDN) that the Edge Server is going to use, and select **Single computer pool**, clicking **Next** when done.</span></span>
    
7. <span data-ttu-id="d5632-128">[機能 **の選択] 画面** には、次の選択肢があります。</span><span class="sxs-lookup"><span data-stu-id="d5632-128">On the **Select features** screen, you have a choice:</span></span>
    
   - <span data-ttu-id="d5632-129">SIP アクセス サービス、Skype for Business Server Web 会議サービス、音声ビデオ エッジ サービスに同じ FQDN と IP アドレスを使用する場合があります。</span><span class="sxs-lookup"><span data-stu-id="d5632-129">You may intend to use the same FQDN and IP address for your SIP Access service, your Skype for Business Server Web Conferencing service, and your A/V Edge service.</span></span> <span data-ttu-id="d5632-130">その場合は、[単一の **FQDN** と IP アドレスを使用する] チェック ボックスをオンにする必要があります (以下の手順 9 ではこの点に注意してください)。</span><span class="sxs-lookup"><span data-stu-id="d5632-130">If so, you need to choose the **Use a single FQDN and IP address checkbox** (and keep this in mind for Step 9 below)</span></span>
    
   - <span data-ttu-id="d5632-131">フェデレーションを有効にする予定の場合は、[このエッジ プールのフェデレーションを有効にする **(ポート 5061)** ] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="d5632-131">If you're planning to enable federation, choose the **Enable federation for this Edge pool (Port 5061)** check box.</span></span>
    
8. <span data-ttu-id="d5632-132">[次へ] **をクリック** すると、[IP オプション] 画面 **が表示** されます。</span><span class="sxs-lookup"><span data-stu-id="d5632-132">Once you've clicked **Next**, you'll find yourself on the **IP Options** screen.</span></span> <span data-ttu-id="d5632-133">オプションは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="d5632-133">Your options are as follows:</span></span>
    
   - <span data-ttu-id="d5632-134">内部インターフェイスで IPv4 を有効にする</span><span class="sxs-lookup"><span data-stu-id="d5632-134">Enable IPv4 on the internal interface</span></span>
    
   - <span data-ttu-id="d5632-135">内部インターフェイスで IPv6 を有効にする</span><span class="sxs-lookup"><span data-stu-id="d5632-135">Enable IPv6 on the internal interface</span></span>
    
   - <span data-ttu-id="d5632-136">外部インターフェイスで IPv4 を有効にする</span><span class="sxs-lookup"><span data-stu-id="d5632-136">Enable IPv4 on the external interface</span></span>
    
   - <span data-ttu-id="d5632-137">外部インターフェイスで IPv6 を有効にする</span><span class="sxs-lookup"><span data-stu-id="d5632-137">Enable IPv6 on the external interface</span></span>
    
   <span data-ttu-id="d5632-138">これらは、IPv4 アドレスと IPv6 アドレスの両方を使用している場合でも、そのアドレスを内部的または外部的にエッジ サーバーに適用する場合でも、非常に簡単です (手順 10 では、この点を念頭に置く必要があります)。</span><span class="sxs-lookup"><span data-stu-id="d5632-138">These are pretty self-explanatory, whether you're using IPv4 or IPv6 addresses, and you're applying those addresses on your Edge Server internally or externally (you'll need to keep this in mind for Step 10).</span></span> <span data-ttu-id="d5632-139">外部 IP アドレスにネットワーク アドレス変換 (NAT) アドレスを使用するためにエッジ サーバーまたはエッジ プールを構成するオプションもあります。</span><span class="sxs-lookup"><span data-stu-id="d5632-139">You also have the option of configuring your Edge Server or your Edge pool to use a network address translation (NAT) address for the external IP address.</span></span> <span data-ttu-id="d5632-140">これを行うには、NAT チェック ボックスでこのエッジ プールの外部 IP アドレスを変換 **するを** 選択します。</span><span class="sxs-lookup"><span data-stu-id="d5632-140">You can do this by choosing **The external IP address of this Edge pool is translated by NAT** check box .</span></span> <span data-ttu-id="d5632-141">準備ができたら **、[次へ** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d5632-141">Click **Next** when ready.</span></span>
    
9. <span data-ttu-id="d5632-142">[外部 FQDN] 画面では、上記の手順 7 で選択した内容によって選択内容が異なっています。</span><span class="sxs-lookup"><span data-stu-id="d5632-142">On the External FQDNs screen, your choices depend on the selection you made in Step 7 above.</span></span>
    
   - <span data-ttu-id="d5632-143">[単一の **FQDN** と IP アドレスを使用する] チェック ボックスをオンにした場合は、[SIP アクセス] ボックスに単一の外部 **FQDN を入力する必要** があります。</span><span class="sxs-lookup"><span data-stu-id="d5632-143">If you checked the **Use a single FQDN and IP Address** check box, you need to enter your single external FQDN in the **SIP Access** box.</span></span> <span data-ttu-id="d5632-144">次に、エッジ サービスごとに異なるポート番号を入力して、すべてのエッジ サービスが個別に接続できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="d5632-144">Then you'll need to enter different port numbers for each edge service to allow them all to connect independently.</span></span> <span data-ttu-id="d5632-145">**SIP** アクセス エッジ サービスには 5061、Web 会議エッジサービスには 444、音声ビデオ エッジサービスには 443 を推奨します。</span><span class="sxs-lookup"><span data-stu-id="d5632-145">We recommend 5061 for the **SIP Access** Edge service, 444 for the **Web Conferencing** Edge service, and 443 for the **A/V** Edge service.</span></span> <span data-ttu-id="d5632-146">操作が完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d5632-146">Click **Next** when done.</span></span>
    
   - <span data-ttu-id="d5632-147">[単一の FQDN と IP アドレスを使用する] チェック ボックスをオンにしなかった場合は、SIP アクセス エッジ サービス **、Web** 会議エッジ サービス、音声ビデオエッジ サービスの 3 つの外部 **FQDN** を入力する必要があります。 </span><span class="sxs-lookup"><span data-stu-id="d5632-147">If you didn't check the **Use a single FQDN and IP Address** check box, you'll now need to enter the three external FQDNs for the **SIP Access** Edge service, the **Web Conferencing** Edge service, and the **A/V** Edge service.</span></span> <span data-ttu-id="d5632-148">操作が完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d5632-148">Click **Next** when done.</span></span>
    
10. <span data-ttu-id="d5632-149">これで、[内部 IP アドレスの **定義] 画面が表示** されます。</span><span class="sxs-lookup"><span data-stu-id="d5632-149">You're now on the **Define the Internal IP address** screen.</span></span> <span data-ttu-id="d5632-150">ここでは、手順 8 で選択した内容に応じて、[内部 **IPv4** アドレス] ボックスと [内部 **IPv6** アドレス] テキスト ボックスにエッジ サーバーの IP アドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="d5632-150">Here you'll type the IP address of your Edge Server in the **Internal IPv4 address** and **Internal IPv6 address** text boxes, depending on the choices you made back in Step 8.</span></span> <span data-ttu-id="d5632-151">準備ができたら **、[次へ** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d5632-151">Click **Next** when ready.</span></span>
    
11. <span data-ttu-id="d5632-152">[ **外部 IP アドレスの** 定義] 画面には、以前の選択内容に応じていくつかのオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="d5632-152">On the **Define the External IP address** screen, you have a few options depending on your previous choices:</span></span>
    
    - <span data-ttu-id="d5632-153">すべてのサービスに 1 つの FQDN を使用している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d5632-153">You may be using a single FQDN for all services.</span></span> <span data-ttu-id="d5632-154">その場合は **、[SIP** アクセス] テキスト ボックスに外部 IPv4 アドレスまたは IPv6 アドレス (使用しているアドレス) を入力し、[次へ] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="d5632-154">If so, type your external IPv4 or IPv6 address (whichever you're using) into the **SIP Access** text box, and then click **Next**.</span></span>
    
    - <span data-ttu-id="d5632-155">サービスに 3 つの別々の FQDN と IP アドレスを使用する場合があります。</span><span class="sxs-lookup"><span data-stu-id="d5632-155">You may have chosen to use three separate FQDNs and IP addresses for the services.</span></span> <span data-ttu-id="d5632-156">その場合は **、SIP** アクセス エッジ サービス **、Web** 会議エッジ サービス、音声ビデオ エッジ サービスの外部 IPv4 アドレスまたはIPv6 アドレスを入力し、[次へ] をクリック **します。**</span><span class="sxs-lookup"><span data-stu-id="d5632-156">If that's the case, enter your external IPv4 or IPv6 addresses for the **SIP Access** Edge service, the **Web Conferencing** Edge service, and the **A/V** Edge service, and then click **Next**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="d5632-157">以前に IPv6 アドレスを有効にして割り当てなかった場合、このダイアログ ボックスは表示されます。</span><span class="sxs-lookup"><span data-stu-id="d5632-157">If you didn't previously choose to enable and assign IPv6 addressing, you won't see this dialog box.</span></span> <span data-ttu-id="d5632-158">これは通常、次の手順に進みます。</span><span class="sxs-lookup"><span data-stu-id="d5632-158">That's normal, just go to the next step.</span></span> 
  
12. <span data-ttu-id="d5632-159">手順 8 で NAT を使用し戻す場合は、パブリック IP アドレス テキスト ボックスが表示された画面 **が** 表示されます。</span><span class="sxs-lookup"><span data-stu-id="d5632-159">If you chose to use NAT back in Step 8, you'll now get a screen with a **Public IP address** textbox.</span></span> <span data-ttu-id="d5632-160">NAT によって変換するには、A/V エッジ サービスに設定したパブリック IPv4 アドレスまたは IPv6 アドレスを入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d5632-160">You'll need to enter the public IPv4 and/or IPv6 address you've set for the A/V Edge service, to be translated by NAT.</span></span> <span data-ttu-id="d5632-161">次に、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d5632-161">Then click **Next**.</span></span>
    
13. <span data-ttu-id="d5632-162">次の画面は次 **ホップの定義です**。</span><span class="sxs-lookup"><span data-stu-id="d5632-162">Next screen up is **Define the next hop**.</span></span> <span data-ttu-id="d5632-163">[次 **ホップ プール]** ボックスで、内部プールの名前 (フロントエンド プールまたはスタンドアロン プール) を選択します。</span><span class="sxs-lookup"><span data-stu-id="d5632-163">In the **Next hop pool** box, select the name of your internal pool, which might be a Front End pool or a Standalone pool.</span></span> <span data-ttu-id="d5632-164">環境にディレクターがある場合は、ディレクターを選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d5632-164">If you have a Director in your environment, you should choose the Director.</span></span> <span data-ttu-id="d5632-165">次に、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d5632-165">Then click **Next**.</span></span>
    
14. <span data-ttu-id="d5632-166">[フロントエンド **プールの** 関連付け] 画面で、このエッジ サーバーに関連付ける 1 つ以上の内部プール (フロントエンド プールと Standard Edition サーバーを含む) を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d5632-166">On the **Associate Front End pools** screen, you'll need to specify one or more internal pools, including Front End pools and Standard Edition servers, to associate with this Edge Server.</span></span> <span data-ttu-id="d5632-167">このエッジ サーバーを使用してサポートされている外部ユーザーと通信する内部プールの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="d5632-167">Just choose the names of the internal pools you want using this Edge Server to communicate with supported external users.</span></span> <span data-ttu-id="d5632-168">[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d5632-168">Click **Next**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="d5632-169">ここで念頭に置く必要があるのは、内部プールまたはスタンドアロン サーバーが既に別の Skype for Business Server エッジ サーバーを使用している場合、複数の関連付けを持てない、という意味です。</span><span class="sxs-lookup"><span data-stu-id="d5632-169">Something to keep in mind here is, if your internal pools or standalone servers are already using a different Skype for Business Server Edge Server, they can't have multiple associations.</span></span> <span data-ttu-id="d5632-170">その状況にある内部プールまたはスタンドアロン サーバーを選択すると、他のエッジ サーバーに関する警告が表示され、続行するかどうかを決定できます。</span><span class="sxs-lookup"><span data-stu-id="d5632-170">If you choose an internal pool or standalone server that's in that situation, you'll see a warning appear telling you about the other Edge Server, and you can decide whether you want to continue or not.</span></span> <span data-ttu-id="d5632-171">この新しい関連付けを続けて実行すると、他のエッジ サーバーへの接続が停止します。</span><span class="sxs-lookup"><span data-stu-id="d5632-171">If you go ahead with this new association, the connection to the other Edge Server will stop.</span></span> 
  
15. <span data-ttu-id="d5632-172">次 **の画面で [** 完了] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d5632-172">Click **Finish** on the next screen.</span></span>
    
16. <span data-ttu-id="d5632-173">これで、この更新されたテクノロジを公開し [、「Skype for Business Server](deploy-edge-servers.md) でエッジ サーバーを展開する」の手順に従って、ここからエッジ サーバーに展開できます。</span><span class="sxs-lookup"><span data-stu-id="d5632-173">Now you'll be able to publish this updated technology, and follow the instructions in [Deploy Edge Servers in Skype for Business Server](deploy-edge-servers.md) to deploy to your Edge Server from here.</span></span>
    
### <a name="defining-the-topology-for-a-dns-load-balanced-edge-server-pool"></a><span data-ttu-id="d5632-174">DNS 負荷分散エッジ サーバー プールのトポロジの定義</span><span class="sxs-lookup"><span data-stu-id="d5632-174">Defining the topology for a DNS load balanced Edge Server pool</span></span>

1. <span data-ttu-id="d5632-175">Skype for Business Server Standard Edition サーバーまたは Skype for Business Server フロントエンド サーバーにログオンします。</span><span class="sxs-lookup"><span data-stu-id="d5632-175">Log onto your Skype for Business Server Standard Edition server, or a Skype for Business Server Front End Server.</span></span>
    
2. <span data-ttu-id="d5632-176">その後 **、Skype for Business Server トポロジ ビルダーを開きます**。</span><span class="sxs-lookup"><span data-stu-id="d5632-176">Once there, open **Skype for Business Server Topology Builder**.</span></span>
    
3. <span data-ttu-id="d5632-177">コンソール ツリーで、エッジ サーバーの展開先のサイトを展開します。</span><span class="sxs-lookup"><span data-stu-id="d5632-177">In the console tree, expand the site you're going to deploy the Edge Server to.</span></span>
    
4. <span data-ttu-id="d5632-178">[エッジ プール **] を右クリックし**、[新しいエッジ プール] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="d5632-178">Right-click **Edge pools**, and then click **New Edge pool**.</span></span>
    
5. <span data-ttu-id="d5632-179">[新しいエッジ プール **の** 定義] **画面で [次へ] をクリック** します。</span><span class="sxs-lookup"><span data-stu-id="d5632-179">You'll click **Next** on the **Define New Edge pool** screen.</span></span>
    
6. <span data-ttu-id="d5632-180">[エッジ プール **の FQDN** の定義] 画面で、エッジ プールが使用する内部完全修飾ドメイン名 (FQDN) を入力し、[複数のコンピュータープール] を選択し、完了したら [次へ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d5632-180">On the **Define the Edge pool FQDN** screen, type the internal fully qualified domain name (FQDN) that the Edge pool is going to use, and select **Multiple computer pool**, clicking **Next** when done.</span></span>
    
7. <span data-ttu-id="d5632-181">[機能 **の選択] 画面** には、次の選択肢があります。</span><span class="sxs-lookup"><span data-stu-id="d5632-181">On the **Select features** screen, you have a choice:</span></span>
    
    - <span data-ttu-id="d5632-182">SIP アクセス サービス、Skype for Business Server Web 会議サービス、音声ビデオ エッジ サービスに同じ FQDN と IP アドレスを使用する場合があります。</span><span class="sxs-lookup"><span data-stu-id="d5632-182">You may intend to use the same FQDN and IP address for your SIP Access service, your Skype for Business Server Web Conferencing Service, and your A/V Edge service.</span></span> <span data-ttu-id="d5632-183">その場合は、[単一の **FQDN** と IP アドレスを使用する] チェック ボックスをオンにする必要があります (以下の手順 9 ではこの点に注意してください)。</span><span class="sxs-lookup"><span data-stu-id="d5632-183">If so, you need to choose the **Use a single FQDN and IP address checkbox** (and keep this in mind for Step 9 below)</span></span>
    
    - <span data-ttu-id="d5632-184">フェデレーションを有効にする予定の場合は、[このエッジ プールのフェデレーションを有効にする **(ポート 5061)** ] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="d5632-184">If you're planning to enable federation, choose the **Enable federation for this Edge pool (Port 5061)** check box.</span></span>
    
8. <span data-ttu-id="d5632-185">[次へ] **をクリック** すると、[IP オプション] 画面 **が表示** されます。</span><span class="sxs-lookup"><span data-stu-id="d5632-185">Once you've clicked **Next**, you'll find yourself on the **IP Options** screen.</span></span> <span data-ttu-id="d5632-186">オプションは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="d5632-186">Your options are as follows:</span></span>
    
    - <span data-ttu-id="d5632-187">内部インターフェイスで IPv4 を有効にする</span><span class="sxs-lookup"><span data-stu-id="d5632-187">Enable IPv4 on the internal interface</span></span>
    
   - <span data-ttu-id="d5632-188">内部インターフェイスで IPv6 を有効にする</span><span class="sxs-lookup"><span data-stu-id="d5632-188">Enable IPv6 on the internal interface</span></span>
    
   - <span data-ttu-id="d5632-189">外部インターフェイスで IPv4 を有効にする</span><span class="sxs-lookup"><span data-stu-id="d5632-189">Enable IPv4 on the external interface</span></span>
    
   - <span data-ttu-id="d5632-190">外部インターフェイスで IPv6 を有効にする</span><span class="sxs-lookup"><span data-stu-id="d5632-190">Enable IPv6 on the external interface</span></span>
    
     <span data-ttu-id="d5632-191">これらは、IPv4 アドレスと IPv6 アドレスの両方を使用している場合でも、そのアドレスをエッジ サーバーに内部的または外部的に適用する場合でも、非常に簡単です (手順 11 でこの点を念頭に置く必要があります)。</span><span class="sxs-lookup"><span data-stu-id="d5632-191">These are pretty self-explanatory, whether you're using IPv4 or IPv6 addresses, and you're applying those addresses on your Edge Server internally or externally (you'll need to keep this in mind for Step 11).</span></span> <span data-ttu-id="d5632-192">外部 IP アドレスにネットワーク アドレス変換 (NAT) アドレスを使用するためにエッジ サーバーまたはエッジ プールを構成するオプションもあります。</span><span class="sxs-lookup"><span data-stu-id="d5632-192">You also have the option of configuring your Edge Server or your Edge pool to use a network address translation (NAT) address for the external IP address.</span></span> <span data-ttu-id="d5632-193">これを行うには、NAT チェック ボックスでこのエッジ プールの外部 IP アドレスを変換 **するを** 選択します。</span><span class="sxs-lookup"><span data-stu-id="d5632-193">You can do this by choosing **The external IP address of this Edge pool is translated by NAT** check box .</span></span> <span data-ttu-id="d5632-194">準備ができたら **、[次へ** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d5632-194">Click **Next** when ready.</span></span>
    
9. <span data-ttu-id="d5632-195">[外部 FQDN] 画面では、上記の手順 7 で選択した内容によって選択内容が異なっています。</span><span class="sxs-lookup"><span data-stu-id="d5632-195">On the External FQDNs screen, your choices depend on the selection you made in Step 7 above.</span></span>
    
   - <span data-ttu-id="d5632-196">[単一の **FQDN** と IP アドレスを使用する] チェック ボックスをオンにした場合は、[SIP アクセス] ボックスに単一の外部 **FQDN を入力する必要** があります。</span><span class="sxs-lookup"><span data-stu-id="d5632-196">If you checked the **Use a single FQDN and IP Address** check box, you need to enter your single external FQDN in the **SIP Access** box.</span></span> <span data-ttu-id="d5632-197">次に、エッジ サービスごとに異なるポート番号を入力して、すべてのエッジ サービスが個別に接続できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="d5632-197">Then you'll need to enter different port numbers for each edge service to allow them all to connect independently.</span></span> <span data-ttu-id="d5632-198">**SIP** アクセス エッジ サービスには 5061、Web 会議エッジサービスには 444、音声ビデオ エッジサービスには 443 を推奨します。</span><span class="sxs-lookup"><span data-stu-id="d5632-198">We recommend 5061 for the **SIP Access** Edge service, 444 for the **Web Conferencing** Edge service, and 443 for the **A/V** Edge service.</span></span> <span data-ttu-id="d5632-199">操作が完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d5632-199">Click **Next** when done.</span></span>
    
   - <span data-ttu-id="d5632-200">[単一の FQDN と IP アドレスを使用する] チェック ボックスをオンにしなかった場合は、SIP アクセス エッジ サービス **、Web** 会議エッジ サービス、音声ビデオエッジ サービスの 3 つの外部 **FQDN** を入力する必要があります。 </span><span class="sxs-lookup"><span data-stu-id="d5632-200">If you didn't check the **Use a single FQDN and IP Address** check box, you'll now need to enter the three external FQDNs for the **SIP Access** Edge service, the **Web Conferencing** Edge service, and the **A/V** Edge service.</span></span> <span data-ttu-id="d5632-201">操作が完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d5632-201">Click **Next** when done.</span></span>
    
10. <span data-ttu-id="d5632-202">これで、[このプールの **コンピューターの定義] 画面に到達** しました。</span><span class="sxs-lookup"><span data-stu-id="d5632-202">Now you've reached the **Define the computers in this pool** screen.</span></span> <span data-ttu-id="d5632-203">[**追加**] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="d5632-203">Click the **Add** button.</span></span>
    
11. <span data-ttu-id="d5632-204">これで、[内部 IP アドレスの **定義] 画面が表示** されます。</span><span class="sxs-lookup"><span data-stu-id="d5632-204">You're now on the **Define the Internal IP address** screen.</span></span> <span data-ttu-id="d5632-205">ここでは、手順 8 で選択した内容に応じて、[内部 **IPv4** アドレス] ボックスと [内部 **IPv6** アドレス] テキスト ボックスにエッジ サーバーの IP アドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="d5632-205">Here you'll type the IP address of your Edge Server in the **Internal IPv4 address** and **Internal IPv6 address** text boxes, depending on the choices you made back in Step 8.</span></span> <span data-ttu-id="d5632-206">準備ができたら **、[次へ** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d5632-206">Click **Next** when ready.</span></span>
    
12. <span data-ttu-id="d5632-207">[ **外部 IP アドレスの** 定義] 画面には、以前の選択内容に応じていくつかのオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="d5632-207">On the **Define the External IP address** screen, you have a few options depending on your previous choices:</span></span>
    
    - <span data-ttu-id="d5632-208">すべてのサービスに 1 つの FQDN を使用している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d5632-208">You may be using a single FQDN for all services.</span></span> <span data-ttu-id="d5632-209">その場合は **、[SIP** アクセス] テキスト ボックスに外部 IPv4 アドレスまたは IPv6 アドレス (使用しているアドレス) を入力し、[次へ] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="d5632-209">If so, type your external IPv4 or IPv6 address (whichever you're using) into the **SIP Access** text box, and then click **Next**.</span></span>
    
    - <span data-ttu-id="d5632-210">サービスに 3 つの別々の FQDN と IP アドレスを使用する場合があります。</span><span class="sxs-lookup"><span data-stu-id="d5632-210">You may have chosen to use three separate FQDNs and IP addresses for the services.</span></span> <span data-ttu-id="d5632-211">その場合は **、SIP** アクセス エッジ サービス **、Web** 会議エッジ サービス、音声ビデオ エッジ サービスの外部 IPv4 アドレスまたはIPv6 アドレスを入力し、[次へ] をクリック **します。**</span><span class="sxs-lookup"><span data-stu-id="d5632-211">If that's the case, enter your external IPv4 or IPv6 addresses for the **SIP Access** Edge service, the **Web Conferencing** Edge service, and the **A/V** Edge service, and then click **Next**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="d5632-212">以前に IPv6 アドレスを有効にして割り当てなかった場合、このダイアログ ボックスは表示されます。</span><span class="sxs-lookup"><span data-stu-id="d5632-212">If you didn't previously choose to enable and assign IPv6 addressing, you won't see this dialog box.</span></span> <span data-ttu-id="d5632-213">これは通常、次の手順に進みます。</span><span class="sxs-lookup"><span data-stu-id="d5632-213">That's normal, just go to the next step.</span></span> 
  
13. <span data-ttu-id="d5632-214">**[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d5632-214">Click **Finish**.</span></span> <span data-ttu-id="d5632-215">作成したエッジ サーバーが、[このプールのコンピューターの定義] ダイアログ **ボックスに** 表示されます。</span><span class="sxs-lookup"><span data-stu-id="d5632-215">The Edge Server you just created should now be listed in the **Define the computers in this pool** dialog box.</span></span>
    
14. <span data-ttu-id="d5632-216">[このプールのコンピューターの定義] 画面で、[追加]ボタンを再度クリックし、このプールに含まれるすべてのエッジ サーバーを追加するまで手順 11 ~ 13 を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="d5632-216">While still on the **Define the computers in this pool** screen, click the **Add** button again and repeat steps 11 through 13 until you've added all the Edge Servers you intend to have in this pool.</span></span> <span data-ttu-id="d5632-217">これが完了したら、[次へ] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="d5632-217">When this is complete, click **Next**.</span></span>
    
15. <span data-ttu-id="d5632-218">手順 8 で NAT を使用し戻す場合は、パブリック IP アドレス テキスト ボックスが表示された画面 **が** 表示されます。</span><span class="sxs-lookup"><span data-stu-id="d5632-218">If you chose to use NAT back in Step 8, you'll now get a screen with a **Public IP address** textbox.</span></span> <span data-ttu-id="d5632-219">NAT によって変換するには、A/V エッジ サービスに設定したパブリック IPv4 アドレスまたは IPv6 アドレスを入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d5632-219">You'll need to enter the public IPv4 and/or IPv6 address you've set for the A/V Edge service, to be translated by NAT.</span></span> <span data-ttu-id="d5632-220">次に、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d5632-220">Then click **Next**.</span></span>
    
16. <span data-ttu-id="d5632-221">次の画面は次 **ホップの定義です**。</span><span class="sxs-lookup"><span data-stu-id="d5632-221">Next screen up is **Define the next hop**.</span></span> <span data-ttu-id="d5632-222">[次 **ホップ プール]** ボックスで、内部プールの名前 (フロントエンド プールまたはスタンドアロン プール) を選択します。</span><span class="sxs-lookup"><span data-stu-id="d5632-222">In the **Next hop pool** box, select the name of your internal pool, which might be a Front End pool or a Standalone pool.</span></span> <span data-ttu-id="d5632-223">環境にディレクターがある場合は、ディレクターを選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d5632-223">If you have a Director in your environment, you should choose the Director.</span></span> <span data-ttu-id="d5632-224">次に、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d5632-224">Then click **Next**.</span></span>
    
17. <span data-ttu-id="d5632-225">[フロントエンド **プールの** 関連付け] 画面で、このエッジ サーバーに関連付ける 1 つ以上の内部プール (フロント エンド プールと Standard Edition プールを含む) を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d5632-225">On the **Associate Front End pools** screen, you'll need to specify one or more internal pools, including Front End pools and Standard Edition pools, to associate with this Edge Server.</span></span> <span data-ttu-id="d5632-226">このエッジ サーバーを使用してサポートされている外部ユーザーと通信する内部プールの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="d5632-226">Just choose the names of the internal pools you want using this Edge Server to communicate with supported external users.</span></span> <span data-ttu-id="d5632-227">[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d5632-227">Click **Next**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="d5632-228">ここで念頭に置く必要があるのは、内部プールまたはスタンドアロン サーバーが既に別の Skype for Business Server エッジ サーバーを使用している場合、複数の関連付けを持てない、という意味です。</span><span class="sxs-lookup"><span data-stu-id="d5632-228">Something to keep in mind here is, if your internal pools or standalone servers are already using a different Skype for Business Server Edge Server, they can't have multiple associations.</span></span> <span data-ttu-id="d5632-229">その状況にある内部プールまたはスタンドアロン サーバーを選択すると、他のエッジ サーバーに関する警告が表示され、続行するかどうかを決定できます。</span><span class="sxs-lookup"><span data-stu-id="d5632-229">If you choose an internal pool or standalone server that's in that situation, you'll see a warning appear telling you about the other Edge Server, and you can decide whether you want to continue or not.</span></span> <span data-ttu-id="d5632-230">この新しい関連付けを続けて実行すると、他のエッジ サーバーへの接続が停止します。</span><span class="sxs-lookup"><span data-stu-id="d5632-230">If you go ahead with this new association, the connection to the other Edge Server will stop.</span></span> 
  
18. <span data-ttu-id="d5632-231">次 **の画面で [** 完了] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d5632-231">Click **Finish** on the next screen.</span></span>
    
19. <span data-ttu-id="d5632-232">これで、この更新されたテクノロジを公開し [、「Skype for Business Server](deploy-edge-servers.md) でエッジ サーバーを展開する」の手順に従って、ここからエッジ サーバーに展開できます。</span><span class="sxs-lookup"><span data-stu-id="d5632-232">Now you'll be able to publish this updated technology, and follow the instructions in [Deploy Edge Servers in Skype for Business Server](deploy-edge-servers.md) to deploy to your Edge Server from here.</span></span>
    
### <a name="defining-the-topology-for-a-hardware-load-balanced-edge-server-pool"></a><span data-ttu-id="d5632-233">ハードウェア負荷分散エッジ サーバー プールのトポロジの定義</span><span class="sxs-lookup"><span data-stu-id="d5632-233">Defining the topology for a hardware load balanced Edge Server pool</span></span>

1. <span data-ttu-id="d5632-234">Skype for Business Server Standard Edition サーバーまたは Skype for Business Server フロントエンド サーバーにログオンします。</span><span class="sxs-lookup"><span data-stu-id="d5632-234">Log onto your Skype for Business Server Standard Edition server, or a Skype for Business Server Front End Server.</span></span>
    
2. <span data-ttu-id="d5632-235">その後 **、Skype for Business Server トポロジ ビルダーを開きます**。</span><span class="sxs-lookup"><span data-stu-id="d5632-235">Once there, open **Skype for Business Server Topology Builder**.</span></span>
    
3. <span data-ttu-id="d5632-236">コンソール ツリーで、エッジ サーバーの展開先のサイトを展開します。</span><span class="sxs-lookup"><span data-stu-id="d5632-236">In the console tree, expand the site you're going to deploy the Edge Server to.</span></span>
    
4. <span data-ttu-id="d5632-237">[エッジ プール **] を右クリックし**、[新しいエッジ プール] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="d5632-237">Right-click **Edge pools**, and then click **New Edge pool**.</span></span>
    
5. <span data-ttu-id="d5632-238">[新しいエッジ プール **の** 定義] **画面で [次へ] をクリック** します。</span><span class="sxs-lookup"><span data-stu-id="d5632-238">You'll click **Next** on the **Define New Edge pool** screen.</span></span>
    
6. <span data-ttu-id="d5632-239">[エッジ プール **の FQDN** の定義] 画面で、エッジ プールが使用する内部完全修飾ドメイン名 (FQDN) を入力し、[複数のコンピュータープール] を選択し、完了したら [次へ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d5632-239">On the **Define the Edge pool FQDN** screen, type the internal fully qualified domain name (FQDN) that the Edge pool is going to use, and select **Multiple computer pool**, clicking **Next** when done.</span></span>
    
7. <span data-ttu-id="d5632-240">[機能 **の選択] 画面** には、次の選択肢があります。</span><span class="sxs-lookup"><span data-stu-id="d5632-240">On the **Select features** screen, you have a choice:</span></span>
    
   - <span data-ttu-id="d5632-241">SIP アクセス サービス、Skype for Business Server Web 会議サービス、音声ビデオ エッジ サービスに同じ FQDN と IP アドレスを使用する場合があります。</span><span class="sxs-lookup"><span data-stu-id="d5632-241">You may intend to use the same FQDN and IP address for your SIP Access service, your Skype for Business Server Web Conferencing Service, and your A/V Edge service.</span></span> <span data-ttu-id="d5632-242">その場合は、[単一の **FQDN** と IP アドレスを使用する] チェック ボックスをオンにする必要があります (以下の手順 9 ではこの点に注意してください)。</span><span class="sxs-lookup"><span data-stu-id="d5632-242">If so, you need to choose the **Use a single FQDN and IP address checkbox** (and keep this in mind for Step 9 below)</span></span>
    
   - <span data-ttu-id="d5632-243">フェデレーションを有効にする予定の場合は、[このエッジ プールのフェデレーションを有効にする **(ポート 5061)** ] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="d5632-243">If you're planning to enable federation, choose the **Enable federation for this Edge pool (Port 5061)** check box.</span></span>
    
8. <span data-ttu-id="d5632-244">[次へ] **をクリック** すると、[IP オプション] 画面 **が表示** されます。</span><span class="sxs-lookup"><span data-stu-id="d5632-244">Once you've clicked **Next**, you'll find yourself on the **IP Options** screen.</span></span> <span data-ttu-id="d5632-245">オプションは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="d5632-245">Your options are as follows:</span></span>
    
   - <span data-ttu-id="d5632-246">内部インターフェイスで IPv4 を有効にする</span><span class="sxs-lookup"><span data-stu-id="d5632-246">Enable IPv4 on the internal interface</span></span>
    
   - <span data-ttu-id="d5632-247">内部インターフェイスで IPv6 を有効にする</span><span class="sxs-lookup"><span data-stu-id="d5632-247">Enable IPv6 on the internal interface</span></span>
    
   - <span data-ttu-id="d5632-248">外部インターフェイスで IPv4 を有効にする</span><span class="sxs-lookup"><span data-stu-id="d5632-248">Enable IPv4 on the external interface</span></span>
    
   - <span data-ttu-id="d5632-249">外部インターフェイスで IPv6 を有効にする</span><span class="sxs-lookup"><span data-stu-id="d5632-249">Enable IPv6 on the external interface</span></span>
    
     <span data-ttu-id="d5632-250">これらは、IPv4 アドレスと IPv6 アドレスの両方を使用している場合でも、そのアドレスをエッジ サーバーに内部的または外部的に適用する場合でも、非常に簡単です (手順 11 でこの点を念頭に置く必要があります)。</span><span class="sxs-lookup"><span data-stu-id="d5632-250">These are pretty self-explanatory, whether you're using IPv4 or IPv6 addresses, and you're applying those addresses on your Edge Server internally or externally (you'll need to keep this in mind for Step 11).</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="d5632-251">他の 2 つのトポロジ オプションとは異なり、ハードウェアロード バランサーを使用する場合は、NAT によってエッジ プールの外部 IP アドレスが変換されるオプションを選択 **しなけずにしてください**。</span><span class="sxs-lookup"><span data-stu-id="d5632-251">Unlike the other two topology options, when using a hardware load balancer, you **MUST NOT** select the option **The external IP address of the Edge Pool is translated by NAT**.</span></span> <span data-ttu-id="d5632-252">これはサポート **されていません**。</span><span class="sxs-lookup"><span data-stu-id="d5632-252">This is **not supported**.</span></span>
  
9. <span data-ttu-id="d5632-253">[外部 FQDN] 画面では、上記の手順 7 で選択した内容によって選択内容が異なっています。</span><span class="sxs-lookup"><span data-stu-id="d5632-253">On the External FQDNs screen, your choices depend on the selection you made in Step 7 above.</span></span>
    
   - <span data-ttu-id="d5632-254">[単一の **FQDN** と IP アドレスを使用する] チェック ボックスをオンにした場合は、[SIP アクセス] ボックスに単一の外部 **FQDN を入力する必要** があります。</span><span class="sxs-lookup"><span data-stu-id="d5632-254">If you checked the **Use a single FQDN and IP Address** check box, you need to enter your single external FQDN in the **SIP Access** box.</span></span> <span data-ttu-id="d5632-255">次に、エッジ サービスごとに異なるポート番号を入力して、すべてのエッジ サービスが個別に接続できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="d5632-255">Then you'll need to enter different port numbers for each edge service to allow them all to connect independently.</span></span> <span data-ttu-id="d5632-256">**SIP** アクセス エッジ サービスには 5061、Web 会議エッジサービスには 444、音声ビデオ エッジサービスには 443 を推奨します。</span><span class="sxs-lookup"><span data-stu-id="d5632-256">We recommend 5061 for the **SIP Access** Edge service, 444 for the **Web Conferencing** Edge service, and 443 for the **A/V** Edge service.</span></span> <span data-ttu-id="d5632-257">操作が完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d5632-257">Click **Next** when done.</span></span>
    
   - <span data-ttu-id="d5632-258">[単一の FQDN と IP アドレスを使用する] チェック ボックスをオンにしなかった場合は、SIP アクセス エッジ サービス **、Web** 会議エッジ サービス、音声ビデオエッジ サービスの 3 つの外部 **FQDN** を入力する必要があります。 </span><span class="sxs-lookup"><span data-stu-id="d5632-258">If you didn't check the **Use a single FQDN and IP Address** check box, you'll now need to enter the three external FQDNs for the **SIP Access** Edge service, the **Web Conferencing** Edge service, and the **A/V** Edge service.</span></span> <span data-ttu-id="d5632-259">操作が完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d5632-259">Click **Next** when done.</span></span>
    
10. <span data-ttu-id="d5632-260">これで、[このプールの **コンピューターの定義] 画面に到達** しました。</span><span class="sxs-lookup"><span data-stu-id="d5632-260">Now you've reached the **Define the computers in this pool** screen.</span></span> <span data-ttu-id="d5632-261">[**追加**] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="d5632-261">Click the **Add** button.</span></span>
    
11. <span data-ttu-id="d5632-262">これで、[内部 IP アドレスの **定義] 画面が表示** されます。</span><span class="sxs-lookup"><span data-stu-id="d5632-262">You're now on the **Define the Internal IP address** screen.</span></span> <span data-ttu-id="d5632-263">ここでは、手順 8 で選択した内容に応じて、[内部 **IPv4** アドレス] ボックスと [内部 **IPv6** アドレス] テキスト ボックスにエッジ サーバーの IP アドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="d5632-263">Here you'll type the IP address of your Edge Server in the **Internal IPv4 address** and **Internal IPv6 address** text boxes, depending on the choices you made back in Step 8.</span></span> <span data-ttu-id="d5632-264">準備ができたら **、[次へ** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d5632-264">Click **Next** when ready.</span></span>
    
12. <span data-ttu-id="d5632-265">[ **外部 IP アドレスの** 定義] 画面には、以前の選択内容に応じていくつかのオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="d5632-265">On the **Define the External IP address** screen, you have a few options depending on your previous choices:</span></span>
    
    - <span data-ttu-id="d5632-266">すべてのサービスに 1 つの FQDN を使用している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d5632-266">You may be using a single FQDN for all services.</span></span> <span data-ttu-id="d5632-267">その場合は **、[SIP** アクセス] テキスト ボックスに外部 IPv4 アドレスまたは IPv6 アドレス (使用しているアドレス) を入力し、[次へ] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="d5632-267">If so, type your external IPv4 or IPv6 address (whichever you're using) into the **SIP Access** text box, and then click **Next**.</span></span>
    
    - <span data-ttu-id="d5632-268">サービスに 3 つの別々の FQDN と IP アドレスを使用する場合があります。</span><span class="sxs-lookup"><span data-stu-id="d5632-268">You may have chosen to use three separate FQDNs and IP addresses for the services.</span></span> <span data-ttu-id="d5632-269">その場合は **、SIP** アクセス エッジ サービス **、Web** 会議エッジ サービス、音声ビデオ エッジ サービスの外部 IPv4 アドレスまたはIPv6 アドレスを入力し、[次へ] をクリック **します。**</span><span class="sxs-lookup"><span data-stu-id="d5632-269">If that's the case, enter your external IPv4 or IPv6 addresses for the **SIP Access** Edge service, the **Web Conferencing** Edge service, and the **A/V** Edge service, and then click **Next**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="d5632-270">以前に IPv6 アドレスを有効にして割り当てなかった場合、このダイアログ ボックスは表示されます。</span><span class="sxs-lookup"><span data-stu-id="d5632-270">If you didn't previously choose to enable and assign IPv6 addressing, you won't see this dialog box.</span></span> <span data-ttu-id="d5632-271">これは通常、次の手順に進みます。</span><span class="sxs-lookup"><span data-stu-id="d5632-271">That's normal, just go to the next step.</span></span> 
  
13. <span data-ttu-id="d5632-272">**[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d5632-272">Click **Finish**.</span></span> <span data-ttu-id="d5632-273">作成したエッジ サーバーが、[このプールのコンピューターの定義] ダイアログ **ボックスに** 表示されます。</span><span class="sxs-lookup"><span data-stu-id="d5632-273">The Edge Server you just created should now be listed in the **Define the computers in this pool** dialog box.</span></span>
    
14. <span data-ttu-id="d5632-274">[このプールのコンピューターの定義] 画面で、[追加]ボタンを再度クリックし、このプールに含まれるすべてのエッジ サーバーを追加するまで手順 11 ~ 13 を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="d5632-274">While still on the **Define the computers in this pool** screen, click the **Add** button again and repeat steps 11 through 13 until you've added all the Edge Servers you intend to have in this pool.</span></span> <span data-ttu-id="d5632-275">これが完了したら、[次へ] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="d5632-275">When this is complete, click **Next**.</span></span>
    
15. <span data-ttu-id="d5632-276">次の画面は次 **ホップの定義です**。</span><span class="sxs-lookup"><span data-stu-id="d5632-276">Next screen up is **Define the next hop**.</span></span> <span data-ttu-id="d5632-277">[次 **ホップ プール]** ボックスで、内部プールの名前 (フロントエンド プールまたはスタンドアロン プール) を選択します。</span><span class="sxs-lookup"><span data-stu-id="d5632-277">In the **Next hop pool** box, select the name of your internal pool, which might be a Front End pool or a Standalone pool.</span></span> <span data-ttu-id="d5632-278">環境にディレクターがある場合は、ディレクターを選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d5632-278">If you have a Director in your environment, you should choose the Director.</span></span> <span data-ttu-id="d5632-279">次に、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d5632-279">Then click **Next**.</span></span>
    
16. <span data-ttu-id="d5632-280">[フロントエンド **プールの** 関連付け] 画面で、このエッジ サーバーに関連付ける 1 つ以上の内部プール (フロント エンド プールと Standard Edition プールを含む) を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d5632-280">On the **Associate Front End pools** screen, you'll need to specify one or more internal pools, including Front End pools and Standard Edition pools, to associate with this Edge Server.</span></span> <span data-ttu-id="d5632-281">このエッジ サーバーを使用してサポートされている外部ユーザーと通信する内部プールの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="d5632-281">Just choose the names of the internal pools you want using this Edge Server to communicate with supported external users.</span></span> <span data-ttu-id="d5632-282">[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d5632-282">Click **Next**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="d5632-283">ここで念頭に置く必要があるのは、内部プールまたはスタンドアロン サーバーが既に別の Skype for Business Server エッジ サーバーを使用している場合、複数の関連付けを持てない、という意味です。</span><span class="sxs-lookup"><span data-stu-id="d5632-283">Something to keep in mind here is, if your internal pools or standalone servers are already using a different Skype for Business Server Edge Server, they can't have multiple associations.</span></span> <span data-ttu-id="d5632-284">その状況にある内部プールまたはスタンドアロン サーバーを選択すると、他のエッジ サーバーに関する警告が表示され、続行するかどうかを決定できます。</span><span class="sxs-lookup"><span data-stu-id="d5632-284">If you choose an internal pool or standalone server that's in that situation, you'll see a warning appear telling you about the other Edge Server, and you can decide whether you want to continue or not.</span></span> <span data-ttu-id="d5632-285">この新しい関連付けを続けて実行すると、他のエッジ サーバーへの接続が停止します。</span><span class="sxs-lookup"><span data-stu-id="d5632-285">If you go ahead with this new association, the connection to the other Edge Server will stop.</span></span> 
  
17. <span data-ttu-id="d5632-286">次 **の画面で [** 完了] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d5632-286">Click **Finish** on the next screen.</span></span>
    
18. <span data-ttu-id="d5632-287">これで、この更新されたテクノロジを公開し [、「Skype for Business Server](deploy-edge-servers.md) でエッジ サーバーを展開する」の手順に従って、ここからエッジ サーバーに展開できます。</span><span class="sxs-lookup"><span data-stu-id="d5632-287">Now you'll be able to publish this updated technology, and follow the instructions in [Deploy Edge Servers in Skype for Business Server](deploy-edge-servers.md) to deploy to your Edge Server from here.</span></span>
    
## <a name="publish-your-edge-server-topology"></a><span data-ttu-id="d5632-288">エッジ サーバー トポロジの公開</span><span class="sxs-lookup"><span data-stu-id="d5632-288">Publish your Edge Server topology</span></span>

<span data-ttu-id="d5632-289">上記の手順を完了したら、この新しいトポロジを公開します。これにより、Skype for Business Server エッジ サーバーまたはエッジ プールにエクスポートすることもできます。</span><span class="sxs-lookup"><span data-stu-id="d5632-289">Once you've finished the steps above, it's time to publish this new topology, which will also allow you to export it to your Skype for Business Server Edge Server or Edge pool.</span></span> <span data-ttu-id="d5632-290">次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="d5632-290">Follow these steps:</span></span>
  
1. <span data-ttu-id="d5632-291">トポロジ **ビルダーを起動** します (前の手順からまだ開始していない場合)。</span><span class="sxs-lookup"><span data-stu-id="d5632-291">Start **Topology Builder** (if it's not started already from the previous procedure).</span></span>
    
2. <span data-ttu-id="d5632-292">トポロジ **ビルダーの** コンソール ツリーで **、[Skype for Business Server]** を右クリックし、[Skype for Business Server トポロジ ビルダー] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="d5632-292">In **Topology Builder**, in the console tree, right-click **Skype for Business Server** and then click **Skype for Business Server Topology Builder**.</span></span>
    
3. <span data-ttu-id="d5632-293">ウィザードの [**ようこそ**] ページで、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d5632-293">On the **Welcome** page of the wizard, click **Next**.</span></span>
    
4. <span data-ttu-id="d5632-294">[**他のデータベースの作成**] ページで、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d5632-294">On the **Create other databases** page, click **Next**.</span></span>
    
5. <span data-ttu-id="d5632-295">状態がデータベースの作成が成功したと示された場合は、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="d5632-295">When the status indicates that the database creation succeeded, do the following:</span></span>
    
    - <span data-ttu-id="d5632-296">ログを表示するには、**[ログの表示]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d5632-296">To view the log, click **View log**.</span></span>
    
    - <span data-ttu-id="d5632-297">ウィザードを閉じるには、**[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d5632-297">To close the wizard, click **Finish**.</span></span>
    
## <a name="export-your-edge-server-topology"></a><span data-ttu-id="d5632-298">エッジ サーバー トポロジをエクスポートする</span><span class="sxs-lookup"><span data-stu-id="d5632-298">Export your Edge Server topology</span></span>

<span data-ttu-id="d5632-299">Skype for Business Server 展開ウィザードを正常に展開するには、中央管理ストアのデータにアクセスする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d5632-299">To deploy successfully, the Skype for Business Server Deployment Wizard needs access to the Central Management store data.</span></span> <span data-ttu-id="d5632-300">ドメインまたはフォレスト内の内部サーバーの場合、通常、これは簡単です。</span><span class="sxs-lookup"><span data-stu-id="d5632-300">For internal servers in your domain or forest, this typically is straightforward.</span></span> <span data-ttu-id="d5632-301">エッジ サーバーはドメインの外部にあるので、トポロジ ファイルをエッジ サーバーの場所 (通常は物理メディア) に手動でエクスポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d5632-301">Edge Servers are outside of the domain, and so it's necessary to manually export the topology file to the Edge Server location, usually on a physical media.</span></span> <span data-ttu-id="d5632-302">このエクスポートは、PowerShell を使用して行われます。</span><span class="sxs-lookup"><span data-stu-id="d5632-302">This export is done via PowerShell:</span></span>
  
1. <span data-ttu-id="d5632-303">Skype **for Business Server 管理シェルを起動します**。</span><span class="sxs-lookup"><span data-stu-id="d5632-303">Start the **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="d5632-304">Skype **for Business Server 管理シェルで、次** のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="d5632-304">In the **Skype for Business Server Management Shell**, run the following:</span></span>
    
   ```powershell
   Export-CsConfiguration -FileName <ConfigurationFilePath.zip>
   ```

3. <span data-ttu-id="d5632-305">エクスポートしたファイルを外部メディア (たとえば、エッジ サーバーの場所からアクセスできる USB ドライブやネットワーク共有) にコピーします。</span><span class="sxs-lookup"><span data-stu-id="d5632-305">Copy the exported file to external media (for example, a USB drive or network share that you can reach from the Edge Server's location).</span></span>
    

