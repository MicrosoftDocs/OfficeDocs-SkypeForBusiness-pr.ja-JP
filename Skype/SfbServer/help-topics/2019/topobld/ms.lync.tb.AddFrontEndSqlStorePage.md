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
description: Standard Edition サーバーの展開では、Express データベース ソフトウェアとデータベースに必要Microsoft SQL Serverが自動的にSQL Serverされます。 したがって、すべてのオプションが事前設定され、既定の構成を変更できない。
ms.openlocfilehash: 6861fd20c8f3e164a4d8d713dfc725bd2f949acd
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51118676"
---
# <a name="add-front-end-sql-server-store"></a>フロント エンド SQL Server ストアの追加

Standard Edition サーバーの展開では、Express データベース ソフトウェアとデータベースに必要Microsoft SQL Serverが自動的にSQL Serverされます。 したがって、すべてのオプションが事前設定され、既定の構成を変更できない。

Enterprise Edition サーバー展開のフロントエンド プールには、サポートされている 64 ビット 版の SQL Server データベース ソフトウェアが必要です。 以前に定義した SQL Server データベースを選択するか、SQL Server データベースが存在するサーバーの完全修飾ドメイン名 (FQDN) と、新しい SQL Server データベースに使用する SQL Server のインスタンス (既定のインスタンスを指定できる) を指定して、新しい SQL Server データベースを定義できます。、または指定した名前付きインスタンス)。 また、サーバー ストアでミラーリングを有効にし、SQL Serverミラーリング監視を指定して自動フェールオーバーを行う方法も選択できます。

サポートの詳細SQL Serverサポートのドキュメントの「 [データベース ソフトウェア](/previous-versions/office/lync-server-2013/lync-server-2013-database-software-support) とクラスタリング サポート」を参照してください。 バック エンド データベースのSQL Server設定の詳細については、「 [展開](/previous-versions/office/lync-server-2013/lync-server-2013-configure-sql-server-for-lync-server) 」のドキュメントSQL Serverを参照してください。

> [!NOTE]
> トポロジの公開に使用されるアカウントに適切なユーザー権限とアクセス許可がある場合は、トポロジを公開するときに、バック エンド データベース (リアルタイム通信 (RTC)) を作成できます。 インストール手順の一部を含め、データベースを後で作成することもできます。

> [!NOTE]
> エンタープライズ エディション展開用の SQL Server ベースのサーバーにデータベースをインストールして展開するには、データベース ファイルをインストールする SQL Server ベースのサーバーの SQL Server sysadmins グループのメンバーである必要があります。 SQL Server sysadmins グループのメンバーではない場合は、データベース ファイルが展開されるまでグループへの追加を要求する必要があります。 sysadmins グループのメンバーにできない場合は、データベースを構成および展開するためのスクリプトを SQL Server データベース管理者に提供する必要があります。 手順を実行するために必要なユーザー権限とアクセス許可の詳細については、「展開アクセス許可 for SQL Server」 [を参照してください](/previous-versions/office/lync-server-2013/lync-server-2013-deployment-permissions-for-sql-server)。