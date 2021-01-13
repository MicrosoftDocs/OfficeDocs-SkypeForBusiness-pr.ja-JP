---
title: Skype for Business Server に管理ツールをインストールする
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 7/14/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 52ee7da4-59ba-499a-a105-d93fa9941334
description: '概要: Skype for Business Server のインストールに必要な管理ツールをインストールする方法について説明します。 Microsoft Evaluation Center から Skype for Business Server の無料試用版を次の場所からダウンロードします https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server 。'
ms.openlocfilehash: ab3e64ae5d330c5b24eff7c23172b1141ff75527
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812107"
---
# <a name="install-administrative-tools-in-skype-for-business-server"></a><span data-ttu-id="b7cc7-104">Skype for Business Server に管理ツールをインストールする</span><span class="sxs-lookup"><span data-stu-id="b7cc7-104">Install administrative tools in Skype for Business Server</span></span>
 
<span data-ttu-id="b7cc7-105">**概要:** Skype for Business Server のインストールに必要な管理ツールをインストールする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="b7cc7-105">**Summary:** Learn how to install the administrative tools required for an installation of Skype for Business Server.</span></span> <span data-ttu-id="b7cc7-106">Microsoft Evaluation Center から Skype for Business Server の無料試用版を次の場所からダウンロードします [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server) 。</span><span class="sxs-lookup"><span data-stu-id="b7cc7-106">Download a free trial of Skype for Business Server from the Microsoft Evaluation center at: [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span></span>
  
<span data-ttu-id="b7cc7-107">管理ツールには、トポロジ ビルダーとコントロール パネルが含まれます。</span><span class="sxs-lookup"><span data-stu-id="b7cc7-107">The administrative tools include Topology Builder and the Control Panel.</span></span> <span data-ttu-id="b7cc7-108">管理ツールは、トポロジ内の少なくとも 1 台のサーバー、または Skype for Business Server でサポートされている Windows OS バージョンを実行している 64 ビットの管理ワークステーションにインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b7cc7-108">The administrative tools must be installed on at least one server in the topology or a 64-bit management workstation running a Windows OS version that is supported for Skype for Business Server.</span></span> <span data-ttu-id="b7cc7-109">手順 1. ~ 5. は任意の順序で実行できます。</span><span class="sxs-lookup"><span data-stu-id="b7cc7-109">You can do steps 1 through 5 in any order.</span></span> <span data-ttu-id="b7cc7-110">ただし、手順 6、7、および 8 を順番に実行し、図に示されている手順 1 ~ 5 の後に実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b7cc7-110">However, you must do steps 6, 7, and 8 in order, and after steps 1 through 5, as outlined in the diagram.</span></span> <span data-ttu-id="b7cc7-111">管理ツールのインストールは、手順 3/8 です。</span><span class="sxs-lookup"><span data-stu-id="b7cc7-111">Installing the administrative tools is step 3 of 8.</span></span>
  
![概要図](../../media/d856afe8-4758-432f-bc45-e1956016419a.png)
  
## <a name="install-skype-for-business-server-administrative-tools"></a><span data-ttu-id="b7cc7-113">Skype for Business Server 管理ツールのインストール</span><span class="sxs-lookup"><span data-stu-id="b7cc7-113">Install Skype for Business Server administrative tools</span></span>

<span data-ttu-id="b7cc7-114">Skype for Business Server のインストール メディアは、柔軟なエクスペリエンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="b7cc7-114">The installation media for Skype for Business Server provides a flexible experience.</span></span> <span data-ttu-id="b7cc7-115">最初にインストールSetup.exeインストールされるツールは、Skype for Business Server 展開ウィザードと Skype for Business Server 管理シェルのみです。</span><span class="sxs-lookup"><span data-stu-id="b7cc7-115">When you first run Setup.exe, the only tools installed are the Skype for Business Server Deployment Wizard and the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="b7cc7-116">コア コンポーネントと呼ばれるこれら 2 つのツールを使用すると、インストール プロセスを続行できますが、Skype for Business Server 環境全体の主要な機能は提供されません。</span><span class="sxs-lookup"><span data-stu-id="b7cc7-116">By using these two tools, known as Core Components, you can continue with the installation process, but they do not provide primary functionality for the overall Skype for Business Server environment.</span></span> <span data-ttu-id="b7cc7-117">コア コンポーネントをインストールすると、展開ウィザードが自動的に起動します。</span><span class="sxs-lookup"><span data-stu-id="b7cc7-117">The Deployment Wizard launches automatically after you install the Core Components.</span></span> <span data-ttu-id="b7cc7-118">展開ウィザードの 「管理ツールのインストール」というタイトルのセクションでは、Skype for Business Server トポロジ ビルダーと Skype for Business Server コントロール パネルをインストールします。</span><span class="sxs-lookup"><span data-stu-id="b7cc7-118">The section of the Deployment Wizard titled **Install Administrative Tools** installs Skype for Business Server Topology Builder and Skype for Business Server Control Panel.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="b7cc7-119">すべての Skype for Business Server 環境には、管理ツールがインストールされたサーバーが少なくとも 1 つ必要です。</span><span class="sxs-lookup"><span data-stu-id="b7cc7-119">Every Skype for Business Server environment must have at least one server with the administrative tools installed.</span></span> 
  
<span data-ttu-id="b7cc7-120">管理ツールのインストールに関する **ビデオの手順をご覧ください**。</span><span class="sxs-lookup"><span data-stu-id="b7cc7-120">Watch the video steps for **Install administrative tools**:</span></span>
  
> [!video https://www.microsoft.com/videoplayer/embed/99a5c436-963b-4eed-b423-651568c87cb1?autoplay=false]
  
### <a name="install-skype-for-business-server-administrative-tools-from-the-deployment-wizard"></a><span data-ttu-id="b7cc7-121">展開ウィザードから Skype for Business Server 管理ツールをインストールする</span><span class="sxs-lookup"><span data-stu-id="b7cc7-121">Install Skype for Business Server administrative tools from the Deployment Wizard</span></span>

1. <span data-ttu-id="b7cc7-122">Skype for Business Server インストール メディアを挿入します。</span><span class="sxs-lookup"><span data-stu-id="b7cc7-122">Insert the Skype for Business Server installation media.</span></span> <span data-ttu-id="b7cc7-123">セットアップが自動的に開始されない場合は、[セットアップ] をダブルクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="b7cc7-123">If the setup does not automatically begin, double-click **Setup**.</span></span>
    
2. <span data-ttu-id="b7cc7-124">インストール メディアを実行するには、Microsoft Visual C++ が必要です。</span><span class="sxs-lookup"><span data-stu-id="b7cc7-124">The installation media requires Microsoft Visual C++ to run.</span></span> <span data-ttu-id="b7cc7-125">インストールを求めるダイアログ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b7cc7-125">A dialog box will pop up asking if you want to install it.</span></span> <span data-ttu-id="b7cc7-126">[**はい**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b7cc7-126">Click **Yes**.</span></span>
    
3. <span data-ttu-id="b7cc7-127">Skype for Business Server の新機能であるスマート セットアップを使用すると、インターネットに接続してインストール プロセス中に更新プログラムを確認できます。</span><span class="sxs-lookup"><span data-stu-id="b7cc7-127">By using Smart Setup, a new feature in Skype for Business Server, you can connect to the Internet to check for updates during the installation process.</span></span> <span data-ttu-id="b7cc7-128">これにより、インストール時に製品に対する最新の更新プログラムが確実に適用され、エクスペリエンスが向上します。</span><span class="sxs-lookup"><span data-stu-id="b7cc7-128">This provides a better experience by making sure you have the most recent updates to the product at installation.</span></span> <span data-ttu-id="b7cc7-129">**[インストール]** をクリックして、インストールを開始します。</span><span class="sxs-lookup"><span data-stu-id="b7cc7-129">Click **Install** to begin the installation.</span></span>
    
4. <span data-ttu-id="b7cc7-130">使用許諾契約書を慎重に確認し、同意する場合は、[使用許諾契約書に同意します] を選択し **、[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b7cc7-130">Carefully review the License Agreement, and if you agree, select **I accept the terms in the license agreement**, and click **OK**.</span></span>
    
5. <span data-ttu-id="b7cc7-131">Skype for Business Server コア コンポーネントがサーバーにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="b7cc7-131">The Skype for Business Server Core Components will be installed on the server.</span></span> 
    
    <span data-ttu-id="b7cc7-132">図に示すように、コア コンポーネントは次の要素で構成されます。</span><span class="sxs-lookup"><span data-stu-id="b7cc7-132">The Core Components consist of the following, as shown in the figure.</span></span>
    
    ![[アプリ] 画面のコア コンポーネント。](../../media/0da1d983-4c4b-4b23-a196-c3bdba4857c6.png)
  
   - <span data-ttu-id="b7cc7-134">**Skype for Business Server 展開ウィザード** Skype for Business Server のさまざまなコンポーネントをインストールする起動パッドを提供する展開プログラム。</span><span class="sxs-lookup"><span data-stu-id="b7cc7-134">**Skype for Business Server Deployment Wizard** A deployment program that provides a launch pad for installing the various components of Skype for Business Server.</span></span>
    
   - <span data-ttu-id="b7cc7-135">**Skype for Business Server 管理シェル** Skype for Business Server の管理を可能にする事前構成済みの PowerShell プログラム。</span><span class="sxs-lookup"><span data-stu-id="b7cc7-135">**Skype for Business Server Management Shell** A preconfigured PowerShell program that allows for administration of Skype for Business Server.</span></span>
    
     <span data-ttu-id="b7cc7-136">コア コンポーネントのインストールが完了すると、次の図に示すように、Skype for Business Server 展開ウィザードが自動的に起動します。</span><span class="sxs-lookup"><span data-stu-id="b7cc7-136">Once the installation of the Core Components is complete, the Skype for Business Server Deployment Wizard will automatically launch, as shown in the figure.</span></span> 
    
     ![Skype for Business Server 展開ウィザード](../../media/310c3437-83f9-48fa-a1e1-9fd09009fe31.png)
  
6. <span data-ttu-id="b7cc7-138">コア コンポーネントに加えて、環境内の少なくとも 1 つのサーバーに Skype for Business Server トポロジ ビルダーと Skype for Business Server コントロール パネルをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b7cc7-138">In addition to the Core Components, you will also need to install Skype for Business Server Topology Builder and Skype for Business Server Control Panel on at least one server in the environment.</span></span> <span data-ttu-id="b7cc7-139">展開 **ウィザードで [管理ツールの** インストール] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b7cc7-139">Click **Install Administrative Tools** on the Deployment Wizard.</span></span>
    
7. <span data-ttu-id="b7cc7-140">[**次へ**] をクリックして、インストールを開始します。</span><span class="sxs-lookup"><span data-stu-id="b7cc7-140">Click **Next** to begin the installation.</span></span>
    
8. <span data-ttu-id="b7cc7-141">インストールが完了したら、[完了] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="b7cc7-141">Once the installation has completed, click **Finish**.</span></span> <span data-ttu-id="b7cc7-142">次の図に示すように、管理ツールがサーバーに追加されます。</span><span class="sxs-lookup"><span data-stu-id="b7cc7-142">The administrative tools are now added to the server, as shown in the figure.</span></span>
    
    ![Skype for Business Server 管理ツール](../../media/760873dd-9c87-4efb-bf98-7162d876fd18.png)
  
   - <span data-ttu-id="b7cc7-144">**Skype for Business Server トポロジ ビルダー** トポロジの構築、展開、および管理に使用するプログラム。</span><span class="sxs-lookup"><span data-stu-id="b7cc7-144">**Skype for Business Server Topology Builder** A program used to build, deploy, and manage topologies.</span></span>
    
   - <span data-ttu-id="b7cc7-145">**Skype for Business Server コントロール パネル** インストールを管理するために使用するプログラム。</span><span class="sxs-lookup"><span data-stu-id="b7cc7-145">**Skype for Business Server Control Panel** A program used to administer the installation.</span></span>
    

