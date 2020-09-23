---
title: フロントエンド アーカイブ ストアを追加する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: アーカイブには、アーカイブデータを格納するために、サポートされている64ビット版の Microsoft SQL Server データベースソフトウェアが必要です。 アーカイブ用に定義されている SQL Server データベースを選択するか、または SQL server データベースが存在するサーバーの完全修飾ドメイン名 (FQDN) を指定して、新しい sql server データベースを定義することができます。これは、新しい SQL Server データベースで使用する SQL Server のインスタンス (既定のインスタンスの場合もあります) になります。、または指定した名前付きインスタンス)。
ms.openlocfilehash: 0cf61aa758b2228c065659f518c81d637022ff47
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2020
ms.locfileid: "48216718"
---
# <a name="add-front-end-archiving-store"></a>フロントエンド アーカイブ ストアを追加する

アーカイブには、アーカイブデータを格納するために、サポートされている64ビット版の Microsoft SQL Server データベースソフトウェアが必要です。 アーカイブ用に定義されている SQL Server データベースを選択するか、または SQL server データベースが存在するサーバーの完全修飾ドメイン名 (FQDN) を指定して、新しい sql server データベースを定義することができます。これは、新しい SQL Server データベースで使用する SQL Server のインスタンス (既定のインスタンスの場合もあります) になります。、または指定した名前付きインスタンス)。

> [!NOTE]
> トポロジを公開するために使用するアカウントに適切なユーザー権限とアクセス許可がある場合、トポロジを公開するときに監視データベースを作成できます。インストール手順の一部として、データベースを後で作成することもできます。

> [!NOTE]
> 監視用に SQL Server ベースのサーバーにデータベースをインストールして展開するには、データベースファイルをインストールする sql server ベースのサーバーの SQL Server の管理者グループのメンバーである必要があります。 SQL Server sysadmin グループのメンバーではない場合は、データベースファイルが展開されるまで、グループに追加するように要求する必要があります。 システム管理者グループのメンバーになることができない場合は、データベースを構成および展開するためのスクリプトを SQL Server データベース管理者に提供する必要があります。 これらの手順を実行するために必要なユーザー権限およびアクセス許可の詳細については、「展開」ドキュメントの「[Deployment Permissions for SQL Server](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx)」を参照してください。


