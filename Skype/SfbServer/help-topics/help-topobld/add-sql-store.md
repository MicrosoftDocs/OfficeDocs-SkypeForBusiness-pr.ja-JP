---
title: SQL ストアを追加する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 新しい SQL ストアを定義するには、SQL Server ベースのデータベースと SQL Server のインスタンス (既定のインスタンスまたは名前付きインスタンス) を指定する必要があります。その場合は、次のように指定します。
ms.openlocfilehash: 261cc9ca3b0f792c9ab6566ba24f1d4d7236937a
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2020
ms.locfileid: "48217128"
---
# <a name="add-sql-store"></a>SQL ストアを追加する

新しい SQL ストアを定義するには、SQL Server ベースのデータベースと SQL Server のインスタンス (既定のインスタンスまたは名前付きインスタンス) を指定する必要があります。その場合は、次のように指定します。

定義するデータベースインスタンスをホストする SQL Server の完全修飾ドメイン名 (FQDN) を指定します。

データをホストする SQL Server のインスタンスを指定します。 既定のインスタンスを指定するか、名前付きインスタンスを指定できます。

特定のインスタンスにおけるデータベースの併置を明確に把握する必要があります。 サーバーの併置とデータベース インスタンスの併置の詳細については、「[Server Collocation in a Front End Pool Deployment](https://technet.microsoft.com/library/0516b18d-14c0-4237-9279-0f92e341b1bd.aspx)」および「[Server Collocation in a Standard Edition Server Deployment](https://technet.microsoft.com/library/0763ffab-4fd6-463a-8e62-d97876b376d3.aspx)」を参照してください。


