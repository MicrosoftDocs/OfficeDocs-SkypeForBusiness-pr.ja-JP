---
title: 監視サーバー SQL Server ストアを追加する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddMonitoringServerSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d873a2ad-9d3a-4ef6-9f25-ccdd3716218c
ROBOTS: NOINDEX, NOFOLLOW
description: 監視サーバーには、監視データを格納するために、サポートされている 64 ビットSQL Serverデータベース ソフトウェアが必要です。 監視に使用する定義済みの SQL Server データベースを選択するか、新しい SQL Server データベースが存在するサーバーの完全修飾ドメイン名 (FQDN) と、新しい SQL Server データベースに使用する SQL Server のインスタンス (既定のインスタンス) を指定して、新しい SQL Server データベースを定義できます。、または指定した名前付きインスタンス)。
ms.openlocfilehash: a96dced5bfae5e8381ea28874d295dcfe146d33e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49807737"
---
# <a name="add-monitoring-server-sql-server-store"></a>監視サーバー SQL Server ストアの追加

監視サーバーには、監視データを格納するために、サポートされている 64 ビットSQL Serverデータベース ソフトウェアが必要です。 監視に使用する定義済みの SQL Server データベースを選択するか、新しい SQL Server データベースが存在するサーバーの完全修飾ドメイン名 (FQDN) と、新しい SQL Server データベースに使用する SQL Server SQL Server のインスタンス (既定のインスタンス) を指定して、新しい SQL Server データベースを定義できます。、または指定した名前付きインスタンス)。

サポートの詳細SQL Serverサポート」のドキュメントの「 [データベース](https://technet.microsoft.com/library/e05d0032-bbea-4e61-987d-d07b1c045fd5.aspx) ソフトウェアとクラスタリングのサポート」を参照してください。 監視データベースの配置など、監視データベースの詳細については、「サポート」のドキュメント[](https://technet.microsoft.com/library/3be990a1-5485-4b83-b73f-947ac97821f9.aspx)の「サポートされるサーバーの場所」、計画に関するドキュメントの「Planning[for Monitoring」、](https://technet.microsoft.com/library/26cead5a-183c-42f1-a4b0-0e8d61c6159d.aspx)および「展開」のドキュメントの[「SQL Server Data and Log File Placement」](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx)を参照してください。

> [!NOTE]
> トポロジを公開するために使用するアカウントに適切なユーザー権限とアクセス許可がある場合、トポロジを公開するときに監視データベースを作成できます。 インストール手順の一部として、データベースを後で作成することもできます。 >監視用に SQL Server ベースのサーバーにデータベースをインストールして展開するには、データベース ファイルをインストールする SQL Server ベースのサーバーの SQL Server sysadmins グループのメンバーである必要があります。 SQL Server sysadmin グループのメンバーではない場合は、データベース ファイルが展開されるまでグループへの追加を要求する必要があります。 sysadmins グループのメンバーにできない場合は、データベースを構成および展開するためのスクリプトを SQL Server データベース管理者に提供する必要があります。 これらの手順を実行するために必要なユーザー権限およびアクセス許可の詳細については、「展開」ドキュメントの「[Deployment Permissions for SQL Server](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx)」を参照してください。


