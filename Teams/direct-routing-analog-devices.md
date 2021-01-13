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
description: この記事では、Microsoft Phone System Direct Routing でアナログ デバイスを使用する方法について説明します。
ms.openlocfilehash: 855bf0dd21659c43037b6171f523983d67c4e755
ms.sourcegitcommit: 1889ca28b9cb952b13c84efa3588957a327f9702
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/13/2021
ms.locfileid: "49841488"
---
# <a name="how-to-use-analog-devices-with-phone-system-direct-routing"></a>電話システムダイレクト ルーティングでアナログ デバイスを使用する方法

この記事では、電話システム ダイレクト ルーティングでアナログ デバイスを使用する方法について説明します。 アナログ デバイスをダイレクト ルーティングに接続するには、アナログ テレフォニー アダプター (ATA) を使用する必要があります。このアダプターは認定されたセッション ボーダー コントローラー (SBC) ベンダーがサポートする必要があります。 

ユーザーがアナログ デバイスから通話を行う場合、シグナリングとメディアはアナログ テレフォニー アダプター (ATA) を介して SBC に向かいます。  SBC は、内部ルーティング テーブルに基づいて、通話を Microsoft Teams エンドポイントまたは公衆交換電話網 (PSTN) に送信します。  デバイスが通話を行う場合、デバイスに対して作成されたルーティング ポリシーに依存します。

次の図では、Teams が +1425 XX XX と +1425 5XX XX XX の間の番号との間の番号との間で通話するように直接ルーティングが構成され、+1425 4XX XX と番号範囲 +1425 5XX XX XX を除くその他の番号との間の番号との間の PSTN 通話は、青色のルート (実線) を取る必要があります。 

> [!div class="mx-imgBorder"]
> ![ダイレクト ルーティング構成を示す図](media/direct-routing-analog-device.png)

## <a name="example--how-to-configure-the-use-of-analog-devices-with-direct-routing"></a>例: ダイレクト ルーティングを使用してアナログ デバイスの使用を構成する方法

ダイレクト ルーティングでアナログ デバイスの使用を構成するには、アナログ テレフォニー アダプターを SBC に接続し、ダイレクト ルーティングを使用するために SBC を構成する必要があります。 

この例では、次の手順を実行します。

1. SBC をダイレクト ルーティングに接続します。
2. PSTN 使用状況を作成します。
3. 音声ルートを作成し、PSTN 使用状況に関連付ける。
4. PSTN 使用状況に音声ルートを割り当てる。
5. オンライン ユーザーを有効にする。
6. ユーザーに音声ルート ポリシーを割り当てる。
7. アナログ デバイスの音声ルートを作成します。

ATA を SBC に接続し、SBC を構成する方法については、SBC 製造元の構成ガイドを参照してください。

- [AudioCodes 構成ドキュメント](https://www.audiocodes.com/media/14278/connecting-audiocodes-sbc-with-analog-device-to-microsoft-teams-direct-routing-enterprise-model-configuration-note.pdf)

- [リボンの構成に関するドキュメント](https://support.sonus.net/display/UXDOC81/Connect+SBC+Edge+to+Microsoft+Teams+Direct+Routing+to+Support+Analog+Devices)
- [Oracle 構成ドキュメント](https://www.oracle.com/technical-resources/documentation/acme-packet.html#Link-MicrosoftTeams)

## <a name="step-1--connect-the-sbc-to-direct-routing"></a>手順 1.  SBC をダイレクト ルーティングに接続する

次のコマンドは、SBC 接続を次のように構成します。

- FQDN sbc.contoso.com
- シグナリング ポート 5068
- メディア バイパス モード
- SBC に転送された通話履歴情報-
- 呼び出しと共に転送される P-Asserted-Identity (HEADER) ヘッダー 

```powershell
PS C:\> New-CsOnlinePSTNGateway -FQDN sbc.contoso.com -SIPSignalingPort 5068 -ForwardCallHistory $true -ForwardPAI $true -MediaBypass $true -Enabled $true 
```

## <a name="step-2--create-the-pstn-usage"></a>手順 2: PSTN 使用状況を作成する 

次のコマンドでは、空の PSTN 使用状況が作成されます。 オンライン PSTN 使用状況は、通話承認に使用される文字列値です。 オンライン PSTN 使用状況は、オンライン音声ポリシーをルートにリンクします。 この例では、使用可能な PSTN 使用状況の現在のリストに文字列 "相互運用" を追加します。 

```powershell
PS C:\> Set-CsOnlinePstnUsage -Identity global -Usage @{add="Interop"} 
```

## <a name="step-3--create-a-voice-route-and-associate-it-with-the-pstn-usage"></a>手順 3: 音声ルートを作成し、PSTN 使用状況に関連付ける:

このコマンドは、番号範囲 +1425 XXX XX XX の ID "アナログ相互運用" を使用して、新しいオンライン音声ルートを作成します。  音声ルートは、オンライン PSTN 使用状況 "相互運用sbc.contoso.comオンライン ゲートウェイの一覧に適用され、関連付けされます。 音声ルートには、特定の音声ルートを経由する電話番号を識別する正規表現が含まれます。

```powershell
PS C:\> New-CsOnlineVoiceRoute -Identity analog-interop -NumberPattern "^\+1(425)(\d{7}])$" -OnlinePstnGatewayList sbc.contoso.com -Priority 1 -OnlinePstnUsages "Interop"
```

## <a name="step-4-assign-the-voice-route-to-the-pstn-usage"></a>手順 4: PSTN 使用状況に音声ルートを割り当てる:

このコマンドは、ID "AnalogInteropPolicy" を使用して、新しいオンラインのユーザーごとの音声ルーティング ポリシーを作成します。 このポリシーには、"相互運用機能" という 1 つのオンライン PSTN 使用状況が割り当てられます。

```powershell
PS C:\> New-CsOnlineVoiceRoutingPolicy -Identity "AnalogInteropPolicy" -Name "AnalogInteropPolicy" -OnlinePstnUsages "Interop"
```

## <a name="step-5-enable-the-online-user"></a>手順 5: オンライン ユーザーを有効にする

このコマンドは、ID コントロールを使用してユーザー exampleuser@contoso.com。 この場合、ボイス メールが有効になっている エンタープライズ VoIP (VoIP の Microsoft 実装) を有効にするためにアカウントが変更され、このユーザーに +14255000000 という番号が割り当てされます。  このコマンドは、会社のテナントの Teams ユーザー (ATA デバイス ユーザーを除く) ごとに実行する必要があります。

```powershell
PS C:\> Set-CsUser -Identity "exampleuser@contoso.com" -EnterpriseVoiceEnabled $True -HostedVoiceMail $True -OnPremLineUri "tel:+14255000000"
```

## <a name="step-6-assign-the-voice-route-policy-to-a-user"></a>手順 6: ユーザーに音声ルート ポリシーを割り当てる

このコマンドは、ユーザーごとのオンライン音声ルーティング ポリシー AnalogInteropPolicy を、ID を持つユーザーに割り当exampleuser@contoso.com。  このコマンドは、会社のテナントの Teams ユーザー (ATA デバイス ユーザーを除く) ごとに実行する必要があります。

```powershell
PS C:\> Grant-CsOnlineVoiceRoutingPolicy -Identity "exampleuser@contoso.com" -PolicyName "AnalogInteropPolicy" 
```

## <a name="step-7--create-a-voice-route-for-an-analog-device"></a>手順 7: アナログ デバイスの音声ルートを作成する

このコマンドは、オンライン ゲートウェイ sbc.contoso.com のリストに該当する番号範囲 +1425 4XX XX XX の ID "アナログ相互運用" を含むオンライン音声ルートを作成し、オンライン PSTN 使用状況 "相互運用機能" と関連付ける。  このコマンドは、適切な電話番号パターンを持つアナログ デバイスごとに実行する必要があります。 また、前の手順の 1 つでオンライン音声ルートを構成する際に、アナログ デバイスの適切な番号パターンを使用することもできます。

```powershell
PS C:\> New-CsOnlineVoiceRoute -Identity analog-interop -NumberPattern "^\+1(4254)(\d{6}])$"  -OnlinePstnGatewayList sbc.contoso.com -Priority 1 -OnlinePstnUsages "Interop"
```

## <a name="considerations"></a>考慮事項

- 特に注意しない限り、アナログ デバイスは DTMF 桁を送信して通話を発信できるデバイスです。 たとえば、アナログ電話、FAX 機、オーバーヘッド ページなどです。

- ATA に接続されているアナログ電話は、Teams から検索できません。 Teams ユーザーがデバイスに通話するには、デバイスに関連付けられている電話番号を手動で入力する必要があります。  
 

## <a name="see-also"></a>関連項目

[ダイレクト ルーティングを計画する](direct-routing-plan.md)

[ダイレクト ルーティングを構成する](direct-routing-configure.md)
