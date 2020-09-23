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
- CSH
ms.custom:
- ms.lync.tb.AddPersistentChatOptionsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f4914a44-2113-48f1-8299-4645fc7011b6
description: 常設チャットサーバーまたは常設チャットサーバープールのオプションを構成するには、次のプロパティを定義します。
ms.openlocfilehash: 8d3cef04d7089ffff640740bb048ca52cf7fd91e
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2020
ms.locfileid: "48218548"
---
# <a name="define-properties-and-options-for-persistent-chat-pool"></a>常設チャット プールのプロパティとオプションの定義
 
常設チャットサーバーまたは常設チャットサーバープールのオプションを構成するには、次のプロパティを定義します。
  
 **常設チャットプールの表示名**: この常設チャットサーバーまたは常設チャットサーバープールに表示されるユーザーフレンドリ名を定義する必須のプロパティ。
  
 **常設チャットポート**: この常設チャットサーバーまたは常設チャットサーバープールがリッスンするポート番号を定義する必須のプロパティ。
  
 [**コンプライアンスを有効に**する]: オプションの常設チャットコンプライアンス機能とデータベースを展開および実装する予定の場合は、このチェックボックスをオンにします。
  
 [**バックアップ SQL server ストアを使用して障害復旧を有効**にする]: 別の sql server にある構成済みのバックアップセットから、常設チャットの sql server ストアの障害復旧を展開および実装する場合は、このチェックボックスをオンにします。 詳細については、「 [Configure high availability and disaster recovery For Persistent Chat server For Skype For Business server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)」を参照してください。
  
> [!NOTE]
> このオプションは、複数のサーバーから成るプールに対してのみ使用できます。 
  
 [ ** \<site that this server or pool is being configured in\> サイトの既定のプールとして使用**する]: これがサイトの既定の常設チャットサーバーまたは常設チャットサーバープールの場合は、このチェックボックスをオンにします。 サイトごとに、常設チャットサーバーまたは1つの既定の常設が必要です。
  
> [!NOTE]
> トポロジに複数のサイトが含まれている場合は、[ **このプールをすべてのサイトの既定として使用** する] チェックボックスも表示されます。
  
前のプール定義ダイアログに戻るには、[**戻る**] をクリックします。
  
このプールのオプションの入力が終了したら、[ **次へ** ] をクリックして、常設チャットサーバープールの定義を続行します。
  
すべての変更を破棄して**新しい常設チャット プールの定義**ウィザードを終了するには、[**キャンセル**] をクリックします。
  
このページのような状況依存のヘルプにアクセスするには、[**ヘルプ**] をクリックします。
  
## <a name="see-also"></a>関連項目

[Skype for Business Server 2015 での常設チャットサーバーの計画](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[常設チャットサーバーを Skype for Business Server 2015 トポロジに追加する](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
