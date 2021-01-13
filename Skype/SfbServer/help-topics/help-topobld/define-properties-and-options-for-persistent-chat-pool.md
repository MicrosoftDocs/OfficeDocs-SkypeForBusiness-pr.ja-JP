---
title: 常設チャット プールのプロパティとオプションの定義
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
- ms.lync.tb.AddPersistentChatOptionsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f4914a44-2113-48f1-8299-4645fc7011b6
description: 常設チャット サーバーまたは常設チャット サーバー プールのオプションを構成するには、次のプロパティを定義します。
ms.openlocfilehash: acc80c76e79364be730ec56a2b64e5dcd001f661
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49818427"
---
# <a name="define-properties-and-options-for-persistent-chat-pool"></a>常設チャット プールのプロパティとオプションの定義
 
常設チャット サーバーまたは常設チャット サーバー プールのオプションを構成するには、次のプロパティを定義します。
  
 **常設チャット プールの** 表示名 : この常設チャット サーバーまたは常設チャット サーバー プールに対して表示されるユーザー フレンドリーな名前を定義する必須のプロパティ。
  
 **常設チャット ポート**: この常設チャット サーバーまたは常設チャット サーバー プールがリッスンするポート番号を定義する必須のプロパティです。
  
 **コンプライアンスの有効化**: オプションの常設チャット コンプライアンス機能とデータベースを展開して実装する場合は、このチェック ボックスをオンにします。
  
 **障害復旧を有効にするには**、バックアップ SQL Server ストアを使用します。別の SQL Server 上の構成済みのストア セットから常設チャット SQL Server ストアの障害復旧を展開および実装する場合は、このチェック ボックスをオンにします。 詳細については [、「Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015」を参照](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)してください。
  
> [!NOTE]
> このオプションは、複数のサーバーを持つプールでのみ使用できます。 
  
 **サイトの既定として \<site that this server or pool is being configured in\>** このプールを使用する: これがサイトの既定の常設チャット サーバーまたは常設チャット サーバー プールになる場合は、このチェック ボックスをオンにします。 サイトごとに既定の常設チャット サーバーまたはプールが 1 つ必要です。
  
> [!NOTE]
> トポロジに複数のサイトが含まれる場合は、[このプールをすべてのサイトの既定として使用する] チェック ボックス **も** 表示されます。
  
前のプール定義ダイアログに戻るには、[**戻る**] をクリックします。
  
この **プール** のオプションの入力が完了したら、[次へ] をクリックして、常設チャット サーバー プールの定義を続行します。
  
すべての変更を破棄して **新しい常設チャット プールの定義** ウィザードを終了するには、[**キャンセル**] をクリックします。
  
このページのような状況依存のヘルプにアクセスするには、[**ヘルプ**] をクリックします。
  
## <a name="see-also"></a>関連項目

[Skype for Business Server 2015 での常設チャット サーバーの計画](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[Skype for Business Server 2015 トポロジへの常設チャット サーバーの追加](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
