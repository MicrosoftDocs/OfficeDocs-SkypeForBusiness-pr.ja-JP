---
title: Skype for Business Server 管理シェル
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 674b523b-c0b7-4ed6-9e67-afa6e8ac7e12
description: Skype for Business Server 管理シェルには、サーバー管理と管理のためのコマンドラインインターフェイスが用意されています。 これは Windows PowerShell で構築されており、Skype および従来の Lync server 製品に固有の一連の管理と管理のコマンドレットが含まれています。
ms.openlocfilehash: 294de750795985d50c6301a88f4b835f1cad78b7
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817556"
---
# <a name="skype-for-business-server-management-shell"></a><span data-ttu-id="3a8bb-104">Skype for Business Server 管理シェル</span><span class="sxs-lookup"><span data-stu-id="3a8bb-104">Skype for Business Server Management Shell</span></span>
 
<span data-ttu-id="3a8bb-105">Skype for Business Server 管理シェルには、サーバー管理と管理のためのコマンドラインインターフェイスが用意されています。</span><span class="sxs-lookup"><span data-stu-id="3a8bb-105">The Skype for Business Server Management Shell provides the command line interface for server administration and management.</span></span> <span data-ttu-id="3a8bb-106">これは Windows PowerShell で構築されており、Skype および従来の Lync server 製品に固有の一連の管理と管理のコマンドレットが含まれています。</span><span class="sxs-lookup"><span data-stu-id="3a8bb-106">It is built on Windows PowerShell and includes a comprehensive set of management and administration cmdlets that are specific to Skype and legacy Lync server products.</span></span>
  
<span data-ttu-id="3a8bb-107">Windows PowerShell を使用すると、コマンドラインから Microsoft アプリケーションを管理できます。</span><span class="sxs-lookup"><span data-stu-id="3a8bb-107">Windows PowerShell allows you to manage Microsoft applications from the command line.</span></span> <span data-ttu-id="3a8bb-108">コマンド ライン環境、製品固有のコマンド、完全なスクリプト言語が用意されています。</span><span class="sxs-lookup"><span data-stu-id="3a8bb-108">It includes a command-line environment, product-specific commands, and a full scripting language.</span></span> <span data-ttu-id="3a8bb-109">Windows PowerShell は、最初に2006の Windows オペレーティングシステムのダウンロード可能なリリースとして導入されましたが、Microsoft Exchange Server 2007 の管理のためのコマンドラインインターフェイスとして採用されています。</span><span class="sxs-lookup"><span data-stu-id="3a8bb-109">Windows PowerShell was first introduced as a downloadable release for the Windows operating system late in 2006, and was incorporated as the command-line interface for manageability of Microsoft Exchange Server 2007.</span></span> <span data-ttu-id="3a8bb-110">Lync Server 2010 で始まる Lync および Skype サーバーを含むほとんどの Microsoft サーバー製品に組み込まれています。</span><span class="sxs-lookup"><span data-stu-id="3a8bb-110">It has been incorporated into most of the Microsoft Server products, including Lync and Skype servers beginning with Lync Server 2010.</span></span> <span data-ttu-id="3a8bb-111">Skype for Business Server 管理シェルでは、700の Lync と Skype 固有のコマンドレットを利用できます。</span><span class="sxs-lookup"><span data-stu-id="3a8bb-111">There are over 700 Lync and Skype specific cmdlets available in the Skype for Business Server Management Shell.</span></span>
  
> [!NOTE]
> <span data-ttu-id="3a8bb-112">Skype for Business コマンドレットリファレンスは docs.microsoft.com に移動されました。</span><span class="sxs-lookup"><span data-stu-id="3a8bb-112">Skype for Business cmdlet reference has moved to docs.microsoft.com.</span></span> <span data-ttu-id="3a8bb-113">以下のリンクをクリックすると、新しい docs.microsoft.com ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="3a8bb-113">Clicking on the links below will take you to the new docs.microsoft.com page.</span></span> <span data-ttu-id="3a8bb-114">これでコンテンツが公開され、GitHub を通じてコミュニティの投稿に使用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="3a8bb-114">The content is now open sourced and available for community contributions through GitHub.</span></span> <span data-ttu-id="3a8bb-115">投稿に興味をお持ちですか?</span><span class="sxs-lookup"><span data-stu-id="3a8bb-115">Interested in contributing?</span></span> <span data-ttu-id="3a8bb-116">ここでは、リポジトリ内の README を確認します。[https://github.com/MicrosoftDocs/office-docs-powershell](https://github.com/MicrosoftDocs/office-docs-powershell)</span><span class="sxs-lookup"><span data-stu-id="3a8bb-116">Check out the README in the repo here: [https://github.com/MicrosoftDocs/office-docs-powershell](https://github.com/MicrosoftDocs/office-docs-powershell)</span></span>
  
<span data-ttu-id="3a8bb-117">Skype for Business Server には、管理者が skype for Business Server Management Shell を使って Skype for Business Server を管理できるようにするための700コマンドレットが付属しています。</span><span class="sxs-lookup"><span data-stu-id="3a8bb-117">Skype for Business Server ships with more than 700 cmdlets that enable administrators to manage Skype for Business Server using the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="3a8bb-118">以下のようなコマンドを入力すると、コマンドレットのヘルプを、コマンド ラインから直接取得することができます。</span><span class="sxs-lookup"><span data-stu-id="3a8bb-118">You can retrieve help for a cmdlet directly from the command line by typing a command similar to the following:</span></span>
  
```PowerShell
Get-Help New-CsVoicePolicy -Full
```

<span data-ttu-id="3a8bb-119">前述のコマンドは、**New-CsVoicePolicy** コマンドレットで使用できるすべてのヘルプを取得します。</span><span class="sxs-lookup"><span data-stu-id="3a8bb-119">The preceding command retrieves the complete help available for the **New-CsVoicePolicy** cmdlet.</span></span> <span data-ttu-id="3a8bb-120">別のコマンドレットのヘルプを表示するには、**New-CsVoicePolicy** を、ヘルプを取得したいコマンドレットの名前に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="3a8bb-120">To view help for a different cmdlet, substitute **New-CsVoicePolicy** with the name of the cmdlet for which you want to retrieve help.</span></span>
  
<span data-ttu-id="3a8bb-121">Skype for Business Server の管理に使用できるすべてのコマンドレットの一覧を取得するには、シェル コマンド プロンプトで以下を入力します。</span><span class="sxs-lookup"><span data-stu-id="3a8bb-121">To retrieve a full list of cmdlets available for managing Skype for Business Server, type the following at the shell command prompt:</span></span> 
  
```PowerShell
Get-Command * -Module SkypeforBusiness -CommandType cmdlet
```



<span data-ttu-id="3a8bb-122">Skype for Business Server での Windows PowerShell について知っておくべきこと:</span><span class="sxs-lookup"><span data-stu-id="3a8bb-122">Things to know about Windows PowerShell in Skype for Business Server:</span></span>
  
- <span data-ttu-id="3a8bb-123">Skype for Business Server コマンドレットを実行するには、Skype for Business Server 管理シェルを開きます。</span><span class="sxs-lookup"><span data-stu-id="3a8bb-123">To run the Skype for Business Server cmdlets, open the Skype for Business Server Management Shell.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="3a8bb-124">Skype for Business Server 管理シェルではなく、Windows PowerShell ウィンドウを開いた場合、既定では、Skype コマンドレットを実行することはできません。</span><span class="sxs-lookup"><span data-stu-id="3a8bb-124">If you open a Windows PowerShell window rather than the Skype for Business Server Management Shell, by default you may not be able to run the Skype cmdlets.</span></span> <span data-ttu-id="3a8bb-125">Windows PowerShell 内から Skype for Business Server コマンドレットを実行するには、まず、Windows PowerShell コマンドプロンプトで次のように入力します。 >`Import-Module SkypeforBusiness`</span><span class="sxs-lookup"><span data-stu-id="3a8bb-125">To run Skype for Business Server cmdlets from within Windows PowerShell, first type the following at the Windows PowerShell command prompt: >  `Import-Module SkypeforBusiness`</span></span>
  
- <span data-ttu-id="3a8bb-126">Skype for business Server 管理シェルは、すべての Skype for Business Server Enterprise Edition のフロントエンドサーバーまたは Standard Edition サーバーに自動的にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="3a8bb-126">Skype for Business Server Management Shell is automatically installed on every Skype for Business Server Enterprise Edition Front End Server or Standard Edition server.</span></span>
    
- <span data-ttu-id="3a8bb-127">Skype for Business Server 管理シェルのヘルプコンテンツは、 [update-ヘルプ](https://technet.microsoft.com/en-us/library/hh849720.aspx)コマンドレットを実行して更新できます。</span><span class="sxs-lookup"><span data-stu-id="3a8bb-127">You can update the Skype for Business Server Management Shell help content by running the [Update-Help](https://technet.microsoft.com/en-us/library/hh849720.aspx) cmdlet.</span></span> <span data-ttu-id="3a8bb-128">更新プログラムのヘルプコマンドレットは、お使いのコンピューターにインストールされているすべてのモジュールで利用できる最新のヘルプファイルをダウンロードしてインストールします。これには、Skype for Business コマンドレットの更新が含まれます。</span><span class="sxs-lookup"><span data-stu-id="3a8bb-128">The Update-Help cmdlet downloads and installs the newest help files available for all of the modules installed on your computer, including updates to Skype for Business cmdlets.</span></span>
    
    <span data-ttu-id="3a8bb-129">既定では、[**更新] ヘルプ**コマンドレットによって、Skype For business Server にインストールされているすべてのモジュールが更新されます。</span><span class="sxs-lookup"><span data-stu-id="3a8bb-129">By default, the **Update-Help** cmdlet will update all the modules installed on your Skype for Business Server.</span></span> <span data-ttu-id="3a8bb-130">特定のモジュールのみ更新する場合は、_Module_ パラメーターを使用してこのコマンドレットのスコープを制限できます。</span><span class="sxs-lookup"><span data-stu-id="3a8bb-130">If you want to update only certain modules, you can use the _Module_ parameter to limit the scope of the cmdlet.</span></span> <span data-ttu-id="3a8bb-131">次の例では、Skype for Business モジュールのみが更新されます。</span><span class="sxs-lookup"><span data-stu-id="3a8bb-131">The following example updates only the Skype for Business module.</span></span>
    
  ```PowerShell
  Update-Help -Module SkypeforBusiness
  ```

    <span data-ttu-id="3a8bb-132">インターネットに接続されていないサーバーでヘルプを更新する必要がある場合は、[ヘルプの[保存](https://technet.microsoft.com/en-us/library/hh849724.aspx)] コマンドレットを使用して最新バージョンのヘルプを取得し、指定した場所に保存します。</span><span class="sxs-lookup"><span data-stu-id="3a8bb-132">If you need to update the Help on servers that are not connected to the internet, you can use the [Save-Help](https://technet.microsoft.com/en-us/library/hh849724.aspx) cmdlet to get the latest version of the help and save it to a location you specify.</span></span> <span data-ttu-id="3a8bb-133">次に、インターネットに接続されていないサーバーの _-SourcePath_パラメーターを指定して**Update-ヘルプ**コマンドレットを使用して、選択した場所から更新されたヘルプを取得できます。</span><span class="sxs-lookup"><span data-stu-id="3a8bb-133">You can then use the **Update-Help** cmdlet with the _-SourcePath_ parameter on servers not connected to the internet to get the updated help from the location you selected.</span></span> <span data-ttu-id="3a8bb-134">次の例は、ヘルプファイルをネットワークファイル共有に保存して、Skype for Business モジュールのヘルプをファイル共有から更新する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="3a8bb-134">The following example shows how to save the help files to a network file share, and then update the help for the Skype for Business module from the file share.</span></span>
    
  ```PowerShell
  // Save the help files
   Save-Help -DestinationPath \\UpdateShare\HelpDownload
  // Run Update-Help against the local help files
   Update-Help -Module SkypeforBusiness -SourcePath \\UpdateShare\HelpDownload
  ```

    <span data-ttu-id="3a8bb-135">詳細については、「[更新可能なヘルプ](https://technet.microsoft.com/library/hh847735.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3a8bb-135">For more detailed information, see [About Updatable Help](https://technet.microsoft.com/library/hh847735.aspx).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="3a8bb-136">PowerShell をリモートで使用している場合は、ファイアウォール経由の通信を許可する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3a8bb-136">If you are using PowerShell remotely you may need to allow communication through a firewall.</span></span> <span data-ttu-id="3a8bb-137">PowerShell のリモート処理で使用されるポートの詳細については、「 [Powershell リモート処理で使用](https://blogs.technet.microsoft.com/christwe/2012/06/20/what-port-does-powershell-remoting-use/)されるポートについて」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3a8bb-137">To learn more about the ports PowerShell remoting uses, see [What Port Does PowerShell Remoting Use?](https://blogs.technet.microsoft.com/christwe/2012/06/20/what-port-does-powershell-remoting-use/).</span></span>
    

