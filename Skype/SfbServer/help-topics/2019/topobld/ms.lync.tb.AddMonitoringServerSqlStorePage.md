---
title: 監視サーバーの SQL Server ストアを追加します。
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
description: サーバーの監視には、監視データを格納する SQL Server データベースのソフトウェアのサポートされている 64 ビット版が必要です。 監視に使用する定義済みの SQL Server データベースを選択するか、SQL Server データベースが格納されている、SQL のインスタンスだけでなく、サーバーの完全修飾ドメイン名 (FQDN) を指定することで新しい SQL Server データベースの定義新しい SQL Server データベース (既定のインスタンスまたは名前付きインスタンスを指定することができます) を使用するサーバーです。
ms.openlocfilehash: 362f4be3d778d0c5607f6c0ee1233d85d6b9149e
ms.sourcegitcommit: 08cf97296fb9ba6fbc4d68c3e380c8f37e86dd02
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/20/2018
ms.locfileid: "19969772"
---
# <a name="add-monitoring-server-sql-server-store"></a>監視サーバーの SQL Server ストアを追加します。
 
サーバーの監視には、監視データを格納する SQL Server データベースのソフトウェアのサポートされている 64 ビット版が必要です。 監視に使用する定義済みの SQL Server データベースを選択するか、SQL Server データベースが格納されている、SQL のインスタンスだけでなく、サーバーの完全修飾ドメイン名 (FQDN) を指定することで新しい SQL Server データベースの定義新しい SQL Server データベース (既定のインスタンスまたは名前付きインスタンスを指定することができます) を使用するサーバーです。
  
詳細については SQL Server のサポートは、[データベース ソフトウェアとクラスタ リングをサポート](http://technet.microsoft.com/library/e05d0032-bbea-4e61-987d-d07b1c045fd5.aspx)サポート マニュアルを参照してください。 監視データベースのコロケーションを含め、監視データベースの詳細について計画マニュアルと[のデータを SQL Server の[監視を計画](http://technet.microsoft.com/library/26cead5a-183c-42f1-a4b0-0e8d61c6159d.aspx)、サポート ドキュメントで[サポートされているサーバーの場所](http://technet.microsoft.com/library/3be990a1-5485-4b83-b73f-947ac97821f9.aspx)を参照してください。ログ ファイルの配置](http://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx)の展開に関するドキュメントです。
  
> [!NOTE]
> トポロジを公開するために使用するアカウントに適切なユーザー権利とアクセス許可がある場合、トポロジを公開すると、監視データベースを作成できます。 インストール手順の一部として含め、後でデータベースを作成することもできます。 > をインストールし、監視するための SQL Server ベースのサーバー上のデータベースを展開、データベース ファイルをインストールしている SQL Server ベースのサーバーの SQL Server システム管理者グループのメンバーをする必要があります。 SQL Server の sysadmin グループのメンバーでない場合は、データベース ファイルを展開するまでに、グループに追加する要求する必要があります。 システム管理者グループのメンバーにすることはできません、スクリプトを構成して、データベースを配置すると、SQL Server データベースの管理者を入力してください。 これらの手順を実行する必要があるアクセス許可とユーザー権利の詳細については、展開に関するドキュメントで[SQL Server の展開のアクセス許可](http://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx)を参照してください。
  

