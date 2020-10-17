---
title: 'Lync Server 2013: Lync Server 管理シェル'
description: 'Lync Server 2013: Lync Server 管理シェル。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Server Management Shell
ms:assetid: 674b523b-c0b7-4ed6-9e67-afa6e8ac7e12
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398474(v=OCS.15)
ms:contentKeyID: 48184386
ms.date: 09/20/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 45727c42899defcf20ce36e2a27a9268a52ecd71
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543183"
---
# <a name="lync-server-2013-management-shell"></a><span data-ttu-id="f7780-103">Lync Server 2013 管理シェル</span><span class="sxs-lookup"><span data-stu-id="f7780-103">Lync Server 2013 Management Shell</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f7780-104">_**トピックの最終更新日:** 2017-09-20_</span><span class="sxs-lookup"><span data-stu-id="f7780-104">_**Topic Last Modified:** 2017-09-20_</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f7780-105">Skype for Business のコマンドレットリファレンスが docs.microsoft.com に移動されました。</span><span class="sxs-lookup"><span data-stu-id="f7780-105">Skype for Business cmdlet reference has moved to docs.microsoft.com.</span></span> <span data-ttu-id="f7780-106">以下のリンクをクリックすると、新しい docs.microsoft.com ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="f7780-106">Clicking on the links below will take you to the new docs.microsoft.com page.</span></span> <span data-ttu-id="f7780-107">これで、GitHub を通じてコミュニティの投稿に使用できるようになるコンテンツが公開されました。</span><span class="sxs-lookup"><span data-stu-id="f7780-107">The content is now open sourced and available for community contributions through GitHub.</span></span> <span data-ttu-id="f7780-108">投稿に興味はありますか?</span><span class="sxs-lookup"><span data-stu-id="f7780-108">Interested in contributing?</span></span> <span data-ttu-id="f7780-109">ここでは、リポジトリ内の README を確認してください。 <A href="https://github.com/microsoftdocs/office-docs-powershell">https://github.com/MicrosoftDocs/office-docs-powershell</A></span><span class="sxs-lookup"><span data-stu-id="f7780-109">Check out the README in the repo here: <A href="https://github.com/microsoftdocs/office-docs-powershell">https://github.com/MicrosoftDocs/office-docs-powershell</A></span></span>



</div>

<span data-ttu-id="f7780-110">Microsoft Lync Server 2010 は、Microsoft Office Communications Server 2007 R2 で利用可能な機能と比較して、新しい機能と改善された機能のセットを導入しました。</span><span class="sxs-lookup"><span data-stu-id="f7780-110">Microsoft Lync Server 2010 introduced a large set of new and improved features compared to what was available in Microsoft Office Communications Server 2007 R2.</span></span> <span data-ttu-id="f7780-111">1つの改善点は、実装を管理する方法です。</span><span class="sxs-lookup"><span data-stu-id="f7780-111">One improvement is the way in which you manage your implementation.</span></span> <span data-ttu-id="f7780-112">たとえば、Lync Server コントロールパネルと呼ばれる新しいユーザーインターフェイスが用意されています。これは、Microsoft 管理コンソールで最も多くのユーザーが使用しているものから大きな変化を表します。</span><span class="sxs-lookup"><span data-stu-id="f7780-112">For example, there’s a new user interface, called the Lync Server Control Panel, which represents a big shift from what most people are used to with the Microsoft Management Console.</span></span> <span data-ttu-id="f7780-113">その他の管理性の向上には、Windows PowerShell が含まれています。</span><span class="sxs-lookup"><span data-stu-id="f7780-113">The other major improvement to manageability is the inclusion of Windows PowerShell.</span></span>

<span data-ttu-id="f7780-114">Windows PowerShell を使用すると、コマンドラインから Microsoft アプリケーションを管理できます。</span><span class="sxs-lookup"><span data-stu-id="f7780-114">Windows PowerShell allows you to manage Microsoft applications from the command line.</span></span> <span data-ttu-id="f7780-115">Windows PowerShell にはコマンドライン環境、製品固有のコマンド、およびすべてのスクリプト言語が含まれます。</span><span class="sxs-lookup"><span data-stu-id="f7780-115">It includes a command-line environment, product-specific commands, and a full scripting language.</span></span> <span data-ttu-id="f7780-116">Windows PowerShell は、最初は2006でリリースされた Windows オペレーティングシステム用のダウンロード可能なリリースとして導入され、Microsoft Exchange Server 2007 を管理するためのコマンドラインインターフェイスとして組み込まれていました。</span><span class="sxs-lookup"><span data-stu-id="f7780-116">Windows PowerShell was first introduced as a downloadable release for the Windows operating system late in 2006, and was incorporated as the command-line interface for manageability of Microsoft Exchange Server 2007.</span></span> <span data-ttu-id="f7780-117">その時点から、成長を続け、多くの Microsoft サーバー製品に組み込まれており、Microsoft Lync Server 2013 の最新の状態になっています。</span><span class="sxs-lookup"><span data-stu-id="f7780-117">From that point it continued to grow, and it has been incorporated into most of the Microsoft Server products, the most recent of these being Microsoft Lync Server 2013.</span></span> <span data-ttu-id="f7780-118">Lync Server 2010 には、展開のすべての側面を管理するために使用できる、550製品固有のコマンドレットがあります。</span><span class="sxs-lookup"><span data-stu-id="f7780-118">Lync Server 2010 introduced close to 550 product-specific cmdlets that you can use to manage every aspect of your deployment.</span></span>

<span data-ttu-id="f7780-119">次のセクションには、コマンドレットの一覧とその説明が含まれます。</span><span class="sxs-lookup"><span data-stu-id="f7780-119">The following sections contain a list of cmdlets and their descriptions.</span></span> <span data-ttu-id="f7780-120">この情報は、コマンド ラインから直接入手することもできます。</span><span class="sxs-lookup"><span data-stu-id="f7780-120">This information is also available directly from the command line.</span></span> <span data-ttu-id="f7780-121">Lync Server 管理シェルコマンドプロンプトで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="f7780-121">Simply type the following at the Lync Server Management Shell command prompt:</span></span>

    Get-Help <cmdlet name> -Full

<span data-ttu-id="f7780-122">たとえば、**New-CsVoicePolicy** コマンドレットに関するヘルプをコマンド プロンプトから取得するには、以下のように入力します。</span><span class="sxs-lookup"><span data-stu-id="f7780-122">For example, to retrieve help from the command prompt on the **New-CsVoicePolicy** cmdlet, type the following:</span></span>

    Get-Help New-CsVoicePolicy -Full

<span data-ttu-id="f7780-123">Lync Server 2013 での Windows PowerShell について知っておくべき事柄:</span><span class="sxs-lookup"><span data-stu-id="f7780-123">Things to know about Windows PowerShell in Lync Server 2013:</span></span>

  - <span data-ttu-id="f7780-124">Lync Server コマンドレットを実行するには、Lync Server 管理シェルを開きます。</span><span class="sxs-lookup"><span data-stu-id="f7780-124">To run the Lync Server cmdlets, open the Lync Server Management Shell.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="f7780-125">Lync Server 管理シェルではなく、Windows PowerShell ウィンドウを開くと、既定で Lync Server コマンドレットを実行することはできません。</span><span class="sxs-lookup"><span data-stu-id="f7780-125">If you open a Windows PowerShell window rather than the Lync Server Management Shell, by default you will not be able to run the Lync Server cmdlets.</span></span> <span data-ttu-id="f7780-126">Windows PowerShell 内から Lync Server コマンドレットを実行するには、まず Windows PowerShell コマンドプロンプトで次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="f7780-126">To run the Lync Server cmdlets from within Windows PowerShell, first type the following at the Windows PowerShell command prompt:</span></span><BR><span data-ttu-id="f7780-127">Import-Module Lync</span><span class="sxs-lookup"><span data-stu-id="f7780-127">Import-Module Lync</span></span>

    
    </div>

  - <span data-ttu-id="f7780-128">Lync server 管理シェルは、すべての Lync Server Enterprise Edition フロントエンドサーバーまたは Standard Edition サーバーに自動的にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="f7780-128">Lync Server Management Shell is automatically installed on every Lync Server Enterprise Edition Front End Server or Standard Edition server.</span></span>

  - <span data-ttu-id="f7780-129">Windows PowerShell および Microsoft Lync Server 2013 コマンドレットの概要と詳細情報については、「Lync Server Windows PowerShell ブログ」を参照して [https://go.microsoft.com/fwlink/p/?linkId=203150](https://go.microsoft.com/fwlink/p/?linkid=203150) ください。</span><span class="sxs-lookup"><span data-stu-id="f7780-129">New and updated information, sample scripts, and help for getting started and learning more about Windows PowerShell and Microsoft Lync Server 2013 cmdlets is available at the Lync Server Windows PowerShell Blog [https://go.microsoft.com/fwlink/p/?linkId=203150](https://go.microsoft.com/fwlink/p/?linkid=203150).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

