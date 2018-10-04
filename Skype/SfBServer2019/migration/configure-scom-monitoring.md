---
title: SCOM で監視を構成します。
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: に移行した後 Microsoft Skype ビジネス サーバー 2019 の System Center Operations Manager を使用するサーバー 2019 のビジネス用の Skype を構成するのには、いくつかのタスクを完了する必要があります。
ms.openlocfilehash: c54038bc89c62a9911e684e451a66f4f12a23124
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/04/2018
ms.locfileid: "25373743"
---
# <a name="configure-scom-monitoring"></a><span data-ttu-id="ae929-103">SCOM で監視を構成します。</span><span class="sxs-lookup"><span data-stu-id="ae929-103">Configure SCOM monitoring</span></span>

<span data-ttu-id="ae929-104">に移行した後 Skype ビジネス サーバー 2019 の System Center Operations Manager を使用するサーバー 2019 のビジネス用の Skype を構成するのには、いくつかのタスクを完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ae929-104">After migrating to Skype for Business Server 2019, you must complete a few tasks to configure Skype for Business Server 2019 to work with System Center Operations Manager.</span></span>
  
- <span data-ttu-id="ae929-105">中央の検出ロジックを管理することを選択するサーバーに更新プログラムを適用します。</span><span class="sxs-lookup"><span data-stu-id="ae929-105">Apply updates to a server elected to manage the central discovery logic.</span></span>
    
- <span data-ttu-id="ae929-106">中央の検索候補のサーバーのレジストリ キーを更新します。</span><span class="sxs-lookup"><span data-stu-id="ae929-106">Update the central discovery candidate server registry key.</span></span>
    
- <span data-ttu-id="ae929-107">候補の中心的な探索ノードを上書きする、プライマリの System Center Operations Manager 管理サーバーを構成します。</span><span class="sxs-lookup"><span data-stu-id="ae929-107">Configure your primary System Center Operations Manager management server to override the candidate central discovery node.</span></span>
    
<span data-ttu-id="ae929-108">これらのタスクを実行するための手順が記載されています。</span><span class="sxs-lookup"><span data-stu-id="ae929-108">Instructions for carrying out each of these tasks are provided below.</span></span>
  
### <a name="apply-updates-to-a-server-elected-to-manage-the-central-discovery-logic"></a><span data-ttu-id="ae929-109">中央の検出ロジックを管理することを選択するサーバーに更新プログラムを適用します。</span><span class="sxs-lookup"><span data-stu-id="ae929-109">Apply updates to a server elected to manage the central discovery logic.</span></span>

1. <span data-ttu-id="ae929-110">System Center Operations Manager エージェントのファイルがインストールされ、候補探索ノードとして構成されているサーバーを選択します。</span><span class="sxs-lookup"><span data-stu-id="ae929-110">Elect a server that has the System Center Operations Manager agent files installed and is configured as a candidate discovery node.</span></span> 
    
2. <span data-ttu-id="ae929-111">このサーバーに更新プログラムを適用します。</span><span class="sxs-lookup"><span data-stu-id="ae929-111">Apply updates to this server.</span></span> <span data-ttu-id="ae929-112">[更新プログラムの適用](apply-updates.md)のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ae929-112">See the topic [Apply updates](apply-updates.md).</span></span>
    
### <a name="update-the-central-discovery-candidate-server-registry-key"></a><span data-ttu-id="ae929-113">中央の検索候補のサーバーのレジストリ キーを更新します。</span><span class="sxs-lookup"><span data-stu-id="ae929-113">Update the central discovery candidate server registry key.</span></span>

1. <span data-ttu-id="ae929-114">中央の検出ロジックを管理することを選択、サーバー上には、Windows PowerShell のコマンド ウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="ae929-114">On the server elected to manage the central discovery logic, open a Windows PowerShell command window.</span></span> 
    
2. <span data-ttu-id="ae929-115">コマンドラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="ae929-115">At the command line, type the following:</span></span>
    
   ```
   New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health"
   ```

   ```
   New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health\CentralDiscoveryCandidate"
   ```

    > [!NOTE]
    > <span data-ttu-id="ae929-116">レジストリを編集するたびに、レジストリ キーが既に存在する場合、コマンドが失敗しましたというエラーが発生するように。</span><span class="sxs-lookup"><span data-stu-id="ae929-116">Whenever you edit the registry, you may experience an error that the command failed if the registry key already exists.</span></span> <span data-ttu-id="ae929-117">この状況が発生する場合は、エラーを無視してかまいません。</span><span class="sxs-lookup"><span data-stu-id="ae929-117">If you experience this, you can safely ignore the error.</span></span> 
  
### <a name="configure-your-primary-system-center-operations-manager-management-server-to-override-the-candidate-central-discovery-watcher-node"></a><span data-ttu-id="ae929-118">候補の中心的な検出の監視ノードを上書きする、プライマリの System Center Operations Manager 管理サーバーを構成します。</span><span class="sxs-lookup"><span data-stu-id="ae929-118">Configure your primary System Center Operations Manager management server to override the candidate central discovery watcher node.</span></span>

1. <span data-ttu-id="ae929-119">System Center Operations Manager コンソールがインストールされているコンピューター、[**管理パック オブジェクト**を展開し、**オブジェクト検出**します。</span><span class="sxs-lookup"><span data-stu-id="ae929-119">On a computer where the System Center Operations Manager console has been installed, expand **Management Pack Objects** and then select **Object Discoveries**.</span></span>
    
2. <span data-ttu-id="ae929-120">[**スコープの変更**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ae929-120">Click **Change Scope**</span></span>
    
3. <span data-ttu-id="ae929-121">**管理パック オブジェクトのスコープ**] ページで、 **LS の検索候補**を選択します。</span><span class="sxs-lookup"><span data-stu-id="ae929-121">From the **Scope Management Pack Objects** page, select **LS Discovery Candidate**.</span></span>
    
4. <span data-ttu-id="ae929-122">**LS 検索候補の有効値**の前の手順で選択した候補のサーバーの名前をオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="ae929-122">Override the **LS Discovery Candidate Effective Value** to the name of the candidate server elected in the earlier procedure.</span></span> 
    
<span data-ttu-id="ae929-123">変更内容を確定するには、システム センター操作マネージャー ルートの管理サーバーの稼働状態サービスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="ae929-123">To finalize your changes, restart the health service on the System Center Operations Manager Root Management Server.</span></span>
  

