---
title: 'Lync Server 2013: Lync Server 管理ツールのインストール'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Install Lync Server administrative tools
ms:assetid: 842b85e4-2eeb-464f-b1c1-ceb8cc04f8d5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398665(v=OCS.15)
ms:contentKeyID: 48184695
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3ded1dbdcd81c846db9f23574fa0b39efa0c33dc
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48498724"
---
# <a name="install-lync-server-2013-administrative-tools"></a><span data-ttu-id="6a3e8-102">Lync Server 2013 管理ツールのインストール</span><span class="sxs-lookup"><span data-stu-id="6a3e8-102">Install Lync Server 2013 administrative tools</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6a3e8-103">_**トピックの最終更新日:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="6a3e8-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="6a3e8-104">このトピックでは、Lync Server 2013 を展開および管理するために使用する必要がある管理ツールをインストールする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="6a3e8-104">This topic describes how to install the administrative tools you need to use to deploy and manage Lync Server 2013.</span></span> <span data-ttu-id="6a3e8-105">管理ツールは、Lync Server 2013 を実行している各サーバーに既定でインストールされます。</span><span class="sxs-lookup"><span data-stu-id="6a3e8-105">The administrative tools are installed by default on each server running Lync Server 2013.</span></span> <span data-ttu-id="6a3e8-106">また、専用の管理コンソールなど、他のコンピューター上に管理ツールをインストールすることもできます。</span><span class="sxs-lookup"><span data-stu-id="6a3e8-106">Additionally, you can install the administrative tools on other computers, such as dedicated administrative consoles.</span></span> <span data-ttu-id="6a3e8-107">Active Directory ドメインサービスの準備手順が既に完了していることを確認することにより、作成する Lync Server 2013 の展開と同じドメインまたはフォレストにあるコンピューターに管理ツールをインストールすることを強くお勧めします。これにより、そのコンピューターで管理ツールを使用してトポロジを公開することができます。</span><span class="sxs-lookup"><span data-stu-id="6a3e8-107">We strongly recommend that you install the administrative tools on a computer that is in the same domain or forest as the Lync Server 2013 deployment you are creating because by doing so you make sure that Active Directory Domain Services preparation steps are already complete, which enables you to use the administrative tools on that computer later to publish your topology.</span></span>

<span data-ttu-id="6a3e8-108">Lync Server 2013 管理ツールをインストールまたは使用する前に、インフラストラクチャ、オペレーティングシステム、ソフトウェア、および管理者の権限要件を確認してください。</span><span class="sxs-lookup"><span data-stu-id="6a3e8-108">Make sure that you review infrastructure, operating system, software, and administrator rights requirements before you install or use the Lync Server 2013 administrative tools.</span></span> <span data-ttu-id="6a3e8-109">インフラストラクチャ要件の詳細については、「 [Lync Server 2013 の管理ツールのインフラストラクチャ要件](lync-server-2013-administrative-tools-infrastructure-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6a3e8-109">For details about infrastructure requirements, see [Administrative tools infrastructure requirements in Lync Server 2013](lync-server-2013-administrative-tools-infrastructure-requirements.md).</span></span> <span data-ttu-id="6a3e8-110">Lync Server 2013 管理ツールをインストールするためのオペレーティングシステムとソフトウェアの要件の詳細については、「lync server [2013 のサーバーおよびツールのオペレーティングシステムのサポート](lync-server-2013-server-and-tools-operating-system-support.md)」、「lync [server 2013 の追加ソフトウェア要件](lync-server-2013-additional-software-requirements.md)」、および「 [lync server 2013 の追加のサーバーサポートと要件](lync-server-2013-additional-server-support-and-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6a3e8-110">For details about operating system and software requirements to install the Lync Server 2013 administrative tools, see [Server and tools operating system support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md), [Additional software requirements for Lync Server 2013](lync-server-2013-additional-software-requirements.md), and [Additional server support and requirements in Lync Server 2013](lync-server-2013-additional-server-support-and-requirements.md).</span></span> <span data-ttu-id="6a3e8-111">ツールのインストールと使用に必要なユーザー権限とアクセス許可の詳細については、「 [Lync Server 2013 のセットアップと管理に必要な管理者権限とアクセス許可](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6a3e8-111">For details about the user rights and permissions required to install and use the tools, see [Administrator rights and permissions required for setup and administration of Lync Server 2013](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="6a3e8-112">組織でインターネット インフォメーション サービス (IIS) およびすべての Web サービスをシステム ドライブ以外のドライブに配置する必要がある場合は、[セットアップ] ダイアログ ボックスで Lync Server ファイルのインストール先パスを変更できます。</span><span class="sxs-lookup"><span data-stu-id="6a3e8-112">If your organization requires that you locate Internet Information Services (IIS) and all Web Services on a drive other than the system drive, you can change the installation location path for the Lync Server files in the Setup dialog box.</span></span> <span data-ttu-id="6a3e8-113">このパスにセットアップファイル (OCSCore.msi を含む) をインストールすると、残りの Lync Server 2013 ファイルもこのドライブに展開されます。</span><span class="sxs-lookup"><span data-stu-id="6a3e8-113">If you install the Setup files to this path, including OCSCore.msi, the rest of the Lync Server 2013 files will be deployed to this drive as well.</span></span>



</div>

<div>

## <a name="to-install-the-lync-server-2013-administrative-tools"></a><span data-ttu-id="6a3e8-114">Lync Server 2013 管理ツールをインストールするには</span><span class="sxs-lookup"><span data-stu-id="6a3e8-114">To install the Lync Server 2013 administrative tools</span></span>

1.  <span data-ttu-id="6a3e8-p104">管理ツールのインストール先のコンピューターにローカル管理者 (最小要件) としてログオンします。Windows Vista または Windows 7 オペレーティング システムの標準ユーザーとしてログオンしており、ユーザー アカウント制御 (UAC) が有効になっている場合は、ローカル管理者または同等のドメイン ユーザーの名前とパスワードの入力を求められます。</span><span class="sxs-lookup"><span data-stu-id="6a3e8-p104">Log on as a local administrator (minimum requirement) to the computer where you want to install the administrative tools. If you are logged on as an a standard user on the Windows Vista or Windows 7 operating systems, and User Account Control (UAC) is enabled, you will be prompted for the local administrator or a domain equivalent user name and password.</span></span>

2.  <span data-ttu-id="6a3e8-117">コンピューターでインストールメディアを見つけ、[Setup amd64Setup.exe] をダブルクリックし \\ \\ \\ ます。</span><span class="sxs-lookup"><span data-stu-id="6a3e8-117">Locate the installation media on your computer, and then double-click \\Setup\\amd64\\Setup.exe.</span></span>

3.  <span data-ttu-id="6a3e8-118">Microsoft Visual C++ 2008 (再頒布可能) のインストールを指示されたら、[**はい**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6a3e8-118">If you are prompted to install the Microsoft Visual C++ 2008 distributable, click **Yes**.</span></span>

4.  <span data-ttu-id="6a3e8-119">[ **Microsoft Lync Server 2013 のインストール先** ] ページで、[ **OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6a3e8-119">On the **Microsoft Lync Server 2013 Installation Location** page, click **OK**.</span></span> <span data-ttu-id="6a3e8-120">ファイルを他の場所にインストールする必要がある場合は、このパスを他の場所またはドライブに変更します。</span><span class="sxs-lookup"><span data-stu-id="6a3e8-120">Change this path to another location or drive if you need to have the files installed to another location.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="6a3e8-121">インターネットインフォメーションサービス (IIS) とすべての Web サービスをシステムドライブ以外のドライブに配置する必要がある組織では、[セットアップ] ダイアログボックスで Lync Server 2013 ファイルのインストール場所のパスを変更できます。</span><span class="sxs-lookup"><span data-stu-id="6a3e8-121">If your organization requires that you locate Internet Information Services (IIS) and all Web Services on a drive other than the system drive, you can change the installation location path for the Lync Server 2013 files in the Setup dialog box.</span></span> <span data-ttu-id="6a3e8-122">このパスにセットアップファイル (OCSCore.msi を含む) をインストールすると、残りの Lync Server 2013 ファイルもこのドライブに展開されます。</span><span class="sxs-lookup"><span data-stu-id="6a3e8-122">If you install the Setup files to this path, including OCSCore.msi, the rest of the Lync Server 2013 files will be deployed to this drive too.</span></span>

    
    </div>

5.  <span data-ttu-id="6a3e8-p107">[**使用許諾契約書**] ページでライセンス条項を確認し、[**同意する**] をクリックしてから [**OK**] をクリックします。続行するにはこのステップが必要です。</span><span class="sxs-lookup"><span data-stu-id="6a3e8-p107">On the **End User License Agreement** page, review the license terms, click **I accept**, and then click **OK**. This step is required before you can continue.</span></span>

6.  <span data-ttu-id="6a3e8-125">[ **Microsoft Lync Server 2013-展開ウィザード** ] ページで、[ **管理者ツールのインストール**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6a3e8-125">On the **Microsoft Lync Server 2013 – Deployment Wizard** page, click **Install Administrator Tools**.</span></span>

7.  <span data-ttu-id="6a3e8-126">インストールが正常に完了したら、[**終了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6a3e8-126">When the installation successfully completes, click **Exit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="6a3e8-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="6a3e8-127">See Also</span></span>


[<span data-ttu-id="6a3e8-128">Lync Server 2013 管理ツールを開く</span><span class="sxs-lookup"><span data-stu-id="6a3e8-128">Open Lync Server 2013 administrative tools</span></span>](lync-server-2013-open-lync-server-administrative-tools.md)  


[<span data-ttu-id="6a3e8-129">Lync Server 2013 管理ツール</span><span class="sxs-lookup"><span data-stu-id="6a3e8-129">Lync Server 2013 administrative tools</span></span>](lync-server-2013-lync-server-administrative-tools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

