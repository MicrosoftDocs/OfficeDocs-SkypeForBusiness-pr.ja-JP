---
title: 常設チャット SQL Server ストアを追加する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddPersistentChatSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c8e6064a-8127-4c25-8685-06f49d8bbfce
description: 常設チャットサーバーまたは常設チャットサーバープールのデータベースを提供する SQL Server ストアを構成します。
ms.openlocfilehash: 2771b63063e155973cd711c4b80f06dee46e1865
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2020
ms.locfileid: "48216328"
---
# <a name="add-persistent-chat-sql-server-store"></a>常設チャット SQL Server ストアを追加する
 
常設チャットサーバーまたは常設チャットサーバープールのデータベースを提供する SQL Server ストアを構成します。
  
 [ **Sql server ストア**]: 既存の sql server と、必要に応じて常設チャットのインスタンスを選択します。
  
[ **新規** ] をクリックして、新しい SQL Server と、必要に応じて常設チャットデータの新しいインスタンスを定義します。
  
[ **Sql server ストアミラーリングの有効化** ] チェックボックスをオンにして、永続的なチャットデータのミラーリングされたデータベースを提供する sql server データベースとオプションのインスタンスを構成します。
  
[ **ミラーリング Sql server ストア** ] の一覧から、常設チャット sql SERVER の sql server ミラーとして機能する sql server とオプションのインスタンスを選択します。
  
[ **新規** ] をクリックして、新しい sql server を定義し、オプションで常設チャットの sql server ミラーリング用の新しいインスタンスを定義します。
  
[**SQL Server ミラーリング監視を自動フェールオーバーの有効化のために使用**] の一覧で、フェールオーバーのシナリオにおいて監視サーバーとして機能する SQL Server を選択します。 ミラーリング監視サーバーは、常設チャットサーバーのデータをミラーリングまたはホストしませんが、ミラーリング構成の SQL サーバーが常にアクティブな SQL Server であることを保証します。
  
[ **新規** ] をクリックして、新しい sql server 監視を定義します。オプションで、常設チャット sql server ミラーリング監視のインスタンスを定義します。
  
前のプール定義ダイアログに戻るには、[**戻る**] をクリックします。
  
このプールの SQL Server ストア構成のオプションの入力が終了した後、[ **次へ** ] をクリックして、常設チャットサーバープールの定義を続行します。
  
すべての変更を破棄して**新しい常設チャット プールの定義**ウィザードを終了するには、[**キャンセル**] をクリックします。
  
このページのような状況依存のヘルプにアクセスするには、[**ヘルプ**] をクリックします。
  
## <a name="see-also"></a>関連項目

[Skype for Business Server 2015 での常設チャットサーバーの計画](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[常設チャットサーバーを Skype for Business Server 2015 トポロジに追加する](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
  
[Skype for Business Server 2015 の常設チャットサーバーのハードウェアおよびソフトウェア要件](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[Skype for Business Server 2015 のサーバー要件](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[Skype for Business Server 2015 のトポロジの基本](../../plan-your-deployment/topology-basics/topology-basics.md)
  
[Skype for Business Server 2015 での常設チャットサーバーの高可用性および障害復旧の構成](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)
