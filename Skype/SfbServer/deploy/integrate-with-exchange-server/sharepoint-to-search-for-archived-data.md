---
title: アーカイブされた Skype for Business データを検索するための SharePoint Server の構成
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 17f49365-8778-4962-a41b-f96faf6902f1
description: '概要: ビジネス サーバー 2015 2016 の Exchange Server や Exchange Server 2013 と Skype でアーカイブ データを検索するのには SharePoint サーバーを構成します。'
ms.openlocfilehash: 161e4dd530490d22d14f5392539e2cc3d788d6bd
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="configure-sharepoint-server-to-search-for-archived-skype-for-business-data"></a><span data-ttu-id="b0791-103">アーカイブされた Skype for Business データを検索するための SharePoint Server の構成</span><span class="sxs-lookup"><span data-stu-id="b0791-103">Configure SharePoint Server to search for archived Skype for Business data</span></span>
 
<span data-ttu-id="b0791-104">**の概要:**ビジネス サーバー 2015 2016 の Exchange Server や Exchange Server 2013 と Skype でアーカイブされたデータを検索するのには SharePoint サーバーを構成します。</span><span class="sxs-lookup"><span data-stu-id="b0791-104">**Summary:** Configure SharePoint Server to search for data archived by Exchange Server 2016 or Exchange Server 2013 and Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="b0791-105">ビジネス サーバー 2015 の Exchange Server 2016 または Skype ではなく、Exchange Server 2013 でインスタント メッセージング、Web 会議の議事録を保存するための大きな利点の 1 つは、同じ場所にデータを格納できる管理者を 1 つのツールを使用するにはExchange のアーカイブ ・ データとアーカイブ済みの Skype ビジネス サーバーのデータを検索します。</span><span class="sxs-lookup"><span data-stu-id="b0791-105">One of the major advantages to storing instant messaging and Web conferencing transcripts in Exchange Server 2016 or Exchange Server 2013 instead of Skype for Business Server 2015 is that storing data in the same location allows administrators to use a single tool to search for archived Exchange data and/or archived Skype for Business Server data.</span></span> <span data-ttu-id="b0791-106">(交換) するために同じデータが保存されているすべて、Exchange のアーカイブ ・ データを検索できるツールがビジネスのサーバーのデータのアーカイブされた Skype の検索もできます。</span><span class="sxs-lookup"><span data-stu-id="b0791-106">Because all the data is stored in the same place (Exchange) any tool that can search for archived Exchange data can also search for archived Skype for Business Server data.</span></span>
  
<span data-ttu-id="b0791-107">アーカイブされたデータを検索しやすい 1 つのツールは、Microsoft SharePoint Server 2013 です。</span><span class="sxs-lookup"><span data-stu-id="b0791-107">One tool that makes it easy to search for archived data is Microsoft SharePoint Server 2013.</span></span> <span data-ttu-id="b0791-108">Skype のビジネス サーバーのデータを検索する SharePoint を使用する場合は、Exchange が Skype のビジネス サーバーのアーカイブを構成するのに関連するすべての手順を完了してする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b0791-108">If you would like to use SharePoint to search for Skype for Business Server data, you must first complete all the steps involved in configuring Exchange archiving in Skype for Business Server.</span></span> <span data-ttu-id="b0791-109">Exchange Server と Skype のビジネス サーバーが正常に統合された後、し、SharePoint サーバー上で Exchange [Web サービスの管理 API](https://go.microsoft.com/fwlink/p/?LinkId=258305)をインストールしてください。</span><span class="sxs-lookup"><span data-stu-id="b0791-109">After Exchange Server and Skype for Business Server have been successfully integrated, you must then install the Exchange [Web Services Managed API](https://go.microsoft.com/fwlink/p/?LinkId=258305) on your SharePoint Server.</span></span> <span data-ttu-id="b0791-110">ダウンロードしたファイル (EWSManagedAPI.msi) は、SharePoint サーバーのどのフォルダーにでも保存できます。</span><span class="sxs-lookup"><span data-stu-id="b0791-110">The downloaded file (EWSManagedAPI.msi) can be saved to any folder on your SharePoint server.</span></span>
  
<span data-ttu-id="b0791-111">ファイルをダウンロードした後、SharePoint サーバー上で次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="b0791-111">After the file has been downloaded complete the following procedure on the SharePoint server:</span></span>
  
1. <span data-ttu-id="b0791-112">[**スタート**]、[**すべてのプログラム**]、[**アクセサリ**] の順にクリックし、[**コマンド プロンプト**] を右クリックし、[**管理者として実行**] をクリックして、コマンド ウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="b0791-112">Open a command window by clicking **Start**, clicking **All Programs**, clicking **Accessories**, right-clicking **Command Prompt**, and then clicking **Run as administrator**.</span></span>
    
2. <span data-ttu-id="b0791-113">[コマンド] ウィンドウで、EWSManagedAPI.msi ファイルが保存されているフォルダーに現在のディレクトリを変更するのには、cd コマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="b0791-113">In the command window, use the cd command to change the current directory to the folder where the file EWSManagedAPI.msi has been saved.</span></span> <span data-ttu-id="b0791-114">、C:\Downloads にファイルを保存した場合コマンド ウィンドウで次のコマンドを入力して Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="b0791-114">For example, if you have saved the file to C:\Downloads type the following command in the command window and then press Enter:</span></span>
    
   ```
   cd C:\Downloads
   ```

3. <span data-ttu-id="b0791-115">API をインストールするには、次のコマンドを入力し、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="b0791-115">To install the API, type the following command then press Enter:</span></span>
    
   ```
   msiexec /I EwsManagedApi.msi addlocal="ExchangeWebServicesApi_Feature,ExchangeWebServicesApi_Gac"
   ```

4. <span data-ttu-id="b0791-116">API をインストールすると、次のコマンドを入力し、Enter キーを押して、IIS をリセットします。</span><span class="sxs-lookup"><span data-stu-id="b0791-116">After the API has been installed, reset IIS by typing the following command and pressing Enter:</span></span>
    
   ```
   iisreset
   ```

<span data-ttu-id="b0791-117">Exchange Web サービスをインストールした後は、SharePoint Server と Exchange Server 間でサーバーからサーバーへの認証を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b0791-117">After Exchange Web Services has been installed you must then configure server-to-server authentication between SharePoint Server and Exchange Server.</span></span> <span data-ttu-id="b0791-118">これを行うには、まず SharePoint 管理シェルを開くし、次の一連のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="b0791-118">To do this, first open the SharePoint Management Shell and run the following set of commands:</span></span>
  
```
New-SPTrustedSecurityTokenIssuer -Name "Exchange" -MetadataEndPoint "https://autodiscover.litwareinc.com/autodiscover/metadata/json/1"
$service = Get-SPSecurityTokenServiceConfig
$service.HybridStsSelectionEnabled = $True
$service.AllowMetadataOverHttp = $False
$service.AllowOAuthOverHttp = $False
$service.Update()
```

> [!NOTE]
> <span data-ttu-id="b0791-119">自動検出サービスの URI を使用してください。</span><span class="sxs-lookup"><span data-stu-id="b0791-119">Be sure and use the URI for your autodiscover service.</span></span> <span data-ttu-id="b0791-120">サンプル URI を使用しないhttps://autodiscover.litwareinc.com/autodiscover/metadata/json/1。</span><span class="sxs-lookup"><span data-stu-id="b0791-120">Do not use the sample URI https://autodiscover.litwareinc.com/autodiscover/metadata/json/1.</span></span> 
  
<span data-ttu-id="b0791-121">トークンの発行元を作成して、トークン サービスを構成することが後、は、SharePoint サイトの URL の代わりにサンプルの URL を確認するこれらのコマンドを実行します。http://atl-sharepoint-001:</span><span class="sxs-lookup"><span data-stu-id="b0791-121">After you have created the token issuer and configured the token service, run these commands, making sure to substitute the URL of your SharePoint site for the sample URL http://atl-sharepoint-001:</span></span>
  
```
$exchange = Get-SPTrustedSecurityTokenIssuer "Exchange"
$app = Get-SPAppPrincipal -Site "https://atl-sharepoint-001" -NameIdentifier $exchange.NameID
$site = Get-SPSite  "https://atl-sharepoint-001"
Set-SPAppPrincipalPermission -AppPrincipal $app -Site $site.RootWeb -Scope "SiteSubscription" -Right "FullControl" -EnableAppOnlyPolicy
```

<span data-ttu-id="b0791-122">Exchange Server のサーバーからサーバーへの認証を構成するには、Exchange 管理シェルを開くし、(と仮定すると、Exchange は、ドライブ c: にインストールされているし、既定のフォルダーのパスを使用する) は、次のようなコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="b0791-122">To configure server-to-server authentication for Exchange Server, open the Exchange Management Shell and run a command similar to this (assuming that Exchange has been installed on drive C: and that it uses the default folder path):</span></span>
  
```
"C:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1 -AuthMetaDataUrl 'https://atl-sharepoint-001/_layouts/15/metadata/json/1' -ApplicationType SharePoint"
```

<span data-ttu-id="b0791-123">パートナー アプリケーションを構成した後、停止し、すべての Exchange メールボックスおよびクライアント アクセス サーバーのインターネット インフォメーション サービス (IIS) を再起動することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="b0791-123">After configuring the partner application it is recommended that you stop and restart Internet Information Services (IIS) on all your Exchange mailbox and client access servers.</span></span> <span data-ttu-id="b0791-124">コマンドを使用して、次のようなコンピューター atl-exchange-001 のサービスを再起動する、IIS を再起動することができます。</span><span class="sxs-lookup"><span data-stu-id="b0791-124">You can restart IIS by using a command similar to this, which restarts the service on the computer atl-exchange-001:</span></span>
  
```
iisreset atl-exchange-001
```

<span data-ttu-id="b0791-125">このコマンドは、Exchange 管理シェル内でまたは他の任意のコマンド ウィンドウから実行できます。</span><span class="sxs-lookup"><span data-stu-id="b0791-125">This command can be run from within the Exchange Management Shell or from any other command window.</span></span>
  
<span data-ttu-id="b0791-126">次に、Exchange 上での検出を実行する権限 (kenmyer など) で指定されたユーザーは、次のようなコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="b0791-126">Next, run a command similar to the following, which gives the specified user (in this example, kenmyer) the right to do discovery on Exchange:</span></span>
  
```
Add-RoleGroupMember "Discovery Management" -Member "kenmyer"
```

<span data-ttu-id="b0791-127">Exchange と SharePoint のサーバーからサーバーへの認証が確立された後、次に、SharePoint で、電子的証拠開示のサイトを作成します。</span><span class="sxs-lookup"><span data-stu-id="b0791-127">After server-to-server authentication has been established between Exchange and SharePoint, your next step is to create an eDiscovery site in SharePoint.</span></span> <span data-ttu-id="b0791-128">SharePoint 管理シェルから以下のようなコマンドを実行することによって行えます。</span><span class="sxs-lookup"><span data-stu-id="b0791-128">That can be done by running commands similar to these from the SharePoint Management Shell:</span></span>
  
```
$template = Get-SPWebTemplate | Where-Object {$_.Title -eq "eDiscovery Center"}
New-SPSite -Url "https://atl-sharepoint-001/sites/discovery" -OwnerAlias "kenmyer" -Template $Template -Name "Discovery Center"
```

> [!NOTE]
> <span data-ttu-id="b0791-129">"電子情報開示" とは、通常、訴訟において "証拠になり得ると合理的に判断できる" 項目の電子的アーカイブを参照するプロセスを表します。</span><span class="sxs-lookup"><span data-stu-id="b0791-129">"eDiscovery" is short for "electronic discovery," and typically refers to the process of looking through electronic archives for items that can be "reasonably calculated to lead to admissible evidence" in a court of law.</span></span> 
  
<span data-ttu-id="b0791-130">新しいサイトの準備ができたら、次に、SharePoint の結果としてソースを動作するように Exchange Server を構成します。</span><span class="sxs-lookup"><span data-stu-id="b0791-130">When the new site is ready, the next step is to configure Exchange Server to act as a result source for SharePoint.</span></span> <span data-ttu-id="b0791-131">SharePoint サーバーの全体管理ページから次の手順を完了しているを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="b0791-131">You can do that by completing the following procedure from the SharePoint Central Administration page:</span></span>
  
1. <span data-ttu-id="b0791-132">サーバーの全体管理ページで、[**サービス アプリケーションの管理**]、[**Search Service アプリケーション**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="b0791-132">On the Central Administration page click **Manage Service Applications** and then click **Search Service Application**.</span></span>
    
2. <span data-ttu-id="b0791-133">[Search Service アプリケーション: 検索管理] ページで、[**検索先**]、[**新しい結果ソース**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="b0791-133">On the Search Service Application: Search Administration page click **Result Sources** and then click **New Result Source**.</span></span>
    
3. <span data-ttu-id="b0791-134">[**新しい結果ソース**] ウィンドウで、[**名前**] ボックスに新しい検索先の名前 (たとえば、**Microsoft Exchange**) を入力します。</span><span class="sxs-lookup"><span data-stu-id="b0791-134">In the **New Result Source** pane enter a name for the new result source (for example, **Microsoft Exchange**) in the **Name** box.</span></span> <span data-ttu-id="b0791-135">**交換****プロトコル**では、結果のソースとして] を選択し、 **Exchange ソースの URL** ] ボックスに Exchange サーバーの web サービスのソースの URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="b0791-135">Select **Exchange** as the result source **Protocol**, and then enter the web services source URL for your Exchange server in the **Exchange Source URL** box.</span></span> <span data-ttu-id="b0791-136">ソース URL は次のような形式です。</span><span class="sxs-lookup"><span data-stu-id="b0791-136">The source URL should look similar to this:</span></span>
    
    https://atl-exchange-001.litwareinc.com/ews/exchange.asmx
    
4. <span data-ttu-id="b0791-137">[**自動検出を使用する**] がオンでないことを確認して、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b0791-137">Make sure that **Use Autodiscover** is not selected, and then click **OK**.</span></span>
    
<span data-ttu-id="b0791-138">最後に、新しい電子的証拠開示のケースと、新しい電子的証拠開示 (たとえば、SharePoint 検索サイトから次の手順を実行して設定を作成します。https://atl-sharepoint-001/sites/discovery):</span><span class="sxs-lookup"><span data-stu-id="b0791-138">Finally, create a new eDiscovery case and a new eDiscovery set by completing the following procedure from the SharePoint Discovery site (for example, https://atl-sharepoint-001/sites/discovery):</span></span>
  
1. <span data-ttu-id="b0791-139">[サイト コンテンツ] ページで、[**新しいケースを作成します**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b0791-139">On the Site Contents page click **Create a new case**.</span></span>
    
2. <span data-ttu-id="b0791-p110">[サイト コンテンツ: 新しい SharePoint サイト] ページで、[**タイトル**] ボックスにユーザーの電子メール エイリアス (たとえば、**kenmyer**) を入力し、同じその URL を [**Web サイトのアドレス**] ボックスに追加します。次のような URL になります。</span><span class="sxs-lookup"><span data-stu-id="b0791-p110">On the Site Contents: New SharePoint Site page, enter the user's email alias (for example, **kenmyer**) in the **Title** box, then add that same URL to the **Web Site Address** box. That will result in a URL similar to this:</span></span>
    
    https://atl-sharepoint-001/sites/eDiscovery/kenmyer
    
3. <span data-ttu-id="b0791-142">[**作成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b0791-142">Click **Create**.</span></span>
    
4. <span data-ttu-id="b0791-143">[電子情報開示セット] ページが表示されたら、[**識別と保存: 情報開示セット**] の下の [**新しいアイテム**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b0791-143">When the eDiscovery set page appears, click **new item** under **Identity and Preserve: Discovery Sets**.</span></span>
    
5. <span data-ttu-id="b0791-144">[新規: 情報開示セット] ページで、[**情報開示セット名**] ボックスにユーザーの電子メール エイリアスを入力します。</span><span class="sxs-lookup"><span data-stu-id="b0791-144">On the New: Discovery Set page, enter the user's email alias in the **Discovery Set Name** box.</span></span> <span data-ttu-id="b0791-145">入力**電子的証拠開示 Lync\* \*\* [**フィルター\*\* ] ボックスをクリック**追加&amp;ソースの管理**です。</span><span class="sxs-lookup"><span data-stu-id="b0791-145">Enter **eDiscovery Lync\*** in the **Filter** box and then click **Add &amp; Manage Sources**.</span></span>
    
6. <span data-ttu-id="b0791-146">追加&amp;ソースの管理] ページで、[**メールボックス]**の最初のテキスト ボックスにユーザーの電子メール エイリアスを入力します。</span><span class="sxs-lookup"><span data-stu-id="b0791-146">On the Add &amp; Manage Sources page, enter the user's email alias in the first textbox under **Mailboxes**.</span></span> <span data-ttu-id="b0791-147">テキスト ボックスの横にある [メールボックスの確認] アイコンをクリックして、SharePoint が指定のメールボックスに接続できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="b0791-147">Click the check mailbox icon located next to the textbook to verify that SharePoint can connect to the specified mailbox.</span></span>
    
7. <span data-ttu-id="b0791-148">[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b0791-148">Click **OK**.</span></span>
    
8. <span data-ttu-id="b0791-149">[電子情報開示セット] ページで、[**保存**] をクリックして新しい電子情報開示セットを保存します。</span><span class="sxs-lookup"><span data-stu-id="b0791-149">On the eDiscovery set page, click **Save** to save the new eDiscovery set.</span></span>
    
<span data-ttu-id="b0791-150">この時点で指定したメールボックス (kenmyer) を検索することや、場で有効にするが、他の SharePoint コンテンツまたは結果ソースの場合と同じ方法を保持しています。</span><span class="sxs-lookup"><span data-stu-id="b0791-150">At this point you can search the specified mailbox (kenmyer) and/or enable In-Place holds the same way you would for any other SharePoint content or result source.</span></span>
  

