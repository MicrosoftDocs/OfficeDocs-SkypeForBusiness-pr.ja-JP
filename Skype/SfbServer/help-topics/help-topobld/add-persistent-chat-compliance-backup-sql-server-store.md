---
title: 常設チャット コンプライアンス バックアップ SQL Server ストアの追加
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
  - CSH
ms.custom:
  - ms.lync.tb.AddPersistentChatBackupComplianceStorePage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 358b74bd-a97d-4f28-9bed-af633ea0099e
description: 常設チャット サーバーまたは常設チャット SQL Serverコンプライアンス ストアのバックアップ データベースを提供するバックアップ コンプライアンス SQL Server構成します。
---

# <a name="add-persistent-chat-compliance-backup-sql-server-store"></a>常設チャット コンプライアンス バックアップ SQL Server ストアの追加
 
常設チャット サーバーまたは常設チャット SQL Serverコンプライアンス ストアのバックアップ データベースを提供するバックアップ コンプライアンス SQL Server構成します。
  
 **SQL Serverストア**: 常設チャットの既存のSQL Server、必要に応じてインスタンスを選択します。
  
[**新規]** をクリックして新SQL Serverし、必要に応じて常設チャット バックアップ コンプライアンス データの新しいインスタンスを定義します。
  
[ストア **ミラーリングSQL Server有効** にする] チェック ボックスをオンにして、常設チャット のバックアップ コンプライアンス データにミラー化されたデータベースを提供する SQL Server データベースとオプションのインスタンスを構成します。
  
[ミラーリング] リストから選択 **SQL Server**、SQL Serverおよびオプションのインスタンスを保存して、常設チャット のバックアップ コンプライアンス SQL Server ミラーとして機能SQL Server。
  
[**新規]** をクリックして新しいSQL Serverし、必要に応じて常設チャット の新しいインスタンスをミラーリングSQL Serverします。
  
[**SQL Server ミラーリング監視を自動フェールオーバーの有効化のために使用**] の一覧で、フェールオーバーのシナリオにおいて監視サーバーとして機能する SQL Server を選択します。 ミラーリング監視サーバーは、常設チャット サーバーのデータをミラーリングまたはホストしませんが、ミラーリングされた構成内の 1 つの SQL Server だけがアクティブなSQL Server状態になります。
  
[**新規]** をクリックして、SQL Serverミラーリング監視の常設チャット バックアップ コンプライアンスのインスタンスをSQL Serverします。
  
前のプール定義ダイアログに戻るには、[**戻る**] をクリックします。
  
[**次へ**] をクリックして、このプールのバックアップ サーバーのSQL Serverを入力し、常設チャット サーバー プールの定義を続行します。
  
すべての変更を破棄して **新しい常設チャット プールの定義** ウィザードを終了するには、[**キャンセル**] をクリックします。
  
このページのような状況依存のヘルプにアクセスするには、[**ヘルプ**] をクリックします。
  
## <a name="see-also"></a>関連項目

[2015 年の常設チャット サーバー Skype for Business Serverする](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[2015 年のサーバー Skype for Business Server要件](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[2015 年の常設チャット サーバーのハードウェア要件とソフトウェア要件Skype for Business Server](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[2015 年の常設チャット サーバーのコンプライアンス Skype for Business Server構成する](../../manage/persistent-chat/configure-compliance.md)
  
[2015 年に常設チャット サーバーの高可用性と障害復旧をSkype for Business Serverする](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)
