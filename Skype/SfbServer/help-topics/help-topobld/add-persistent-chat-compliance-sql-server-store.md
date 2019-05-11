---
title: 常設チャット コンプライアンス SQL Server ストアの追加
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddPersistentChatComplianceStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b9771b53-e19a-4a12-bf01-24bae6f7e482
description: 永続的なチャット サーバーまたはコンプライアンス機能の永続的なチャット サーバーのデータベースを提供する SQL Server の格納に準拠を構成するとします。
ms.openlocfilehash: 02caeac7641cd592f6ca16d1e739253b0f48a30d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33897626"
---
# <a name="add-persistent-chat-compliance-sql-server-store"></a>常設チャット コンプライアンス SQL Server ストアの追加
 
永続的なチャット サーバーまたはコンプライアンス機能の永続的なチャット サーバーのデータベースを提供する SQL Server の格納に準拠を構成するとします。
  
 **SQL Server に格納**します。 永続的なチャットの既存の SQL Server およびインスタンスを選択します。
  
新しい SQL Server と、オプションで対応データの永続的なチャットの新しいインスタンスを定義するのには**新規**をクリックします。
  
対応データの永続的なチャットにミラー化されたデータベースを提供する省略可能なインスタンスと、SQL Server データベースを構成するのには**SQL Server を有効にするストアがミラー化**のチェック ボックスをオンにします。
  
永続的なチャット コンプライアンス SQL Server の SQL Server ミラーとして動作するには、SQL Server と省略可能なインスタンスを**SQL Server のミラーを格納**するリストから選択します。
  
新しい SQL Server と、オプションで永続的なチャットの SQL Server のミラーリング用の新しいインスタンスを定義するのには**新規**をクリックします。
  
[**SQL Server ミラーリング監視を自動フェールオーバーの有効化のために使用**] の一覧で、フェールオーバーのシナリオにおいて監視サーバーとして機能する SQL Server を選択します。 ミラーリング監視サーバーはミラーまたはホストのデータは、永続的なチャット サーバーですが、により、ミラー化構成で SQL Server を 1 つだけアクティブな SQL Server の任意の時点。
  
必要に応じて永続的なチャット コンプライアンス ミラーリング監視を SQL Server のインスタンスの新しい SQL Server のミラーリング監視サーバーを定義するのには**新規**をクリックします。
  
前のプール定義ダイアログに戻るには、[**戻る**] をクリックします。
  
このプールのバックアップ SQL Server ストア構成の永続的なチャット サーバー プールの定義を続行するオプションの入力が終了したら**次へ**をクリックします。
  
すべての変更を破棄して**新しい常設チャット プールの定義**ウィザードを終了するには、[**キャンセル**] をクリックします。
  
このページのような状況依存のヘルプにアクセスするには、[**ヘルプ**] をクリックします。
  
## <a name="see-also"></a>関連項目

[Skype for Business Server 2015 の常設チャット サーバーの計画](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[Skype for Business Server 2015 の常設チャット サーバーのハードウェアおよびソフトウェア要件](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[Skype for Business Server 2015 での常設チャット サーバーのコンプライアンス サービスの構成](../../manage/persistent-chat/configure-compliance.md)
