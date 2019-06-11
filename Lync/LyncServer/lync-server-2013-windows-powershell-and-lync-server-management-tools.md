---
title: 'Lync Server 2013: Windows PowerShell と Lync Server の管理ツール'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Windows PowerShell and Lync Server 2013 management tools
ms:assetid: 6a285f7c-0ef5-4cab-9976-d03be276e35d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481130(v=OCS.15)
ms:contentKeyID: 59893869
ms.date: 07/20/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 814253d909ff7065ccc028cf5822be7a7331a2fe
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848095"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="windows-powershell-and-lync-server-2013-management-tools"></a><span data-ttu-id="46c39-102">Windows PowerShell と Lync Server 2013 の管理ツール</span><span class="sxs-lookup"><span data-stu-id="46c39-102">Windows PowerShell and Lync Server 2013 management tools</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="46c39-103">_**最終更新日:** 2016-07-20_</span><span class="sxs-lookup"><span data-stu-id="46c39-103">_**Topic Last Modified:** 2016-07-20_</span></span>

<span data-ttu-id="46c39-104">Microsoft Lync Server 2013 では、管理ツールは Windows PowerShell を使って実装されています。</span><span class="sxs-lookup"><span data-stu-id="46c39-104">In Microsoft Lync Server 2013, management tools are implemented using Windows PowerShell.</span></span> <span data-ttu-id="46c39-105">Windows PowerShell には、コマンドライン環境、製品固有のコマンド、完全なスクリプト言語が含まれています。</span><span class="sxs-lookup"><span data-stu-id="46c39-105">Windows PowerShell includes a command-line environment, product-specific commands, and a full scripting language.</span></span> <span data-ttu-id="46c39-106">Windows PowerShell を使用して実装されている Lync Server 2013 ツールには、次のようなものがあります。</span><span class="sxs-lookup"><span data-stu-id="46c39-106">Lync Server 2013 tools that are implemented using Windows PowerShell include the following:</span></span>

  - <span data-ttu-id="46c39-107">**トポロジビルダー**。</span><span class="sxs-lookup"><span data-stu-id="46c39-107">**Topology Builder**.</span></span> <span data-ttu-id="46c39-108">トポロジビルダーを使用して、計画されたトポロジを作成、調整、および公開し、サーバーのインストールを開始する前にトポロジを検証します。</span><span class="sxs-lookup"><span data-stu-id="46c39-108">You use Topology Builder to create, adjust, and publish your planned topology, and it validates your topology before you begin server installations.</span></span> <span data-ttu-id="46c39-109">個々のサーバーに Lync Server 2013 をインストールすると、サーバーはインストールプロセスの一環として公開されたトポロジを読み取り、インストールプログラムはトポロジで指示されたとおりにサーバーを展開します。</span><span class="sxs-lookup"><span data-stu-id="46c39-109">When you install Lync Server 2013 on individual servers, the servers read the published topology as part of the installation process, and the installation program deploys the server as directed in the topology.</span></span> <span data-ttu-id="46c39-110">After setup, configuration information is automatically replicated to all servers.</span><span class="sxs-lookup"><span data-stu-id="46c39-110">After setup, configuration information is automatically replicated to all servers.</span></span> <span data-ttu-id="46c39-111">Components can be added to your deployment only by using Topology Builder.</span><span class="sxs-lookup"><span data-stu-id="46c39-111">Components can be added to your deployment only by using Topology Builder.</span></span>

  - <span data-ttu-id="46c39-112">**Lync Server 管理シェル**。</span><span class="sxs-lookup"><span data-stu-id="46c39-112">**Lync Server Management Shell**.</span></span> <span data-ttu-id="46c39-113">Lync Server 管理シェルを使用すると、展開の完全なコマンドライン管理を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="46c39-113">You can use Lync Server Management Shell for full command-line management of your deployment.</span></span>

  - <span data-ttu-id="46c39-114">**Lync Server コントロールパネル**。</span><span class="sxs-lookup"><span data-stu-id="46c39-114">**Lync Server Control Panel**.</span></span> <span data-ttu-id="46c39-115">Microsoft Lync Server 2013 コントロールパネルのユーザーインターフェイスを使用して、展開で最も一般的なタスクを管理することができます。</span><span class="sxs-lookup"><span data-stu-id="46c39-115">You can use the Microsoft Lync Server 2013 Control Panel user interface to manage the most common tasks in your deployment.</span></span>

<span data-ttu-id="46c39-116">これらのツールは、550製品固有のコマンドレットを閉じるなど、展開を管理するための Windows PowerShell コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="46c39-116">These tools use Windows PowerShell cmdlets for management of your deployment, including close to 550 product-specific cmdlets.</span></span> <span data-ttu-id="46c39-117">Lync Server 2013 に含まれているセキュリティコマンドレットは、主に認証、ユーザー権利、アクセス許可を管理するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="46c39-117">The security cmdlets included in Lync Server 2013 are primarily used to manage authentication, and user rights and permissions.</span></span> <span data-ttu-id="46c39-118">認証の管理には、さまざまなコマンドレット (証明書と暗証番号 (PIN) の認証用のコマンドレットなど) を使用できます。</span><span class="sxs-lookup"><span data-stu-id="46c39-118">A wide variety of cmdlets are available for managing authentication, including cmdlets for certificate and personal identification number (PIN) authentication.</span></span> <span data-ttu-id="46c39-119">さらに、いくつかのコマンドレットを使用して、新しい役割ベースのアクセス制御 (RBAC) 機能を使用して、Lync Server 2013 の管理制御を委任することができます。</span><span class="sxs-lookup"><span data-stu-id="46c39-119">In addition, a number of cmdlets enable you to use the new Role-Based Access Control (RBAC) feature to delegate administrative control of Lync Server 2013.</span></span> <span data-ttu-id="46c39-120">Lync Server のコマンドレットの詳細については、「 [Lync server 2013 管理シェル](lync-server-2013-lync-server-management-shell.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="46c39-120">For details about the Lync Server cmdlets, see [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md).</span></span>

<span data-ttu-id="46c39-121">Windows PowerShell のスクリプト セキュリティ機能は、Microsoft Visual Basic Scripting Edition (VBScript) など、古いテクノロジにおけるスクリプト関連のいくつかのセキュリティ問題を回避するように特別に設計されています。</span><span class="sxs-lookup"><span data-stu-id="46c39-121">The script security features for Windows PowerShell are specifically designed to help prevent some of the scripting-related security problems of older technologies, including Microsoft Visual Basic Scripting Edition (VBScript).</span></span> <span data-ttu-id="46c39-122">Windows PowerShell のセキュリティ機能は、ユーザーが簡単にスクリプトを実行することができない環境を作成することを目的としています。</span><span class="sxs-lookup"><span data-stu-id="46c39-122">The Windows PowerShell security features are intended to create an environment in which users cannot easily or unknowingly run scripts.</span></span> <span data-ttu-id="46c39-123">既定では、Windows PowerShell のセキュリティ機能は有効になっています。</span><span class="sxs-lookup"><span data-stu-id="46c39-123">By default, Windows PowerShell security features are enabled.</span></span> <span data-ttu-id="46c39-124">これらの機能の状態は、スクリプトに関するニーズと多様なセキュリティの目標に応じて変更できます。</span><span class="sxs-lookup"><span data-stu-id="46c39-124">You can modify the state of those features to accommodate your scripting needs and a variety of security goals.</span></span> <span data-ttu-id="46c39-125">シェルによってユーザーがスクリプトを実行できないようにするというわけではありません。</span><span class="sxs-lookup"><span data-stu-id="46c39-125">This is not to say that the shell makes it impossible for users to run scripts.</span></span> <span data-ttu-id="46c39-126">あくまでも、ユーザー自身がスクリプトを実行しているという認識を持たずにスクリプトを実行することを、既定で困難にするということです。</span><span class="sxs-lookup"><span data-stu-id="46c39-126">Rather, the shell makes it difficult—by default—for users to run scripts without realizing they are doing so.</span></span> <span data-ttu-id="46c39-127">詳細については、「Windows PowerShell [http://go.microsoft.com/fwlink/p/?LinkId=213145](http://go.microsoft.com/fwlink/p/?linkid=213145)スクリプトのセキュリティ」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="46c39-127">For details, see Windows PowerShell Script Security at [http://go.microsoft.com/fwlink/p/?LinkId=213145](http://go.microsoft.com/fwlink/p/?linkid=213145).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

