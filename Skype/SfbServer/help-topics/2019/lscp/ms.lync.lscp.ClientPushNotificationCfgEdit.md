---
title: Mobile Client Create or Edit Push Notification Configuration
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.ClientPushNotificationCfgEdit
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: fb39af60-c999-42fb-9538-0bd87098f508
ROBOTS: NOINDEX, NOFOLLOW
description: プッシュ通知とプッシュ通知クリアリング ハウス (PNCH) は、モビリティ機能の 2 つの重要な部分です。 プッシュ通知は、メッセージが PNCH に送信されるプロセスです。 メッセージは、モバイル クライアントに配信できるまで、またはタイムアウト期間が切れるまで、ここで保持されます。
ms.openlocfilehash: 7e214b9fa92db420b0451d2a32e8158df2d5212c4394fb7307a7198ff733c425
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54316293"
---
# <a name="mobile-client-create-or-edit-push-notification-configuration"></a>モバイル クライアント: プッシュ通知の構成の作成または編集
 
プッシュ通知とプッシュ通知クリアリング ハウス (PNCH) は、モビリティ機能の 2 つの重要な部分です。 プッシュ通知は、メッセージが PNCH に送信されるプロセスです。 メッセージは、モバイル クライアントに配信できるまで、またはタイムアウト期間が切れるまで、ここで保持されます。 
  
> [!NOTE]
> 期間はプッシュ通知クリアリング ハウスで設定され、展開のユーザーまたは管理者は構成できません。 
  
プッシュ通知を有効にするには、次の操作を行います。
  
1. **スコープ:** このポリシーのスコープに注意してください。 これは、この展開 **のすべての** ユーザーに適用されるグローバル 、または指定したサイト内のホーム サーバーに割り当てられたユーザーのみであるサイトのいずれかです。
    
    > [!IMPORTANT]
    > あるポリシー レベルで適用されているポリシー設定が、他のポリシー レベルで適用されている設定をオーバーライドすることがあります。 ポリシーの優先順位は、ユーザー ポリシー (ほとんどの影響) がサイト ポリシーを上書きし、サイト ポリシーがグローバル ポリシーを上書きします (影響が最も少ない)。 つまり、ポリシー設定が、そのポリシーの影響を受けるオブジェクトに近いほど、オブジェクトに及ぼす影響は大きくなります。 
  
2. 有効にするプッシュ通知サービスを選択するには、次のチェック ボックスをオンにします。
    
   - **Microsoft プッシュ通知を有効** にすると、クラウド ベースの PNCH へのプッシュ通知が有効Windows PhoneアプリSkype for Businessできます
    
   - **Apple のプッシュ通知** を有効にすると、Apple の iOS を実行しているデバイス (iPhone、iPad など) とアプリを使用するデバイスの Apple PNCH へのプッシュ通知が有効Skype for Business
    
3. ポリシーの編集が完了したら、[コミット] をクリックして **変更を** 保存します。 行った変更を削除する必要がある場合は、[キャンセル] を **選択します**。 ポリシーに対する変更は保存されません。
    

