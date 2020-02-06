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
- NOCSH
ms.custom:
- ms.lync.tb.AddArchivingServerSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 26e0a748-e31d-4c66-b225-b37e0a45408f
description: アーカイブデータを保存するには、アーカイブサーバーでサポートされている64ビット版の SQL Server データベースソフトウェアが必要です。 以前に定義した SQL Server データベースをアーカイブまたは新しい sql Server データベースとして使用するには、SQL Server データベースが存在するサーバーの完全修飾ドメイン名 (FQDN) を指定し、次のような SQL Server データベースを作成することができます。新しい SQL Server データベース (既定のインスタンスまたは指定した名前付きインスタンス) に使用します。
ms.openlocfilehash: d4fcb526abf0eb1ef961f5790b574a9f30a80b87
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41821289"
---
# <a name="add-archiving-server-sql-server-store"></a>アーカイブ サーバー SQL Server ストアの追加

アーカイブデータを保存するには、アーカイブサーバーでサポートされている64ビット版の SQL Server データベースソフトウェアが必要です。 以前に定義した SQL Server データベースをアーカイブまたは新しい sql Server データベースとして使用するには、SQL Server データベースが存在するサーバーの完全修飾ドメイン名 (FQDN) を指定し、次のような SQL Server データベースを作成することができます。新しい SQL Server データベース (既定のインスタンスまたは指定した名前付きインスタンス) に使用します。

> [!NOTE]
> トポロジを公開するために使用されるアカウントに適切なユーザー権限と権限がある場合は、トポロジを公開するときにアーカイブデータベース (LcsLog) を作成できます。 また、インストール手順の一部として、またはその他の方法でデータベースを作成することもできます。

> [!NOTE]
> アーカイブのために SQL Server ベースのサーバーにデータベースをインストールして展開するには、データベースファイルをインストールする SQL server ベースのサーバーの SQL Server の [の機能] グループのメンバーである必要があります。 SQL Server の [ユーザー名] グループのメンバーでない場合は、データベースファイルが展開されるまで、グループに追加するように依頼する必要があります。 [管理者] グループのメンバーになることができない場合は、SQL Server データベース管理者に、データベースを構成して展開するためのスクリプトを用意する必要があります。 手順を実行するために必要なユーザー権限とアクセス許可の詳細については、展開ドキュメントの「 [SQL Server の展開権限](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx)」を参照してください。


