---
title: サーバーの SQL Server ストアにアーカイブを追加します。
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddArchivingServerSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 26e0a748-e31d-4c66-b225-b37e0a45408f
description: アーカイブ サーバーには、アーカイブ ・ データを格納する SQL Server データベース ソフトウェアのサポートされている 64 ビット版が必要です。 アーカイブに使用するか、SQL Server データベースが格納されているサーバーと SQL Server のインスタンスの完全修飾ドメイン名 (FQDN) を指定することで新しい SQL Server データベースを定義する定義済みの SQL Server データベースを選択するかを新しい SQL Server データベース (既定のインスタンスまたは名前付きインスタンスを指定することができます) を使用するには。
ms.openlocfilehash: 80b77efdda5f2a844f92d30fe76a584e8ef25b7e
ms.sourcegitcommit: 08cf97296fb9ba6fbc4d68c3e380c8f37e86dd02
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/21/2018
ms.locfileid: "19988986"
---
# <a name="add-archiving-server-sql-server-store"></a>サーバーの SQL Server ストアにアーカイブを追加します。
 
アーカイブ サーバーには、アーカイブ ・ データを格納する SQL Server データベース ソフトウェアのサポートされている 64 ビット版が必要です。 アーカイブに使用するか、SQL Server データベースが格納されているサーバーと SQL Server のインスタンスの完全修飾ドメイン名 (FQDN) を指定することで新しい SQL Server データベースを定義する定義済みの SQL Server データベースを選択するかを新しい SQL Server データベース (既定のインスタンスまたは名前付きインスタンスを指定することができます) を使用するには。
  
> [!NOTE]
> トポロジを公開するために使用するアカウントに適切なユーザー権利とアクセス許可がある場合、トポロジを公開するときにアーカイブ データベース (LcsLog) を作成できます。 以降では、インストール手順の一部として、データベースを作成することもできます。 または、それ以外の場合。 
  
> [!NOTE]
> インストールして、アーカイブのための SQL Server ベースのサーバー上のデータベースを展開、データベース ファイルをインストールしている SQL Server ベースのサーバーの SQL Server システム管理者グループのメンバーをする必要があります。 SQL Server のシステム管理者グループのメンバーでない場合は、データベース ファイルを展開するまでに、グループに追加する要求する必要があります。 システム管理者グループのメンバーにすることはできません、スクリプトを構成して、データベースを配置すると、SQL Server データベースの管理者を入力してください。 ユーザー権利とアクセス許可の手順を実行する必要があるについての詳細は、展開に関するドキュメントで[SQL Server の展開のアクセス許可](http://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx)を参照してください。
  

