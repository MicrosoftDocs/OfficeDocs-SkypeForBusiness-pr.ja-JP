---
title: Skype for Business Server 管理シェル
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 674b523b-c0b7-4ed6-9e67-afa6e8ac7e12
description: Skype for Business Server 管理シェルは、サーバーの管理と管理のためのコマンド ライン インターフェイスを提供します。 このコマンドレットは、Windows PowerShell上に構築され、Skype および従来の Lync サーバー製品に固有の管理および管理コマンドレットの包括的なセットが含まれています。
ms.openlocfilehash: 0653faa542bc9bc579bd7617e40d3efed030569f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816537"
---
# <a name="skype-for-business-server-management-shell"></a><span data-ttu-id="bbb49-104">Skype for Business Server 管理シェル</span><span class="sxs-lookup"><span data-stu-id="bbb49-104">Skype for Business Server Management Shell</span></span>
 
<span data-ttu-id="bbb49-105">Skype for Business Server 管理シェルは、サーバーの管理と管理のためのコマンド ライン インターフェイスを提供します。</span><span class="sxs-lookup"><span data-stu-id="bbb49-105">The Skype for Business Server Management Shell provides the command line interface for server administration and management.</span></span> <span data-ttu-id="bbb49-106">このコマンドレットは、Windows PowerShell上に構築され、Skype および従来の Lync サーバー製品に固有の管理および管理コマンドレットの包括的なセットが含まれています。</span><span class="sxs-lookup"><span data-stu-id="bbb49-106">It is built on Windows PowerShell and includes a comprehensive set of management and administration cmdlets that are specific to Skype and legacy Lync server products.</span></span>
  
<span data-ttu-id="bbb49-107">Windows PowerShellコマンド ラインから Microsoft アプリケーションを管理できます。</span><span class="sxs-lookup"><span data-stu-id="bbb49-107">Windows PowerShell allows you to manage Microsoft applications from the command line.</span></span> <span data-ttu-id="bbb49-108">Windows PowerShell にはコマンドライン環境、製品固有のコマンド、およびすべてのスクリプト言語が含まれます。</span><span class="sxs-lookup"><span data-stu-id="bbb49-108">It includes a command-line environment, product-specific commands, and a full scripting language.</span></span> <span data-ttu-id="bbb49-109">Windows PowerShellは、2006 年後半に Windows オペレーティング システムのダウンロード可能なリリースとして初めて導入され、Microsoft Exchange Server 2007 の管理性を確保するためのコマンド ライン インターフェイスとして組み込まれたものになります。</span><span class="sxs-lookup"><span data-stu-id="bbb49-109">Windows PowerShell was first introduced as a downloadable release for the Windows operating system late in 2006, and was incorporated as the command-line interface for manageability of Microsoft Exchange Server 2007.</span></span> <span data-ttu-id="bbb49-110">これは、Lync Server 2010 で始まる Lync サーバーや Skype サーバーを含む、ほとんどの Microsoft Server 製品に組み込まれています。</span><span class="sxs-lookup"><span data-stu-id="bbb49-110">It has been incorporated into most of the Microsoft Server products, including Lync and Skype servers beginning with Lync Server 2010.</span></span> <span data-ttu-id="bbb49-111">Skype for Business Server 管理シェルには、700 を超える Lync および Skype 固有のコマンドレットを使用できます。</span><span class="sxs-lookup"><span data-stu-id="bbb49-111">There are over 700 Lync and Skype specific cmdlets available in the Skype for Business Server Management Shell.</span></span>
  
> [!NOTE]
> <span data-ttu-id="bbb49-112">Skype for Business コマンドレット リファレンスは、docs.microsoft.com。</span><span class="sxs-lookup"><span data-stu-id="bbb49-112">Skype for Business cmdlet reference has moved to docs.microsoft.com.</span></span> <span data-ttu-id="bbb49-113">以下のリンクをクリックすると、新しいページdocs.microsoft.comされます。</span><span class="sxs-lookup"><span data-stu-id="bbb49-113">Clicking on the links below will take you to the new docs.microsoft.com page.</span></span> <span data-ttu-id="bbb49-114">コンテンツはオープン ソースとして公開され、GitHub を通じてコミュニティへの投稿に利用できます。</span><span class="sxs-lookup"><span data-stu-id="bbb49-114">The content is now open sourced and available for community contributions through GitHub.</span></span> <span data-ttu-id="bbb49-115">関心がある場合</span><span class="sxs-lookup"><span data-stu-id="bbb49-115">Interested in contributing?</span></span> <span data-ttu-id="bbb49-116">以下のレポで README を確認してください。 [https://github.com/MicrosoftDocs/office-docs-powershell](https://github.com/MicrosoftDocs/office-docs-powershell)</span><span class="sxs-lookup"><span data-stu-id="bbb49-116">Check out the README in the repo here: [https://github.com/MicrosoftDocs/office-docs-powershell](https://github.com/MicrosoftDocs/office-docs-powershell)</span></span>
  
<span data-ttu-id="bbb49-117">Skype for Business Server には、管理者が Skype for Business Server 管理シェルを使用して Skype for Business Server を管理できる 700 を超えるコマンドレットが組み込されています。</span><span class="sxs-lookup"><span data-stu-id="bbb49-117">Skype for Business Server ships with more than 700 cmdlets that enable administrators to manage Skype for Business Server using the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="bbb49-118">次のようなコマンドを入力すると、コマンド ラインから直接コマンドレットのヘルプを取得できます。</span><span class="sxs-lookup"><span data-stu-id="bbb49-118">You can retrieve help for a cmdlet directly from the command line by typing a command similar to the following:</span></span>
  
```PowerShell
Get-Help New-CsVoicePolicy -Full
```

<span data-ttu-id="bbb49-119">前述のコマンドは、**New-CsVoicePolicy** コマンドレットで使用できるすべてのヘルプを取得します。</span><span class="sxs-lookup"><span data-stu-id="bbb49-119">The preceding command retrieves the complete help available for the **New-CsVoicePolicy** cmdlet.</span></span> <span data-ttu-id="bbb49-120">別のコマンドレットのヘルプを表示するには、**New-CsVoicePolicy** を、ヘルプを取得したいコマンドレットの名前に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="bbb49-120">To view help for a different cmdlet, substitute **New-CsVoicePolicy** with the name of the cmdlet for which you want to retrieve help.</span></span>
  
<span data-ttu-id="bbb49-121">Skype for Business Server の管理に使用できるコマンドレットの完全な一覧を取得するには、シェル コマンド プロンプトで次を入力します。</span><span class="sxs-lookup"><span data-stu-id="bbb49-121">To retrieve a full list of cmdlets available for managing Skype for Business Server, type the following at the shell command prompt:</span></span> 
  
```PowerShell
Get-Command * -Module SkypeforBusiness -CommandType cmdlet
```



<span data-ttu-id="bbb49-122">Skype for Business Server のWindows PowerShellについて知る必要があります。</span><span class="sxs-lookup"><span data-stu-id="bbb49-122">Things to know about Windows PowerShell in Skype for Business Server:</span></span>
  
- <span data-ttu-id="bbb49-123">Skype for Business Server コマンドレットを実行するには、Skype for Business Server 管理シェルを開きます。</span><span class="sxs-lookup"><span data-stu-id="bbb49-123">To run the Skype for Business Server cmdlets, open the Skype for Business Server Management Shell.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="bbb49-124">Skype for Business Server 管理シェルWindows PowerShell新しいウィンドウを開いた場合、既定では Skype コマンドレットを実行できない場合があります。</span><span class="sxs-lookup"><span data-stu-id="bbb49-124">If you open a Windows PowerShell window rather than the Skype for Business Server Management Shell, by default you may not be able to run the Skype cmdlets.</span></span> <span data-ttu-id="bbb49-125">Skype for Business Server コマンドレットを Windows PowerShell から実行するには、最初に次のコマンド プロンプトで次Windows PowerShell入力します。>  `Import-Module SkypeforBusiness`</span><span class="sxs-lookup"><span data-stu-id="bbb49-125">To run Skype for Business Server cmdlets from within Windows PowerShell, first type the following at the Windows PowerShell command prompt: >  `Import-Module SkypeforBusiness`</span></span>
  
- <span data-ttu-id="bbb49-126">Skype for Business Server 管理シェルは、すべての Skype for Business Server Enterprise Edition フロントエンド サーバーまたは Standard Edition サーバーに自動的にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="bbb49-126">Skype for Business Server Management Shell is automatically installed on every Skype for Business Server Enterprise Edition Front End Server or Standard Edition server.</span></span>
    
- <span data-ttu-id="bbb49-127">Skype for Business Server 管理シェル のヘルプ コンテンツを更新するには [、Update-Help コマンドレットを実行](https://technet.microsoft.com/library/hh849720.aspx) します。</span><span class="sxs-lookup"><span data-stu-id="bbb49-127">You can update the Skype for Business Server Management Shell help content by running the [Update-Help](https://technet.microsoft.com/library/hh849720.aspx) cmdlet.</span></span> <span data-ttu-id="bbb49-128">次Update-Helpコマンドレットは、Skype for Business コマンドレットの更新プログラムを含め、コンピューターにインストールされているモジュールのすべてで使用可能な最新のヘルプ ファイルをダウンロードしてインストールします。</span><span class="sxs-lookup"><span data-stu-id="bbb49-128">The Update-Help cmdlet downloads and installs the newest help files available for all of the modules installed on your computer, including updates to Skype for Business cmdlets.</span></span>
    
    <span data-ttu-id="bbb49-129">既定では **、Update-Help** コマンドレットは Skype for Business Server にインストールされているモジュールを更新します。</span><span class="sxs-lookup"><span data-stu-id="bbb49-129">By default, the **Update-Help** cmdlet will update all the modules installed on your Skype for Business Server.</span></span> <span data-ttu-id="bbb49-130">特定のモジュールのみを更新する場合は _、Module_ パラメーターを使用してコマンドレットのスコープを制限できます。</span><span class="sxs-lookup"><span data-stu-id="bbb49-130">If you want to update only certain modules, you can use the _Module_ parameter to limit the scope of the cmdlet.</span></span> <span data-ttu-id="bbb49-131">次の例では、Skype for Business モジュールのみを更新します。</span><span class="sxs-lookup"><span data-stu-id="bbb49-131">The following example updates only the Skype for Business module.</span></span>
    
  ```PowerShell
  Update-Help -Module SkypeforBusiness
  ```

    <span data-ttu-id="bbb49-132">インターネットに接続されていないサーバーでヘルプを更新する必要がある場合は [、Save-Help](https://technet.microsoft.com/library/hh849724.aspx) コマンドレットを使用してヘルプの最新バージョンを取得し、指定した場所に保存できます。</span><span class="sxs-lookup"><span data-stu-id="bbb49-132">If you need to update the Help on servers that are not connected to the internet, you can use the [Save-Help](https://technet.microsoft.com/library/hh849724.aspx) cmdlet to get the latest version of the help and save it to a location you specify.</span></span> <span data-ttu-id="bbb49-133">その後、インターネットに接続されていないサーバーで **Update-Help** コマンドレットを _-SourcePath_ パラメーターと共に使用して、選択した場所から更新されたヘルプを取得できます。</span><span class="sxs-lookup"><span data-stu-id="bbb49-133">You can then use the **Update-Help** cmdlet with the _-SourcePath_ parameter on servers not connected to the internet to get the updated help from the location you selected.</span></span> <span data-ttu-id="bbb49-134">次の例は、ヘルプ ファイルをネットワーク ファイル共有に保存し、ファイル共有から Skype for Business モジュールのヘルプを更新する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="bbb49-134">The following example shows how to save the help files to a network file share, and then update the help for the Skype for Business module from the file share.</span></span>
    
  ```PowerShell
  // Save the help files
   Save-Help -DestinationPath \\UpdateShare\HelpDownload
  // Run Update-Help against the local help files
   Update-Help -Module SkypeforBusiness -SourcePath \\UpdateShare\HelpDownload
  ```

    <span data-ttu-id="bbb49-135">詳細については、「更新可能なヘルプ [について」を参照してください](https://technet.microsoft.com/library/hh847735.aspx)。</span><span class="sxs-lookup"><span data-stu-id="bbb49-135">For more detailed information, see [About Updatable Help](https://technet.microsoft.com/library/hh847735.aspx).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="bbb49-136">リモートで PowerShell を使用している場合は、ファイアウォール経由の通信を許可する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bbb49-136">If you are using PowerShell remotely you may need to allow communication through a firewall.</span></span> <span data-ttu-id="bbb49-137">PowerShell リモート処理で使用されるポートの詳細については [、「PowerShell リモート処理で使用するポート」を参照してください](https://blogs.technet.microsoft.com/christwe/2012/06/20/what-port-does-powershell-remoting-use/)。</span><span class="sxs-lookup"><span data-stu-id="bbb49-137">To learn more about the ports PowerShell remoting uses, see [What Port Does PowerShell Remoting Use?](https://blogs.technet.microsoft.com/christwe/2012/06/20/what-port-does-powershell-remoting-use/).</span></span>
    

