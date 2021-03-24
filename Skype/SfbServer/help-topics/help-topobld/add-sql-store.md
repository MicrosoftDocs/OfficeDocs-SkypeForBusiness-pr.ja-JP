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
description: 新しい SQL ストアを定義するには、SQL Server ベースのデータベースと SQL Server のインスタンス (既定のインスタンスまたは名前付きインスタンス) を指定します。
ms.openlocfilehash: 28018a7320bc42761a668aaff385302016781592
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095601"
---
# <a name="add-sql-store"></a><span data-ttu-id="e24b3-103">SQL ストアの追加</span><span class="sxs-lookup"><span data-stu-id="e24b3-103">Add SQL Store</span></span>

<span data-ttu-id="e24b3-104">新しい SQL ストアを定義するには、SQL Server ベースのデータベースと SQL Server のインスタンス (既定のインスタンスまたは名前付きインスタンス) を指定します。</span><span class="sxs-lookup"><span data-stu-id="e24b3-104">To define a new SQL Store, which means that you are specifying a SQL Server-based database and an instance of SQL Server—either a default instance or a named instance—you specify the following.</span></span>

<span data-ttu-id="e24b3-105">定義するデータベース インスタンスをホストするSQL Serverの完全修飾ドメイン名 (FQDN) を指定します。</span><span class="sxs-lookup"><span data-stu-id="e24b3-105">Specify the fully qualified domain name (FQDN) of the SQL Server that will host the database instance that you are defining.</span></span>

<span data-ttu-id="e24b3-106">データをホストするSQL Serverインスタンスを指定します。</span><span class="sxs-lookup"><span data-stu-id="e24b3-106">Specify the instance of SQL Server that will host the data.</span></span> <span data-ttu-id="e24b3-107">既定のインスタンスを指定するか、名前付きインスタンスを指定できます。</span><span class="sxs-lookup"><span data-stu-id="e24b3-107">You can specify the default instance, or you can specify a named instance.</span></span>

<span data-ttu-id="e24b3-108">特定のインスタンスにおけるデータベースの併置を明確に把握する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e24b3-108">Collocation of databases in specific instances should be very clearly understood.</span></span> <span data-ttu-id="e24b3-109">サーバーの併置とデータベース インスタンスの併置の詳細については、「[Server Collocation in a Front End Pool Deployment](/previous-versions/office/lync-server-2013/lync-server-2013-server-collocation-in-an-enterprise-edition-front-end-pool-deployment)」および「[Server Collocation in a Standard Edition Server Deployment](/previous-versions/office/lync-server-2013/lync-server-2013-server-collocation-in-a-standard-edition-server-deployment)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e24b3-109">For details about server collocation and database instance collocation, see [Server Collocation in a Front End Pool Deployment](/previous-versions/office/lync-server-2013/lync-server-2013-server-collocation-in-an-enterprise-edition-front-end-pool-deployment) and [Server Collocation in a Standard Edition Server Deployment](/previous-versions/office/lync-server-2013/lync-server-2013-server-collocation-in-a-standard-edition-server-deployment).</span></span>