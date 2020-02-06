---
title: Skype for Business Server の AlwaysOn 可用性グループでデータベースを管理する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 026c4469-f471-4e4f-a77d-a7d22a925e5a
description: '概要: Skype for Business Server データベースを既存の AlwaysOn 可用性グループに追加する方法について説明し、Skype for the AlwaysOn 可用性グループの一部であるバックエンドサーバーを修正またはアップグレードした後に必要な追加の手順について説明します。Business Server。'
ms.openlocfilehash: 579b00047a9966e3ce991863506f5686d8a2d520
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817138"
---
# <a name="manage-databases-with-an-alwayson-availability-group-in-skype-for-business-server"></a><span data-ttu-id="047ef-103">Skype for Business Server の AlwaysOn 可用性グループでデータベースを管理する</span><span class="sxs-lookup"><span data-stu-id="047ef-103">Manage databases with an AlwaysOn Availability Group in Skype for Business Server</span></span>

<span data-ttu-id="047ef-104">この記事の手順を使用して、Skype for Business Server の既存の AlwaysOn 可用性グループにさらに Skype for Business Server データベースを追加します。 AlwaysOn の一部であるバックエンドサーバーを修正またはアップグレードした後で、必要な追加の手順を確認してください。Skype for Business Server の可用性グループ。</span><span class="sxs-lookup"><span data-stu-id="047ef-104">Use the steps in this article to add more Skype for Business Server databases to an existing AlwaysOn Availability Group in Skype for Business Server, and find out about the necessary additional steps after you patch or upgrade a Back End Server that is part of a AlwaysOn Availability Group in Skype for Business Server.</span></span>

## <a name="add-databases-to-an-alwayson-availability-group"></a><span data-ttu-id="047ef-105">AlwaysOn 可用性グループにデータベースを追加する</span><span class="sxs-lookup"><span data-stu-id="047ef-105">Add databases to an AlwaysOn Availability Group</span></span> 

1. <span data-ttu-id="047ef-106">SQL Server Management Studio を開き、AlwaysOn 可用性グループに移動します。</span><span class="sxs-lookup"><span data-stu-id="047ef-106">Open SQL Server Management Studio, and navigate to the AlwaysOn Availability Group.</span></span> <span data-ttu-id="047ef-107">プライマリレプリカにフェイルオーバーします。</span><span class="sxs-lookup"><span data-stu-id="047ef-107">Fail it over to the primary replica.</span></span>
    
2. <span data-ttu-id="047ef-108">[トポロジビルダー] で、AlwaysOn 可用性グループの SQL Server FQDN をそのグループのプライマリノードの FQDN に設定します。</span><span class="sxs-lookup"><span data-stu-id="047ef-108">In Topology Builder, set the SQL Server FQDN of the AlwaysOn Availability Group to the FQDN of the primary node of that group.</span></span>
    
   - <span data-ttu-id="047ef-109">トポロジビルダーを開き、[**既存の展開からトポロジをダウンロード**] を選択して、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="047ef-109">Open Topology Builder, select **Download topology from existing deployment**, and click **OK**.</span></span>
    
   - <span data-ttu-id="047ef-110">[Skype for Business Server]、使用するトポロジ、[**SQL Server ストア**] の順に展開します。</span><span class="sxs-lookup"><span data-stu-id="047ef-110">Expand Skype for Business Server, expand your topology, and expand **SQL Server Stores**.</span></span> <span data-ttu-id="047ef-111">新しい AlwaysOn 可用性グループの SQL ストアを右クリックし、[プロパティの**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="047ef-111">Right-click the SQL store of the new AlwaysOn Availability Group, and click **Edit Properties**.</span></span>
    
   - <span data-ttu-id="047ef-112">ページの下部にある [ **SQL SERVER FQDN** ] ボックスに、AlwaysOn 可用性グループのプライマリノードの FQDN を入力します。</span><span class="sxs-lookup"><span data-stu-id="047ef-112">At the bottom of the page, in the **SQL Server FQDN** box, type in the FQDN of the primary node of the AlwaysOn Availability Group.</span></span>
    
3. <span data-ttu-id="047ef-113">トポロジを公開します。</span><span class="sxs-lookup"><span data-stu-id="047ef-113">Publish the topology.</span></span> <span data-ttu-id="047ef-114">[**操作**] メニューから、[**トポロジ**]、[**公開**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="047ef-114">From the **Action** menu click **Topology** and then **Publish**.</span></span> <span data-ttu-id="047ef-115">続いて、確認ページで [**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="047ef-115">Then in the confirmation page click **Next**.</span></span>
    
4. <span data-ttu-id="047ef-116">SQL Server Management Studio を使用して、新しいデータベースを AlwaysOn 可用性グループに追加します。</span><span class="sxs-lookup"><span data-stu-id="047ef-116">Use SQL Server Management Studio to add the new database to the AlwaysOn Availability Group.</span></span>
    
## <a name="patch-or-update-a-sql-server-in-an-alwayson-availability-group"></a><span data-ttu-id="047ef-117">AlwaysOn 可用性グループの SQL Server に対して修正プログラムを適用または更新を実行する</span><span class="sxs-lookup"><span data-stu-id="047ef-117">Patch or update a SQL Server in an AlwaysOn Availability Group</span></span>

<span data-ttu-id="047ef-118">AlwaysOn 可用性グループの一部であるバックエンドサーバーを更新した後、トポロジを再公開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="047ef-118">After patching a Back End Server that is part of an AlwaysOn Availability Group, you must republish the topology.</span></span>

1. <span data-ttu-id="047ef-119">Skype for Business Server に更新プログラムをインストールします。</span><span class="sxs-lookup"><span data-stu-id="047ef-119">Install the update on your Skype for Business server or servers.</span></span>
    
2. <span data-ttu-id="047ef-120">Skype for Business 管理シェルで次の PowerShell コマンドを (SQL AlwaysOn データベースに変更を適用する適切な権限を持ったアカウントでログインした上で) 次のとおり実行します。</span><span class="sxs-lookup"><span data-stu-id="047ef-120">Run the following PowerShell command in your Skype for Business Management Shell (logged in with an account that's appropriately permissioned to apply changes to the SQL AlwaysOn databases) as follows:</span></span>
    
    ```PowerShell
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn [sqlpool.contoso.com] -Verbose
    ```

    <span data-ttu-id="047ef-121">[sqlpool.contoso.com] は、AlwaysOn 可用性グループの完全修飾ドメイン名 (FQDN) に置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="047ef-121">Where [sqlpool.contoso.com] is replaced with the fully qualified domain name (FQDN) of your AlwaysOn availability group.</span></span>
