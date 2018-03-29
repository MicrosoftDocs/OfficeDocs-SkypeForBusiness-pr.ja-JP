---
title: 常設チャット コンプライアンス バックアップ SQL Server ストアの追加
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/27/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddPersistentChatBackupComplianceStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 358b74bd-a97d-4f28-9bed-af633ea0099e
description: 永続的なチャット サーバーのデータベースのバックアップを提供するように SQL Server に格納されてバックアップ コンプライアンスまたは SQL Server に格納する永続的なチャット サーバー コンプライアンスを構成するとします。
ms.openlocfilehash: 4e3a2bf034d5ab20c7352f2b6ef9c8a6a0c4befa
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="add-persistent-chat-compliance-backup-sql-server-store"></a>常設チャット コンプライアンス バックアップ SQL Server ストアの追加
 
永続的なチャット サーバーのデータベースのバックアップを提供するように SQL Server に格納されてバックアップ コンプライアンスまたは SQL Server に格納する永続的なチャット サーバー コンプライアンスを構成するとします。
  
 **SQL Server に格納**します。 永続的なチャットの既存の SQL Server およびインスタンスを選択します。
  
新しい SQL Server と、オプションで永続的なチャットのコンプライアンスのバックアップ ・ データの新しいインスタンスを定義するのには**新規**をクリックします。
  
SQL Server データベースおよび永続的なチャットのコンプライアンスのバックアップ ・ データのミラー化されたデータベースを提供する省略可能なインスタンスを構成する**SQL Server を有効にするストアがミラー化**のチェック ボックスをオンにします。
  
永続的なチャットのバックアップ コンプライアンス SQL Server の SQL Server ミラーとして動作するには、SQL Server と省略可能なインスタンスを**SQL Server のミラーを格納**するリストから選択します。
  
新しい SQL Server と、オプションで永続的なチャットの SQL Server のミラーリング用の新しいインスタンスを定義するのには**新規**をクリックします。
  
[**SQL Server ミラーリング監視を自動フェールオーバーの有効化のために使用**] の一覧で、フェールオーバーのシナリオにおいて監視サーバーとして機能する SQL Server を選択します。 ミラーリング監視サーバーはミラーまたはホストのデータは、永続的なチャット サーバーですが、により、ミラー化構成で SQL Server を 1 つだけアクティブな SQL Server の任意の時点。
  
必要に応じて永続的なチャットのバックアップ コンプライアンス ミラーリング監視を SQL Server のインスタンスの新しい SQL Server のミラーリング監視サーバーを定義するのには**新規**をクリックします。
  
前のプール定義ダイアログに戻るには、[**戻る**] をクリックします。
  
このプールのバックアップ SQL Server ストア構成の永続的なチャット サーバー プールの定義を続行するオプションの入力が終了したら**次へ**をクリックします。
  
すべての変更を破棄して**新しい常設チャット プールの定義**ウィザードを終了するには、[**キャンセル**] をクリックします。
  
このページのような状況依存のヘルプにアクセスするには、[**ヘルプ**] をクリックします。
  
## <a name="see-also"></a>関連項目

#### 

[ビジネス サーバー 2015 の Skype での永続的なチャット サーバーの計画](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[ビジネス サーバー 2015 の Skype のサーバーの要件](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[ビジネス サーバー 2015 の Skype での永続的なチャット サーバーのハードウェアおよびソフトウェアの要件](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[ビジネス サーバー 2015 の Skype で永続的なチャット サーバーのコンプライアンス サービスを構成します。](../../manage/persistent-chat/configure-compliance.md)
  
[ビジネス サーバー 2015 の Skype での永続的なチャット サーバーの高可用性と障害回復を構成します。](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)

