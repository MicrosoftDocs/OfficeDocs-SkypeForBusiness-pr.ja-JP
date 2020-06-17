---
title: SCOM 監視の構成
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Microsoft Skype for Business Server 2019 に移行した後、いくつかのタスクを実行して、System Center Operations Manager と連携するように Skype for Business Server 2019 を構成する必要があります。
ms.openlocfilehash: ef40890cb3ac01d8223c4b9a9cd0c4712e544376
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754047"
---
# <a name="configure-scom-monitoring"></a><span data-ttu-id="9427b-103">SCOM 監視の構成</span><span class="sxs-lookup"><span data-stu-id="9427b-103">Configure SCOM monitoring</span></span>

<span data-ttu-id="9427b-104">Skype for business Server 2019 に移行した後、いくつかのタスクを実行して、System Center Operations Manager と連携するように Skype for Business Server 2019 を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9427b-104">After migrating to Skype for Business Server 2019, you must complete a few tasks to configure Skype for Business Server 2019 to work with System Center Operations Manager.</span></span>
  
- <span data-ttu-id="9427b-105">中央検出ロジックを管理するために選択したサーバーに更新プログラムを適用します。</span><span class="sxs-lookup"><span data-stu-id="9427b-105">Apply updates to a server elected to manage the central discovery logic.</span></span>
    
- <span data-ttu-id="9427b-106">中央検出候補サーバーのレジストリ キーを更新する。</span><span class="sxs-lookup"><span data-stu-id="9427b-106">Update the central discovery candidate server registry key.</span></span>
    
- <span data-ttu-id="9427b-107">プライマリの System Center Operations Manager 管理サーバーを構成して、[中央探索の候補」ノードを上書きします。</span><span class="sxs-lookup"><span data-stu-id="9427b-107">Configure your primary System Center Operations Manager management server to override the candidate central discovery node.</span></span>
    
<span data-ttu-id="9427b-108">各タスクを実行する手順を次に示します。</span><span class="sxs-lookup"><span data-stu-id="9427b-108">Instructions for carrying out each of these tasks are provided below.</span></span>
  
### <a name="apply-updates-to-a-server-elected-to-manage-the-central-discovery-logic"></a><span data-ttu-id="9427b-109">中央検出ロジックを管理するために選択したサーバーに更新プログラムを適用します。</span><span class="sxs-lookup"><span data-stu-id="9427b-109">Apply updates to a server elected to manage the central discovery logic.</span></span>

1. <span data-ttu-id="9427b-110">System Center Operations Manager エージェント ファイルがインストールされ、候補検出ノードとして構成されているサーバーを選択します。</span><span class="sxs-lookup"><span data-stu-id="9427b-110">Elect a server that has the System Center Operations Manager agent files installed and is configured as a candidate discovery node.</span></span> 
    
2. <span data-ttu-id="9427b-111">このサーバーに更新プログラムを適用します。</span><span class="sxs-lookup"><span data-stu-id="9427b-111">Apply updates to this server.</span></span> <span data-ttu-id="9427b-112">「 [Apply updates](apply-updates.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9427b-112">See the topic [Apply updates](apply-updates.md).</span></span>
    
### <a name="update-the-central-discovery-candidate-server-registry-key"></a><span data-ttu-id="9427b-113">中央検出候補サーバーのレジストリ キーを更新する。</span><span class="sxs-lookup"><span data-stu-id="9427b-113">Update the central discovery candidate server registry key.</span></span>

1. <span data-ttu-id="9427b-114">中央検出ロジックを管理することを選択したサーバーで、Windows PowerShell コマンドウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="9427b-114">On the server elected to manage the central discovery logic, open a Windows PowerShell command window.</span></span> 
    
2. <span data-ttu-id="9427b-115">コマンド ラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="9427b-115">At the command line, type the following:</span></span>
    
   ```PowerShell
   New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health"
   ```

   ```PowerShell
   New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health\CentralDiscoveryCandidate"
   ```

    > [!NOTE]
    > <span data-ttu-id="9427b-116">Whenever you edit the registry, you may experience an error that the command failed if the registry key already exists.</span><span class="sxs-lookup"><span data-stu-id="9427b-116">Whenever you edit the registry, you may experience an error that the command failed if the registry key already exists.</span></span> <span data-ttu-id="9427b-117">If you experience this, you can safely ignore the error.</span><span class="sxs-lookup"><span data-stu-id="9427b-117">If you experience this, you can safely ignore the error.</span></span> 
  
### <a name="configure-your-primary-system-center-operations-manager-management-server-to-override-the-candidate-central-discovery-watcher-node"></a><span data-ttu-id="9427b-118">プライマリの System Center Operations Manager 管理サーバーを構成して、[中央探索の候補監視ノードの候補を上書きします。</span><span class="sxs-lookup"><span data-stu-id="9427b-118">Configure your primary System Center Operations Manager management server to override the candidate central discovery watcher node.</span></span>

1. <span data-ttu-id="9427b-119">System Center Operations Manager コントロールがインストールされているコンピューターで、[**管理パック オブジェクト**] を展開し、[**オブジェクト検出**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9427b-119">On a computer where the System Center Operations Manager console has been installed, expand **Management Pack Objects** and then select **Object Discoveries**.</span></span>
    
2. <span data-ttu-id="9427b-120">[**スコープの変更**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9427b-120">Click **Change Scope**</span></span>
    
3. <span data-ttu-id="9427b-121">[**管理パック オブジェクトのスコープ設定**] ページで、[**LS Discovery Candidate**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9427b-121">From the **Scope Management Pack Objects** page, select **LS Discovery Candidate**.</span></span>
    
4. <span data-ttu-id="9427b-122">前の手順で選択した候補サーバーの名前の [**LS Discovery Candidate Effective Value**] を上書きします。</span><span class="sxs-lookup"><span data-stu-id="9427b-122">Override the **LS Discovery Candidate Effective Value** to the name of the candidate server elected in the earlier procedure.</span></span> 
    
<span data-ttu-id="9427b-123">変更を確定するには、System Center Operations Manager のルート管理サーバーで正常性サービスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="9427b-123">To finalize your changes, restart the health service on the System Center Operations Manager Root Management Server.</span></span>
  

