---
title: 'Lync Server 2013: Lync クライアントの展開'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying Lync clients
ms:assetid: 3d10abf2-d484-4fa0-8f10-4a5f9dfba4f5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204827(v=OCS.15)
ms:contentKeyID: 48183925
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6ad8735834ab004753444849c529cb4ceec18c16
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "43776712"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploying-lync-clients-in-lync-server-2013"></a><span data-ttu-id="a0cd6-102">Lync Server 2013 での Lync クライアントの展開</span><span class="sxs-lookup"><span data-stu-id="a0cd6-102">Deploying Lync clients in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a0cd6-103">_**トピックの最終更新日:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="a0cd6-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="a0cd6-104">Lync 2013 には、クライアントの展開には別の方法が導入されています。</span><span class="sxs-lookup"><span data-stu-id="a0cd6-104">Lync 2013 introduces a different approach to client deployment.</span></span> <span data-ttu-id="a0cd6-105">以前のリリースからの出発では、Lync 2013 には独自のインストーラーがありません。</span><span class="sxs-lookup"><span data-stu-id="a0cd6-105">In a departure from previous releases, Lync 2013 no longer has its own installer.</span></span> <span data-ttu-id="a0cd6-106">その代わりに、Lync は Office 2013 セットアッププログラムに含まれています。</span><span class="sxs-lookup"><span data-stu-id="a0cd6-106">Instead, Lync is included with the Office 2013 setup program.</span></span> <span data-ttu-id="a0cd6-107">Lync 2013 をユーザーに展開するには、Office 2013 のインストール方法とカスタマイズツールを使用できます。</span><span class="sxs-lookup"><span data-stu-id="a0cd6-107">To deploy Lync 2013 to your users, you can use Office 2013 installation methods and customization tools.</span></span>

  - <span data-ttu-id="a0cd6-108">**Office 2013 Windows インストーラー**は、複数の MSI ファイルで構成される windows インストーラーベースのインストールパッケージです。</span><span class="sxs-lookup"><span data-stu-id="a0cd6-108">**Office 2013 Windows Installer** is a Windows Installer-based installation package that consists of multiple MSI files.</span></span> <span data-ttu-id="a0cd6-109">言語に依存しないコア MSI パッケージと 1 つ以上の言語固有のパッケージが組み合わされ 1 つの完全な製品になっています。</span><span class="sxs-lookup"><span data-stu-id="a0cd6-109">A language-neutral core MSI package is combined with one or more language-specific packages to make a complete product.</span></span> <span data-ttu-id="a0cd6-110">セットアップによって個々のパッケージがアセンブルされ、ユーザーのコンピューターへの Office のインストール中およびインストール後に、カスタマイズ タスクとメンテナンス タスクが実行されます。</span><span class="sxs-lookup"><span data-stu-id="a0cd6-110">Setup assembles the individual packages and performs customization and maintenance tasks during and after installation of Office on users' computers.</span></span> <span data-ttu-id="a0cd6-111">このセクションのトピックでは、Lync 2013 を展開するために Office 2013 Windows インストーラーを使用およびカスタマイズする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="a0cd6-111">The topics in this section describe how to use and customize the Office 2013 Windows Installer to deploy Lync 2013.</span></span>

  - <span data-ttu-id="a0cd6-112">**Office 2013 クイック実行**は、office セットアップファイルを Microsoft 365 管理センターからユーザーにストリームするインストールプログラムです。</span><span class="sxs-lookup"><span data-stu-id="a0cd6-112">**Office 2013 Click-to-Run** is an installation program that streams Office setup files to the user from the Microsoft 365 admin center.</span></span> <span data-ttu-id="a0cd6-113">管理者は、クイック実行用の Office 展開ツールを使用して、インストールをカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="a0cd6-113">Administrators can customize installation by using the Office Deployment Tool for Click-to-Run.</span></span> <span data-ttu-id="a0cd6-114">Office 2013 クイック実行は、主に Microsoft Office 365 環境で使用されるため、このセクションではこのインストール方法については詳しく説明しません。</span><span class="sxs-lookup"><span data-stu-id="a0cd6-114">Because Office 2013 Click-to-Run is primarily used in the Microsoft Office 365 environment, this installation method is not described in detail in this section.</span></span> <span data-ttu-id="a0cd6-115">クイック実行インストールの使用およびカスタマイズの詳細については、「Office 2013 リソースキット」のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a0cd6-115">Detailed information about using and customizing Click-to-Run installation is available in the Office 2013 Resource Kit documentation.</span></span> <span data-ttu-id="a0cd6-116">管理者は、Office 2013 クイック実行プログラムおよび言語ソースファイルを社内の場所にダウンロードすることもできます。これは、企業のセキュリティ要件により、ネットワーク上の需要を最小限に抑えたり、ユーザーがインターネットからソフトウェアをインストールしたりできないようにする場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="a0cd6-116">Administrators can also download the Office 2013 Click-to-Run program and language source files to an on-premises location, which is useful when you want to minimize the demand on the network or prevent users from installing software from the Internet because of corporate security requirements.</span></span>

<span data-ttu-id="a0cd6-117">このセクションのトピックでは、Office 2013 MSI ベースのインストーラーを使用してクライアントを展開する方法に重点を置いて説明します。</span><span class="sxs-lookup"><span data-stu-id="a0cd6-117">The topics in this section focus on how to deploy clients by using the Office 2013 MSI-based installer.</span></span> <span data-ttu-id="a0cd6-118">主な参照は、Office 2013 リソースキットのドキュメントであり、インフラストラクチャの準備、セットアップのカスタマイズ、および Office 2013 の展開方法について詳しく説明されています。</span><span class="sxs-lookup"><span data-stu-id="a0cd6-118">Your primary reference should be the Office 2013 Resource Kit documentation, which describes in detail how to prepare your infrastructure, customize setup, and deploy Office 2013.</span></span> <span data-ttu-id="a0cd6-119">ただし、Lync 2013 に固有の展開に関する考慮事項については、このセクションのトピックと一緒に Office ドキュメントを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a0cd6-119">However, you should use the Office documentation in conjunction with topics in this section, which point out deployment considerations that are specific to Lync 2013.</span></span>

<div>


> [!NOTE]  
> <UL>
> <LI>
> <P><span data-ttu-id="a0cd6-120">Outlook メッセージングおよびコラボレーションクライアント内から会議管理をサポートする Lync 2013 用オンラインミーティングアドインは、Lync 2013 と共に自動的にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="a0cd6-120">The Online Meeting Add-in for Lync 2013, which supports meeting management from within the Outlook messaging and collaboration client, installs automatically with Lync 2013.</span></span></P>
> <LI>
> <P><span data-ttu-id="a0cd6-121">Office 2013 セットアッププログラムを実行しても、以前のバージョンの Lync または Office Communicator はアンインストールされません。</span><span class="sxs-lookup"><span data-stu-id="a0cd6-121">The Office 2013 setup program does not uninstall previous versions of Lync or Office Communicator.</span></span> <span data-ttu-id="a0cd6-122">Lync 2013 クライアントは、他の Lync または Office Communicator クライアントと共存してインストールします。</span><span class="sxs-lookup"><span data-stu-id="a0cd6-122">The Lync 2013 client installs side-by-side with other Lync or Office Communicator clients</span></span></P></LI></UL>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="a0cd6-123">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="a0cd6-123">In This Section</span></span>

  - [<span data-ttu-id="a0cd6-124">Lync Server 2013 でのクライアントインストールのカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="a0cd6-124">Customizing client installation in Lync Server 2013</span></span>](lync-server-2013-customizing-client-installation.md)

  - [<span data-ttu-id="a0cd6-125">Lync Server 2013 での Lync の動作とユーザーインターフェイスのカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="a0cd6-125">Customizing Lync behavior and the user interface in Lync Server 2013</span></span>](lync-server-2013-customizing-lync-behavior-and-the-user-interface.md)

  - [<span data-ttu-id="a0cd6-126">Lync Server 2013 でのオンラインミーティングアドインのカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="a0cd6-126">Customizing the Online Meeting Add-in in Lync Server 2013</span></span>](lync-server-2013-customizing-the-online-meeting-add-in.md)

  - [<span data-ttu-id="a0cd6-127">Lync Server 2013 での会議参加ページの構成</span><span class="sxs-lookup"><span data-stu-id="a0cd6-127">Configuring the meeting join page in Lync Server 2013</span></span>](lync-server-2013-configuring-the-meeting-join-page.md)

  - [<span data-ttu-id="a0cd6-128">Lync Server 2013 でサポートされているクライアントバージョンを構成する</span><span class="sxs-lookup"><span data-stu-id="a0cd6-128">Configuring supported client versions in Lync Server 2013</span></span>](lync-server-2013-configuring-supported-client-versions.md)

  - [<span data-ttu-id="a0cd6-129">Lync Server 2013 での拡張プレゼンスプライバシーモードの構成</span><span class="sxs-lookup"><span data-stu-id="a0cd6-129">Configuring enhanced presence privacy mode in Lync Server 2013</span></span>](lync-server-2013-configuring-enhanced-presence-privacy-mode.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

