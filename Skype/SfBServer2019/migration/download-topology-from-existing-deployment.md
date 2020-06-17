---
title: 既存の展開環境からトポロジをダウンロードする
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
description: Skype for Business Server 2019 プールを作成する場合は、従来のインストールに関連付けられている中央管理ストアを使用します。 初めてトポロジ ビルダーを起動して、その後、編集セッションを行う場合、トポロジ ビルダーに現在の構成ドキュメントを読み込ませる場所を指定するようメッセージが表示されます。 トポロジが既に定義され、中央管理ストアが確立されているため、既存の展開からトポロジをダウンロードすることを選択する必要があります。 トポロジ ビルダーは、データベースを読み取り、現在の定義を取得します。
ms.openlocfilehash: 56234c24d9278c2702f4b07bd6df774bff45c387
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752849"
---
# <a name="download-topology-from-existing-deployment"></a><span data-ttu-id="53956-106">既存の展開環境からトポロジをダウンロードする</span><span class="sxs-lookup"><span data-stu-id="53956-106">Download topology from existing deployment</span></span>

<span data-ttu-id="53956-107">Skype for Business Server 2019 プールを作成する場合は、従来のインストールに関連付けられている中央管理ストアを使用します。</span><span class="sxs-lookup"><span data-stu-id="53956-107">When creating a Skype for Business Server 2019 pool, you will use the Central Management Store that is associated with the legacy installation.</span></span> <span data-ttu-id="53956-108">初めてトポロジ ビルダーを起動して、その後、編集セッションを行う場合、トポロジ ビルダーに現在の構成ドキュメントを読み込ませる場所を指定するようメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="53956-108">When you start Topology Builder on first use and subsequent edit sessions, you are prompted for the location where you want Topology Builder to load the current configuration document.</span></span> <span data-ttu-id="53956-109">トポロジが既に定義され、中央管理ストアが確立されているため、既存の展開からトポロジをダウンロードすることを選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="53956-109">Because you already have a topology defined and have established the Central Management store, you should choose to download a topology from an existing deployment.</span></span> <span data-ttu-id="53956-110">トポロジ ビルダーは、データベースを読み取り、現在の定義を取得します。</span><span class="sxs-lookup"><span data-stu-id="53956-110">Topology Builder will read the database and retrieve the current definition.</span></span> 
  
### <a name="to-download-a-topology-from-an-existing-deployment"></a><span data-ttu-id="53956-111">既存の展開環境からトポロジをダウンロードするには</span><span class="sxs-lookup"><span data-stu-id="53956-111">To download a topology from an existing deployment</span></span>

1. <span data-ttu-id="53956-112">Skype for Business Server 展開ウィザードを開きます。</span><span class="sxs-lookup"><span data-stu-id="53956-112">Open the Skype for Business Server Deployment Wizard.</span></span>
    
2. <span data-ttu-id="53956-113">[ **Skype For Business Server 2019-展開ウィザード**] ページで、[**管理ツールのインストール**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="53956-113">From the **Skype for Business Server 2019 - Deployment Wizard** page, click **Install Administrative Tools**.</span></span>
    
3. <span data-ttu-id="53956-114">トポロジビルダーを起動します。 [**スタート**]、[**すべてのプログラム**]、[ **Microsoft Skype for business Server 2019**]、[ **skype for business server トポロジビルダー**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="53956-114">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Topology Builder**.</span></span>
    
4. <span data-ttu-id="53956-115">[**既存の展開からトポロジをダウンロードする**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="53956-115">Select **Download Topology from existing deployment**.</span></span>
  
5. <span data-ttu-id="53956-116">ファイル名を選択し、redmond.tbxml ファイルの種類が既定のトポロジを保存します。</span><span class="sxs-lookup"><span data-stu-id="53956-116">Choose a file name, and save the topology with the default .tbxml file type.</span></span>
    
6. <span data-ttu-id="53956-117">[Skype for Business Server] ノードを展開して、展開に含まれるさまざまなサーバーの役割を確認します。</span><span class="sxs-lookup"><span data-stu-id="53956-117">Expand the Skype for Business Server node to reveal the various server roles in the deployment.</span></span>
    
  

