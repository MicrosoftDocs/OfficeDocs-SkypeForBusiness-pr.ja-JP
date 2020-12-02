---
title: 直接ルーティング用のボイスルーティングを構成する
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
description: Microsoft Phone システムのダイレクトルーティングでボイスルーティングを構成する方法について説明します。
ms.openlocfilehash: e87d7d04f9b2477d65e08f461ac3ff113b4d0e7c
ms.sourcegitcommit: d85425d9e6022d1bf84b877920640f9cbaf8bdce
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/02/2020
ms.locfileid: "49530994"
---
# <a name="configure-voice-routing-for-direct-routing"></a>直接ルーティング用のボイスルーティングを構成する

この記事では、電話システムのダイレクトルーティングのボイスルーティングを構成する方法について説明します。  これは、次の手順の手順3で、直接ルーティングを構成します。

- 手順1 [SBC と Microsoft 電話システムを接続して接続を検証する](direct-routing-connect-the-sbc.md) 
- 手順2 [ユーザーが直接ルーティング、音声、ボイスメールを使用できるようにする](direct-routing-enable-users.md)
- **手順3音声ルーティングを構成する** (この記事)
- 手順4。 [数値を別の形式に変換する](direct-routing-translate-numbers.md) 

直接ルーティングを設定するために必要なすべての手順については、「 [直接ルーティングを構成する](direct-routing-configure.md)」を参照してください。

## <a name="voice-routing-overview"></a>音声ルーティングの概要

Microsoft 電話システムには、次のことに基づいて特定のセッションボーダーコントローラー (SBC) に通話を送信できるルーティングメカニズムがあります。 

- 呼び出した番号のパターン 
- 呼び出された番号パターンと、通話を発信した特定のユーザー
 
SBCs は、アクティブなバックアップとして指定できます。 Active として構成されている SBC を特定の通話ルートで利用できない場合、通話はバックアップ SBC にルーティングされます。
 
音声ルーティングは、次の要素で構成されます。 

- **ボイスルーティングポリシー** – PSTN の使用を可能にするコンテナーであり、ユーザーまたは複数のユーザーに割り当てることができます。 

- **Pstn 使用状況** –ボイスルートと pstn 使用のコンテナー。さまざまな音声ルーティングポリシーで共有できます。 

- **ボイスルーティング** –番号パターンとオンライン PSTN ゲートウェイのセットによって、通話番号がパターンと一致する通話に使用されます。

- **オンライン PSTN ゲートウェイ** -sbc を介して通話を発信するときに適用される構成 (たとえば、P-指定された ID (pai) や優先コーデックなど) を保存する sbc へのポインターです。音声ルートに追加することができます。

## <a name="voice-routing-policy-considerations"></a>ボイスルーティングポリシーに関する考慮事項

ユーザーが通話プランのライセンスを持っている場合、そのユーザーの発信通話は、Microsoft 通話プランの PSTN インフラストラクチャを介して自動的にルーティングされます。 通話プランのユーザーにオンラインボイスルーティングポリシーを構成して割り当てると、そのユーザーの発信通話は、ダイヤルした番号がオンラインボイスルーティングポリシーで定義されている番号パターンと一致するかどうかを確認するためにチェックされます。 対戦がある場合、通話はダイレクトルーティングトランクを介してルーティングされます。 一致するものがない場合は、通話プランの PSTN インフラストラクチャを経由して通話がルーティングされます。

> [!CAUTION]
> グローバルな (組織全体の既定の) オンラインボイスルーティングポリシーを構成して適用すると、組織内のすべての音声対応ユーザーはそのポリシーを継承します。これにより、通話プランのユーザーが誤って直接ルーティングトランクにルーティングされる可能性があります。 すべてのユーザーがグローバルなオンラインボイスルーティングポリシーを使用しないようにするには、カスタムのオンラインボイスルーティングポリシーを構成して、ボイス対応ユーザーに割り当てる必要があります。

## <a name="example-1-voice-routing-with-one-pstn-usage"></a>例 1: 1 つの PSTN 利用状況での音声ルーティング

次の図は、通話フローにおけるボイスルーティングポリシーの2つの例を示しています。

**通話フロー 1 (左側):** ユーザーが + 1 425 XXX XX xx または + 1 206 XXX XX xx を呼び出した場合、通話は SBC sbc1.contoso.biz または sbc2.contoso.biz にルーティングされます。 Sbc1.contoso.biz と sbc2.contoso.biz のどちらも使用できない場合は、通話が切断されます。 

**通話フロー 2 (右側):** ユーザーが + 1 425 XXX XX xx または + 1 206 XXX XX xx への通話を発信した場合、通話はまず SBC sbc1.contoso.biz または sbc2.contoso.biz にルーティングされます。 どちらの SBC も使用できない場合は、優先度の低いルートが試されます (sbc3.contoso.biz と sbc4.contoso.biz)。 利用可能な SBCs がない場合は、通話が切断されます。 

![ボイスルーティングポリシーの例を示しています](media/ConfigDirectRouting-VoiceRoutingPolicyExamples.png)

どちらの例でも、ボイスルートには優先順位が割り当てられていますが、ルートの SBCs はランダムな順序で試行されます。 1つのルートで2つの SBC が構成されている場合、転送に対する新しい招待がルート内の別の SBC に送信される可能性があるため、ネットワークトラフィックは、両方の SBC またはメディアの間でルーティング可能でなければなりません。

  > [!NOTE]
  > ユーザーに Microsoft の通話プランライセンスも付与されていない限り、そのパターンに一致する番号 (1 425 XXX XX XX または + 1 206 XXX XX xx) は、この構成の例では削除されません。 ユーザーが通話プランライセンスを持っている場合は、Microsoft 通話プランのポリシーに従って、通話が自動的にルーティングされます。 Microsoft 通話プランは、Microsoft 通話プランライセンスを持つすべてのユーザーに対して、最後のルートとして自動的に適用され、追加の通話ルーティング構成は必要ありません。

次の図に示す例では、すべての米国とカナダの電話番号に通話を送信するための音声ルートが追加されています (通話は、番号パターン + 1 XXX XXX XX XX) に移動します。

![ボイスルーティングポリシーを3番目のルートとともに示しています](media/ConfigDirectRouting-VoiceRoutingPolicywith3rdroute.png)

その他のすべての通話では、ユーザーに両方のライセンスがある場合 (Microsoft Phone システムと Microsoft 通話プラン)、自動ルートが使用されます。 管理者が作成したオンラインボイスルートの番号パターンと一致しない場合、その通話は Microsoft の通話プランを介してルーティングされます。 ユーザーが Microsoft 電話システムしか使用していない場合は、一致するルールがないため、通話が切断されます。

  > [!NOTE]
  > ルート "Other + 1" の優先度の値は、パターン + 1 XXX XXX XX XX と一致するルートが1つだけであるため、この例では問題ありません。 ユーザーが + 1 324 567 89 89 に通話を発信し、sbc5.contoso.biz と sbc6.contoso.biz の両方を利用できない場合は、通話が切断されます。

次の表は、3つのボイスルートを使った構成をまとめたものです。 この例では、3つのルートすべてが同じ PSTN 使用量 "US とカナダ" に含まれています。  すべてのルートは、"US とカナダ" の PSTN 使用と関連付けられており、PSTN の使用は "米国限定" ボイスルーティングポリシーに関連付けられています。

|**PSTN 使用法**|**ボイスルート**|**番号パターン**|**[Priority]**|**SBC**|**説明**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|米国およびカナダ|"レドモンド 1"|^\\+ 1 (425 \| 206) (\d {7} ) $|1|sbc1.contoso.biz<br/>sbc2.contoso.biz|呼び出された数値 + 1 425 XXX XX XX または + 1 206 XXX XX xx のアクティブルート|
|米国およびカナダ|"Redmond 2"|^\\+ 1 (425 \| 206) (\d {7} ) $|2|sbc3.contoso.biz<br/>sbc4.contoso.biz|呼び出した数値 + 1 425 XXX XX XX または + 1 206 XXX XX xx のバックアップルート|
|米国およびカナダ|"Other + 1"|^\\+ 1 (\d {10} ) $|3|sbc5.contoso.biz<br/>sbc6.contoso.biz|"発信番号" のルート + 1 XXX XXX XX XX (+ 1 425 XXX XX xx または + 1 206 XXX XX xx)|
|||||||

## <a name="example-1-configuration-steps"></a>使用例 1: 構成手順

次の例は、次の方法を示しています。

1. 単一の PSTN 使用を作成します。
2. 3つのボイスルーティングを構成します。
3. ボイスルーティングポリシーを作成します。
4. Spencer Low という名前のユーザーにポリシーを割り当てます。

[Microsoft Teams 管理センター](#admincenterexample1)または[PowerShell](#powershellexample1)を使用して、次の手順を実行できます。

### <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターの使用
<a name="admincenterexample1"></a>

#### <a name="step-1-create-the-us-and-canada-pstn-usage"></a>手順 1: "US とカナダ" の PSTN 使用量を作成する

1. Microsoft Teams 管理センターの左のナビゲーションで、[**音声**  >  の **直接ルーティング**] に移動し、右上隅の [ **PSTN 使用状況レコードの管理**] を選びます。
2. [ **追加**] をクリックし、「 **米国」と「カナダ**」と入力して、[ **適用**] をクリックします。

#### <a name="step-2-create-three-voice-routes-redmond-1-redmond-2-and-other-1"></a>手順 2: 3 つのボイスルーティングルート (Redmond 1、Redmond 2、その他 + 1) を作成する

次の手順では、ボイスルートの作成方法について説明します。 次の手順を使用して、前の表で説明した設定を使用して、この例で Redmond 1、Redmond 2、その他の + 1 という名前の3つのボイスルートを作成します。

1. Microsoft Teams 管理センターの左のナビゲーションで、[**音声** の直接ルーティング] に移動し、  >  **Direct Routing**[**ボイス** ルーティング] タブを選択します。
2. [ **追加**] をクリックして、ボイスルートの名前と説明を入力します。
3. 優先度を設定し、ダイヤル番号のパターンを指定します。
4. 音声ルートを使用して SBC を登録するには、[ **sbcs 登録 (オプション)**] で [ **sbcs の追加**] をクリックし、登録する sbcs を選択して、[ **適用**] をクリックします。
5. PSTN 使用状況レコードを追加するには、[ **pstn 使用状況レコード] (オプション)** の [ **pstn 使用量の追加**] をクリックし、追加する pstn レコードを選択して、[ **適用**] をクリックします。
6. [**保存**] をクリックします。

#### <a name="step-3-create-a-voice-routing-policy-named-us-only-and-add-the-us-and-canada-pstn-usage-to-the-policy"></a>手順 3: "US Only" という名前の音声ルーティングポリシーを作成し、ポリシーに "US" と "カナダ" の PSTN 使用を追加する

1. Microsoft Teams 管理センターの左のナビゲーションで、[**音声**  >  **音声ルーティングポリシー**] に移動し、[**追加**] をクリックします。
2. 名前として「 **US** 」と入力して、説明を追加します。
3. [ **Pstn 使用状況レコード**] で、[ **pstn 使用量の追加**] をクリックし、"米国およびカナダ" の pstn 利用状況レコードを選択して、[ **適用**] をクリックします。
4. [**保存**] をクリックします。

詳細については、「 [ボイスルーティングポリシーを管理](manage-voice-routing-policies.md)する」を参照してください。

#### <a name="step-4-assign-the-voice-routing-policy-to-a-user-named-spencer-low"></a>手順 4: Spencer Low という名前のユーザーに音声ルーティングポリシーを割り当てる

1. Microsoft Teams 管理センターの左側のナビゲーションで、**[ユーザー]** に移動してユーザーをクリックします。
2. **[ポリシー]** をクリックし、**[割り当てられたポリシー]** の横にある **[編集]** をクリックします。
3. [ **音声ルーティングポリシー**] で、[US のみ] ポリシーを選択し、[ **保存**] をクリックします。

詳細については、「 [ボイスルーティングポリシーを管理](manage-voice-routing-policies.md)する」を参照してください。

### <a name="using-powershell"></a>PowerShell の使用
<a name="powershellexample1"></a>


#### <a name="step-1-create-the-us-and-canada-pstn-usage"></a>手順 1: "US とカナダ" の PSTN 使用量を作成する

Skype for Business Online のリモート PowerShell セッションで、次のように入力します。

```PowerShell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="US and Canada"}
```

次のように入力して使用が作成されたことを確認します。

```PowerShell
Get-CSOnlinePSTNUsage
``` 

これは、切り捨てられる可能性がある名前のリストを返します。

```console
Identity    : Global
Usage        : {testusage, US and Canada, International, karlUsage. . .}
```

次の例は、Powershell コマンドを実行して完全な名前を表示した場合の結果を示して `(Get-CSOnlinePSTNUsage).usage` います (トランケートされません)。

<pre>
 testusage
 US and Canada
 International
 karlUsage
 New test env
 Tallinn Lab Sonus
 karlUsage2
 Unrestricted
 Two trunks
</pre>

#### <a name="step-2-create-three-voice-routes-redmond-1-redmond-2-and-other-1"></a>手順 2: 3 つのボイスルーティングルート (Redmond 1、Redmond 2、その他 + 1) を作成する

"Redmond 1" ルートを作成するには、Skype for Business Online の PowerShell セッションで、次のように入力します。

```PowerShell
New-CsOnlineVoiceRoute -Identity "Redmond 1" -NumberPattern "^\+1(425|206)
(\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```

戻り値:
<pre>
Identity                : Redmond 1
Priority                : 1
Description             :
NumberPattern           : ^\+1(425|206) (\d{7})$
OnlinePstnUsages        : {US and Canada}
OnlinePstnGatewayList   : {sbc1.contoso.biz, sbc2.contoso.biz}
Name                    : Redmond 1
</pre>

レドモンド2ルートを作成するには、次のように入力します。

```PowerShell
New-CsOnlineVoiceRoute -Identity "Redmond 2" -NumberPattern "^\+1(425|206)
(\d{7})$" -OnlinePstnGatewayList sbc3.contoso.biz, sbc4.contoso.biz -Priority 2 -OnlinePstnUsages "US and Canada"
```

他の + 1 ルートを作成するには、次のように入力します。

```PowerShell
New-CsOnlineVoiceRoute -Identity "Other +1" -NumberPattern "^\+1(\d{10})$"
-OnlinePstnGatewayList sbc5.contoso.biz, sbc6.contoso.biz -OnlinePstnUsages "US and Canada"
```

  > [!CAUTION]
  > 数値 Pattern 属性の正規表現が有効な式であることを確認します。 次の web サイトを使ってテストできます。 [https://www.regexpal.com](https://www.regexpal.com)

場合によっては、すべての通話を同じ SBC にルーティングする必要があります。use-Number パターン ". *"

すべての通話を同じ SBC にルーティングします。

```PowerShell
Set-CsOnlineVoiceRoute -id "Redmond 1" -NumberPattern ".*" -OnlinePstnGatewayList sbc1.contoso.biz
```

次のような `Get-CSOnlineVoiceRoute` オプションを使用して PowerShell コマンドを実行して、ルートが正しく構成されていることを確認します。

```PowerShell
Get-CsOnlineVoiceRoute | Where-Object {($_.priority -eq 1) -or ($_.priority -eq 2) or ($_.priority -eq 4) -Identity "Redmond 1" -NumberPattern "^\+1(425|206) (\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```
戻り値:
<pre>
Identity            : Redmond 1 
Priority               : 1
Description         : 
NumberPattern         : ^\+1(425|206) (\d{7})$
OnlinePstnUsages     : {US and Canada}     
OnlinePstnGatewayList    : {sbc1.contoso.biz, sbc2.contoso.biz}
Name             : Redmond 1
Identity        : Redmond 2 
Priority               : 2
Description         : 
NumberPattern         : ^\+1(425|206) (\d{7})$
OnlinePstnUsages     : {US and Canada}     
OnlinePstnGatewayList    : {sbc3.contoso.biz, sbc4.contoso.biz}
Name             : Redmond 2
    
Identity        : Other +1 
Priority               : 4
Description         : 
NumberPattern         : ^\+1(\d{10})$
OnlinePstnUsages     : {US and Canada}     
OnlinePstnGatewayList    : {sbc5.contoso.biz, sbc6.contoso.biz}
Name             : Other +1
</pre>

この例では、ルート "Other + 1" は優先度4を自動的に割り当てられています。 

#### <a name="step-3-create-a-voice-routing-policy-named-us-only-and-add-the-us-and-canada-pstn-usage-to-the-policy"></a>手順 3: "US Only" という名前の音声ルーティングポリシーを作成し、ポリシーに "US" と "カナダ" の PSTN 使用を追加する

Skype for Business Online の PowerShell セッションで、次のように入力します。

```PowerShell
New-CsOnlineVoiceRoutingPolicy "US Only" -OnlinePstnUsages "US and Canada"
```

結果は、次の例のように表示されます。

<pre>
Identity            : Tag:US only
OnlinePstnUsages    : {US and Canada}
Description         :
RouteType           : BYOT
</pre>

#### <a name="step-4-assign-the-voice-routing-policy-to-a-user-named-spencer-low"></a>手順 4: Spencer Low という名前のユーザーに音声ルーティングポリシーを割り当てる

Skype for Business Online の PowerShell セッションで、次のように入力します。

```PowerShell
Grant-CsOnlineVoiceRoutingPolicy -Identity "Spencer Low" -PolicyName "US Only"
```

このコマンドを入力して、ポリシーの割り当てを確認します。

```PowerShell
Get-CsOnlineUser "Spencer Low" | select OnlineVoiceRoutingPolicy
```

このコマンドは次の値を返します。
<pre>
OnlineVoiceRoutingPolicy
---------------------
US Only
</pre>

## <a name="example-2-voice-routing-with-multiple-pstn-usages"></a>例 2: 複数の PSTN 使用によるボイスルーティング

例1で作成した音声ルーティングポリシーでは、Microsoft 通話プランライセンスもユーザーに割り当てられていない限り、米国とカナダでの電話番号への通話のみが許可されています。

次の例では、"制限なし" のボイスルーティングポリシーを作成できます。 このポリシーは、例1で作成された "US and カナダ" PSTN 使用量と、新しい "国際" PSTN の使用状況を再利用します。 このポリシーは、SBCs sbc2.contoso.biz と sbc5.contoso.biz に対するその他のすべての通話をルーティングします。

次に示す例では、ユーザー Spencer 低に米国限定ポリシーを割り当て、ユーザー John 森には制限なしのポリシーを割り当てて、ルーティングが次のように行われるようにします。

- Spencer 安値– US のみのポリシー。  通話は米国とカナダの番号のみに許可されています。 Redmond の番号範囲に発信する場合は、特定の SBCs セットを使用する必要があります。 米国以外の番号は、通話プランライセンスがユーザーに割り当てられていない限り、ルーティングされません。

- John 森–国際ポリシー。  通話は任意の番号に許可されています。 Redmond の番号範囲に発信する場合は、特定の SBCs セットを使用する必要があります。 米国以外の番号は、sbc2.contoso.biz と sbc5.contoso.biz を使ってルーティングされます。

![ユーザー Spencer Low に割り当てられている音声ルーティングポリシーを表示します](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoSpencerLow.png)

その他のすべての通話では、ユーザーに両方のライセンス (Microsoft Phone システムと Microsoft 通話プラン) がある場合、自動ルートが使用されます。 管理者が作成したオンラインボイスルートの番号パターンと一致しない場合は、Microsoft 通話プランを使って通話がルーティングされます。  ユーザーが Microsoft 電話システムのみを使用している場合は、一致するルールがないため、通話が切断されます。

![ユーザー John 森に割り当てられているボイスルーティングポリシーを示しています](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoJohnWoods.png)

次の表は、ルーティングポリシーの "制限なし" を使用しています。 

|**PSTN 使用法**|**ボイスルート**|**番号パターン**|**[Priority]**|**SBC**|**説明**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|米国およびカナダ|"レドモンド 1"|^\\+ 1 (425 \| 206) (\d {7} ) $|1|sbc1.contoso.biz<br/>sbc2.contoso.biz|呼び出し先の番号 + 1 425 XXX XX XX または + 1 206 XXX XX xx のアクティブルート|
|米国およびカナダ|"Redmond 2"|^\\+ 1 (425 \| 206) (\d {7} ) $|2|sbc3.contoso.biz<br/>sbc4.contoso.biz|呼び出し先の番号のバックアップルート + 1 425 XXX XX XX または + 1 206 XXX XX xx|
|米国およびカナダ|"Other + 1"|^\\+ 1 (\d {10} ) $|3|sbc5.contoso.biz<br/>sbc6.contoso.biz|呼び出し先の番号のルーティング + 1 XXX XXX XX XX (+ 1 425 XXX XX xx または + 1 206 XXX XX xx)|
|International|International|\d +|4|sbc2.contoso.biz<br/>sbc5.contoso.biz|任意の番号パターンのルート |

  > [!NOTE]
  > - ボイスルーティングポリシーの PSTN 使用の順序は重要です。 使用状況は順番に適用され、最初の使用で一致が見つかった場合は、他の使用法は評価されません。 "国際" PSTN 使用量は、"米国およびカナダ" PSTN の使用の後に配置する必要があります。 PSTN の使用順序を変更するには、コマンドを実行し `Set-CSOnlineVoiceRoutingPolicy` ます。 <br/>たとえば、"US" と "カナダ" の順序を "第 1" と "海外" の順に変更するには、次のようにします。<br/> `Set-CsOnlineVoiceRoutingPolicy -id tag:"no Restrictions" -OnlinePstnUsages @{Replace="International", "US and Canada"}`
 > - "Other + 1" と "海外" のボイスルートの優先度は、自動的に割り当てられます。 "Redmond 1" と "レドモンド 2" よりも優先順位が低い場合は、問題ありません。

## <a name="example-2-configuration-steps"></a>例 2: 構成手順

次の例は、次の方法を示しています。

1. 「国際」と呼ばれる新しい PSTN 使用法を作成します。
2. 国際通話と呼ばれる新しいボイスルートを作成します。
3. 制限なしと呼ばれる音声ルーティングポリシーを作成します。
4. ユーザー John 森にポリシーを割り当てます。

[Microsoft Teams 管理センター](#admincenterexample2)または[PowerShell](#powershellexample2)を使用して、次の手順を実行できます。

### <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターの使用
<a name="admincenterexample2"></a>

#### <a name="step-1-create-the-international-pstn-usage"></a>手順 1: "国際" PSTN 使用量を作成する

1. Microsoft Teams 管理センターの左のナビゲーションで、[**音声**  >  の **直接ルーティング**] に移動し、右上隅の [ **PSTN 使用状況レコードの管理**] を選びます。
2. [ **追加**] をクリックし、[ **国際**] と入力して、[ **適用**] をクリックします。

#### <a name="step-2-create-the-international-voice-route"></a>手順 2: "国際" ボイスルーティングを作成する

1. Microsoft Teams 管理センターの左のナビゲーションで、[**音声** の直接ルーティング] に移動し、  >  **Direct Routing**[**ボイス** ルーティング] タブを選択します。
2. [ **追加**] をクリックし、名前として「国際」と入力して、説明を追加します。
3. 優先度を4に設定して、ダイヤルされた番号のパターンを \d + に設定します。
4. [ **Sbcs 登録 (オプション)**] で [ **sbcs の追加**] をクリックし、[sbc2.contoso.biz] と [sbc5.contoso.biz] を選択して、[ **適用**] をクリックします。
5. [ **Pstn 使用状況レコード] (オプション)** で、[ **pstn 使用量の追加**] をクリックし、"国際" pstn 使用状況レコードを選択して、[ **適用**] をクリックします。
6. [**保存**] をクリックします。

#### <a name="step-3-create-a-voice-routing-policy-named-no-restrictions-and-add-the-us-and-canada-and-international-pstn-usages-to-the-policy"></a>手順 3: "制限なし" という名前の音声ルーティングポリシーを作成し、"US and カナダ" と "国際" PSTN の使用をポリシーに追加する

PSTN の使用状況 "US とカナダ" は、電話番号 "+ 1 425 XXX XX XX" と "+ 1 206 XXX XX XX" への通話に対する特別な処理を、ローカルまたはオンプレミスの通話として維持するために、この音声ルーティングポリシーで再利用されます。

1. Microsoft Teams 管理センターの左のナビゲーションで、[**音声**  >  **音声ルーティングポリシー**] に移動し、[**追加**] をクリックします。
2. 名前として「 **制限なし** 」と入力し、説明を追加します。
3. [ **Pstn 使用状況レコード**] の [ **pstn 使用量の追加**] をクリックし、"米国およびカナダ" の pstn 利用状況レコードを選択し、[国際] pstn 使用状況レコードを選択します。 [**適用**] をクリックします。

    PSTN の使用順序に注意してください。

    - この例で使用されているように、通話が "+ 1 425 XXX XX XX" に設定されている場合、通話は "US とカナダ" の使用に設定され、特殊なルーティングロジックが適用されます。 つまり、sbc1.contoso.biz と sbc2.contoso.biz を使用して通話がルーティングされ、次にバックアップルートとして sbc3.contoso.biz と sbc4.contoso.biz が送信されます。

    - "国際" という PSTN の使用が "US とカナダ" よりも前にある場合は、ルーティングロジックの一部として、+ 1 425 XXX XX XX への通話が sbc2.contoso.biz と sbc5.contoso.biz にルーティングされます。

4. [**保存**] をクリックします。

詳細については、「 [ボイスルーティングポリシーを管理](manage-voice-routing-policies.md)する」を参照してください。

#### <a name="step-4-assign-the-voice-routing-policy-to-a-user-named-john-woods"></a>手順 4: John 森という名前のユーザーにボイスルーティングポリシーを割り当てる

1. Microsoft Teams 管理センターの左側のナビゲーションで、**[ユーザー]** に移動してユーザーをクリックします。
2. **[ポリシー]** をクリックし、**[割り当てられたポリシー]** の横にある **[編集]** をクリックします。
3. [ **音声ルーティングポリシー**] で、[制限なし] ポリシーを選択し、[ **保存**] をクリックします。

結果として、John 森の通話に適用されるボイスポリシーは無制限であり、米国、カナダ、国際通話で利用可能な通話ルーティングのロジックに従っていることになります。

### <a name="using-powershell"></a>PowerShell の使用
<a name="powershellexample2"></a>

#### <a name="step-1-create-the-international-pstn-usage"></a>手順 1: "国際" PSTN 使用量を作成する

Skype for Business Online のリモート PowerShell セッションで、次のように入力します。

```PowerShell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="International"}
```

#### <a name="step-2--create-a-new-voice-route-named-international"></a>手順 2: "インターナショナル" という名前の新しいボイスルートを作成する

```PowerShell
New-CsOnlineVoiceRoute -Identity "International" -NumberPattern ".*" -OnlinePstnGatewayList sbc2.contoso.biz, sbc5.contoso.biz -OnlinePstnUsages "International"
```
戻り値:

<pre>
Identity                  : International
Priority                  : 5
Description               :
NumberPattern             : .*
OnlinePstnUsages          : {International}
OnlinePstnGatewayList     : {sbc2.contoso.biz, sbc5.contoso.biz}
Name                      : International
</pre>

#### <a name="step-3-create-a-voice-routing-policy-named-no-restrictions"></a>手順 3: "制限なし" という名前の音声ルーティングポリシーを作成する

PSTN の利用状況 "レドモンド 1" と "Redmond" は、電話番号 "+ 1 425 XXX XX XX" と "+ 1 206 XXX XX XX" への通話に対する特別な処理を、ローカルまたはオンプレミスの通話として維持するために、この音声ルーティングポリシーで再利用されています。

  ```PowerShell
  New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"
  ```

PSTN の使用順序に注意してください。

  - 次の例のように、利用状況を設定して、"+ 1 425 XXX XX XX" という数値を指定した場合は、通話は "US およびカナダ" の使用に設定され、特殊なルーティングロジックが適用されます。 つまり、sbc1.contoso.biz と sbc2.contoso.biz を使用して通話がルーティングされ、次にバックアップルートとして sbc3.contoso.biz と sbc4.contoso.biz が送信されます。

  - "国際" という PSTN の使用が "US とカナダ" よりも前にある場合は、ルーティングロジックの一部として、+ 1 425 XXX XX XX への通話が sbc2.contoso.biz と sbc5.contoso.biz にルーティングされます。 コマンドを入力します。

  ```PowerShell
  New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"
  ```

戻り値:

    <pre>
    Identity              : International 
    OnlinePstnUsages : {US and Canada, International}     
    Description         :  
    RouteType               : BYOT
    </pre>

#### <a name="step-4-assign-the-voice-routing-policy-to-the-user-named-john-woods"></a>手順 4: John 森という名前のユーザーに音声ルーティングポリシーを割り当てる

```PowerShell
Grant-CsOnlineVoiceRoutingPolicy -Identity "John Woods" -PolicyName "No Restrictions"
```

次に、コマンドを使用して課題を確認します。 

```PowerShell
Get-CsOnlineUser "John Woods" | Select OnlineVoiceRoutingPolicy
```

戻り値:

<pre>
OnlineVoiceRoutingPolicy
------------------------
No Restrictions
</pre>

結果として、John 森の通話に適用されるボイスポリシーは無制限であり、米国、カナダ、国際通話で利用可能な通話ルーティングのロジックに従うことになります。

## <a name="see-also"></a>関連項目

[ダイレクト ルーティングを計画する](direct-routing-plan.md)

[ダイレクト ルーティングを構成する](direct-routing-configure.md)
