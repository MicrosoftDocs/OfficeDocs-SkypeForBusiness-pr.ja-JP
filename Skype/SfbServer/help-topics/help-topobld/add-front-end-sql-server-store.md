---
title: フロント エンド SQL Server ストアの追加
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndSqlStorePage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: dace9561-3eb4-4647-83cb-56c246919ae1
description: サーバー Standard Edition展開では、必要なデータベース ソフトウェアとデータベースMicrosoft SQL Server Expressが自動的にSQL Serverされます。 したがって、すべてのオプションが事前設定され、既定の構成を変更できない。
ms.openlocfilehash: a0a6aad58ef7824baf3bc740565a25d056b67211
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/08/2021
ms.locfileid: "60855574"
---
# <a name="add-front-end-sql-server-store"></a>フロント エンド SQL Server ストアの追加

サーバー Standard Edition展開では、必要なデータベース ソフトウェアとデータベースMicrosoft SQL Server Expressが自動的にSQL Serverされます。 したがって、すべてのオプションが事前設定され、既定の構成を変更できない。

Enterprise Edition サーバー展開のフロントエンド プールには、サポートされている 64 ビット 版の SQL Server データベース ソフトウェアが必要です。 以前に定義した SQL Server データベースを選択するか、SQL Server データベースが存在するサーバーの完全修飾ドメイン名 (FQDN) と、新しい SQL Server データベースに使用する SQL Server のインスタンス (既定のインスタンス、または指定する名前付きインスタンス) を指定して、新しい SQL Server データベースを定義できます。 また、サーバー ストアでミラーリングを有効にし、SQL Serverミラーリング監視を指定して自動フェールオーバーを行う方法も選択できます。

サポートの詳細SQL Serverサポートのドキュメントの[「Database Software and Clustering Support」](/previous-versions/office/lync-server-2013/lync-server-2013-database-software-support)を参照してください。 バックエンド データベース用の SQL Server の設定の詳細については、「展開」のドキュメントの「[Lync Server 2010 用 SQL Server の構成](/previous-versions/office/lync-server-2013/lync-server-2013-configure-sql-server-for-lync-server)」を参照してください。

> [!NOTE]
> トポロジの公開に使用されるアカウントに適切なユーザー権限とアクセス許可がある場合は、トポロジを公開するときに、バック エンド データベース (リアルタイム通信 (RTC)) を作成できます。 インストール手順の一部を含め、データベースを後で作成することもできます。

> [!NOTE]
> Enterprise Edition 展開用に SQL Server ベースのサーバーにデータベースをインストールして展開するには、データベース ファイルをインストールする SQL Server ベースのサーバーの SQL Server sysadmins グループのメンバーである必要があります。 SQL Server sysadmins グループのメンバーではない場合は、データベース ファイルが展開されるまでグループへの追加を要求する必要があります。 sysadmins グループのメンバーにできない場合は、データベースを構成および展開するためのスクリプトを SQL Server データベース管理者に提供する必要があります。 手順を実行するために必要なユーザー権限とアクセス許可の詳細については、「展開アクセス許可 for SQL Server」[を参照してください](/previous-versions/office/lync-server-2013/lync-server-2013-deployment-permissions-for-sql-server)。