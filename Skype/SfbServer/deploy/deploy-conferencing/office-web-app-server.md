---
title: Skype for Business Server Office Web Apps サーバーとの統合を構成する
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
ms.assetid: b7e9149e-bf16-4120-afe0-3ee09c88f5eb
description: '概要: Web Apps Server と Skype for Business Server の間の統合を構成して、Web 会議Office PowerPoint プレゼンテーションを有効にする方法については、このトピックを参照してください。'
ms.openlocfilehash: 24332154efacd0dac889bcad5b95379b28faf7a2
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103653"
---
# <a name="configure-integration-with-office-web-apps-server-in-skype-for-business-server"></a><span data-ttu-id="450b1-103">Skype for Business Server Office Web Apps サーバーとの統合を構成する</span><span class="sxs-lookup"><span data-stu-id="450b1-103">Configure integration with Office Web Apps Server in Skype for Business Server</span></span>
 
<span data-ttu-id="450b1-104">**概要:** このトピックでは、Web Apps Server と Skype for Business Server Officeの統合を構成して、Web 会議用の PowerPoint プレゼンテーションを有効にする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="450b1-104">**Summary:** Read this topic to learn how to configure integration between Office Web Apps Server and Skype for Business Server to enable PowerPoint presentations for web conferencing.</span></span>
  
<span data-ttu-id="450b1-105">Skype for Business Server は、Web Office会議用の PowerPoint プレゼンテーションを処理する Web Apps サーバーを採用しています。</span><span class="sxs-lookup"><span data-stu-id="450b1-105">Skype for Business Server employs Office Web Apps Server to handle PowerPoint presentations for web conferencing.</span></span> <span data-ttu-id="450b1-106">この方法の利点については、「Skype for Business Server での会議の計画 [」を参照してください](../../plan-your-deployment/conferencing/conferencing.md)。</span><span class="sxs-lookup"><span data-stu-id="450b1-106">For information about the advantages to this approach, see [Plan for conferencing in Skype for Business Server](../../plan-your-deployment/conferencing/conferencing.md).</span></span>
  
<span data-ttu-id="450b1-107">Skype for Business Server で Web Apps サーバー Office構成する前に、Web Apps サーバー Office展開および構成されていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="450b1-107">Before you can configure Skype for Business Server to use Office Web Apps Server, you must ensure that Office Web Apps Server is already deployed and configured.</span></span> <span data-ttu-id="450b1-108">Web Apps Server のOfficeについては、「Deploy the [infrastructure: Office」を参照してください](/webappsserver/deploy-the-infrastructure-office-web-apps-server)。</span><span class="sxs-lookup"><span data-stu-id="450b1-108">For information on Office Web Apps Server, see the article [Deploy the infrastructure: Office Online Server](/webappsserver/deploy-the-infrastructure-office-web-apps-server).</span></span> 
  
<span data-ttu-id="450b1-109">Office Web Apps サーバーが正常にインストールされ、Web ファームが正しく構成された後、Office Web Apps Server 検出 URL を Skype for Business Server トポロジに追加して、新しいサーバーと通信するように Skype for Business Server を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="450b1-109">After Office Web Apps Server has been successfully installed and your Web farm correctly configured, you must then configure Skype for Business Server to communicate with the new server by adding the Office Web Apps Server discovery URL to your Skype for Business Server topology.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="450b1-110">Web Apps Server の最新Officeは、Skype for Business Server でOfficeオンライン サーバーという名前です。</span><span class="sxs-lookup"><span data-stu-id="450b1-110">The latest iteration of Office Web Apps Server is named Office Online Server, which is supported by Skype for Business Server.</span></span> <span data-ttu-id="450b1-111">詳細については、オンライン サーバーのドキュメント [Office参照してください](/officeonlineserver/office-online-server)。</span><span class="sxs-lookup"><span data-stu-id="450b1-111">For more detail, refer to the [Office Online Server documentation](/officeonlineserver/office-online-server).</span></span> 
  
## <a name="configure-skype-for-business-server-to-communicate-with-office-web-apps-server"></a><span data-ttu-id="450b1-112">Skype for Business Server が Web Apps サーバーと通信Office構成する</span><span class="sxs-lookup"><span data-stu-id="450b1-112">Configure Skype for Business Server to communicate with Office Web Apps Server</span></span>

<span data-ttu-id="450b1-113">Web Apps server Officeトポロジに追加するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="450b1-113">To add Office Web Apps Server to your topology, complete the following steps:</span></span>
  
1. <span data-ttu-id="450b1-114">Skype for Business Server トポロジ ビルダーを開きます。</span><span class="sxs-lookup"><span data-stu-id="450b1-114">Open Skype for Business Server Topology Builder.</span></span>
    
2. <span data-ttu-id="450b1-115">[**トポロジ ビルダー**] ダイアログ ボックスで、[**既存の展開環境からトポロジをダウンロードする**] をクリックし、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="450b1-115">In the **Topology Builder** dialog box, select **Download Topology from existing deployment** and then click **OK**.</span></span>
    
3. <span data-ttu-id="450b1-p104">[**トポロジに名前を付けて保存**] ダイアログ ボックスで、トポロジ ドキュメントの名前 (例: **PreWebAppsServerTopology**) を [**ファイル名**] ボックスに入力し、[**保存**] をクリックします。新しいトポロジで問題が発生した場合、後でこのトポロジを取得して再発行できます。</span><span class="sxs-lookup"><span data-stu-id="450b1-p104">In the **Save Topology As** dialog box, type a name for your topology document (for example, **PreWebAppsServerTopology**) in the **File name** box and then click **Save**. This topology can later be retrieved and republished if you encounter problems with your new topology.</span></span>
    
4. <span data-ttu-id="450b1-118">トポロジ ビルダーで **、[Skype for Business Server]** を展開し、サイトの名前を展開し **、[Enterprise Edition** フロントエンド プール] を展開し、プールの 1 つの名前を右クリックし、[プロパティの編集] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="450b1-118">In Topology Builder, expand **Skype for Business Server**, expand the name of your site, expand **Enterprise Edition Front End pools**, right-click the name of one of your pools, and then click **Edit Properties**.</span></span>
    
5. <span data-ttu-id="450b1-119">[**プロパティの編集**] ダイアログ ボックスの [**全般**] タブで、[**Office Web Apps サーバーの関連付け**] という見出しを探し、[**新規作成**] をクリックします (または、ドロップダウン リストから既存の Office Web Apps サーバーを選択します)。</span><span class="sxs-lookup"><span data-stu-id="450b1-119">In the **Edit Properties** dialog box, on the **General** tab, find the heading **Associate Office Web Apps Server** and then click **New** (or select an existing Office Web Apps Server from the drop-down list).</span></span>
    
6. <span data-ttu-id="450b1-120">[**新しい Office Web Apps サーバーの定義**] ダイアログ ボックスで、Office Web Apps サーバー コンピューターの完全修飾ドメイン名 (FQDN) を [**Office Web Apps サーバーの FQDN**] ボックスに入力します。これを行うと、Office Web Apps サーバー検出の URL が [**Office Web Apps サーバー検出の URL**] ボックスに自動的に入力されます。</span><span class="sxs-lookup"><span data-stu-id="450b1-120">In the **Define New Office Web Apps Server** dialog box, type the fully qualified domain name (FQDN) of your Office Web Apps Server computer in the **Office Web Apps Server FQDN** box; when you do this, your Office Web Apps Server discovery URL should automatically be entered into the **Office Web Apps Server discovery URL** box.</span></span>
    
   - <span data-ttu-id="450b1-121">Office Web Apps サーバーがオンプレミスで Skype for Business Server と同じネットワーク 領域にインストールされている場合は、オプション **Office Web Apps Server** が外部ネットワーク (境界/インターネット) に展開される必要があります。</span><span class="sxs-lookup"><span data-stu-id="450b1-121">If the Office Web Apps Server is installed on-premises and in the same network zone as Skype for Business Server then the option **Office Web Apps Server is deployed in an external network (that is, perimeter/Internet)** should not be selected.</span></span>
    
   - <span data-ttu-id="450b1-122">Office Web Apps サーバーを内部ファイアウォールの外側に展開する場合は、[**Office Web Apps サーバーは外部ネットワークで展開 (境界ネットワークまたはインターネット)**] オプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="450b1-122">If the Office Web Apps Server is deployed outside your internal firewall, then select the option **Office Web Apps Server is deployed in an external network (that is, perimeter/Internet)**.</span></span>
    
7. <span data-ttu-id="450b1-123">[**新しい Office Web Apps サーバーの定義**] ダイアログ ボックスで、[**OK**] をクリックし、[**プロパティの編集**] ダイアログ ボックスで [**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="450b1-123">In the **Define New Office Web Apps Server** dialog box, click **OK**, and then click **OK** in the **Edit Properties** dialog box.</span></span> <span data-ttu-id="450b1-124">検出 URL は、プールの関連付けの 1 つとして一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="450b1-124">The discovery URL will then be listed as one of the pool's Associations.</span></span>
    
<span data-ttu-id="450b1-125">Office Web Apps サーバーに関連付ける必要がある各プールに対してこのプロセスを繰り返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="450b1-125">You will have to repeat this process for each pool that needs to be associated with your Office Web Apps Server.</span></span>
  
<span data-ttu-id="450b1-126">探索 URL をトポロジに追加したら、更新されたトポロジを公開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="450b1-126">After you have added the discovery URL to the topology, you must then publish the updated topology.</span></span> <span data-ttu-id="450b1-127">これを行うには、トポロジ ビルダーで次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="450b1-127">To do that in Topology Builder:</span></span>
  
1. <span data-ttu-id="450b1-128">[**操作**] をクリックし、[**トポロジの公開**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="450b1-128">Click **Action** and then click **Publish Topology**.</span></span>
    
2. <span data-ttu-id="450b1-129">トポロジの公開ウィザードの [**トポロジの公開**] ページで、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="450b1-129">In the Publish Topology wizard, on the **Publish the Topology** page, click **Next**.</span></span>
    
3. <span data-ttu-id="450b1-130">[**公開ウィザードの完了**] ページで、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="450b1-130">On the **Publishing wizard complete** page, click **Finish**.</span></span>
    
4. <span data-ttu-id="450b1-131">トポロジ ビルダーを閉じます。</span><span class="sxs-lookup"><span data-stu-id="450b1-131">Close Topology Builder.</span></span>
    
## <a name="configure-access-for-external-users"></a><span data-ttu-id="450b1-132">外部ユーザーのアクセスを構成する</span><span class="sxs-lookup"><span data-stu-id="450b1-132">Configure access for external users</span></span>

<span data-ttu-id="450b1-133">外部ユーザー (つまり、組織のファイアウォールの外部からログオンしているユーザー) に Office Web Apps Server PowerPoint プレゼンテーションへのアクセスを許可する場合は、Office Web Apps Server とリバース プロキシ サーバーを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="450b1-133">If you want external users (that is, users logging on from outside your organization's firewall) to have access to Office Web Apps Server PowerPoint presentations, then you will need to use Office Web Apps Server and a reverse proxy server.</span></span> <span data-ttu-id="450b1-134">また、ユーザーがサーバーに接続できる Web サイト発行ルールを作成して構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="450b1-134">You will also need to create and configure a website publishing rule, which will help ensure that users are able to connect to the server.</span></span> 
  
## <a name="validate-the-configuration"></a><span data-ttu-id="450b1-135">構成の検証</span><span class="sxs-lookup"><span data-stu-id="450b1-135">Validate the configuration</span></span>

<span data-ttu-id="450b1-136">Web Officeサーバーがトポロジに追加され、そのトポロジが公開された後、Skype for Business Server イベント ログに 2 つの新しいイベント ログ イベントが表示されます。</span><span class="sxs-lookup"><span data-stu-id="450b1-136">After Office Web Apps Server has been added to the topology, and after that topology has been published, you should see two new event log events in the Skype for Business Server event log.</span></span> <span data-ttu-id="450b1-137">まず、LS データ MCU イベント (イベント ID 41034) を追加する必要があります。このイベントは、Web Apps サーバー Officeが検出されたと報告します。</span><span class="sxs-lookup"><span data-stu-id="450b1-137">First, an LS Data MCU event (event ID 41034) should be added; this event will report that the Office Web Apps Server has been discovered:</span></span>
  
 <span data-ttu-id="450b1-138">**Web Apps サーバー Office Web 会議サーバーが検出された場合、PowerPoint コンテンツが有効になります。**</span><span class="sxs-lookup"><span data-stu-id="450b1-138">**Web Conferencing Server Office Web Apps Server is discovered, PowerPoint content is enabled.**</span></span>
  
<span data-ttu-id="450b1-p109">これに加えて、Office Web Apps Server URL を報告する別の LS Data MCU イベント (イベント ID 41032) が表示されます。たとえば、次のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="450b1-p109">In addition to that you should see another LS Data MCU event (event ID 41032) that reports back Office Web Apps Server URLs. For example, you should see something similar to this:</span></span>
  
 <span data-ttu-id="450b1-141">**Web Apps サーバー Office Web 会議サーバーの検出が成功しました。**</span><span class="sxs-lookup"><span data-stu-id="450b1-141">**Web Conferencing Server Office Web Apps Server discovery has succeeded.**</span></span>
  
 <span data-ttu-id="450b1-142">**Office Web Apps Server の内部発表者ページ: https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0&amp ;embed=**</span><span class="sxs-lookup"><span data-stu-id="450b1-142">**Office Web Apps Server internal presenter page: https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0&amp;embed=**</span></span>
  
 <span data-ttu-id="450b1-143">**Office Web Apps Server の内部出席者ページ: https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0&amp ;embed=true&amp;=**</span><span class="sxs-lookup"><span data-stu-id="450b1-143">**Office Web Apps Server internal attendee page: https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0&amp;embed=true&amp;=**</span></span>
  
<span data-ttu-id="450b1-144">外部ユーザーのアクセスを構成している場合は、次のような情報も表示されます。</span><span class="sxs-lookup"><span data-stu-id="450b1-144">If you have configured access for external users, you will also see something similar to:</span></span>
  
 <span data-ttu-id="450b1-145">**Office Web Apps Server 外部発表者ページ: https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0&amp ;embed**</span><span class="sxs-lookup"><span data-stu-id="450b1-145">**Office Web Apps Server external presenter page: https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0&amp;embed**</span></span>
  
 <span data-ttu-id="450b1-146">**Office Web Apps Server の内部出席者 <https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0&amp;embed=true&amp> ページ:**</span><span class="sxs-lookup"><span data-stu-id="450b1-146">**Office Web Apps Server internal attendee page: <https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0&amp;embed=true&amp>;**</span></span>
  
<span data-ttu-id="450b1-147">イベント ID が 41033 の LS Data MCU イベントが表示された場合、Office Web Apps Server の検出が失敗したことを意味します。</span><span class="sxs-lookup"><span data-stu-id="450b1-147">If you see an LS Data MCU event with the event ID of 41033 that means that Office Web Apps Server discovery has failed.</span></span> <span data-ttu-id="450b1-148">その場合、Skype for Business Server は、新しく構成された Web Apps サーバーを検出するために必要な回数Office試します。</span><span class="sxs-lookup"><span data-stu-id="450b1-148">In that case, Skype for Business Server will try as many times as needed to discover the newly-configured Office Web Apps Server.</span></span> <span data-ttu-id="450b1-149">検出プロセスが繰り返し失敗する場合、Office Web Apps Server をトポロジー ドキュメントから削除し、更新されたトポロジーを公開し、接続の問題が解決された後に Office Web Apps Server をトポロジーに再度追加します。</span><span class="sxs-lookup"><span data-stu-id="450b1-149">If the discovery process fails repeatedly you should remove Office Web Apps Server from your topology document, publish the updated topology, and then try adding Office Web Apps Server back to the topology after the connectivity issues have been resolved.</span></span>
  
<span data-ttu-id="450b1-150">Office Web Apps サーバーが正しく構成されている場合、検出プロセスによって認識されている場合は、2 つの Skype for Business クライアント間で PowerPoint プレゼンテーションを共有することで、Office Web Apps Server が期待通り動作しているのを確認できます。</span><span class="sxs-lookup"><span data-stu-id="450b1-150">If Office Web Apps Server appears to be configured correctly and has been recognized by the discovery process you can verify that Office Web Apps Server is working as expected by sharing a PowerPoint presentation between a pair of Skype for Business clients.</span></span> <span data-ttu-id="450b1-151">ユーザー A が PowerPoint プレゼンテーションを読み込んで表示でき、ユーザー B が会議に参加してそのプレゼンテーションを表示できる場合、Office Web Apps Server は機能しています。</span><span class="sxs-lookup"><span data-stu-id="450b1-151">If User A can load and display the PowerPoint presentation and if User B can then join the meeting and see that presentation then Office Web Apps Server is working.</span></span>
  
<span data-ttu-id="450b1-152">Web Apps サーバー Office正しく構成されている場合でも、PowerPoint プレゼンテーションを共有しようとするときに、「サーバー接続の問題により一部の共有機能が利用できない」というエラー メッセージが表示される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="450b1-152">Even if Office Web Apps Server appears to be configured correctly, you could potentially receive the error message "Some sharing features are unavailable due to server connectivity issues" when you try sharing a PowerPoint presentation.</span></span> <span data-ttu-id="450b1-153">このエラー メッセージを受け取った場合、新しい Office Web Apps Server に関連したフロントエンド サーバー (場合によっては複数) を再起動します。</span><span class="sxs-lookup"><span data-stu-id="450b1-153">If you receive that error message you should restart the Front End server (or servers) associated with the new Office Web Apps Server.</span></span>
