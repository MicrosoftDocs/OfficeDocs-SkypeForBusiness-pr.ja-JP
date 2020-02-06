---
title: SCOM 監視の構成
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Microsoft Skype for Business Server 2019 に移行した後は、いくつかのタスクを実行して、System Center Operations Manager で動作するように Skype for Business Server 2019 を設定する必要があります。
ms.openlocfilehash: 79398336bf372fd2ca779d2ec2ff58dc5219da61
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813805"
---
# <a name="configure-scom-monitoring"></a><span data-ttu-id="bc892-103">SCOM 監視の構成</span><span class="sxs-lookup"><span data-stu-id="bc892-103">Configure SCOM monitoring</span></span>

<span data-ttu-id="bc892-104">Skype for Business Server 2019 に移行した後は、いくつかのタスクを実行して、System Center Operations Manager で動作するように Skype for Business Server 2019 を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bc892-104">After migrating to Skype for Business Server 2019, you must complete a few tasks to configure Skype for Business Server 2019 to work with System Center Operations Manager.</span></span>
  
- <span data-ttu-id="bc892-105">セントラル検出ロジックを管理するように選択されたサーバーに更新プログラムを適用します。</span><span class="sxs-lookup"><span data-stu-id="bc892-105">Apply updates to a server elected to manage the central discovery logic.</span></span>
    
- <span data-ttu-id="bc892-106">セントラル探索候補サーバーのレジストリキーを更新します。</span><span class="sxs-lookup"><span data-stu-id="bc892-106">Update the central discovery candidate server registry key.</span></span>
    
- <span data-ttu-id="bc892-107">"候補" セントラル探索ノードを上書きするように、プライマリ System Center Operations Manager management サーバーを構成します。</span><span class="sxs-lookup"><span data-stu-id="bc892-107">Configure your primary System Center Operations Manager management server to override the candidate central discovery node.</span></span>
    
<span data-ttu-id="bc892-108">これらの各タスクを実行する手順については、以下で説明します。</span><span class="sxs-lookup"><span data-stu-id="bc892-108">Instructions for carrying out each of these tasks are provided below.</span></span>
  
### <a name="apply-updates-to-a-server-elected-to-manage-the-central-discovery-logic"></a><span data-ttu-id="bc892-109">セントラル検出ロジックを管理するように選択されたサーバーに更新プログラムを適用します。</span><span class="sxs-lookup"><span data-stu-id="bc892-109">Apply updates to a server elected to manage the central discovery logic.</span></span>

1. <span data-ttu-id="bc892-110">System Center Operations Manager エージェントファイルがインストールされ、候補探索ノードとして構成されているサーバーを選びます。</span><span class="sxs-lookup"><span data-stu-id="bc892-110">Elect a server that has the System Center Operations Manager agent files installed and is configured as a candidate discovery node.</span></span> 
    
2. <span data-ttu-id="bc892-111">このサーバーに更新プログラムを適用します。</span><span class="sxs-lookup"><span data-stu-id="bc892-111">Apply updates to this server.</span></span> <span data-ttu-id="bc892-112">「[更新プログラムを適用](apply-updates.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bc892-112">See the topic [Apply updates](apply-updates.md).</span></span>
    
### <a name="update-the-central-discovery-candidate-server-registry-key"></a><span data-ttu-id="bc892-113">セントラル探索候補サーバーのレジストリキーを更新します。</span><span class="sxs-lookup"><span data-stu-id="bc892-113">Update the central discovery candidate server registry key.</span></span>

1. <span data-ttu-id="bc892-114">サーバー上でセントラル検出ロジックを管理することを選択した場合は、Windows PowerShell コマンドウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="bc892-114">On the server elected to manage the central discovery logic, open a Windows PowerShell command window.</span></span> 
    
2. <span data-ttu-id="bc892-115">コマンドラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="bc892-115">At the command line, type the following:</span></span>
    
   ```PowerShell
   New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health"
   ```

   ```PowerShell
   New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health\CentralDiscoveryCandidate"
   ```

    > [!NOTE]
    > <span data-ttu-id="bc892-116">レジストリを編集すると、レジストリキーが既に存在する場合に、コマンドが失敗するというエラーが発生する場合があります。</span><span class="sxs-lookup"><span data-stu-id="bc892-116">Whenever you edit the registry, you may experience an error that the command failed if the registry key already exists.</span></span> <span data-ttu-id="bc892-117">この問題が発生した場合は、エラーを無視しても問題ありません。</span><span class="sxs-lookup"><span data-stu-id="bc892-117">If you experience this, you can safely ignore the error.</span></span> 
  
### <a name="configure-your-primary-system-center-operations-manager-management-server-to-override-the-candidate-central-discovery-watcher-node"></a><span data-ttu-id="bc892-118">主要な System Center Operations Manager management server を構成して、[セントラル探索の候補となるサービスの管理者ノードを上書きする。</span><span class="sxs-lookup"><span data-stu-id="bc892-118">Configure your primary System Center Operations Manager management server to override the candidate central discovery watcher node.</span></span>

1. <span data-ttu-id="bc892-119">System Center Operations Manager コンソールがインストールされているコンピューターで、[**管理パックのオブジェクト**] を展開し、[**オブジェクト**検出] を選択します。</span><span class="sxs-lookup"><span data-stu-id="bc892-119">On a computer where the System Center Operations Manager console has been installed, expand **Management Pack Objects** and then select **Object Discoveries**.</span></span>
    
2. <span data-ttu-id="bc892-120">[**範囲の変更**] をクリックする</span><span class="sxs-lookup"><span data-stu-id="bc892-120">Click **Change Scope**</span></span>
    
3. <span data-ttu-id="bc892-121">[**スコープ管理パックのオブジェクト**] ページで、[ **LS 検出候補**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="bc892-121">From the **Scope Management Pack Objects** page, select **LS Discovery Candidate**.</span></span>
    
4. <span data-ttu-id="bc892-122">**LS 検出候補の有効値**を、前の手順で選択した候補サーバーの名前に上書きします。</span><span class="sxs-lookup"><span data-stu-id="bc892-122">Override the **LS Discovery Candidate Effective Value** to the name of the candidate server elected in the earlier procedure.</span></span> 
    
<span data-ttu-id="bc892-123">変更を完了するには、System Center Operations Manager ルート管理サーバーで正常性サービスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="bc892-123">To finalize your changes, restart the health service on the System Center Operations Manager Root Management Server.</span></span>
  

