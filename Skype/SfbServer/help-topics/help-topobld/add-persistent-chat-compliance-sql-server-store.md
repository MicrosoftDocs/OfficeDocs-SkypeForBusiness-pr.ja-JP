---
title: 常設チャット コンプライアンス SQL Server ストアの追加
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddPersistentChatComplianceStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b9771b53-e19a-4a12-bf01-24bae6f7e482
description: 常設チャットサーバーまたは常設チャットサーバーのコンプライアンス機能のデータベースを提供するコンプライアンス SQL Server ストアを構成します。
ms.openlocfilehash: 79d7351563f049c7d05a0d592ecb3d65dba3eebb
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34281761"
---
# <a name="add-persistent-chat-compliance-sql-server-store"></a>常設チャット コンプライアンス SQL Server ストアの追加
 
常設チャットサーバーまたは常設チャットサーバーのコンプライアンス機能のデータベースを提供するコンプライアンス SQL Server ストアを構成します。
  
 **Sql server ストア**: 既存の sql server を選択し、必要に応じて常設チャットのインスタンスも選択します。
  
[**新規**] をクリックして、新しい SQL Server を定義し、必要に応じて、常設チャットのコンプライアンスデータ用の新しいインスタンスを作成します。
  
[ **Sql server ストアのミラーリングを有効**にする] チェックボックスをオンにして、sql server データベースと、常設チャットのコンプライアンスデータのミラーリングされたデータベースを提供するオプションのインスタンスを構成します。
  
リストの**ミラーリング Sql server ストア**から選択します。 sql server とオプションのインスタンスは、常設チャットのコンプライアンス sql SERVER の sql server ミラーとして機能します。
  
[**新規**] をクリックして、新しい sql server を定義し、必要に応じて、常設チャットの sql server ミラーリング用の新しいインスタンスを作成します。
  
[**SQL Server ミラーリング監視を自動フェールオーバーの有効化のために使用**] の一覧で、フェールオーバーのシナリオにおいて監視サーバーとして機能する SQL Server を選択します。 監視サーバーは、常設チャットサーバーのデータをミラーリングまたはホストしませんが、ミラー化された構成内の1つの SQL Server のみがアクティブな SQL Server であることを常に確認します。
  
[**新規**] をクリックして、新しい sql server の監視を定義します。必要に応じて、永続的なチャット準拠の SQL server ミラーリング監視用のインスタンスを作成します。
  
前のプール定義ダイアログに戻るには、[**戻る**] をクリックします。
  
このプールの backup SQL Server ストア構成のオプションを入力して、常設チャットサーバープールの定義を続行するには、[**次へ**] をクリックします。
  
すべての変更を破棄して**新しい常設チャット プールの定義**ウィザードを終了するには、[**キャンセル**] をクリックします。
  
このページのような状況依存のヘルプにアクセスするには、[**ヘルプ**] をクリックします。
  
## <a name="see-also"></a>関連項目

[Skype for Business Server 2015 の常設チャット サーバーの計画](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[Skype for Business Server 2015 の常設チャット サーバーのハードウェアおよびソフトウェア要件](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[Skype for Business Server 2015 での常設チャット サーバーのコンプライアンス サービスの構成](../../manage/persistent-chat/configure-compliance.md)
