---
title: フロントエンド アーカイブ ストアを追加する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndArchivingStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ce1723eb-7c93-424a-a622-9c888bf6d3bc
description: アーカイブには、アーカイブ データを格納するために、サポートされている 64 ビット 版Microsoft SQL Serverデータベース ソフトウェアが必要です。 アーカイブに使用する定義済みの SQL Server データベースを選択するか、新しい SQL Server データベースに使用する SQL Server データベースの完全修飾ドメイン名 (FQDN) を指定して、新しい SQL Server データベース (既定のインスタンス、または指定した名前付きインスタンス) に使用する SQL Server のインスタンスを指定します。
ms.openlocfilehash: 46f1d06994ce88800432ca9e653555b05c5756710127ad90d70e624e35bdd8dc
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54321739"
---
# <a name="add-front-end-archiving-store"></a>フロント エンド アーカイブ ストアの追加

アーカイブには、アーカイブ データを格納するために、サポートされている 64 ビット 版Microsoft SQL Serverデータベース ソフトウェアが必要です。 アーカイブに使用する定義済みの SQL Server データベースを選択するか、新しい SQL Server データベースに使用する SQL Server データベースの完全修飾ドメイン名 (FQDN) を指定して、新しい SQL Server データベース (既定のインスタンス、または指定した名前付きインスタンス) に使用する SQL Server のインスタンスを指定します。

> [!NOTE]
> トポロジを公開するために使用するアカウントに適切なユーザー権限とアクセス許可がある場合、トポロジを公開するときに監視データベースを作成できます。インストール手順の一部として、データベースを後で作成することもできます。

> [!NOTE]
> SQL Server ベースのサーバーにデータベースをインストールして展開して監視するには、データベース ファイルをインストールする SQL Server ベースのサーバーの SQL Server sysadmins グループのメンバーである必要があります。 SQL Server sysadmin グループのメンバーではない場合は、データベース ファイルが展開されるまでグループに追加する必要があります。 sysadmins グループのメンバーにできない場合は、データベースを構成および展開するためのスクリプトを SQL Server データベース管理者に提供する必要があります。 これらの手順を実行するために必要なユーザー権限およびアクセス許可の詳細については、「展開」ドキュメントの「[Deployment Permissions for SQL Server](/previous-versions/office/lync-server-2013/lync-server-2013-deployment-permissions-for-sql-server)」を参照してください。