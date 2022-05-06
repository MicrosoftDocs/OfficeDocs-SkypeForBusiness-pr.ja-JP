---
title: 電話会議用のネットワーク上会議
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.reviewer: oscarr
ms.topic: conceptual
ms.tgt.pltfrm: cloud
audience: admin
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
- m365initiative-meetings
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 次に、電話会議用のネットワーク上について説明します。
ms.openlocfilehash: c6820bade333b6672d00e4f52a361280c10c8771
ms.sourcegitcommit: 8f999bd2e20f177c6c6d8b174ededbff43ff5076
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/15/2022
ms.locfileid: "62055667"
---
# <a name="on-network-conferencing-for-audio-conferencing"></a>電話会議用のネットワーク上会議

オンネットワーク会議を使用すると、組織は直接ルーティングを介して Microsoft ダイヤルイン番号に着信および送信電話会議の通話を送信できます。 この機能は、電話会議のサポートをサード パーティのダイヤルイン番号に拡張することを目的としていません。 サード パーティのダイヤルイン電話番号または Microsoft 電話会議ブリッジから PSTN への発信通話を介して電話会議サービスに着信通話をルーティングするために使用される場合、ネットワーク上会議はサポートされません。

この記事では、組織のオンネットワーク会議を有効にするために必要な前提条件と構成手順について説明します。

> [!IMPORTANT]
> インドでは、ネットワーク上の会議をテレフォニー機器と共に展開しないでください。
  
## <a name="prerequisites"></a>前提条件

オンネットワーク会議を構成する前に、組織が次の前提条件を満たしていることを確認します。

- 電話会議に対して有効または有効になっている組織内のすべてのユーザーが、すべての会議に対してTeamsを使用していることを確認します。 オンネットワーク会議を介した受信および送信電話会議の呼び出しのルーティングは、Teams会議でのみサポートされます。

- ネットワーク会議を使用するすべてのユーザーに電話会議ライセンスを割り当てます。

- 電話会議サービスを設定します。 詳細については、「[Microsoft Teamsの電話会議を設定する](set-up-audio-conferencing-in-teams.md)」を参照してください。

- ダイレクト ルーティング用にセッション ボーダー コントローラー (SBC) を設定します。 詳細については、「 [ダイレクト ルーティングの計画とダイレクト ルーティング](direct-routing-plan.md) の [構成」を参照してください](direct-routing-configure.md)。

  電話会議の目的でのみダイレクト ルーティングを設定する場合は、On-network 会議の "手順 1: SBC をConnectする" のみを行う必要があります。
  
## <a name="enable-the-routing-of-dial-in-calls-to-microsoft-audio-conferencing-through-direct-routing"></a>直接ルーティングを使用して Microsoft 電話会議へのダイヤルイン呼び出しのルーティングを有効にする

オンプレミス ユーザーによって行われたダイヤルイン呼び出しを直接ルーティングを介して電話会議サービスにルーティングするには、SBC と Private Branch Exchange (PBX) に対して適切なルーティング規則を構成する必要があります。

サイトのテレフォニー機器を構成して、ダイレクト ルーティング トランクを介して組織の会議ブリッジの任意のサービス番号に通話をルーティングする必要があります。

サービス番号は、Teams管理センターの **[会議 - >会議ブリッジ**] または Skype for Business Online PowerShell コマンドレット Get-CsOnlineDialInConferencingBridge を使用して確認できます。 詳細については、[Microsoft Teamsの電話会議番号](see-a-list-of-audio-conferencing-numbers-in-teams.md)の一覧を参照してください。

> [!NOTE]
> この機能は、分単位の電話会議ライセンスを持つユーザーには使用できません。

## <a name="enable-the-routing-of-teams-meeting-dial-out-calls-through-direct-routing"></a>ダイレクト ルーティングを使用してTeams会議のダイヤルアウト呼び出しのルーティングを有効にする

Teams会議のダイヤルアウト通話は、組織内の会議内から PSTN 番号に開始されます。これには、通話時の通話や新しい参加者を会議に呼び出すための通話が含まれます。

ネットワーク上のユーザーに直接ルーティングを使用して会議のダイヤルアウト ルーティングをTeamsできるようにするには、"OnlineAudioConferencingRoutingPolicy" という電話会議ルーティング ポリシーを作成して割り当てる必要があります。

OnlineAudioConferencingRoutingPolicy ポリシーは、ダイレクト ルーティングを介した 1:1 PSTN 通話の CsOnlineVoiceRoutingPolicy に相当します。 OnlineAudioConferencingRoutingPolicy ポリシーは、次のコマンドレットを使用して管理できます。

-   New-CsOnlineAudioConferencingRoutingPolicy
- Set-CsOnlineAudioConferencingRoutingPolicy
- Get-CsOnlineAudioConferencingRoutingPolicy
- Grant-CsOnlineAudioConferencingRoutingPolicy
- Remove-CsOnlineAudioConferencingRoutingPolicy

ダイレクト ルーティングのルーティングの詳細については、「ダイレクト ルーティング [の音声ルーティングを構成する」を参照してください](direct-routing-voice-routing.md)。

ダイレクト ルーティングを使用して会議ダイヤルアウト呼び出しのルーティングを有効にするには、次の手順を実行する必要があります。

- 電話会議ルーティング ポリシーを構成する
- 組織のテレフォニー機器でルーティングを構成する
- (省略可能)ダイヤル プランを構成する

Teams会議からのダイヤルアウト通話は、会議ブリッジの既定のサービス番号から発信されます。 電話会議ブリッジの既定のサービス番号の詳細については、「電話会議ブリッジ [の電話番号を変更する」](change-the-phone-numbers-on-your-audio-conferencing-bridge.md)を参照してください。

### <a name="configure-audio-conferencing-routing-policies"></a>電話会議ルーティング ポリシーを構成する

電話会議ルーティング ポリシー OnlineAudioConferencingRoutingPolicy によって、ダイレクト ルーティング トランクにルーティングされる会議のダイヤルアウト呼び出しが決まります。 CsOnlineVoiceRoutingPolicy ポリシーに精通している場合、このポリシーは非常に似た方法で動作します。

電話会議ルーティング ポリシーを設定するには、次の手順が必要です。

1. PSTN 使用法を作成する
1. 音声ルートを構成する
1. 電話会議の音声ルーティング ポリシーを作成する
1. ユーザーにポリシーを割り当てる

#### <a name="create-pstn-usages"></a>PSTN 使用法を作成する

PSTN 使用法は、音声ルートのコレクションです。 特定の開催者の会議からダイヤルアウト通話が開始されると、音声ルートは、ユーザーの音声ルーティング ポリシーを介してユーザーに関連付けられている PSTN 使用法に基づいて通話のルーティング パスを決定するために使用されます。

"Set-CsOnlinePstnUsage" コマンドレットを使用して PSTN 使用法を作成できます。 次に例を示します。

```powershell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="US and Canada"}
```

#### <a name="configure-voice-routes"></a>音声ルートを構成する

音声ルートは、Teams会議からダイヤルされた電話番号に基づいて、通話のルーティングに使用する PSTN ゲートウェイを決定します。 音声ルートは、Teams会議からダイヤルされた電話番号と正規表現パターンを照合することで、特定の通話のルーティングに使用する PSTN ゲートウェイを決定します。 音声ルートを作成するときは、ルートを 1 つ以上の PSTN 使用法に関連付ける必要があります。

"New-CsOnlineVoiceRoute" コマンドレットを使用して、音声ルートを作成し、音声ルートに関連付ける正規表現とゲートウェイを定義できます。 次に例を示します。

```powershell
New-CsOnlineVoiceRoute -Identity "Redmond 1" -NumberPattern "^\+1(425|206)(\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```

#### <a name="create-audio-conferencing-voice-routing-policies"></a>電話会議の音声ルーティング ポリシーを作成する

電話会議音声ルーティング ポリシーは、会議ダイヤルアウト通話のターゲット電話番号に基づいて、開催者の会議から発信される通話をルーティングするために使用できるルートを決定します。 電話会議音声ルーティング ポリシーは、1 つ以上の PSTN 使用法に関連付けられます。これにより、ポリシーに関連付けられている開催者の会議ダイヤルアウト呼び出しに使用される可能性のあるルートが決定されます。

"New- CsOnlineAudioConferencingRoutingPolicy" コマンドレットを使用して、電話会議の音声ルーティング ポリシーを作成できます。 次に例を示します。

```powershell
New-CsOnlineAudioConferencingRoutingPolicy "Policy 1" -OnlinePstnUsages "US and Canada"
```

ポリシーがユーザーに割り当てられ、会議のダイヤルアウト通話がユーザーの会議から開始されると、ユーザーの音声ルーティング ポリシーを介して開催者に関連付けられている PSTN 使用法の音声ルートが評価されます。 会議のダイヤルアウト通話の宛先が、開催者に関連付けられている音声ルートの 1 つの正規表現と一致する場合、会議のダイヤルアウト呼び出しは、音声ルートで定義されている PSTN ゲートウェイにルーティングされます。 会議のダイヤルアウト通話の宛先が、開催者に関連付けられている音声ルートと一致しない場合、会議のダイヤルアウト通話は Microsoft によってルーティングされます。

#### <a name="assign-a-policy-to-your-users"></a>ユーザーにポリシーを割り当てる

電話会議ルーティング ポリシーが定義されたら、それらをユーザーに割り当てることができます。 ポリシーが割り当てられると、会議のダイヤルアウト呼び出しがそれに対して評価され、ルーティング パスが決定されます。 電話会議ルーティング ポリシーは、会議のダイヤルアウト呼び出しを開始する会議のユーザーとは別に、会議の開催者に基づいて常に評価されます。

"Grant-CsOnlineAudioConferencingRoutingPolicy" コマンドレットを使用して、ユーザーに電話会議音声ルーティング ポリシーを割り当てることができます。 次に例を示します。

```powershell
Grant-CsOnlineAudioConferencingRoutingPolicy -Identity "<User Identity>" -PolicyName "Policy 1”
```

### <a name="configure-routing-on-the-telephony-equipment-of-your-organization"></a>組織のテレフォニー機器でルーティングを構成する

組織のテレフォニー機器では、ダイレクト ルーティング経由でルーティングされる会議ダイヤルアウト通話が、目的のネットワーク上の宛先にルーティングされるようにする必要があります。

### <a name="optional-configure-a-dial-plan"></a>(省略可能)ダイヤル プランを構成する

ダイヤル プランは、通話承認と通話ルーティングを目的として、個々のユーザーによってダイヤルされた電話番号を別の形式 (通常は E.164) に変換する正規化ルールのセットです。

既定では、Teams ユーザーは E.164 形式の PSTN 番号 (+\<country code\>\<number\>) にダイヤルアウトできます。 ただし、ダイヤル プランを使用すると、ユーザーは 4 桁の内線番号など、他の形式で電話番号をダイヤルできます。

On-network 会議を使用して拡張機能ベースのダイヤルを有効にする場合は、内線番号ダイヤル パターンを組織の電話番号の電話番号範囲と一致するようにダイヤル プランを設定できます。 ダイヤル プランを設定するには、「ダイヤル プラン [の作成と管理](create-and-manage-dial-plans.md)」を参照してください。

## <a name="related-topics"></a>関連項目
