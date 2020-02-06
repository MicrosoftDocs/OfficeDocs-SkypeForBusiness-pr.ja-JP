---
title: SQL ストアの追加
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.custom:
- ms.lync.tb.AddSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8ec39dfc-c58d-4fdb-b61e-f71dd691cef8
description: 新しい SQL ストアを定義するには、SQL Server ベースのデータベースと SQL Server のインスタンス (既定のインスタンスまたは名前付きインスタンスのいずれか) を指定する必要があります。その場合は、次のように指定します。
ms.openlocfilehash: f65eb47327df45b7b1bd5c5a0c2a5bb8173d8bc9
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41820609"
---
# <a name="add-sql-store"></a><span data-ttu-id="10de6-103">SQL ストアの追加</span><span class="sxs-lookup"><span data-stu-id="10de6-103">Add SQL Store</span></span>

<span data-ttu-id="10de6-104">新しい SQL ストアを定義するには、SQL Server ベースのデータベースと SQL Server のインスタンス (既定のインスタンスまたは名前付きインスタンスのいずれか) を指定する必要があります。その場合は、次のように指定します。</span><span class="sxs-lookup"><span data-stu-id="10de6-104">To define a new SQL Store, which means that you are specifying a SQL Server-based database and an instance of SQL Server—either a default instance or a named instance—you specify the following.</span></span>

<span data-ttu-id="10de6-105">定義するデータベースインスタンスをホストする SQL Server の完全修飾ドメイン名 (FQDN) を指定します。</span><span class="sxs-lookup"><span data-stu-id="10de6-105">Specify the fully qualified domain name (FQDN) of the SQL Server that will host the database instance that you are defining.</span></span>

<span data-ttu-id="10de6-106">データをホストする SQL Server のインスタンスを指定します。</span><span class="sxs-lookup"><span data-stu-id="10de6-106">Specify the instance of SQL Server that will host the data.</span></span> <span data-ttu-id="10de6-107">既定のインスタンスを指定することも、名前付きインスタンスを指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="10de6-107">You can specify the default instance, or you can specify a named instance.</span></span>

<span data-ttu-id="10de6-108">特定のインスタンスでのデータベースの collocation は、非常に明確に理解しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="10de6-108">Collocation of databases in specific instances should be very clearly understood.</span></span> <span data-ttu-id="10de6-109">サーバーの collocation とデータベースインスタンスの collocation の詳細については、「[フロントエンドプールの展開のサーバー Collocation](https://technet.microsoft.com/library/0516b18d-14c0-4237-9279-0f92e341b1bd.aspx) 」および「 [Standard Edition server の展開におけるサーバーの場所](https://technet.microsoft.com/library/0763ffab-4fd6-463a-8e62-d97876b376d3.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="10de6-109">For details about server collocation and database instance collocation, see [Server Collocation in a Front End Pool Deployment](https://technet.microsoft.com/library/0516b18d-14c0-4237-9279-0f92e341b1bd.aspx) and [Server Collocation in a Standard Edition Server Deployment](https://technet.microsoft.com/library/0763ffab-4fd6-463a-8e62-d97876b376d3.aspx).</span></span>


