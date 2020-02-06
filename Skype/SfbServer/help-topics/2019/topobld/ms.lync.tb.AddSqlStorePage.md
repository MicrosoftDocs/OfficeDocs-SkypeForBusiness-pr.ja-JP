---
title: SQL ストアの追加
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 新しい SQL ストアを定義するには、SQL Server ベースのデータベースと SQL Server のインスタンス (既定のインスタンスまたは名前付きインスタンスのいずれか) を指定する必要があります。その場合は、次のように指定します。
ms.openlocfilehash: 80fb2fbbf1bad7a160df087969c9820ed05ebeea
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41794326"
---
# <a name="add-sql-store"></a>SQL ストアの追加

新しい SQL ストアを定義するには、SQL Server ベースのデータベースと SQL Server のインスタンス (既定のインスタンスまたは名前付きインスタンスのいずれか) を指定する必要があります。その場合は、次のように指定します。

定義するデータベースインスタンスをホストする SQL Server の完全修飾ドメイン名 (FQDN) を指定します。

データをホストする SQL Server のインスタンスを指定します。 既定のインスタンスを指定することも、名前付きインスタンスを指定することもできます。

特定のインスタンスでのデータベースの collocation は、非常に明確に理解しておく必要があります。 サーバーの collocation とデータベースインスタンスの collocation の詳細については、「[フロントエンドプールの展開のサーバー Collocation](https://technet.microsoft.com/library/0516b18d-14c0-4237-9279-0f92e341b1bd.aspx) 」および「 [Standard Edition server の展開におけるサーバーの場所](https://technet.microsoft.com/library/0763ffab-4fd6-463a-8e62-d97876b376d3.aspx)」を参照してください。


