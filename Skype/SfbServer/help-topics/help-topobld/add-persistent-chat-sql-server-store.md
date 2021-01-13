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
description: 常設チャット サーバー SQL Serverデータベースを提供する常設チャット サーバー ストアを構成します。
ms.openlocfilehash: e93705e0646f1115994a61c936a5c0cb16149dfa
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49818657"
---
# <a name="add-persistent-chat-sql-server-store"></a>常設チャット SQL Server ストアの追加
 
常設チャット サーバー SQL Serverデータベースを提供する常設チャット サーバー ストアを構成します。
  
 **SQL Serverストア**: 既存のチャット を選択SQL Server、必要に応じて常設チャットのインスタンスを選択します。
  
[ **新規]** をクリックして、新SQL Serverし、必要に応じて常設チャット データの新しいインスタンスを定義します。
  
常設チャット **データSQL Server** データベースを提供する SQL Server データベースとオプションのインスタンスを構成するには、[ストア ミラーリングの有効化] チェック ボックスをオンにします。
  
[ミラーリング] リストから選択 **SQL Server常設** チャット SQL Serverのミラーとして機能するSQL Serverおよびオプションのインスタンスを格納SQL Server。
  
[ **新規]** をクリックして新しいSQL Serverし、必要に応じて常設チャット の新しいインスタンスをSQL Serverします。
  
[**SQL Server ミラーリング監視を自動フェールオーバーの有効化のために使用**] の一覧で、フェールオーバーのシナリオにおいて監視サーバーとして機能する SQL Server を選択します。 ミラーリング監視サーバーは、常設チャット サーバーのデータをミラー化またはホストしませんが、ミラー化された構成の 1 つの SQL Server だけがアクティブなチャット サーバー SQL Server保証します。
  
[ **新規]** をクリックして、SQL Serverミラーリング監視のインスタンスを必要に応じて新しいSQL Server定義します。
  
前のプール定義ダイアログに戻るには、[**戻る**] をクリックします。
  
この **プール** のストア構成のオプションの入力が完了したら、[次へ] をSQL Serverし、常設チャット サーバー プールの定義に進みます。
  
すべての変更を破棄して **新しい常設チャット プールの定義** ウィザードを終了するには、[**キャンセル**] をクリックします。
  
このページのような状況依存のヘルプにアクセスするには、[**ヘルプ**] をクリックします。
  
## <a name="see-also"></a>関連項目

[Skype for Business Server 2015 での常設チャット サーバーの計画](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[Skype for Business Server 2015 トポロジへの常設チャット サーバーの追加](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
  
[Skype for Business Server 2015 の常設チャット サーバーのハードウェア要件およびソフトウェア要件](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[Skype for Business Server 2015 のサーバー要件](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[Skype for Business Server 2015 のトポロジの基本](../../plan-your-deployment/topology-basics/topology-basics.md)
  
[Skype for Business Server 2015 での常設チャット サーバーの高可用性と障害復旧の構成](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)
