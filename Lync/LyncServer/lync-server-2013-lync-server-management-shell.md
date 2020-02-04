---
title: 'Lync Server 2013: Lync Server 管理シェル'
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
ms.openlocfilehash: d519b647eae4937af10a38673803484a253baef7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742187"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-server-2013-management-shell"></a><span data-ttu-id="1d2c9-102">Lync Server 2013 管理シェル</span><span class="sxs-lookup"><span data-stu-id="1d2c9-102">Lync Server 2013 Management Shell</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1d2c9-103">_**最終更新日:** 2017-09-20_</span><span class="sxs-lookup"><span data-stu-id="1d2c9-103">_**Topic Last Modified:** 2017-09-20_</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1d2c9-104">Skype for Business コマンドレットリファレンスは docs.microsoft.com に移動されました。</span><span class="sxs-lookup"><span data-stu-id="1d2c9-104">Skype for Business cmdlet reference has moved to docs.microsoft.com.</span></span> <span data-ttu-id="1d2c9-105">以下のリンクをクリックすると、新しい docs.microsoft.com ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="1d2c9-105">Clicking on the links below will take you to the new docs.microsoft.com page.</span></span> <span data-ttu-id="1d2c9-106">これでコンテンツが公開され、GitHub を通じてコミュニティの投稿に使用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="1d2c9-106">The content is now open sourced and available for community contributions through GitHub.</span></span> <span data-ttu-id="1d2c9-107">投稿に興味をお持ちですか?</span><span class="sxs-lookup"><span data-stu-id="1d2c9-107">Interested in contributing?</span></span> <span data-ttu-id="1d2c9-108">ここでは、リポジトリ内の README を確認します。<A href="https://github.com/microsoftdocs/office-docs-powershell">https://github.com/MicrosoftDocs/office-docs-powershell</A></span><span class="sxs-lookup"><span data-stu-id="1d2c9-108">Check out the README in the repo here: <A href="https://github.com/microsoftdocs/office-docs-powershell">https://github.com/MicrosoftDocs/office-docs-powershell</A></span></span>



</div>

<span data-ttu-id="1d2c9-109">Microsoft Lync Server 2010 は、Microsoft Office Communications Server 2007 R2 で利用可能な新機能と改善された機能のセットを導入しました。</span><span class="sxs-lookup"><span data-stu-id="1d2c9-109">Microsoft Lync Server 2010 introduced a large set of new and improved features compared to what was available in Microsoft Office Communications Server 2007 R2.</span></span> <span data-ttu-id="1d2c9-110">改善点の1つとして、実装を管理する方法があります。</span><span class="sxs-lookup"><span data-stu-id="1d2c9-110">One improvement is the way in which you manage your implementation.</span></span> <span data-ttu-id="1d2c9-111">たとえば、Lync Server コントロールパネルと呼ばれる新しいユーザーインターフェイスが用意されています。このインターフェイスは、Microsoft 管理コンソールでほとんどのユーザーが使用しているものからの大きなシフトを表します。</span><span class="sxs-lookup"><span data-stu-id="1d2c9-111">For example, there’s a new user interface, called the Lync Server Control Panel, which represents a big shift from what most people are used to with the Microsoft Management Console.</span></span> <span data-ttu-id="1d2c9-112">管理性の大幅な向上には、Windows PowerShell が含まれています。</span><span class="sxs-lookup"><span data-stu-id="1d2c9-112">The other major improvement to manageability is the inclusion of Windows PowerShell.</span></span>

<span data-ttu-id="1d2c9-113">Windows PowerShell を使用すると、コマンドラインから Microsoft アプリケーションを管理できます。</span><span class="sxs-lookup"><span data-stu-id="1d2c9-113">Windows PowerShell allows you to manage Microsoft applications from the command line.</span></span> <span data-ttu-id="1d2c9-114">コマンド ライン環境、製品固有のコマンド、完全なスクリプト言語が用意されています。</span><span class="sxs-lookup"><span data-stu-id="1d2c9-114">It includes a command-line environment, product-specific commands, and a full scripting language.</span></span> <span data-ttu-id="1d2c9-115">Windows PowerShell は、最初に2006の Windows オペレーティングシステムのダウンロード可能なリリースとして導入されましたが、Microsoft Exchange Server 2007 の管理のためのコマンドラインインターフェイスとして採用されています。</span><span class="sxs-lookup"><span data-stu-id="1d2c9-115">Windows PowerShell was first introduced as a downloadable release for the Windows operating system late in 2006, and was incorporated as the command-line interface for manageability of Microsoft Exchange Server 2007.</span></span> <span data-ttu-id="1d2c9-116">この時点では、今後も成長し、Microsoft Server 製品のほとんどに組み込まれており、最新の microsoft Lync Server 2013 になっています。</span><span class="sxs-lookup"><span data-stu-id="1d2c9-116">From that point it continued to grow, and it has been incorporated into most of the Microsoft Server products, the most recent of these being Microsoft Lync Server 2013.</span></span> <span data-ttu-id="1d2c9-117">Lync Server 2010 は、展開のすべての局面を管理するために使用できる、550製品固有のコマンドレットに近い方法で導入されています。</span><span class="sxs-lookup"><span data-stu-id="1d2c9-117">Lync Server 2010 introduced close to 550 product-specific cmdlets that you can use to manage every aspect of your deployment.</span></span>

<span data-ttu-id="1d2c9-118">以降のセクションに、コマンドレットの一覧とその説明を示します。</span><span class="sxs-lookup"><span data-stu-id="1d2c9-118">The following sections contain a list of cmdlets and their descriptions.</span></span> <span data-ttu-id="1d2c9-119">この情報は、コマンド ラインで直接表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="1d2c9-119">This information is also available directly from the command line.</span></span> <span data-ttu-id="1d2c9-120">Lync Server 管理シェルのコマンドプロンプトで次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="1d2c9-120">Simply type the following at the Lync Server Management Shell command prompt:</span></span>

    Get-Help <cmdlet name> -Full

<span data-ttu-id="1d2c9-121">たとえば、**New-CsVoicePolicy** コマンドレットに関するヘルプをコマンド プロンプトで表示するには、以下のように入力します。</span><span class="sxs-lookup"><span data-stu-id="1d2c9-121">For example, to retrieve help from the command prompt on the **New-CsVoicePolicy** cmdlet, type the following:</span></span>

    Get-Help New-CsVoicePolicy -Full

<span data-ttu-id="1d2c9-122">Lync Server 2013 での Windows PowerShell について知っておくべきこと:</span><span class="sxs-lookup"><span data-stu-id="1d2c9-122">Things to know about Windows PowerShell in Lync Server 2013:</span></span>

  - <span data-ttu-id="1d2c9-123">Lync Server のコマンドレットを実行するには、Lync Server 管理シェルを開きます。</span><span class="sxs-lookup"><span data-stu-id="1d2c9-123">To run the Lync Server cmdlets, open the Lync Server Management Shell.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="1d2c9-124">Lync Server 管理シェルではなく、Windows PowerShell ウィンドウを開いた場合、既定では、Lync Server コマンドレットを実行することはできません。</span><span class="sxs-lookup"><span data-stu-id="1d2c9-124">If you open a Windows PowerShell window rather than the Lync Server Management Shell, by default you will not be able to run the Lync Server cmdlets.</span></span> <span data-ttu-id="1d2c9-125">Windows PowerShell 内から Lync Server コマンドレットを実行するには、Windows PowerShell コマンドプロンプトで次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="1d2c9-125">To run the Lync Server cmdlets from within Windows PowerShell, first type the following at the Windows PowerShell command prompt:</span></span><BR><span data-ttu-id="1d2c9-126">インポート-モジュール Lync</span><span class="sxs-lookup"><span data-stu-id="1d2c9-126">Import-Module Lync</span></span>

    
    </div>

  - <span data-ttu-id="1d2c9-127">Lync Server 管理シェルは、すべての Lync Server Enterprise Edition のフロントエンドサーバーまたは Standard Edition サーバーに自動的にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="1d2c9-127">Lync Server Management Shell is automatically installed on every Lync Server Enterprise Edition Front End Server or Standard Edition server.</span></span>

  - <span data-ttu-id="1d2c9-128">新規および更新された情報、サンプルスクリプト、および使用を開始するためのヘルプ、および Windows PowerShell と Microsoft Lync Server 2013 コマンドレットの詳細につい[https://go.microsoft.com/fwlink/p/?linkId=203150](https://go.microsoft.com/fwlink/p/?linkid=203150)ては、「Lync Server Windows powershell ブログ」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1d2c9-128">New and updated information, sample scripts, and help for getting started and learning more about Windows PowerShell and Microsoft Lync Server 2013 cmdlets is available at the Lync Server Windows PowerShell Blog [https://go.microsoft.com/fwlink/p/?linkId=203150](https://go.microsoft.com/fwlink/p/?linkid=203150).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

