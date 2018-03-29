---
title: Skype for Business Server 2015 の AlwaysOn 可用性グループの SQL Server に対して修正プログラムを適用または更新を実行する
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 9/11/2017
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7298254b-bc33-450e-846a-2612f6dc7006
description: '概要: では、修正した後、必要な追加手順について調べるか、バック エンド サーバー ビジネス サーバーの Skype での AlwaysOn 可用性グループの一部であるをアップグレードします。'
ms.openlocfilehash: 8f5c9131e59ccedd7f590f696fe53aa6c18c7d22
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="patch-or-update-a-sql-server-in-an-alwayson-availability-group-in-skype-for-business-server-2015"></a><span data-ttu-id="e19c5-103">Skype for Business Server 2015 の AlwaysOn 可用性グループの SQL Server に対して修正プログラムを適用または更新を実行する</span><span class="sxs-lookup"><span data-stu-id="e19c5-103">Patch or update a SQL Server in an AlwaysOn Availability Group in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="e19c5-104">**の概要:**修正プログラムを適用または、バック エンド サーバー ビジネス サーバーの Skype での AlwaysOn 可用性グループの一部であるをアップグレードした後、必要な追加手順をお探しです。</span><span class="sxs-lookup"><span data-stu-id="e19c5-104">**Summary:** Find out about the necessary additional steps after you patch or upgrade a Back End Server that is part of a AlwaysOn Availability Group in Skype for Business Server.</span></span>
  
<span data-ttu-id="e19c5-105">バック エンド サーバー、AlwaysOn 可用性グループの一部を修正するには後に、、トポロジを再発行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e19c5-105">After patching a Back End Server that is part of an AlwaysOn Availability Group, you must republish the topology.</span></span>
  
### <a name="patching-or-updating-a-sql-server-that-is-part-of-an-alwayson-availability-group"></a><span data-ttu-id="e19c5-106">AlwaysOn 可用性グループの一部である SQL Server に対する修正プログラムの適用または更新の実行</span><span class="sxs-lookup"><span data-stu-id="e19c5-106">Patching or updating a SQL Server that is part of an AlwaysOn Availability Group</span></span>

1. <span data-ttu-id="e19c5-107">Skype for Business Server に更新プログラムをインストールします。</span><span class="sxs-lookup"><span data-stu-id="e19c5-107">Install the update on your Skype for Business server or servers.</span></span>
    
2. <span data-ttu-id="e19c5-108">Skype for Business 管理シェルで次の PowerShell コマンドを (SQL AlwaysOn データベースに変更を適用する適切な権限を持ったアカウントでログインした上で) 次のとおり実行します。</span><span class="sxs-lookup"><span data-stu-id="e19c5-108">Run the following PowerShell command in your Skype for Business Management Shell (logged in with an account that's appropriately permissioned to apply changes to the SQL AlwaysOn databases) as follows:</span></span>
    
    ```
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn [sqlpool.contoso.com] -Verbose
    ```

    <span data-ttu-id="e19c5-109">[sqlpool.contoso.com] は、AlwaysOn 可用性グループの完全修飾ドメイン名 (FQDN) に置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="e19c5-109">Where [sqlpool.contoso.com] is replaced with the fully qualified domain name (FQDN) of your AlwaysOn availability group.</span></span>
    

