---
title: デバイス構成の作成 (新規) または [既存の編集]
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/23/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.ClientPhoneCfgEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aac152bf-80e9-408a-9dbb-60d0843484ab
description: '[新しいデバイスの構成] または [デバイス構成の編集] ページでは、Skype for Business Phone Edition の管理に使用する設定のコレクションを作成または変更できます。 これらの設定を使用すると、必須のセキュリティ モード、デバイス ログ レベル、音声のサービス品質 (QoS) の設定、非アクティブな電話を指定の時間の経過後に自動的にロックするかどうかなどを構成できます。'
ms.openlocfilehash: ba84c6b9f820d0130940fce4dadad1cd38e7efec
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49807307"
---
# <a name="device-configuration-create-new-or-edit-existing"></a>デバイス構成: 新規作成または現在の形式のままで編集
 
[新 **しいデバイスの構成**] または [デバイス構成の編集] ページでは、Skype for Business Phone Edition の管理に使用する設定のコレクションを作成または変更できます。  これらの設定を使用すると、必須のセキュリティ モード、デバイス ログ レベル、音声のサービス品質 (QoS) の設定、非アクティブな電話を指定の時間の経過後に自動的にロックするかどうかなどを構成できます。
  
## <a name="tasks-you-can-perform"></a>実行できるタスク

[**新しいデバイス構成**] または [**デバイス構成の編集**] ページでは、次のタスクを実行できます。
  
- 新しいデバイス構成を追加する
    
- 既存のデバイス構成のプロパティを変更する
    
## <a name="ui-reference"></a>UI リファレンス

次の一覧に、このページのメニュー、コマンド、フィールド、およびプロパティを示します。
  
- **スコープ** デバイス構成のスコープ (グローバルまたはサイト) を識別します。
    
- **名前** デバイス構成の名前を追加または変更できます。
    
- **SIP セキュリティ** Skype for Business Phone Edition デバイスのトランスポートおよび認証の要件を構成できます。 次のオプションから選択できます。
    
  - **低** 任意の種類の承認またはトランスポートを許可します。
    
  - **中** ユーザー認証には NTLM または Kerberos が必要です。
    
  - **高** ユーザー認証には NTLM または Kerberos が必要であり、SIP 接続には TLS が必要です。
    
- **ログ 出力レベル** UC デバイスでログ記録を有効にできます。 有効な値は次のとおりです。低;中および高。 既定値は Off です。
    
- **音声サービスの品質 (QoS)** Skype for Business Phone Edition デバイスから提供される音声トラフィックに割り当てられる DSCP 値を指定できます。 既定値は 40 です。 音声トラフィックは、ほとんど常に DSCP コード 46 でマーキングされます。 ネットワーク全体の一貫性を維持するために、この値を 46 に変更できます。
    
- **電話ロック** UC 電話は、指定した非アクティブ期間が終了した後に自動的にロックするかどうかを指定できます。 構成できる設定を次に示します。
    
  - **デバイスロックの適用** このチェック ボックスをオンにすると、デバイスのロックを適用できます。
    
  - **PIN の最小長** 電話のロック解除に使用する暗証番号 (PIN) の最小の長さを指定できます。 PIN の長さの範囲は 4 ~ 15 桁です。 既定の長さは 6 桁です。
    
  - **電話ロックのタイム アウト** 電話がそれ自体をロックする最小時間を指定できます。 既定値は 10 分です。 値は、HH:MM:SS の形式で入力してください。
    
## <a name="see-also"></a>関連項目

[デバイス構成](device-configuration.md)

[Set-CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csucphoneconfiguration?view=skype-ps)
