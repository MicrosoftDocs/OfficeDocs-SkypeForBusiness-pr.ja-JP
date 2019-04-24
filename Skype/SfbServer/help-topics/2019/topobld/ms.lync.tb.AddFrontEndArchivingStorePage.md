---
title: フロントエンド アーカイブ ストアの追加
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddFrontEndArchivingStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ce1723eb-7c93-424a-a622-9c888bf6d3bc
ROBOTS: NOINDEX, NOFOLLOW
description: アーカイブには、Microsoft SQL Server データベース ・ ソフトウェア ・ アーカイブ ・ データを格納するのにサポートされている 64 ビット版が必要です。 アーカイブに使用する定義済みの SQL Server データベースを選択するか、SQL Server データベースを SQL の Se のインスタンスだけでなく、あるサーバーの完全修飾ドメイン名 (FQDN) を指定することにより、新しい SQL Server データベースの定義した rver の新しい SQL Server データベース (既定のインスタンスまたは名前付きインスタンスを指定することができます) を使用します。
ms.openlocfilehash: e43d7de6598a24306cc9622f24bea0b2b7e7cc25
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32202090"
---
# <a name="add-front-end-archiving-store"></a>フロントエンド アーカイブ ストアの追加

アーカイブには、Microsoft SQL Server データベース ・ ソフトウェア ・ アーカイブ ・ データを格納するのにサポートされている 64 ビット版が必要です。 アーカイブに使用する定義済みの SQL Server データベースを選択するか、SQL Server データベースを SQL の Se のインスタンスだけでなく、あるサーバーの完全修飾ドメイン名 (FQDN) を指定することにより、新しい SQL Server データベースの定義した rver の新しい SQL Server データベース (既定のインスタンスまたは名前付きインスタンスを指定することができます) を使用します。

> [!NOTE]
> トポロジを公開するために使用するアカウントに適切なユーザー権利とアクセス許可がある場合、トポロジを公開すると、監視データベースを作成できます。 インストール手順の一部を含め、データベースを後で作成することもできます。

> [!NOTE]
> インストールし、監視するための SQL Server ベースのサーバー上のデータベースを展開、データベース ファイルをインストールしている SQL Server ベースのサーバーの SQL Server システム管理者グループのメンバーをする必要があります。 SQL Server の sysadmin グループのメンバーでない場合は、するが、データベース ・ ファイルが配置されるまで、グループに追加することを要求する必要があります。 システム管理者グループのメンバーにすることはできません、スクリプトを構成して、データベースを配置すると、SQL Server データベースの管理者を入力してください。 ユーザー権利とアクセス許可の手順を実行する必要があるについての詳細は、展開に関するドキュメントで[SQL Server の展開のアクセス許可](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx)を参照してください。


