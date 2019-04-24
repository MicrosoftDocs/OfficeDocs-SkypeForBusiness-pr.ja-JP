---
title: Skype for Business Server 管理シェル
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 674b523b-c0b7-4ed6-9e67-afa6e8ac7e12
description: ビジネス サーバー管理シェルの Skype では、サーバーの管理と管理のコマンド ライン インターフェイスを提供します。 Windows PowerShell の上に構築し、Skype と従来の Lync server 製品に固有のコマンドレットが管理の包括的なセットが含まれています。
ms.openlocfilehash: 243ff7a684bb14f73ef9f4836ce00e8048fbb236
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32199232"
---
# <a name="skype-for-business-server-management-shell"></a><span data-ttu-id="915bc-104">Skype for Business Server 管理シェル</span><span class="sxs-lookup"><span data-stu-id="915bc-104">Skype for Business Server Management Shell</span></span>
 
<span data-ttu-id="915bc-105">ビジネス サーバー管理シェルの Skype では、サーバーの管理と管理のコマンド ライン インターフェイスを提供します。</span><span class="sxs-lookup"><span data-stu-id="915bc-105">The Skype for Business Server Management Shell provides the command line interface for server administration and management.</span></span> <span data-ttu-id="915bc-106">Windows PowerShell の上に構築し、Skype と従来の Lync server 製品に固有のコマンドレットが管理の包括的なセットが含まれています。</span><span class="sxs-lookup"><span data-stu-id="915bc-106">It is built on Windows PowerShell and includes a comprehensive set of management and administration cmdlets that are specific to Skype and legacy Lync server products.</span></span>
  
<span data-ttu-id="915bc-107">Windows PowerShell を使用すると、Microsoft アプリケーションをコマンドラインから管理できます。</span><span class="sxs-lookup"><span data-stu-id="915bc-107">Windows PowerShell allows you to manage Microsoft applications from the command line.</span></span> <span data-ttu-id="915bc-108">コマンド ライン環境、製品固有のコマンド、完全なスクリプト言語が用意されています。</span><span class="sxs-lookup"><span data-stu-id="915bc-108">It includes a command-line environment, product-specific commands, and a full scripting language.</span></span> <span data-ttu-id="915bc-109">Windows PowerShell は、2006 年の後半で Windows オペレーティング システム用のダウンロード可能なリリースとして初めて導入され、Microsoft Exchange Server 2007 の管理用のコマンド ライン インターフェイスとして採用されました。</span><span class="sxs-lookup"><span data-stu-id="915bc-109">Windows PowerShell was first introduced as a downloadable release for the Windows operating system late in 2006, and was incorporated as the command-line interface for manageability of Microsoft Exchange Server 2007.</span></span> <span data-ttu-id="915bc-110">それは、Lync Server 2010 から Lync と Skype のサーバーを含む、Microsoft サーバー製品の大部分に組み込まれています。</span><span class="sxs-lookup"><span data-stu-id="915bc-110">It has been incorporated into most of the Microsoft Server products, including Lync and Skype servers beginning with Lync Server 2010.</span></span> <span data-ttu-id="915bc-111">700 を超える Lync と Skype の特定のコマンドレットがビジネスのサーバー管理シェルの Skype で利用できます。</span><span class="sxs-lookup"><span data-stu-id="915bc-111">There are over 700 Lync and Skype specific cmdlets available in the Skype for Business Server Management Shell.</span></span>
  
> [!NOTE]
> <span data-ttu-id="915bc-112">コマンドレット参照のビジネス用の Skype は、docs.microsoft.com に移動します。</span><span class="sxs-lookup"><span data-stu-id="915bc-112">Skype for Business cmdlet reference has moved to docs.microsoft.com.</span></span> <span data-ttu-id="915bc-113">以下のリンクをクリックするとクリックすると、新しい docs.microsoft.com ページです。</span><span class="sxs-lookup"><span data-stu-id="915bc-113">Clicking on the links below will take you to the new docs.microsoft.com page.</span></span> <span data-ttu-id="915bc-114">コンテンツは、ここでは GitHub から差し引かれるとの利用可能なコミュニティを開いている投稿です。</span><span class="sxs-lookup"><span data-stu-id="915bc-114">The content is now open sourced and available for community contributions through GitHub.</span></span> <span data-ttu-id="915bc-115">寄贈したいですか。</span><span class="sxs-lookup"><span data-stu-id="915bc-115">Interested in contributing?</span></span> <span data-ttu-id="915bc-116">ここでは、リポジトリの索引にある readme ファイルを確認します。[https://github.com/MicrosoftDocs/office-docs-powershell](https://github.com/MicrosoftDocs/office-docs-powershell)</span><span class="sxs-lookup"><span data-stu-id="915bc-116">Check out the README in the repo here: [https://github.com/MicrosoftDocs/office-docs-powershell](https://github.com/MicrosoftDocs/office-docs-powershell)</span></span>
  
<span data-ttu-id="915bc-117">ビジネス サーバー管理シェルには、Skype を使用してビジネス サーバーの Skype を管理する管理者を有効にするコマンドレットが 700 を超えるビジネス サーバーの Skype が同梱されています。</span><span class="sxs-lookup"><span data-stu-id="915bc-117">Skype for Business Server ships with more than 700 cmdlets that enable administrators to manage Skype for Business Server using the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="915bc-118">以下のようなコマンドを入力すると、コマンドレットのヘルプを、コマンド ラインから直接取得することができます。</span><span class="sxs-lookup"><span data-stu-id="915bc-118">You can retrieve help for a cmdlet directly from the command line by typing a command similar to the following:</span></span>
  
```
Get-Help New-CsVoicePolicy -Full
```

<span data-ttu-id="915bc-119">前述のコマンドは、**New-CsVoicePolicy** コマンドレットで使用できるすべてのヘルプを取得します。</span><span class="sxs-lookup"><span data-stu-id="915bc-119">The preceding command retrieves the complete help available for the **New-CsVoicePolicy** cmdlet.</span></span> <span data-ttu-id="915bc-120">別のコマンドレットのヘルプを表示するには、**New-CsVoicePolicy** を、ヘルプを取得したいコマンドレットの名前に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="915bc-120">To view help for a different cmdlet, substitute **New-CsVoicePolicy** with the name of the cmdlet for which you want to retrieve help.</span></span>
  
<span data-ttu-id="915bc-121">Skype for Business Server の管理に使用できるすべてのコマンドレットの一覧を取得するには、シェル コマンド プロンプトで以下を入力します。</span><span class="sxs-lookup"><span data-stu-id="915bc-121">To retrieve a full list of cmdlets available for managing Skype for Business Server, type the following at the shell command prompt:</span></span> 
  
```
Get-Command * -Module SkypeforBusiness -CommandType cmdlet
```



<span data-ttu-id="915bc-122">ビジネス サーバー用 Skype で Windows PowerShell について理解すること:</span><span class="sxs-lookup"><span data-stu-id="915bc-122">Things to know about Windows PowerShell in Skype for Business Server:</span></span>
  
- <span data-ttu-id="915bc-123">Skype ビジネス サーバー コマンドレットを実行するには、ビジネス サーバー管理シェルには、Skype を開きます。</span><span class="sxs-lookup"><span data-stu-id="915bc-123">To run the Skype for Business Server cmdlets, open the Skype for Business Server Management Shell.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="915bc-124">ビジネス サーバー管理シェルには、Skype ではなく、Windows PowerShell のウィンドウを開いた場合既定では、できないことがあります Skype コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="915bc-124">If you open a Windows PowerShell window rather than the Skype for Business Server Management Shell, by default you may not be able to run the Skype cmdlets.</span></span> <span data-ttu-id="915bc-125">Skype Windows PowerShell 内からのビジネス サーバー コマンドレットを実行する Windows PowerShell コマンド プロンプトで最初に、次の入力: _gt`Import-Module SkypeforBusiness`</span><span class="sxs-lookup"><span data-stu-id="915bc-125">To run Skype for Business Server cmdlets from within Windows PowerShell, first type the following at the Windows PowerShell command prompt: >  `Import-Module SkypeforBusiness`</span></span>
  
- <span data-ttu-id="915bc-126">ビジネス サーバー エンタープライズ版フロント エンド サーバーまたは Standard Edition サーバーのすべての Skype のビジネス サーバー管理シェルの Skype が自動的にインストールします。</span><span class="sxs-lookup"><span data-stu-id="915bc-126">Skype for Business Server Management Shell is automatically installed on every Skype for Business Server Enterprise Edition Front End Server or Standard Edition server.</span></span>
    
- <span data-ttu-id="915bc-127">ビジネス サーバー管理シェルのヘルプ コンテンツの Skype を更新するには、[更新プログラムのヘルプ](https://technet.microsoft.com/en-us/library/hh849720.aspx)のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="915bc-127">You can update the Skype for Business Server Management Shell help content by running the [Update-Help](https://technet.microsoft.com/en-us/library/hh849720.aspx) cmdlet.</span></span> <span data-ttu-id="915bc-128">更新ヘルプのコマンドレットでは、Skype ビジネス コマンドレットの更新など、コンピューターにインストールされているモジュールのすべての利用可能な最新のヘルプ ファイルをダウンロードしています。</span><span class="sxs-lookup"><span data-stu-id="915bc-128">The Update-Help cmdlet downloads and installs the newest help files available for all of the modules installed on your computer, including updates to Skype for Business cmdlets.</span></span>
    
    <span data-ttu-id="915bc-129">既定では、**更新プログラムのヘルプ**のコマンドレットは、Skype のビジネス サーバーがインストールされているすべてのモジュールを更新します。</span><span class="sxs-lookup"><span data-stu-id="915bc-129">By default, the **Update-Help** cmdlet will update all the modules installed on your Skype for Business Server.</span></span> <span data-ttu-id="915bc-130">特定のモジュールのみ更新する場合は、_Module_ パラメーターを使用してこのコマンドレットのスコープを制限できます。</span><span class="sxs-lookup"><span data-stu-id="915bc-130">If you want to update only certain modules, you can use the _Module_ parameter to limit the scope of the cmdlet.</span></span> <span data-ttu-id="915bc-131">次の例では、ビジネス モジュールの Skype のみを更新します。</span><span class="sxs-lookup"><span data-stu-id="915bc-131">The following example updates only the Skype for Business module.</span></span>
    
  ```
  Update-Help -Module SkypeforBusiness
  ```

    <span data-ttu-id="915bc-132">インターネットに接続されていないサーバーのヘルプを更新する場合は、ヘルプの最新バージョンを取得し、指定された場所に保存する[保存ヘルプ](https://technet.microsoft.com/en-us/library/hh849724.aspx)コマンドレットを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="915bc-132">If you need to update the Help on servers that are not connected to the internet, you can use the [Save-Help](https://technet.microsoft.com/en-us/library/hh849724.aspx) cmdlet to get the latest version of the help and save it to a location you specify.</span></span> <span data-ttu-id="915bc-133">選択した場所から更新済みのヘルプを表示するのにはインターネットに接続されていないサーバー上_で見つかった_パラメーターを使用して、**更新プログラムのヘルプ**のコマンドレットを使用できます。</span><span class="sxs-lookup"><span data-stu-id="915bc-133">You can then use the **Update-Help** cmdlet with the _-SourcePath_ parameter on servers not connected to the internet to get the updated help from the location you selected.</span></span> <span data-ttu-id="915bc-134">次の使用例は、ヘルプ ファイルをネットワーク ファイル共有に保存し、ファイル共有からビジネス モジュールの Skype のヘルプを更新する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="915bc-134">The following example shows how to save the help files to a network file share, and then update the help for the Skype for Business module from the file share.</span></span>
    
  ```
  // Save the help files
   Save-Help -DestinationPath \\UpdateShare\HelpDownload
  // Run Update-Help against the local help files
   Update-Help -Module SkypeforBusiness -SourcePath \\UpdateShare\HelpDownload
  ```

    <span data-ttu-id="915bc-135">詳細については、[更新可能なヘルプについて](https://technet.microsoft.com/library/hh847735.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="915bc-135">For more detailed information, see [About Updatable Help](https://technet.microsoft.com/library/hh847735.aspx).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="915bc-136">リモート PowerShell を使用している場合は、ファイアウォール経由の通信を許可する必要があります。</span><span class="sxs-lookup"><span data-stu-id="915bc-136">If you are using PowerShell remotely you may need to allow communication through a firewall.</span></span> <span data-ttu-id="915bc-137">PowerShell リモート処理を使用するポートの詳細についてを参照してください[どのようなポートは PowerShell リモート処理の使用ですか?](https://blogs.technet.microsoft.com/christwe/2012/06/20/what-port-does-powershell-remoting-use/)です。</span><span class="sxs-lookup"><span data-stu-id="915bc-137">To learn more about the ports PowerShell remoting uses, see [What Port Does PowerShell Remoting Use?](https://blogs.technet.microsoft.com/christwe/2012/06/20/what-port-does-powershell-remoting-use/).</span></span>
    

