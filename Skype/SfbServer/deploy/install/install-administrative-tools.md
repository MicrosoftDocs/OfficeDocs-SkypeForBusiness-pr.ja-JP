---
title: Skype for Business Server に管理ツールをインストールする
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
description: '概要: Skype for Business Server のインストールに必要な管理ツールをインストールする方法について説明します。 次https://www.microsoft.com/evalcenter/evaluate-skype-for-business-serverの Microsoft 評価センターから、無料の Skype For business Server の試用版をダウンロードしてください。'
ms.openlocfilehash: 27cda52612eef1259017250ebcc4669e45165229
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42018268"
---
# <a name="install-administrative-tools-in-skype-for-business-server"></a><span data-ttu-id="cd087-104">Skype for Business Server に管理ツールをインストールする</span><span class="sxs-lookup"><span data-stu-id="cd087-104">Install administrative tools in Skype for Business Server</span></span>
 
<span data-ttu-id="cd087-105">**概要:** Skype for Business Server のインストールに必要な管理ツールのインストール方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="cd087-105">**Summary:** Learn how to install the administrative tools required for an installation of Skype for Business Server.</span></span> <span data-ttu-id="cd087-106">次[https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)の Microsoft 評価センターから、無料の Skype For business Server の試用版をダウンロードしてください。</span><span class="sxs-lookup"><span data-stu-id="cd087-106">Download a free trial of Skype for Business Server from the Microsoft Evaluation center at: [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span></span>
  
<span data-ttu-id="cd087-107">管理ツールには、トポロジビルダーとコントロールパネルがあります。</span><span class="sxs-lookup"><span data-stu-id="cd087-107">The administrative tools include Topology Builder and the Control Panel.</span></span> <span data-ttu-id="cd087-108">管理ツールは、トポロジ内の少なくとも1つのサーバーにインストールするか、Skype for Business Server でサポートされている Windows OS バージョンを実行している64ビットの管理ワークステーションにインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="cd087-108">The administrative tools must be installed on at least one server in the topology or a 64-bit management workstation running a Windows OS version that is supported for Skype for Business Server.</span></span> <span data-ttu-id="cd087-109">手順1から5までを任意の順序で実行できます。</span><span class="sxs-lookup"><span data-stu-id="cd087-109">You can do steps 1 through 5 in any order.</span></span> <span data-ttu-id="cd087-110">ただし、手順6、7、および8は、図に示されているように、手順 1 ~ 5 の後で実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cd087-110">However, you must do steps 6, 7, and 8 in order, and after steps 1 through 5, as outlined in the diagram.</span></span> <span data-ttu-id="cd087-111">管理ツールのインストール手順は 3/8 です。</span><span class="sxs-lookup"><span data-stu-id="cd087-111">Installing the administrative tools is step 3 of 8.</span></span>
  
![概要図](../../media/d856afe8-4758-432f-bc45-e1956016419a.png)
  
## <a name="install-skype-for-business-server-administrative-tools"></a><span data-ttu-id="cd087-113">Skype for Business Server 管理ツールのインストール</span><span class="sxs-lookup"><span data-stu-id="cd087-113">Install Skype for Business Server administrative tools</span></span>

<span data-ttu-id="cd087-114">Skype for Business Server のインストールメディアには、柔軟な環境が用意されています。</span><span class="sxs-lookup"><span data-stu-id="cd087-114">The installation media for Skype for Business Server provides a flexible experience.</span></span> <span data-ttu-id="cd087-115">Setup.exe を最初に実行したときにインストールされるツールは、Skype for Business Server 展開ウィザードと Skype for Business Server 管理シェルのみです。</span><span class="sxs-lookup"><span data-stu-id="cd087-115">When you first run Setup.exe, the only tools installed are the Skype for Business Server Deployment Wizard and the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="cd087-116">コアコンポーネントと呼ばれるこれら2つのツールを使用することにより、インストールプロセスを続行できますが、全体的な Skype for Business Server 環境の主要な機能は提供されません。</span><span class="sxs-lookup"><span data-stu-id="cd087-116">By using these two tools, known as Core Components, you can continue with the installation process, but they do not provide primary functionality for the overall Skype for Business Server environment.</span></span> <span data-ttu-id="cd087-117">展開ウィザードは、コアコンポーネントをインストールした後に自動的に起動します。</span><span class="sxs-lookup"><span data-stu-id="cd087-117">The Deployment Wizard launches automatically after you install the Core Components.</span></span> <span data-ttu-id="cd087-118">「 **Install 管理ツール**」というタイトルの展開ウィザードのセクションでは、Skype For Business Server トポロジビルダーと Skype For Business Server コントロールパネルがインストールされます。</span><span class="sxs-lookup"><span data-stu-id="cd087-118">The section of the Deployment Wizard titled **Install Administrative Tools** installs Skype for Business Server Topology Builder and Skype for Business Server Control Panel.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="cd087-119">すべての Skype for Business Server 環境には、管理ツールがインストールされた少なくとも1つのサーバーが必要です。</span><span class="sxs-lookup"><span data-stu-id="cd087-119">Every Skype for Business Server environment must have at least one server with the administrative tools installed.</span></span> 
  
<span data-ttu-id="cd087-120">**管理ツールをインストール**するためのビデオの手順をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="cd087-120">Watch the video steps for **Install administrative tools**:</span></span>
  
> [!video https://www.microsoft.com/videoplayer/embed/99a5c436-963b-4eed-b423-651568c87cb1?autoplay=false]
  
### <a name="install-skype-for-business-server-administrative-tools-from-the-deployment-wizard"></a><span data-ttu-id="cd087-121">展開ウィザードから Skype for Business Server 管理ツールをインストールする</span><span class="sxs-lookup"><span data-stu-id="cd087-121">Install Skype for Business Server administrative tools from the Deployment Wizard</span></span>

1. <span data-ttu-id="cd087-122">Skype for Business Server のインストールメディアを挿入します。</span><span class="sxs-lookup"><span data-stu-id="cd087-122">Insert the Skype for Business Server installation media.</span></span> <span data-ttu-id="cd087-123">セットアップが自動的に開始しない場合は、[**セットアップ**] をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="cd087-123">If the setup does not automatically begin, double-click **Setup**.</span></span>
    
2. <span data-ttu-id="cd087-124">インストールメディアを実行するには、Microsoft Visual C++ が必要です。</span><span class="sxs-lookup"><span data-stu-id="cd087-124">The installation media requires Microsoft Visual C++ to run.</span></span> <span data-ttu-id="cd087-125">インストールするかどうかを確認するダイアログボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="cd087-125">A dialog box will pop up asking if you want to install it.</span></span> <span data-ttu-id="cd087-126">[**はい**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cd087-126">Click **Yes**.</span></span>
    
3. <span data-ttu-id="cd087-127">Skype for Business Server の新機能であるスマートセットアップを使用すると、インストールプロセス中にインターネットに接続して更新プログラムを確認できます。</span><span class="sxs-lookup"><span data-stu-id="cd087-127">By using Smart Setup, a new feature in Skype for Business Server, you can connect to the Internet to check for updates during the installation process.</span></span> <span data-ttu-id="cd087-128">これにより、インストール時に最新の更新プログラムがインストールされていることを確認することができるようになります。</span><span class="sxs-lookup"><span data-stu-id="cd087-128">This provides a better experience by making sure you have the most recent updates to the product at installation.</span></span> <span data-ttu-id="cd087-129">**[インストール]** をクリックして、インストールを開始します。</span><span class="sxs-lookup"><span data-stu-id="cd087-129">Click **Install** to begin the installation.</span></span>
    
4. <span data-ttu-id="cd087-130">使用許諾契約書をよく読んで、同意する場合は [**使用許諾契約書に同意**します] を選択して、[ **OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cd087-130">Carefully review the License Agreement, and if you agree, select **I accept the terms in the license agreement**, and click **OK**.</span></span>
    
5. <span data-ttu-id="cd087-131">Skype for Business Server のコアコンポーネントがサーバーにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="cd087-131">The Skype for Business Server Core Components will be installed on the server.</span></span> 
    
    <span data-ttu-id="cd087-132">コアコンポーネントは、図に示すように、次の要素で構成されています。</span><span class="sxs-lookup"><span data-stu-id="cd087-132">The Core Components consist of the following, as shown in the figure.</span></span>
    
    ![アプリ画面のコアコンポーネント。](../../media/0da1d983-4c4b-4b23-a196-c3bdba4857c6.png)
  
   - <span data-ttu-id="cd087-134">**Skype For Business Server 展開ウィザード**Skype for Business Server のさまざまなコンポーネントをインストールするための起動パッドを提供する展開プログラム。</span><span class="sxs-lookup"><span data-stu-id="cd087-134">**Skype for Business Server Deployment Wizard** A deployment program that provides a launch pad for installing the various components of Skype for Business Server.</span></span>
    
   - <span data-ttu-id="cd087-135">**Skype For Business Server 管理シェル**Skype for Business Server の管理を可能にする、あらかじめ構成された PowerShell プログラム。</span><span class="sxs-lookup"><span data-stu-id="cd087-135">**Skype for Business Server Management Shell** A preconfigured PowerShell program that allows for administration of Skype for Business Server.</span></span>
    
     <span data-ttu-id="cd087-136">コアコンポーネントのインストールが完了すると、図に示すように、Skype for Business Server 展開ウィザードが自動的に起動します。</span><span class="sxs-lookup"><span data-stu-id="cd087-136">Once the installation of the Core Components is complete, the Skype for Business Server Deployment Wizard will automatically launch, as shown in the figure.</span></span> 
    
     ![Skype for Business Server 展開ウィザード](../../media/310c3437-83f9-48fa-a1e1-9fd09009fe31.png)
  
6. <span data-ttu-id="cd087-138">コアコンポーネントに加えて、Skype for Business Server トポロジビルダーと Skype for Business Server コントロールパネルを環境内の少なくとも1つのサーバーにインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="cd087-138">In addition to the Core Components, you will also need to install Skype for Business Server Topology Builder and Skype for Business Server Control Panel on at least one server in the environment.</span></span> <span data-ttu-id="cd087-139">展開ウィザードで、[**管理ツールのインストール**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cd087-139">Click **Install Administrative Tools** on the Deployment Wizard.</span></span>
    
7. <span data-ttu-id="cd087-140">[**次へ**] をクリックして、インストールを開始します。</span><span class="sxs-lookup"><span data-stu-id="cd087-140">Click **Next** to begin the installation.</span></span>
    
8. <span data-ttu-id="cd087-141">インストールが完了したら、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cd087-141">Once the installation has completed, click **Finish**.</span></span> <span data-ttu-id="cd087-142">図に示すように、管理ツールがサーバーに追加されました。</span><span class="sxs-lookup"><span data-stu-id="cd087-142">The administrative tools are now added to the server, as shown in the figure.</span></span>
    
    ![Skype for Business Server 管理ツール](../../media/760873dd-9c87-4efb-bf98-7162d876fd18.png)
  
   - <span data-ttu-id="cd087-144">**Skype For Business Server トポロジビルダー**トポロジを構築、展開、および管理するために使用されるプログラム。</span><span class="sxs-lookup"><span data-stu-id="cd087-144">**Skype for Business Server Topology Builder** A program used to build, deploy, and manage topologies.</span></span>
    
   - <span data-ttu-id="cd087-145">**Skype For Business Server コントロールパネル**インストールを管理するために使用されるプログラム。</span><span class="sxs-lookup"><span data-stu-id="cd087-145">**Skype for Business Server Control Panel** A program used to administer the installation.</span></span>
    

