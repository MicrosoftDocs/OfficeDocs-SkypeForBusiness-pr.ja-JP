---
title: 既存の展開環境からトポロジをダウンロードする
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Skype for Business Server 2019 プールを作成する場合は、従来のインストールに関連付けられている中央管理ストアを使用します。 最初の使用時と後続の編集セッションでトポロジビルダーを起動すると、トポロジビルダーで現在の構成ドキュメントを読み込む場所を確認するメッセージが表示されます。 既にトポロジが定義されていて、全体管理ストアを確立しているため、既存の展開からトポロジをダウンロードすることを選択する必要があります。 トポロジビルダーはデータベースを読み取り、現在の定義を取得します。
ms.openlocfilehash: 67317f9acf477d6b6decd42433844ef088d27021
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280858"
---
# <a name="download-topology-from-existing-deployment"></a><span data-ttu-id="a2c86-106">既存の展開環境からトポロジをダウンロードする</span><span class="sxs-lookup"><span data-stu-id="a2c86-106">Download topology from existing deployment</span></span>

<span data-ttu-id="a2c86-107">Skype for Business Server 2019 プールを作成する場合は、従来のインストールに関連付けられている中央管理ストアを使用します。</span><span class="sxs-lookup"><span data-stu-id="a2c86-107">When creating a Skype for Business Server 2019 pool, you will use the Central Management Store that is associated with the legacy installation.</span></span> <span data-ttu-id="a2c86-108">最初の使用時と後続の編集セッションでトポロジビルダーを起動すると、トポロジビルダーで現在の構成ドキュメントを読み込む場所を確認するメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a2c86-108">When you start Topology Builder on first use and subsequent edit sessions, you are prompted for the location where you want Topology Builder to load the current configuration document.</span></span> <span data-ttu-id="a2c86-109">既にトポロジが定義されていて、全体管理ストアを確立しているため、既存の展開からトポロジをダウンロードすることを選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a2c86-109">Because you already have a topology defined and have established the Central Management store, you should choose to download a topology from an existing deployment.</span></span> <span data-ttu-id="a2c86-110">トポロジビルダーはデータベースを読み取り、現在の定義を取得します。</span><span class="sxs-lookup"><span data-stu-id="a2c86-110">Topology Builder will read the database and retrieve the current definition.</span></span> 
  
### <a name="to-download-a-topology-from-an-existing-deployment"></a><span data-ttu-id="a2c86-111">既存の展開からトポロジをダウンロードするには</span><span class="sxs-lookup"><span data-stu-id="a2c86-111">To download a topology from an existing deployment</span></span>

1. <span data-ttu-id="a2c86-112">Skype for Business Server 展開ウィザードを開きます。</span><span class="sxs-lookup"><span data-stu-id="a2c86-112">Open the Skype for Business Server Deployment Wizard.</span></span>
    
2. <span data-ttu-id="a2c86-113">**Skype For Business Server 2019 の展開ウィザード**ページで、[**管理ツールのインストール**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a2c86-113">From the **Skype for Business Server 2019 - Deployment Wizard** page, click **Install Administrative Tools**.</span></span>
    
3. <span data-ttu-id="a2c86-114">トポロジビルダーを開始します。 [**スタート**]、[**すべてのプログラム**]、[ **Microsoft skype for business Server 2019**]、[ **skype for business server Topology Builder**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="a2c86-114">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Topology Builder**.</span></span>
    
4. <span data-ttu-id="a2c86-115">[**既存の展開からトポロジをダウンロード**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a2c86-115">Select **Download Topology from existing deployment**.</span></span>
  
5. <span data-ttu-id="a2c86-116">ファイル名を選択し、tbxml ファイルの種類が設定されたトポロジを保存します。</span><span class="sxs-lookup"><span data-stu-id="a2c86-116">Choose a file name, and save the topology with the default .tbxml file type.</span></span>
    
6. <span data-ttu-id="a2c86-117">[Skype for Business Server] ノードを展開して、展開内のさまざまなサーバーの役割を表示します。</span><span class="sxs-lookup"><span data-stu-id="a2c86-117">Expand the Skype for Business Server node to reveal the various server roles in the deployment.</span></span>
    
  

