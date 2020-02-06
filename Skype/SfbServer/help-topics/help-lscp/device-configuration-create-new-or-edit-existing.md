---
title: デバイス構成の新規作成または既存の編集
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: '[新しいデバイスの構成] または [デバイス構成の編集] ページでは、Skype for Business Phone Edition を管理するために使用される設定のコレクションを作成または変更できます。 これらの設定により、必要なセキュリティ モード、デバイス ログ レベル、音声のサービス品質 (QoS) の設定などを構成したり、指定した非アクティブ期間の経過後、電話を自動的にロックするかどうかを指定したりすることができます。'
ms.openlocfilehash: 95ce62b5d3505e10049d61ead77ce79ee7f2f51b
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41822930"
---
# <a name="device-configuration-create-new-or-edit-existing"></a>デバイス構成: 新規作成または現在の形式のままで編集
 
[**新しいデバイスの構成**] または [**デバイス構成の編集**] ページでは、Skype for business Phone Edition を管理するために使用される設定のコレクションを作成または変更できます。 これらの設定により、必要なセキュリティ モード、デバイス ログ レベル、音声のサービス品質 (QoS) の設定などを構成したり、指定した非アクティブ期間の経過後、電話を自動的にロックするかどうかを指定したりすることができます。
  
## <a name="tasks-you-can-perform"></a>実行できるタスク

[**新しいデバイス構成**] または [**デバイス構成の編集**] ページでは、次のタスクを実行できます。
  
- 新しいデバイス構成を追加する
    
- 既存のデバイス構成のプロパティを変更する
    
## <a name="ui-reference"></a>UI リファレンス

次の一覧に、このページのメニュー、コマンド、フィールド、およびプロパティを示します。
  
- **スコープ**デバイス構成のスコープ (グローバルまたはサイト) を識別します。
    
- **名前**デバイス構成の名前を追加または変更することができます。
    
- **SIP セキュリティ**Skype for Business Phone Edition デバイスのトランスポートと認証の要件を構成することができます。 次のオプションから選択できます。
    
  - **低**任意の種類の承認またはトランスポートを許可します。
    
  - **Medium**ユーザー認証には、NTLM または Kerberos が必要です。
    
  - **高**ユーザー認証には NTLM または Kerberos が必要です。また、SIP 接続には TLS が必要です。
    
- **ログレベル**UC デバイスでログを有効にすることができます。 有効な値は次のとおりです。価媒体および高。 既定値はオフです。
    
- **音声品質サービス (QoS)** Skype for Business Phone Edition デバイスから、ボイストラフィック emanating に割り当てられている DSCP 値を指定できます。 既定値は40です。 ただし、40は、通常はオーディオトラフィックに使用される値ではありません。代わりに、ほとんどの場合、音声トラフィックは DSCP コード46でマークされます。 ネットワーク全体の一貫性を維持するために、この値を46に変更することもできます。
    
- **電話のロック**指定した時間の経過後に、UC 携帯電話が自動的にロックされるかどうかを指定できます。 次の設定を構成できます。
    
  - **デバイスのロックを適用**するこのチェックボックスをオンにすると、デバイスのロックを適用できます。
    
  - **PIN の最小文字数**電話のロックを解除するために使用される暗証番号 (PIN) の最小文字数を指定できます。 PIN の長さの範囲は 4 ~ 15 桁です。 既定の長さは6桁です。
    
  - **電話のロックタイムアウト**電話がロックされるまでの最小時間を指定できます。 既定値は 10 分です。 値は、HH:MM:SS の形式で入力してください。
    
## <a name="see-also"></a>関連項目

[デバイス構成](device-configuration.md)

[Set-CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csucphoneconfiguration?view=skype-ps)
