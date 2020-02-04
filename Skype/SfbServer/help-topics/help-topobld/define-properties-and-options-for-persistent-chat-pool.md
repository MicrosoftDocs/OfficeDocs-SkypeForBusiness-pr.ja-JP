---
title: 常設チャット プールのプロパティとオプションの定義
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.AddPersistentChatOptionsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f4914a44-2113-48f1-8299-4645fc7011b6
description: 常設チャットサーバープールまたは常設チャットサーバープールのオプションを構成するには、次のプロパティを定義します。
ms.openlocfilehash: 458e50ecc3ddd389a8e413e8f2dd368fc0f15369
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2020
ms.locfileid: "41697552"
---
# <a name="define-properties-and-options-for-persistent-chat-pool"></a>常設チャット プールのプロパティとオプションの定義
 
常設チャットサーバープールまたは常設チャットサーバープールのオプションを構成するには、次のプロパティを定義します。
  
 **常設チャットプールの表示名**: この常設チャットサーバーまたは常設チャットサーバープールに表示されるユーザーフレンドリ名を定義する必須プロパティ。
  
 [**常設チャットポート**: 常設チャットサーバーまたは常設チャットサーバープールがリッスンするポート番号を定義する必須プロパティ。
  
 **コンプライアンスを有効**にする: オプションの常設チャットのコンプライアンス機能とデータベースを展開して実装する場合は、このチェックボックスをオンにします。
  
 [ **Sql Server ストアのバックアップ] を使って、障害回復を有効**にする: 別の sql server 上に構成されているストアのバックアップセットから、常設チャットの SQL Server ストアの障害回復を展開して実装する場合は、このチェックボックスをオンにします。 詳細については、「 [Skype For Business server 2015 の常設チャットサーバー用に高可用性と障害回復を構成する](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)」を参照してください。
  
> [!NOTE]
> このオプションは、複数のサーバーで構成されたプールに対してのみ使用できます。 
  
 この**プールは、このサーバーまたは\<プールを構成\>するサイトサイトの既定のプールとして使用**します。これが、サイトの既定の常設チャットサーバーまたは常設チャットサーバープールになる場合は、このチェックボックスをオンにします。 既定の常設チャットサーバーまたは、サイトごとに1つの既定の常設が必要です。
  
> [!NOTE]
> トポロジに複数のサイトが含まれる場合は、[**このプールをすべてのサイトの既定プールとして使う**] チェック ボックスも表示されます。
  
前のプール定義ダイアログに戻るには、[**戻る**] をクリックします。
  
このプールのオプションの入力が完了したら、[**次へ**] をクリックして、常設チャットサーバープールの定義を続行します。
  
すべての変更を破棄して**新しい常設チャット プールの定義**ウィザードを終了するには、[**キャンセル**] をクリックします。
  
このページのような状況依存のヘルプにアクセスするには、[**ヘルプ**] をクリックします。
  
## <a name="see-also"></a>関連項目

[Skype for Business Server 2015 の常設チャット サーバーの計画](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[Skype for Business Server 2015 トポロジに常設チャットサーバーを追加する](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
