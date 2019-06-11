---
title: 'Lync Server 2013: Lync クライアントを展開する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploying Lync clients
ms:assetid: 3d10abf2-d484-4fa0-8f10-4a5f9dfba4f5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204827(v=OCS.15)
ms:contentKeyID: 48183925
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3bbbecc50ed88ac9b3237277ba1c991f8c1fcba2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833553"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-lync-clients-in-lync-server-2013"></a><span data-ttu-id="08d19-102">Lync Server 2013 での Lync クライアントの展開</span><span class="sxs-lookup"><span data-stu-id="08d19-102">Deploying Lync clients in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="08d19-103">_**最終更新日:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="08d19-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="08d19-104">Lync 2013 では、クライアントの展開にさまざまなアプローチが導入されています。</span><span class="sxs-lookup"><span data-stu-id="08d19-104">Lync 2013 introduces a different approach to client deployment.</span></span> <span data-ttu-id="08d19-105">以前のリリースから出発した Lync 2013 には、独自のインストーラーがありません。</span><span class="sxs-lookup"><span data-stu-id="08d19-105">In a departure from previous releases, Lync 2013 no longer has its own installer.</span></span> <span data-ttu-id="08d19-106">代わりに Lync は、Office 2013 セットアッププログラムに含まれています。</span><span class="sxs-lookup"><span data-stu-id="08d19-106">Instead, Lync is included with the Office 2013 setup program.</span></span> <span data-ttu-id="08d19-107">Lync 2013 をユーザーに展開するには、Office 2013 のインストール方法とカスタマイズツールを使用できます。</span><span class="sxs-lookup"><span data-stu-id="08d19-107">To deploy Lync 2013 to your users, you can use Office 2013 installation methods and customization tools.</span></span>

  - <span data-ttu-id="08d19-108">**Office 2013 Windows installer**は、複数の MSI ファイルで構成される windows installer ベースのインストールパッケージです。</span><span class="sxs-lookup"><span data-stu-id="08d19-108">**Office 2013 Windows Installer** is a Windows Installer-based installation package that consists of multiple MSI files.</span></span> <span data-ttu-id="08d19-109">言語に依存しないコア MSI パッケージと 1 つ以上の言語固有のパッケージが組み合わされ 1 つの完全な製品になっています。</span><span class="sxs-lookup"><span data-stu-id="08d19-109">A language-neutral core MSI package is combined with one or more language-specific packages to make a complete product.</span></span> <span data-ttu-id="08d19-110">セットアップによって個々のパッケージがアセンブルされ、ユーザーのコンピューターへの Office のインストール中およびインストール後に、カスタマイズ タスクとメンテナンス タスクが実行されます。</span><span class="sxs-lookup"><span data-stu-id="08d19-110">Setup assembles the individual packages and performs customization and maintenance tasks during and after installation of Office on users' computers.</span></span> <span data-ttu-id="08d19-111">このセクションのトピックでは、Lync 2013 を展開するために Office 2013 Windows インストーラーを使用およびカスタマイズする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="08d19-111">The topics in this section describe how to use and customize the Office 2013 Windows Installer to deploy Lync 2013.</span></span>

  - <span data-ttu-id="08d19-112">**Office 2013 クイック実行**は、office のセットアップファイルを Microsoft office 365 ポータルからユーザーにストリーミングするインストールプログラムです。</span><span class="sxs-lookup"><span data-stu-id="08d19-112">**Office 2013 Click-to-Run** is an installation program that streams Office setup files to the user from the Microsoft Office 365 portal.</span></span> <span data-ttu-id="08d19-113">管理者は、Office 展開ツールを使用してクイック実行用にインストールをカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="08d19-113">Administrators can customize installation by using the Office Deployment Tool for Click-to-Run.</span></span> <span data-ttu-id="08d19-114">Office 2013 クイック実行は主に Microsoft Office 365 環境で使用されるため、このインストール方法についてはこのセクションで詳しく説明しません。</span><span class="sxs-lookup"><span data-stu-id="08d19-114">Because Office 2013 Click-to-Run is primarily used in the Microsoft Office 365 environment, this installation method is not described in detail in this section.</span></span> <span data-ttu-id="08d19-115">クイック実行インストールの使用とカスタマイズの詳細については、「Office 2013 リソースキット」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="08d19-115">Detailed information about using and customizing Click-to-Run installation is available in the Office 2013 Resource Kit documentation.</span></span> <span data-ttu-id="08d19-116">管理者は、Office 2013 クイック実行プログラムと言語ソースファイルをオンプレミスの場所にダウンロードすることもできます。この機能は、ネットワーク上の需要を最小限に抑えたい場合や、ユーザーがインターネットからソフトウェアをインストールできないようにする場合に便利です。企業のセキュリティ要件。</span><span class="sxs-lookup"><span data-stu-id="08d19-116">Administrators can also download the Office 2013 Click-to-Run program and language source files to an on-premises location, which is useful when you want to minimize the demand on the network or prevent users from installing software from the Internet because of corporate security requirements.</span></span>

<span data-ttu-id="08d19-117">このセクションのトピックでは、Office 2013 MSI ベースのインストーラーを使用してクライアントを展開する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="08d19-117">The topics in this section focus on how to deploy clients by using the Office 2013 MSI-based installer.</span></span> <span data-ttu-id="08d19-118">主な参照は、Office 2013 リソースキットドキュメントです。ここでは、インフラストラクチャの準備、セットアップのカスタマイズ、Office 2013 の展開の方法について詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="08d19-118">Your primary reference should be the Office 2013 Resource Kit documentation, which describes in detail how to prepare your infrastructure, customize setup, and deploy Office 2013.</span></span> <span data-ttu-id="08d19-119">ただし、Office ドキュメントをこのセクションのトピックと組み合わせて使用する必要があります。このセクションでは、Lync 2013 に固有の展開に関する考慮事項について説明します。</span><span class="sxs-lookup"><span data-stu-id="08d19-119">However, you should use the Office documentation in conjunction with topics in this section, which point out deployment considerations that are specific to Lync 2013.</span></span>

<div>


> [!NOTE]  
> <UL>
> <LI>
> <P><span data-ttu-id="08d19-120">Lync 2013 用のオンライン会議アドインは、Outlook メッセージングおよびコラボレーションクライアント内からの会議管理をサポートしており、Lync 2013 と共に自動的にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="08d19-120">The Online Meeting Add-in for Lync 2013, which supports meeting management from within the Outlook messaging and collaboration client, installs automatically with Lync 2013.</span></span></P>
> <LI>
> <P><span data-ttu-id="08d19-121">Office 2013 セットアッププログラムでは、以前のバージョンの Lync や Office Communicator はアンインストールされません。</span><span class="sxs-lookup"><span data-stu-id="08d19-121">The Office 2013 setup program does not uninstall previous versions of Lync or Office Communicator.</span></span> <span data-ttu-id="08d19-122">Lync 2013 クライアントは、他の Lync または Office Communicator クライアントと並行してインストールされます。</span><span class="sxs-lookup"><span data-stu-id="08d19-122">The Lync 2013 client installs side-by-side with other Lync or Office Communicator clients</span></span></P></LI></UL>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="08d19-123">このセクション中</span><span class="sxs-lookup"><span data-stu-id="08d19-123">In This Section</span></span>

  - [<span data-ttu-id="08d19-124">Lync Server 2013 でのクライアントインストールのカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="08d19-124">Customizing client installation in Lync Server 2013</span></span>](lync-server-2013-customizing-client-installation.md)

  - [<span data-ttu-id="08d19-125">Lync Server 2013 での Lync の動作とユーザーインターフェイスのカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="08d19-125">Customizing Lync behavior and the user interface in Lync Server 2013</span></span>](lync-server-2013-customizing-lync-behavior-and-the-user-interface.md)

  - [<span data-ttu-id="08d19-126">Lync Server 2013 でのオンライン会議アドインのカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="08d19-126">Customizing the Online Meeting Add-in in Lync Server 2013</span></span>](lync-server-2013-customizing-the-online-meeting-add-in.md)

  - [<span data-ttu-id="08d19-127">Lync Server 2013 での会議参加ページの構成</span><span class="sxs-lookup"><span data-stu-id="08d19-127">Configuring the meeting join page in Lync Server 2013</span></span>](lync-server-2013-configuring-the-meeting-join-page.md)

  - [<span data-ttu-id="08d19-128">Lync Server 2013 でサポートされているクライアントバージョンを構成する</span><span class="sxs-lookup"><span data-stu-id="08d19-128">Configuring supported client versions in Lync Server 2013</span></span>](lync-server-2013-configuring-supported-client-versions.md)

  - [<span data-ttu-id="08d19-129">Lync Server 2013 で拡張プレゼンスプライバシーモードを構成する</span><span class="sxs-lookup"><span data-stu-id="08d19-129">Configuring enhanced presence privacy mode in Lync Server 2013</span></span>](lync-server-2013-configuring-enhanced-presence-privacy-mode.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

