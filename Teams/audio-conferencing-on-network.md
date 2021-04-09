---
title: 電話会議のオンネットワーク会議
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
description: 次に、電話会議用のオンネットワークの Open Preview 機能について説明します。
ms.openlocfilehash: d6df81cc077c69fdeb4246d682797d2ebb26b875
ms.sourcegitcommit: 950387da2a2c094b7580bcf81ae5d8b6dfba0d6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2021
ms.locfileid: "51637839"
---
# <a name="open-preview-of-on-network-conferencing-for-audio-conferencing"></a>電話会議用のネットワーク上会議のプレビューを開く

オンネットワーク会議のオープン プレビューは、すべてのお客様が利用できます。 オンネットワーク会議を使用すると、組織は直接ルーティングを通じて Microsoft ダイヤルイン番号に電話会議の受信および発信を送信できます。 この機能は、電話会議のサポートをサードパーティのダイヤルイン番号に拡張することを目的とした機能ではありません。 着信通話を電話会議サービスに第三者のダイヤルイン電話番号または発信通話を経由して Microsoft 電話会議ブリッジから PSTN にルーティングするために使用される場合、ネットワーク上会議はサポートされません。 

この記事では、組織でネットワーク上会議を有効にするために必要な前提条件と構成手順について説明します。

> [!IMPORTANT]
> インドでは、電話会議をテレフォニー機器と一緒に展開する必要があります。
  
## <a name="prerequisites"></a>前提条件

ネットワーク上会議を構成する前に、組織が次の前提条件を満たしていることを確認します。 

- 組織内で電話会議が有効になっているか、有効になるすべてのユーザーが、すべての会議に Teams を使用している必要があります。 オンネットワーク会議を介した受信および送信の電話会議のルーティングは、Teams 会議でのみサポートされます。

- 電話会議ライセンスを、オンネットワーク会議を使用するすべてのユーザーに割り当てる。

- 電話会議サービスをセットアップします。 詳細については [、「Microsoft Teams の電話会議をセットアップする」を参照してください](set-up-audio-conferencing-in-teams.md)。

- 直接ルーティング用にセッション ボーダー コントローラー (SBC) をセットアップします。 詳細については、「ダイレクト ルーティングを計画 [する」および「](direct-routing-plan.md) ダイレクト ルーティング [を構成する」を参照してください](direct-routing-configure.md)。 

  電話会議の目的でのみ直接ルーティングを設定する場合は、"手順 1: SBC を接続する" をオンネットワーク会議用に完了する必要があります。
  
## <a name="enable-the-routing-of-dial-in-calls-to-microsoft-audio-conferencing-through-direct-routing"></a>直接ルーティングを使用して Microsoft 電話会議へのダイヤルイン通話のルーティングを有効にする 

オンプレミス ユーザーが行ったダイヤルイン通話を直接ルーティングを通じて電話会議サービスにルーティングするには、SBC と Private Branch Exchange (PBX) に適切なルーティング ルールを構成する必要があります。

直接ルーティング トランクを介して組織の会議ブリッジの任意のサービス番号に通話をルーティングするには、サイトのテレフォニー機器を構成する必要があります。

Teams 管理センターの [会議 - **>** 会議ブリッジ] または Skype for Business Online PowerShell コマンドレット Get-CsOnlineDialInConferencingBridge を使用して、サービス番号を確認できます。 詳細については、Microsoft Teams の電話会議番号 [の一覧を参照してください](see-a-list-of-audio-conferencing-numbers-in-teams.md)。

> [!NOTE]
> この機能は、分単位支払い電話会議ライセンスを持つユーザーは使用できません。

## <a name="enable-the-routing-of-teams-meeting-dial-out-calls-through-direct-routing"></a>直接ルーティングを使用して Teams 会議のダイヤルアウト通話のルーティングを有効にする

Teams 会議のダイヤルアウト通話は、組織内の会議内から PSTN 番号に開始されます。この番号には、コール/Me-at 通話や、新しい参加者を会議に追加する通話が含されます。 

Teams 会議のダイヤルアウト ルーティングを有効にするには、"OnlineAudioConferencingRoutingPolicy" と呼ばれる電話会議ルーティング ポリシーを作成して割り当てる必要があります。 

OnlineAudioConferencingRoutingPolicy ポリシーは、ダイレクト ルーティングを介した 1 対 1 PSTN 通話の CsOnlineVoiceRoutingPolicy と同等です。 OnlineAudioConferencingRoutingPolicy ポリシーは、次のコマンドレットを使用して管理できます。

-   New-CsOnlineAudioConferencingRoutingPolicy
- Set-CsOnlineAudioConferencingRoutingPolicy
- Get-CsOnlineAudioConferencingRoutingPolicy
- Grant-CsOnlineAudioConferencingRoutingPolicy
- Remove-CsOnlineAudioConferencingRoutingPolicy

ダイレクト ルーティングのルーティングの詳細については、「ダイレクト ルーティングの音声ルーティング [を構成する」を参照してください](direct-routing-voice-routing.md)。


直接ルーティングを使用して会議のダイヤルアウト通話のルーティングを有効にするには、次の必要があります。 

- 電話会議ルーティング ポリシーを構成する
- 組織のテレフォニー機器でルーティングを構成する
- (省略可能)ダイヤル プランを構成する

Teams 会議からのダイヤルアウト通話は、会議ブリッジの既定のサービス番号から発信されます。 電話会議ブリッジの既定のサービス番号の詳細については、「電話会議ブリッジの電話番号を変更する」 [を参照してください](change-the-phone-numbers-on-your-audio-conferencing-bridge.md)。

### <a name="configure-audio-conferencing-routing-policies"></a>電話会議ルーティング ポリシーを構成する

電話会議ルーティング ポリシー OnlineAudioConferencingRoutingPolicy は、ダイレクト ルーティング トランクにルーティングされる会議ダイヤルアウト通話を決定します。 CsOnlineVoiceRoutingPolicy ポリシーをよく知っている場合、このポリシーは非常に似た方法で動作します。

電話会議ルーティング ポリシーを設定するには、次の手順が必要です。
1.  PSTN 使用状況を作成する
2.  音声ルートを構成する
3.  電話会議の音声ルーティング ポリシーを作成する
4.  ユーザーにポリシーを割り当てる


#### <a name="create-pstn-usages"></a>PSTN 使用状況を作成する

PSTN の使用状況は、音声ルートのコレクションです。 ダイヤルアウト通話が指定の開催者の会議から開始される場合、音声ルートは、ユーザーの音声ルーティング ポリシーを介してユーザーに関連付けられている PSTN 使用状況に基づいて、通話のルーティング パスを決定するために使用されます。

"Set-CsOnlinePstnUsage" コマンドレットを使用して PSTN 使用状況を作成できます。 次に例を示します。

```powershell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="US and Canada"}
```

#### <a name="configure-voice-routes"></a>音声ルートを構成する

音声ルートは、Teams 会議からダイヤルされた電話番号に基づいて通話をルーティングするために使用する必要がある PSTN ゲートウェイを決定します。 音声ルートは、Teams 会議からダイヤルされた電話番号と正規表現パターンを照合して、特定の通話をルーティングするために使用する PSTN ゲートウェイを決定します。 音声ルートを作成する場合、ルートは 1 つ以上の PSTN 使用状況に関連付けられている必要があります。

音声ルートを作成し、"New-CsOnlineVoiceRoute" コマンドレットを使用して、音声ルートに関連付けられる正規表現とゲートウェイを定義できます。 次に例を示します。

```powershell
New-CsOnlineVoiceRoute -Identity "Redmond 1" -NumberPattern "^\+1(425|206)(\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```

#### <a name="create-audio-conferencing-voice-routing-policies"></a>電話会議の音声ルーティング ポリシーを作成する

電話会議の音声ルーティング ポリシーは、会議ダイヤルアウト通話の対象電話番号に基づいて、開催者の会議から発信される通話をルーティングするために使用できる可能性があるルートを決定します。 電話会議の音声ルーティング ポリシーは、1 つ以上の PSTN 使用状況に関連付けられているので、ポリシーに関連付けられている開催者の会議ダイヤルアウト通話に使用される可能性があるルートを決定します。

電話会議の音声ルーティング ポリシーは、"New- CsOnlineAudioConferencingRoutingPolicy" コマンドレットを使用して作成できます。 次に例を示します。

```powershell
New-CsOnlineAudioConferencingRoutingPolicy "Policy 1" -OnlinePstnUsages "US and Canada"
```

ポリシーがユーザーに割り当てられると、ユーザーの会議の 1 つから会議のダイヤルアウト通話が開始されると、ユーザーの音声ルーティング ポリシーを通じて開催者に関連付けられている PSTN 使用状況の音声ルートが評価されます。 会議のダイヤルアウト呼び出し先が、開催者に関連付けられている音声ルートの 1 つの正規表現と一致する場合、会議のダイヤルアウト通話は音声ルートで定義された PSTN ゲートウェイにルーティングされます。 会議のダイヤルアウト通話先が開催者に関連付けられている音声ルートと一致しない場合、会議のダイヤルアウト通話は Microsoft によってルーティングされます。

#### <a name="assign-a-policy-to-your-users"></a>ユーザーにポリシーを割り当てる

電話会議ルーティング ポリシーを定義した後、ユーザーに割り当て可能です。 ポリシーが割り当てられると、会議のダイヤルアウト通話がポリシーに対して評価され、ルーティング パスが決定されます。 電話会議ルーティング ポリシーは、会議のダイヤルアウト通話を開始する会議のユーザーとは独立して、常に会議の開催者に基づいて評価されます。

ユーザーに電話会議音声ルーティング ポリシーを割り当てるには、"Grant-CsOnlineAudioConferencingRoutingPolicy" コマンドレットを使用します。 次に例を示します。

```powershell
Grant-CsOnlineAudioConferencingRoutingPolicy -Identity "<User Identity>" -PolicyName "Policy 1”
```


### <a name="configure-routing-on-the-telephony-equipment-of-your-organization"></a>組織のテレフォニー機器でルーティングを構成する

組織のテレフォニー機器では、ダイレクト ルーティングを介してルーティングされる会議のダイヤルアウト通話が、意図したネットワーク上の宛先にルーティングされる必要があります。


### <a name="optional-configure-a-dial-plan"></a>(省略可能)ダイヤル プランを構成する

ダイヤル プランは、個別のユーザーによるダイヤルされた電話番号を、通話承認と通話ルーティングの目的で代替形式 (通常は E.164) に変換する正規化ルールのセットです。

既定では、Teams ユーザーは E.164 形式 (+) で PSTN 番号にダイヤルアウトできます \<country code\> \<number\> 。 ただし、ダイヤル プランを使用すると、ユーザーが他の形式 (4 桁の内線番号など) で電話番号をダイヤルできます。

ネットワーク上の会議を通じて内線番号ベースのダイヤルを有効にする場合は、組織の電話番号の電話番号範囲と内線番号のダイヤル パターンを一致するようにダイヤル プランを設定できます。 ダイヤル プランを設定するには、「ダイヤル プランを作成 [して管理する」を参照してください](create-and-manage-dial-plans.md)。


## <a name="known-issues-in-open-preview"></a>Open Preview の既知の問題

以下は、オンネットワーク会議の Open Preview リリースに現在存在する既知の問題の一覧です。 Microsoft では、これらの問題の解決に取り組み中です。

| 問題 | 回避策 |
| :--- | :--- |
| オンネットワーク会議を介してルーティングされる匿名/非表示の発信者 ID を含むダイヤルイン通話は、会議に接続できません。 | 可能であれば、PBX または SBC で構成を設定して、常にオンネットワーク会議経由でルーティングされる通話の発信者番号を送信します。|
| 場合によっては、ユーザーがサービスにダイヤルインするときに再生されるウェルカム メッセージ ("電話会議サービスへようこそ...") が切り捨てられ、ユーザーには "ようこそ" という単語が聞こえない場合があります。| 現時点では、この問題の回避策はありません。 |




## <a name="related-topics"></a>関連項目


