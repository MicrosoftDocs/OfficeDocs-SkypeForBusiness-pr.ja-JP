---
title: モバイル クライアントプッシュ通知構成の作成または編集
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.ClientPushNotificationCfgEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fb39af60-c999-42fb-9538-0bd87098f508
description: プッシュ通知とプッシュ通知クリアリング 家 (PNCH) は、モビリティ機能の 2 つの重要な部分です。 プッシュ通知は、メッセージが PNCH に送信されるプロセスです。 メッセージがモバイル クライアントに配信されるか、タイムアウト期間が経過するまで、メッセージはここで保持されます。
ms.openlocfilehash: 0cd2b17f764891dbb1ad89ada27f6be0b6246ba0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49810887"
---
# <a name="mobile-client-create-or-edit-push-notification-configuration"></a>モバイル クライアント: プッシュ通知の構成の作成または編集
 
プッシュ通知とプッシュ通知クリアリング 家 (PNCH) は、モビリティ機能の 2 つの重要な部分です。 プッシュ通知は、メッセージが PNCH に送信されるプロセスです。 メッセージは、モバイル クライアントに配信されるか、タイムアウト期間が経過するまで、ここで保持されます。 
  
> [!NOTE]
> この期間は、プッシュ通知クリアリング 家で設定され、展開のユーザーまたは管理者は構成できません。 
  
プッシュ通知を有効にするには、次の操作を行います。
  
1. **スコープ:** このポリシーのスコープをメモします。 グローバル **(この展開** のすべてのユーザーに適用される) またはサイト (指定したサイト内のホーム サーバーに割り当てられているユーザーのみ) のいずれかを指定できます。
    
    > [!IMPORTANT]
    > あるポリシー レベルで適用されているポリシー設定が、他のポリシー レベルで適用されている設定をオーバーライドすることがあります。 ポリシーの優先順位は、ユーザー ポリシー (最も影響を受ける) がサイト ポリシーを上書きし、サイト ポリシーがグローバル ポリシーよりも優先される (最も影響が少ない) という点です。 つまり、ポリシー設定が、そのポリシーの影響を受けるオブジェクトに近いほど、オブジェクトに及ぼす影響は大きくなります。 
  
2. 有効にするプッシュ通知サービスを選択するには、次のチェック ボックスをオンにします。
    
   - **Microsoft プッシュ通知を有効** にして、Skype for Business アプリを使用して Windows Phone 用のクラウドベースの PNCH へのプッシュ通知を有効にする
    
   - **Apple** プッシュ通知を有効にした場合、Apple の iOS を実行しているデバイス (iPhone、iPad など) と Skype for Business アプリの使用に対して Apple PNCH へのプッシュ通知が有効になります。
    
3. ポリシーの編集が完了したら、[確定] をクリックして **変更を** 保存します。 加えた変更を削除する必要がある場合は、[キャンセル] を選択 **します**。 変更はポリシーに保存されません。
    

