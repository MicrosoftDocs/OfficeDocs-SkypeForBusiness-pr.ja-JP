---
title: 常設チャット バックアップ SQL Server ストアの追加
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddPersistentChatBackupSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 106698e4-ce73-4a34-8fc7-e9d3208a17dc
description: 常設チャットサーバーまたは常設チャットサーバープールのバックアップデータベースを提供するバックアップ SQL Server ストアを構成します。
ms.openlocfilehash: 39e5e1ead6ed3cb089545406852de16170d782dc
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34304654"
---
# <a name="add-persistent-chat-backup-sql-server-store"></a>常設チャット バックアップ SQL Server ストアの追加
 
常設チャットサーバーまたは常設チャットサーバープールのバックアップデータベースを提供するバックアップ SQL Server ストアを構成します。
  
 **Sql server ストア**: 既存の sql server を選択し、必要に応じて常設チャットのインスタンスも選択します。
  
[**新規**] をクリックして、新しい SQL Server を定義し、必要に応じて永続的なチャットバックアップデータの新しいインスタンスを作成します。
  
[ **Sql server ストアのミラーリングを有効**にする] チェックボックスをオンにして、sql server データベースと永続的なチャットバックアップデータのミラーリングされたデータベースを提供するオプションのインスタンスを構成します。
  
リストの**ミラーリング Sql server ストア**から選択します。 sql server とオプションのインスタンスは、常設チャットバックアップの sql SERVER の sql server ミラーとして機能します。
  
[**新規**] をクリックして、新しい sql server を定義し、必要に応じて、常設チャットの sql server ミラーリング用の新しいインスタンスを作成します。
  
[**SQL Server ミラーリング監視を自動フェールオーバーの有効化のために使用**] の一覧で、フェールオーバーのシナリオにおいて監視サーバーとして機能する SQL Server を選択します。 監視サーバーは、常設チャットサーバーのデータをミラーリングまたはホストしませんが、ミラー化された構成内の1つの SQL Server のみがアクティブな SQL Server であることを常に確認します。
  
[**新規**] をクリックして、新しい sql server 監視を定義します。必要に応じて、永続的なチャットバックアップ SQL server ミラーリング監視のインスタンスを指定します。
  
前のプール定義ダイアログに戻るには、[**戻る**] をクリックします。
  
このプールの backup SQL Server ストア構成のオプションを入力して、常設チャットサーバープールの定義を続行するには、[**次へ**] をクリックします。
  
すべての変更を破棄して**新しい常設チャット プールの定義**ウィザードを終了するには、[**キャンセル**] をクリックします。
  
このページのような状況依存のヘルプにアクセスするには、[**ヘルプ**] をクリックします。
  
## <a name="see-also"></a>関連項目

[Skype for Business Server 2015 の常設チャット サーバーの計画](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[Skype for Business Server 2015 の常設チャット サーバーのハードウェアおよびソフトウェア要件](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[Skype for Business Server 2015 での常設チャット サーバーの高可用性および障害復旧の構成](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)
