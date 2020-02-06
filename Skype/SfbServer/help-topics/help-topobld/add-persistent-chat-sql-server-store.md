---
title: 常設チャット SQL Server ストアの追加
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
- ms.lync.tb.AddPersistentChatSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c8e6064a-8127-4c25-8685-06f49d8bbfce
description: 常設チャットサーバーまたは常設チャットサーバープールのデータベースを提供する SQL Server ストアを構成します。
ms.openlocfilehash: 36939e6192b8d26e5fa84c3c2fe5ef4efe45b577
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41820659"
---
# <a name="add-persistent-chat-sql-server-store"></a>常設チャット SQL Server ストアの追加
 
常設チャットサーバーまたは常設チャットサーバープールのデータベースを提供する SQL Server ストアを構成します。
  
 **Sql server ストア**: 既存の sql server を選択し、必要に応じて常設チャットのインスタンスも選択します。
  
[**新規**] をクリックして、新しい SQL Server を定義し、必要に応じて、常設チャットデータの新しいインスタンスを作成します。
  
[ **Sql server ストアのミラーリングを有効**にする] チェックボックスをオンにして、sql server データベースと、常設チャットデータのミラーリングされたデータベースを提供するオプションのインスタンスを構成します。
  
リストの**ミラーリング Sql server ストア**から選択します。 sql server とオプションのインスタンスは、常設チャット sql SERVER の sql server ミラーとして機能します。
  
[**新規**] をクリックして、新しい sql server を定義し、必要に応じて、常設チャットの sql server ミラーリング用の新しいインスタンスを作成します。
  
[**SQL Server ミラーリング監視を自動フェールオーバーの有効化のために使用**] の一覧で、フェールオーバーのシナリオにおいて監視サーバーとして機能する SQL Server を選択します。 監視サーバーは、常設チャットサーバーのデータをミラーリングまたはホストしませんが、ミラー化された構成内の1つの SQL Server のみがアクティブな SQL Server であることを常に確認します。
  
[**新規**] をクリックして、新しい sql server 監視を定義します。必要に応じて、永続的なチャット sql server ミラーリング監視用のインスタンスを作成します。
  
前のプール定義ダイアログに戻るには、[**戻る**] をクリックします。
  
このプールの SQL Server ストア構成のオプションを入力して、常設チャットサーバープールの定義を続行するには、[**次へ**] をクリックします。
  
すべての変更を破棄して**新しい常設チャット プールの定義**ウィザードを終了するには、[**キャンセル**] をクリックします。
  
このページのような状況依存のヘルプにアクセスするには、[**ヘルプ**] をクリックします。
  
## <a name="see-also"></a>関連項目

[Skype for Business Server 2015 の常設チャット サーバーの計画](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[Skype for Business Server 2015 トポロジに常設チャットサーバーを追加する](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
  
[Skype for Business Server 2015 の常設チャット サーバーのハードウェアおよびソフトウェア要件](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[Skype for Business Server 2015 のトポロジの基本](../../plan-your-deployment/topology-basics/topology-basics.md)
  
[Skype for Business Server 2015 での常設チャット サーバーの高可用性および障害復旧の構成](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)
