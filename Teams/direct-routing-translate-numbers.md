---
title: ダイレクト ルーティングの電話番号を変換する
ms.reviewer: filippse
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: システム ダイレクト ルーティングMicrosoft 電話構成する方法について説明します。
ms.openlocfilehash: 2a9f5c92da348a47f5a6d24389254436f2fd510c
ms.sourcegitcommit: 2e8daa3511cd198b3e0d43b153dd37a59cb21692
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/11/2022
ms.locfileid: "62763292"
---
# <a name="translate-phone-numbers-to-an-alternate-format"></a>電話番号を別の形式に変換する

この記事では、発信呼び出しと着信呼び出しの番号を別の形式に変換する方法について説明します。 これは、ダイレクト ルーティングを構成するための次の手順の手順 4 です。

- 手順 1. [Microsoft 電話 System を使用して SBC をConnectし、接続を検証する](direct-routing-connect-the-sbc.md) 
- 手順 2. [ダイレクト ルーティング、音声、ボイスメールのユーザーを有効にする](direct-routing-enable-users.md)   
- 手順 3. [音声ルーティングを構成する](direct-routing-voice-routing.md)
- **手順 4.数値を別の形式に変換する**   (この記事)

ダイレクト ルーティングの設定に必要なすべての手順については、「ダイレクト ルーティングの [構成」を参照してください](direct-routing-configure.md)。

テナント管理者は、セッション ボーダー コントローラー (SBC) との相互運用性を確保するために作成したパターンに基づいて、発信呼び出しまたは着信呼び出しの数を変更したい場合があります。 この記事では、数値を別の形式に変換する数値変換ルール ポリシーを指定する方法について説明します。 

数値変換ルール ポリシーを使用して、次の番号を変換できます。

- 着信呼び出し: PSTN エンドポイント (呼び出し元) からTeams クライアント (呼び出し先) への呼び出し
- 発信通話: Teams クライアント (呼び出し元) から PSTN エンドポイント (呼び出し先) への呼び出し

ポリシーは SBC レベルで適用されます。 複数の翻訳ルールを SBC に割り当てることができます。これは、PowerShell で一覧表示するときに表示される順序で適用されます。 ポリシー内のルールの順序を変更することもできます。

数値操作規則を作成、変更、表示、削除するには、 [New-CsTeamsTranslationRule](/powershell/module/skype/new-csteamstranslationrule)、 [Set-CsTeamsTranslationRule](/powershell/module/skype/set-csteamstranslationrule)、 [Get-CsTeamsTranslationRule](/powershell/module/skype/get-csteamstranslationrule)、 [Remove-CsTeamsTranslationRule](/powershell/module/skype/remove-csteamstranslationrule) コマンドレットを使用します。

SBCs で番号操作規則を割り当て、構成、および一覧表示するには、 [New-CSOnlinePSTNGateway](/powershell/module/skype/new-csonlinepstngateway) コマンドレットと [Set-CSOnlinePSTNGateway](/powershell/module/skype/set-csonlinepstngateway) コマンドレットを InboundTeamsNumberTranslationRules、InboundPSTNNumberTranslationRules、OutboundTeamsNumberTranslationRules、OutboundPSTNNumberTranslationRules パラメーターと共に使用します。

> [!NOTE]
> 変換規則の最大数は 400、変換パラメーター名の最大長は 100 シンボル、最大変換パラメーター パターン長は 1024 シンボル、変換パラメーター変換の最大長は 256 シンボルです。


## <a name="example-sbc-configuration"></a>SBC 構成の例

このシナリオでは、New-CsOnlinePSTNGateway コマンドレットを実行して、次の SBC 構成を作成します。

```PowerShell
New-CSOnlinePSTNGateway -Identity sbc1.contoso.com -SipSignalingPort 5061 –InboundTeamsNumberTranslationRules ‘AddPlus1’, ‘AddE164SeattleAreaCode’ -InboundPSTNNumberTranslationRules ‘AddPlus1’ -OutboundPSTNNumberTranslationRules ‘AddSeattleAreaCode’,‘StripPlus1’  -OutboundTeamsNumberTranslationRules ‘StripPlus1’
```

SBC に割り当てられた変換規則を次の表にまとめます。

|名前  |パターン |変換  |
|---------|---------|---------|
|AddPlus1     |^(\d{10})$          |+1$1          |
|AddE164SeattleAreaCode      |^(\d{4})$          | +1206555$1         |
|AddSeattleAreaCode    |^(\d{4})$          | 425555$1         |
|StripPlus1    |^+1(\d{10})$          | $1         |

次の例では、Alice と Bob の 2 人のユーザーがいます。 Alice は、数値が +1 206 555 0100 のTeams ユーザーです。 Bob は PSTN ユーザーで、番号は +1 425 555 0100 です。

## <a name="example-1-inbound-call-to-a-ten-digit-number"></a>例 1: 10 桁の番号への着信呼び出し

Bob は、E.164 以外の 10 桁の番号を使用して Alice を呼び出します。 Bob は2065550100をダイヤルして Alice に到達します。
SBC では、RequestURI ヘッダーと To ヘッダーの2065550100を使用し、From ヘッダーの4255550100を使用します。


|ヘッダー  |翻訳元 |翻訳済みヘッダー |適用されたパラメーターとルール  |
|---------|---------|---------|---------|
|RequestURI  |sip:2065550100@sbc.contoso.com を招待する|sip:+12065550100@sbc.contoso.com を招待する|InboundTeamsNumberTranslationRules 'AddPlus1'|
|宛先    |宛先： \<sip:2065550100@sbc.contoso.com>|宛先： \<sip:+12065550100@sbc.contoso.com>|InboundTeamsNumberTranlationRules 'AddPlus1'|
|差出人   |差出人： \<sip:4255550100@sbc.contoso.com>|差出人： \<sip:+14255550100@sbc.contoso.com>|InboundPSTNNumberTranslationRules 'AddPlus1'|

## <a name="example-2-inbound-call-to-a-four-digit-number"></a>例 2: 4 桁の番号への受信呼び出し

Bob は 4 桁の番号を使用して Alice を呼び出します。 Bob は、Alice に到達するために 0100 をダイヤルします。
SBC は RequestURI ヘッダーと To ヘッダーで 0100 を使用し、From ヘッダーの4255550100を使用します。


|ヘッダー  |翻訳元 |翻訳済みヘッダー |適用されたパラメーターとルール  |
|---------|---------|---------|---------|
|RequestURI  |sip:0100@sbc.contoso.com を招待する          |sip:+12065550100@sbc.contoso.com を招待する           |InboundTeamsNumberTranlationRules 'AddE164SeattleAreaCode'        |
|宛先    |宛先： \<sip:0100@sbc.contoso.com>|宛先： \<sip:+12065550100@sbc.contoso.com>|InboundTeamsNumberTranlationRules 'AddE164SeattleAreaCode'         |
|差出人   |差出人： \<sip:4255550100@sbc.contoso.com>|差出人： \<sip:+14255550100@sbc.contoso.com>|InboundPSTNNumberTranlationRules 'AddPlus1'        |

## <a name="example-3-outbound-call-using-a-ten-digit-non-e164-number"></a>例 3: 10 桁の E.164 以外の番号を使用した発信呼び出し

Alice は 10 桁の番号を使用して Bob を呼び出します。 Alice は Bob に到達するために 425 555 0100 にダイヤルします。
SBC は、Teams ユーザーと PSTN ユーザーの両方に E.164 以外の 10 桁の数字を使用するように構成されています。

このシナリオでは、ダイヤル プランは番号を直接ルーティング インターフェイスに送信する前に変換します。 Alice がTeams クライアントで 425 555 0100 に入ると、番号は国のダイヤル プランによって +14255550100に変換されます。 結果の数値は、ダイヤル プラン ルールとTeams変換ルールの累積正規化です。 Teams変換規則は、ダイヤル プランによって追加された "+1" を削除します。


|ヘッダー  |翻訳元 |翻訳済みヘッダー |適用されたパラメーターとルール  |
|---------|---------|---------|---------|
|RequestURI  |sip:+14255550100@sbc.contoso.com を招待する          |sip:4255550100@sbc.contoso.com を招待する       |OutboundPSTNNumberTranlationRules 'StripPlus1'         |
|宛先    |宛先： \<sip:+14255550100@sbc.contoso.com>|宛先： \<sip:4255555555@sbc.contoso.com>|OutboundPSTNNumberTranlationRules 'StripPlus1'       |
|差出人   |差出人： \<sip:+12065550100@sbc.contoso.com>|差出人： \<sip:2065550100@sbc.contoso.com>|OutboundTeamsNumberTranlationRules 'StripPlus1'         |

## <a name="example-4-outbound-call-using-a-four-digit-non-e164-number"></a>例 4: 4 桁の E.164 以外の番号を使用した発信呼び出し

Alice は、4 桁の番号を使用して Bob を呼び出します。 Alice は 0100 を使用して、通話または連絡先から Bob に連絡します。
SBC は、Teams ユーザーに E.164 以外の 4 桁の数字を使用し、PSTN ユーザーに 10 桁の番号を使用するように構成されています。 このシナリオでは、ダイヤル プランは適用されません。


|ヘッダー  |翻訳元 |翻訳済みヘッダー |適用されたパラメーターとルール  |
|---------|---------|---------|---------|
|RequestURI  |sip:0100@sbc.contoso.com を招待する           |sip:4255550100@sbc.contoso.com を招待する       |InboundTeamsNumberTranlationRules 'AddSeattleAreaCode'         |
|宛先    |宛先： \<sip:0100@sbc.contoso.com>|宛先： \<sip:4255555555@sbc.contoso.com>|InboundTeamsNumberTranlationRulesList 'AddSeattleAreaCode'       |
|差出人   |差出人： \<sip:+12065550100@sbc.contoso.com>|差出人： \<sip:2065550100@sbc.contoso.com>| InboundPSTNNumberTranlationRules 'StripPlus1' |

## <a name="see-also"></a>関連項目

[ダイレクト ルーティングを計画する](direct-routing-plan.md)

[ダイレクト ルーティングを構成する](direct-routing-configure.md)
