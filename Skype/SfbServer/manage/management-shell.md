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
description: Skype for Business Server 管理シェルは、サーバーの管理と管理のためのコマンド ライン インターフェイスを提供します。 このコマンドレットは、Skype Windows PowerShell従来の Lync サーバー製品に固有の管理コマンドレットと管理コマンドレットの包括的なセットが含まれています。
ms.openlocfilehash: 24da9ac341129239399ea17218be8547f3549d6f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51118586"
---
# <a name="skype-for-business-server-management-shell"></a><span data-ttu-id="f4d7d-104">Skype for Business Server 管理シェル</span><span class="sxs-lookup"><span data-stu-id="f4d7d-104">Skype for Business Server Management Shell</span></span>
 
<span data-ttu-id="f4d7d-105">Skype for Business Server 管理シェルは、サーバーの管理と管理のためのコマンド ライン インターフェイスを提供します。</span><span class="sxs-lookup"><span data-stu-id="f4d7d-105">The Skype for Business Server Management Shell provides the command line interface for server administration and management.</span></span> <span data-ttu-id="f4d7d-106">このコマンドレットは、Skype Windows PowerShell従来の Lync サーバー製品に固有の管理コマンドレットと管理コマンドレットの包括的なセットが含まれています。</span><span class="sxs-lookup"><span data-stu-id="f4d7d-106">It is built on Windows PowerShell and includes a comprehensive set of management and administration cmdlets that are specific to Skype and legacy Lync server products.</span></span>
  
<span data-ttu-id="f4d7d-107">Windows PowerShellコマンド ラインから Microsoft アプリケーションを管理できます。</span><span class="sxs-lookup"><span data-stu-id="f4d7d-107">Windows PowerShell allows you to manage Microsoft applications from the command line.</span></span> <span data-ttu-id="f4d7d-108">Windows PowerShell にはコマンドライン環境、製品固有のコマンド、およびすべてのスクリプト言語が含まれます。</span><span class="sxs-lookup"><span data-stu-id="f4d7d-108">It includes a command-line environment, product-specific commands, and a full scripting language.</span></span> <span data-ttu-id="f4d7d-109">Windows PowerShellは、2006 年後半に Windows オペレーティング システムのダウンロード可能なリリースとして初めて導入され、Microsoft Exchange Server 2007 の管理性を確保するためのコマンド ライン インターフェイスとして組み込まれた。</span><span class="sxs-lookup"><span data-stu-id="f4d7d-109">Windows PowerShell was first introduced as a downloadable release for the Windows operating system late in 2006, and was incorporated as the command-line interface for manageability of Microsoft Exchange Server 2007.</span></span> <span data-ttu-id="f4d7d-110">これは、Lync Server 2010 で始まる Lync サーバーや Skype サーバーなど、ほとんどの Microsoft Server 製品に組み込まれています。</span><span class="sxs-lookup"><span data-stu-id="f4d7d-110">It has been incorporated into most of the Microsoft Server products, including Lync and Skype servers beginning with Lync Server 2010.</span></span> <span data-ttu-id="f4d7d-111">Skype for Business Server 管理シェルには、700 を超える Lync および Skype 固有のコマンドレットを使用できます。</span><span class="sxs-lookup"><span data-stu-id="f4d7d-111">There are over 700 Lync and Skype specific cmdlets available in the Skype for Business Server Management Shell.</span></span>
  
> [!NOTE]
> <span data-ttu-id="f4d7d-112">Skype for Business コマンドレットの参照は、Skype for Business コマンドレットの docs.microsoft.com。</span><span class="sxs-lookup"><span data-stu-id="f4d7d-112">Skype for Business cmdlet reference has moved to docs.microsoft.com.</span></span> <span data-ttu-id="f4d7d-113">以下のリンクをクリックすると、新しいページ docs.microsoft.com されます。</span><span class="sxs-lookup"><span data-stu-id="f4d7d-113">Clicking on the links below will take you to the new docs.microsoft.com page.</span></span> <span data-ttu-id="f4d7d-114">このコンテンツはオープンソースで、GitHub を通じてコミュニティへの投稿に利用できます。</span><span class="sxs-lookup"><span data-stu-id="f4d7d-114">The content is now open sourced and available for community contributions through GitHub.</span></span> <span data-ttu-id="f4d7d-115">貢献に興味がありますか?</span><span class="sxs-lookup"><span data-stu-id="f4d7d-115">Interested in contributing?</span></span> <span data-ttu-id="f4d7d-116">repo の README を確認してください。 [https://github.com/MicrosoftDocs/office-docs-powershell](https://github.com/MicrosoftDocs/office-docs-powershell)</span><span class="sxs-lookup"><span data-stu-id="f4d7d-116">Check out the README in the repo here: [https://github.com/MicrosoftDocs/office-docs-powershell](https://github.com/MicrosoftDocs/office-docs-powershell)</span></span>
  
<span data-ttu-id="f4d7d-117">Skype for Business Server には、管理者が Skype for Business Server 管理シェルを使用して Skype for Business Server を管理できる 700 を超えるコマンドレットが含されています。</span><span class="sxs-lookup"><span data-stu-id="f4d7d-117">Skype for Business Server ships with more than 700 cmdlets that enable administrators to manage Skype for Business Server using the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="f4d7d-118">次のようなコマンドを入力すると、コマンド ラインからコマンドレットのヘルプを直接取得できます。</span><span class="sxs-lookup"><span data-stu-id="f4d7d-118">You can retrieve help for a cmdlet directly from the command line by typing a command similar to the following:</span></span>
  
```PowerShell
Get-Help New-CsVoicePolicy -Full
```

<span data-ttu-id="f4d7d-119">前述のコマンドは、**New-CsVoicePolicy** コマンドレットで使用できるすべてのヘルプを取得します。</span><span class="sxs-lookup"><span data-stu-id="f4d7d-119">The preceding command retrieves the complete help available for the **New-CsVoicePolicy** cmdlet.</span></span> <span data-ttu-id="f4d7d-120">別のコマンドレットのヘルプを表示するには、**New-CsVoicePolicy** を、ヘルプを取得したいコマンドレットの名前に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="f4d7d-120">To view help for a different cmdlet, substitute **New-CsVoicePolicy** with the name of the cmdlet for which you want to retrieve help.</span></span>
  
<span data-ttu-id="f4d7d-121">Skype for Business Server の管理に使用できるコマンドレットの完全な一覧を取得するには、シェル コマンド プロンプトで次を入力します。</span><span class="sxs-lookup"><span data-stu-id="f4d7d-121">To retrieve a full list of cmdlets available for managing Skype for Business Server, type the following at the shell command prompt:</span></span> 
  
```PowerShell
Get-Command * -Module SkypeforBusiness -CommandType cmdlet
```



<span data-ttu-id="f4d7d-122">Skype for Business Server Windows PowerShellの詳細については、次の情報を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f4d7d-122">Things to know about Windows PowerShell in Skype for Business Server:</span></span>
  
- <span data-ttu-id="f4d7d-123">Skype for Business Server コマンドレットを実行するには、Skype for Business Server 管理シェルを開きます。</span><span class="sxs-lookup"><span data-stu-id="f4d7d-123">To run the Skype for Business Server cmdlets, open the Skype for Business Server Management Shell.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="f4d7d-124">Skype for Business Server 管理シェルWindows PowerShellウィンドウを開く場合、既定では Skype コマンドレットを実行できない場合があります。</span><span class="sxs-lookup"><span data-stu-id="f4d7d-124">If you open a Windows PowerShell window rather than the Skype for Business Server Management Shell, by default you may not be able to run the Skype cmdlets.</span></span> <span data-ttu-id="f4d7d-125">Skype for Business Server コマンドレットを Windows PowerShell 内から実行するには、まず、次のコマンド プロンプトで次Windows PowerShell入力します>  `Import-Module SkypeforBusiness`</span><span class="sxs-lookup"><span data-stu-id="f4d7d-125">To run Skype for Business Server cmdlets from within Windows PowerShell, first type the following at the Windows PowerShell command prompt: >  `Import-Module SkypeforBusiness`</span></span>
  
- <span data-ttu-id="f4d7d-126">Skype for Business Server Management Shell は、すべての Skype for Business Server Enterprise Edition フロントエンド サーバーまたは Standard Edition サーバーに自動的にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="f4d7d-126">Skype for Business Server Management Shell is automatically installed on every Skype for Business Server Enterprise Edition Front End Server or Standard Edition server.</span></span>
    
- <span data-ttu-id="f4d7d-127">Update-Help コマンドレットを実行すると、Skype for Business Server 管理シェルのヘルプ [コンテンツを更新](/powershell/module/microsoft.powershell.core/update-help) できます。</span><span class="sxs-lookup"><span data-stu-id="f4d7d-127">You can update the Skype for Business Server Management Shell help content by running the [Update-Help](/powershell/module/microsoft.powershell.core/update-help) cmdlet.</span></span> <span data-ttu-id="f4d7d-128">このUpdate-Helpは、Skype for Business コマンドレットの更新プログラムを含め、コンピューターにインストールされているモジュールすべてで利用可能な最新のヘルプ ファイルをダウンロードしてインストールします。</span><span class="sxs-lookup"><span data-stu-id="f4d7d-128">The Update-Help cmdlet downloads and installs the newest help files available for all of the modules installed on your computer, including updates to Skype for Business cmdlets.</span></span>
    
    <span data-ttu-id="f4d7d-129">既定では **、Update-Help コマンドレット** は、Skype for Business Server にインストールされているすべてのモジュールを更新します。</span><span class="sxs-lookup"><span data-stu-id="f4d7d-129">By default, the **Update-Help** cmdlet will update all the modules installed on your Skype for Business Server.</span></span> <span data-ttu-id="f4d7d-130">特定のモジュールのみを更新する場合は _、Module_ パラメーターを使用してコマンドレットのスコープを制限できます。</span><span class="sxs-lookup"><span data-stu-id="f4d7d-130">If you want to update only certain modules, you can use the _Module_ parameter to limit the scope of the cmdlet.</span></span> <span data-ttu-id="f4d7d-131">次の例では、Skype for Business モジュールのみを更新します。</span><span class="sxs-lookup"><span data-stu-id="f4d7d-131">The following example updates only the Skype for Business module.</span></span>
    
  ```PowerShell
  Update-Help -Module SkypeforBusiness
  ```

    <span data-ttu-id="f4d7d-132">インターネットに接続されていないサーバーでヘルプを更新する必要がある場合は [、Save-Help](/powershell/module/microsoft.powershell.core/save-help) コマンドレットを使用して、ヘルプの最新バージョンを取得し、指定した場所に保存できます。</span><span class="sxs-lookup"><span data-stu-id="f4d7d-132">If you need to update the Help on servers that are not connected to the internet, you can use the [Save-Help](/powershell/module/microsoft.powershell.core/save-help) cmdlet to get the latest version of the help and save it to a location you specify.</span></span> <span data-ttu-id="f4d7d-133">その後 **、Update-Help** コマンドレットを使用して、インターネットに接続されていないサーバー上の _-SourcePath_ パラメーターを使用して、選択した場所から更新されたヘルプを取得できます。</span><span class="sxs-lookup"><span data-stu-id="f4d7d-133">You can then use the **Update-Help** cmdlet with the _-SourcePath_ parameter on servers not connected to the internet to get the updated help from the location you selected.</span></span> <span data-ttu-id="f4d7d-134">次の例は、ヘルプ ファイルをネットワーク ファイル共有に保存し、ファイル共有から Skype for Business モジュールのヘルプを更新する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="f4d7d-134">The following example shows how to save the help files to a network file share, and then update the help for the Skype for Business module from the file share.</span></span>
    
  ```PowerShell
  // Save the help files
   Save-Help -DestinationPath \\UpdateShare\HelpDownload
  // Run Update-Help against the local help files
   Update-Help -Module SkypeforBusiness -SourcePath \\UpdateShare\HelpDownload
  ```

    <span data-ttu-id="f4d7d-135">詳細については、「更新可能なヘルプ [について」を参照してください](/powershell/module/microsoft.powershell.core/about/about_updatable_help)。</span><span class="sxs-lookup"><span data-stu-id="f4d7d-135">For more detailed information, see [About Updatable Help](/powershell/module/microsoft.powershell.core/about/about_updatable_help).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="f4d7d-136">PowerShell をリモートで使用している場合は、ファイアウォール経由の通信を許可する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f4d7d-136">If you are using PowerShell remotely you may need to allow communication through a firewall.</span></span> <span data-ttu-id="f4d7d-137">PowerShell リモート処理で使用されるポートの詳細については、「PowerShell リモート処理で使用する [ポート」を参照してください](/archive/blogs/christwe/what-port-does-powershell-remoting-use)。</span><span class="sxs-lookup"><span data-stu-id="f4d7d-137">To learn more about the ports PowerShell remoting uses, see [What Port Does PowerShell Remoting Use?](/archive/blogs/christwe/what-port-does-powershell-remoting-use).</span></span>
