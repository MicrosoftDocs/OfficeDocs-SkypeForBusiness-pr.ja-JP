---
title: 常設チャット SQL Server ストアの追加
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/27/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddPersistentChatSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c8e6064a-8127-4c25-8685-06f49d8bbfce
description: 永続的なチャット サーバーまたはプールの永続的なチャット サーバーのデータベースを提供する SQL Server ストアを構成するとします。
ms.openlocfilehash: 856c74db37ef99243e024b0c044b20d095ca6ba6
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30899562"
---
# <a name="add-persistent-chat-sql-server-store"></a>常設チャット SQL Server ストアの追加
 
永続的なチャット サーバーまたはプールの永続的なチャット サーバーのデータベースを提供する SQL Server ストアを構成するとします。
  
 **SQL Server に格納**します。 永続的なチャットの既存の SQL Server およびインスタンスを選択します。
  
新しい SQL Server および必要に応じてデータの永続的なチャットの新しいインスタンスを定義するのには**新規**をクリックします。
  
SQL Server データベースおよび永続的なチャットのデータのミラー化されたデータベースを提供する省略可能なインスタンスを構成する**SQL Server を有効にするストアがミラー化**のチェック ボックスをオンにします。
  
永続的なチャットの SQL Server 用の SQL Server ミラーとして動作するには、SQL Server と省略可能なインスタンスを**SQL Server のミラーを格納**するリストから選択します。
  
新しい SQL Server と、オプションで永続的なチャットの SQL Server のミラーリング用の新しいインスタンスを定義するのには**新規**をクリックします。
  
[**SQL Server ミラーリング監視を自動フェールオーバーの有効化のために使用**] の一覧で、フェールオーバーのシナリオにおいて監視サーバーとして機能する SQL Server を選択します。 ミラーリング監視サーバーはミラーまたはホストのデータは、永続的なチャット サーバーですが、により、ミラー化構成で SQL Server を 1 つだけアクティブな SQL Server の任意の時点。
  
新しい SQL Server のミラーリング監視サーバー インスタンスでは必要に応じて、永続的なチャット SQL Server ミラーリング監視を定義する**新規**をクリックします。
  
前のプール定義ダイアログに戻るには、[**戻る**] をクリックします。
  
このプールの SQL Server ストア構成の永続的なチャット サーバー プールの定義を続行するオプションの入力が終了したら**次へ**をクリックします。
  
すべての変更を破棄して**新しい常設チャット プールの定義**ウィザードを終了するには、[**キャンセル**] をクリックします。
  
このページのような状況依存のヘルプにアクセスするには、[**ヘルプ**] をクリックします。
  
## <a name="see-also"></a>関連項目

[Skype for Business Server 2015 の常設チャット サーバーの計画](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[ビジネス サーバー 2015 トポロジの場合、Skype に永続的なチャット サーバーを追加します。](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
  
[Skype for Business Server 2015 の常設チャット サーバーのハードウェアおよびソフトウェア要件](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[Topology Basics for Skype for Business Server 2015](../../plan-your-deployment/topology-basics/topology-basics.md)
  
[Skype for Business Server 2015 での常設チャット サーバーの高可用性および障害復旧の構成](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)
