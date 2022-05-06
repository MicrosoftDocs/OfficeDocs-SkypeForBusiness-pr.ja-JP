---
title: ダイレクト ルーティング - アナログ デバイスの接続
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.reviewer: filippse
ms.topic: conceptual
ms.service: msteams
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: この記事では、Microsoft Teams 電話 システム ダイレクト ルーティングでアナログ デバイスを使用する方法について説明します。
ms.openlocfilehash: e3de63de032d2caf06993ac0a08b624feb5a5b42
ms.sourcegitcommit: 79dfda39db208cf943d0f7b4906883bb9d034281
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/09/2022
ms.locfileid: "62457387"
---
# <a name="how-to-use-analog-devices-with-direct-routing"></a>ダイレクト ルーティングでアナログ デバイスを使用する方法

この記事では、ダイレクト ルーティングでアナログ デバイスを使用する方法について説明します。 アナログ デバイスをダイレクト ルーティングに接続するには、アナログ テレフォニー アダプター (ATA) を使用する必要があります。このアダプターは、認定されたセッション ボーダー コントローラー (SBC) ベンダーによってサポートされている必要があります。 

ユーザーがアナログ デバイスから呼び出しを行うと、シグナリングとメディアがアナログ テレフォニー アダプター (ATA) を介して SBC に流れ込みます。  SBC は、内部ルーティング テーブルに基づいて、Microsoft Teams エンドポイントまたは公衆交換電話網 (PSTN) に通話を送信します。  デバイスが呼び出しを行うとき、デバイスのルートは、デバイスに対して作成されたルーティング ポリシーによって異なります。

次の図では、+1425 4XX XX XX と +1425 5XX XX XX XX の間の番号との間で発信されるTeamsが赤いルート (点線) を使用する必要があり、+1425 4XX XX XX と番号範囲 +1425 5XX XX XX を除く他の番号との間の PSTN 通話は青色のルート (実線) を受け取る必要があります。 

> [!div class="mx-imgBorder"]
> ![ダイレクト ルーティングの構成を示す図。](media/direct-routing-analog-device.png)

## <a name="example-how-to-configure-the-use-of-analog-devices-with-direct-routing"></a>例: ダイレクト ルーティングでアナログ デバイスの使用を構成する方法

ダイレクト ルーティングでアナログ デバイスの使用を構成するには、アナログ テレフォニー アダプターを SBC に接続し、直接ルーティングを使用するように SBC を構成する必要があります。 

この例では、次の手順について説明します。

1. SBC をダイレクト ルーティングにConnectします。
2. PSTN 使用法を作成します。
3. 音声ルートを作成し、PSTN 使用法に関連付けます。
4. PSTN 使用法に音声ルートを割り当てます。
5. オンライン ユーザーを有効にします。
6. 音声ルート ポリシーをユーザーに割り当てます。
7. アナログ デバイスの音声ルートを作成します。

ATA を SBC に接続し、SBC を構成する方法については、SBC 製造元の構成ガイドを参照してください。

- [AudioCodes 構成ドキュメント](https://www.audiocodes.com/media/14278/connecting-audiocodes-sbc-with-analog-device-to-microsoft-teams-direct-routing-enterprise-model-configuration-note.pdf)

- [リボン構成のドキュメント](https://support.sonus.net/display/UXDOC81/Connect+SBC+Edge+to+Microsoft+Teams+Direct+Routing+to+Support+Analog+Devices)
- [Oracle 構成のドキュメント](https://www.oracle.com/technical-resources/documentation/acme-packet.html#Link-MicrosoftTeams)

## <a name="step-1-connect-the-sbc-to-direct-routing"></a>手順 1. SBC をダイレクト ルーティングにConnectする

次のコマンドは、SBC 接続を次のように構成します。

- FQDN sbc.contoso.com
- シグナリング ポート 5068
- メディア バイパス モード
- SBC に転送された通話履歴情報-
- 呼び出しと共に転送される P-Asserted-Identity (PAI) ヘッダー 

```powershell
PS C:\> New-CsOnlinePSTNGateway -FQDN sbc.contoso.com -SIPSignalingPort 5068 -ForwardCallHistory $true -ForwardPAI $true -MediaBypass $true -Enabled $true 
```

## <a name="step-2-create-the-pstn-usage"></a>手順 2: PSTN 使用法を作成する 

次のコマンドでは、空の PSTN 使用法が作成されます。 オンライン PSTN 使用法は、通話承認に使用される文字列値です。 オンライン PSTN 使用法は、オンライン音声ポリシーをルートにリンクします。 次の使用例は、使用可能な PSTN 使用法の現在の一覧に文字列 "相互運用" を追加します。 

```powershell
PS C:\> Set-CsOnlinePstnUsage -Identity global -Usage @{add="Interop"} 
```

## <a name="step-3-create-a-voice-route-and-associate-it-with-the-pstn-usage"></a>手順 3: 音声ルートを作成し、PSTN 使用法に関連付ける

このコマンドは、番号範囲 +1425 XXX XX XX の ID "analog-interop" を持つ新しいオンライン音声ルートを作成します。  音声ルートは、sbc.contoso.com オンライン ゲートウェイの一覧に適用され、ルートをオンライン PSTN 使用法 "相互運用" に関連付けます。 音声ルートには、特定の音声ルートを介してルーティングされる電話番号を識別する正規表現が含まれます。

```powershell
PS C:\> New-CsOnlineVoiceRoute -Identity analog-interop -NumberPattern "^\+1(425)(\d{7})$" -OnlinePstnGatewayList sbc.contoso.com -Priority 1 -OnlinePstnUsages "Interop"
```

## <a name="step-4-assign-the-voice-route-to-the-pstn-usage"></a>手順 4: PSTN 使用法に音声ルートを割り当てます。

このコマンドは、IDENTITY "AnalogInteropPolicy" を使用して、新しいオンラインのユーザーごとの音声ルーティング ポリシーを作成します。 このポリシーには、"相互運用" という 1 つのオンライン PSTN 使用法が割り当てられます。

```powershell
PS C:\> New-CsOnlineVoiceRoutingPolicy -Identity "AnalogInteropPolicy" -OnlinePstnUsages "Interop"
```

## <a name="step-5-enable-the-online-user"></a>手順 5: オンライン ユーザーを有効にする

このコマンドは、ID exampleuser@contoso.com を使用してユーザー アカウントを変更します。 この場合、アカウントは、ボイス メールが有効になっている VoIP の Microsoft 実装エンタープライズ VoIPを有効にするように変更され、このユーザーに番号 +14255000000 が割り当てられます。  このコマンドは、会社のテナント内の各Teams ユーザー (ATA デバイス ユーザーを除く) に対して実行する必要があります。

```powershell
PS C:\> Set-CsUser -Identity "exampleuser@contoso.com" -EnterpriseVoiceEnabled $True -HostedVoiceMail $True -OnPremLineUri "tel:+14255000000"
```

## <a name="step-6-assign-the-voice-route-policy-to-a-user"></a>手順 6: 音声ルート ポリシーをユーザーに割り当てる

このコマンドは、ID exampleuser@contoso.com を使用して、ユーザーごとのオンライン音声ルーティング ポリシー AnalogInteropPolicy をユーザーに割り当てます。 このコマンドは、会社のテナント内の各Teams ユーザー (ATA デバイス ユーザーを除く) に対して実行する必要があります。

```powershell
PS C:\> Grant-CsOnlineVoiceRoutingPolicy -Identity "exampleuser@contoso.com" -PolicyName "AnalogInteropPolicy" 
```

## <a name="step-7-create-a-voice-route-for-an-analog-device"></a>手順 7: アナログ デバイスの音声ルートを作成する

このコマンドは、番号範囲 +1425 4XX XX XX の ID "analog-interop" を持つオンライン音声ルートを sbc.contoso.com オンライン ゲートウェイの一覧に適用し、それをオンライン PSTN 使用法 "相互運用" に関連付けます。  このコマンドは、適切な電話番号パターンを持つ各アナログ デバイスに対して実行する必要があります。 または、前の手順のいずれかでオンライン音声ルートを構成するときに、アナログ デバイスに適切な番号パターンを使用することもできます。

```powershell
PS C:\> New-CsOnlineVoiceRoute -Identity analog-interop -NumberPattern "^\+1(4254)(\d{6})$"  -OnlinePstnGatewayList sbc.contoso.com -Priority 1 -OnlinePstnUsages "Interop"
```

## <a name="considerations"></a>考慮事項

- 特に注意しない限り、アナログ デバイスは DTMF 桁を送信して通話を発信できるデバイスです。 たとえば、アナログ電話、FAX マシン、オーバーヘッド ポケットベルなどです。

- ATA に接続されているアナログ電話は、Teamsから検索できません。 Teamsユーザーは、デバイスに関連付けられている電話番号を手動で入力して、そのデバイスを呼び出す必要があります。  
 

## <a name="see-also"></a>関連項目

[ダイレクト ルーティングを計画する](direct-routing-plan.md)

[ダイレクト ルーティングを構成する](direct-routing-configure.md)
