---
title: 単一の Standard Edition サーバーの準備 (起動)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployAIOInvoke
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5da0aa73-8bf8-41f3-81e7-94f955cda541
description: '[コマンドの実行] ページでは、SQL Server Express をインストールし、中央管理ストアとして機能する構成のタスクを作業ウィンドウに表示できます。 既定では、RTC という名前SQL Serverベースのデータベースのインスタンスが作成されます。 サーバーおよびクライアントの着信および発信アクセスを許可するファイアウォール ルールも作成され、データベースおよびインスタンスとの通信が行われます。 タスクが完了すると、ドロップダウン リストからログ ファイルを選択できます。 ログ ファイルは [ブートストラップ ローカル コンピューター] と命名されます。 ログ ファイルを選択して、[ログの表示] をクリックします。 ログ ファイルにエラーや警告がないかどうか確認します。 次に進む準備ができたら、[完了] をクリックします。 まだ定義していない場合は、トポロジ ビルダーを使用してトポロジを定義する必要があります。'
ms.openlocfilehash: adf980ec2576eb4e23983fcd99befb1fc6bfb6ee
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49829747"
---
# <a name="prepare-single-standard-edition-server-invoke"></a>単一の Standard Edition サーバーの準備 (起動)
 
[ **コマンドの** 実行] ページでは、SQL Server Express をインストールし、中央管理ストアとして機能する構成のタスクを作業ウィンドウに表示できます。 既定では、RTC という名前SQL Serverベースのデータベースのインスタンスが作成されます。 サーバーおよびクライアントの着信および発信アクセスを許可するファイアウォール ルールも作成され、データベースおよびインスタンスとの通信が行われます。 タスクが完了すると、ドロップダウン リストからログ ファイルを選択できます。 ログ ファイルは **[ブートストラップ ローカル コンピューター]** と命名されます。 ログ ファイルを選択して、**[ログの表示]** をクリックします。 ログ ファイルにエラーや警告がないかどうか確認します。 次に進む準備ができたら、**[完了]** をクリックします。 まだ定義していない場合は、トポロジ ビルダーを使用してトポロジを定義する必要があります。
  
> [!IMPORTANT]
> SQL Server Express のインストールが完了するには、少し時間がかかる場合があります。 インストール中、画面やタスク ウィンドウに進行状況は表示されません。 インストールを監視するには、Windows タスク マネージャーを使用して、MSIExec プロセスとセットアップ ファイルを探SQL Server。 この方法により、インストールの状態を表示し、インストールが進行していることを確認できます。 このヘルプ トピックの範囲を超える要因によっては、インストールが完了するのに最大 15 分以上かかるSQL Serverがあります。 
  

