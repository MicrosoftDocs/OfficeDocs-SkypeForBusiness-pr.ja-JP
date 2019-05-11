---
title: アーカイブ サーバー SQL Server ストアの追加
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/8/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddArchivingServerSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 26e0a748-e31d-4c66-b225-b37e0a45408f
description: アーカイブ サーバーには、アーカイブ ・ データを格納する SQL Server データベース ソフトウェアのサポートされている 64 ビット版が必要です。 アーカイブに使用するか、SQL Server データベースが格納されているサーバーと SQL Server のインスタンスの完全修飾ドメイン名 (FQDN) を指定することで新しい SQL Server データベースを定義する定義済みの SQL Server データベースを選択するかを新しい SQL Server データベース (既定のインスタンスまたは名前付きインスタンスを指定することができます) を使用するには。
ms.openlocfilehash: 54a51ad26be95a4657e4e04d84fd0246a58849ac
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33886636"
---
# <a name="add-archiving-server-sql-server-store"></a>アーカイブ サーバー SQL Server ストアの追加

アーカイブ サーバーには、アーカイブ ・ データを格納する SQL Server データベース ソフトウェアのサポートされている 64 ビット版が必要です。 アーカイブに使用するか、SQL Server データベースが格納されているサーバーと SQL Server のインスタンスの完全修飾ドメイン名 (FQDN) を指定することで新しい SQL Server データベースを定義する定義済みの SQL Server データベースを選択するかを新しい SQL Server データベース (既定のインスタンスまたは名前付きインスタンスを指定することができます) を使用するには。

> [!NOTE]
> トポロジを公開するために使用するアカウントに適切なユーザー権利とアクセス許可がある場合、トポロジを公開するときにアーカイブ データベース (LcsLog) を作成できます。 以降では、インストール手順の一部として、データベースを作成することもできます。 または、それ以外の場合。

> [!NOTE]
> インストールして、アーカイブのための SQL Server ベースのサーバー上のデータベースを展開、データベース ファイルをインストールしている SQL Server ベースのサーバーの SQL Server システム管理者グループのメンバーをする必要があります。 SQL Server のシステム管理者グループのメンバーでない場合は、データベース ファイルを展開するまでに、グループに追加する要求する必要があります。 システム管理者グループのメンバーにすることはできません、スクリプトを構成して、データベースを配置すると、SQL Server データベースの管理者を入力してください。 ユーザー権利とアクセス許可の手順を実行する必要があるについての詳細は、展開に関するドキュメントで[SQL Server の展開のアクセス許可](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx)を参照してください。


