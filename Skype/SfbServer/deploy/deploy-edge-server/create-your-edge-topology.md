---
title: Skype for Business Server の Edge トポロジを作成する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 5ea18841-afdc-4ccb-8d86-30584c1f5aca
description: '概要: Skype for Business Server で Edge Server トポロジを作成、公開、エクスポートする方法について説明します。'
ms.openlocfilehash: c2df17d107845309242ef1df156f2da56fa2b883
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34306959"
---
# <a name="create-your-edge-topology-for-skype-for-business-server"></a><span data-ttu-id="80f6f-103">Skype for Business Server の Edge トポロジを作成する</span><span class="sxs-lookup"><span data-stu-id="80f6f-103">Create your Edge topology for Skype for Business Server</span></span>
 
<span data-ttu-id="80f6f-104">**概要:** Skype for Business Server で Edge Server トポロジを作成、公開、エクスポートする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="80f6f-104">**Summary:** Learn how to build, publish, and export your Edge Server topology in Skype for Business Server.</span></span>
  
<span data-ttu-id="80f6f-105">トポロジビルダーは、Skype for Business Server のトポロジコンポーネントに使用されるのと同じように、エッジサーバートポロジの構築に使用する必要があるツールです。</span><span class="sxs-lookup"><span data-stu-id="80f6f-105">Topology Builder is the tool you need to use to build your Edge Server topology, just as it's used for any topology component for Skype for Business Server.</span></span> <span data-ttu-id="80f6f-106">以下の手順を実行する前に、少なくとも1つのフロントエンドプールまたは Standard Edition サーバーを設定しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="80f6f-106">Before following the steps below, you will need to have set up at least one Front End pool or a Standard Edition server.</span></span>
  
<span data-ttu-id="80f6f-107">この記事では、次のトピックを扱います。</span><span class="sxs-lookup"><span data-stu-id="80f6f-107">We cover the following topics in this article:</span></span>
  
- <span data-ttu-id="80f6f-108">エッジサーバートポロジを構築する</span><span class="sxs-lookup"><span data-stu-id="80f6f-108">Build your Edge Server topology</span></span>
    
- <span data-ttu-id="80f6f-109">エッジ サーバー トポロジを公開する</span><span class="sxs-lookup"><span data-stu-id="80f6f-109">Publish your Edge Server topology</span></span>
    
- <span data-ttu-id="80f6f-110">エッジ サーバー トポロジをエクスポートする</span><span class="sxs-lookup"><span data-stu-id="80f6f-110">Export your Edge Server topology</span></span>
    
  > [!NOTE]
  > <span data-ttu-id="80f6f-111">以下の手順に従うには、次のドメイン グループのメンバーであるユーザーとして、下記のドメイン サーバーにログインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="80f6f-111">To follow the steps below, you're going to need to log into the domain servers mentioned below as a user who's a member of the following domain groups:</span></span> 
  
- <span data-ttu-id="80f6f-112">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="80f6f-112">RTCUniversalServerAdmins</span></span>
    
- <span data-ttu-id="80f6f-113">Domain Admins</span><span class="sxs-lookup"><span data-stu-id="80f6f-113">Domain Admins</span></span>
    
## <a name="build-your-edge-server-topology"></a><span data-ttu-id="80f6f-114">エッジサーバートポロジを構築する</span><span class="sxs-lookup"><span data-stu-id="80f6f-114">Build your Edge Server topology</span></span>

<span data-ttu-id="80f6f-115">最初の展開手順では、次の3つのオプションのいずれかで構成される、Skype for Business Server Edge Server のトポロジを構築します。</span><span class="sxs-lookup"><span data-stu-id="80f6f-115">The first deployment step is building your Skype for Business Server Edge Server topology, which consists of one of three options:</span></span>
  
- <span data-ttu-id="80f6f-116">1つのエッジサーバー</span><span class="sxs-lookup"><span data-stu-id="80f6f-116">A single Edge Server</span></span>
    
- <span data-ttu-id="80f6f-117">DNS 負荷分散エッジプール (1 台以上のサーバー)</span><span class="sxs-lookup"><span data-stu-id="80f6f-117">A DNS load balanced Edge pool (one or more servers)</span></span>
    
- <span data-ttu-id="80f6f-118">ハードウェア負荷分散エッジプール (1 台以上のサーバー)</span><span class="sxs-lookup"><span data-stu-id="80f6f-118">A hardware load balanced Edge pool (one or more servers)</span></span>
    
<span data-ttu-id="80f6f-p102">必要なエッジが不明である場合は、以下の手順を開始する前に、「計画」のドキュメントを参照してください。不明でなければ、作業を開始します。</span><span class="sxs-lookup"><span data-stu-id="80f6f-p102">If you aren't sure what you need, then before you start following these steps, it's a good time to go over the Planning documentation. Otherwise, let's begin.</span></span>
  
### <a name="defining-the-topology-for-a-single-edge-server"></a><span data-ttu-id="80f6f-121">単一エッジサーバーのトポロジの定義</span><span class="sxs-lookup"><span data-stu-id="80f6f-121">Defining the topology for a single Edge Server</span></span>

1. <span data-ttu-id="80f6f-122">Skype for Business Server Standard Edition server、または Skype for Business Server フロントエンドプールにログオンします。</span><span class="sxs-lookup"><span data-stu-id="80f6f-122">Log onto your Skype for Business Server Standard Edition server, or a Skype for Business Server Front End pool.</span></span>
    
2. <span data-ttu-id="80f6f-123">**Skype For Business Server Topology Builder**を開きます。</span><span class="sxs-lookup"><span data-stu-id="80f6f-123">Once there, open **Skype for Business Server Topology Builder**.</span></span>
    
3. <span data-ttu-id="80f6f-124">コンソールツリーで、エッジサーバーを展開するサイトを展開します。</span><span class="sxs-lookup"><span data-stu-id="80f6f-124">In the console tree, expand the site you're going to deploy the Edge Server to.</span></span>
    
4. <span data-ttu-id="80f6f-125">[**エッジプール**] を右クリックし、[**新しいエッジプール**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="80f6f-125">Right-click **Edge pools**, and then click **New Edge pool**.</span></span>
    
5. <span data-ttu-id="80f6f-126">[**新しいエッジプールの定義**] 画面の [**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="80f6f-126">You'll click **Next** on the **Define New Edge pool** screen.</span></span>
    
6. <span data-ttu-id="80f6f-127">[ **Edge プールの FQDN の定義**] 画面で、エッジサーバーで使用する内部の完全修飾ドメイン名 (FQDN) を入力して、[**単一コンピュータープール**] を選択し、完了したら [**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="80f6f-127">On the **Define the Edge pool FQDN** screen, type the internal fully qualified domain name (FQDN) that the Edge Server is going to use, and select **Single computer pool**, clicking **Next** when done.</span></span>
    
7. <span data-ttu-id="80f6f-128">[**機能の選択**] 画面には、次の選択肢があります。</span><span class="sxs-lookup"><span data-stu-id="80f6f-128">On the **Select features** screen, you have a choice:</span></span>
    
   - <span data-ttu-id="80f6f-129">SIP アクセスサービス、Skype for Business Server Web 会議サービス、A/V Edge サービスには、同じ FQDN と IP アドレスを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="80f6f-129">You may intend to use the same FQDN and IP address for your SIP Access service, your Skype for Business Server Web Conferencing service, and your A/V Edge service.</span></span> <span data-ttu-id="80f6f-130">その場合は、[**単一の FQDN と IP アドレスを使用する] チェックボックスをオン**にする必要があります (以下の手順9の場合はこの点に注意してください)。</span><span class="sxs-lookup"><span data-stu-id="80f6f-130">If so, you need to choose the **Use a single FQDN and IP address checkbox** (and keep this in mind for Step 9 below)</span></span>
    
   - <span data-ttu-id="80f6f-131">フェデレーションを有効にする計画がある場合は、[**このエッジ プールのフェデレーションを有効化 (ポート 5061)**] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="80f6f-131">If you're planning to enable federation, choose the **Enable federation for this Edge pool (Port 5061)** check box.</span></span>
    
8. <span data-ttu-id="80f6f-p104">[**次へ**] をクリックすると、[**IP オプション**] 画面に移動します。次のオプションが使用できます。</span><span class="sxs-lookup"><span data-stu-id="80f6f-p104">Once you've clicked **Next**, you'll find yourself on the **IP Options** screen. Your options are as follows:</span></span>
    
   - <span data-ttu-id="80f6f-134">内部インターフェイスで IPv4 を有効にする</span><span class="sxs-lookup"><span data-stu-id="80f6f-134">Enable IPv4 on the internal interface</span></span>
    
   - <span data-ttu-id="80f6f-135">内部インターフェイスで IPv6 を有効にする</span><span class="sxs-lookup"><span data-stu-id="80f6f-135">Enable IPv6 on the internal interface</span></span>
    
   - <span data-ttu-id="80f6f-136">外部インターフェイスで IPv4 を有効にする</span><span class="sxs-lookup"><span data-stu-id="80f6f-136">Enable IPv4 on the external interface</span></span>
    
   - <span data-ttu-id="80f6f-137">外部インターフェイスで IPv6 を有効にする</span><span class="sxs-lookup"><span data-stu-id="80f6f-137">Enable IPv6 on the external interface</span></span>
    
   <span data-ttu-id="80f6f-138">これらのアドレスは、IPv4 と IPv6 のどちらのアドレスを使用しているかにかかわらず、エッジサーバー上または外部でそれらのアドレスを適用しているかどうかによってわかりやすいものになります (手順10の場合は、この点に注意する必要があります)。</span><span class="sxs-lookup"><span data-stu-id="80f6f-138">These are pretty self-explanatory, whether you're using IPv4 or IPv6 addresses, and you're applying those addresses on your Edge Server internally or externally (you'll need to keep this in mind for Step 10).</span></span> <span data-ttu-id="80f6f-139">また、エッジサーバーまたは Edge プールで、外部 IP アドレスにネットワークアドレス変換 (NAT) アドレスを使用するように構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="80f6f-139">You also have the option of configuring your Edge Server or your Edge pool to use a network address translation (NAT) address for the external IP address.</span></span> <span data-ttu-id="80f6f-140">これを行うには **、[このエッジプールの外部 IP アドレスを NAT で変換**する] チェックボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="80f6f-140">You can do this by choosing **The external IP address of this Edge pool is translated by NAT** check box .</span></span> <span data-ttu-id="80f6f-141">[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="80f6f-141">Click **Next** when ready.</span></span>
    
9. <span data-ttu-id="80f6f-142">[外部 FQDN] 画面の選択肢は、上記の手順 7. で行った選択内容に応じて異なります。</span><span class="sxs-lookup"><span data-stu-id="80f6f-142">On the External FQDNs screen, your choices depend on the selection you made in Step 7 above.</span></span>
    
   - <span data-ttu-id="80f6f-143">[**単一の FQDN と IP アドレスを使用**する] チェックボックスをオンにした場合、[ **SIP アクセス**] ボックスに1つの外部 FQDN を入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="80f6f-143">If you checked the **Use a single FQDN and IP Address** check box, you need to enter your single external FQDN in the **SIP Access** box.</span></span> <span data-ttu-id="80f6f-144">その後、各エッジサービスに別々のポート番号を入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="80f6f-144">Then you'll need to enter different port numbers for each edge service to allow them all to connect independently.</span></span> <span data-ttu-id="80f6f-145">[**SIP アクセス**] エッジ サービスには 5061、[**Web 会議**] エッジ サービスには 444、[**音声ビデオ**] エッジ サービスには 443 を指定することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="80f6f-145">We recommend 5061 for the **SIP Access** Edge service, 444 for the **Web Conferencing** Edge service, and 443 for the **A/V** Edge service.</span></span> <span data-ttu-id="80f6f-146">作業が完了したら [**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="80f6f-146">Click **Next** when done.</span></span>
    
   - <span data-ttu-id="80f6f-147">[**単一の FQDN と IP アドレスを使用**する] チェックボックスをオンにしていない場合は、 **SIP アクセス**エッジサービス、 **Web 会議**エッジサービス、 **a/V** Edge サービス用に、3つの外部 fqdn を入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="80f6f-147">If you didn't check the **Use a single FQDN and IP Address** check box, you'll now need to enter the three external FQDNs for the **SIP Access** Edge service, the **Web Conferencing** Edge service, and the **A/V** Edge service.</span></span> <span data-ttu-id="80f6f-148">作業が完了したら [**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="80f6f-148">Click **Next** when done.</span></span>
    
10. <span data-ttu-id="80f6f-149">これで [**内部 IP アドレスの定義**] 画面が表示されます。</span><span class="sxs-lookup"><span data-stu-id="80f6f-149">You're now on the **Define the Internal IP address** screen.</span></span> <span data-ttu-id="80f6f-150">ここでは、手順8で行った選択に応じて、**内部 IPv4 アドレス**と**内部 IPv6 アドレス**のテキストボックスにエッジサーバーの IP アドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="80f6f-150">Here you'll type the IP address of your Edge Server in the **Internal IPv4 address** and **Internal IPv6 address** text boxes, depending on the choices you made back in Step 8.</span></span> <span data-ttu-id="80f6f-151">[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="80f6f-151">Click **Next** when ready.</span></span>
    
11. <span data-ttu-id="80f6f-152">[**外部 IP アドレスの定義**] 画面では、以前の選択内容に応じた複数のオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="80f6f-152">On the **Define the External IP address** screen, you have a few options depending on your previous choices:</span></span>
    
    - <span data-ttu-id="80f6f-153">すべてのサービスに単一の FQDN を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="80f6f-153">You may be using a single FQDN for all services.</span></span> <span data-ttu-id="80f6f-154">その場合は、外部 IPv4 または IPv6 アドレスを**SIP アクセス**テキストボックスに入力して、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="80f6f-154">If so, type your external IPv4 or IPv6 address (whichever you're using) into the **SIP Access** text box, and then click **Next**.</span></span>
    
    - <span data-ttu-id="80f6f-155">3つの独立した Fqdn と IP アドレスをサービスに使用することを選択している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="80f6f-155">You may have chosen to use three separate FQDNs and IP addresses for the services.</span></span> <span data-ttu-id="80f6f-156">その場合は、 **SIP アクセス**エッジサービス、 **Web 会議**エッジサービス、 **A/V** edge サービスの外部 IPv4 または IPv6 アドレスを入力して、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="80f6f-156">If that's the case, enter your external IPv4 or IPv6 addresses for the **SIP Access** Edge service, the **Web Conferencing** Edge service, and the **A/V** Edge service, and then click **Next**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="80f6f-p111">以前に IPv6 アドレスを有効にして割り当てることを選択しなかった場合、このダイアログ ボックスは表示されません。これで問題はないため、次の手順に進みます。</span><span class="sxs-lookup"><span data-stu-id="80f6f-p111">If you didn't previously choose to enable and assign IPv6 addressing, you won't see this dialog box. That's normal, just go to the next step.</span></span> 
  
12. <span data-ttu-id="80f6f-159">手順8で NAT を使用するように選択した場合は、[**パブリック IP アドレス**] ボックスの画面が表示されるようになります。</span><span class="sxs-lookup"><span data-stu-id="80f6f-159">If you chose to use NAT back in Step 8, you'll now get a screen with a **Public IP address** textbox.</span></span> <span data-ttu-id="80f6f-160">NAT で翻訳するには、A/V Edge サービスに設定したパブリック IPv4 および IPv6 アドレスを入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="80f6f-160">You'll need to enter the public IPv4 and/or IPv6 address you've set for the A/V Edge service, to be translated by NAT.</span></span> <span data-ttu-id="80f6f-161">続いて [ **次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="80f6f-161">Then click **Next**.</span></span>
    
13. <span data-ttu-id="80f6f-162">次に表示される画面は [**次ホップの定義**] です。</span><span class="sxs-lookup"><span data-stu-id="80f6f-162">Next screen up is **Define the next hop**.</span></span> <span data-ttu-id="80f6f-163">[ **Next ホッププール**] ボックスで、内部プールの名前を選びます。これは、フロントエンドプールでも、スタンドアロンプールでもかまいません。</span><span class="sxs-lookup"><span data-stu-id="80f6f-163">In the **Next hop pool** box, select the name of your internal pool, which might be a Front End pool or a Standalone pool.</span></span> <span data-ttu-id="80f6f-164">お客様の環境にディレクターがある場合は、ディレクターを選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="80f6f-164">If you have a Director in your environment, you should choose the Director.</span></span> <span data-ttu-id="80f6f-165">続いて [ **次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="80f6f-165">Then click **Next**.</span></span>
    
14. <span data-ttu-id="80f6f-166">[**フロントエンドプールの関連付け**] 画面では、このエッジサーバーと関連付けるために、1つ以上の内部プールを指定する必要があります (フロントエンドプールと Standard Edition サーバーを含む)。</span><span class="sxs-lookup"><span data-stu-id="80f6f-166">On the **Associate Front End pools** screen, you'll need to specify one or more internal pools, including Front End pools and Standard Edition servers, to associate with this Edge Server.</span></span> <span data-ttu-id="80f6f-167">このエッジサーバーを使用して、サポートされている外部ユーザーと通信する内部プールの名前を選択するだけです。</span><span class="sxs-lookup"><span data-stu-id="80f6f-167">Just choose the names of the internal pools you want using this Edge Server to communicate with supported external users.</span></span> <span data-ttu-id="80f6f-168">[ **次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="80f6f-168">Click **Next**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="80f6f-169">内部プールまたはスタンドアロンサーバーで、既に別の Skype for Business Server Edge サーバーを使用している場合は、複数のアソシエーションを持つことはできません。</span><span class="sxs-lookup"><span data-stu-id="80f6f-169">Something to keep in mind here is, if your internal pools or standalone servers are already using a different Skype for Business Server Edge Server, they can't have multiple associations.</span></span> <span data-ttu-id="80f6f-170">このような状況にある内部プールまたはスタンドアロンサーバーを選択すると、他のエッジサーバーについて警告が表示され、続行するかどうかを決定できます。</span><span class="sxs-lookup"><span data-stu-id="80f6f-170">If you choose an internal pool or standalone server that's in that situation, you'll see a warning appear telling you about the other Edge Server, and you can decide whether you want to continue or not.</span></span> <span data-ttu-id="80f6f-171">この新しい関連付けを使用している場合は、他のエッジサーバーへの接続が停止します。</span><span class="sxs-lookup"><span data-stu-id="80f6f-171">If you go ahead with this new association, the connection to the other Edge Server will stop.</span></span> 
  
15. <span data-ttu-id="80f6f-172">次の画面で [**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="80f6f-172">Click **Finish** on the next screen.</span></span>
    
16. <span data-ttu-id="80f6f-173">これで、この更新されたテクノロジを公開し、「 [Skype For Business Server でエッジ](deploy-edge-servers.md)サーバーを展開する」の指示に従って、ここから edge サーバーに展開できるようになります。</span><span class="sxs-lookup"><span data-stu-id="80f6f-173">Now you'll be able to publish this updated technology, and follow the instructions in [Deploy Edge Servers in Skype for Business Server](deploy-edge-servers.md) to deploy to your Edge Server from here.</span></span>
    
### <a name="defining-the-topology-for-a-dns-load-balanced-edge-server-pool"></a><span data-ttu-id="80f6f-174">DNS 負荷分散エッジサーバープールのトポロジの定義</span><span class="sxs-lookup"><span data-stu-id="80f6f-174">Defining the topology for a DNS load balanced Edge Server pool</span></span>

1. <span data-ttu-id="80f6f-175">Skype for Business Server Standard Edition server、または Skype for Business Server フロントエンドサーバーにログオンします。</span><span class="sxs-lookup"><span data-stu-id="80f6f-175">Log onto your Skype for Business Server Standard Edition server, or a Skype for Business Server Front End Server.</span></span>
    
2. <span data-ttu-id="80f6f-176">**Skype For Business Server Topology Builder**を開きます。</span><span class="sxs-lookup"><span data-stu-id="80f6f-176">Once there, open **Skype for Business Server Topology Builder**.</span></span>
    
3. <span data-ttu-id="80f6f-177">コンソールツリーで、エッジサーバーを展開するサイトを展開します。</span><span class="sxs-lookup"><span data-stu-id="80f6f-177">In the console tree, expand the site you're going to deploy the Edge Server to.</span></span>
    
4. <span data-ttu-id="80f6f-178">[**エッジプール**] を右クリックし、[**新しいエッジプール**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="80f6f-178">Right-click **Edge pools**, and then click **New Edge pool**.</span></span>
    
5. <span data-ttu-id="80f6f-179">[**新しいエッジプールの定義**] 画面の [**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="80f6f-179">You'll click **Next** on the **Define New Edge pool** screen.</span></span>
    
6. <span data-ttu-id="80f6f-180">[ **Edge プールの FQDN の定義**] 画面で、エッジプールで使用する内部の完全修飾ドメイン名 (FQDN) を入力して、[**複数のコンピュータープール**] を選択し、完了したら [**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="80f6f-180">On the **Define the Edge pool FQDN** screen, type the internal fully qualified domain name (FQDN) that the Edge pool is going to use, and select **Multiple computer pool**, clicking **Next** when done.</span></span>
    
7. <span data-ttu-id="80f6f-181">[**機能の選択**] 画面には、次の選択肢があります。</span><span class="sxs-lookup"><span data-stu-id="80f6f-181">On the **Select features** screen, you have a choice:</span></span>
    
    - <span data-ttu-id="80f6f-182">SIP アクセスサービス、Skype for Business Server Web 会議サービス、A/V Edge サービスには、同じ FQDN と IP アドレスを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="80f6f-182">You may intend to use the same FQDN and IP address for your SIP Access service, your Skype for Business Server Web Conferencing Service, and your A/V Edge service.</span></span> <span data-ttu-id="80f6f-183">その場合は、[**単一の FQDN と IP アドレスを使用する] チェックボックスをオン**にする必要があります (以下の手順9の場合はこの点に注意してください)。</span><span class="sxs-lookup"><span data-stu-id="80f6f-183">If so, you need to choose the **Use a single FQDN and IP address checkbox** (and keep this in mind for Step 9 below)</span></span>
    
    - <span data-ttu-id="80f6f-184">フェデレーションを有効にする計画がある場合は、[**このエッジ プールのフェデレーションを有効化 (ポート 5061)**] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="80f6f-184">If you're planning to enable federation, choose the **Enable federation for this Edge pool (Port 5061)** check box.</span></span>
    
8. <span data-ttu-id="80f6f-p117">[**次へ**] をクリックすると、[**IP オプション**] 画面に移動します。次のオプションが使用できます。</span><span class="sxs-lookup"><span data-stu-id="80f6f-p117">Once you've clicked **Next**, you'll find yourself on the **IP Options** screen. Your options are as follows:</span></span>
    
    - <span data-ttu-id="80f6f-187">内部インターフェイスで IPv4 を有効にする</span><span class="sxs-lookup"><span data-stu-id="80f6f-187">Enable IPv4 on the internal interface</span></span>
    
   - <span data-ttu-id="80f6f-188">内部インターフェイスで IPv6 を有効にする</span><span class="sxs-lookup"><span data-stu-id="80f6f-188">Enable IPv6 on the internal interface</span></span>
    
   - <span data-ttu-id="80f6f-189">外部インターフェイスで IPv4 を有効にする</span><span class="sxs-lookup"><span data-stu-id="80f6f-189">Enable IPv4 on the external interface</span></span>
    
   - <span data-ttu-id="80f6f-190">外部インターフェイスで IPv6 を有効にする</span><span class="sxs-lookup"><span data-stu-id="80f6f-190">Enable IPv6 on the external interface</span></span>
    
     <span data-ttu-id="80f6f-191">これらのアドレスは、IPv4 と IPv6 のどちらのアドレスを使用しているかにかかわらず、エッジサーバー上または外部でそれらのアドレスを適用しているかどうかによってわかりやすいものになります (手順11の場合は、この点に注意する必要があります)。</span><span class="sxs-lookup"><span data-stu-id="80f6f-191">These are pretty self-explanatory, whether you're using IPv4 or IPv6 addresses, and you're applying those addresses on your Edge Server internally or externally (you'll need to keep this in mind for Step 11).</span></span> <span data-ttu-id="80f6f-192">また、エッジサーバーまたは Edge プールで、外部 IP アドレスにネットワークアドレス変換 (NAT) アドレスを使用するように構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="80f6f-192">You also have the option of configuring your Edge Server or your Edge pool to use a network address translation (NAT) address for the external IP address.</span></span> <span data-ttu-id="80f6f-193">これを行うには **、[このエッジプールの外部 IP アドレスを NAT で変換**する] チェックボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="80f6f-193">You can do this by choosing **The external IP address of this Edge pool is translated by NAT** check box .</span></span> <span data-ttu-id="80f6f-194">[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="80f6f-194">Click **Next** when ready.</span></span>
    
9. <span data-ttu-id="80f6f-195">[外部 FQDN] 画面の選択肢は、上記の手順 7. で行った選択内容に応じて異なります。</span><span class="sxs-lookup"><span data-stu-id="80f6f-195">On the External FQDNs screen, your choices depend on the selection you made in Step 7 above.</span></span>
    
   - <span data-ttu-id="80f6f-196">[**単一の FQDN と IP アドレスを使用**する] チェックボックスをオンにした場合、[ **SIP アクセス**] ボックスに1つの外部 FQDN を入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="80f6f-196">If you checked the **Use a single FQDN and IP Address** check box, you need to enter your single external FQDN in the **SIP Access** box.</span></span> <span data-ttu-id="80f6f-197">その後、各エッジサービスに別々のポート番号を入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="80f6f-197">Then you'll need to enter different port numbers for each edge service to allow them all to connect independently.</span></span> <span data-ttu-id="80f6f-198">[**SIP アクセス**] エッジ サービスには 5061、[**Web 会議**] エッジ サービスには 444、[**音声ビデオ**] エッジ サービスには 443 を指定することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="80f6f-198">We recommend 5061 for the **SIP Access** Edge service, 444 for the **Web Conferencing** Edge service, and 443 for the **A/V** Edge service.</span></span> <span data-ttu-id="80f6f-199">作業が完了したら [**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="80f6f-199">Click **Next** when done.</span></span>
    
   - <span data-ttu-id="80f6f-200">[**単一の FQDN と IP アドレスを使用**する] チェックボックスをオンにしていない場合は、 **SIP アクセス**エッジサービス、 **Web 会議**エッジサービス、 **a/V** Edge サービス用に、3つの外部 fqdn を入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="80f6f-200">If you didn't check the **Use a single FQDN and IP Address** check box, you'll now need to enter the three external FQDNs for the **SIP Access** Edge service, the **Web Conferencing** Edge service, and the **A/V** Edge service.</span></span> <span data-ttu-id="80f6f-201">作業が完了したら [**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="80f6f-201">Click **Next** when done.</span></span>
    
10. <span data-ttu-id="80f6f-202">これで、[**このプールのコンピューターを定義**します] 画面が表示されました。</span><span class="sxs-lookup"><span data-stu-id="80f6f-202">Now you've reached the **Define the computers in this pool** screen.</span></span> <span data-ttu-id="80f6f-203">[**追加**] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="80f6f-203">Click the **Add** button.</span></span>
    
11. <span data-ttu-id="80f6f-204">これで [**内部 IP アドレスの定義**] 画面が表示されます。</span><span class="sxs-lookup"><span data-stu-id="80f6f-204">You're now on the **Define the Internal IP address** screen.</span></span> <span data-ttu-id="80f6f-205">ここでは、手順8で行った選択に応じて、**内部 IPv4 アドレス**と**内部 IPv6 アドレス**のテキストボックスにエッジサーバーの IP アドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="80f6f-205">Here you'll type the IP address of your Edge Server in the **Internal IPv4 address** and **Internal IPv6 address** text boxes, depending on the choices you made back in Step 8.</span></span> <span data-ttu-id="80f6f-206">[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="80f6f-206">Click **Next** when ready.</span></span>
    
12. <span data-ttu-id="80f6f-207">[**外部 IP アドレスの定義**] 画面では、以前の選択内容に応じた複数のオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="80f6f-207">On the **Define the External IP address** screen, you have a few options depending on your previous choices:</span></span>
    
    - <span data-ttu-id="80f6f-208">すべてのサービスに単一の FQDN を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="80f6f-208">You may be using a single FQDN for all services.</span></span> <span data-ttu-id="80f6f-209">その場合は、外部 IPv4 または IPv6 アドレスを**SIP アクセス**テキストボックスに入力して、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="80f6f-209">If so, type your external IPv4 or IPv6 address (whichever you're using) into the **SIP Access** text box, and then click **Next**.</span></span>
    
    - <span data-ttu-id="80f6f-210">3つの独立した Fqdn と IP アドレスをサービスに使用することを選択している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="80f6f-210">You may have chosen to use three separate FQDNs and IP addresses for the services.</span></span> <span data-ttu-id="80f6f-211">その場合は、 **SIP アクセス**エッジサービス、 **Web 会議**エッジサービス、 **A/V** edge サービスの外部 IPv4 または IPv6 アドレスを入力して、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="80f6f-211">If that's the case, enter your external IPv4 or IPv6 addresses for the **SIP Access** Edge service, the **Web Conferencing** Edge service, and the **A/V** Edge service, and then click **Next**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="80f6f-p125">以前に IPv6 アドレスを有効にして割り当てることを選択しなかった場合、このダイアログ ボックスは表示されません。これで問題はないため、次の手順に進みます。</span><span class="sxs-lookup"><span data-stu-id="80f6f-p125">If you didn't previously choose to enable and assign IPv6 addressing, you won't see this dialog box. That's normal, just go to the next step.</span></span> 
  
13. <span data-ttu-id="80f6f-214">[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="80f6f-214">Click **Finish**.</span></span> <span data-ttu-id="80f6f-215">これで作成したエッジサーバーが、[**このプールのコンピューターの定義**] ダイアログボックスに表示されます。</span><span class="sxs-lookup"><span data-stu-id="80f6f-215">The Edge Server you just created should now be listed in the **Define the computers in this pool** dialog box.</span></span>
    
14. <span data-ttu-id="80f6f-216">[**このプールのコンピューターの定義**] 画面で、[**追加**] ボタンをもう一度クリックし、このプールで使用するすべてのエッジサーバーが追加されるまで、手順 11 ~ 13 を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="80f6f-216">While still on the **Define the computers in this pool** screen, click the **Add** button again and repeat steps 11 through 13 until you've added all the Edge Servers you intend to have in this pool.</span></span> <span data-ttu-id="80f6f-217">完了したら、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="80f6f-217">When this is complete, click **Next**.</span></span>
    
15. <span data-ttu-id="80f6f-218">手順8で NAT を使用するように選択した場合は、[**パブリック IP アドレス**] ボックスの画面が表示されるようになります。</span><span class="sxs-lookup"><span data-stu-id="80f6f-218">If you chose to use NAT back in Step 8, you'll now get a screen with a **Public IP address** textbox.</span></span> <span data-ttu-id="80f6f-219">NAT で翻訳するには、A/V Edge サービスに設定したパブリック IPv4 および IPv6 アドレスを入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="80f6f-219">You'll need to enter the public IPv4 and/or IPv6 address you've set for the A/V Edge service, to be translated by NAT.</span></span> <span data-ttu-id="80f6f-220">続いて [ **次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="80f6f-220">Then click **Next**.</span></span>
    
16. <span data-ttu-id="80f6f-221">次に表示される画面は [**次ホップの定義**] です。</span><span class="sxs-lookup"><span data-stu-id="80f6f-221">Next screen up is **Define the next hop**.</span></span> <span data-ttu-id="80f6f-222">[ **Next ホッププール**] ボックスで、内部プールの名前を選びます。これは、フロントエンドプールでも、スタンドアロンプールでもかまいません。</span><span class="sxs-lookup"><span data-stu-id="80f6f-222">In the **Next hop pool** box, select the name of your internal pool, which might be a Front End pool or a Standalone pool.</span></span> <span data-ttu-id="80f6f-223">お客様の環境にディレクターがある場合は、ディレクターを選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="80f6f-223">If you have a Director in your environment, you should choose the Director.</span></span> <span data-ttu-id="80f6f-224">続いて [ **次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="80f6f-224">Then click **Next**.</span></span>
    
17. <span data-ttu-id="80f6f-225">[**フロントエンドプールの関連付け**] 画面では、このエッジサーバーと関連付けるために、フロントエンドプールや標準エディションプールなどの内部プールを1つ以上指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="80f6f-225">On the **Associate Front End pools** screen, you'll need to specify one or more internal pools, including Front End pools and Standard Edition pools, to associate with this Edge Server.</span></span> <span data-ttu-id="80f6f-226">このエッジサーバーを使用して、サポートされている外部ユーザーと通信する内部プールの名前を選択するだけです。</span><span class="sxs-lookup"><span data-stu-id="80f6f-226">Just choose the names of the internal pools you want using this Edge Server to communicate with supported external users.</span></span> <span data-ttu-id="80f6f-227">[ **次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="80f6f-227">Click **Next**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="80f6f-228">内部プールまたはスタンドアロンサーバーで、既に別の Skype for Business Server Edge サーバーを使用している場合は、複数のアソシエーションを持つことはできません。</span><span class="sxs-lookup"><span data-stu-id="80f6f-228">Something to keep in mind here is, if your internal pools or standalone servers are already using a different Skype for Business Server Edge Server, they can't have multiple associations.</span></span> <span data-ttu-id="80f6f-229">このような状況にある内部プールまたはスタンドアロンサーバーを選択すると、他のエッジサーバーについて警告が表示され、続行するかどうかを決定できます。</span><span class="sxs-lookup"><span data-stu-id="80f6f-229">If you choose an internal pool or standalone server that's in that situation, you'll see a warning appear telling you about the other Edge Server, and you can decide whether you want to continue or not.</span></span> <span data-ttu-id="80f6f-230">この新しい関連付けを使用している場合は、他のエッジサーバーへの接続が停止します。</span><span class="sxs-lookup"><span data-stu-id="80f6f-230">If you go ahead with this new association, the connection to the other Edge Server will stop.</span></span> 
  
18. <span data-ttu-id="80f6f-231">次の画面で [**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="80f6f-231">Click **Finish** on the next screen.</span></span>
    
19. <span data-ttu-id="80f6f-232">これで、この更新されたテクノロジを公開し、「 [Skype For Business Server でエッジ](deploy-edge-servers.md)サーバーを展開する」の指示に従って、ここから edge サーバーに展開できるようになります。</span><span class="sxs-lookup"><span data-stu-id="80f6f-232">Now you'll be able to publish this updated technology, and follow the instructions in [Deploy Edge Servers in Skype for Business Server](deploy-edge-servers.md) to deploy to your Edge Server from here.</span></span>
    
### <a name="defining-the-topology-for-a-hardware-load-balanced-edge-server-pool"></a><span data-ttu-id="80f6f-233">ハードウェア負荷分散エッジサーバープールのトポロジの定義</span><span class="sxs-lookup"><span data-stu-id="80f6f-233">Defining the topology for a hardware load balanced Edge Server pool</span></span>

1. <span data-ttu-id="80f6f-234">Skype for Business Server Standard Edition server、または Skype for Business Server フロントエンドサーバーにログオンします。</span><span class="sxs-lookup"><span data-stu-id="80f6f-234">Log onto your Skype for Business Server Standard Edition server, or a Skype for Business Server Front End Server.</span></span>
    
2. <span data-ttu-id="80f6f-235">**Skype For Business Server Topology Builder**を開きます。</span><span class="sxs-lookup"><span data-stu-id="80f6f-235">Once there, open **Skype for Business Server Topology Builder**.</span></span>
    
3. <span data-ttu-id="80f6f-236">コンソールツリーで、エッジサーバーを展開するサイトを展開します。</span><span class="sxs-lookup"><span data-stu-id="80f6f-236">In the console tree, expand the site you're going to deploy the Edge Server to.</span></span>
    
4. <span data-ttu-id="80f6f-237">[**エッジプール**] を右クリックし、[**新しいエッジプール**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="80f6f-237">Right-click **Edge pools**, and then click **New Edge pool**.</span></span>
    
5. <span data-ttu-id="80f6f-238">[**新しいエッジプールの定義**] 画面の [**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="80f6f-238">You'll click **Next** on the **Define New Edge pool** screen.</span></span>
    
6. <span data-ttu-id="80f6f-239">[ **Edge プールの FQDN の定義**] 画面で、エッジプールで使用する内部の完全修飾ドメイン名 (FQDN) を入力して、[**複数のコンピュータープール**] を選択し、完了したら [**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="80f6f-239">On the **Define the Edge pool FQDN** screen, type the internal fully qualified domain name (FQDN) that the Edge pool is going to use, and select **Multiple computer pool**, clicking **Next** when done.</span></span>
    
7. <span data-ttu-id="80f6f-240">[**機能の選択**] 画面には、次の選択肢があります。</span><span class="sxs-lookup"><span data-stu-id="80f6f-240">On the **Select features** screen, you have a choice:</span></span>
    
   - <span data-ttu-id="80f6f-241">SIP アクセスサービス、Skype for Business Server Web 会議サービス、A/V Edge サービスには、同じ FQDN と IP アドレスを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="80f6f-241">You may intend to use the same FQDN and IP address for your SIP Access service, your Skype for Business Server Web Conferencing Service, and your A/V Edge service.</span></span> <span data-ttu-id="80f6f-242">その場合は、[**単一の FQDN と IP アドレスを使用する] チェックボックスをオン**にする必要があります (以下の手順9の場合はこの点に注意してください)。</span><span class="sxs-lookup"><span data-stu-id="80f6f-242">If so, you need to choose the **Use a single FQDN and IP address checkbox** (and keep this in mind for Step 9 below)</span></span>
    
   - <span data-ttu-id="80f6f-243">フェデレーションを有効にする計画がある場合は、[**このエッジ プールのフェデレーションを有効化 (ポート 5061)**] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="80f6f-243">If you're planning to enable federation, choose the **Enable federation for this Edge pool (Port 5061)** check box.</span></span>
    
8. <span data-ttu-id="80f6f-p133">[**次へ**] をクリックすると、[**IP オプション**] 画面に移動します。次のオプションが使用できます。</span><span class="sxs-lookup"><span data-stu-id="80f6f-p133">Once you've clicked **Next**, you'll find yourself on the **IP Options** screen. Your options are as follows:</span></span>
    
   - <span data-ttu-id="80f6f-246">内部インターフェイスで IPv4 を有効にする</span><span class="sxs-lookup"><span data-stu-id="80f6f-246">Enable IPv4 on the internal interface</span></span>
    
   - <span data-ttu-id="80f6f-247">内部インターフェイスで IPv6 を有効にする</span><span class="sxs-lookup"><span data-stu-id="80f6f-247">Enable IPv6 on the internal interface</span></span>
    
   - <span data-ttu-id="80f6f-248">外部インターフェイスで IPv4 を有効にする</span><span class="sxs-lookup"><span data-stu-id="80f6f-248">Enable IPv4 on the external interface</span></span>
    
   - <span data-ttu-id="80f6f-249">外部インターフェイスで IPv6 を有効にする</span><span class="sxs-lookup"><span data-stu-id="80f6f-249">Enable IPv6 on the external interface</span></span>
    
     <span data-ttu-id="80f6f-250">これらのアドレスは、IPv4 と IPv6 のどちらのアドレスを使用しているかにかかわらず、エッジサーバー上または外部でそれらのアドレスを適用しているかどうかによってわかりやすいものになります (手順11の場合は、この点に注意する必要があります)。</span><span class="sxs-lookup"><span data-stu-id="80f6f-250">These are pretty self-explanatory, whether you're using IPv4 or IPv6 addresses, and you're applying those addresses on your Edge Server internally or externally (you'll need to keep this in mind for Step 11).</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="80f6f-251">他の2つのトポロジオプションとは異なり、ハードウェアロードバランサーを使用する場合は、**エッジプールの外部 IP アドレスが NAT によって変換さ**れるオプションを選択**しないでください**。</span><span class="sxs-lookup"><span data-stu-id="80f6f-251">Unlike the other two topology options, when using a hardware load balancer, you **MUST NOT** select the option **The external IP address of the Edge Pool is translated by NAT**.</span></span> <span data-ttu-id="80f6f-252">これは**サポートされていません**。</span><span class="sxs-lookup"><span data-stu-id="80f6f-252">This is **not supported**.</span></span>
  
9. <span data-ttu-id="80f6f-253">[外部 FQDN] 画面の選択肢は、上記の手順 7. で行った選択内容に応じて異なります。</span><span class="sxs-lookup"><span data-stu-id="80f6f-253">On the External FQDNs screen, your choices depend on the selection you made in Step 7 above.</span></span>
    
   - <span data-ttu-id="80f6f-254">[**単一の FQDN と IP アドレスを使用**する] チェックボックスをオンにした場合、[ **SIP アクセス**] ボックスに1つの外部 FQDN を入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="80f6f-254">If you checked the **Use a single FQDN and IP Address** check box, you need to enter your single external FQDN in the **SIP Access** box.</span></span> <span data-ttu-id="80f6f-255">その後、各エッジサービスに別々のポート番号を入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="80f6f-255">Then you'll need to enter different port numbers for each edge service to allow them all to connect independently.</span></span> <span data-ttu-id="80f6f-256">[**SIP アクセス**] エッジ サービスには 5061、[**Web 会議**] エッジ サービスには 444、[**音声ビデオ**] エッジ サービスには 443 を指定することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="80f6f-256">We recommend 5061 for the **SIP Access** Edge service, 444 for the **Web Conferencing** Edge service, and 443 for the **A/V** Edge service.</span></span> <span data-ttu-id="80f6f-257">作業が完了したら [**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="80f6f-257">Click **Next** when done.</span></span>
    
   - <span data-ttu-id="80f6f-258">[**単一の FQDN と IP アドレスを使用**する] チェックボックスをオンにしていない場合は、 **SIP アクセス**エッジサービス、 **Web 会議**エッジサービス、 **a/V** Edge サービス用に、3つの外部 fqdn を入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="80f6f-258">If you didn't check the **Use a single FQDN and IP Address** check box, you'll now need to enter the three external FQDNs for the **SIP Access** Edge service, the **Web Conferencing** Edge service, and the **A/V** Edge service.</span></span> <span data-ttu-id="80f6f-259">作業が完了したら [**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="80f6f-259">Click **Next** when done.</span></span>
    
10. <span data-ttu-id="80f6f-260">これで、[**このプールのコンピューターを定義**します] 画面が表示されました。</span><span class="sxs-lookup"><span data-stu-id="80f6f-260">Now you've reached the **Define the computers in this pool** screen.</span></span> <span data-ttu-id="80f6f-261">[**追加**] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="80f6f-261">Click the **Add** button.</span></span>
    
11. <span data-ttu-id="80f6f-262">これで [**内部 IP アドレスの定義**] 画面が表示されます。</span><span class="sxs-lookup"><span data-stu-id="80f6f-262">You're now on the **Define the Internal IP address** screen.</span></span> <span data-ttu-id="80f6f-263">ここでは、手順8で行った選択に応じて、**内部 IPv4 アドレス**と**内部 IPv6 アドレス**のテキストボックスにエッジサーバーの IP アドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="80f6f-263">Here you'll type the IP address of your Edge Server in the **Internal IPv4 address** and **Internal IPv6 address** text boxes, depending on the choices you made back in Step 8.</span></span> <span data-ttu-id="80f6f-264">[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="80f6f-264">Click **Next** when ready.</span></span>
    
12. <span data-ttu-id="80f6f-265">[**外部 IP アドレスの定義**] 画面では、以前の選択内容に応じた複数のオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="80f6f-265">On the **Define the External IP address** screen, you have a few options depending on your previous choices:</span></span>
    
    - <span data-ttu-id="80f6f-266">すべてのサービスに単一の FQDN を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="80f6f-266">You may be using a single FQDN for all services.</span></span> <span data-ttu-id="80f6f-267">その場合は、外部 IPv4 または IPv6 アドレスを**SIP アクセス**テキストボックスに入力して、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="80f6f-267">If so, type your external IPv4 or IPv6 address (whichever you're using) into the **SIP Access** text box, and then click **Next**.</span></span>
    
    - <span data-ttu-id="80f6f-268">3つの独立した Fqdn と IP アドレスをサービスに使用することを選択している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="80f6f-268">You may have chosen to use three separate FQDNs and IP addresses for the services.</span></span> <span data-ttu-id="80f6f-269">その場合は、 **SIP アクセス**エッジサービス、 **Web 会議**エッジサービス、 **A/V** edge サービスの外部 IPv4 または IPv6 アドレスを入力して、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="80f6f-269">If that's the case, enter your external IPv4 or IPv6 addresses for the **SIP Access** Edge service, the **Web Conferencing** Edge service, and the **A/V** Edge service, and then click **Next**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="80f6f-p141">以前に IPv6 アドレスを有効にして割り当てることを選択しなかった場合、このダイアログ ボックスは表示されません。これで問題はないため、次の手順に進みます。</span><span class="sxs-lookup"><span data-stu-id="80f6f-p141">If you didn't previously choose to enable and assign IPv6 addressing, you won't see this dialog box. That's normal, just go to the next step.</span></span> 
  
13. <span data-ttu-id="80f6f-272">[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="80f6f-272">Click **Finish**.</span></span> <span data-ttu-id="80f6f-273">これで作成したエッジサーバーが、[**このプールのコンピューターの定義**] ダイアログボックスに表示されます。</span><span class="sxs-lookup"><span data-stu-id="80f6f-273">The Edge Server you just created should now be listed in the **Define the computers in this pool** dialog box.</span></span>
    
14. <span data-ttu-id="80f6f-274">[**このプールのコンピューターの定義**] 画面で、[**追加**] ボタンをもう一度クリックし、このプールで使用するすべてのエッジサーバーが追加されるまで、手順 11 ~ 13 を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="80f6f-274">While still on the **Define the computers in this pool** screen, click the **Add** button again and repeat steps 11 through 13 until you've added all the Edge Servers you intend to have in this pool.</span></span> <span data-ttu-id="80f6f-275">完了したら、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="80f6f-275">When this is complete, click **Next**.</span></span>
    
15. <span data-ttu-id="80f6f-276">次に表示される画面は [**次ホップの定義**] です。</span><span class="sxs-lookup"><span data-stu-id="80f6f-276">Next screen up is **Define the next hop**.</span></span> <span data-ttu-id="80f6f-277">[ **Next ホッププール**] ボックスで、内部プールの名前を選びます。これは、フロントエンドプールでも、スタンドアロンプールでもかまいません。</span><span class="sxs-lookup"><span data-stu-id="80f6f-277">In the **Next hop pool** box, select the name of your internal pool, which might be a Front End pool or a Standalone pool.</span></span> <span data-ttu-id="80f6f-278">お客様の環境にディレクターがある場合は、ディレクターを選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="80f6f-278">If you have a Director in your environment, you should choose the Director.</span></span> <span data-ttu-id="80f6f-279">続いて [ **次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="80f6f-279">Then click **Next**.</span></span>
    
16. <span data-ttu-id="80f6f-280">[**フロントエンドプールの関連付け**] 画面では、このエッジサーバーと関連付けるために、フロントエンドプールや標準エディションプールなどの内部プールを1つ以上指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="80f6f-280">On the **Associate Front End pools** screen, you'll need to specify one or more internal pools, including Front End pools and Standard Edition pools, to associate with this Edge Server.</span></span> <span data-ttu-id="80f6f-281">このエッジサーバーを使用して、サポートされている外部ユーザーと通信する内部プールの名前を選択するだけです。</span><span class="sxs-lookup"><span data-stu-id="80f6f-281">Just choose the names of the internal pools you want using this Edge Server to communicate with supported external users.</span></span> <span data-ttu-id="80f6f-282">[ **次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="80f6f-282">Click **Next**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="80f6f-283">内部プールまたはスタンドアロンサーバーで、既に別の Skype for Business Server Edge サーバーを使用している場合は、複数のアソシエーションを持つことはできません。</span><span class="sxs-lookup"><span data-stu-id="80f6f-283">Something to keep in mind here is, if your internal pools or standalone servers are already using a different Skype for Business Server Edge Server, they can't have multiple associations.</span></span> <span data-ttu-id="80f6f-284">このような状況にある内部プールまたはスタンドアロンサーバーを選択すると、他のエッジサーバーについて警告が表示され、続行するかどうかを決定できます。</span><span class="sxs-lookup"><span data-stu-id="80f6f-284">If you choose an internal pool or standalone server that's in that situation, you'll see a warning appear telling you about the other Edge Server, and you can decide whether you want to continue or not.</span></span> <span data-ttu-id="80f6f-285">この新しい関連付けを使用している場合は、他のエッジサーバーへの接続が停止します。</span><span class="sxs-lookup"><span data-stu-id="80f6f-285">If you go ahead with this new association, the connection to the other Edge Server will stop.</span></span> 
  
17. <span data-ttu-id="80f6f-286">次の画面で [**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="80f6f-286">Click **Finish** on the next screen.</span></span>
    
18. <span data-ttu-id="80f6f-287">これで、この更新されたテクノロジを公開し、「 [Skype For Business Server でエッジ](deploy-edge-servers.md)サーバーを展開する」の指示に従って、ここから edge サーバーに展開できるようになります。</span><span class="sxs-lookup"><span data-stu-id="80f6f-287">Now you'll be able to publish this updated technology, and follow the instructions in [Deploy Edge Servers in Skype for Business Server](deploy-edge-servers.md) to deploy to your Edge Server from here.</span></span>
    
## <a name="publish-your-edge-server-topology"></a><span data-ttu-id="80f6f-288">エッジ サーバー トポロジを公開する</span><span class="sxs-lookup"><span data-stu-id="80f6f-288">Publish your Edge Server topology</span></span>

<span data-ttu-id="80f6f-289">上記の手順が完了したら、この新しいトポロジを公開して、Skype for Business Server Edge サーバーまたはエッジプールにエクスポートすることもできます。</span><span class="sxs-lookup"><span data-stu-id="80f6f-289">Once you've finished the steps above, it's time to publish this new topology, which will also allow you to export it to your Skype for Business Server Edge Server or Edge pool.</span></span> <span data-ttu-id="80f6f-290">次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="80f6f-290">Follow these steps:</span></span>
  
1. <span data-ttu-id="80f6f-291">**トポロジ ビルダー**を起動します (以前の手順でまだ起動されていない場合)。</span><span class="sxs-lookup"><span data-stu-id="80f6f-291">Start **Topology Builder** (if it's not started already from the previous procedure).</span></span>
    
2. <span data-ttu-id="80f6f-292">[**トポロジビルダー**] のコンソールツリーで、[ **Skype for business server** ] を右クリックし、[ **Skype for business server Topology Builder**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="80f6f-292">In **Topology Builder**, in the console tree, right-click **Skype for Business Server** and then click **Skype for Business Server Topology Builder**.</span></span>
    
3. <span data-ttu-id="80f6f-293">ウィザードの [**ようこそ**] ページで、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="80f6f-293">On the **Welcome** page of the wizard, click **Next**.</span></span>
    
4. <span data-ttu-id="80f6f-294">[**他のデータベースの作成**] ページで、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="80f6f-294">On the **Create other databases** page, click **Next**.</span></span>
    
5. <span data-ttu-id="80f6f-295">状態に、データベースが正常に作成されたことが示されたら、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="80f6f-295">When the status indicates that the database creation succeeded, do the following:</span></span>
    
    - <span data-ttu-id="80f6f-296">ログを表示するには、[**ログの表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="80f6f-296">To view the log, click **View log**.</span></span>
    
    - <span data-ttu-id="80f6f-297">ウィザードを閉じるには、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="80f6f-297">To close the wizard, click **Finish**.</span></span>
    
## <a name="export-your-edge-server-topology"></a><span data-ttu-id="80f6f-298">エッジ サーバー トポロジをエクスポートする</span><span class="sxs-lookup"><span data-stu-id="80f6f-298">Export your Edge Server topology</span></span>

<span data-ttu-id="80f6f-299">正常に展開するには、Skype for Business Server 展開ウィザードで、サーバーの全体管理ストアデータにアクセスする必要があります。</span><span class="sxs-lookup"><span data-stu-id="80f6f-299">To deploy successfully, the Skype for Business Server Deployment Wizard needs access to the Central Management store data.</span></span> <span data-ttu-id="80f6f-300">ドメインまたはフォレスト内の内部サーバーの場合、通常、この作業は単純です。</span><span class="sxs-lookup"><span data-stu-id="80f6f-300">For internal servers in your domain or forest, this typically is straightforward.</span></span> <span data-ttu-id="80f6f-301">エッジサーバーはドメインの外部にあるため、トポロジファイルをエッジサーバーの場所 (通常は物理メディア) に手動でエクスポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="80f6f-301">Edge Servers are outside of the domain, and so it's necessary to manually export the topology file to the Edge Server location, usually on a physical media.</span></span> <span data-ttu-id="80f6f-302">このエクスポートは、次のように PowerShell を介して行われます。</span><span class="sxs-lookup"><span data-stu-id="80f6f-302">This export is done via PowerShell:</span></span>
  
1. <span data-ttu-id="80f6f-303">**Skype For Business Server 管理シェル**を起動します。</span><span class="sxs-lookup"><span data-stu-id="80f6f-303">Start the **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="80f6f-304">**Skype For Business Server 管理シェル**で、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="80f6f-304">In the **Skype for Business Server Management Shell**, run the following:</span></span>
    
   ```
   Export-CsConfiguration -FileName <ConfigurationFilePath.zip>
   ```

3. <span data-ttu-id="80f6f-305">エクスポートしたファイルを外部メディア (たとえば、エッジサーバーの場所から接続できる USB ドライブやネットワーク共有など) にコピーします。</span><span class="sxs-lookup"><span data-stu-id="80f6f-305">Copy the exported file to external media (for example, a USB drive or network share that you can reach from the Edge Server's location).</span></span>
    

