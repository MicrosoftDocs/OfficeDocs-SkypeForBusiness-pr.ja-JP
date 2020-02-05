---
title: Skype for Business Server の Office Web Apps サーバーとの統合を構成する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b7e9149e-bf16-4120-afe0-3ee09c88f5eb
description: '概要: このトピックでは、Office Web Apps サーバーと Skype for Business Server の統合を構成し、Web 会議用の PowerPoint プレゼンテーションを有効にする方法について説明します。'
ms.openlocfilehash: b20646f31a7925ca66180c1580751574152047e5
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768350"
---
# <a name="configure-integration-with-office-web-apps-server-in-skype-for-business-server"></a><span data-ttu-id="138b6-103">Skype for Business Server の Office Web Apps サーバーとの統合を構成する</span><span class="sxs-lookup"><span data-stu-id="138b6-103">Configure integration with Office Web Apps Server in Skype for Business Server</span></span>
 
<span data-ttu-id="138b6-104">**概要:** このトピックでは、Office Web Apps サーバーと Skype for Business Server の統合を構成して、Web 会議用の PowerPoint プレゼンテーションを有効にする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="138b6-104">**Summary:** Read this topic to learn how to configure integration between Office Web Apps Server and Skype for Business Server to enable PowerPoint presentations for web conferencing.</span></span>
  
<span data-ttu-id="138b6-105">Skype for Business Server は Office Web Apps サーバーを使用して、web 会議用の PowerPoint プレゼンテーションを処理します。</span><span class="sxs-lookup"><span data-stu-id="138b6-105">Skype for Business Server employs Office Web Apps Server to handle PowerPoint presentations for web conferencing.</span></span> <span data-ttu-id="138b6-106">この方法の利点については、「 [Skype For Business Server の会議の計画](../../plan-your-deployment/conferencing/conferencing.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="138b6-106">For information about the advantages to this approach, see [Plan for conferencing in Skype for Business Server](../../plan-your-deployment/conferencing/conferencing.md).</span></span>
  
<span data-ttu-id="138b6-107">Skype for Business Server で Office Web Apps サーバーを使用するように構成するには、Office Web Apps サーバーが既に展開され、構成されていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="138b6-107">Before you can configure Skype for Business Server to use Office Web Apps Server, you must ensure that Office Web Apps Server is already deployed and configured.</span></span> <span data-ttu-id="138b6-108">Office Web Apps サーバーについては、「[インフラストラクチャを展開する: Office Online server](https://go.microsoft.com/fwlink/p/?linkid=257525)」の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="138b6-108">For information on Office Web Apps Server, see the article [Deploy the infrastructure: Office Online Server](https://go.microsoft.com/fwlink/p/?linkid=257525).</span></span> 
  
<span data-ttu-id="138b6-109">Office Web Apps サーバーが正常にインストールされ、Web ファームが正常に構成されたら、Office Web Apps Server discovery URL を Skype for Business に追加して、新しいサーバーと通信するように Skype for Business Server を構成する必要があります。サーバートポロジ。</span><span class="sxs-lookup"><span data-stu-id="138b6-109">After Office Web Apps Server has been successfully installed and your Web farm correctly configured, you must then configure Skype for Business Server to communicate with the new server by adding the Office Web Apps Server discovery URL to your Skype for Business Server topology.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="138b6-110">Office Web Apps サーバーの最新のイテレーションは、Skype for Business Server でサポートされている Office Online Server という名前です。</span><span class="sxs-lookup"><span data-stu-id="138b6-110">The latest iteration of Office Web Apps Server is named Office Online Server, which is supported by Skype for Business Server.</span></span> <span data-ttu-id="138b6-111">詳細については、「 [Office Online Server のドキュメント](https://technet.microsoft.com/en-us/library/jj219456%28v=office.16%29.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="138b6-111">For more detail, refer to the [Office Online Server documentation](https://technet.microsoft.com/en-us/library/jj219456%28v=office.16%29.aspx).</span></span> 
  
## <a name="configure-skype-for-business-server-to-communicate-with-office-web-apps-server"></a><span data-ttu-id="138b6-112">Office Web Apps サーバーと通信できるように Skype for Business Server を構成する</span><span class="sxs-lookup"><span data-stu-id="138b6-112">Configure Skype for Business Server to communicate with Office Web Apps Server</span></span>

<span data-ttu-id="138b6-113">トポロジに Office Web Apps サーバーを追加するには、次の手順を行います。</span><span class="sxs-lookup"><span data-stu-id="138b6-113">To add Office Web Apps Server to your topology, complete the following steps:</span></span>
  
1. <span data-ttu-id="138b6-114">Skype for Business Server トポロジビルダーを開きます。</span><span class="sxs-lookup"><span data-stu-id="138b6-114">Open Skype for Business Server Topology Builder.</span></span>
    
2. <span data-ttu-id="138b6-115">[**トポロジ ビルダー**] ダイアログ ボックスで、[**既存の展開からトポロジをダウンロードする**] を選択して [**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="138b6-115">In the **Topology Builder** dialog box, select **Download Topology from existing deployment** and then click **OK**.</span></span>
    
3. <span data-ttu-id="138b6-p104">[**トポロジに名前を付けて保存**] ダイアログ ボックスで、トポロジ ドキュメントの名前 (例: **PreWebAppsServerTopology**) を [**ファイル名**] ボックスに入力し、[**保存**] をクリックします。新しいトポロジで問題が発生した場合、後でこのトポロジを取得して再発行できます。</span><span class="sxs-lookup"><span data-stu-id="138b6-p104">In the **Save Topology As** dialog box, type a name for your topology document (for example, **PreWebAppsServerTopology**) in the **File name** box and then click **Save**. This topology can later be retrieved and republished if you encounter problems with your new topology.</span></span>
    
4. <span data-ttu-id="138b6-118">トポロジ ビルダーで、[**Skype for Business Server**]、ユーザーのサイトの名前、[**Enterprise Edition フロントエンド プール**] の順に展開します。いずれかのプールの名前を右クリックし、[**プロパティの編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="138b6-118">In Topology Builder, expand **Skype for Business Server**, expand the name of your site, expand **Enterprise Edition Front End pools**, right-click the name of one of your pools, and then click **Edit Properties**.</span></span>
    
5. <span data-ttu-id="138b6-119">[**プロパティの編集**] ダイアログ ボックスの [**全般**] タブで、[**Office Web Apps サーバーの関連付け**] という見出しを探し、[**新規作成**] をクリックします (または、ドロップダウン リストから既存の Office Web Apps サーバーを選択します)。</span><span class="sxs-lookup"><span data-stu-id="138b6-119">In the **Edit Properties** dialog box, on the **General** tab, find the heading **Associate Office Web Apps Server** and then click **New** (or select an existing Office Web Apps Server from the drop-down list).</span></span>
    
6. <span data-ttu-id="138b6-120">[**新しい Office Web Apps サーバーの定義**] ダイアログ ボックスで、Office Web Apps サーバー コンピューターの完全修飾ドメイン名 (FQDN) を [**Office Web Apps サーバーの FQDN**] ボックスに入力します。これを行うと、Office Web Apps サーバー検出の URL が [**Office Web Apps サーバー検出の URL**] ボックスに自動的に入力されます。</span><span class="sxs-lookup"><span data-stu-id="138b6-120">In the **Define New Office Web Apps Server** dialog box, type the fully qualified domain name (FQDN) of your Office Web Apps Server computer in the **Office Web Apps Server FQDN** box; when you do this, your Office Web Apps Server discovery URL should automatically be entered into the **Office Web Apps Server discovery URL** box.</span></span>
    
   - <span data-ttu-id="138b6-121">Office Web Apps サーバーがオンプレミスでインストールされていて、Skype for Business Server と同じネットワークゾーンにインストールされている場合は、 **Office Web Apps サーバーは外部ネットワーク ([境界/インターネット]) に展開**されます。</span><span class="sxs-lookup"><span data-stu-id="138b6-121">If the Office Web Apps Server is installed on-premises and in the same network zone as Skype for Business Server then the option **Office Web Apps Server is deployed in an external network (that is, perimeter/Internet)** should not be selected.</span></span>
    
   - <span data-ttu-id="138b6-122">Office Web Apps サーバーを内部ファイアウォールの外側に展開する場合は、[**Office Web Apps サーバーは外部ネットワークで展開 (境界ネットワークまたはインターネット)**] オプションをオンにします。</span><span class="sxs-lookup"><span data-stu-id="138b6-122">If the Office Web Apps Server is deployed outside your internal firewall, then select the option **Office Web Apps Server is deployed in an external network (that is, perimeter/Internet)**.</span></span>
    
7. <span data-ttu-id="138b6-123">[**新しい Office Web Apps サーバーの定義**] ダイアログ ボックスで、[**OK**] をクリックし、[**プロパティの編集**] ダイアログ ボックスで [**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="138b6-123">In the **Define New Office Web Apps Server** dialog box, click **OK**, and then click **OK** in the **Edit Properties** dialog box.</span></span> <span data-ttu-id="138b6-124">検出 URL がプールの関連付けの1つとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="138b6-124">The discovery URL will then be listed as one of the pool's Associations.</span></span>
    
<span data-ttu-id="138b6-125">Office Web Apps サーバーに関連付ける必要がある各プールに対してこのプロセスを繰り返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="138b6-125">You will have to repeat this process for each pool that needs to be associated with your Office Web Apps Server.</span></span>
  
<span data-ttu-id="138b6-p106">検出 URL をトポロジに追加した後、更新されたトポロジを公開する必要があります。これを行うには、トポロジ ビルダーで次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="138b6-p106">After you have added the discovery URL to the topology, you must then publish the updated topology. To do that in Topology Builder:</span></span>
  
1. <span data-ttu-id="138b6-128">[**操作**] をクリックし、[**トポロジの公開**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="138b6-128">Click **Action** and then click **Publish Topology**.</span></span>
    
2. <span data-ttu-id="138b6-129">トポロジの公開ウィザードの [**トポロジの公開**] ページで、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="138b6-129">In the Publish Topology wizard, on the **Publish the Topology** page, click **Next**.</span></span>
    
3. <span data-ttu-id="138b6-130">[**公開ウィザードの完了**] ページで、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="138b6-130">On the **Publishing wizard complete** page, click **Finish**.</span></span>
    
4. <span data-ttu-id="138b6-131">トポロジ ビルダーを閉じます。</span><span class="sxs-lookup"><span data-stu-id="138b6-131">Close Topology Builder.</span></span>
    
## <a name="configure-access-for-external-users"></a><span data-ttu-id="138b6-132">外部ユーザー用のアクセスの構成</span><span class="sxs-lookup"><span data-stu-id="138b6-132">Configure access for external users</span></span>

<span data-ttu-id="138b6-133">外部ユーザー (つまり、組織のファイアウォール外からログオンしているユーザー) が Office Web Apps Server PowerPoint プレゼンテーションにアクセスできるようにするには、Office Web Apps サーバーとリバースプロキシサーバーを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="138b6-133">If you want external users (that is, users logging on from outside your organization's firewall) to have access to Office Web Apps Server PowerPoint presentations, then you will need to use Office Web Apps Server and a reverse proxy server.</span></span> <span data-ttu-id="138b6-134">また、web サイトの公開ルールを作成して構成する必要があります。これは、ユーザーがサーバーに接続できるようにするために役立ちます。</span><span class="sxs-lookup"><span data-stu-id="138b6-134">You will also need to create and configure a website publishing rule, which will help ensure that users are able to connect to the server.</span></span> 
  
## <a name="validate-the-configuration"></a><span data-ttu-id="138b6-135">構成を検証する</span><span class="sxs-lookup"><span data-stu-id="138b6-135">Validate the configuration</span></span>

<span data-ttu-id="138b6-136">Office Web Apps サーバーをトポロジに追加した後で、そのトポロジが公開されると、Skype for Business Server イベントログに2つの新しいイベントログイベントが表示されます。</span><span class="sxs-lookup"><span data-stu-id="138b6-136">After Office Web Apps Server has been added to the topology, and after that topology has been published, you should see two new event log events in the Skype for Business Server event log.</span></span> <span data-ttu-id="138b6-137">最初に、LS データ MCU イベント (イベント ID 41034) を追加する必要があります。このイベントは、Office Web Apps サーバーが検出されたことを報告します。</span><span class="sxs-lookup"><span data-stu-id="138b6-137">First, an LS Data MCU event (event ID 41034) should be added; this event will report that the Office Web Apps Server has been discovered:</span></span>
  
 <span data-ttu-id="138b6-138">**Web 会議サーバー Office Web Apps サーバーが検出され、PowerPoint コンテンツが有効になりました。**</span><span class="sxs-lookup"><span data-stu-id="138b6-138">**Web Conferencing Server Office Web Apps Server is discovered, PowerPoint content is enabled.**</span></span>
  
<span data-ttu-id="138b6-p109">これに加えて、Office Web Apps Server URL を報告する別の LS Data MCU イベント (イベント ID 41032) が表示されます。たとえば、次のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="138b6-p109">In addition to that you should see another LS Data MCU event (event ID 41032) that reports back Office Web Apps Server URLs. For example, you should see something similar to this:</span></span>
  
 <span data-ttu-id="138b6-141">**Web 会議サーバー Office Web Apps サーバー検出が成功しました。**</span><span class="sxs-lookup"><span data-stu-id="138b6-141">**Web Conferencing Server Office Web Apps Server discovery has succeeded.**</span></span>
  
 <span data-ttu-id="138b6-142">**Office Web Apps サーバーの内部発表者https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0&ampページ:; 埋め込み =**</span><span class="sxs-lookup"><span data-stu-id="138b6-142">**Office Web Apps Server internal presenter page: https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0&amp;embed=**</span></span>
  
 <span data-ttu-id="138b6-143">**Office Web Apps サーバーの内部出席者ページhttps://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0&amp:; 埋め込み = true&amp;=**</span><span class="sxs-lookup"><span data-stu-id="138b6-143">**Office Web Apps Server internal attendee page: https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0&amp;embed=true&amp;=**</span></span>
  
<span data-ttu-id="138b6-144">外部ユーザーへのアクセスを構成している場合は、次のような内容も表示されます。</span><span class="sxs-lookup"><span data-stu-id="138b6-144">If you have configured access for external users, you will also see something similar to:</span></span>
  
 <span data-ttu-id="138b6-145">**Office Web Apps サーバーの外部発表者https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0&ampページ:; 埋め込み**</span><span class="sxs-lookup"><span data-stu-id="138b6-145">**Office Web Apps Server external presenter page: https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0&amp;embed**</span></span>
  
 <span data-ttu-id="138b6-146">**Office Web Apps サーバーの内部出席者ページ<https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0&amp;embed=true&amp>:;**</span><span class="sxs-lookup"><span data-stu-id="138b6-146">**Office Web Apps Server internal attendee page: <https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0&amp;embed=true&amp>;**</span></span>
  
<span data-ttu-id="138b6-147">Office Web Apps サーバーの検出に失敗したことを示す、イベント ID が41033の LS データ MCU イベントが表示される場合。</span><span class="sxs-lookup"><span data-stu-id="138b6-147">If you see an LS Data MCU event with the event ID of 41033 that means that Office Web Apps Server discovery has failed.</span></span> <span data-ttu-id="138b6-148">この場合、Skype for Business Server は、新しく構成された Office Web Apps サーバーを検出するために必要な回数だけ試します。</span><span class="sxs-lookup"><span data-stu-id="138b6-148">In that case, Skype for Business Server will try as many times as needed to discover the newly-configured Office Web Apps Server.</span></span> <span data-ttu-id="138b6-149">検出プロセスが繰り返し失敗する場合は、トポロジドキュメントから Office Web Apps サーバーを削除し、更新されたトポロジを公開して、接続の問題が解決した後で、Office Web Apps サーバーをトポロジに追加してみます。</span><span class="sxs-lookup"><span data-stu-id="138b6-149">If the discovery process fails repeatedly you should remove Office Web Apps Server from your topology document, publish the updated topology, and then try adding Office Web Apps Server back to the topology after the connectivity issues have been resolved.</span></span>
  
<span data-ttu-id="138b6-150">Office Web Apps サーバーが正しく構成されていて、検出プロセスによって認識されている場合、Office Web Apps サーバーが正常に動作していることを確認するには、1組の Skype for Business クライアント間で PowerPoint プレゼンテーションを共有します。</span><span class="sxs-lookup"><span data-stu-id="138b6-150">If Office Web Apps Server appears to be configured correctly and has been recognized by the discovery process you can verify that Office Web Apps Server is working as expected by sharing a PowerPoint presentation between a pair of Skype for Business clients.</span></span> <span data-ttu-id="138b6-151">ユーザー A が PowerPoint プレゼンテーションを読み込み、表示できる場合に、ユーザー B が会議に参加すると、そのプレゼンテーションが Office Web Apps サーバーで動作することを確認できます。</span><span class="sxs-lookup"><span data-stu-id="138b6-151">If User A can load and display the PowerPoint presentation and if User B can then join the meeting and see that presentation then Office Web Apps Server is working.</span></span>
  
<span data-ttu-id="138b6-152">Office Web Apps サーバーが正しく構成されているように見えても、PowerPoint プレゼンテーションを共有しようとすると、"サーバーの接続に問題が発生したため、一部の共有機能を利用できません" というエラーメッセージが表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="138b6-152">Even if Office Web Apps Server appears to be configured correctly, you could potentially receive the error message "Some sharing features are unavailable due to server connectivity issues" when you try sharing a PowerPoint presentation.</span></span> <span data-ttu-id="138b6-153">このエラーメッセージが表示された場合は、新しい Office Web Apps サーバーに関連付けられたフロントエンドサーバー (またはサーバー) を再起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="138b6-153">If you receive that error message you should restart the Front End server (or servers) associated with the new Office Web Apps Server.</span></span>
  

