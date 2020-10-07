---
title: 電話会議のネットワーク上会議
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
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 以下では、電話会議のネットワーク上での、オープンなプレビュー機能について説明します。
ms.openlocfilehash: 38b8be382ccd1b80002688cdb7fce9aa166efc2c
ms.sourcegitcommit: f9daef3213a305676127cf5140af907e3b96d046
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/07/2020
ms.locfileid: "48369182"
---
# <a name="open-preview-of-on-network-conferencing-for-audio-conferencing"></a>電話会議のネットワーク上の会議のプレビューを開く

ネットワーク上の会議のオープンプレビューは、すべてのユーザーが利用できます。 ネットワーク上の会議では、組織は、直接ルーティングを介して、着信/発信の電話会議通話を Microsoft ダイヤルイン番号に送信できます。 この機能は、電話会議のサポートをサードパーティのダイヤルイン番号に拡張するためのものではありません。 ネットワーク上の会議は、サードパーティのダイヤルイン電話番号を使用して着信通話を電話会議サービスにルーティングするために使用されている場合はサポートされません。

この記事では、組織のネットワーク会議を有効にするために必要な前提条件と構成手順について説明します。

> [!IMPORTANT]
> ネットワーク上の会議は、インドのテレフォニー機器と共に展開することはできません。
  
## <a name="prerequisites"></a>前提条件

ネットワーク上の会議を構成する前に、組織が次の前提条件を満たしていることを確認してください。 

- 電話会議を有効にしている、または有効にする組織内のすべてのユーザーが、[チームのみ] モードであることを確認します。 ネットワーク会議経由での着信通話と発信電話会議のルーティングは、Teams 会議でのみサポートされます。

- ネットワーク上の会議を使用するすべてのユーザーに電話会議のライセンスを割り当てます。

- 電話会議サービスをセットアップします。 詳細については、「 [Microsoft Teams の電話会議をセットアップする](set-up-audio-conferencing-in-teams.md)」を参照してください。

- ダイレクトルーティング用にセッション境界コントローラー (SBC) を設定します。 詳細については、「 [ダイレクトルーティングを計画](direct-routing-plan.md) し、 [直接ルーティングを構成する](direct-routing-configure.md)」を参照してください。 

  電話会議の目的にのみ直接ルーティングを設定する場合は、「手順 1: お使いのネットワーク会議用に SBC を接続する」を完了してください。
  
## <a name="enable-the-routing-of-dial-in-calls-to-microsoft-audio-conferencing-through-direct-routing"></a>直接ルーティングによって Microsoft 電話会議へのダイヤルイン通話のルーティングを有効にする 

オンプレミスのユーザーによって行われたダイヤルイン通話を、直接ルーティングを通じて電話会議サービスにルーティングするには、SBCs とプライベート支店の Exchange (Pbx) に対して適切なルーティングルールを構成する必要があります。

ダイレクトルーティングトランクを通じて、組織の電話会議ブリッジの任意のサービス番号への通話をルーティングするように、サイトのテレフォニー機器を構成する必要があります。

[ **会議-> 会議ブリッジ** ] または [Skype For Business Online PowerShell コマンドレット get-csonlinedialinconferencingbridge を使用して、Teams 管理センターでサービス番号を見つけることができます。 詳細については、 [Microsoft Teams の電話会議番号](see-a-list-of-audio-conferencing-numbers-in-teams.md)の一覧を参照してください。

> [!NOTE]
> この機能は、1分あたりの有料電話会議ライセンスをお持ちのユーザーは利用できません。

## <a name="enable-the-routing-of-teams-meeting-dial-out-calls-through-direct-routing"></a>直接ルーティングを使用して、Teams 会議のダイヤルアウト通話のルーティングを有効にする

チーム会議のダイヤルアウト通話は、組織内の会議内から、PSTN 番号への通話 (コールイン通話、通話など) に対して開始され、新しい参加者を会議に追加します。 

直接ルーティングを使用してチーム会議のダイヤルアウトルーティングを有効にするには、"OnlineAudioConferencingRoutingPolicy" と呼ばれる電話会議ルーティングポリシーを作成して割り当てる必要があります。 

OnlineAudioConferencingRoutingPolicy ポリシーは、ダイレクトルーティングによる1:1 の PSTN 通話の CsOnlineVoiceRoutingPolicy と同じです。 OnlineAudioConferencingRoutingPolicy ポリシーは、次のコマンドレットを使用して管理できます。

-   新規-CsOnlineAudioConferencingRoutingPolicy
- Set-CsOnlineAudioConferencingRoutingPolicy
- Get-CsOnlineAudioConferencingRoutingPolicy
- Grant-CsOnlineAudioConferencingRoutingPolicy
- Remove-CsOnlineAudioConferencingRoutingPolicy

直接ルーティングのルーティングの詳細については、「 [直接ルーティング用にボイスルーティングを構成する](direct-routing-voice-routing.md)」を参照してください。


直接ルーティングによって会議のダイヤルアウト通話のルーティングを有効にするには、次の操作を行う必要があります。 

- 電話会議ルーティングポリシーを構成する
- 組織のテレフォニー機器でルーティングを構成する
- 省略ダイヤルプランを設定する

Teams 会議からのダイヤルアウト通話は、会議ブリッジの既定のサービス番号から提供されます。 電話会議ブリッジの既定のサービス番号の詳細については、「 [電話会議ブリッジの電話番号を変更](change-the-phone-numbers-on-your-audio-conferencing-bridge.md)する」を参照してください。

### <a name="configure-audio-conferencing-routing-policies"></a>電話会議ルーティングポリシーを構成する

電話会議ルーティングポリシー OnlineAudioConferencingRoutingPolicy は、ダイレクトルーティング trunks にルーティングされる会議のダイヤルアウト通話を決定します。 CsOnlineVoiceRoutingPolicy ポリシーに精通している場合、このポリシーはよく似た方法で動作します。

電話会議のルーティングポリシーをセットアップするには、次の手順を実行する必要があります。
1.  PSTN の使用状況を作成する
2.  ボイスルーティングを構成する
3.  電話会議のボイスルーティングポリシーを作成する
4.  ユーザーにポリシーを割り当てる


#### <a name="create-pstn-usages"></a>PSTN の使用状況を作成する

PSTN 使用量は、ボイスルートのコレクションです。 特定の開催者の会議でダイヤルアウト通話が開始されると、ユーザーのボイスルーティングポリシーによってユーザーに関連付けられている PSTN 経由での通話のルーティングパスが決定されます。

PSTN の使用状況を作成するには、"CsOnlinePstnUsage" コマンドレットを使用します。 次に例を示します。

```
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="US and Canada"}
```

#### <a name="configure-voice-routes"></a>ボイスルーティングを構成する

音声ルーティングでは、Teams 会議からダイヤルされた電話番号に基づいて通話をルーティングするために使用する PSTN ゲートウェイを決定します。 ボイスルーティングは、特定の通話をルーティングするために使用する PSTN ゲートウェイを決定します。これは、Teams の会議でダイヤルされた電話番号と regex のパターンを照合することによって決まります。 ボイスルートを作成する場合は、1つ以上の PSTN 使用状況にルートを関連付ける必要があります。

"CsOnlineVoiceRoute" コマンドレットを使用して、ボイスルートを作成し、その音声ルートに関連付ける regex とゲートウェイを定義できます。 次に例を示します。

```
New-CsOnlineVoiceRoute -Identity "Redmond 1" -NumberPattern "^\+1(425|206)(\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```

#### <a name="create-audio-conferencing-voice-routing-policies"></a>電話会議のボイスルーティングポリシーを作成する

電話会議の音声ルーティングポリシーは、会議のダイヤルアウト通話のターゲットの電話番号に基づいて開催者の会議から発信する通話をルーティングするために使用できるルートの候補を決定します。 電話会議のボイスルーティングポリシーは、1つ以上の PSTN 使用状況に関連付けられています。これにより、ポリシーに関連付けられた開催者の会議のダイヤルアウト呼び出しに対して使用できるルートを決定することができます。

"New-CsOnlineAudioConferencingRoutingPolicy" コマンドレットを使用して、電話会議の音声ルーティングポリシーを作成できます。 次に例を示します。

```
New-CsOnlineAudioConferencingRoutingPolicy "Policy 1" -OnlinePstnUsages "US and Canada"
```

ポリシーがユーザーに割り当てられた後、会議のダイヤルアウト通話がユーザーの会議のいずれかから開始されると、ユーザーのボイスルーティングポリシーを通じて開催者に関連付けられている PSTN の使用状況のボイスルートが評価されます。 会議のダイヤルアウトの発信先が、開催者に関連付けられているいずれかのボイスルートの regex と一致する場合、会議のダイヤルアウト通話は、ボイスルートで定義された PSTN ゲートウェイにルーティングされます。 会議のダイヤルアウトの発信先が、開催者に関連付けられているボイスルートと一致しない場合、会議のダイヤルアウト通話は Microsoft によってルーティングされます。

#### <a name="assign-a-policy-to-your-users"></a>ユーザーにポリシーを割り当てる

電話会議のルーティングポリシーが定義されたら、ユーザーに割り当てることができます。 ポリシーが割り当てられると、会議のダイヤルアウト通話がそのルーティングパスを判断するために評価されます。 電話会議のルーティングポリシーは、会議の開催者に基づいて、会議のダイヤルアウト通話を開始する会議のユーザーから独立して、常に評価されます。

"Grant-CsOnlineAudioConferencingRoutingPolicy" コマンドレットを使用して、電話会議の音声ルーティングポリシーをユーザーに割り当てることができます。 次に例を示します。

```
Grant-CsOnlineAudioConferencingRoutingPolicy -Identity "<User Identity>" -PolicyName "Policy 1”
```


### <a name="configure-routing-on-the-telephony-equipment-of-your-organization"></a>組織のテレフォニー機器でルーティングを構成する

組織のテレフォニー機器で、直接ルーティング経由でルーティングされた会議のダイヤルアウト通話が、意図した宛先にルーティングされることを確認する必要があります。


### <a name="optional-configure-a-dial-plan"></a>省略ダイヤルプランを設定する

ダイヤルプランとは、個々のユーザーによってダイヤルされた電話番号を、別の形式 (通常は E.i) に変換する正規化ルールのセットです。

既定では、Teams ユーザーは、164形式の PSTN 番号にダイヤルアウトすることができます。これは、+ \<country code\> \<number\> です。 ただし、ダイヤルプランを使って、4桁の内線番号など、他の形式で電話番号をダイヤルすることができます。

ネットワーク上の会議経由の内線番号に基づくダイヤルを有効にするには、ダイヤルプランを、内線番号のダイヤルパターンと組織の電話番号の電話番号の範囲に合わせて設定します。 ダイヤルプランを設定する方法については、「 [ダイヤルプランを作成して管理](create-and-manage-dial-plans.md)する」をご覧ください。


## <a name="known-issues-in-open-preview"></a>開いているプレビューの既知の問題

次に示すのは、ネットワーク会議のオープンプレビューリリースで現在存在する既知の問題の一覧です。 Microsoft は、これらの問題の解決に取り組んでいます。

| 問題 | ところ |
| :--- | :--- |
| ネットワーク上の会議経由でルーティングされた、匿名/非表示の発信者番号を使用したダイヤルイン通話は、会議に接続できません。 | 可能であれば、PBX または SBC の構成を設定して、ネットワーク上の会議経由でルーティングされた通話に対して、常に発信者番号認識を送信します。|
| 場合によっては、ユーザーがサービスにダイヤルインしたときに再生されるようこそメッセージ ("電話会議へようこそ") が切り捨てられ、ユーザーは "ようこそ" の単語を読み上げません。| 現時点では、この問題の回避策はありません。 |




## <a name="related-topics"></a>関連項目


