---
title: アーカイブ ストアのフロント エンドを追加します。
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
ms.openlocfilehash: b8d5a46f0eeebca36bfb8c355a32d61f477564e7
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/28/2018
ms.locfileid: "23261778"
---
# <a name="add-front-end-archiving-store"></a>アーカイブ ストアのフロント エンドを追加します。

アーカイブには、Microsoft SQL Server データベース ・ ソフトウェア ・ アーカイブ ・ データを格納するのにサポートされている 64 ビット版が必要です。 アーカイブに使用する定義済みの SQL Server データベースを選択するか、SQL Server データベースを SQL の Se のインスタンスだけでなく、あるサーバーの完全修飾ドメイン名 (FQDN) を指定することにより、新しい SQL Server データベースの定義した rver の新しい SQL Server データベース (既定のインスタンスまたは名前付きインスタンスを指定することができます) を使用します。

> [!NOTE]
> トポロジを公開するために使用するアカウントに適切なユーザー権利とアクセス許可がある場合、トポロジを公開すると、監視データベースを作成できます。 インストール手順の一部を含め、データベースを後で作成することもできます。

> [!NOTE]
> インストールし、監視するための SQL Server ベースのサーバー上のデータベースを展開、データベース ファイルをインストールしている SQL Server ベースのサーバーの SQL Server システム管理者グループのメンバーをする必要があります。 SQL Server の sysadmin グループのメンバーでない場合は、するが、データベース ・ ファイルが配置されるまで、グループに追加することを要求する必要があります。 システム管理者グループのメンバーにすることはできません、スクリプトを構成して、データベースを配置すると、SQL Server データベースの管理者を入力してください。 ユーザー権利とアクセス許可の手順を実行する必要があるについての詳細は、展開に関するドキュメントで[SQL Server の展開のアクセス許可](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx)を参照してください。


