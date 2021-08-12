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
description: 常設チャット サーバーまたは常設チャット SQL Serverコンプライアンス ストアのバックアップ データベースを提供するバックアップ コンプライアンス SQL Server構成します。
ms.openlocfilehash: edcb80d798e6039560db4149b17ce7c2d2d61b9d92a4450199dcad29b12093dc
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54344926"
---
# <a name="add-persistent-chat-compliance-backup-sql-server-store"></a>常設チャット コンプライアンス バックアップ SQL Server ストアの追加
 
常設チャット サーバーまたは常設チャット SQL Serverコンプライアンス ストアのバックアップ データベースを提供するバックアップ コンプライアンス SQL Server構成します。
  
 **SQL Serverストア**: 既存のストアを選択SQL Server、必要に応じて常設チャットのインスタンスを選択します。
  
[**新規]** をクリックして新SQL Serverし、必要に応じて常設チャット バックアップ コンプライアンス データの新しいインスタンスを定義します。
  
[ストア **ミラーリングSQL Server** 有効にする] チェック ボックスをオンにして、SQL Server データベースとオプションのインスタンスを構成し、常設チャット のバックアップ コンプライアンス データにミラー化されたデータベースを提供します。
  
[ミラーリング] リストから選択 **SQL Server、SQL Server** およびオプションのインスタンスを保存して、常設チャット のバックアップ コンプライアンス SQL Serverミラーとして機能SQL Server。
  
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
