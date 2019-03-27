---
title: 監視サーバー SQL Server ストアの追加
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddMonitoringServerSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d873a2ad-9d3a-4ef6-9f25-ccdd3716218c
ROBOTS: NOINDEX, NOFOLLOW
description: サーバーの監視には、監視データを格納する SQL Server データベースのソフトウェアのサポートされている 64 ビット版が必要です。 監視に使用する定義済みの SQL Server データベースを選択するか、SQL Server データベースが格納されている、SQL のインスタンスだけでなく、サーバーの完全修飾ドメイン名 (FQDN) を指定することで新しい SQL Server データベースの定義新しい SQL Server データベース (既定のインスタンスまたは名前付きインスタンスを指定することができます) を使用するサーバーです。
ms.openlocfilehash: f0efdf2662567f786a035d30236d11c14ccc8efe
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30890705"
---
# <a name="add-monitoring-server-sql-server-store"></a>監視サーバー SQL Server ストアの追加

サーバーの監視には、監視データを格納する SQL Server データベースのソフトウェアのサポートされている 64 ビット版が必要です。 監視に使用する定義済みの SQL Server データベースを選択するか、SQL Server データベースが格納されている、SQL のインスタンスだけでなく、サーバーの完全修飾ドメイン名 (FQDN) を指定することで新しい SQL Server データベースの定義新しい SQL Server データベース (既定のインスタンスまたは名前付きインスタンスを指定することができます) を使用するサーバーです。

詳細については SQL Server のサポートは、[データベース ソフトウェアとクラスタ リングをサポート](https://technet.microsoft.com/library/e05d0032-bbea-4e61-987d-d07b1c045fd5.aspx)サポート マニュアルを参照してください。 監視データベースのコロケーションを含め、監視データベースの詳細について計画マニュアルと[のデータを SQL Server の[監視を計画](https://technet.microsoft.com/library/26cead5a-183c-42f1-a4b0-0e8d61c6159d.aspx)、サポート ドキュメントで[サポートされているサーバーの場所](https://technet.microsoft.com/library/3be990a1-5485-4b83-b73f-947ac97821f9.aspx)を参照してください。ログ ファイルの配置](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx)の展開に関するドキュメントです。

> [!NOTE]
> トポロジを公開するために使用するアカウントに適切なユーザー権利とアクセス許可がある場合、トポロジを公開すると、監視データベースを作成できます。 インストール手順の一部として含め、後でデータベースを作成することもできます。 _gt をインストールし、監視するための SQL Server ベースのサーバー上のデータベースを配置するデータベース ファイルをインストールしている SQL Server ベースのサーバーの SQL Server システム管理者グループのメンバーであることが必要です。 SQL Server の sysadmin グループのメンバーでない場合は、データベース ファイルを展開するまでに、グループに追加する要求する必要があります。 システム管理者グループのメンバーにすることはできません、スクリプトを構成して、データベースを配置すると、SQL Server データベースの管理者を入力してください。 これらの手順を実行する必要があるアクセス許可とユーザー権利の詳細については、展開に関するドキュメントで[SQL Server の展開のアクセス許可](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx)を参照してください。


