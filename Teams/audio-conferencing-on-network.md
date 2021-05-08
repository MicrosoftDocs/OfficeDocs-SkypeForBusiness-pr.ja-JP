---
title: 電話会議用のネットワーク上会議
ms.author: crowe
author: CarolynRowe
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
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 次に、電話会議用のオンネットワークのオープン プレビュー機能について説明します。
ms.openlocfilehash: d6df81cc077c69fdeb4246d682797d2ebb26b875
ms.sourcegitcommit: 950387da2a2c094b7580bcf81ae5d8b6dfba0d6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2021
ms.locfileid: "51637839"
---
# <a name="open-preview-of-on-network-conferencing-for-audio-conferencing"></a>電話会議用のオンネットワーク会議のプレビューを開く

オンネットワーク会議のオープン プレビューは、すべてのお客様が利用できます。 ネットワーク上の会議を使用すると、組織は直接ルーティングを通じて、着信および発信の電話会議通話を Microsoft ダイヤルイン番号に送信できます。 この機能は、電話会議のサポートをサード パーティのダイヤルイン番号に拡張する目的ではありません。 サード パーティのダイヤルイン電話番号または Microsoft 電話会議ブリッジから PSTN への発信通話を介して電話会議サービスへの着信通話をルーティングするために使用される場合、ネットワーク会議はサポートされません。 

この記事では、組織のネットワーク上会議を有効にするために必要な前提条件と構成手順について説明します。

> [!IMPORTANT]
> インドでは、電話会議をテレフォニー機器と一緒に展開していけはなけり。
  
## <a name="prerequisites"></a>前提条件

オンネットワーク会議を構成する前に、組織が次の前提条件を満たしていることを確認します。 

- 電話会議で有効になっている、または有効にする組織内のすべてのユーザーが、すべての会議に Teamsを使用します。 オンネットワーク会議を介した受信および送信電話会議のルーティングは、電話会議Teamsされます。

- 電話会議ライセンスを、オンネットワーク会議を使用するすべてのユーザーに割り当てる。

- 電話会議サービスを設定します。 詳細については、「電話会議[をセットアップする」を参照Microsoft Teams。](set-up-audio-conferencing-in-teams.md)

- 直接ルーティング用にセッション ボーダー コントローラー (SBC) を設定します。 詳細については、「直接ルーティングの[計画」および「ダイレクト ルーティング](direct-routing-plan.md)[の構成」を参照してください](direct-routing-configure.md)。 

  電話会議の目的でのみ直接ルーティングを設定する場合は、"手順 1: Connect SBC" をオンネットワーク会議用に完了する必要があります。
  
## <a name="enable-the-routing-of-dial-in-calls-to-microsoft-audio-conferencing-through-direct-routing"></a>直接ルーティングを使用して Microsoft 電話会議へのダイヤルイン通話のルーティングを有効にする 

オンプレミス ユーザーが行ったダイヤルイン通話を直接ルーティングを通じて電話会議サービスにルーティングするには、SBC と Private Branch Exchange (PBX) に対して適切なルーティング規則を構成する必要があります。

直接ルーティング トランクを介して組織の電話会議ブリッジの任意のサービス番号に通話をルーティングするには、サイトのテレフォニー機器を構成する必要があります。

Teams 管理センターの [会議 **- >** 会議ブリッジ] または Skype for Business Online PowerShell コマンドレット Get-CsOnlineDialInConferencingBridge を使用して、サービス番号を確認できます。 詳細については、 の電話会議番号の一覧を参照[Microsoft Teams。](see-a-list-of-audio-conferencing-numbers-in-teams.md)

> [!NOTE]
> この機能は、分単位の電話会議ライセンスを持つユーザーは使用できません。

## <a name="enable-the-routing-of-teams-meeting-dial-out-calls-through-direct-routing"></a>直接ルーティングを使用してTeamsダイヤルアウト通話のルーティングを有効にする

Teams会議のダイヤルアウト通話は、組織内の会議から PSTN 番号に開始されます。会議に新しい参加者を追加するコールや通話などです。 

ネットワーク上Teams直接ルーティングを介した会議のダイヤルアウト ルーティングを有効にするには、"OnlineAudioConferencingRoutingPolicy" という電話会議ルーティング ポリシーを作成して割り当てる必要があります。 

OnlineAudioConferencingRoutingPolicy ポリシーは、直接ルーティングを介した 1 対 1 の PSTN 呼び出しの CsOnlineVoiceRoutingPolicy と同等です。 OnlineAudioConferencingRoutingPolicy ポリシーは、次のコマンドレットを使用して管理できます。

-   New-CsOnlineAudioConferencingRoutingPolicy
- Set-CsOnlineAudioConferencingRoutingPolicy
- Get-CsOnlineAudioConferencingRoutingPolicy
- Grant-CsOnlineAudioConferencingRoutingPolicy
- Remove-CsOnlineAudioConferencingRoutingPolicy

ダイレクト ルーティングのルーティングの詳細については、「ダイレクト ルーティングの音声ルーティング [を構成する」を参照してください](direct-routing-voice-routing.md)。


直接ルーティングを介した会議ダイヤルアウト通話のルーティングを有効にするには、次の手順を実行する必要があります。 

- 電話会議ルーティング ポリシーを構成する
- 組織のテレフォニー機器でルーティングを構成する
- (省略可能)ダイヤル プランを構成する

会議からのダイヤルTeamsは、会議ブリッジの既定のサービス番号から発信されます。 電話会議ブリッジの既定のサービス番号の詳細については、「電話会議ブリッジの電話番号を変更 [する」を参照してください](change-the-phone-numbers-on-your-audio-conferencing-bridge.md)。

### <a name="configure-audio-conferencing-routing-policies"></a>電話会議ルーティング ポリシーを構成する

電話会議ルーティング ポリシー OnlineAudioConferencingRoutingPolicy は、ダイレクト ルーティング トランクにルーティングされる会議ダイヤルアウト呼び出しを決定します。 CsOnlineVoiceRoutingPolicy ポリシーをよく理解している場合、このポリシーは非常に似た方法で動作します。

電話会議ルーティング ポリシーを設定するには、次の手順が必要です。
1.  PSTN の使用状況を作成する
2.  音声ルートを構成する
3.  電話会議の音声ルーティング ポリシーを作成する
4.  ユーザーにポリシーを割り当てる


#### <a name="create-pstn-usages"></a>PSTN の使用状況を作成する

PSTN 使用法は、音声ルートのコレクションです。 特定の開催者の会議からダイヤルアウト通話が開始されると、音声ルートを使用して、ユーザーの音声ルーティング ポリシーを介してユーザーに関連付けられている PSTN 使用法に基づいて通話のルーティング パスを決定します。

PSTN 使用法は、"Set-CsOnlinePstnUsage" コマンドレットを使用して作成できます。 次に例を示します。

```powershell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="US and Canada"}
```

#### <a name="configure-voice-routes"></a>音声ルートを構成する

音声ルートは、会議からダイヤルされた電話番号に基づいて、通話をルーティングするために使用する PSTN Teamsします。 音声ルートは、特定の通話をルーティングするために使用する PSTN ゲートウェイを決定します。これは、Teamsからダイヤルされた電話番号と正規表現パターンを照合することで行います。 音声ルートを作成する場合、ルートは 1 つ以上の PSTN 使用法に関連付けられている必要があります。

"New-CsOnlineVoiceRoute" コマンドレットを使用して、音声ルートを作成し、音声ルートに関連付けられる正規表現とゲートウェイを定義できます。 次に例を示します。

```powershell
New-CsOnlineVoiceRoute -Identity "Redmond 1" -NumberPattern "^\+1(425|206)(\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```

#### <a name="create-audio-conferencing-voice-routing-policies"></a>電話会議の音声ルーティング ポリシーを作成する

電話会議の音声ルーティング ポリシーは、会議のダイヤルアウト通話のターゲット電話番号に基づいて、開催者の会議から発信された通話をルーティングするために使用できるルートを決定します。 電話会議の音声ルーティング ポリシーは、1 つ以上の PSTN 使用法に関連付けられるので、ポリシーに関連付けられている開催者の会議ダイヤルアウト通話に使用される可能性があるルートを決定します。

"New- CsOnlineAudioConferencingRoutingPolicy" コマンドレットを使用して、電話会議の音声ルーティング ポリシーを作成できます。 次に例を示します。

```powershell
New-CsOnlineAudioConferencingRoutingPolicy "Policy 1" -OnlinePstnUsages "US and Canada"
```

ポリシーがユーザーに割り当てられると、ユーザーの会議の 1 つから会議のダイヤルアウト通話が開始されると、ユーザーの音声ルーティング ポリシーを通じて開催者に関連付けられている PSTN 使用法の音声ルートが評価されます。 会議のダイヤルアウト通話先が、開催者に関連付けられている音声ルートの 1 つの正規表現と一致する場合、会議のダイヤルアウト通話は、音声ルートで定義されている PSTN ゲートウェイにルーティングされます。 会議のダイヤルアウト通話先が開催者に関連付けられているどの音声ルートとも一致しない場合、会議のダイヤルアウト通話は Microsoft によってルーティングされます。

#### <a name="assign-a-policy-to-your-users"></a>ユーザーにポリシーを割り当てる

電話会議ルーティング ポリシーを定義した後、ユーザーに割り当て可能です。 ポリシーが割り当てられると、会議のダイヤルアウト呼び出しがポリシーに対して評価され、ルーティング パスが決定されます。 電話会議ルーティング ポリシーは、会議の開催者に基づいて常に評価されます。会議のダイヤルアウト通話を開始する会議のユーザーとは独立しています。

"Grant-CsOnlineAudioConferencingRoutingPolicy" コマンドレットを使用して、電話会議の音声ルーティング ポリシーをユーザーに割り当てできます。 次に例を示します。

```powershell
Grant-CsOnlineAudioConferencingRoutingPolicy -Identity "<User Identity>" -PolicyName "Policy 1”
```


### <a name="configure-routing-on-the-telephony-equipment-of-your-organization"></a>組織のテレフォニー機器でルーティングを構成する

組織のテレフォニー機器では、ダイレクト ルーティングを介してルーティングされた会議ダイヤルアウト通話が、目的のネットワーク上の宛先にルーティングされる必要があります。


### <a name="optional-configure-a-dial-plan"></a>(省略可能)ダイヤル プランを構成する

ダイヤル プランは、通話の承認と通話ルーティングの目的で、ダイヤルされた電話番号を個々のユーザーが別の形式 (通常は E.164) に変換する正規化ルールのセットです。

既定では、Teamsユーザーは、E.164 形式 (+) で PSTN 番号にダイヤルアウトできます \<country code\> \<number\> 。 ただし、ダイヤル プランを使用して、ユーザーが他の形式 (4 桁の内線番号など) で電話番号をダイヤルできます。

ネットワーク上の会議を通じて内線番号ベースのダイヤルを有効にする場合は、組織の電話番号の電話番号範囲に合わせて、内線番号のダイヤル パターンに合わせてダイヤル プランを設定できます。 ダイヤル プランを設定するには、「ダイヤル プランを作成 [して管理する」を参照してください](create-and-manage-dial-plans.md)。


## <a name="known-issues-in-open-preview"></a>Open Preview の既知の問題

オンネットワーク会議のオープン プレビュー リリースに現在存在する既知の問題の一覧を次に示します。 Microsoft は、これらの問題に対処する作業を行っています。

| 問題 | 回避策 |
| :--- | :--- |
| オンネットワーク会議を介してルーティングされる匿名/非表示の発信者 ID を使用したダイヤルイン通話は、会議に接続できません。 | 可能であれば、PBX または SBC の構成を設定して、オンネットワーク会議を介してルーティングされた通話の発信者番号を常に送信します。|
| 場合によっては、ユーザーがサービスにダイヤルインするときに再生されるウェルカム メッセージ ("電話会議サービスへようこそ...") が切り捨てられ、ユーザーに "ようこそ" という単語が聞こえない場合があります。| 現時点では、この問題の回避策はありません。 |




## <a name="related-topics"></a>関連トピック


