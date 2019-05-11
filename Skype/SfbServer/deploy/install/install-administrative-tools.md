---
title: Skype のビジネス サーバーの管理ツールをインストールします。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/14/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 52ee7da4-59ba-499a-a105-d93fa9941334
description: '概要では、Skype のインストールに必要なビジネス サーバーの管理ツールをインストールする方法について説明します。 ビジネスのサーバーで Microsoft の評価の中心からの Skype の無料試用版をダウンロード: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server。'
ms.openlocfilehash: cb5e1766ca4e0b7d6ad03db2004835e1a51d52cd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33891832"
---
# <a name="install-administrative-tools-in-skype-for-business-server"></a><span data-ttu-id="7aeaa-104">Skype のビジネス サーバーの管理ツールをインストールします。</span><span class="sxs-lookup"><span data-stu-id="7aeaa-104">Install administrative tools in Skype for Business Server</span></span>
 
<span data-ttu-id="7aeaa-105">**の概要:** Skype のインストールに必要なビジネス サーバーの管理ツールをインストールする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="7aeaa-105">**Summary:** Learn how to install the administrative tools required for an installation of Skype for Business Server.</span></span> <span data-ttu-id="7aeaa-106">ビジネスのサーバーで Microsoft の評価の中心からの Skype の無料試用版をダウンロード: [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)。</span><span class="sxs-lookup"><span data-stu-id="7aeaa-106">Download a free trial of Skype for Business Server from the Microsoft Evaluation center at: [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span></span>
  
<span data-ttu-id="7aeaa-107">管理ツールには、トポロジ ビルダーおよびコントロール パネルが含まれます。</span><span class="sxs-lookup"><span data-stu-id="7aeaa-107">The administrative tools include Topology Builder and the Control Panel.</span></span> <span data-ttu-id="7aeaa-108">トポロジまたは Skype ビジネス サーバーのサポートされている Windows のオペレーティング システムのバージョンを実行している 64 ビットの管理ワークステーションで少なくとも 1 つのサーバーの管理ツールをインストールしなければなりません。</span><span class="sxs-lookup"><span data-stu-id="7aeaa-108">The administrative tools must be installed on at least one server in the topology or a 64-bit management workstation running a Windows OS version that is supported for Skype for Business Server.</span></span> <span data-ttu-id="7aeaa-109">手順 1 ～ 5 は任意の順序で実行できます。</span><span class="sxs-lookup"><span data-stu-id="7aeaa-109">You can do steps 1 through 5 in any order.</span></span> <span data-ttu-id="7aeaa-110">ただし、手順 6、7、および 8 は、手順 1 ～ 5 の後に、図の順序で実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7aeaa-110">However, you must do steps 6, 7, and 8 in order, and after steps 1 through 5, as outlined in the diagram.</span></span> <span data-ttu-id="7aeaa-111">8 のステップ 3 は、管理ツールをインストールします。</span><span class="sxs-lookup"><span data-stu-id="7aeaa-111">Installing the administrative tools is step 3 of 8.</span></span>
  
![概要図](../../media/d856afe8-4758-432f-bc45-e1956016419a.png)
  
## <a name="install-skype-for-business-server-administrative-tools"></a><span data-ttu-id="7aeaa-113">Skype をビジネスのサーバー管理ツールをインストールします。</span><span class="sxs-lookup"><span data-stu-id="7aeaa-113">Install Skype for Business Server administrative tools</span></span>

<span data-ttu-id="7aeaa-114">Skype ビジネス サーバー用のインストール メディアでは、柔軟性の高いエクスペリエンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="7aeaa-114">The installation media for Skype for Business Server provides a flexible experience.</span></span> <span data-ttu-id="7aeaa-115">最初に Setup.exe を実行するときのみのツールがインストールされているビジネス サーバーの展開ウィザードの Skype とビジネスのサーバー管理シェルの Skype</span><span class="sxs-lookup"><span data-stu-id="7aeaa-115">When you first run Setup.exe, the only tools installed are the Skype for Business Server Deployment Wizard and the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="7aeaa-116">コア コンポーネントと呼ばれるこれらの 2 つのツールを使用して、インストール プロセスを続行することができますが、ビジネス サーバー環境の全体的な Skype の主要な機能は提供されません。</span><span class="sxs-lookup"><span data-stu-id="7aeaa-116">By using these two tools, known as Core Components, you can continue with the installation process, but they do not provide primary functionality for the overall Skype for Business Server environment.</span></span> <span data-ttu-id="7aeaa-117">展開ウィザードはコア コンポーネントのインストール後に自動で起動されます。</span><span class="sxs-lookup"><span data-stu-id="7aeaa-117">The Deployment Wizard launches automatically after you install the Core Components.</span></span> <span data-ttu-id="7aeaa-118">**管理ツールのインストール**を [展開ウィザード] のセクションでは、ビジネス サーバーのコントロール パネルのビジネス サーバー トポロジ ビルダーと Skype の Skype をインストールします。</span><span class="sxs-lookup"><span data-stu-id="7aeaa-118">The section of the Deployment Wizard titled **Install Administrative Tools** installs Skype for Business Server Topology Builder and Skype for Business Server Control Panel.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="7aeaa-119">ビジネス サーバー環境のすべての Skype がインストールされている管理ツールを使用して、少なくとも 1 つのサーバーが必要です。</span><span class="sxs-lookup"><span data-stu-id="7aeaa-119">Every Skype for Business Server environment must have at least one server with the administrative tools installed.</span></span> 
  
<span data-ttu-id="7aeaa-120">**管理ツールのインストール**手順に関するビデオを見てください。</span><span class="sxs-lookup"><span data-stu-id="7aeaa-120">Watch the video steps for **Install administrative tools**:</span></span>
  
> [!video https://www.microsoft.com/en-us/videoplayer/embed/99a5c436-963b-4eed-b423-651568c87cb1?autoplay=false]
  
### <a name="install-skype-for-business-server-administrative-tools-from-the-deployment-wizard"></a><span data-ttu-id="7aeaa-121">展開ウィザードからのビジネスのサーバー管理ツールの Skype をインストールします。</span><span class="sxs-lookup"><span data-stu-id="7aeaa-121">Install Skype for Business Server administrative tools from the Deployment Wizard</span></span>

1. <span data-ttu-id="7aeaa-122">Skype ビジネス サーバーのインストール メディアを挿入します。</span><span class="sxs-lookup"><span data-stu-id="7aeaa-122">Insert the Skype for Business Server installation media.</span></span> <span data-ttu-id="7aeaa-123">セットアップが自動で開始されない場合は、[**セットアップ**] をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="7aeaa-123">If the setup does not automatically begin, double-click **Setup**.</span></span>
    
2. <span data-ttu-id="7aeaa-p106">インストール メディアを実行するには、Microsoft Visual C++ が必要です。インストールするかどうかをたずねるダイアログ ボックスが表示されたら、[**はい**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7aeaa-p106">The installation media requires Microsoft Visual C++ to run. A dialog box will pop up asking if you want to install it. Click **Yes**.</span></span>
    
3. <span data-ttu-id="7aeaa-127">スマート セットアップ、ビジネス サーバー、Skype の新機能を使用して、インストール処理中に更新プログラムを確認するのにはインターネットに接続できます。</span><span class="sxs-lookup"><span data-stu-id="7aeaa-127">By using Smart Setup, a new feature in Skype for Business Server, you can connect to the Internet to check for updates during the installation process.</span></span> <span data-ttu-id="7aeaa-128">これにより、インストール時の製品に最新の更新プログラムを確実に適用できるため、作業がしやすくなります。</span><span class="sxs-lookup"><span data-stu-id="7aeaa-128">This provides a better experience by making sure you have the most recent updates to the product at installation.</span></span> <span data-ttu-id="7aeaa-129">[**インストール**] をクリックしてインストールを開始します。</span><span class="sxs-lookup"><span data-stu-id="7aeaa-129">Click **Install** to begin the installation.</span></span>
    
4. <span data-ttu-id="7aeaa-130">使用許諾契約書の内容をよく読んでください。同意する場合は [**使用許諾契約書に同意します**] を選択し、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7aeaa-130">Carefully review the License Agreement, and if you agree, select **I accept the terms in the license agreement**, and click **OK**.</span></span>
    
5. <span data-ttu-id="7aeaa-131">ビジネス サーバーのコア コンポーネントの Skype は、サーバーにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="7aeaa-131">The Skype for Business Server Core Components will be installed on the server.</span></span> 
    
    <span data-ttu-id="7aeaa-132">コア コンポーネントは、図に示されている次のコンポーネントで構成されています。</span><span class="sxs-lookup"><span data-stu-id="7aeaa-132">The Core Components consist of the following, as shown in the figure.</span></span>
    
    ![アプリの画面のコア コンポーネント](../../media/0da1d983-4c4b-4b23-a196-c3bdba4857c6.png)
  
   - <span data-ttu-id="7aeaa-134">**Skype ビジネス サーバーの展開ウィザードの**コンポーネントをインストールする、さまざまな Skype のビジネス サーバーの起動パッドを提供する導入プログラムです。</span><span class="sxs-lookup"><span data-stu-id="7aeaa-134">**Skype for Business Server Deployment Wizard** A deployment program that provides a launch pad for installing the various components of Skype for Business Server.</span></span>
    
   - <span data-ttu-id="7aeaa-135">**ビジネス サーバー管理シェルの Skype**Skype のビジネスのサーバーで管理できるようにする構成済みの PowerShell プログラムです。</span><span class="sxs-lookup"><span data-stu-id="7aeaa-135">**Skype for Business Server Management Shell** A preconfigured PowerShell program that allows for administration of Skype for Business Server.</span></span>
    
     <span data-ttu-id="7aeaa-136">コア ・ コンポーネントのインストールが完了した後、ビジネス サーバーの展開ウィザードの Skype が自動的に起動、図に示すようにします。</span><span class="sxs-lookup"><span data-stu-id="7aeaa-136">Once the installation of the Core Components is complete, the Skype for Business Server Deployment Wizard will automatically launch, as shown in the figure.</span></span> 
    
     ![Skype for Business Server 展開ウィザード](../../media/310c3437-83f9-48fa-a1e1-9fd09009fe31.png)
  
6. <span data-ttu-id="7aeaa-138">コア コンポーネントに加えて、環境内の少なくとも 1 つのサーバーで、ビジネス サーバーのコントロール パネルのビジネス サーバー トポロジ ビルダーと Skype の Skype をインストールする必要がも。</span><span class="sxs-lookup"><span data-stu-id="7aeaa-138">In addition to the Core Components, you will also need to install Skype for Business Server Topology Builder and Skype for Business Server Control Panel on at least one server in the environment.</span></span> <span data-ttu-id="7aeaa-139">展開ウィザードの [**管理ツールのインストール**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7aeaa-139">Click **Install Administrative Tools** on the Deployment Wizard.</span></span>
    
7. <span data-ttu-id="7aeaa-140">[**次へ**] をクリックして、インストールを開始します。</span><span class="sxs-lookup"><span data-stu-id="7aeaa-140">Click **Next** to begin the installation.</span></span>
    
8. <span data-ttu-id="7aeaa-p109">インストールが完了したら、[**完了**] をクリックします。これで、管理ツールがサーバーに追加されました。図に例を示します。</span><span class="sxs-lookup"><span data-stu-id="7aeaa-p109">Once the installation has completed, click **Finish**. The administrative tools are now added to the server, as shown in the figure.</span></span>
    
    ![Skype ビジネスのサーバー管理ツールの](../../media/760873dd-9c87-4efb-bf98-7162d876fd18.png)
  
   - <span data-ttu-id="7aeaa-144">**Skype ビジネス サーバー トポロジ ビルダーの**プログラムをビルド、配置、およびトポロジを管理するために使用します。</span><span class="sxs-lookup"><span data-stu-id="7aeaa-144">**Skype for Business Server Topology Builder** A program used to build, deploy, and manage topologies.</span></span>
    
   - <span data-ttu-id="7aeaa-145">**Skype ビジネス サーバーのコントロール パネルの**プログラムのインストールを管理するために使用します。</span><span class="sxs-lookup"><span data-stu-id="7aeaa-145">**Skype for Business Server Control Panel** A program used to administer the installation.</span></span>
    

