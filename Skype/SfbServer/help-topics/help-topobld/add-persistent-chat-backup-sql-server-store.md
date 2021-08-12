---
title: 常設チャット バックアップ SQL Server ストアを追加する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddPersistentChatBackupSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 106698e4-ce73-4a34-8fc7-e9d3208a17dc
description: 常設チャット サーバー SQL Server常設チャット サーバー プールのバックアップ データベースを提供するバックアップ サーバー ストアを構成します。
ms.openlocfilehash: c62cf2114d2a982e70aa6218b90109d7fafcea2f85abf9aff5bfd155a5ddef76
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54302561"
---
# <a name="add-persistent-chat-backup-sql-server-store"></a>常設チャット バックアップ SQL Server ストアの追加
 
常設チャット サーバー SQL Server常設チャット サーバー プールのバックアップ データベースを提供するバックアップ サーバー ストアを構成します。
  
 **SQL Serverストア**: 既存のストアを選択SQL Server、必要に応じて常設チャットのインスタンスを選択します。
  
[**新規]** をクリックして新SQL Serverし、必要に応じて常設チャット バックアップ データの新しいインスタンスを定義します。
  
[ストア **ミラーリングSQL Server有効** にする] チェック ボックスをオンにして、永続的SQL Serverバックアップ データにミラー化されたデータベースを提供するデータベースとオプションのインスタンスを構成します。
  
[ミラーリング] リストから選択 **SQL Server、SQL Server** およびオプションのインスタンスを格納して、常設チャット バックアップ SQL Serverミラーとして機能SQL Server。
  
[**新規]** をクリックして新しいSQL Serverし、必要に応じて常設チャット の新しいインスタンスをミラーリングSQL Serverします。
  
[**SQL Server ミラーリング監視を自動フェールオーバーの有効化のために使用**] の一覧で、フェールオーバーのシナリオにおいて監視サーバーとして機能する SQL Server を選択します。 ミラーリング監視サーバーは、常設チャット サーバーのデータをミラーリングまたはホストしませんが、ミラーリングされた構成内の 1 つの SQL Server だけがアクティブなSQL Server状態になります。
  
[**新規]** をクリックして、SQL Serverミラーリング監視の永続的なチャット バックアップのインスタンスをSQL Serverします。
  
前のプール定義ダイアログに戻るには、[**戻る**] をクリックします。
  
[**次へ**] をクリックして、このプールのバックアップ サーバーのSQL Serverを入力し、常設チャット サーバー プールの定義を続行します。
  
すべての変更を破棄して **新しい常設チャット プールの定義** ウィザードを終了するには、[**キャンセル**] をクリックします。
  
このページのような状況依存のヘルプにアクセスするには、[**ヘルプ**] をクリックします。
  
## <a name="see-also"></a>関連項目

[2015 年の常設チャット サーバー Skype for Business Serverする](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[2015 年のサーバー Skype for Business Server要件](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[2015 年の常設チャット サーバーのハードウェア要件とソフトウェア要件Skype for Business Server](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[2015 年に常設チャット サーバーの高可用性と障害復旧をSkype for Business Serverする](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)
