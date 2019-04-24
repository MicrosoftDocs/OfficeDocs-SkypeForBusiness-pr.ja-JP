---
title: ビジネス サーバー用の Skype では、Office Web アプリケーション サーバーとの統合を構成します。
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b7e9149e-bf16-4120-afe0-3ee09c88f5eb
description: '概要: は、PowerPoint のプレゼンテーションを web 会議を有効にするには、Office Web アプリケーション サーバーと Skype ビジネス サーバーの間の統合を構成する方法については、このトピックを読みます。'
ms.openlocfilehash: 69cdbd50387f2e3267a0fc2acb38e47260970578
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32223825"
---
# <a name="configure-integration-with-office-web-apps-server-in-skype-for-business-server"></a><span data-ttu-id="f2f5f-103">ビジネス サーバー用の Skype では、Office Web アプリケーション サーバーとの統合を構成します。</span><span class="sxs-lookup"><span data-stu-id="f2f5f-103">Configure integration with Office Web Apps Server in Skype for Business Server</span></span>
 
<span data-ttu-id="f2f5f-104">**の概要:** Office Web アプリケーション サーバーと web 会議のための PowerPoint プレゼンテーションを有効にする Skype ビジネス サーバーの間の統合を構成する方法については、このトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f2f5f-104">**Summary:** Read this topic to learn how to configure integration between Office Web Apps Server and Skype for Business Server to enable PowerPoint presentations for web conferencing.</span></span>
  
<span data-ttu-id="f2f5f-105">Skype ビジネス サーバー用には、web 会議のための PowerPoint プレゼンテーションを処理するために Office の Web アプリケーション サーバーが使用されています。</span><span class="sxs-lookup"><span data-stu-id="f2f5f-105">Skype for Business Server employs Office Web Apps Server to handle PowerPoint presentations for web conferencing.</span></span> <span data-ttu-id="f2f5f-106">このアプローチの利点の詳細については、[ビジネスのサーバー用の Skype での会議の計画](../../plan-your-deployment/conferencing/conferencing.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f2f5f-106">For information about the advantages to this approach, see [Plan for conferencing in Skype for Business Server](../../plan-your-deployment/conferencing/conferencing.md).</span></span>
  
<span data-ttu-id="f2f5f-107">ビジネス サーバーは、Office Web アプリケーション サーバーを使用するの Skype を構成することができます、前に、Office Web アプリケーション サーバーが既に展開され、構成されていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f2f5f-107">Before you can configure Skype for Business Server to use Office Web Apps Server, you must ensure that Office Web Apps Server is already deployed and configured.</span></span> <span data-ttu-id="f2f5f-108">Office Web アプリケーション サーバーについては、資料を参照してください[インフラストラクチャを展開します。 Office オンラインのサーバー](https://go.microsoft.com/fwlink/p/?linkid=257525)。</span><span class="sxs-lookup"><span data-stu-id="f2f5f-108">For information on Office Web Apps Server, see the article [Deploy the infrastructure: Office Online Server](https://go.microsoft.com/fwlink/p/?linkid=257525).</span></span> 
  
<span data-ttu-id="f2f5f-109">Office Web アプリケーション サーバーが正常にインストールされて正しく構成されている Web ファーム、行う必要がありますし、Skype、Skype をビジネスのために Office の Web アプリケーション サーバーの検出 URL を追加することによって新しいサーバーと通信するためにビジネスのサーバーの後サーバー トポロジです。</span><span class="sxs-lookup"><span data-stu-id="f2f5f-109">After Office Web Apps Server has been successfully installed and your Web farm correctly configured, you must then configure Skype for Business Server to communicate with the new server by adding the Office Web Apps Server discovery URL to your Skype for Business Server topology.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="f2f5f-110">Office オンライン サーバー、ビジネス サーバーの Skype がサポートしている Office Web アプリケーション サーバーの最新のイテレーションの名前です。</span><span class="sxs-lookup"><span data-stu-id="f2f5f-110">The latest iteration of Office Web Apps Server is named Office Online Server, which is supported by Skype for Business Server.</span></span> <span data-ttu-id="f2f5f-111">詳細については、 [Office オンラインのサーバーのマニュアル](https://technet.microsoft.com/en-us/library/jj219456%28v=office.16%29.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f2f5f-111">For more detail, refer to the [Office Online Server documentation](https://technet.microsoft.com/en-us/library/jj219456%28v=office.16%29.aspx).</span></span> 
  
## <a name="configure-skype-for-business-server-to-communicate-with-office-web-apps-server"></a><span data-ttu-id="f2f5f-112">Office Web アプリケーション サーバーと通信するサーバーをビジネス用の Skype を構成します。</span><span class="sxs-lookup"><span data-stu-id="f2f5f-112">Configure Skype for Business Server to communicate with Office Web Apps Server</span></span>

<span data-ttu-id="f2f5f-113">トポロジに Office Web Apps サーバーを追加するには、次の手順を行います。</span><span class="sxs-lookup"><span data-stu-id="f2f5f-113">To add Office Web Apps Server to your topology, complete the following steps:</span></span>
  
1. <span data-ttu-id="f2f5f-114">Skype をビジネス サーバー トポロジ ビルダーを開きます。</span><span class="sxs-lookup"><span data-stu-id="f2f5f-114">Open Skype for Business Server Topology Builder.</span></span>
    
2. <span data-ttu-id="f2f5f-115">[**トポロジ ビルダー**] ダイアログ ボックスで、[**既存の展開からトポロジをダウンロードする**] を選択して [**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f2f5f-115">In the **Topology Builder** dialog box, select **Download Topology from existing deployment** and then click **OK**.</span></span>
    
3. <span data-ttu-id="f2f5f-p104">[**トポロジに名前を付けて保存**] ダイアログ ボックスで、トポロジ ドキュメントの名前 (例: **PreWebAppsServerTopology**) を [**ファイル名**] ボックスに入力し、[**保存**] をクリックします。新しいトポロジで問題が発生した場合、後でこのトポロジを取得して再発行できます。</span><span class="sxs-lookup"><span data-stu-id="f2f5f-p104">In the **Save Topology As** dialog box, type a name for your topology document (for example, **PreWebAppsServerTopology**) in the **File name** box and then click **Save**. This topology can later be retrieved and republished if you encounter problems with your new topology.</span></span>
    
4. <span data-ttu-id="f2f5f-118">トポロジ ビルダーで、[**Skype for Business Server**]、ユーザーのサイトの名前、[**Enterprise Edition フロントエンド プール**] の順に展開します。いずれかのプールの名前を右クリックし、[**プロパティの編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f2f5f-118">In Topology Builder, expand **Skype for Business Server**, expand the name of your site, expand **Enterprise Edition Front End pools**, right-click the name of one of your pools, and then click **Edit Properties**.</span></span>
    
5. <span data-ttu-id="f2f5f-119">[**プロパティの編集**] ダイアログ ボックスの [**全般**] タブで、[**Office Web Apps サーバーの関連付け**] という見出しを探し、[**新規作成**] をクリックします (または、ドロップダウン リストから既存の Office Web Apps サーバーを選択します)。</span><span class="sxs-lookup"><span data-stu-id="f2f5f-119">In the **Edit Properties** dialog box, on the **General** tab, find the heading **Associate Office Web Apps Server** and then click **New** (or select an existing Office Web Apps Server from the drop-down list).</span></span>
    
6. <span data-ttu-id="f2f5f-120">[**新しい Office Web Apps サーバーの定義**] ダイアログ ボックスで、Office Web Apps サーバー コンピューターの完全修飾ドメイン名 (FQDN) を [**Office Web Apps サーバーの FQDN**] ボックスに入力します。これを行うと、Office Web Apps サーバー検出の URL が [**Office Web Apps サーバー検出の URL**] ボックスに自動的に入力されます。</span><span class="sxs-lookup"><span data-stu-id="f2f5f-120">In the **Define New Office Web Apps Server** dialog box, type the fully qualified domain name (FQDN) of your Office Web Apps Server computer in the **Office Web Apps Server FQDN** box; when you do this, your Office Web Apps Server discovery URL should automatically be entered into the **Office Web Apps Server discovery URL** box.</span></span>
    
   - <span data-ttu-id="f2f5f-121">Office Web アプリケーション サーバーがインストールされている設置型の場合と、ネットワークと同じゾーンのビジネス サーバー オプションでは、Skype で**Office Web アプリケーション サーバーが外部ネットワーク (つまり、境界領域またはインターネット) に配置**する必要がありますオフにします。</span><span class="sxs-lookup"><span data-stu-id="f2f5f-121">If the Office Web Apps Server is installed on-premises and in the same network zone as Skype for Business Server then the option **Office Web Apps Server is deployed in an external network (that is, perimeter/Internet)** should not be selected.</span></span>
    
   - <span data-ttu-id="f2f5f-122">Office Web Apps サーバーを内部ファイアウォールの外側に展開する場合は、[**Office Web Apps サーバーは外部ネットワークで展開 (境界ネットワークまたはインターネット)**] オプションをオンにします。</span><span class="sxs-lookup"><span data-stu-id="f2f5f-122">If the Office Web Apps Server is deployed outside your internal firewall, then select the option **Office Web Apps Server is deployed in an external network (that is, perimeter/Internet)**.</span></span>
    
7. <span data-ttu-id="f2f5f-p105">[**新しい Office Web Apps サーバーの定義**] ダイアログ ボックスで、[**OK**] をクリックし、[**プロパティの編集**] ダイアログ ボックスで [**OK**] をクリックします。Office Online の検出 URL がプールの関連付けの 1 つとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="f2f5f-p105">In the **Define New Office Web Apps Server** dialog box, click **OK**, and then click **OK** in the **Edit Properties** dialog box. The Office Online discovery URL will then be listed as one of the pool's Associations.</span></span>
    
<span data-ttu-id="f2f5f-125">Office Web Apps サーバーに関連付ける必要がある各プールに対してこのプロセスを繰り返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="f2f5f-125">You will have to repeat this process for each pool that needs to be associated with your Office Web Apps Server.</span></span>
  
<span data-ttu-id="f2f5f-p106">検出 URL をトポロジに追加した後、更新されたトポロジを公開する必要があります。これを行うには、トポロジ ビルダーで次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="f2f5f-p106">After you have added the discovery URL to the topology, you must then publish the updated topology. To do that in Topology Builder:</span></span>
  
1. <span data-ttu-id="f2f5f-128">[**操作**] をクリックし、[**トポロジの公開**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f2f5f-128">Click **Action** and then click **Publish Topology**.</span></span>
    
2. <span data-ttu-id="f2f5f-129">トポロジの公開ウィザードの [**トポロジの公開**] ページで、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f2f5f-129">In the Publish Topology wizard, on the **Publish the Topology** page, click **Next**.</span></span>
    
3. <span data-ttu-id="f2f5f-130">[**公開ウィザードの完了**] ページで、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f2f5f-130">On the **Publishing wizard complete** page, click **Finish**.</span></span>
    
4. <span data-ttu-id="f2f5f-131">トポロジ ビルダーを閉じます。</span><span class="sxs-lookup"><span data-stu-id="f2f5f-131">Close Topology Builder.</span></span>
    
## <a name="configure-access-for-external-users"></a><span data-ttu-id="f2f5f-132">外部ユーザー用のアクセスの構成</span><span class="sxs-lookup"><span data-stu-id="f2f5f-132">Configure access for external users</span></span>

<span data-ttu-id="f2f5f-133">外部ユーザー (組織のファイアウォールの外側からログオンしているユーザー) をする場合、Office Web アプリケーション サーバーの PowerPoint プレゼンテーションにアクセスし、Office Web アプリケーション サーバーとリバース プロキシ サーバーを使用する必要がありますが。</span><span class="sxs-lookup"><span data-stu-id="f2f5f-133">If you want external users (that is, users logging on from outside your organization's firewall) to have access to Office Web Apps Server PowerPoint presentations, then you will need to use Office Web Apps Server and a reverse proxy server.</span></span> <span data-ttu-id="f2f5f-134">作成し、ユーザーがサーバーに接続することであることを確認に役立ちますが、web サイト公開ルールを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f2f5f-134">You will also need to create and configure a website publishing rule, which will help ensure that users are able to connect to the server.</span></span> 
  
## <a name="validate-the-configuration"></a><span data-ttu-id="f2f5f-135">構成を検証する</span><span class="sxs-lookup"><span data-stu-id="f2f5f-135">Validate the configuration</span></span>

<span data-ttu-id="f2f5f-136">Office Web アプリケーション サーバー、トポロジに追加した後、そのトポロジが公開された後、Skype のビジネス サーバーのイベント ログに新しいイベント ログのイベントを 2 つを参照してくださいする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f2f5f-136">After Office Web Apps Server has been added to the topology, and after that topology has been published, you should see two new event log events in the Skype for Business Server event log.</span></span> <span data-ttu-id="f2f5f-137">最初に、データ MCU の LS イベント (イベント ID 41034) を追加する必要があります。このイベントは、Office Web アプリケーション サーバーが検出されたことが報告されます。</span><span class="sxs-lookup"><span data-stu-id="f2f5f-137">First, an LS Data MCU event (event ID 41034) should be added; this event will report that the Office Web Apps Server has been discovered:</span></span>
  
 <span data-ttu-id="f2f5f-138">**Web 会議サーバー Office Web Apps サーバーが検出され、PowerPoint コンテンツが有効になりました。**</span><span class="sxs-lookup"><span data-stu-id="f2f5f-138">**Web Conferencing Server Office Web Apps Server is discovered, PowerPoint content is enabled.**</span></span>
  
<span data-ttu-id="f2f5f-p109">これに加えて、Office Web Apps Server URL を報告する別の LS Data MCU イベント (イベント ID 41032) が表示されます。たとえば、次のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="f2f5f-p109">In addition to that you should see another LS Data MCU event (event ID 41032) that reports back Office Web Apps Server URLs. For example, you should see something similar to this:</span></span>
  
 <span data-ttu-id="f2f5f-141">**Web 会議サーバー Office Web Apps サーバー検出が成功しました。**</span><span class="sxs-lookup"><span data-stu-id="f2f5f-141">**Web Conferencing Server Office Web Apps Server discovery has succeeded.**</span></span>
  
 <span data-ttu-id="f2f5f-142">**Office Web アプリケーション サーバー内部の発表者のページ: https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0&amp; 埋め込む =**</span><span class="sxs-lookup"><span data-stu-id="f2f5f-142">**Office Web Apps Server internal presenter page: https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0&amp;embed=**</span></span>
  
 <span data-ttu-id="f2f5f-143">**Office Web アプリケーション サーバー内部の出席者のページ: https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0&amp; 埋め込む = true&amp;=**</span><span class="sxs-lookup"><span data-stu-id="f2f5f-143">**Office Web Apps Server internal attendee page: https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0&amp;embed=true&amp;=**</span></span>
  
<span data-ttu-id="f2f5f-144">外部ユーザーのアクセスを構成した場合、以下のようにも表示されます。</span><span class="sxs-lookup"><span data-stu-id="f2f5f-144">If you have configured access for external users, you will also see something similar to:</span></span>
  
 <span data-ttu-id="f2f5f-145">**Office Web アプリケーション サーバーの外部発表のページ: https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0&amp; を埋め込む**</span><span class="sxs-lookup"><span data-stu-id="f2f5f-145">**Office Web Apps Server external presenter page: https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0&amp;embed**</span></span>
  
 <span data-ttu-id="f2f5f-146">**Office Web アプリケーション サーバー内部の出席者のページ:<https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0&amp;embed=true&amp>です。**</span><span class="sxs-lookup"><span data-stu-id="f2f5f-146">**Office Web Apps Server internal attendee page: <https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0&amp;embed=true&amp>;**</span></span>
  
<span data-ttu-id="f2f5f-147">表示する場合は、Office Web アプリケーション サーバーの検出のことを意味する 41033 のイベント ID を持つデータ MCU の LS イベントに失敗しました。</span><span class="sxs-lookup"><span data-stu-id="f2f5f-147">If you see an LS Data MCU event with the event ID of 41033 that means that Office Web Apps Server discovery has failed.</span></span> <span data-ttu-id="f2f5f-148">Skype ビジネス サーバーの場合は、新たに構成されている Office の Web アプリケーション サーバーを検出するために必要な回数だけ再試行されます。</span><span class="sxs-lookup"><span data-stu-id="f2f5f-148">In that case, Skype for Business Server will try as many times as needed to discover the newly-configured Office Web Apps Server.</span></span> <span data-ttu-id="f2f5f-149">検出プロセスが繰り返し失敗した場合、トポロジ ドキュメントから Office Web アプリケーション サーバーを削除、更新されたトポロジを公開する、接続の問題が解決された後に、トポロジに Office Web アプリケーション サーバーを追加してくださいしてください。</span><span class="sxs-lookup"><span data-stu-id="f2f5f-149">If the discovery process fails repeatedly you should remove Office Web Apps Server from your topology document, publish the updated topology, and then try adding Office Web Apps Server back to the topology after the connectivity issues have been resolved.</span></span>
  
<span data-ttu-id="f2f5f-150">Office Web アプリケーション サーバーを正しく構成するが表示され、検出プロセスによって認識された場合は、Skype のビジネス クライアント用のペアの間で PowerPoint プレゼンテーションを共有することで期待どおりに、Office Web アプリケーション サーバーが動作しているを確認できます。</span><span class="sxs-lookup"><span data-stu-id="f2f5f-150">If Office Web Apps Server appears to be configured correctly and has been recognized by the discovery process you can verify that Office Web Apps Server is working as expected by sharing a PowerPoint presentation between a pair of Skype for Business clients.</span></span> <span data-ttu-id="f2f5f-151">ユーザー A は、ロードし、PowerPoint プレゼンテーションを表示し、ユーザー B が会議に参加し、そのプレゼンテーションを参照してください場合は、Office Web アプリケーション サーバーが動作してください。</span><span class="sxs-lookup"><span data-stu-id="f2f5f-151">If User A can load and display the PowerPoint presentation and if User B can then join the meeting and see that presentation then Office Web Apps Server is working.</span></span>
  
<span data-ttu-id="f2f5f-152">正しく構成するのには、Office Web アプリケーション サーバーが表示されたら、たとえ可能性があります可能性があります、エラー メッセージが表示「いくつかの共有機能はサーバー接続の問題のために利用可能な」しようとすると、PowerPoint のプレゼンテーションを共有します。</span><span class="sxs-lookup"><span data-stu-id="f2f5f-152">Even if Office Web Apps Server appears to be configured correctly, you could potentially receive the error message "Some sharing features are unavailable due to server connectivity issues" when you try sharing a PowerPoint presentation.</span></span> <span data-ttu-id="f2f5f-153">そのエラー メッセージが表示される場合は、新しいオフィスの Web アプリケーション サーバーに関連付けられているフロント エンド サーバー (またはサーバー) を再起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f2f5f-153">If you receive that error message you should restart the Front End server (or servers) associated with the new Office Web Apps Server.</span></span>
  

