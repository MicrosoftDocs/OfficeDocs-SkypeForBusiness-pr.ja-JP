---
title: フロントエンド SQL Server ストアの追加
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.AddFrontEndSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: dace9561-3eb4-4647-83cb-56c246919ae1
ROBOTS: NOINDEX, NOFOLLOW
description: Standard Edition サーバーの展開では、必要な Microsoft SQL Server Express データベースソフトウェアと SQL Server データベースが自動的にインストールされます。 そのため、すべてのオプションがあらかじめ設定されているため、既定の構成を変更することはできません。
ms.openlocfilehash: b7f76eca506160013b4b7db5e60ea1cc298511b4
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2020
ms.locfileid: "41689226"
---
# <a name="add-front-end-sql-server-store"></a>フロントエンド SQL Server ストアの追加

Standard Edition サーバーの展開では、必要な Microsoft SQL Server Express データベースソフトウェアと SQL Server データベースが自動的にインストールされます。 そのため、すべてのオプションがあらかじめ設定されているため、既定の構成を変更することはできません。

Enterprise Edition server 展開のフロントエンドプールには、バックエンドデータベース用の SQL Server データベースソフトウェアのサポートされている64ビット版が必要です。 バックエンドデータベースとして使用するために定義済みの SQL Server データベースを選ぶか、SQL Server データベースが配置されているサーバーの完全修飾ドメイン名 (FQDN) を指定して新しい sql Server データベースを定義するか、SQL S のインスタンスを指定することができます。新しい SQL Server データベース (既定のインスタンスまたは指定した名前付きインスタンス) として使用するサーバー。 SQL Server ストアでミラーリングを有効にし、自動フェールオーバーのミラーリング監視を指定することもできます。

SQL Server のサポートについて詳しくは、「サポートドキュメント」の「[データベースソフトウェアとクラスタリングのサポート](https://technet.microsoft.com/library/e05d0032-bbea-4e61-987d-d07b1c045fd5.aspx)」をご覧ください。 バックエンドデータベース用の SQL Server のセットアップの詳細については、「展開ドキュメントで[Sql server を構成する](https://technet.microsoft.com/library/375e5cc4-e436-46dc-9b02-5063f35cdcc1.aspx)」を参照してください。

> [!NOTE]
> トポロジを公開するために使用されるアカウントに適切なユーザー権限と権限がある場合は、トポロジを公開するときにバックエンドデータベース (リアルタイム通信 (RTC)) を作成することができます。 また、インストール手順の一部として、後でデータベースを作成することもできます。

> [!NOTE]
> Enterprise Edition の展開のために SQL Server ベースのサーバーにデータベースをインストールして展開するには、データベースファイルをインストールする SQL server ベースのサーバーの SQL Server 管理者グループのメンバーである必要があります。 SQL Server の [ユーザー名] グループのメンバーでない場合は、データベースファイルが展開されるまで、グループに追加するように依頼する必要があります。 [管理者] グループのメンバーになることができない場合は、SQL Server データベース管理者に、データベースを構成して展開するためのスクリプトを用意する必要があります。 手順を実行するために必要なユーザー権限と権限の詳細については、「 [SQL Server の展開権限](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx)」を参照してください。


