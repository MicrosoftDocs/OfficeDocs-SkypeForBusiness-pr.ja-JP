---
title: ビジネス サーバー 2015 の Skype での AlwaysOn 可用性グループにデータベースを追加します。
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 1/30/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 026c4469-f471-4e4f-a77d-a7d22a925e5a
description: '概要: ビジネス サーバー 2015 のビジネス サーバー データベースの複数の Skype を Skype で既存の AlwaysOn 可用性グループに追加する方法を説明します。'
ms.openlocfilehash: 31678d6cc374ecdbe40d2fdf3039905176c0178d
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="add-databases-to-an-alwayson-availability-group-in-skype-for-business-server-2015"></a><span data-ttu-id="9108b-103">ビジネス サーバー 2015 の Skype での AlwaysOn 可用性グループにデータベースを追加します。</span><span class="sxs-lookup"><span data-stu-id="9108b-103">Add databases to an AlwaysOn Availability Group in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="9108b-104">**の概要:**ビジネス サーバー 2015 のビジネス サーバー データベースの複数の Skype を Skype で既存の AlwaysOn 可用性グループに追加する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="9108b-104">**Summary:** Learn how to add more Skype for Business Server databases to an existing AlwaysOn Availability Group in Skype for Business Server 2015.</span></span>
  
### <a name="adding-databases-to-an-alwayson-availability-group"></a><span data-ttu-id="9108b-105">AlwaysOn 可用性グループにデータベースを追加します。</span><span class="sxs-lookup"><span data-stu-id="9108b-105">Adding databases to an AlwaysOn Availability Group</span></span>

1. <span data-ttu-id="9108b-106">SQL Server Management Studio を開き AlwaysOn 可用性グループに移動します。</span><span class="sxs-lookup"><span data-stu-id="9108b-106">Open SQL Server Management Studio, and navigate to the AlwaysOn Availability Group.</span></span> <span data-ttu-id="9108b-107">フェールオーバー、プライマリ レプリカにします。</span><span class="sxs-lookup"><span data-stu-id="9108b-107">Fail it over to the primary replica.</span></span>
    
2. <span data-ttu-id="9108b-108">トポロジ ビルダーでは、AlwaysOn 可用性グループの SQL Server の FQDN をそのグループのプライマリ ノードの FQDN に設定します。</span><span class="sxs-lookup"><span data-stu-id="9108b-108">In Topology Builder, set the SQL Server FQDN of the AlwaysOn Availability Group to the FQDN of the primary node of that group.</span></span>
    
  - <span data-ttu-id="9108b-109">トポロジ ビルダーを開き**既存の展開からトポロジをダウンロード**するを選択して**[ok]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9108b-109">Open Topology Builder, select **Download topology from existing deployment**, and click **OK**.</span></span>
    
  - <span data-ttu-id="9108b-110">[Skype for Business Server]、使用するトポロジ、[**SQL Server ストア**] の順に展開します。</span><span class="sxs-lookup"><span data-stu-id="9108b-110">Expand Skype for Business Server, expand your topology, and expand **SQL Server Stores**.</span></span> <span data-ttu-id="9108b-111">新しい AlwaysOn 可用性グループの SQL ストアを右クリックし、[**プロパティの編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9108b-111">Right-click the SQL store of the new AlwaysOn Availability Group, and click **Edit Properties**.</span></span>
    
  - <span data-ttu-id="9108b-112">**SQL Server の FQDN** ] ボックスで、ページの下部に、AlwaysOn 可用性グループのプライマリ ノードの FQDN を入力します。</span><span class="sxs-lookup"><span data-stu-id="9108b-112">At the bottom of the page, in the **SQL Server FQDN** box, type in the FQDN of the primary node of the AlwaysOn Availability Group.</span></span>
    
3. <span data-ttu-id="9108b-p103">トポロジを公開します。[**操作**] メニューから、[**トポロジ**]、[**公開**] の順にクリックします。続いて確認ページで [**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9108b-p103">Publish the topology. From the **Action** menu click **Topology** and then **Publish**. Then in the confirmation page click **Next**.</span></span>
    
4. <span data-ttu-id="9108b-116">AlwaysOn 可用性グループに新しいデータベースを追加するのにには、SQL Server Management Studio を使用します。</span><span class="sxs-lookup"><span data-stu-id="9108b-116">Use SQL Server Management Studio to add the new database to the AlwaysOn Availability Group.</span></span>
    

