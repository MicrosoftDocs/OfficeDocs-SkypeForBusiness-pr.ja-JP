---
title: 常設チャット コンプライアンス SQL Server ストアの追加
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddPersistentChatComplianceStorePage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: b9771b53-e19a-4a12-bf01-24bae6f7e482
description: 常設チャット サーバーまたは常設チャット SQL Serverのコンプライアンス機能にデータベースを提供するコンプライアンス ストアを構成します。
ms.openlocfilehash: e6db005c44606a7d79f25e5999630cc805ed5f54
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/04/2021
ms.locfileid: "60747843"
---
# <a name="add-persistent-chat-compliance-sql-server-store"></a>常設チャット コンプライアンス SQL Server ストアの追加
 
常設チャット サーバーまたは常設チャット SQL Serverのコンプライアンス機能にデータベースを提供するコンプライアンス ストアを構成します。
  
 **SQL Serverストア**: 既存のストアを選択SQL Server、必要に応じて常設チャットのインスタンスを選択します。
  
[**新規]** をクリックして新しいSQL Serverし、必要に応じて常設チャット コンプライアンス データの新しいインスタンスを定義します。
  
[ストア **ミラーリングSQL Server** 有効にする] チェック ボックスをオンにして、永続的なチャット コンプライアンス データSQL Serverミラー化されたデータベースを提供する SQL Server データベースとオプションのインスタンスを構成します。
  
[ミラーリング] リストから選択 **SQL Server、SQL Server** およびオプションのインスタンスを格納し、常設チャット コンプライアンス SQL Serverミラーとして機能SQL Server。
  
[**新規]** をクリックして新しいSQL Serverし、必要に応じて常設チャット の新しいインスタンスをミラーリングSQL Serverします。
  
[**SQL Server ミラーリング監視を自動フェールオーバーの有効化のために使用**] の一覧で、フェールオーバーのシナリオにおいて監視サーバーとして機能する SQL Server を選択します。 ミラーリング監視サーバーは、常設チャット サーバーのデータをミラーリングまたはホストしませんが、ミラーリングされた構成内の 1 つの SQL Server だけがアクティブなSQL Server状態になります。
  
[**新規]** をクリックして、SQL Serverミラーリング監視の常設チャット コンプライアンスのインスタンスをSQL Serverします。
  
前のプール定義ダイアログに戻るには、[**戻る**] をクリックします。
  
[**次へ**] をクリックして、このプールのバックアップ サーバーのSQL Serverを入力し、常設チャット サーバー プールの定義を続行します。
  
すべての変更を破棄して **新しい常設チャット プールの定義** ウィザードを終了するには、[**キャンセル**] をクリックします。
  
このページのような状況依存のヘルプにアクセスするには、[**ヘルプ**] をクリックします。
  
## <a name="see-also"></a>関連項目

[2015 年の常設チャット サーバー Skype for Business Serverする](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[2015 年のサーバー Skype for Business Server要件](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[2015 年の常設チャット サーバーのハードウェア要件とソフトウェア要件Skype for Business Server](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[2015 年の常設チャット サーバーのコンプライアンス Skype for Business Server構成する](../../manage/persistent-chat/configure-compliance.md)
