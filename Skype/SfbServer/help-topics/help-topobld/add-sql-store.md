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
- ms.lync.tb.AddSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8ec39dfc-c58d-4fdb-b61e-f71dd691cef8
description: 新しい SQL ストアを定義するには、SQL Server ベースのデータベースと SQL Server のインスタンス (既定のインスタンスまたは名前付きインスタンスのいずれか) を指定する必要があります。その場合は、次のように指定します。
ms.openlocfilehash: 10fca86e0d132a482636cd9f83f3a893f8380b4a
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2020
ms.locfileid: "41697972"
---
# <a name="add-sql-store"></a>SQL ストアの追加

新しい SQL ストアを定義するには、SQL Server ベースのデータベースと SQL Server のインスタンス (既定のインスタンスまたは名前付きインスタンスのいずれか) を指定する必要があります。その場合は、次のように指定します。

定義するデータベースインスタンスをホストする SQL Server の完全修飾ドメイン名 (FQDN) を指定します。

データをホストする SQL Server のインスタンスを指定します。 既定のインスタンスを指定することも、名前付きインスタンスを指定することもできます。

特定のインスタンスでのデータベースの collocation は、非常に明確に理解しておく必要があります。 サーバーの collocation とデータベースインスタンスの collocation の詳細については、「[フロントエンドプールの展開のサーバー Collocation](https://technet.microsoft.com/library/0516b18d-14c0-4237-9279-0f92e341b1bd.aspx) 」および「 [Standard Edition server の展開におけるサーバーの場所](https://technet.microsoft.com/library/0763ffab-4fd6-463a-8e62-d97876b376d3.aspx)」を参照してください。


