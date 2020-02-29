---
title: 直接ルーティング-アナログデバイスの接続
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
description: この記事では、Microsoft Phone システムのダイレクトルーティングでアナログデバイスを使用する方法について説明します。
ms.openlocfilehash: 525e898bd0eafe88d6893249465734d7c33a10b2
ms.sourcegitcommit: 6cfaadec5782ca7316db36472bd0be20217da693
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/29/2020
ms.locfileid: "42341791"
---
# <a name="how-to-use-analog-devices-with-phone-system-direct-routing"></a>電話システムのダイレクトルーティングでアナログデバイスを使用する方法

この記事では、電話システムダイレクトルーティングでアナログデバイスを使用する方法について説明します。 アナログデバイスを直接ルーティングに接続するには、アナログテレフォニーアダプター (ATA) を使用する必要があります。このアダプターは、認定セッションボーダーコントローラー (SBC) ベンダーによってサポートされている必要があります。 

ユーザーがアナログデバイスから通話を発信すると、アナログテレフォニーアダプター (ATA) 経由での信号送信およびメディアフローが SBC に転送されます。  SBC は、内部ルーティングテーブルに基づいて、通話を Microsoft Teams のエンドポイントに、または PSTN (公衆交換電話網) に送ります。  デバイスが通話を発信すると、デバイスに対して作成されたルーティングポリシーによって、ルーティングが行われます。

次の図では、2つのチームが + 1425 4XX XX XX と + 1425 5XX XX xx の間の番号を呼び出し、かつ、+ 1425 4XX xx xx とその他の数字との間にある任意の数の PSTN 通話を受け取るように、ダイレクトルーティングが構成されています。 数値の範囲 + 1425 5XX XX XX は、青色のルート (実線) を受け取る必要があります。 

![ダイレクトルーティング構成を示す図](media/direct-routing-analog-device.png)

## <a name="example--how-to-configure-the-use-of-analog-devices-with-direct-routing"></a>例: ダイレクトルーティングでアナログデバイスの使用を構成する方法

ダイレクトルーティングでアナログデバイスの使用を構成するには、アナログのテレフォニーアダプターを SBC に接続し、直接ルーティングを使用するように SBC を構成する必要があります。 

この例では、次の手順を実行します。

1. SBC をダイレクトルーティングに接続する
2. PSTN の使用状況を作成する
3. ボイスルートを作成して、PSTN 使用量と関連付ける
4. ボイスルートを PSTN 使用量に割り当てる
5. オンラインユーザーを有効にする
6. ユーザーに音声ルートポリシーを割り当てる
7. アナログデバイスのボイスルートを作成する

ATA に ATA を接続して SBC を構成する方法については、「SBC 製造元構成ガイド」を参照してください。
- [AudioCodes 構成の文書化](https://www.audiocodes.com/media/14278/connecting-audiocodes-sbc-with-analog-device-to-microsoft-teams-direct-routing-enterprise-model-configuration-note.pdf)

## <a name="step-1--connect-the-sbc-to-direct-routing"></a>手順1  SBC をダイレクトルーティングに接続する

次のコマンドは、SBC 接続を次のように構成します。

- FQDN sbc.contoso.com
- シグナリングポート5068
- メディアバイパスモード
- SBC に転送された通話履歴情報
- 呼び出しと共に転送される P-Id (PAI) ヘッダー 

```
PS C:\> New-CsOnlinePSTNGateway -FQDN sbc.contoso.com -SIPSignalingPort 5068 -ForwardCallHistory $true -ForwardPAI $true -MediaBypass $true -Enabled $true 
```

## <a name="step-2--create-the-pstn-usage"></a>手順 2: PSTN の使用状況を作成する 

次のコマンドでは、空の PSTN の使用状況が作成されます。 オンラインの PSTN 使用状況は、通話承認に使用される文字列値です。 オンラインの PSTN 使用により、オンラインボイスポリシーがルートにリンクされます。 この例では、使用できる PSTN の現在のリストに "Interop" という文字列を追加します。 

```
PS C:\> Set-CsOnlinePstnUsage -Identity global -Usage @{add="Interop"} 
```

## <a name="step-3--create-a-voice-route-and-associate-it-with-the-pstn-usage"></a>手順 3: ボイスルートを作成して、それを PSTN 使用のために関連付けます。

このコマンドは、番号範囲 + 1425 XXX XX XX の id "アナログ相互運用" を使って、新しいオンラインボイスルートを作成します。  この音声ルートは、オンラインゲートウェイのリストに適用され、オンラインの PSTN 使用状況 "Interop" と関連付けられます。 sbc.contoso.com ボイスルートには、特定のボイスルートを通じてルーティングされる電話番号を特定する正規表現が含まれています。

```
PS C:\> New-CsOnlineVoiceRoute -Identity analog-interop -NumberPattern "^\+1(425)(\d{7}])$" -OnlinePstnGatewayList sbc.contoso.com -Priority 1 -OnlinePstnUsages "
```

## <a name="step-4-assign-the-voice-route-to-the-pstn-usage"></a>手順 4: ボイスルートを PSTN 使用量に割り当てる:

このコマンドは、Id が "AnalogInteropPolicy" のオンラインのユーザーごとのボイスルーティングポリシーを新規作成します。 このポリシーには、"Interop" という1つのオンライン PSTN 使用法が割り当てられています。

```
PS C:\> New-CsOnlineVoiceRoutingPolicy -Identity "AnalogInteropPolicy" -Name "AnalogInteropPolicy" -OnlinePstnUsages "Interop"
```

## <a name="step-5-enable-the-online-user"></a>手順 5: オンラインユーザーを有効にする

このコマンドは、Id exampleuser@contoso.com を持つユーザーアカウントを変更します。 この場合、アカウントが変更され、有効になっているボイスメールを使用して、このユーザーに番号 + 142億5500万が割り当てられます。  このコマンドは、会社のテナントの各 Teams ユーザー (ATA デバイスユーザーを除く) に対して実行する必要があります。

```
PS C:\> Set-CsUser -Identity "exampleuser@contoso.com" -EnterpriseVoiceEnabled $True -HostedVoiceMail $True -OnPremLineUri "tel:+14255000000"
```

## <a name="step-6-assign-the-voice-route-policy-to-a-user"></a>手順 6: ボイスルーティングポリシーをユーザーに割り当てる

このコマンドは、ユーザーごとのオンラインボイスルーティングポリシー AnalogInteropPolicy を id exampleuser@contoso.com のユーザーに割り当てます。  このコマンドは、会社のテナントの各 Teams ユーザー (ATA デバイスユーザーを除く) に対して実行する必要があります。

```
PS C:\> Grant-CsOnlineVoiceRoutingPolicy -Identity "exampleuser@contoso.com" -PolicyName "AnalogInteropPolicy" 
```

## <a name="step-7--create-a-voice-route-for-an-analog-device"></a>手順 7: アナログデバイスのボイスルートを作成する

このコマンドを実行すると、番号1425範囲が "アナログ-相互運用" という id のオンラインボイスルーティングが作成され、オンラインゲートウェイ sbc.contoso.com のリストにも適用され、オンラインの PSTN 使用状況 "Interop" と関連付けられます。  このコマンドは、適切な電話番号パターンを持つ各アナログデバイスに対して実行する必要があります。 または、前の手順のいずれかを実行しているときに、オンラインボイスルーティングを構成するときに、アナログデバイス用の適切な番号パターンを使用できます。

```
PS C:\> New-CsOnlineVoiceRoute -Identity analog-interop -NumberPattern "^\+1(4254)(\d{6}])$"  -OnlinePstnGatewayList sbc.contoso.com -Priority 1 -OnlinePstnUsages "Interop"
```

## <a name="considerations"></a>考慮事項

- 特に注記がない限り、アナログデバイスは、通話を発信するために DTMF 数字を送信できるデバイスです。 たとえば、アナログ電話、ファックス機器、オーバーヘッドのポケットベルなどがあります。
- ATA に接続されたアナログ電話は、Teams から検索することはできません。 チームユーザーは、デバイスに関連付けられている電話番号を手動で入力して、そのデバイスに通話を発信する必要があります。  
 

## <a name="see-also"></a>関連項目

[ダイレクト ルーティングを計画する](direct-routing-plan.md)

[ダイレクト ルーティングを構成する](direct-routing-configure.md)
