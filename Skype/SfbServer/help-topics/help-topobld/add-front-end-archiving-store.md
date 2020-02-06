---
title: フロントエンド アーカイブ ストアの追加
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.custom:
- ms.lync.tb.AddFrontEndArchivingStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ce1723eb-7c93-424a-a622-9c888bf6d3bc
description: アーカイブには、アーカイブデータを保存するために、Microsoft SQL Server データベースソフトウェアのサポートされている64ビット版が必要です。 アーカイブに使用するために定義済みの SQL Server データベースを選ぶか、sql Server データベースが存在するサーバーの完全修飾ドメイン名 (FQDN) を指定して新しい SQL Server データベースを定義することができます。また、SQL Se のインスタンスについてもかまいません。新しい SQL Server データベース (既定のインスタンスまたは指定した名前付きインスタンス) として使用する rver。
ms.openlocfilehash: e315e27ddb96d018ca0bead13564ad88e944cd34
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41820929"
---
# <a name="add-front-end-archiving-store"></a>フロントエンド アーカイブ ストアの追加

アーカイブには、アーカイブデータを保存するために、Microsoft SQL Server データベースソフトウェアのサポートされている64ビット版が必要です。 アーカイブに使用するために定義済みの SQL Server データベースを選ぶか、sql Server データベースが存在するサーバーの完全修飾ドメイン名 (FQDN) を指定して新しい SQL Server データベースを定義することができます。また、SQL Se のインスタンスについてもかまいません。新しい SQL Server データベース (既定のインスタンスまたは指定した名前付きインスタンス) として使用する rver。

> [!NOTE]
> トポロジの公開に使用したアカウントに適切なユーザー権限と権限がある場合は、トポロジを公開するときに監視データベースを作成することができます。 インストール手順の一部を含め、データベースを後で作成することもできます。

> [!NOTE]
> 監視用に SQL Server ベースのサーバーにデータベースをインストールして展開するには、データベースファイルをインストールする SQL server ベースのサーバーの SQL Server 管理者グループのメンバーである必要があります。 SQL Server sysadmin グループのメンバーでない場合は、データベースファイルが展開されるまで、グループに追加するように依頼する必要があります。 [管理者] グループのメンバーになることができない場合は、SQL Server データベース管理者に、データベースを構成して展開するためのスクリプトを用意する必要があります。 手順を実行するために必要なユーザー権限とアクセス許可の詳細については、展開ドキュメントの「 [SQL Server の展開権限](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx)」を参照してください。


