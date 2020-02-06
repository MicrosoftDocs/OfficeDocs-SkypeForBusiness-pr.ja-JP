---
title: Skype for Business Server で管理ツールをインストールする
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: '概要: Skype for Business Server のインストールに必要な管理ツールをインストールする方法について説明します。 Skype for Business Server の無料トライアルは、次https://www.microsoft.com/evalcenter/evaluate-skype-for-business-serverの Microsoft 評価センターからダウンロードしてください。'
ms.openlocfilehash: 3abf2eb35a4593f25db75e175f3cd30fdf49e21b
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41790175"
---
# <a name="install-administrative-tools-in-skype-for-business-server"></a><span data-ttu-id="72b5d-104">Skype for Business Server で管理ツールをインストールする</span><span class="sxs-lookup"><span data-stu-id="72b5d-104">Install administrative tools in Skype for Business Server</span></span>
 
<span data-ttu-id="72b5d-105">**概要:** Skype for Business Server のインストールに必要な管理ツールをインストールする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="72b5d-105">**Summary:** Learn how to install the administrative tools required for an installation of Skype for Business Server.</span></span> <span data-ttu-id="72b5d-106">Skype for Business Server の無料トライアルは、次[https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)の Microsoft 評価センターからダウンロードしてください。</span><span class="sxs-lookup"><span data-stu-id="72b5d-106">Download a free trial of Skype for Business Server from the Microsoft Evaluation center at: [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span></span>
  
<span data-ttu-id="72b5d-107">管理ツールには、トポロジビルダーとコントロールパネルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="72b5d-107">The administrative tools include Topology Builder and the Control Panel.</span></span> <span data-ttu-id="72b5d-108">Skype for Business Server でサポートされている Windows OS バージョンを実行している場合は、トポロジまたは64ビット管理ワークステーションの少なくとも1つのサーバーに管理ツールをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="72b5d-108">The administrative tools must be installed on at least one server in the topology or a 64-bit management workstation running a Windows OS version that is supported for Skype for Business Server.</span></span> <span data-ttu-id="72b5d-109">手順 1 ～ 5 は任意の順序で実行できます。</span><span class="sxs-lookup"><span data-stu-id="72b5d-109">You can do steps 1 through 5 in any order.</span></span> <span data-ttu-id="72b5d-110">ただし、手順 6、7、および 8 は、手順 1 ～ 5 の後に、図の順序で実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="72b5d-110">However, you must do steps 6, 7, and 8 in order, and after steps 1 through 5, as outlined in the diagram.</span></span> <span data-ttu-id="72b5d-111">管理ツールのインストール手順は 3/8 です。</span><span class="sxs-lookup"><span data-stu-id="72b5d-111">Installing the administrative tools is step 3 of 8.</span></span>
  
![概要図](../../media/d856afe8-4758-432f-bc45-e1956016419a.png)
  
## <a name="install-skype-for-business-server-administrative-tools"></a><span data-ttu-id="72b5d-113">Skype for Business Server 管理ツールをインストールする</span><span class="sxs-lookup"><span data-stu-id="72b5d-113">Install Skype for Business Server administrative tools</span></span>

<span data-ttu-id="72b5d-114">Skype for Business Server のインストールメディアには、柔軟なエクスペリエンスが用意されています。</span><span class="sxs-lookup"><span data-stu-id="72b5d-114">The installation media for Skype for Business Server provides a flexible experience.</span></span> <span data-ttu-id="72b5d-115">Setup.exe を初めて実行するときにインストールされるツールは、Skype for Business Server 展開ウィザードと Skype for Business Server 管理シェルだけです。</span><span class="sxs-lookup"><span data-stu-id="72b5d-115">When you first run Setup.exe, the only tools installed are the Skype for Business Server Deployment Wizard and the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="72b5d-116">コアコンポーネントと呼ばれるこれら2つのツールを使用することで、インストールプロセスを続行できますが、Skype for Business Server 環境全体の主要機能は提供されません。</span><span class="sxs-lookup"><span data-stu-id="72b5d-116">By using these two tools, known as Core Components, you can continue with the installation process, but they do not provide primary functionality for the overall Skype for Business Server environment.</span></span> <span data-ttu-id="72b5d-117">展開ウィザードはコア コンポーネントのインストール後に自動で起動されます。</span><span class="sxs-lookup"><span data-stu-id="72b5d-117">The Deployment Wizard launches automatically after you install the Core Components.</span></span> <span data-ttu-id="72b5d-118">「**管理ツールをインストール**する」というタイトルの展開ウィザードのセクションでは、Skype For Business Server Topology Builder と Skype For Business Server コントロールパネルをインストールします。</span><span class="sxs-lookup"><span data-stu-id="72b5d-118">The section of the Deployment Wizard titled **Install Administrative Tools** installs Skype for Business Server Topology Builder and Skype for Business Server Control Panel.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="72b5d-119">すべての Skype for Business Server 環境には、管理ツールがインストールされているサーバーが少なくとも1つ必要です。</span><span class="sxs-lookup"><span data-stu-id="72b5d-119">Every Skype for Business Server environment must have at least one server with the administrative tools installed.</span></span> 
  
<span data-ttu-id="72b5d-120">**管理ツールのインストール**手順に関するビデオを見てください。</span><span class="sxs-lookup"><span data-stu-id="72b5d-120">Watch the video steps for **Install administrative tools**:</span></span>
  
> [!video https://www.microsoft.com/en-us/videoplayer/embed/99a5c436-963b-4eed-b423-651568c87cb1?autoplay=false]
  
### <a name="install-skype-for-business-server-administrative-tools-from-the-deployment-wizard"></a><span data-ttu-id="72b5d-121">展開ウィザードから Skype for Business Server 管理ツールをインストールする</span><span class="sxs-lookup"><span data-stu-id="72b5d-121">Install Skype for Business Server administrative tools from the Deployment Wizard</span></span>

1. <span data-ttu-id="72b5d-122">Skype for Business Server インストールメディアを挿入します。</span><span class="sxs-lookup"><span data-stu-id="72b5d-122">Insert the Skype for Business Server installation media.</span></span> <span data-ttu-id="72b5d-123">セットアップが自動で開始されない場合は、[**セットアップ**] をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="72b5d-123">If the setup does not automatically begin, double-click **Setup**.</span></span>
    
2. <span data-ttu-id="72b5d-p106">インストール メディアを実行するには、Microsoft Visual C++ が必要です。インストールするかどうかをたずねるダイアログ ボックスが表示されたら、[**はい**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="72b5d-p106">The installation media requires Microsoft Visual C++ to run. A dialog box will pop up asking if you want to install it. Click **Yes**.</span></span>
    
3. <span data-ttu-id="72b5d-127">Skype for Business Server の新機能であるスマートセットアップを使用すると、インターネットに接続して、インストールプロセス中に更新プログラムを確認することができます。</span><span class="sxs-lookup"><span data-stu-id="72b5d-127">By using Smart Setup, a new feature in Skype for Business Server, you can connect to the Internet to check for updates during the installation process.</span></span> <span data-ttu-id="72b5d-128">これにより、インストール時の製品に最新の更新プログラムを確実に適用できるため、作業がしやすくなります。</span><span class="sxs-lookup"><span data-stu-id="72b5d-128">This provides a better experience by making sure you have the most recent updates to the product at installation.</span></span> <span data-ttu-id="72b5d-129">[**インストール**] をクリックしてインストールを開始します。</span><span class="sxs-lookup"><span data-stu-id="72b5d-129">Click **Install** to begin the installation.</span></span>
    
4. <span data-ttu-id="72b5d-130">使用許諾契約書の内容をよく読んでください。同意する場合は [**使用許諾契約書に同意します**] を選択し、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="72b5d-130">Carefully review the License Agreement, and if you agree, select **I accept the terms in the license agreement**, and click **OK**.</span></span>
    
5. <span data-ttu-id="72b5d-131">Skype for Business Server のコアコンポーネントはサーバーにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="72b5d-131">The Skype for Business Server Core Components will be installed on the server.</span></span> 
    
    <span data-ttu-id="72b5d-132">コア コンポーネントは、図に示されている次のコンポーネントで構成されています。</span><span class="sxs-lookup"><span data-stu-id="72b5d-132">The Core Components consist of the following, as shown in the figure.</span></span>
    
    ![アプリの画面のコア コンポーネント](../../media/0da1d983-4c4b-4b23-a196-c3bdba4857c6.png)
  
   - <span data-ttu-id="72b5d-134">**Skype For Business Server Deployment ウィザード**Skype for Business Server のさまざまなコンポーネントをインストールするための起動パッドを提供する展開プログラム。</span><span class="sxs-lookup"><span data-stu-id="72b5d-134">**Skype for Business Server Deployment Wizard** A deployment program that provides a launch pad for installing the various components of Skype for Business Server.</span></span>
    
   - <span data-ttu-id="72b5d-135">**Skype For Business Server 管理シェル**Skype for Business Server の管理を可能にする事前構成済み PowerShell プログラム。</span><span class="sxs-lookup"><span data-stu-id="72b5d-135">**Skype for Business Server Management Shell** A preconfigured PowerShell program that allows for administration of Skype for Business Server.</span></span>
    
     <span data-ttu-id="72b5d-136">コアコンポーネントのインストールが完了すると、図に示すように、Skype for Business Server Deployment ウィザードが自動的に起動します。</span><span class="sxs-lookup"><span data-stu-id="72b5d-136">Once the installation of the Core Components is complete, the Skype for Business Server Deployment Wizard will automatically launch, as shown in the figure.</span></span> 
    
     ![Skype for Business Server 展開ウィザード](../../media/310c3437-83f9-48fa-a1e1-9fd09009fe31.png)
  
6. <span data-ttu-id="72b5d-138">コアコンポーネントに加えて、環境内の少なくとも1台のサーバーに Skype for Business Server Topology Builder と Skype for Business Server コントロールパネルをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="72b5d-138">In addition to the Core Components, you will also need to install Skype for Business Server Topology Builder and Skype for Business Server Control Panel on at least one server in the environment.</span></span> <span data-ttu-id="72b5d-139">展開ウィザードの [**管理ツールのインストール**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="72b5d-139">Click **Install Administrative Tools** on the Deployment Wizard.</span></span>
    
7. <span data-ttu-id="72b5d-140">[**次へ**] をクリックして、インストールを開始します。</span><span class="sxs-lookup"><span data-stu-id="72b5d-140">Click **Next** to begin the installation.</span></span>
    
8. <span data-ttu-id="72b5d-p109">インストールが完了したら、[**完了**] をクリックします。これで、管理ツールがサーバーに追加されました。図に例を示します。</span><span class="sxs-lookup"><span data-stu-id="72b5d-p109">Once the installation has completed, click **Finish**. The administrative tools are now added to the server, as shown in the figure.</span></span>
    
    ![Skype for Business Server 管理ツール](../../media/760873dd-9c87-4efb-bf98-7162d876fd18.png)
  
   - <span data-ttu-id="72b5d-144">**Skype For Business Server トポロジビルダー**トポロジを構築、展開、管理するために使用されるプログラム。</span><span class="sxs-lookup"><span data-stu-id="72b5d-144">**Skype for Business Server Topology Builder** A program used to build, deploy, and manage topologies.</span></span>
    
   - <span data-ttu-id="72b5d-145">**Skype For Business Server コントロールパネル**インストールを管理するために使用されるプログラム。</span><span class="sxs-lookup"><span data-stu-id="72b5d-145">**Skype for Business Server Control Panel** A program used to administer the installation.</span></span>
    

