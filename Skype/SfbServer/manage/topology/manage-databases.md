---
title: Skype for Business Server で AlwaysOn 可用性グループを使用してデータベースを管理する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 026c4469-f471-4e4f-a77d-a7d22a925e5a
description: '概要: 既存の AlwaysOn 可用性グループにさらに Skype for Business Server データベースを追加する方法と、Skype for Business Server の AlwaysOn 可用性グループの一部であるバック エンド サーバーにパッチを適用またはアップグレードした後の必要な追加手順について説明します。'
ms.openlocfilehash: 444194c9cda5f4c3f82e6f3f7698395dce1a5d07
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826367"
---
# <a name="manage-databases-with-an-alwayson-availability-group-in-skype-for-business-server"></a><span data-ttu-id="07db3-103">Skype for Business Server で AlwaysOn 可用性グループを使用してデータベースを管理する</span><span class="sxs-lookup"><span data-stu-id="07db3-103">Manage databases with an AlwaysOn Availability Group in Skype for Business Server</span></span>

<span data-ttu-id="07db3-104">この記事の手順を使用して、Skype for Business Server の既存の AlwaysOn 可用性グループにさらに Skype for Business Server データベースを追加し、Skype for Business Server の AlwaysOn 可用性グループの一部であるバック エンド サーバーにパッチを適用またはアップグレードした後に必要な追加の手順を確認します。</span><span class="sxs-lookup"><span data-stu-id="07db3-104">Use the steps in this article to add more Skype for Business Server databases to an existing AlwaysOn Availability Group in Skype for Business Server, and find out about the necessary additional steps after you patch or upgrade a Back End Server that is part of a AlwaysOn Availability Group in Skype for Business Server.</span></span>

## <a name="add-databases-to-an-alwayson-availability-group"></a><span data-ttu-id="07db3-105">AlwaysOn 可用性グループにデータベースを追加する</span><span class="sxs-lookup"><span data-stu-id="07db3-105">Add databases to an AlwaysOn Availability Group</span></span> 

1. <span data-ttu-id="07db3-106">このSQL Server Management Studio開き、AlwaysOn 可用性グループに移動します。</span><span class="sxs-lookup"><span data-stu-id="07db3-106">Open SQL Server Management Studio, and navigate to the AlwaysOn Availability Group.</span></span> <span data-ttu-id="07db3-107">プライマリ レプリカにフェールオーバーします。</span><span class="sxs-lookup"><span data-stu-id="07db3-107">Fail it over to the primary replica.</span></span>
    
2. <span data-ttu-id="07db3-108">トポロジ ビルダーで、AlwaysOn 可用性SQL Serverの FQDN をそのグループのプライマリ ノードの FQDN に設定します。</span><span class="sxs-lookup"><span data-stu-id="07db3-108">In Topology Builder, set the SQL Server FQDN of the AlwaysOn Availability Group to the FQDN of the primary node of that group.</span></span>
    
   - <span data-ttu-id="07db3-109">トポロジ ビルダーを開き、[既存の展開から **トポロジ** をダウンロードする] を選択し **、[OK] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="07db3-109">Open Topology Builder, select **Download topology from existing deployment**, and click **OK**.</span></span>
    
   - <span data-ttu-id="07db3-110">[Skype for Business Server] を展開し、トポロジを展開し、[ストア] **SQL Server展開します**。</span><span class="sxs-lookup"><span data-stu-id="07db3-110">Expand Skype for Business Server, expand your topology, and expand **SQL Server Stores**.</span></span> <span data-ttu-id="07db3-111">新しい AlwaysOn 可用性SQLストアを右クリックし、[プロパティの編集] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="07db3-111">Right-click the SQL store of the new AlwaysOn Availability Group, and click **Edit Properties**.</span></span>
    
   - <span data-ttu-id="07db3-112">ページの下部にある [SQL Server **FQDN]** ボックスに、AlwaysOn 可用性グループのプライマリ ノードの FQDN を入力します。</span><span class="sxs-lookup"><span data-stu-id="07db3-112">At the bottom of the page, in the **SQL Server FQDN** box, type in the FQDN of the primary node of the AlwaysOn Availability Group.</span></span>
    
3. <span data-ttu-id="07db3-113">トポロジを公開します。</span><span class="sxs-lookup"><span data-stu-id="07db3-113">Publish the topology.</span></span> <span data-ttu-id="07db3-114">[操作 **] メニューの** [ **トポロジ] をクリックし、[公開]** を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="07db3-114">From the **Action** menu click **Topology** and then **Publish**.</span></span> <span data-ttu-id="07db3-115">次に、確認ページで [次へ] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="07db3-115">Then in the confirmation page click **Next**.</span></span>
    
4. <span data-ttu-id="07db3-116">このSQL Server Management Studio使用して、新しいデータベースを AlwaysOn 可用性グループに追加します。</span><span class="sxs-lookup"><span data-stu-id="07db3-116">Use SQL Server Management Studio to add the new database to the AlwaysOn Availability Group.</span></span>
    
## <a name="patch-or-update-a-sql-server-in-an-alwayson-availability-group"></a><span data-ttu-id="07db3-117">AlwaysOn 可用性グループのSQL Serverまたは更新する</span><span class="sxs-lookup"><span data-stu-id="07db3-117">Patch or update a SQL Server in an AlwaysOn Availability Group</span></span>

<span data-ttu-id="07db3-118">AlwaysOn 可用性グループの一部であるバック エンド サーバーにパッチを適用した後、トポロジを再公開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="07db3-118">After patching a Back End Server that is part of an AlwaysOn Availability Group, you must republish the topology.</span></span>

1. <span data-ttu-id="07db3-119">Skype for Business サーバーに更新プログラムをインストールします。</span><span class="sxs-lookup"><span data-stu-id="07db3-119">Install the update on your Skype for Business server or servers.</span></span>
    
2. <span data-ttu-id="07db3-120">Skype for Business 管理シェルで次の PowerShell コマンドを実行します (SQL AlwaysOn データベースに変更を適用するための適切なアクセス許可を持つアカウントでログインします)。</span><span class="sxs-lookup"><span data-stu-id="07db3-120">Run the following PowerShell command in your Skype for Business Management Shell (logged in with an account that's appropriately permissioned to apply changes to the SQL AlwaysOn databases) as follows:</span></span>
    
    ```PowerShell
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn [sqlpool.contoso.com] -Verbose
    ```

    <span data-ttu-id="07db3-121">ここで、[sqlpool.contoso.com] は AlwaysOn 可用性グループの完全修飾ドメイン名 (FQDN) に置き換えてください。</span><span class="sxs-lookup"><span data-stu-id="07db3-121">Where [sqlpool.contoso.com] is replaced with the fully qualified domain name (FQDN) of your AlwaysOn availability group.</span></span>
