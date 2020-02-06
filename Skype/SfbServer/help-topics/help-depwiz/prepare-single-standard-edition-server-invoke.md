---
title: 単一の Standard Edition サーバーの準備 (起動)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: '[コマンドの実行] ページでは、SQL Server Express をインストールして、中央管理ストアとして機能するように構成するタスクを作業ウィンドウで確認できます。 既定では、RTC という名前の SQL Server ベースのデータベースのインスタンスが作成されます。 ファイアウォールルールも作成され、サーバーとクライアントがデータベースとインスタンスと通信できるように、受信および送信のアクセスが許可されます。 タスクが完了したら、ドロップダウンリストからログファイルを選ぶことができます。 ログファイルは、ブートストラップのローカルコンピューターという名前です。 ログファイルを選択したら、[ログの表示] をクリックします。 エラーや警告のログファイルを確認します。 続行する準備ができたら、[完了] をクリックします。 まだトポロジビルダーを使用してトポロジを定義する必要があります。'
ms.openlocfilehash: 16cc6ada75ae90da4da2cb269aed26adbf472a33
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41823441"
---
# <a name="prepare-single-standard-edition-server-invoke"></a>単一の Standard Edition サーバーの準備 (起動)
 
[**コマンドの実行**] ページでは、SQL Server Express をインストールして、中央管理ストアとして機能するように構成するタスクを作業ウィンドウで確認できます。 既定では、RTC という名前の SQL Server ベースのデータベースのインスタンスが作成されます。 ファイアウォールルールも作成され、サーバーとクライアントがデータベースとインスタンスと通信できるように、受信および送信のアクセスが許可されます。 タスクが完了したら、ドロップダウンリストからログファイルを選ぶことができます。 ログファイルは、**ブートストラップのローカルコンピューター**という名前です。 ログファイルを選択したら、[**ログの表示**] をクリックします。 エラーや警告のログファイルを確認します。 続行する準備ができたら、[完了] をクリックし**ます。** まだトポロジビルダーを使用してトポロジを定義する必要があります。
  
> [!IMPORTANT]
> SQL Server Express のインストールが完了するまでに時間がかかる場合があります。 インストール中は、画面または作業ウィンドウに進行状況は表示されません。 インストールを監視するには、Windows タスクマネージャーを使用して、MSIExec プロセスと SQL Server のセットアップファイルを確認する必要があります。 この方法では、インストールの状態を表示して、インストールが進行中であることを確認できます。 このヘルプトピックの範囲を超える要因によっては、SQL Server インスタンスの実行を完了するために最大15分以上かかる場合があります。 
  

