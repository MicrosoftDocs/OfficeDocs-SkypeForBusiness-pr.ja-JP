---
title: 直接ルーティングの電話番号を翻訳する
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
description: システム ダイレクト ルーティングを構成Microsoft 電話方法について説明します。
ms.openlocfilehash: 03abeed954a7760c7c53142380a8ca558c5b3761
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096377"
---
# <a name="translate-phone-numbers-to-an-alternate-format"></a>電話番号を別の形式に翻訳する

この記事では、発信呼び出しと受信呼び出しの番号を別の形式に変換する方法について説明します。  これは、ダイレクト ルーティングを構成するための次の手順の手順 4 です。

- 手順 1. [Connect システムを使用して SBC Microsoft 電話し、接続を検証する](direct-routing-connect-the-sbc.md) 
- 手順 2. [ダイレクト ルーティング、音声、ボイスメールのユーザーを有効にする](direct-routing-enable-users.md)   
- 手順 3. [音声ルーティングを構成する](direct-routing-voice-routing.md)
- **手順 4.数値を別の形式に翻訳する**   (この記事)

ダイレクト ルーティングを設定するために必要なすべての手順については、「ダイレクト ルーティングの構成 [」を参照してください](direct-routing-configure.md)。

テナント管理者は、セッション ボーダー コントローラー (SBC) との相互運用性を確保するために、作成したパターンに基づいて発信および受信呼び出しの番号を変更したい場合があります。 この記事では、数値を別の形式に変換する数値変換ルール ポリシーを指定する方法について説明します。 

数値変換ルール ポリシーを使用して、次の数値を翻訳できます。

- 着信呼び出し: PSTN エンドポイント (呼び出し元) からクライアント (呼び出し先) Teamsへの呼び出し
- 発信呼び出し: TEAMS (呼び出し元) から PSTN エンドポイント (呼び出し先) への呼び出し

ポリシーは SBC レベルで適用されます。 複数の翻訳ルールを SBC に割り当て、PowerShell で一覧表示するときに表示される順序で適用できます。 ポリシー内のルールの順序を変更することもできます。

番号操作ルールを作成、変更、表示、削除するには [、New-CsTeamsTranslationRule](/powershell/module/skype/new-csteamstranslationrule)コマンドレット [、Set-CsTeamsTranslationRule](/powershell/module/skype/set-csteamstranslationrule)コマンドレット [、Get-CsTeamsTranslationRule](/powershell/module/skype/get-csteamstranslationrule)コマンドレット [、Remove-CsTeamsTranslationRule](/powershell/module/skype/remove-csteamstranslationrule) コマンドレットを使用します。

SBC で番号操作ルールを割り当て、構成、および一覧表示するには [、New-CSOnlinePSTNGateway](/powershell/module/skype/new-csonlinepstngateway) コマンドレットと [Set-CSOnlinePSTNGateway](/powershell/module/skype/set-csonlinepstngateway) コマンドレットを InboundTeamsNumberTranslationRules と共に使用します。 InboundPSTNNumberTranslationRules、OutboundTeamsNumberTranslationRules、OutboundPSTNNumberTranslationRules、InboundTeamsNumberTranslationRules、InboundPSTNNumberTranslationRules、OutboundTeamsNumberTranslationRules、および OutboundPSTNNumberTranslationRules パラメーター。

> [!NOTE]
> 翻訳ルールの最大数は 400、翻訳パラメーター名の最大長は 100 記号、最大翻訳パラメーター パターン長は 1024 記号、翻訳パラメーターの最大翻訳長は 256 記号です。


## <a name="example-sbc-configuration"></a>SBC 構成の例

このシナリオでは、コマンドレット ```New-CsOnlinePSTNGateway``` を実行して次の SBC 構成を作成します。

```PowerShell
New-CSOnlinePSTNGateway -Identity sbc1.contoso.com -SipSignalingPort 5061 –InboundTeamsNumberTranslationRules ‘AddPlus1’, ‘AddE164SeattleAreaCode’ -InboundPSTNNumberTranslationRules ‘AddPlus1’ -OutboundPSTNNumberTranslationRules ‘AddSeattleAreaCode’,  -OutboundTeamsNumberTranslationRules ‘StripPlus1’
```

SBC に割り当てられた翻訳規則を次の表にまとめると、次の表に示します。

|名前  |パターン |変換  |
|---------|---------|---------|
|AddPlus1     |^(\d {10} )$          |+1$1          |
|AddE164SeattleAreaCode      |^(\d {4} )$          | +1206555$1         |
|AddSeattleAreaCode    |^(\d {4} )$          | 425555$1         |
|StripPlus1    |^+1(\d {10} )$          | $1         |

次の例では、Alice と Bob の 2 人のユーザーがいます。 Alice は、Teams +1 206 555 0100 のユーザーです。 Bob は PSTN ユーザーで、番号は +1 425 555 0100 です。

## <a name="example-1-inbound-call-to-a-ten-digit-number"></a>例 1: 10 桁の番号への着信呼び出し

Bob は、E.164 以外の 10 桁の番号を使用して Alice を呼び出します。 Bob は 2065550100 にダイヤルして Alice に到達します。
SBC は、RequestURI ヘッダーと To ヘッダーに 2065550100 を使用し、From ヘッダーに 4255550100 を使用します。


|ヘッダー  |翻訳元 |翻訳済みヘッダー |パラメーターとルールの適用  |
|---------|---------|---------|---------|
|RequestURI  |招待 sip:2065550100@sbc.contoso.com|招待 sip:+12065550100@sbc.contoso.com|InboundTeamsNumberTranslationRules 'AddPlus1'|
|宛先    |宛先： \<sip:2065550100@sbc.contoso.com>|宛先： \<sip:+12065550100@sbc.contoso.com>|InboundTeamsNumberTranlationRules 'AddPlus1'|
|差出人   |差出人： \<sip:4255550100@sbc.contoso.com>|差出人： \<sip:+14255550100@sbc.contoso.com>|InboundPSTNNumberTranslationRules 'AddPlus1'|

## <a name="example-2-inbound-call-to-a-four-digit-number"></a>例 2: 4 桁の番号への着信呼び出し

Bob は、4 桁の番号を使用して Alice を呼び出します。 Bob は 0100 をダイヤルして Alice に到達します。
SBC では、RequestURI ヘッダーと To ヘッダーに 0100、From ヘッダーに 4255550100 を使用します。


|ヘッダー  |翻訳元 |翻訳済みヘッダー |パラメーターとルールの適用  |
|---------|---------|---------|---------|
|RequestURI  |招待 sip:0100@sbc.contoso.com          |招待 sip:+12065550100@sbc.contoso.com           |InboundTeamsNumberTranlationRules 'AddE164SeattleAreaCode'        |
|宛先    |宛先： \<sip:0100@sbc.contoso.com>|宛先： \<sip:+12065550100@sbc.contoso.com>|InboundTeamsNumberTranlationRules 'AddE164SeattleAreaCode'         |
|差出人   |差出人： \<sip:4255550100@sbc.contoso.com>|差出人： \<sip:+14255550100@sbc.contoso.com>|InboundPSTNNumberTranlationRules 'AddPlus1'        |

## <a name="example-3-outbound-call-using-a-ten-digit-non-e164-number"></a>例 3: 10 桁の非 E.164 番号を使用した発信呼び出し

Alice は、10 桁の番号を使用して Bob を呼び出します。 Alice は 425 555 0100 にダイヤルして Bob に到達します。
SBC は、ユーザーと PSTN ユーザーの両方に E.164 以外の 10 桁の番号Teams構成されています。

このシナリオでは、ダイヤル プランは、ダイレクト ルーティング インターフェイスに送信する前に番号を変換します。 Alice が Teams クライアントに 425 555 0100 を入力すると、国のダイヤル プランによって番号が +14255550100 に変換されます。 結果として得られる数値は、ダイヤル プラン ルールと翻訳ルールのTeams正規化です。 このTeams、ダイヤル プランによって追加された "+1" を削除します。


|ヘッダー  |翻訳元 |翻訳済みヘッダー |パラメーターとルールの適用  |
|---------|---------|---------|---------|
|RequestURI  |招待 sip:+14255550100@sbc.contoso.com          |招待 sip:4255550100@sbc.contoso.com       |OutboundPSTNNumberTranlationRules 'StripPlus1'         |
|宛先    |宛先： \<sip:+14255550100@sbc.contoso.com>|宛先： \<sip:4255555555@sbc.contoso.com>|OutboundPSTNNumberTranlationRules 'StripPlus1'       |
|差出人   |差出人： \<sip:+12065550100@sbc.contoso.com>|差出人： \<sip:2065550100@sbc.contoso.com>|OutboundTeamsNumberTranlationRules 'StripPlus1'         |

## <a name="example-4-outbound-call-using-a-four-digit-non-e164-number"></a>例 4: 4 桁の非 E.164 番号を使用した発信呼び出し

Alice は 4 桁の番号を使用して Bob を呼び出します。 Alice は 0100 を使用して、通話から、または連絡先を使用して Bob に到達します。
SBC は、ユーザーに E.164 以外の 4 桁の番号をTeams PSTN ユーザーには 10 桁の番号を使用するように構成されています。 このシナリオでは、ダイヤル プランは適用されません。


|ヘッダー  |翻訳元 |翻訳済みヘッダー |パラメーターとルールの適用  |
|---------|---------|---------|---------|
|RequestURI  |招待 sip:0100@sbc.contoso.com           |招待 sip:4255550100@sbc.contoso.com       |InboundTeamsNumberTranlationRules 'AddSeattleAreaCode'         |
|宛先    |宛先： \<sip:0100@sbc.contoso.com>|宛先： \<sip:4255555555@sbc.contoso.com>|InboundTeamsNumberTranlationRulesList 'AddSeattleAreaCode'       |
|差出人   |差出人： \<sip:+12065550100@sbc.contoso.com>|差出人： \<sip:2065550100@sbc.contoso.com>| InboundPSTNNumberTranlationRules 'StripPlus1' |

## <a name="see-also"></a>関連項目

[ダイレクト ルーティングを計画する](direct-routing-plan.md)

[ダイレクト ルーティングを構成する](direct-routing-configure.md)