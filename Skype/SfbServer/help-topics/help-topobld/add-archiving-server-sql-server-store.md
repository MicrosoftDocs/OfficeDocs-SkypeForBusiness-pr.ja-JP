---
title: アーカイブ サーバー SQL Server ストアの追加
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddArchivingServerSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 26e0a748-e31d-4c66-b225-b37e0a45408f
description: アーカイブサーバーには、アーカイブデータを格納するために、サポートされている64ビット版の SQL Server データベースソフトウェアが必要です。 アーカイブに使用するために定義済みの SQL Server データベースを選択するか、SQL server データベースが存在するサーバーの完全修飾ドメイン名 (FQDN) を指定して新しい sql server データベースを定義するか、または新しい sql server データベースで使用する SQL Server のインスタンス (指定した既定のインスタンスまたは名前付きインスタンス) を指定します。
ms.openlocfilehash: eb25152916c61ff40274705a408fe0a7a618cbcc
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2020
ms.locfileid: "48217438"
---
# <a name="add-archiving-server-sql-server-store"></a>アーカイブ サーバー SQL Server ストアの追加

アーカイブサーバーには、アーカイブデータを格納するために、サポートされている64ビット版の SQL Server データベースソフトウェアが必要です。 アーカイブに使用するために定義済みの SQL Server データベースを選択するか、SQL server データベースが存在するサーバーの完全修飾ドメイン名 (FQDN) を指定して新しい sql server データベースを定義するか、または新しい sql server データベースで使用する SQL Server のインスタンス (指定した既定のインスタンスまたは名前付きインスタンス) を指定します。

> [!NOTE]
> トポロジの公開に使用するアカウントに適切なユーザー権限とアクセス許可があれば、トポロジの発行時にアーカイブ データベース (LcsLog) を作成できます。インストール手順の一部として実行するなど、データベースを後で作成することもできます。

> [!NOTE]
> アーカイブ用に SQL Server ベースのサーバーにデータベースをインストールして展開するには、データベースファイルをインストールする sql server ベースのサーバーの SQL Server の [ユーザー] グループのメンバーである必要があります。 SQL Server の [ユーザー] グループのメンバーでない場合は、データベースファイルが展開されるまで、グループに追加するよう要求する必要があります。 システム管理者グループのメンバーになることができない場合は、データベースを構成および展開するためのスクリプトを SQL Server データベース管理者に提供する必要があります。 これらの手順を実行するために必要なユーザー権限およびアクセス許可の詳細については、「展開」ドキュメントの「[Deployment Permissions for SQL Server](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx)」を参照してください。


