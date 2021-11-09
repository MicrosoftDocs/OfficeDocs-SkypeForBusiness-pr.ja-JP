---
title: 監視サーバー SQL Server ストアを追加する
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddMonitoringServerSqlStorePage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: d873a2ad-9d3a-4ef6-9f25-ccdd3716218c
description: 監視サーバーでは、監視データを格納するために、サポートされている 64 ビット 版SQL Serverデータベース ソフトウェアが必要です。 監視に使用する定義済みの SQL Server データベースを選択するか、または新しい SQL Server データベースが存在するサーバーの完全修飾ドメイン名 (FQDN) を指定して、新しい SQL Server データベース (既定のインスタンス、または指定した名前付きインスタンス) に使用する SQL Server のインスタンスを指定して、新しい SQL Server データベースを定義できます。
ms.openlocfilehash: b4c5617d125208924554b2420de18c026288ecfc
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/08/2021
ms.locfileid: "60834265"
---
# <a name="add-monitoring-server-sql-server-store"></a>監視サーバー SQL Server ストアの追加

監視サーバーでは、監視データを格納するために、サポートされている 64 ビット 版SQL Serverデータベース ソフトウェアが必要です。 監視に使用する定義済みの SQL Server データベースを選択するか、または新しい SQL Server データベースが存在するサーバーの完全修飾ドメイン名 (FQDN) を指定して、新しい SQL Server データベース (既定のインスタンス、または指定した名前付きインスタンス) に使用する SQL Server のインスタンスを指定して、新しい SQL Server データベースを定義できます。

サポートの詳細SQL Serverサポートのドキュメントの[「Database Software and Clustering Support」](/previous-versions/office/lync-server-2013/lync-server-2013-database-software-support)を参照してください。 監視データベースのコロケーションを含む監視データベースの詳細については、「Supportability」のドキュメント「Planning[for](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-monitoring) Monitoring」の「サポートされるサーバーの場所」および「展開」のドキュメントの「SQL Server Data and Log [File Placement」](/previous-versions/office/lync-server-2013/lync-server-2013-sql-server-data-and-log-file-placement)を参照してください。 [](/previous-versions/office/lync-server-2013/lync-server-2013-supported-server-collocation)

> [!NOTE]
> トポロジを公開するために使用するアカウントに適切なユーザー権限とアクセス許可がある場合、トポロジを公開するときに監視データベースを作成できます。 インストール手順の一部として、データベースを後で作成することもできます。 > SQL Server ベースのサーバーにデータベースをインストールして展開して監視するには、データベース ファイルをインストールする SQL Server ベースのサーバーの SQL Server sysadmins グループのメンバーである必要があります。 SQL Server sysadmin グループのメンバーではない場合は、データベース ファイルが展開されるまでグループへの追加を要求する必要があります。 sysadmins グループのメンバーにできない場合は、データベースを構成および展開するためのスクリプトを SQL Server データベース管理者に提供する必要があります。 これらの手順を実行するために必要なユーザー権限およびアクセス許可の詳細については、「展開」ドキュメントの「[Deployment Permissions for SQL Server](/previous-versions/office/lync-server-2013/lync-server-2013-deployment-permissions-for-sql-server)」を参照してください。