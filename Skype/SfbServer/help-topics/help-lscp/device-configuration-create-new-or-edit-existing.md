---
title: デバイス構成 新規の作成または既存の編集
ms.reviewer: ''
ms.author: v-mahoffman
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
ms.localizationpriority: medium
ms.assetid: aac152bf-80e9-408a-9dbb-60d0843484ab
description: '[新しいデバイス構成] または [デバイス構成の編集] ページで、エディションの管理に使用される設定のコレクションをSkype for Business 電話できます。 これらの設定を使用すると、必須のセキュリティ モード、デバイス ログ レベル、音声のサービス品質 (QoS) の設定、非アクティブな電話を指定の時間の経過後に自動的にロックするかどうかなどを構成できます。'
ms.openlocfilehash: 8211e31ddb4f28d72c50b90d982fbb1e16ab0f63
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/04/2021
ms.locfileid: "60758449"
---
# <a name="device-configuration-create-new-or-edit-existing"></a>デバイス構成: 新規作成または現在の形式のままで編集
 
[新 **しいデバイス構成]** または **[デバイス** 構成の編集] ページで、エディションの管理に使用する設定のコレクションをSkype for Business 電話できます。 これらの設定を使用すると、必須のセキュリティ モード、デバイス ログ レベル、音声のサービス品質 (QoS) の設定、非アクティブな電話を指定の時間の経過後に自動的にロックするかどうかなどを構成できます。
  
## <a name="tasks-you-can-perform"></a>実行できるタスク

[**新しいデバイス構成**] または [**デバイス構成の編集**] ページでは、次のタスクを実行できます。
  
- 新しいデバイス構成を追加する
    
- 既存のデバイス構成のプロパティを変更する
    
## <a name="ui-reference"></a>UI リファレンス

次の一覧に、このページのメニュー、コマンド、フィールド、およびプロパティを示します。
  
- **スコープ** デバイス構成のスコープ (グローバルまたはサイト) を識別します。
    
- **名前** デバイス構成の名前を追加または変更できます。
    
- **SIP セキュリティ** このエディションのデバイスのトランスポート要件と認証要件Skype for Business 電話構成できます。 次のオプションから選択できます:
    
  - **低** 任意の種類の承認またはトランスポートを許可します。
    
  - **中程度** ユーザー認証には NTLM または Kerberos が必要です。
    
  - **High** ユーザー認証には NTLM または Kerberos が必要で、SIP 接続には TLS が必要です。
    
- **ログ レベル** UC デバイスでログ記録を有効にできます。 有効な値は次のとおりです。低。Medium。と High。 既定値は Off です。
    
- **音声サービス品質 (QoS)** 音声トラフィックに割り当てられた DSCP 値は、Skype for Business 電話 Edition デバイスから指定できます。 既定値は 40 です。 音声トラフィックは、ほとんど常に DSCP コード 46 でマーキングされます。 ネットワーク全体で一貫性を保つには、この値を 46 に変更する必要があります。
    
- **電話ロック** 指定された非アクティブ期間の後に UC 電話が自動的にロックするかどうかを指定できます。 構成できる設定は次のとおりです。
    
  - **デバイスのロックを強制する** このチェック ボックスをオンにすると、デバイスのロックを適用できます。
    
  - **PIN の最小長** 電話のロック解除に使用する個人識別番号 (PIN) の最小長を指定できます。 PIN の長さの範囲は 4 ~ 15 桁です。 既定の長さは 6 桁です。
    
  - **電話ロックのタイム アウト** 電話がそれ自体をロックする前の最小時間を指定できます。 既定値は 10 分です。 値は、HH:MM:SS の形式で入力してください。
    
## <a name="see-also"></a>関連項目

[デバイス構成](device-configuration.md)

[Set-CsUCPhoneConfiguration](/powershell/module/skype/set-csucphoneconfiguration?view=skype-ps)