---
title: SQL ストアを追加する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8ec39dfc-c58d-4fdb-b61e-f71dd691cef8
ROBOTS: NOINDEX, NOFOLLOW
description: 新しい SQL ストアを定義するには、つまり、SQL Server ベースのデータベースと SQL Server のインスタンス (既定のインスタンスまたは名前付きインスタンス) を指定する場合は、以下を指定します。
ms.openlocfilehash: 46cdbed683abc2121ce4038b6692f1f73f8abc0c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49824507"
---
# <a name="add-sql-store"></a>SQL ストアの追加

新しい SQL ストアを定義するには、つまり、SQL Server ベースのデータベースと SQL Server のインスタンス (既定のインスタンスまたは名前付きインスタンス) を指定する場合は、以下を指定します。

定義するデータベース インスタンスをホストするSQL Serverの完全修飾ドメイン名 (FQDN) を指定します。

データをホストするSQL Serverインスタンスを指定します。 既定のインスタンスを指定するか、名前付きインスタンスを指定できます。

特定のインスタンスにおけるデータベースの併置を明確に把握する必要があります。 サーバーの併置とデータベース インスタンスの併置の詳細については、「[Server Collocation in a Front End Pool Deployment](https://technet.microsoft.com/library/0516b18d-14c0-4237-9279-0f92e341b1bd.aspx)」および「[Server Collocation in a Standard Edition Server Deployment](https://technet.microsoft.com/library/0763ffab-4fd6-463a-8e62-d97876b376d3.aspx)」を参照してください。


