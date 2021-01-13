---
title: フロント エンド SQL Server ストアの追加
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: dace9561-3eb4-4647-83cb-56c246919ae1
ROBOTS: NOINDEX, NOFOLLOW
description: Standard Edition サーバーの展開では、Express データベース ソフトウェアと Microsoft SQL Serverデータベースに必要なSQL Serverインストールされます。 したがって、すべてのオプションが事前に設定され、既定の構成を変更できない。
ms.openlocfilehash: d1a3fd6a27ab6229f84e8b74259be6a2da7652f0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49811637"
---
# <a name="add-front-end-sql-server-store"></a>フロント エンド SQL Server ストアの追加

Standard Edition サーバーの展開では、必要な Microsoft SQL Server Express データベース ソフトウェアと SQL Serverインストールされます。 したがって、すべてのオプションが事前に設定され、既定の構成を変更できない。

Enterprise Edition サーバー展開のフロントエンド プールには、サポートされている 64 ビット版の SQL Server データベース ソフトウェアが必要です。 バック エンド データベースに使用する定義済みの SQL Server データベースを選択するか、または SQL Server データベースが存在するサーバーの完全修飾ドメイン名 (FQDN) と、新しい SQL Server データベースに使用する SQL Server のインスタンス (既定のインスタンス) を指定して、新しい SQL Server データベースを定義できます。、または指定した名前付きインスタンス)。 また、SQL Server ストアでミラーリングを有効にし、自動フェールオーバーのミラーリング監視を指定できます。

サポートの詳細SQL Serverサポート」のドキュメントの「 [データベース](https://technet.microsoft.com/library/e05d0032-bbea-4e61-987d-d07b1c045fd5.aspx) ソフトウェアとクラスタリングのサポート」を参照してください。 バック エンド データベースのSQL Server設定の詳細については、「展開」のドキュメントの[](https://technet.microsoft.com/library/375e5cc4-e436-46dc-9b02-5063f35cdcc1.aspx)「SQL Server」を参照してください。

> [!NOTE]
> トポロジの公開に使用するアカウントに適切なユーザー権限とアクセス許可がある場合は、トポロジを公開するときに、バック エンド データベース (リアルタイム通信 (RTC)) を作成できます。 インストール手順の一部を含め、データベースを後で作成することもできます。

> [!NOTE]
> Enterprise Edition 展開用に SQL Server ベースのサーバーにデータベースをインストールして展開するには、データベース ファイルをインストールする SQL Server ベースのサーバーの SQL Server sysadmins グループのメンバーである必要があります。 SQL Server sysadmins グループのメンバーではない場合は、データベース ファイルが展開されるまでグループへの追加を要求する必要があります。 sysadmins グループのメンバーにできない場合は、データベースを構成および展開するためのスクリプトを SQL Server データベース管理者に提供する必要があります。 手順を実行するために必要なユーザー権限とアクセス許可の詳細については、「展開のアクセス許可」 [を](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx)参照SQL Server。


