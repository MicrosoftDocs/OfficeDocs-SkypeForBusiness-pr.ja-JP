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
description: 常設チャット サーバー SQL Serverバックアップ データベースを提供するバックアップ サーバー ストアを構成します。
ms.openlocfilehash: c21cd099372bb49b621447697320df2785a0c9dc
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49818737"
---
# <a name="add-persistent-chat-backup-sql-server-store"></a>常設チャット バックアップ SQL Server ストアの追加
 
常設チャット サーバー SQL Serverバックアップ データベースを提供するバックアップ サーバー ストアを構成します。
  
 **SQL Serverストア**: 既存のチャット を選択SQL Server、必要に応じて常設チャットのインスタンスを選択します。
  
[ **新規]** をクリックして、新しいSQL Serverし、必要に応じて常設チャットのバックアップ データの新しいインスタンスを定義します。
  
常設チャット **の** SQL Serverデータベースを提供する SQL Server データベースとオプションのインスタンスを構成するには、[ストア ミラーリングの有効化] チェック ボックスをオンにします。
  
リストから **選択しSQL Server** 常設チャット のバックアップ SQL Serverミラーとして機能する SQL Server およびオプションのインスタンスを格納SQL Server。
  
[ **新規]** をクリックして新しいSQL Serverし、必要に応じて常設チャット の新しいインスタンスをSQL Serverします。
  
[**SQL Server ミラーリング監視を自動フェールオーバーの有効化のために使用**] の一覧で、フェールオーバーのシナリオにおいて監視サーバーとして機能する SQL Server を選択します。 ミラーリング監視サーバーは、常設チャット サーバーのデータをミラー化またはホストしませんが、ミラー化された構成の 1 つの SQL Server だけがアクティブなチャット サーバー SQL Server保証します。
  
[ **新規]** をクリックして、ミラーリング監視SQL Server常設チャット バックアップ監視のインスタンスを定義SQL Server定義します。
  
前のプール定義ダイアログに戻るには、[**戻る**] をクリックします。
  
この **プール** のバックアップ サーバー構成のオプションの入力が完了したら、[次へ] SQL Serverをクリックし、常設チャット サーバー プールの定義に進みます。
  
すべての変更を破棄して **新しい常設チャット プールの定義** ウィザードを終了するには、[**キャンセル**] をクリックします。
  
このページのような状況依存のヘルプにアクセスするには、[**ヘルプ**] をクリックします。
  
## <a name="see-also"></a>関連項目

[Skype for Business Server 2015 での常設チャット サーバーの計画](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[Skype for Business Server 2015 のサーバー要件](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[Skype for Business Server 2015 の常設チャット サーバーのハードウェア要件およびソフトウェア要件](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[Skype for Business Server 2015 での常設チャット サーバーの高可用性と障害復旧の構成](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)
