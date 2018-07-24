---
title: 修正プログラムを適用または、Skype での AlwaysOn 可用性グループ内の SQL Server をビジネスのサーバーの更新
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7298254b-bc33-450e-846a-2612f6dc7006
description: '概要: では、修正した後、必要な追加手順について調べるか、バック エンド サーバー ビジネス サーバーの Skype での AlwaysOn 可用性グループの一部であるをアップグレードします。'
ms.openlocfilehash: 7227bdc61e7accbdd6f6e760e1a33d9a2b76eb30
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2018
ms.locfileid: "20982987"
---
# <a name="patch-or-update-a-sql-server-in-an-alwayson-availability-group-in-skype-for-business-server"></a><span data-ttu-id="26a1a-103">修正プログラムを適用または、Skype での AlwaysOn 可用性グループ内の SQL Server をビジネスのサーバーの更新</span><span class="sxs-lookup"><span data-stu-id="26a1a-103">Patch or update a SQL Server in an AlwaysOn Availability Group in Skype for Business Server</span></span>
 
<span data-ttu-id="26a1a-104">**の概要:** 修正プログラムを適用または、バック エンド サーバー ビジネス サーバーの Skype での AlwaysOn 可用性グループの一部であるをアップグレードした後、必要な追加手順をお探しです。</span><span class="sxs-lookup"><span data-stu-id="26a1a-104">**Summary:** Find out about the necessary additional steps after you patch or upgrade a Back End Server that is part of a AlwaysOn Availability Group in Skype for Business Server.</span></span>
  
<span data-ttu-id="26a1a-105">バック エンド サーバー、AlwaysOn 可用性グループの一部を修正するには後に、、トポロジを再発行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="26a1a-105">After patching a Back End Server that is part of an AlwaysOn Availability Group, you must republish the topology.</span></span>
  
### <a name="patching-or-updating-a-sql-server-that-is-part-of-an-alwayson-availability-group"></a><span data-ttu-id="26a1a-106">AlwaysOn 可用性グループの一部である SQL Server に対する修正プログラムの適用または更新の実行</span><span class="sxs-lookup"><span data-stu-id="26a1a-106">Patching or updating a SQL Server that is part of an AlwaysOn Availability Group</span></span>

1. <span data-ttu-id="26a1a-107">Skype for Business Server に更新プログラムをインストールします。</span><span class="sxs-lookup"><span data-stu-id="26a1a-107">Install the update on your Skype for Business server or servers.</span></span>
    
2. <span data-ttu-id="26a1a-108">Skype for Business 管理シェルで次の PowerShell コマンドを (SQL AlwaysOn データベースに変更を適用する適切な権限を持ったアカウントでログインした上で) 次のとおり実行します。</span><span class="sxs-lookup"><span data-stu-id="26a1a-108">Run the following PowerShell command in your Skype for Business Management Shell (logged in with an account that's appropriately permissioned to apply changes to the SQL AlwaysOn databases) as follows:</span></span>
    
    ```
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn [sqlpool.contoso.com] -Verbose
    ```

    <span data-ttu-id="26a1a-109">[sqlpool.contoso.com] は、AlwaysOn 可用性グループの完全修飾ドメイン名 (FQDN) に置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="26a1a-109">Where [sqlpool.contoso.com] is replaced with the fully qualified domain name (FQDN) of your AlwaysOn availability group.</span></span>
    

