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
ms.openlocfilehash: 76556335f87a673c5ae6d8df576bd6fd47d140ae9338c27183d58971ebe4a439
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54281110"
---
# <a name="define-properties-and-options-for-persistent-chat-pool"></a>常設チャット プールのプロパティとオプションの定義
 
常設チャット サーバーまたは常設チャット サーバー プールのオプションを構成するには、次のプロパティを定義します。
  
 **常設チャット プールの表示** 名: この常設チャット サーバーまたは常設チャット サーバー プールに表示されるユーザー フレンドリー名を定義する必須プロパティ。
  
 **常設チャット ポート**: この常設チャット サーバーまたは常設チャット サーバー プールがリッスンするポート番号を定義する必要なプロパティ。
  
 **コンプライアンスを有効** にする: オプションの常設チャット コンプライアンス機能とデータベースを展開して実装する場合は、チェック ボックスをオンにします。
  
 **バックアップ SQL Server** ストアを使用して障害復旧を有効にする : 別の SQL Server の構成済みのバックアップ セットから常設チャット SQL Server ストアの障害復旧を展開および実装する場合は、このチェック ボックスをオンにします。 詳細については、「Configure High availability and disaster recovery for Persistent Chat Server in Skype for Business Server [2015」を参照](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)してください。
  
> [!NOTE]
> このオプションは、複数のサーバーを持つプールでのみ使用できます。 
  
 **このプールをサイトの既定 \<site that this server or pool is being configured in\>** として使用する: サイトの既定の常設チャット サーバーまたは常設チャット サーバー プールになる場合は、このチェック ボックスをオンにします。 サイトごとに 1 つの既定の常設チャット サーバーまたは pol が必要です。
  
> [!NOTE]
> トポロジに複数のサイトが含まれる場合は、[このプールをすべてのサイトで既定として使用する] チェック ボックス **も** 表示されます。
  
前のプール定義ダイアログに戻るには、[**戻る**] をクリックします。
  
常設 **チャット** サーバー プール定義を続行するには、このプールのオプションの入力が完了したら、[次へ] をクリックします。
  
すべての変更を破棄して **新しい常設チャット プールの定義** ウィザードを終了するには、[**キャンセル**] をクリックします。
  
このページのような状況依存のヘルプにアクセスするには、[**ヘルプ**] をクリックします。
  
## <a name="see-also"></a>関連項目

[2015 年の常設チャット サーバー Skype for Business Serverする](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[常設チャット サーバーを 2015 Skype for Business Serverトポロジに追加する](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
