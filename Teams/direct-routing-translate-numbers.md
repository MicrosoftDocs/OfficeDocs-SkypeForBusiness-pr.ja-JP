---
title: ダイレクト ルーティングの電話番号を翻訳する
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
description: Microsoft 電話システム ダイレクト ルーティングを構成する方法について説明します。
ms.openlocfilehash: 03abeed954a7760c7c53142380a8ca558c5b3761
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096377"
---
# <a name="translate-phone-numbers-to-an-alternate-format"></a>電話番号を別の形式に翻訳する

この記事では、発信および受信の呼び出しの番号を別の形式に変換する方法について説明します。  これは、ダイレクト ルーティングを構成するための次の手順の手順 4 です。

- 手順 1. [SBC を Microsoft Phone System に接続し、接続を検証する](direct-routing-connect-the-sbc.md) 
- 手順 2. [ユーザーに直接ルーティング、音声、ボイスメールを有効にする](direct-routing-enable-users.md)   
- 手順 3. [音声ルーティングを構成する](direct-routing-voice-routing.md)
- **手順 4.数値を別の形式に翻訳する**   (この記事)

ダイレクト ルーティングを設定するために必要なすべての手順については、「ダイレクト ルーティングを構成する」を [参照してください](direct-routing-configure.md)。

テナント管理者は、セッション ボーダー コントローラー (SPC) との相互運用性を確保するために、作成したパターンに基づいて、発信および受信通話の番号を変更したい場合があります。 この記事では、数値を別の形式に変換する数値翻訳ルール ポリシーを指定する方法について説明します。 

数値翻訳ルール ポリシーを使用して、次の数値を翻訳できます。

- 着信通話: PSTN エンドポイント (呼び出し元) から Teams クライアント (呼び出し先) への通話
- 発信通話: Teams クライアント (呼び出し元) から PSTN エンドポイント (呼び出し先) への通話

ポリシーは SBC レベルで適用されます。 複数の翻訳ルールを SBC に割り当て、PowerShell で一覧表示するときに表示される順序で適用できます。 ポリシー内のルールの順序を変更することもできます。

番号操作ルールを作成、変更、表示、および削除するには、New-CsTeamsTranslationRule、Set-CsTeamsTranslationRule、Get-CsTeamsTranslationRule、Remove-CsTeamsTranslationRule コマンドレットを使用します。 [](/powershell/module/skype/new-csteamstranslationrule) [](/powershell/module/skype/set-csteamstranslationrule) [](/powershell/module/skype/get-csteamstranslationrule) [](/powershell/module/skype/remove-csteamstranslationrule)

SBC で番号操作ルールを割り当て、構成、およびリストするには [、New-CSOnlinePSTNGateway](/powershell/module/skype/new-csonlinepstngateway) コマンドレットと [Set-CSOnlinePSTNGateway](/powershell/module/skype/set-csonlinepstngateway) コマンドレットを InboundTeamsNumberTranslationRules と共に使用します。 InboundPSTNNumberTranslationRules、OutboundTeamsNumberTranslationRules、OutboundPSTNNumberTranslationRules、InboundTeamsNumberTranslationRules、InboundPSTNNumberTranslationRules、OutboundTeamsNumberTranslationRules、および OutboundPSTSTNNumberTranslationRules パラメーター。

> [!NOTE]
> 翻訳ルールの最大数は 400、翻訳パラメーター名の最大長は 100 記号、最大翻訳パラメーター パターンの長さは 1024 記号、翻訳パラメーターの最大翻訳長は 256 記号です。


## <a name="example-sbc-configuration"></a>SBC 構成の例

このシナリオでは、コマンドレット ```New-CsOnlinePSTNGateway``` を実行して次の SBC 構成を作成します。

```PowerShell
New-CSOnlinePSTNGateway -Identity sbc1.contoso.com -SipSignalingPort 5061 –InboundTeamsNumberTranslationRules ‘AddPlus1’, ‘AddE164SeattleAreaCode’ -InboundPSTNNumberTranslationRules ‘AddPlus1’ -OutboundPSTNNumberTranslationRules ‘AddSeattleAreaCode’,  -OutboundTeamsNumberTranslationRules ‘StripPlus1’
```

SBC に割り当てられている翻訳ルールを次の表にまとめています。

|名前  |パターン |変換  |
|---------|---------|---------|
|AddPlus1     |^(\d {10} )$          |+1$1          |
|AddE164SeattleAreaCode      |^(\d {4} )$          | +1206555$1         |
|AddSeattleAreaCode    |^(\d {4} )$          | 425555$1         |
|StripPlus1    |^+1(\d {10} )$          | $1         |

次の例では、Alice と Bob の 2 人のユーザーがいます。 Alice は Teams ユーザーで、その番号は +1 206 555 0100 です。 Bob は PSTN ユーザーで、番号は +1 425 555 0100 です。

## <a name="example-1-inbound-call-to-a-ten-digit-number"></a>例 1: 10 桁の番号への着信通話

Bob は、E.164 以外の 10 桁の番号を使用して、Alice を呼び出します。 Bob は 2065550100 にダイヤルして、Alice に到達します。
SBC では、RequestURI ヘッダーと To ヘッダーに 2065550100、From ヘッダーに 4255550100 が使用されます。


|ヘッダー  |翻訳元 |翻訳されたヘッダー |適用されたパラメーターとルール  |
|---------|---------|---------|---------|
|RequestURI  |招待 sip:2065550100@sbc.contoso.com|招待 sip:+12065550100@sbc.contoso.com|InboundTeamsNumberTranslationRules 'AddPlus1'|
|宛先    |宛先： \<sip:2065550100@sbc.contoso.com>|宛先： \<sip:+12065550100@sbc.contoso.com>|InboundTeamsNumberTranlationRules 'AddPlus1'|
|差出人   |差出人： \<sip:4255550100@sbc.contoso.com>|差出人： \<sip:+14255550100@sbc.contoso.com>|InboundPSTNNumberTranslationRules 'AddPlus1'|

## <a name="example-2-inbound-call-to-a-four-digit-number"></a>例 2: 4 桁の番号への着信呼び出し

Bob は 4 桁の番号を使用して Alice を呼び出します。 Bob が 0100 をダイヤルして、Alice に到達します。
SBC では、RequestURI ヘッダーと To ヘッダーに 0100、From ヘッダーに 4255550100 が使用されます。


|ヘッダー  |翻訳元 |翻訳されたヘッダー |適用されたパラメーターとルール  |
|---------|---------|---------|---------|
|RequestURI  |招待 sip:0100@sbc.contoso.com          |招待 sip:+12065550100@sbc.contoso.com           |InboundTeamsNumberTranlationRules 'AddE164SeattleAreaCode'        |
|宛先    |宛先： \<sip:0100@sbc.contoso.com>|宛先： \<sip:+12065550100@sbc.contoso.com>|InboundTeamsNumberTranlationRules 'AddE164SeattleAreaCode'         |
|差出人   |差出人： \<sip:4255550100@sbc.contoso.com>|差出人： \<sip:+14255550100@sbc.contoso.com>|InboundPSTNNumberTranlationRules 'AddPlus1'        |

## <a name="example-3-outbound-call-using-a-ten-digit-non-e164-number"></a>例 3: 10 桁の非 E.164 番号を使用した発信通話

Alice は 10 桁の番号を使用して Bob を呼び出します。 425 555 0100 にダイヤルすると、ボブに届く。
SBC は、Teams と PSTN ユーザーの両方に E.164 以外の 10 桁の番号を使用するように構成されています。

このシナリオでは、ダイヤル プランは番号をダイレクト ルーティング インターフェイスに送信する前に番号を変換します。 Alice が Teams クライアントで 425 555 0100 に入った場合、番号は国のダイヤル プランによって +14255550100 に変換されます。 結果の数値は、ダイヤル プラン ルールと Teams 翻訳ルールの累積的な正規化です。 Teams の翻訳ルールは、ダイヤル プランによって追加された "+1" を削除します。


|ヘッダー  |翻訳元 |翻訳されたヘッダー |適用されたパラメーターとルール  |
|---------|---------|---------|---------|
|RequestURI  |招待 sip:+14255550100@sbc.contoso.com          |招待 sip:4255550100@sbc.contoso.com       |OutboundPSTNNumberTranlationRules 'StripPlus1'         |
|宛先    |宛先： \<sip:+14255550100@sbc.contoso.com>|宛先： \<sip:4255555555@sbc.contoso.com>|OutboundPSTNNumberTranlationRules 'StripPlus1'       |
|差出人   |差出人： \<sip:+12065550100@sbc.contoso.com>|差出人： \<sip:2065550100@sbc.contoso.com>|OutboundTeamsNumberTranlationRules 'StripPlus1'         |

## <a name="example-4-outbound-call-using-a-four-digit-non-e164-number"></a>例 4: 4 桁の非 E.164 番号を使用した発信通話

Alice は 4 桁の番号を使用して Bob を呼び出します。 Alice は 0100 を使用して、通話または連絡先を使用して Bob に連絡します。
SBC は、Teams ユーザーには E.164 以外の 4 桁の番号を使用し、PSTN ユーザーには 10 桁の番号を使用するように構成されています。 ダイヤル プランは、このシナリオでは適用されません。


|ヘッダー  |翻訳元 |翻訳されたヘッダー |適用されたパラメーターとルール  |
|---------|---------|---------|---------|
|RequestURI  |招待 sip:0100@sbc.contoso.com           |招待 sip:4255550100@sbc.contoso.com       |InboundTeamsNumberTranlationRules 'AddSeattleAreaCode'         |
|宛先    |宛先： \<sip:0100@sbc.contoso.com>|宛先： \<sip:4255555555@sbc.contoso.com>|InboundTeamsNumberTranlationRulesList 'AddSeattleAreaCode'       |
|差出人   |差出人： \<sip:+12065550100@sbc.contoso.com>|差出人： \<sip:2065550100@sbc.contoso.com>| InboundPSTNNumberTranlationRules 'StripPlus1' |

## <a name="see-also"></a>関連項目

[ダイレクト ルーティングを計画する](direct-routing-plan.md)

[ダイレクト ルーティングを構成する](direct-routing-configure.md)