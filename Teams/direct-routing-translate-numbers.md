---
title: ダイレクト ルーティングの電話番号を翻訳する
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
description: Microsoft Phone システム ダイレクト ルーティングを構成する方法について説明します。
ms.openlocfilehash: ac6dbd46d525232235d957b7d47f1fe108e3e4a3
ms.sourcegitcommit: eb0e754d7e2877f686021d3ab75b6d8d44db3a95
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/06/2023
ms.locfileid: "69727769"
---
# <a name="translate-phone-numbers-to-an-alternate-format"></a>電話番号を別の形式に変換する

この記事では、送信呼び出しと受信呼び出しの番号を別の形式に変換する方法について説明します。 これは、ダイレクト ルーティングを構成するための次の手順の手順 4 です。

- 手順 1. [SBC を Microsoft Phone System に接続し、接続を検証する](direct-routing-connect-the-sbc.md) 
- 手順 2. [ダイレクト ルーティング、音声、ボイスメールのユーザーを有効にする](direct-routing-enable-users.md)   
- 手順 3. [音声ルーティングを構成する](direct-routing-voice-routing.md)
- **手順 4.数値を別の形式に変換する**   (この記事)

ダイレクト ルーティングの設定に必要なすべての手順については、「ダイレクト ルーティングの [構成](direct-routing-configure.md)」を参照してください。

テナント管理者が、セッション ボーダー コントローラー (SBC) との相互運用性を確保するために作成したパターンに基づいて、送信呼び出しまたは受信呼び出しの番号を変更したい場合があります。 この記事では、数値変換ルール ポリシーを指定して、数値を別の形式に変換する方法について説明します。 

数値変換ルール ポリシーを使用して、次の番号を翻訳できます。

- 受信呼び出し: PSTN エンドポイント (呼び出し元) から Teams クライアント (呼び出し先) への通話
- 送信呼び出し: Teams クライアント (呼び出し元) から PSTN エンドポイント (呼び出し先) への呼び出し

ポリシーは SBC レベルで適用されます。 複数の翻訳ルールを 1 つの SBC に割り当てることができます。これは、PowerShell で一覧表示するときに表示される順序で適用されます。 ポリシー内のルールの順序を変更することもできます。

数値操作ルールを作成、変更、表示、削除するには、 [New-CsTeamsTranslationRule](/powershell/module/skype/new-csteamstranslationrule)、 [Set-CsTeamsTranslationRule](/powershell/module/skype/set-csteamstranslationrule)、 [Get-CsTeamsTranslationRule](/powershell/module/skype/get-csteamstranslationrule)、 [Remove-CsTeamsTranslationRule コマンドレットを](/powershell/module/skype/remove-csteamstranslationrule) 使用します。

SBC で番号操作規則を割り当て、構成し、リストするには、 [New-CSOnlinePSTNGateway](/powershell/module/skype/new-csonlinepstngateway) コマンドレットと [Set-CSOnlinePSTNGateway](/powershell/module/skype/set-csonlinepstngateway) コマンドレットを InboundTeamsNumberTranslationRules、InboundPSTNNumberTranslationRules、OutboundTeamsNumberTranslationRules、および OutboundPSTNNumberTranslationRules パラメーターと共に使用します。

> [!NOTE]
> 変換ルールの最大数は 400、最大翻訳パラメーター名の長さは 100 シンボル、最大翻訳パラメーター パターン長は 1024 シンボル、最大翻訳パラメーター変換長は 256 シンボルです。


## <a name="example-sbc-configuration"></a>SBC 構成の例

このシナリオでは、New-CsOnlinePSTNGateway コマンドレットを実行して、次の SBC 構成を作成します。

```PowerShell
New-CSOnlinePSTNGateway -Identity sbc1.contoso.com -SipSignalingPort 5061 –InboundTeamsNumberTranslationRules ‘AddPlus1’, ‘AddE164SeattleAreaCode’ -InboundPSTNNumberTranslationRules ‘AddPlus1’ -OutboundPSTNNumberTranslationRules ‘AddSeattleAreaCode’,‘StripPlus1’  -OutboundTeamsNumberTranslationRules ‘StripPlus1’
```

SBC に割り当てられた変換ルールを次の表にまとめます。

|名前  |パターン |変換  |
|---------|---------|---------|
|AddPlus1     |^(\d{10})$          |+1$1          |
|AddE164SeattleAreaCode      |^(\d{4})$          | +1206555$1         |
|AddSeattleAreaCode    |^(\d{4})$          | 425555$1         |
|StripPlus1    |^\+1(\d{10})$          | $1         |

次の例では、Alice と Bob の 2 人のユーザーがあります。 Alice は、+1 206 555 0100 の Teams ユーザーです。 Bob は PSTN ユーザーで、番号は +1 425 555 0100 です。

## <a name="example-1-inbound-call-to-a-ten-digit-number"></a>例 1: 10 桁の番号への着信呼び出し

Bob は、E.164 以外の 10 桁の番号を使用して Alice を呼び出します。 Bob は2065550100にダイヤルして Alice に到達します。
SBC では、RequestURI ヘッダーと To ヘッダーで2065550100を使用し、From ヘッダーに4255550100します。


|ヘッダー  |翻訳元 |翻訳されたヘッダー |パラメーターと規則が適用されました  |
|---------|---------|---------|---------|
|RequestURI  |INVITE sip:2065550100@sbc.contoso.com|INVITE sip:+12065550100@sbc.contoso.com|InboundTeamsNumberTranslationRules 'AddPlus1'|
|宛先    |宛先： \<sip:2065550100@sbc.contoso.com>|宛先： \<sip:+12065550100@sbc.contoso.com>|InboundTeamsNumberTranlationRules 'AddPlus1'|
|差出人   |差出人： \<sip:4255550100@sbc.contoso.com>|差出人： \<sip:+14255550100@sbc.contoso.com>|InboundPSTNNumberTranslationRules 'AddPlus1'|

## <a name="example-2-inbound-call-to-a-four-digit-number"></a>例 2: 4 桁の番号への着信呼び出し

Bob は、4 桁の番号を使用して Alice を呼び出します。 Bob は 0100 にダイヤルして Alice に到達します。
SBC では、RequestURI ヘッダーと To ヘッダーで 0100 が使用され、From ヘッダーに4255550100されます。


|ヘッダー  |翻訳元 |翻訳されたヘッダー |パラメーターと規則が適用されました  |
|---------|---------|---------|---------|
|RequestURI  |INVITE sip:0100@sbc.contoso.com          |INVITE sip:+12065550100@sbc.contoso.com           |InboundTeamsNumberTranlationRules 'AddE164SeattleAreaCode'        |
|宛先    |宛先： \<sip:0100@sbc.contoso.com>|宛先： \<sip:+12065550100@sbc.contoso.com>|InboundTeamsNumberTranlationRules 'AddE164SeattleAreaCode'         |
|差出人   |差出人： \<sip:4255550100@sbc.contoso.com>|差出人： \<sip:+14255550100@sbc.contoso.com>|InboundPSTNNumberTranlationRules 'AddPlus1'        |

## <a name="example-3-outbound-call-using-a-ten-digit-non-e164-number"></a>例 3: E.164 以外の 10 桁の番号を使用したアウトバウンド呼び出し

Alice は、10 桁の番号を使用して Bob を呼び出します。 Alice は 425 555 0100 にダイヤルして Bob に到達します。
SBC は、Teams ユーザーと PSTN ユーザーの両方に E.164 以外の 10 桁の番号を使用するように構成されています。

このシナリオでは、ダイヤル プランは番号をダイレクト ルーティング インターフェイスに送信する前に変換します。 Alice が Teams クライアントで 425 555 0100 に入ると、番号は国のダイヤル プランによって +14255550100 に変換されます。 結果の数値は、ダイヤル プランルールと Teams 翻訳ルールの累積正規化です。 Teams 翻訳ルールでは、ダイヤル プランによって追加された "+1" が削除されます。


|ヘッダー  |翻訳元 |翻訳されたヘッダー |パラメーターと規則が適用されました  |
|---------|---------|---------|---------|
|RequestURI  |INVITE sip:+14255550100@sbc.contoso.com          |INVITE sip:4255550100@sbc.contoso.com       |OutboundPSTNNumberTranlationRules 'StripPlus1'         |
|宛先    |宛先： \<sip:+14255550100@sbc.contoso.com>|宛先： \<sip:4255555555@sbc.contoso.com>|OutboundPSTNNumberTranlationRules 'StripPlus1'       |
|差出人   |差出人： \<sip:+12065550100@sbc.contoso.com>|差出人： \<sip:2065550100@sbc.contoso.com>|OutboundTeamsNumberTranlationRules 'StripPlus1'         |

## <a name="example-4-outbound-call-using-a-four-digit-non-e164-number"></a>例 4: E.164 以外の 4 桁の番号を使用したアウトバウンド呼び出し

Alice は、4 桁の番号を使用して Bob を呼び出します。 Alice は 0100 を使用して、通話から、または連絡先を使用して Bob に到達します。
SBC は、Teams ユーザーに E.164 以外の 4 桁の数字を使用し、PSTN ユーザーに 10 桁の数字を使用するように構成されています。 ダイヤル プランは、このシナリオでは適用されません。


|ヘッダー  |翻訳元 |翻訳されたヘッダー |パラメーターと規則が適用されました  |
|---------|---------|---------|---------|
|RequestURI  |INVITE sip:0100@sbc.contoso.com           |INVITE sip:4255550100@sbc.contoso.com       |InboundTeamsNumberTranlationRules 'AddSeattleAreaCode'         |
|宛先    |宛先： \<sip:0100@sbc.contoso.com>|宛先： \<sip:4255555555@sbc.contoso.com>|InboundTeamsNumberTranlationRulesList 'AddSeattleAreaCode'       |
|差出人   |差出人： \<sip:+12065550100@sbc.contoso.com>|差出人： \<sip:2065550100@sbc.contoso.com>| InboundPSTNNumberTranlationRules 'StripPlus1' |

## <a name="see-also"></a>関連項目

[ダイレクト ルーティングを計画する](direct-routing-plan.md)

[ダイレクト ルーティングを構成する](direct-routing-configure.md)
