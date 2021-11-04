---
title: SQL ストアを追加する
ms.reviewer: ''
ms.author: v-mahoffman
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
ms.localizationpriority: medium
ms.assetid: 8ec39dfc-c58d-4fdb-b61e-f71dd691cef8
description: 新しい SQL ストアを定義するには、SQL Server ベースのデータベースと SQL Server のインスタンス (既定のインスタンスまたは名前付きインスタンス) を指定します。
ms.openlocfilehash: 1e72569385a4cabf02cdaf1ddd71fd56ecc34909
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/04/2021
ms.locfileid: "60770495"
---
# <a name="add-sql-store"></a>SQL ストアの追加

新しい SQL ストアを定義するには、SQL Server ベースのデータベースと SQL Server のインスタンス (既定のインスタンスまたは名前付きインスタンス) を指定します。

定義するデータベース インスタンスをホストするSQL Serverの完全修飾ドメイン名 (FQDN) を指定します。

データをホストするSQL Serverインスタンスを指定します。 既定のインスタンスを指定するか、名前付きインスタンスを指定できます。

特定のインスタンスにおけるデータベースの併置を明確に把握する必要があります。サーバーの併置とデータベース インスタンスの併置の詳細については、「[Server Collocation in a Front End Pool Deployment](/previous-versions/office/lync-server-2013/lync-server-2013-server-collocation-in-an-enterprise-edition-front-end-pool-deployment)」および「[Server Collocation in a Standard Edition Server Deployment](/previous-versions/office/lync-server-2013/lync-server-2013-server-collocation-in-a-standard-edition-server-deployment)」を参照してください。