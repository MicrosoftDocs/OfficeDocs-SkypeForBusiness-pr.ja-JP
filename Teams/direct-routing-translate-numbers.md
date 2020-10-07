---
title: 電話番号を直接ルーティング用に翻訳する
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Microsoft Phone システムのダイレクトルーティングを構成する方法について説明します。
ms.openlocfilehash: 7d48e9163dd5927cbeddf4a4104d2382e69e7e2b
ms.sourcegitcommit: f9daef3213a305676127cf5140af907e3b96d046
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/07/2020
ms.locfileid: "48369162"
---
# <a name="translate-phone-numbers-to-an-alternate-format"></a>電話番号を別の形式に変換する

この記事では、通話の発信と着信の番号を別の形式に変換する方法について説明します。  これは、次の手順の手順4で、直接ルーティングを構成します。

- 手順1 [SBC と Microsoft 電話システムを接続して接続を検証する](direct-routing-connect-the-sbc.md) 
- 手順2 [ユーザーが直接ルーティング、音声、ボイスメールを使用できるようにする](direct-routing-enable-users.md)   
- 手順3 [音声ルーティングを構成する](direct-routing-voice-routing.md)
- **手順4。数値を別の形式に変換する**   (この記事)

直接ルーティングを設定するために必要なすべての手順については、「 [直接ルーティングを構成する](direct-routing-configure.md)」を参照してください。

テナント管理者が、作成したパターンに基づいて、発信または着信の番号を変更して、セッションの境界コントローラー (SBCs) との相互運用性を確保したい場合があります。 この記事では、番号の翻訳ルールポリシーを指定して、数値を別の形式に変換する方法について説明します。 

数値の翻訳ルールポリシーを使用すると、次のような数値を翻訳できます。

- 着信通話: PSTN エンドポイントからチームクライアント (呼び出し先) への通話
- 発信通話: チームクライアント (発信者) から PSTN エンドポイントへの通話 (呼び出し先)

ポリシーは、SBC レベルで適用されます。 1つの SBC に複数の翻訳ルールを割り当てることができます。これは、PowerShell でそれらをリストしたときに表示される順序で適用されます。 ポリシーのルールの順序を変更することもできます。

数値操作ルールを作成、変更、表示、削除するには、 [CsTeamsTranslationRule](https://docs.microsoft.com/powershell/module/skype/new-csteamstranslationrule)、 [CsTeamsTranslationRule](https://docs.microsoft.com/powershell/module/skype/set-csteamstranslationrule)、 [CsTeamsTranslationRule](https://docs.microsoft.com/powershell/module/skype/get-csteamstranslationrule)、および [CsTeamsTranslationRule](https://docs.microsoft.com/powershell/module/skype/remove-csteamstranslationrule) コマンドレットを使用します。

SBCs で番号操作ルールを割り当て、構成、および一覧表示するには、InboundTeamsNumberTranslationRules、InboundPSTNNumberTranslationRules、OutboundTeamsNumberTranslationRules、OutboundPSTNNumberTranslationRules、InboundTeamsNumberTranslationRules、InboundPSTNNumberTranslationRules、OutboundTeamsNumberTranslationRules、OutboundPSTNNumberTranslationRules の各コマンドと共に、 [CSOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway) と [Set-CSOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway) コマンドレットを使用します。

> [!NOTE]
> 翻訳ルールの最大数は400、翻訳パラメーター名の最大長は100シンボル、翻訳パラメーターパターンの最大長は1024記号、翻訳パラメーターの翻訳の最大長は256記号です。


## <a name="example-sbc-configuration"></a>SBC 構成の例

このシナリオでは、 ```New-CsOnlinePSTNGateway``` コマンドレットを実行して次の SBC 構成を作成します。

```PowerShell
New-CSOnlinePSTNGateway -Identity sbc1.contoso.com -SipSignalingPort 5061 –InboundTeamsNumberTranslationRules ‘AddPlus1’, ‘AddE164SeattleAreaCode’ -InboundPSTNNumberTranslationRules ‘AddPlus1’ -OutboundPSTNNumberTranslationRules ‘AddSeattleAreaCode’,  -OutboundTeamsNumberTranslationRules ‘StripPlus1’
```

SBC に割り当てられている翻訳ルールは、次の表のようにまとめられています。

|名前  |実線 |変換  |
|---------|---------|---------|
|AddPlus1     |^ (\d {10} ) $          |+1$1          |
|AddE164SeattleAreaCode      |^ (\d {4} ) $          | + 1206555 $ 1         |
|AddSeattleAreaCode    |^ (\d {4} ) $          | 425555 $ 1         |
|StripPlus1    |^ + 1 (\d {10} ) $          | $1         |

次の例では、Alice と Bob の2人のユーザーがいます。 アリスは、数字が + 1 206 555 0100 の Teams ユーザーです。 ボブは、番号が + 1 425 555 0100 の PSTN ユーザーです。

## <a name="example-1-inbound-call-to-a-ten-digit-number"></a>例 1:10 桁の番号への着信通話

ボブの10桁の数字以外の番号を使用してアリスが通話を発信します。 ボブは、アリスに連絡するために2065550100をダイヤルします。
SBC は、RequestURI で2065550100を使用し、From ヘッダーではヘッダーと4255550100を使用します。


|Header  |翻訳元 |翻訳済みヘッダー |パラメーターとルールの適用  |
|---------|---------|---------|---------|
|RequestURI  |Sip:2065550100@sbc.contoso.com を招待する|Sip:+12065550100@sbc.contoso.com を招待する|InboundTeamsNumberTranslationRules 'AddPlus1'|
|宛先    |宛先： \<sip:2065550100@sbc.contoso.com>|宛先： \<sip:+12065550100@sbc.contoso.com>|InboundTeamsNumberTranlationRules 'AddPlus1'|
|差出人   |差出人： \<sip:4255550100@sbc.contoso.com>|差出人： \<sip:+14255550100@sbc.contoso.com>|InboundPSTNNumberTranslationRules 'AddPlus1'|

## <a name="example-2-inbound-call-to-a-four-digit-number"></a>例 2: 4 桁の番号への着信通話

ボブは、4桁の数字を使って Alice と通話します。 ボブは、アリスに連絡するために0100をダイヤルします。
SBC は、RequestURI で0100を使用し、From ヘッダーではヘッダーと4255550100を使用します。


|Header  |翻訳元 |翻訳済みヘッダー |パラメーターとルールの適用  |
|---------|---------|---------|---------|
|RequestURI  |Sip:0100@sbc.contoso.com を招待する          |Sip:+12065550100@sbc.contoso.com を招待する           |InboundTeamsNumberTranlationRules 'AddE164SeattleAreaCode'        |
|宛先    |宛先： \<sip:0100@sbc.contoso.com>|宛先： \<sip:+12065550100@sbc.contoso.com>|InboundTeamsNumberTranlationRules 'AddE164SeattleAreaCode'         |
|差出人   |差出人： \<sip:4255550100@sbc.contoso.com>|差出人： \<sip:+14255550100@sbc.contoso.com>|InboundPSTNNumberTranlationRules 'AddPlus1'        |

## <a name="example-3-outbound-call-using-a-ten-digit-non-e164-number"></a>例 3:10 桁の番号を使用した発信通話

アリスは、10桁の数字を使ってボブを呼び出します。 アリスは、425 555 0100 にダイヤルしてボブに連絡します。
SBC は、Teams と PSTN の両方の10桁の10桁の番号を使用するように構成されています。

このシナリオでは、ダイヤルプランによって電話番号がダイレクトルーティングインターフェイスに送信される前に変換されます。 アリスが Teams クライアントに 425 555 0100 を入力すると、その番号は国のダイヤルプランによって + 14255550100 に変換されます。 結果として得られる数値は、ダイヤルプランのルールと Teams の翻訳ルールの累積正規化です。 Teams の翻訳ルールは、ダイヤルプランによって追加された "+ 1" を削除します。


|Header  |翻訳元 |翻訳済みヘッダー |パラメーターとルールの適用  |
|---------|---------|---------|---------|
|RequestURI  |Sip:+14255550100@sbc.contoso.com を招待する          |Sip:4255550100@sbc.contoso.com を招待する       |OutboundPSTNNumberTranlationRules 'StripPlus1'         |
|宛先    |宛先： \<sip:+14255550100@sbc.contoso.com>|宛先： \<sip:4255555555@sbc.contoso.com>|OutboundPSTNNumberTranlationRules 'StripPlus1'       |
|差出人   |差出人： \<sip:+12065550100@sbc.contoso.com>|差出人： \<sip:2065550100@sbc.contoso.com>|Outboundteams の番号の自動仕分けルール ' StripPlus1 '         |

## <a name="example-4-outbound-call-using-a-four-digit-non-e164-number"></a>例 4: 4 桁以外の番号を使用した発信通話

アリスは、4桁の数字を使ってボブを呼び出します。 アリスは、0100を使って、通話から、または連絡先を使ってボブに連絡します。
SBC は、Teams ユーザーと PSTN ユーザー用に10桁の4桁の番号を使用するように構成されています。 このシナリオでは、ダイヤルプランは適用されません。


|Header  |翻訳元 |翻訳済みヘッダー |パラメーターとルールの適用  |
|---------|---------|---------|---------|
|RequestURI  |Sip:0100@sbc.contoso.com を招待する           |Sip:4255550100@sbc.contoso.com を招待する       |InboundTeamsNumberTranlationRules 'AddSeattleAreaCode'         |
|宛先    |宛先： \<sip:0100@sbc.contoso.com>|宛先： \<sip:4255555555@sbc.contoso.com>|InboundTeamsNumberTranlationRulesList 'AddSeattleAreaCode'       |
|差出人   |差出人： \<sip:+12065550100@sbc.contoso.com>|差出人： \<sip:2065550100@sbc.contoso.com>| InboundPSTNNumberTranlationRules 'StripPlus1' |

## <a name="see-also"></a>関連項目

[ダイレクト ルーティングを計画する](direct-routing-plan.md)

[ダイレクト ルーティングを構成する](direct-routing-configure.md)
