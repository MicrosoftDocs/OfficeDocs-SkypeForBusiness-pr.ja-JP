---
title: アーカイブされた Skype for Business データを検索する SharePoint Server を構成する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 17f49365-8778-4962-a41b-f96faf6902f1
description: '概要: SharePoint Server を構成して、Exchange Server Skype for Business Server によってアーカイブされたデータを検索します。'
ms.openlocfilehash: 406e0a713c65bc147ce6eb492f251a25ea2a3afc
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49833947"
---
# <a name="configure-sharepoint-server-to-search-for-archived-skype-for-business-data"></a><span data-ttu-id="3803d-103">アーカイブされた Skype for Business データを検索する SharePoint Server を構成する</span><span class="sxs-lookup"><span data-stu-id="3803d-103">Configure SharePoint Server to search for archived Skype for Business data</span></span>
 
<span data-ttu-id="3803d-104">**概要:** Exchange Server 2016 または Exchange Server 2013 および Skype for Business Server によってアーカイブされたデータを検索する SharePoint Server を構成します。</span><span class="sxs-lookup"><span data-stu-id="3803d-104">**Summary:** Configure SharePoint Server to search for data archived by Exchange Server 2016 or Exchange Server 2013 and Skype for Business Server.</span></span>
  
<span data-ttu-id="3803d-105">Skype for Business Server ではなく Exchange Server にインスタント メッセージングと Web 会議のトランスクリプトを保存する主な利点の 1 つは、管理者が 1 つのツールを使用してアーカイブされた Exchange データやアーカイブされた Skype for Business Server データを検索できるという方法です。</span><span class="sxs-lookup"><span data-stu-id="3803d-105">One of the major advantages to storing instant messaging and Web conferencing transcripts in Exchange Server instead of Skype for Business Server is that storing data in the same location allows administrators to use a single tool to search for archived Exchange data and/or archived Skype for Business Server data.</span></span> <span data-ttu-id="3803d-106">すべてのデータは同じ場所 (Exchange) に格納されます。アーカイブされた Exchange データを検索できるツールは、アーカイブされた Skype for Business Server データも検索できます。</span><span class="sxs-lookup"><span data-stu-id="3803d-106">Because all the data is stored in the same place (Exchange) any tool that can search for archived Exchange data can also search for archived Skype for Business Server data.</span></span>
  
<span data-ttu-id="3803d-107">アーカイブされたデータを簡単に検索できるツールの 1 つは、Microsoft SharePoint Server 2013 です。</span><span class="sxs-lookup"><span data-stu-id="3803d-107">One tool that makes it easy to search for archived data is Microsoft SharePoint Server 2013.</span></span> <span data-ttu-id="3803d-108">SharePoint を使用して Skype for Business Server データを検索する場合は、最初に Skype for Business Server での Exchange アーカイブの構成に関連する手順を完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3803d-108">If you would like to use SharePoint to search for Skype for Business Server data, you must first complete all the steps involved in configuring Exchange archiving in Skype for Business Server.</span></span> <span data-ttu-id="3803d-109">Exchange Exchange Server Skype for Business Server が正常に統合された後、Exchange Web [サービスマネージ API](https://go.microsoft.com/fwlink/p/?LinkId=258305) を SharePoint Server にインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="3803d-109">After Exchange Server and Skype for Business Server have been successfully integrated, you must then install the Exchange [Web Services Managed API](https://go.microsoft.com/fwlink/p/?LinkId=258305) on your SharePoint Server.</span></span> <span data-ttu-id="3803d-110">ダウンロードしたファイル (EWSManagedAPI.msi) は、SharePoint サーバー上の任意のフォルダーに保存できます。</span><span class="sxs-lookup"><span data-stu-id="3803d-110">The downloaded file (EWSManagedAPI.msi) can be saved to any folder on your SharePoint server.</span></span>
  
<span data-ttu-id="3803d-111">ファイルをダウンロードした後、SharePoint サーバー上で次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="3803d-111">After the file has been downloaded complete the following procedure on the SharePoint server:</span></span>
  
1. <span data-ttu-id="3803d-112">[**スタート**]、[**すべてのプログラム**]、[**アクセサリ**] の順にクリックし、[**コマンド プロンプト**] を右クリックし、[**管理者として実行**] をクリックして、コマンド ウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="3803d-112">Open a command window by clicking **Start**, clicking **All Programs**, clicking **Accessories**, right-clicking **Command Prompt**, and then clicking **Run as administrator**.</span></span>
    
2. <span data-ttu-id="3803d-113">コマンド ウィンドウで、cd コマンドを使用して、EWSManagedAPI.msi ファイルが保存されているフォルダーに現在のディレクトリを変更します。</span><span class="sxs-lookup"><span data-stu-id="3803d-113">In the command window, use the cd command to change the current directory to the folder where the file EWSManagedAPI.msi has been saved.</span></span> <span data-ttu-id="3803d-114">たとえば、ファイルを C:\Downloads に保存した場合、コマンド ウィンドウに次のコマンドを入力し、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="3803d-114">For example, if you have saved the file to C:\Downloads type the following command in the command window and then press Enter:</span></span>
    
   ```console
   cd C:\Downloads
   ```

3. <span data-ttu-id="3803d-115">API をインストールするには、次のコマンドを入力し、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="3803d-115">To install the API, type the following command then press Enter:</span></span>
    
   ```console
   msiexec /I EwsManagedApi.msi addlocal="ExchangeWebServicesApi_Feature,ExchangeWebServicesApi_Gac"
   ```

4. <span data-ttu-id="3803d-116">API がインストールされた後、次のコマンドを入力して Enter キーを押して IIS をリセットします。</span><span class="sxs-lookup"><span data-stu-id="3803d-116">After the API has been installed, reset IIS by typing the following command and pressing Enter:</span></span>
    
   ```console
   iisreset
   ```

<span data-ttu-id="3803d-117">Exchange Web サービスをインストールした後、SharePoint Server とサーバー間のサーバー間認証を構成Exchange Server。</span><span class="sxs-lookup"><span data-stu-id="3803d-117">After Exchange Web Services has been installed you must then configure server-to-server authentication between SharePoint Server and Exchange Server.</span></span> <span data-ttu-id="3803d-118">これを行うには、まず SharePoint 管理シェルを開き、次の一連のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="3803d-118">To do this, first open the SharePoint Management Shell and run the following set of commands:</span></span>
  
```powershell
New-SPTrustedSecurityTokenIssuer -Name "Exchange" -MetadataEndPoint "https://autodiscover.litwareinc.com/autodiscover/metadata/json/1"
$service = Get-SPSecurityTokenServiceConfig
$service.HybridStsSelectionEnabled = $True
$service.AllowMetadataOverHttp = $False
$service.AllowOAuthOverHttp = $False
$service.Update()
```

> [!NOTE]
> <span data-ttu-id="3803d-119">自動検出サービスの URI を使用してください。</span><span class="sxs-lookup"><span data-stu-id="3803d-119">Be sure and use the URI for your autodiscover service.</span></span> <span data-ttu-id="3803d-120">サンプル URI は使用しない https://autodiscover.litwareinc.com/autodiscover/metadata/json/1 。</span><span class="sxs-lookup"><span data-stu-id="3803d-120">Do not use the sample URI https://autodiscover.litwareinc.com/autodiscover/metadata/json/1.</span></span> 
  
<span data-ttu-id="3803d-121">トークン発行者を作成し、トークン サービスを構成したら、次のコマンドを実行して、SharePoint サイトの URL をサンプル URL に置き換える必要があります。 http://atl-sharepoint-001:</span><span class="sxs-lookup"><span data-stu-id="3803d-121">After you have created the token issuer and configured the token service, run these commands, making sure to substitute the URL of your SharePoint site for the sample URL http://atl-sharepoint-001:</span></span>
  
```powershell
$exchange = Get-SPTrustedSecurityTokenIssuer "Exchange"
$app = Get-SPAppPrincipal -Site "https://atl-sharepoint-001" -NameIdentifier $exchange.NameID
$site = Get-SPSite  "https://atl-sharepoint-001"
Set-SPAppPrincipalPermission -AppPrincipal $app -Site $site.RootWeb -Scope "SiteSubscription" -Right "FullControl" -EnableAppOnlyPolicy
```

<span data-ttu-id="3803d-122">Exchange Server のサーバー間認証を構成するには、Exchange 管理シェルを開き、次のようなコマンドを実行します (Exchange が C ドライブにインストールされ、既定のフォルダー パスが使用されている場合)。</span><span class="sxs-lookup"><span data-stu-id="3803d-122">To configure server-to-server authentication for Exchange Server, open the Exchange Management Shell and run a command similar to this (assuming that Exchange has been installed on drive C: and that it uses the default folder path):</span></span>
  
```powershell
"C:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1 -AuthMetaDataUrl 'https://atl-sharepoint-001/_layouts/15/metadata/json/1' -ApplicationType SharePoint"
```

<span data-ttu-id="3803d-123">パートナー アプリケーションを構成した後、すべての Exchange メールボックスサーバーとクライアント アクセス サーバーでインターネット インフォメーション サービス (IIS) を停止して再起動してください。</span><span class="sxs-lookup"><span data-stu-id="3803d-123">After configuring the partner application it is recommended that you stop and restart Internet Information Services (IIS) on all your Exchange mailbox and client access servers.</span></span> <span data-ttu-id="3803d-124">次のようなコマンドを使用して IIS を再起動できます。これにより、コンピューター atl-exchange-001 上のサービスが再起動されます。</span><span class="sxs-lookup"><span data-stu-id="3803d-124">You can restart IIS by using a command similar to this, which restarts the service on the computer atl-exchange-001:</span></span>
  
```powershell
iisreset atl-exchange-001
```

<span data-ttu-id="3803d-125">このコマンドは、Exchange 管理シェル 内または他のコマンド ウィンドウから実行できます。</span><span class="sxs-lookup"><span data-stu-id="3803d-125">This command can be run from within the Exchange Management Shell or from any other command window.</span></span>
  
<span data-ttu-id="3803d-126">次に、次のようなコマンドを実行します。これにより、指定したユーザー (この例では kenmyer) が Exchange で検出を行う権限を与えます。</span><span class="sxs-lookup"><span data-stu-id="3803d-126">Next, run a command similar to the following, which gives the specified user (in this example, kenmyer) the right to do discovery on Exchange:</span></span>
  
```powershell
Add-RoleGroupMember "Discovery Management" -Member "kenmyer"
```

<span data-ttu-id="3803d-127">Exchange と SharePoint の間でサーバー間認証が確立された後、次の手順は SharePoint で電子情報開示サイトを作成することです。</span><span class="sxs-lookup"><span data-stu-id="3803d-127">After server-to-server authentication has been established between Exchange and SharePoint, your next step is to create an eDiscovery site in SharePoint.</span></span> <span data-ttu-id="3803d-128">これは、SharePoint 管理シェルから次のようなコマンドを実行することで実行できます。</span><span class="sxs-lookup"><span data-stu-id="3803d-128">That can be done by running commands similar to these from the SharePoint Management Shell:</span></span>
  
```powershell
$template = Get-SPWebTemplate | Where-Object {$_.Title -eq "eDiscovery Center"}
New-SPSite -Url "https://atl-sharepoint-001/sites/discovery" -OwnerAlias "kenmyer" -Template $Template -Name "Discovery Center"
```

> [!NOTE]
> <span data-ttu-id="3803d-129">"電子情報開示" とは、通常、訴訟において "証拠になり得ると合理的に判断できる" 項目の電子的アーカイブを参照するプロセスを表します。</span><span class="sxs-lookup"><span data-stu-id="3803d-129">"eDiscovery" is short for "electronic discovery," and typically refers to the process of looking through electronic archives for items that can be "reasonably calculated to lead to admissible evidence" in a court of law.</span></span> 
  
<span data-ttu-id="3803d-130">新しいサイトの準備ができたら、次の手順では、SharePoint のExchange Serverソースとして機能するサイトを構成します。</span><span class="sxs-lookup"><span data-stu-id="3803d-130">When the new site is ready, the next step is to configure Exchange Server to act as a result source for SharePoint.</span></span> <span data-ttu-id="3803d-131">これを行うには、[SharePoint サーバーの全体管理] ページから次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="3803d-131">You can do that by completing the following procedure from the SharePoint Central Administration page:</span></span>
  
1. <span data-ttu-id="3803d-132">サーバーの全体管理ページで、[**サービス アプリケーションの管理**]、[**Search Service アプリケーション**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="3803d-132">On the Central Administration page click **Manage Service Applications** and then click **Search Service Application**.</span></span>
    
2. <span data-ttu-id="3803d-133">[Search Service アプリケーション: 検索管理] ページで、[**検索先**]、[**新しい結果ソース**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="3803d-133">On the Search Service Application: Search Administration page click **Result Sources** and then click **New Result Source**.</span></span>
    
3. <span data-ttu-id="3803d-134">[**新しい結果ソース**] ウィンドウで、[**名前**] ボックスに新しい検索先の名前 (たとえば、**Microsoft Exchange**) を入力します。</span><span class="sxs-lookup"><span data-stu-id="3803d-134">In the **New Result Source** pane enter a name for the new result source (for example, **Microsoft Exchange**) in the **Name** box.</span></span> <span data-ttu-id="3803d-135">検索 **先プロトコルとして [Exchange]** **を選択し**、[Exchange ソース URL] ボックスに Exchange サーバーの Web サービス ソース **URL を入力** します。</span><span class="sxs-lookup"><span data-stu-id="3803d-135">Select **Exchange** as the result source **Protocol**, and then enter the web services source URL for your Exchange server in the **Exchange Source URL** box.</span></span> <span data-ttu-id="3803d-136">ソース URL は次のような形式です。</span><span class="sxs-lookup"><span data-stu-id="3803d-136">The source URL should look similar to this:</span></span>
    
    https://atl-exchange-001.litwareinc.com/ews/exchange.asmx
    
4. <span data-ttu-id="3803d-137">[**自動検出を使用する**] がオンでないことを確認して、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3803d-137">Make sure that **Use Autodiscover** is not selected, and then click **OK**.</span></span>
    
<span data-ttu-id="3803d-138">最後に、SharePoint 探索サイトから次の手順を実行して、新しい電子情報開示ケースと新しい電子情報開示セットを作成します (例: https://atl-sharepoint-001/sites/discovery):</span><span class="sxs-lookup"><span data-stu-id="3803d-138">Finally, create a new eDiscovery case and a new eDiscovery set by completing the following procedure from the SharePoint Discovery site (for example, https://atl-sharepoint-001/sites/discovery):</span></span>
  
1. <span data-ttu-id="3803d-139">[サイト コンテンツ] ページで、[**新しいケースを作成します**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3803d-139">On the Site Contents page click **Create a new case**.</span></span>
    
2. <span data-ttu-id="3803d-p110">[サイト コンテンツ: 新しい SharePoint サイト] ページで、[**タイトル**] ボックスにユーザーの電子メール エイリアス (たとえば、**kenmyer**) を入力し、同じその URL を [**Web サイトのアドレス**] に追加します。次のような URL になります。</span><span class="sxs-lookup"><span data-stu-id="3803d-p110">On the Site Contents: New SharePoint Site page, enter the user's email alias (for example, **kenmyer**) in the **Title** box, then add that same URL to the **Web Site Address** box. That will result in a URL similar to this:</span></span>
    
    https://atl-sharepoint-001/sites/eDiscovery/kenmyer
    
3. <span data-ttu-id="3803d-142">[**作成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3803d-142">Click **Create**.</span></span>
    
4. <span data-ttu-id="3803d-143">[電子情報開示セット] ページが表示されたら、[**識別と保存: 情報開示セット**] の下の [**新しいアイテム**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3803d-143">When the eDiscovery set page appears, click **new item** under **Identity and Preserve: Discovery Sets**.</span></span>
    
5. <span data-ttu-id="3803d-144">[新規: 情報開示セット] ページで、[**情報開示セット名**] ボックスにユーザーの電子メール エイリアスを入力します。</span><span class="sxs-lookup"><span data-stu-id="3803d-144">On the New: Discovery Set page, enter the user's email alias in the **Discovery Set Name** box.</span></span> <span data-ttu-id="3803d-145">Enter **eDiscovery \\ Lync** _ in the _ *Filter*\* box and then click Add **Manage &amp; Sources**.</span><span class="sxs-lookup"><span data-stu-id="3803d-145">Enter **eDiscovery Lync\\** _ in the _ *Filter*\* box and then click **Add &amp; Manage Sources**.</span></span>
    
6. <span data-ttu-id="3803d-146">[ソースの管理の追加] ページで、[メールボックス] の下の最初のテキスト ボックスにユーザーの電子メール エイリアス &amp; **を入力します**。</span><span class="sxs-lookup"><span data-stu-id="3803d-146">On the Add &amp; Manage Sources page, enter the user's email alias in the first textbox under **Mailboxes**.</span></span> <span data-ttu-id="3803d-147">テキスト ボックスの横にある [メールボックスの確認] アイコンをクリックして、SharePoint が指定のメールボックスに接続できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="3803d-147">Click the check mailbox icon located next to the textbook to verify that SharePoint can connect to the specified mailbox.</span></span>
    
7. <span data-ttu-id="3803d-148">[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3803d-148">Click **OK**.</span></span>
    
8. <span data-ttu-id="3803d-149">[電子情報開示セット] ページで、[**保存**] をクリックして新しい電子情報開示セットを保存します。</span><span class="sxs-lookup"><span data-stu-id="3803d-149">On the eDiscovery set page, click **Save** to save the new eDiscovery set.</span></span>
    
<span data-ttu-id="3803d-150">この時点で、指定したメールボックス (kenmyer) を検索したり、他の SharePoint コンテンツまたは検索ソースと同じ方法で In-Place の保持を有効にできます。</span><span class="sxs-lookup"><span data-stu-id="3803d-150">At this point you can search the specified mailbox (kenmyer) and/or enable In-Place holds the same way you would for any other SharePoint content or result source.</span></span>
  

