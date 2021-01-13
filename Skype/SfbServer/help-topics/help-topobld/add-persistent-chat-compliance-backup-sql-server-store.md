---
title: 常設チャット コンプライアンス バックアップ SQL Server ストアの追加
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
- ms.lync.tb.AddPersistentChatBackupComplianceStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 358b74bd-a97d-4f28-9bed-af633ea0099e
description: 常設チャット サーバーまたは常設SQL Serverサーバー コンプライアンス データベースのバックアップ データベースを提供するバックアップ コンプライアンス サーバーストアを構成SQL Serverします。
ms.openlocfilehash: 9b380091978d62294c6ea16ffa8586b9f8d9d322
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49818717"
---
# <a name="add-persistent-chat-compliance-backup-sql-server-store"></a>常設チャット コンプライアンス バックアップ SQL Server ストアの追加
 
常設チャット サーバーまたは常設SQL Serverサーバー コンプライアンス データベースのバックアップ データベースを提供するバックアップ コンプライアンス サーバーストアを構成SQL Serverします。
  
 **SQL Serverストア**: 既存のチャット をSQL Server、必要に応じて常設チャットのインスタンスを選択します。
  
[ **新規]** をクリックして、新しいSQL Serverし、必要に応じて常設チャット のバックアップ コンプライアンス データの新しいインスタンスを定義します。
  
常設チャット の **バックアップ SQL Server** コンプライアンス データ用にミラー化されたデータベースを提供する SQL Server データベースとオプションのインスタンスを構成するには、[ストア ミラーリングストアのミラーリングを有効にする] チェック ボックスをオンにします。
  
リストから選択し **、SQL Server** 常設チャット のSQL Serverコンプライアンス ポリシーのミラーとして機能する SQL Server およびオプションのインスタンスを格納SQL Server。
  
[ **新規]** をクリックして新しいSQL Serverし、必要に応じて常設チャット の新しいインスタンスをSQL Serverします。
  
[**SQL Server ミラーリング監視を自動フェールオーバーの有効化のために使用**] の一覧で、フェールオーバーのシナリオにおいて監視サーバーとして機能する SQL Server を選択します。 ミラーリング監視サーバーは、常設チャット サーバーのデータをミラー化またはホストしませんが、ミラー化された構成の 1 つの SQL Server だけがアクティブなチャット サーバー SQL Server保証します。
  
[ **新規]** をクリックして、ミラーリング監視SQL Server常設チャット バックアップ コンプライアンス監視のインスタンスを定義SQL Server定義します。
  
前のプール定義ダイアログに戻るには、[**戻る**] をクリックします。
  
この **プール** のバックアップ サーバー構成のオプションの入力が完了したら、[次へ] SQL Serverをクリックし、常設チャット サーバー プールの定義に進みます。
  
すべての変更を破棄して **新しい常設チャット プールの定義** ウィザードを終了するには、[**キャンセル**] をクリックします。
  
このページのような状況依存のヘルプにアクセスするには、[**ヘルプ**] をクリックします。
  
## <a name="see-also"></a>関連項目

[Skype for Business Server 2015 での常設チャット サーバーの計画](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[Skype for Business Server 2015 のサーバー要件](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[Skype for Business Server 2015 の常設チャット サーバーのハードウェア要件およびソフトウェア要件](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[Skype for Business Server 2015 での常設チャット サーバーのコンプライアンス サービスの構成](../../manage/persistent-chat/configure-compliance.md)
  
[Skype for Business Server 2015 での常設チャット サーバーの高可用性と障害復旧の構成](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)
