---
title: SQL ストアを追加する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8ec39dfc-c58d-4fdb-b61e-f71dd691cef8
description: 新しい SQL ストアを定義するには、つまり、SQL Server ベースのデータベースと SQL Server のインスタンス (既定のインスタンスまたは名前付きインスタンス) を指定する場合は、以下を指定します。
ms.openlocfilehash: 79429b596eef1ed0695aeb24594ea08ce12093be
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49833307"
---
# <a name="add-sql-store"></a><span data-ttu-id="9f938-103">SQL ストアの追加</span><span class="sxs-lookup"><span data-stu-id="9f938-103">Add SQL Store</span></span>

<span data-ttu-id="9f938-104">新しい SQL ストアを定義するには、つまり、SQL Server ベースのデータベースと SQL Server のインスタンス (既定のインスタンスまたは名前付きインスタンス) を指定する場合は、以下を指定します。</span><span class="sxs-lookup"><span data-stu-id="9f938-104">To define a new SQL Store, which means that you are specifying a SQL Server-based database and an instance of SQL Server—either a default instance or a named instance—you specify the following.</span></span>

<span data-ttu-id="9f938-105">定義するデータベース インスタンスをホストするSQL Serverの完全修飾ドメイン名 (FQDN) を指定します。</span><span class="sxs-lookup"><span data-stu-id="9f938-105">Specify the fully qualified domain name (FQDN) of the SQL Server that will host the database instance that you are defining.</span></span>

<span data-ttu-id="9f938-106">データをホストするSQL Serverインスタンスを指定します。</span><span class="sxs-lookup"><span data-stu-id="9f938-106">Specify the instance of SQL Server that will host the data.</span></span> <span data-ttu-id="9f938-107">既定のインスタンスを指定するか、名前付きインスタンスを指定できます。</span><span class="sxs-lookup"><span data-stu-id="9f938-107">You can specify the default instance, or you can specify a named instance.</span></span>

<span data-ttu-id="9f938-108">特定のインスタンスにおけるデータベースの併置を明確に把握する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9f938-108">Collocation of databases in specific instances should be very clearly understood.</span></span> <span data-ttu-id="9f938-109">サーバーの併置とデータベース インスタンスの併置の詳細については、「[Server Collocation in a Front End Pool Deployment](https://technet.microsoft.com/library/0516b18d-14c0-4237-9279-0f92e341b1bd.aspx)」および「[Server Collocation in a Standard Edition Server Deployment](https://technet.microsoft.com/library/0763ffab-4fd6-463a-8e62-d97876b376d3.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9f938-109">For details about server collocation and database instance collocation, see [Server Collocation in a Front End Pool Deployment](https://technet.microsoft.com/library/0516b18d-14c0-4237-9279-0f92e341b1bd.aspx) and [Server Collocation in a Standard Edition Server Deployment](https://technet.microsoft.com/library/0763ffab-4fd6-463a-8e62-d97876b376d3.aspx).</span></span>


