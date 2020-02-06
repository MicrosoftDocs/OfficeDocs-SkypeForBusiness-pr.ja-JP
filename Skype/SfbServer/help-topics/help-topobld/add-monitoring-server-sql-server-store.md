---
title: 監視サーバー SQL Server ストアの追加
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
- ms.lync.tb.AddMonitoringServerSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d873a2ad-9d3a-4ef6-9f25-ccdd3716218c
description: Monitoring Server には、監視データを保存するために、サポートされている64ビット版の SQL Server データベースソフトウェアが必要です。 監視に使用するために定義済みの SQL Server データベースを選択するか、sql Server データベースが存在するサーバーの完全修飾ドメイン名 (FQDN) を指定して新しい sql Server データベースを定義することができます。また、SQL server データベースは、SQL のインスタンスにも含まれます。新しい SQL Server データベースに使用するサーバー (既定のインスタンス、または指定した名前付きインスタンスのいずれか)。
ms.openlocfilehash: f1950b01aba29ddff6c7622a6fead726bf835ef3
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41820749"
---
# <a name="add-monitoring-server-sql-server-store"></a>監視サーバー SQL Server ストアの追加

Monitoring Server には、監視データを保存するために、サポートされている64ビット版の SQL Server データベースソフトウェアが必要です。 監視に使用するために定義済みの SQL Server データベースを選択するか、sql Server データベースが存在するサーバーの完全修飾ドメイン名 (FQDN) を指定して新しい sql Server データベースを定義することができます。また、SQL server データベースは、SQL のインスタンスにも含まれます。新しい SQL Server データベースに使用するサーバー (既定のインスタンス、または指定した名前付きインスタンスのいずれか)。

SQL Server のサポートについて詳しくは、「サポートドキュメント」の「[データベースソフトウェアとクラスタリングのサポート](https://technet.microsoft.com/library/e05d0032-bbea-4e61-987d-d07b1c045fd5.aspx)」をご覧ください。 監視データベースの collocation などの監視データベースの詳細については、「[サポートされているサーバーの場所](https://technet.microsoft.com/library/3be990a1-5485-4b83-b73f-947ac97821f9.aspx)」を参照してください。計画ドキュメントの[監視の計画](https://technet.microsoft.com/library/26cead5a-183c-42f1-a4b0-0e8d61c6159d.aspx)、展開ドキュメントの[SQL Server データとログファイルの配置](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx)について説明します。

> [!NOTE]
> トポロジの公開に使用したアカウントに適切なユーザー権限と権限がある場合は、トポロジを公開するときに監視データベースを作成することができます。 また、インストール手順の一部として、後でデータベースを作成することもできます。 監視のために SQL Server ベースのサーバーにデータベースをインストールして展開する >、データベースファイルをインストールする SQL server ベースのサーバーの SQL Server 管理者グループのメンバーである必要があります。 SQL Server sysadmin グループのメンバーでない場合は、データベースファイルが展開されるまで、グループに追加するように依頼する必要があります。 [管理者] グループのメンバーになることができない場合は、SQL Server データベース管理者に、データベースを構成して展開するためのスクリプトを用意する必要があります。 これらの手順を実行するために必要なユーザー権限と権限の詳細については、「展開ドキュメントの[SQL Server の展開権限](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx)」を参照してください。


