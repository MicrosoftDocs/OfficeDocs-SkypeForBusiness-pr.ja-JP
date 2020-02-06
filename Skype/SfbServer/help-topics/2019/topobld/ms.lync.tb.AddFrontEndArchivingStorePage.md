---
title: フロントエンド アーカイブ ストアの追加
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndArchivingStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ce1723eb-7c93-424a-a622-9c888bf6d3bc
ROBOTS: NOINDEX, NOFOLLOW
description: アーカイブには、アーカイブデータを保存するために、Microsoft SQL Server データベースソフトウェアのサポートされている64ビット版が必要です。 アーカイブに使用するために定義済みの SQL Server データベースを選ぶか、sql Server データベースが存在するサーバーの完全修飾ドメイン名 (FQDN) を指定して新しい SQL Server データベースを定義することができます。また、SQL Se のインスタンスについてもかまいません。新しい SQL Server データベース (既定のインスタンスまたは指定した名前付きインスタンス) として使用する rver。
ms.openlocfilehash: 234d0a2d4ef14aa969b8ef8c7445558e53ca2fee
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41794906"
---
# <a name="add-front-end-archiving-store"></a>フロントエンド アーカイブ ストアの追加

アーカイブには、アーカイブデータを保存するために、Microsoft SQL Server データベースソフトウェアのサポートされている64ビット版が必要です。 アーカイブに使用するために定義済みの SQL Server データベースを選ぶか、sql Server データベースが存在するサーバーの完全修飾ドメイン名 (FQDN) を指定して新しい SQL Server データベースを定義することができます。また、SQL Se のインスタンスについてもかまいません。新しい SQL Server データベース (既定のインスタンスまたは指定した名前付きインスタンス) として使用する rver。

> [!NOTE]
> トポロジの公開に使用したアカウントに適切なユーザー権限と権限がある場合は、トポロジを公開するときに監視データベースを作成することができます。 インストール手順の一部を含め、データベースを後で作成することもできます。

> [!NOTE]
> 監視用に SQL Server ベースのサーバーにデータベースをインストールして展開するには、データベースファイルをインストールする SQL server ベースのサーバーの SQL Server 管理者グループのメンバーである必要があります。 SQL Server sysadmin グループのメンバーでない場合は、データベースファイルが展開されるまで、グループに追加するように依頼する必要があります。 [管理者] グループのメンバーになることができない場合は、SQL Server データベース管理者に、データベースを構成して展開するためのスクリプトを用意する必要があります。 手順を実行するために必要なユーザー権限とアクセス許可の詳細については、展開ドキュメントの「 [SQL Server の展開権限](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx)」を参照してください。


