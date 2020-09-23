---
title: フロントエンド SQL Server ストアの追加
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
- ms.lync.tb.AddFrontEndSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: dace9561-3eb4-4647-83cb-56c246919ae1
description: Standard Edition サーバーの展開では、必要な Microsoft SQL Server Express データベースソフトウェアと SQL Server データベースが自動的にインストールされます。 そのため、すべてのオプションが事前に設定されており、既定の構成を変更することはできません。
ms.openlocfilehash: 614c3a852bb52a73c8a3f71ee467a2d71f82e9b6
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2020
ms.locfileid: "48216498"
---
# <a name="add-front-end-sql-server-store"></a>フロントエンド SQL Server ストアの追加

Standard Edition サーバーの展開では、必要な Microsoft SQL Server Express データベースソフトウェアと SQL Server データベースが自動的にインストールされます。 そのため、すべてのオプションが事前に設定されており、既定の構成を変更することはできません。

Enterprise Edition サーバー展開のフロントエンドプールでは、バックエンドデータベース用にサポートされている64ビット版の SQL Server データベースソフトウェアが必要です。 以前に定義した SQL Server データベースをバックエンドデータベースに使用するように選択するか、または SQL server データベースを配置するサーバーの完全修飾ドメイン名 (FQDN) を指定して新しい SQL Server データベースを定義するか、または新しい sql server データベースで使用する SQL server のインスタンス (既定のインスタンスにすることができます。、または指定した名前付きインスタンス)。 また、SQL Server ストアでミラーリングを有効にし、自動フェールオーバーのミラーリング監視を指定することもできます。

SQL Server のサポートの詳細については、「サポート」のドキュメントの「 [データベースソフトウェアとクラスタリングのサポート](https://technet.microsoft.com/library/e05d0032-bbea-4e61-987d-d07b1c045fd5.aspx) 」を参照してください。 バックエンド データベース用の SQL Server の設定の詳細については、「展開」のドキュメントの「[Lync Server 2010 用 SQL Server の構成](https://technet.microsoft.com/library/375e5cc4-e436-46dc-9b02-5063f35cdcc1.aspx)」を参照してください。

> [!NOTE]
> トポロジの公開に使用されるアカウントに適切なユーザー権限とアクセス許可がある場合は、トポロジを公開するときにバックエンドデータベース (リアルタイム通信 (RTC)) を作成できます。 インストール手順の一部を含め、データベースを後で作成することもできます。

> [!NOTE]
> Enterprise Edition 展開用の SQL Server ベースのサーバーにデータベースをインストールして展開するには、データベースファイルをインストールする sql server ベースのサーバーの SQL server 管理者グループのメンバーである必要があります。 SQL Server の [ユーザー] グループのメンバーでない場合は、データベースファイルが展開されるまで、グループに追加するよう要求する必要があります。 システム管理者グループのメンバーになることができない場合は、データベースを構成および展開するためのスクリプトを SQL Server データベース管理者に提供する必要があります。 手順を実行するために必要なユーザー権限とアクセス許可の詳細については、「 [SQL Server の展開権限](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx)」を参照してください。


