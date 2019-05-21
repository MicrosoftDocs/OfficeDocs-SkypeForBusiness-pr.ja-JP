---
title: モバイルクライアントのプッシュ通知の構成の作成または編集
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientPushNotificationCfgEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fb39af60-c999-42fb-9538-0bd87098f508
ROBOTS: NOINDEX, NOFOLLOW
description: プッシュ通知とプッシュ通知クリアリング ハウス (PNCH) は、モビリティ機能の重要な 2 つの構成要素です。プッシュ通知は、メッセージが PNCH に送信されるプロセスです。メッセージは、モバイル クライアントに配信されるか、タイムアウト期間が過ぎるまで、PNCH で保持されます。
ms.openlocfilehash: 3a15e88e40b37da4570d04a93ef13a793d6dabaf
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34300337"
---
# <a name="mobile-client-create-or-edit-push-notification-configuration"></a>モバイル クライアント: プッシュ通知の構成の作成または編集
 
プッシュ通知とプッシュ通知クリアリング ハウス (PNCH) は、モビリティ機能の重要な 2 つの構成要素です。プッシュ通知は、メッセージが PNCH に送信されるプロセスです。メッセージは、モバイル クライアントに配信されるか、タイムアウト期間が過ぎるまで、PNCH で保持されます。 
  
> [!NOTE]
> この期間はプッシュ通知クリアリング ハウス側の設定値なので、展開のユーザーまたは管理者は変更できません。 
  
プッシュ通知を有効にするには、次の操作を行います。
  
1. [**範囲**]: このポリシーの範囲を示します。設定値は、展開に含まれるすべてのユーザーにポリシーが適用される [**グローバル**]、または指定されたサイトのホーム サーバーに割り当てられたユーザーにのみポリシーが適用される [**サイト**] のどちらかです。
    
    > [!IMPORTANT]
    > あるポリシー レベルで適用されているポリシー設定が、他のポリシー レベルで適用されている設定によって無効になることがあります。ポリシーの優先順位は、ユーザー ポリシーが最も高く、サイト ポリシー、グローバル ポリシー (優先度が最も低い) と続きます。つまり、ポリシー設定が、そのポリシーの影響を受けるオブジェクトに近いほど、オブジェクトに及ぼす影響は大きくなります。 
  
2. 有効にするプッシュ通知サービスの種類を選択するには、対応するチェック ボックスをオンにします。
    
   - **Microsoft プッシュ通知を有効**にすると、Skype for business アプリを使用して、クラウドベースの Pnch For Windows Phone にプッシュ通知を有効にすることができます。
    
   - アップル**プッシュ通知を有効**にすると、APPLE Pnch for IOS (IPhone、iPad など) および Skype for business アプリを使用しているデバイスのプッシュ通知が有効になります。
    
3. ポリシーの編集が完了したら、[**コミット**] をクリックして変更内容を保存します。変更した設定を削除する必要がある場合は、[**キャンセル**] をクリックします。変更内容はポリシーに保存されません。
    

