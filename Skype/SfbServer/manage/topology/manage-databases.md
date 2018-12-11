---
title: ビジネス サーバーの Skype での AlwaysOn 可用性グループにデータベースを管理します。
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 026c4469-f471-4e4f-a77d-a7d22a925e5a
description: '概要: ビジネス サーバー データベースの複数の Skype を既存の AlwaysOn 可用性グループに追加、修正した後、必要な追加手順の詳細についてや、バック エンド サーバーの Skype での AlwaysOn 可用性グループの一部であるをアップグレードする方法を学習します。ビジネス サーバーです。'
ms.openlocfilehash: ca7a792e001c29e087b9b6ac1637029c90ea1ae9
ms.sourcegitcommit: 5576463b0295e48e0506f7e4b44006ffc0b38a95
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2018
ms.locfileid: "27222808"
---
# <a name="manage-databases-with-an-alwayson-availability-group-in-skype-for-business-server"></a><span data-ttu-id="ff59f-103">ビジネス サーバーの Skype での AlwaysOn 可用性グループにデータベースを管理します。</span><span class="sxs-lookup"><span data-stu-id="ff59f-103">Manage databases with an AlwaysOn Availability Group in Skype for Business Server</span></span>

<span data-ttu-id="ff59f-104">この資料の手順を使用して、ビジネスのサーバーの Skype で既存の AlwaysOn 可用性グループにビジネス サーバー データベースの複数の Skype を追加し、修正プログラムを適用または、バック エンド サーバー、AlwaysOn の一部をアップグレードした後、必要な追加手順をお探しSkype ビジネス サーバーの可用性グループです。</span><span class="sxs-lookup"><span data-stu-id="ff59f-104">Use the steps in this article to add more Skype for Business Server databases to an existing AlwaysOn Availability Group in Skype for Business Server, and find out about the necessary additional steps after you patch or upgrade a Back End Server that is part of a AlwaysOn Availability Group in Skype for Business Server.</span></span>

## <a name="add-databases-to-an-alwayson-availability-group"></a><span data-ttu-id="ff59f-105">データベースを AlwaysOn 可用性グループに追加します。</span><span class="sxs-lookup"><span data-stu-id="ff59f-105">Add databases to an AlwaysOn Availability Group</span></span> 

1. <span data-ttu-id="ff59f-106">SQL Server Management Studio を開き AlwaysOn 可用性グループに移動します。</span><span class="sxs-lookup"><span data-stu-id="ff59f-106">Open SQL Server Management Studio, and navigate to the AlwaysOn Availability Group.</span></span> <span data-ttu-id="ff59f-107">フェールオーバー、プライマリ レプリカにします。</span><span class="sxs-lookup"><span data-stu-id="ff59f-107">Fail it over to the primary replica.</span></span>
    
2. <span data-ttu-id="ff59f-108">トポロジ ビルダーでは、AlwaysOn 可用性グループの SQL Server の FQDN をそのグループのプライマリ ノードの FQDN に設定します。</span><span class="sxs-lookup"><span data-stu-id="ff59f-108">In Topology Builder, set the SQL Server FQDN of the AlwaysOn Availability Group to the FQDN of the primary node of that group.</span></span>
    
   - <span data-ttu-id="ff59f-109">トポロジ ビルダーを開き**既存の展開からトポロジをダウンロード**するを選択して **[ok]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ff59f-109">Open Topology Builder, select **Download topology from existing deployment**, and click **OK**.</span></span>
    
   - <span data-ttu-id="ff59f-110">[Skype for Business Server]、使用するトポロジ、[**SQL Server ストア**] の順に展開します。</span><span class="sxs-lookup"><span data-stu-id="ff59f-110">Expand Skype for Business Server, expand your topology, and expand **SQL Server Stores**.</span></span> <span data-ttu-id="ff59f-111">新しい AlwaysOn 可用性グループの SQL ストアを右クリックし、[**プロパティの編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ff59f-111">Right-click the SQL store of the new AlwaysOn Availability Group, and click **Edit Properties**.</span></span>
    
   - <span data-ttu-id="ff59f-112">**SQL Server の FQDN** ] ボックスで、ページの下部に、AlwaysOn 可用性グループのプライマリ ノードの FQDN を入力します。</span><span class="sxs-lookup"><span data-stu-id="ff59f-112">At the bottom of the page, in the **SQL Server FQDN** box, type in the FQDN of the primary node of the AlwaysOn Availability Group.</span></span>
    
3. <span data-ttu-id="ff59f-113">トポロジを公開します。</span><span class="sxs-lookup"><span data-stu-id="ff59f-113">Publish the topology.</span></span> <span data-ttu-id="ff59f-114">[**操作**] メニューから、[**トポロジ**]、[**公開**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="ff59f-114">From the **Action** menu click **Topology** and then **Publish**.</span></span> <span data-ttu-id="ff59f-115">続いて、確認ページで [**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ff59f-115">Then in the confirmation page click **Next**.</span></span>
    
4. <span data-ttu-id="ff59f-116">AlwaysOn 可用性グループに新しいデータベースを追加するのにには、SQL Server Management Studio を使用します。</span><span class="sxs-lookup"><span data-stu-id="ff59f-116">Use SQL Server Management Studio to add the new database to the AlwaysOn Availability Group.</span></span>
    
## <a name="patch-or-update-a-sql-server-in-an-alwayson-availability-group"></a><span data-ttu-id="ff59f-117">AlwaysOn 可用性グループの SQL Server に対して修正プログラムを適用または更新を実行する</span><span class="sxs-lookup"><span data-stu-id="ff59f-117">Patch or update a SQL Server in an AlwaysOn Availability Group</span></span>

<span data-ttu-id="ff59f-118">バック エンド サーバー、AlwaysOn 可用性グループの一部を修正するには後に、、トポロジを再発行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ff59f-118">After patching a Back End Server that is part of an AlwaysOn Availability Group, you must republish the topology.</span></span>

1. <span data-ttu-id="ff59f-119">Skype for Business Server に更新プログラムをインストールします。</span><span class="sxs-lookup"><span data-stu-id="ff59f-119">Install the update on your Skype for Business server or servers.</span></span>
    
2. <span data-ttu-id="ff59f-120">Skype for Business 管理シェルで次の PowerShell コマンドを (SQL AlwaysOn データベースに変更を適用する適切な権限を持ったアカウントでログインした上で) 次のとおり実行します。</span><span class="sxs-lookup"><span data-stu-id="ff59f-120">Run the following PowerShell command in your Skype for Business Management Shell (logged in with an account that's appropriately permissioned to apply changes to the SQL AlwaysOn databases) as follows:</span></span>
    
    ```
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn [sqlpool.contoso.com] -Verbose
    ```

    <span data-ttu-id="ff59f-121">[sqlpool.contoso.com] は、AlwaysOn 可用性グループの完全修飾ドメイン名 (FQDN) に置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="ff59f-121">Where [sqlpool.contoso.com] is replaced with the fully qualified domain name (FQDN) of your AlwaysOn availability group.</span></span>