---
title: 単一の Standard Edition サーバーの準備 (起動)
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployAIOInvoke
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 5da0aa73-8bf8-41f3-81e7-94f955cda541
description: '[コマンドの実行] ページで、SQL Server Express をインストールし、サーバーの全体管理ストアとして機能する構成のタスクを作業ウィンドウに表示できます。 既定では、RTC という名前SQL Serverベースのデータベースのインスタンスが作成されます。 サーバーおよびクライアントの着信および発信アクセスを許可するファイアウォール ルールも作成され、データベースおよびインスタンスとの通信が行われます。 タスクが完了すると、ドロップダウン リストからログ ファイルを選択できます。 ログ ファイルは [ブートストラップ ローカル コンピューター] と命名されます。 ログ ファイルを選択して、[ログの表示] をクリックします。 ログ ファイルにエラーや警告がないかどうか確認します。 次に進む準備ができたら、[完了] をクリックします。 トポロジ ビルダーを使用してトポロジを定義する必要があります (まだ定義していない場合)。'
ms.openlocfilehash: fbb66e6e79b25fed8db266f727fb33a0d68bce1c
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/05/2022
ms.locfileid: "62410270"
---
# <a name="prepare-single-standard-edition-server-invoke"></a>単一の Standard Edition サーバーの準備 (起動)
 
[コマンド **の実行**] ページで、SQL Server Express をインストールし、サーバーの全体管理ストアとして機能する構成のタスクを作業ウィンドウに表示できます。 既定では、RTC という名前SQL Serverベースのデータベースのインスタンスが作成されます。 サーバーおよびクライアントの着信および発信アクセスを許可するファイアウォール ルールも作成され、データベースおよびインスタンスとの通信が行われます。 タスクが完了すると、ドロップダウン リストからログ ファイルを選択できます。 ログ ファイルは **[ブートストラップ ローカル コンピューター]** と命名されます。 ログ ファイルを選択して、**[ログの表示]** をクリックします。 ログ ファイルにエラーや警告がないかどうか確認します。 次に進む準備ができたら、**[完了]** をクリックします。 トポロジ ビルダーを使用してトポロジを定義する必要があります (まだ定義していない場合)。
  
> [!IMPORTANT]
> インストールが完了SQL Server Express時間がかかる場合があります。 インストール中、画面やタスク ウィンドウに進行状況は表示されません。 インストールを監視するには、タスク マネージャー Windowsを使用して、MSIExec プロセスとセットアップ ファイルを探SQL Server。 この方法により、インストールの状態を表示し、インストールが進行していることを確認できます。 このヘルプ トピックの範囲を超える要因によっては、インストールが完了する SQL Server 15 分以上かかる場合があります。 
  

