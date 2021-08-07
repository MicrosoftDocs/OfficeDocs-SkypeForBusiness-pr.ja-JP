---
title: 常設チャット SQL Server ストアを追加する
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
- ms.lync.tb.AddPersistentChatSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c8e6064a-8127-4c25-8685-06f49d8bbfce
description: 常設チャット サーバー SQL Server常設チャット サーバー プールのデータベースを提供するサーバー ストアを構成します。
ms.openlocfilehash: 62e4eeab923f4af1671047b00141cd06bfe477ef6c140d66be28210eceab4246
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54277012"
---
# <a name="add-persistent-chat-sql-server-store"></a>常設チャット SQL Server ストアの追加
 
常設チャット サーバー SQL Server常設チャット サーバー プールのデータベースを提供するサーバー ストアを構成します。
  
 **SQL Serverストア**: 既存のストアを選択SQL Server、必要に応じて常設チャットのインスタンスを選択します。
  
[**新規]** をクリックして新しいSQL Serverし、必要に応じて常設チャット データの新しいインスタンスを定義します。
  
[ストア **ミラーリングSQL Server有効** にする] チェック ボックスをオンにして、永続的なチャット データSQL Serverミラー化されたデータベースを提供するデータベースとオプションのインスタンスを構成します。
  
[ミラーリング] リストから選択 **SQL Server、SQL Server** 常設チャット サーバーのSQL Serverミラーとして機能するSQL Server。
  
[**新規]** をクリックして新しいSQL Serverし、必要に応じて常設チャット の新しいインスタンスをミラーリングSQL Serverします。
  
[**SQL Server ミラーリング監視を自動フェールオーバーの有効化のために使用**] の一覧で、フェールオーバーのシナリオにおいて監視サーバーとして機能する SQL Server を選択します。 ミラーリング監視サーバーは、常設チャット サーバーのデータをミラーリングまたはホストしませんが、ミラーリングされた構成内の 1 つの SQL Server だけがアクティブなSQL Server状態になります。
  
[**新規]** をクリックして、SQL Serverミラーリング監視のインスタンスを必要に応じて定義SQL Serverします。
  
前のプール定義ダイアログに戻るには、[**戻る**] をクリックします。
  
この **プールの** ストア構成のオプションの入力が完了したら、[SQL Server] をクリックして、常設チャット サーバー プール定義を続行します。
  
すべての変更を破棄して **新しい常設チャット プールの定義** ウィザードを終了するには、[**キャンセル**] をクリックします。
  
このページのような状況依存のヘルプにアクセスするには、[**ヘルプ**] をクリックします。
  
## <a name="see-also"></a>関連項目

[2015 年の常設チャット サーバー Skype for Business Serverする](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[常設チャット サーバーを 2015 Skype for Business Serverトポロジに追加する](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
  
[2015 年の常設チャット サーバーのハードウェア要件とソフトウェア要件Skype for Business Server](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[2015 年のサーバー Skype for Business Server要件](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[トポロジ 2015 Skype for Business Serverの基本](../../plan-your-deployment/topology-basics/topology-basics.md)
  
[2015 年に常設チャット サーバーの高可用性と障害復旧をSkype for Business Serverする](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)
