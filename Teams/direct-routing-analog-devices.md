---
title: ダイレクト ルーティング - アナログ デバイスの接続
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.reviewer: NMuravlyannikov
ms.topic: conceptual
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: この記事では、システム ダイレクト ルーティングでアナログ デバイスを使用するMicrosoft 電話説明します。
ms.openlocfilehash: dc49c22dceffda6905d1f57652fd14d584d02cf6
ms.sourcegitcommit: 9d446485aa842abbdcd34d946b247166c2bf1610
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/25/2021
ms.locfileid: "52642097"
---
# <a name="how-to-use-analog-devices-with-phone-system-direct-routing"></a>ダイレクト ルーティングでアナログ デバイスを使用電話システム方法

この記事では、ダイレクト ルーティングでアナログ デバイスを使用する電話システム説明します。 アナログ デバイスをダイレクト ルーティングに接続するには、アナログ テレフォニー アダプター (ATA) を使用する必要があります。このアダプターは認定セッション ボーダー コントローラー (SBC) ベンダーによってサポートされている必要があります。 

ユーザーがアナログ デバイスから呼び出しを行った場合、信号とメディアはアナログ テレフォニー アダプター (ATA) を介して SBC に送信されます。  SBC は、内部ルーティング テーブルに基づいて、Microsoft Teams エンドポイントまたは公衆交換電話網 (PSTN) に通話を送信します。  デバイスが呼び出しを行う場合、そのデバイスが使用するルートは、デバイス用に作成されたルーティング ポリシーによって異なります。

次の図では、 直接ルーティングは、+1425 4XX XX XX と +1425 5XX XX XX の間の番号との間の Teams 呼び出しが赤いルート (点線) を受け取る必要があります。また、+1425 4XX XX XX と数字範囲 +1425 5XX XX XX を除く他の番号との間の PSTN 呼び出しは、青色のルート (実線) を取得する必要があります。 

> [!div class="mx-imgBorder"]
> ![ダイレクト ルーティングの構成を示す図](media/direct-routing-analog-device.png)

## <a name="example--how-to-configure-the-use-of-analog-devices-with-direct-routing"></a>例: ダイレクト ルーティングを使用してアナログ デバイスの使用を構成する方法

ダイレクト ルーティングを使用してアナログ デバイスの使用を構成するには、アナログ テレフォニー アダプターを SBC に接続し、ダイレクト ルーティングを使用するために SBC を構成する必要があります。 

この例では、次の手順を実行します。

1. Connect SBC からダイレクト ルーティングに接続します。
2. PSTN 使用法を作成します。
3. 音声ルートを作成し、PSTN 使用法に関連付ける。
4. PSTN 使用法に音声ルートを割り当てる。
5. オンライン ユーザーを有効にする。
6. 音声ルート ポリシーをユーザーに割り当てる。
7. アナログ デバイスの音声ルートを作成します。

ATA を SBC に接続して SBC を構成する方法については、SBC 製造元の構成ガイドを参照してください。

- [AudioCodes 構成ドキュメント](https://www.audiocodes.com/media/14278/connecting-audiocodes-sbc-with-analog-device-to-microsoft-teams-direct-routing-enterprise-model-configuration-note.pdf)

- [リボンの構成に関するドキュメント](https://support.sonus.net/display/UXDOC81/Connect+SBC+Edge+to+Microsoft+Teams+Direct+Routing+to+Support+Analog+Devices)
- [Oracle 構成のドキュメント](https://www.oracle.com/technical-resources/documentation/acme-packet.html#Link-MicrosoftTeams)

## <a name="step-1--connect-the-sbc-to-direct-routing"></a>手順 1.  Connect SBC からダイレクト ルーティングへの接続

次のコマンドは、次のように SBC 接続を構成します。

- FQDN sbc.contoso.com
- 信号ポート 5068
- メディア バイパス モード
- SBC に転送された通話履歴情報
- 呼び出しと共に転送される P-Asserted-Identity (ASSERTed-Identity)ヘッダー 

```powershell
PS C:\> New-CsOnlinePSTNGateway -FQDN sbc.contoso.com -SIPSignalingPort 5068 -ForwardCallHistory $true -ForwardPAI $true -MediaBypass $true -Enabled $true 
```

## <a name="step-2--create-the-pstn-usage"></a>手順 2: PSTN 使用状況を作成する 

次のコマンドでは、空の PSTN 使用法が作成されます。 オンライン PSTN 使用法は、通話承認に使用される文字列値です。 オンライン PSTN 使用法は、オンライン音声ポリシーをルートにリンクします。 この例では、使用可能な PSTN 使用法の現在の一覧に文字列 "Interop" を追加します。 

```powershell
PS C:\> Set-CsOnlinePstnUsage -Identity global -Usage @{add="Interop"} 
```

## <a name="step-3--create-a-voice-route-and-associate-it-with-the-pstn-usage"></a>手順 3: 音声ルートを作成し、PSTN 使用法に関連付ける:

このコマンドは、番号範囲 +1425 XXX XX XX の ID "analog-interop" を持つ新しいオンライン音声ルートを作成します。  音声ルートは、オンライン PSTN 使用法 "Interop" sbc.contoso.com 関連付けるオンライン ゲートウェイの一覧に適用できます。 音声ルートには、特定の音声ルートを介してルーティングされる電話番号を識別する正規表現が含まれています。

```powershell
PS C:\> New-CsOnlineVoiceRoute -Identity analog-interop -NumberPattern "^\+1(425)(\d{7})$" -OnlinePstnGatewayList sbc.contoso.com -Priority 1 -OnlinePstnUsages "Interop"
```

## <a name="step-4-assign-the-voice-route-to-the-pstn-usage"></a>手順 4: PSTN 使用法に音声ルートを割り当てる:

このコマンドは、ID "AnalogInteropPolicy" を使用して、ユーザーごとの新しいオンライン音声ルーティング ポリシーを作成します。 このポリシーには、単一のオンライン PSTN 使用法 "Interop" が割り当てられます。

```powershell
PS C:\> New-CsOnlineVoiceRoutingPolicy -Identity "AnalogInteropPolicy" -Name "AnalogInteropPolicy" -OnlinePstnUsages "Interop"
```

## <a name="step-5-enable-the-online-user"></a>手順 5: オンライン ユーザーを有効にする

このコマンドは、ID アカウントを使用してユーザー アカウントを変更 exampleuser@contoso.com。 この場合、VoIP の Microsoft 実装である エンタープライズ VoIP を有効にし、ボイス メールを有効にし、このユーザーに +14255000000 の番号を割り当て、アカウントが変更されます。  このコマンドは、会社のテナントTeamsユーザー (ATA デバイス ユーザーを除く) ごとに実行する必要があります。

```powershell
PS C:\> Set-CsUser -Identity "exampleuser@contoso.com" -EnterpriseVoiceEnabled $True -HostedVoiceMail $True -OnPremLineUri "tel:+14255000000"
```

## <a name="step-6-assign-the-voice-route-policy-to-a-user"></a>手順 6: 音声ルート ポリシーをユーザーに割り当てる

このコマンドは、ユーザーごとのオンライン音声ルーティング ポリシー AnalogInteropPolicy を ID アドレスを持つユーザーに割り当 exampleuser@contoso.com。  このコマンドは、会社のテナントTeamsユーザー (ATA デバイス ユーザーを除く) ごとに実行する必要があります。

```powershell
PS C:\> Grant-CsOnlineVoiceRoutingPolicy -Identity "exampleuser@contoso.com" -PolicyName "AnalogInteropPolicy" 
```

## <a name="step-7--create-a-voice-route-for-an-analog-device"></a>手順 7: アナログ デバイスの音声ルートを作成する

このコマンドは、オンライン ゲートウェイ sbc.contoso.com の一覧に適用できる番号範囲 +1425 4XX XX XX の ID "analog-interop" を持つオンライン音声ルートを作成し、オンライン PSTN 使用法 "Interop" に関連付ける。  このコマンドは、適切な電話番号パターンを持つアナログ デバイスごとに実行する必要があります。 または、前のいずれかの手順でオンライン音声ルートを構成する際に、アナログ デバイスの適切な番号パターンを使用できます。

```powershell
PS C:\> New-CsOnlineVoiceRoute -Identity analog-interop -NumberPattern "^\+1(4254)(\d{6})$"  -OnlinePstnGatewayList sbc.contoso.com -Priority 1 -OnlinePstnUsages "Interop"
```

## <a name="considerations"></a>考慮事項

- 特に注意しない限り、アナログ デバイスは DTMF 数字を送信して通話を発信できる任意のデバイスです。 たとえば、アナログ電話、FAX マシン、オーバーヘッド ページなどです。

- ATA に接続されているアナログ電話は、デバイスからTeams。 Teamsユーザーは、デバイスに関連付けられている電話番号を手動で入力して、そのデバイスを呼び出す必要があります。  
 

## <a name="see-also"></a>関連項目

[ダイレクト ルーティングを計画する](direct-routing-plan.md)

[ダイレクト ルーティングを構成する](direct-routing-configure.md)
