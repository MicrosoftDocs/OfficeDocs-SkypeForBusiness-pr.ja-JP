---
title: フロント エンドの SQL Server ストアを追加します。
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddFrontEndSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: dace9561-3eb4-4647-83cb-56c246919ae1
description: Standard Edition サーバーの展開は、必要なデータベース ソフトウェアの高速に Microsoft SQL Server と SQL Server データベースに自動的にインストールします。 したがって、すべてのオプション、事前に設定されて、既定の構成に変更を加えることはできません。
ms.openlocfilehash: 2b7527207974310c30b559011a580fe8871164d1
ms.sourcegitcommit: 08cf97296fb9ba6fbc4d68c3e380c8f37e86dd02
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/20/2018
ms.locfileid: "19964492"
---
# <a name="add-front-end-sql-server-store"></a>フロント エンドの SQL Server ストアを追加します。
 
Standard Edition サーバーの展開は、必要なデータベース ソフトウェアの高速に Microsoft SQL Server と SQL Server データベースに自動的にインストールします。 したがって、すべてのオプション、事前に設定されて、既定の構成に変更を加えることはできません。
  
Enterprise Edition サーバー展開のフロント エンド プールには、バック エンド データベースの SQL Server データベース ソフトウェアのサポート対象の 64 ビット版が必要です。 バック エンド データベースに使用する定義済みの SQL Server データベースを選択するか、サーバーを SQL Server データベースが存在するが、S の SQL のインスタンスの完全修飾ドメイン名 (FQDN) を指定することで新しい SQL Server データベースの定義erver、新しい SQL Server データベース (既定のインスタンスまたは名前付きインスタンスを指定することができます) を使用します。 SQL Server ストアのミラーリングを有効にするを選択し、自動フェイル オーバーのミラーリング ・ ミラーリング監視サーバーを指定できます。
  
詳細については SQL Server のサポートは、[データベース ソフトウェアとクラスタ リングをサポート](http://technet.microsoft.com/library/e05d0032-bbea-4e61-987d-d07b1c045fd5.aspx)サポート マニュアルを参照してください。 バック エンド データベースの SQL Server の設定に関する詳細については、展開に関するドキュメントで[SQL Server の構成](http://technet.microsoft.com/library/375e5cc4-e436-46dc-9b02-5063f35cdcc1.aspx)を参照してください。
  
> [!NOTE]
> (リアルタイム通信 (RTC)) のバック エンド データベースを作成するには、トポロジを公開するために使用されるアカウントに適切なユーザー権利とアクセス許可がある場合、トポロジを公開するとします。 インストール手順の一部として含め、後でデータベースを作成することもできます。 
  
> [!NOTE]
> インストールおよび展開の場合エンタープライズ版の SQL Server ベースのサーバー上のデータベースを展開、データベース ファイルをインストールしている SQL Server ベースのサーバーの SQL Server システム管理者グループのメンバーをする必要があります。 SQL Server のシステム管理者グループのメンバーでない場合は、データベース ファイルを展開するまでに、グループに追加する要求する必要があります。 システム管理者グループのメンバーにすることはできません、スクリプトを構成して、データベースを配置すると、SQL Server データベースの管理者を入力してください。 ユーザー権利とアクセス許可の手順を実行する必要があるの詳細については、 [SQL Server の展開のアクセス許可](http://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx)を参照してください。 
  

