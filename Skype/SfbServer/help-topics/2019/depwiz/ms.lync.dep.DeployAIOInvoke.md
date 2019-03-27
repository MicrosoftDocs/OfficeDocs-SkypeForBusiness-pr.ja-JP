---
title: 単一の Standard Edition サーバーの準備 (起動)
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployAIOInvoke
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5da0aa73-8bf8-41f3-81e7-94f955cda541
ROBOTS: NOINDEX, NOFOLLOW
description: コマンドの実行中] ページで、[作業ウィンドウで SQL Server Express をインストールして、中央管理ストアとして機能するように構成するタスクを表示できます。 既定では、RTC をという名前の SQL Server ベースのデータベースのインスタンスが作成されます。 サーバーとデータベース インスタンスと通信するためにクライアントの受信および送信のアクセスを許可するファイアウォール規則が作成されます。 タスクが完了したら、ドロップダウン リストからログ ファイルを選択できます。 ログ ファイルをローカル コンピューターのブートス トラップといいます。 ログ ファイルを選択すると、ログの表示] をクリックします。 エラーと警告のログ ファイルを確認します。 続行する準備ができたら、[完了] をクリックします。 されていない場合は、ここでトポロジ ビルダーでトポロジを定義してください。
ms.openlocfilehash: b4c1807f383e6933e15d49b6e486978d3afc087f
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30878635"
---
# <a name="prepare-single-standard-edition-server-invoke"></a>単一の Standard Edition サーバーの準備 (起動)
 
**コマンドの実行中**] ページで、[作業ウィンドウで SQL Server Express をインストールして、中央管理ストアとして機能するように構成するタスクを表示できます。 既定では、RTC をという名前の SQL Server ベースのデータベースのインスタンスが作成されます。 サーバーとデータベース インスタンスと通信するためにクライアントの受信および送信のアクセスを許可するファイアウォール規則が作成されます。 タスクが完了したら、ドロップダウン リストからログ ファイルを選択できます。 ログ ファイルを**ローカル コンピューターのブートス トラップ**といいます。 ログ ファイルを選択すると、**ログの表示**] をクリックします。 エラーと警告のログ ファイルを確認します。 続行する準備ができたらをクリックして**を終了します**。 されていない場合は、ここでトポロジ ビルダーでトポロジを定義してください。
  
> [!IMPORTANT]
> SQL Server Express のインストールには、完了に時間がかかります。 インストール中は進行状況画面または作業ウィンドウに表示されて、 インストールを監視するには、Windows タスク マネージャーを使用して SQL Server の MSIExec プロセスとセットアップ ファイルを探してください。 この方法では、インストールのステータスを表示し、インストールが続行であることを確認できます。 このヘルプ トピックの範囲外の要因によってファイルに最大 15 分かかるか、複数インストール SQL Server のインスタンス化を完了します。 
  

