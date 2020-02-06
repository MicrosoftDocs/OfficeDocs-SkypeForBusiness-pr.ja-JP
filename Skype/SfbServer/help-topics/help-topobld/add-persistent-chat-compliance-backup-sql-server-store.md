---
title: 常設チャット コンプライアンス バックアップ SQL Server ストアの追加
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.custom:
- ms.lync.tb.AddPersistentChatBackupComplianceStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 358b74bd-a97d-4f28-9bed-af633ea0099e
description: 常設チャットサーバーまたは常設チャットサーバーのコンプライアンス SQL Server ストアのバックアップデータベースを提供するバックアップコンプライアンス SQL Server ストアを構成します。
ms.openlocfilehash: e557651c7c55a847de85be1ce724168fcc713a96
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41820699"
---
# <a name="add-persistent-chat-compliance-backup-sql-server-store"></a>常設チャット コンプライアンス バックアップ SQL Server ストアの追加
 
常設チャットサーバーまたは常設チャットサーバーのコンプライアンス SQL Server ストアのバックアップデータベースを提供するバックアップコンプライアンス SQL Server ストアを構成します。
  
 **Sql server ストア**: 既存の sql server を選択し、必要に応じて常設チャットのインスタンスも選択します。
  
[**新規作成**] をクリックして、新しい SQL Server を定義し、必要に応じて、常設チャットバックアップのコンプライアンスデータ用の新しいインスタンスを作成します。
  
[ **Sql server ストアのミラーリングを有効**にする] チェックボックスをオンにして、sql server データベースと、永続的なチャットのバックアップコンプライアンスデータのミラーリングされたデータベースを提供するオプションのインスタンスを構成します。
  
リストの**ミラーリング Sql server ストア**で sql server とオプションのインスタンスを選択すると、永続的なチャットバックアップのコンプライアンス sql SERVER の sql server ミラーとして機能します。
  
[**新規**] をクリックして、新しい sql server を定義し、必要に応じて、常設チャットの sql server ミラーリング用の新しいインスタンスを作成します。
  
[**SQL Server ミラーリング監視を自動フェールオーバーの有効化のために使用**] の一覧で、フェールオーバーのシナリオにおいて監視サーバーとして機能する SQL Server を選択します。 監視サーバーは、常設チャットサーバーのデータをミラーリングまたはホストしませんが、ミラー化された構成内の1つの SQL Server のみがアクティブな SQL Server であることを常に確認します。
  
[**新規**] をクリックして、新しい sql server 監視を定義します。必要に応じて、永続的なチャットバックアップのコンプライアンス SQL server ミラーリング監視のインスタンスを指定します。
  
前のプール定義ダイアログに戻るには、[**戻る**] をクリックします。
  
このプールの backup SQL Server ストア構成のオプションを入力して、常設チャットサーバープールの定義を続行するには、[**次へ**] をクリックします。
  
すべての変更を破棄して**新しい常設チャット プールの定義**ウィザードを終了するには、[**キャンセル**] をクリックします。
  
このページのような状況依存のヘルプにアクセスするには、[**ヘルプ**] をクリックします。
  
## <a name="see-also"></a>関連項目

[Skype for Business Server 2015 の常設チャット サーバーの計画](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[Skype for Business Server 2015 の常設チャット サーバーのハードウェアおよびソフトウェア要件](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[Skype for Business Server 2015 での常設チャット サーバーのコンプライアンス サービスの構成](../../manage/persistent-chat/configure-compliance.md)
  
[Skype for Business Server 2015 での常設チャット サーバーの高可用性および障害復旧の構成](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)
