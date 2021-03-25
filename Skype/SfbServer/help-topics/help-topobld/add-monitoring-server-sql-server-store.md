---
title: 監視サーバー SQL Server ストアを追加する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddMonitoringServerSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d873a2ad-9d3a-4ef6-9f25-ccdd3716218c
description: 監視サーバーでは、監視データを格納するために、サポートされている 64 ビット 版SQL Serverデータベース ソフトウェアが必要です。 監視に使用する定義済みの SQL Server データベースを選択するか、または新しい SQL Server SQL Server データベースが存在するサーバーの完全修飾ドメイン名 (FQDN) を指定して、新しい SQL Server データベースに使用する SQL Server のインスタンス (既定のインスタンスを指定できます) を定義します。、または指定した名前付きインスタンス)。
ms.openlocfilehash: 5c1ef4c7b2474a094492aa7905c044a5da145ff5
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119726"
---
# <a name="add-monitoring-server-sql-server-store"></a>監視サーバー SQL Server ストアの追加

監視サーバーでは、監視データを格納するために、サポートされている 64 ビット 版SQL Serverデータベース ソフトウェアが必要です。 監視に使用する定義済みの SQL Server データベースを選択するか、または新しい SQL Server SQL Server データベースが存在するサーバーの完全修飾ドメイン名 (FQDN) を指定して、新しい SQL Server データベースに使用する SQL Server のインスタンス (既定のインスタンスを指定できます) を定義します。、または指定した名前付きインスタンス)。

サポートの詳細SQL Serverサポートのドキュメントの「 [データベース ソフトウェア](/previous-versions/office/lync-server-2013/lync-server-2013-database-software-support) とクラスタリング サポート」を参照してください。 監視データベースのコロケーションを含む、監視データベースの詳細については、「Supportability」のドキュメント「Planning[for](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-monitoring) Monitoring」の「Supported [Server Location」、](/previous-versions/office/lync-server-2013/lync-server-2013-supported-server-collocation)展開ドキュメントの「SQL Server Data and Log [File Placement」](/previous-versions/office/lync-server-2013/lync-server-2013-sql-server-data-and-log-file-placement)を参照してください。

> [!NOTE]
> トポロジを公開するために使用するアカウントに適切なユーザー権限とアクセス許可がある場合、トポロジを公開するときに監視データベースを作成できます。 インストール手順の一部として、データベースを後で作成することもできます。 > SQL Server ベースのサーバーにデータベースをインストールして展開して監視するには、データベース ファイルをインストールする SQL Server ベースのサーバーの SQL Server sysadmins グループのメンバーである必要があります。 SQL Server sysadmin グループのメンバーではない場合は、データベース ファイルが展開されるまでグループへの追加を要求する必要があります。 sysadmins グループのメンバーにできない場合は、データベースを構成および展開するためのスクリプトを SQL Server データベース管理者に提供する必要があります。 これらの手順を実行するために必要なユーザー権限およびアクセス許可の詳細については、「展開」ドキュメントの「[Deployment Permissions for SQL Server](/previous-versions/office/lync-server-2013/lync-server-2013-deployment-permissions-for-sql-server)」を参照してください。