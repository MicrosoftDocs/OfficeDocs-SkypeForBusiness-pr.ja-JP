---
title: ダイレクト ルーティングの呼び出しルーティングを構成する
ms.reviewer: ''
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
description: Microsoft Direct Routing を使用して通話ルーティングを構成する方法について説明します。
ms.openlocfilehash: 919b98d6c8c8ee5a1af08967dc55c30748af37f1
ms.sourcegitcommit: 4095a1d5e507ac5cb23ed17611c1fbd4b744b23f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/13/2021
ms.locfileid: "61420157"
---
# <a name="configure-call-routing-for-direct-routing"></a>ダイレクト ルーティングの呼び出しルーティングを構成する

この記事では、ダイレクト ルーティングの呼び出しルーティングを構成する方法について説明します。 これは、ダイレクト ルーティングを構成するための次の手順の手順 3 です。

- 手順 1. [Microsoft 電話 System を使用して SBC をConnectし、接続を検証する](direct-routing-connect-the-sbc.md) 
- 手順 2. [ダイレクト ルーティング、音声、ボイスメールのユーザーを有効にする](direct-routing-enable-users.md)
- **手順 3.通話ルーティングの構成** (この記事)
- 手順 4. [数値を別の形式に変換する](direct-routing-translate-numbers.md) 

ダイレクト ルーティングの設定に必要なすべての手順については、「ダイレクト ルーティングの [構成」を参照してください](direct-routing-configure.md)。

## <a name="call-routing-overview"></a>通話ルーティングの概要

Microsoft 電話 システムには、次に基づいて特定のセッション ボーダー コントローラー (SBC) に呼び出しを送信できるルーティング メカニズムがあります。 

- 呼び出された番号パターン 
- 着信番号パターンと呼び出しを行う特定のユーザー
 
SBC は、アクティブおよびバックアップとして指定できます。 アクティブとして構成された SBC が特定の呼び出しルートで使用できない場合、呼び出しはバックアップ SBC にルーティングされます。
 
呼び出しルーティングは、次の要素で構成されます。 

- **通話ルーティング ポリシー** – 音声ルーティング ポリシーとも呼ばれます。 PSTN 使用法用のコンテナー。ユーザーまたは複数のユーザーに割り当てることができます。 

- **PSTN 使用法** – 音声ルートと PSTN 使用法用のコンテナーで、さまざまな音声ルーティング ポリシーで共有できます。 

- **音声ルート** – 発信番号がパターンと一致する通話に使用する、番号パターンと一連のオンライン PSTN ゲートウェイ。

- **オンライン PSTN ゲートウェイ** - 転送 P アサート ID (PAI) や優先コーデックなど、SBC を介して呼び出しが行われるときに適用される構成も格納する SBC へのポインター。は音声ルートに追加できます。

## <a name="voice-routing-policy-considerations"></a>音声ルーティング ポリシーに関する考慮事項

ユーザーが通話プラン ライセンスを持っている場合、そのユーザーの発信通話は、Microsoft 通話プラン PSTN インフラストラクチャを介して自動的にルーティングされます。 通話プラン ユーザーにオンライン音声ルーティング ポリシーを構成して割り当てる場合、そのユーザーの発信通話がチェックされ、ダイヤルされた番号がオンライン音声ルーティング ポリシーで定義されている番号パターンと一致するかどうかを判断します。 一致する場合は、ダイレクト ルーティング トランク経由で呼び出しがルーティングされます。 一致しない場合、通話は通話プラン PSTN インフラストラクチャ経由でルーティングされます。

> [!CAUTION]
> グローバル (組織全体の既定) のオンライン音声ルーティング ポリシーを構成して適用すると、組織内のすべての音声が有効なユーザーがそのポリシーを継承し、プランの呼び出しユーザーからの PSTN 通話が誤ってダイレクト ルーティング トランクにルーティングされる可能性があります。 すべてのユーザーにグローバル なオンライン音声ルーティング ポリシーを使用させたくない場合は、カスタム オンライン音声ルーティング ポリシーを構成し、個々の音声対応ユーザーに割り当てます。

## <a name="example-1-voice-routing-with-one-pstn-usage"></a>例 1: 1 つの PSTN 使用法を使用した音声ルーティング

次の図は、通話フロー内の音声ルーティング ポリシーの 2 つの例を示しています。

**Flow 1 (左側):** ユーザーが +1 425 XXX XX XX または +1 206 XXX XX XX を呼び出すと、呼び出しは SBC sbc1.contoso.biz または sbc2.contoso.biz にルーティングされます。 sbc1.contoso.biz も sbc2.contoso.biz も使用できない場合、呼び出しは破棄されます。 

**Flow 2 を呼び出す (右側):** ユーザーが +1 425 XXX XX XX または +1 206 XXX XX XX を呼び出した場合、呼び出しは最初に SBC sbc1.contoso.biz または sbc2.contoso.biz にルーティングされます。 どちらの SBC も使用できない場合は、優先度の低いルートが試行されます (sbc3.contoso.biz と sbc4.contoso.biz)。 使用可能な SBC がない場合、呼び出しは削除されます。 

![音声ルーティング ポリシーの例を示します。](media/ConfigDirectRouting-VoiceRoutingPolicyExamples.png)

どちらの例でも、音声ルートには優先順位が割り当てられますが、ルート内の SBC はランダムな順序で試行されます。

  > [!NOTE]
  > ユーザーに Microsoft 通話プランライセンスがない限り、構成例のパターン +1 425 XXX XX XX または +1 206 XXX XX XX に一致する番号を除く任意の番号への呼び出しは削除されます。 ユーザーが通話プラン ライセンスを持っている場合、通話は Microsoft 通話プランのポリシーに従って自動的にルーティングされます。 Microsoft 通話プランは、Microsoft 通話プラン ライセンスを持つすべてのユーザーに対する最後のルートとして自動的に適用され、追加の通話ルーティング構成は必要ありません。

次の図に示す例では、音声ルートが追加され、他のすべての米国およびカナダの番号に呼び出しが送信されます (着信番号パターン +1 XXX XXX XX XX XX に移動する呼び出し)。

![3 番目のルートを持つ音声ルーティング ポリシーを表示します。](media/ConfigDirectRouting-VoiceRoutingPolicywith3rdroute.png)

他のすべての呼び出しでは、ユーザーが両方のライセンス (Microsoft 電話 システムと Microsoft 通話プラン) を持っている場合は、自動ルートが使用されます。 管理者が作成したオンライン音声ルートの番号パターンと一致するものがない場合、通話は Microsoft 通話プランを介してルーティングされます。 ユーザーにシステムMicrosoft 電話しかない場合は、一致するルールが使用できないため、呼び出しは破棄されます。

  > [!NOTE]
  > この場合、ルート "Other +1" の優先度の値は関係ありません。これは、パターン +1 XXX XXX XX XX に一致するルートが 1 つだけであるためです。 ユーザーが +1 324 567 89 89 への呼び出しを行い、sbc5.contoso.biz と sbc6.contoso.biz の両方が使用できない場合、呼び出しは削除されます。

次の表に、3 つの音声ルートを使用した構成の概要を示します。 この例では、3 つのルートはすべて、同じ PSTN 使用法である "米国とカナダ" の一部です。  すべてのルートは "米国とカナダ" の PSTN 使用法に関連付けられ、PSTN の使用法は "US のみ" 音声ルーティング ポリシーに関連付けられます。

|**PSTN 使用法**|**音声ルート**|**番号パターン**|**Priority**|**SBC**|**説明**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|米国とカナダ|"Redmond 1"|^\\+1(425206\|)(\d{7})$|1|sbc1.contoso.biz<br/>sbc2.contoso.biz|着信番号 +1 425 XXX XX XX または +1 206 XXX XX XX のアクティブ ルート|
|米国とカナダ|"Redmond 2"|^\\+1(425206\|)(\d{7})$|2|sbc3.contoso.biz<br/>sbc4.contoso.biz|着信番号 +1 425 XXX XX XX または +1 206 XXX XX XX のバックアップ ルート|
|米国とカナダ|"その他の +1"|^\\+1(\d{10})$|3|sbc5.contoso.biz<br/>sbc6.contoso.biz|着信番号のルート +1 XXX XXX XX XX (+1 425 XXX XX XX または +1 206 XXX XX XX を除く)|
|||||||

## <a name="example-1-configuration-steps"></a>例 1: 構成手順

次の例は、次の方法を示しています。

1. 1 つの PSTN 使用法を作成します。
2. 3 つの音声ルートを構成します。
3. 音声ルーティング ポリシーを作成します。
4. Spencer Low という名前のユーザーにポリシーを割り当てます。

[Microsoft Teams管理センター](#admincenterexample1)または [PowerShell](#powershellexample1) を使用して、これらの手順を実行できます。

### <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターの使用
<a name="admincenterexample1"></a>

#### <a name="step-1-create-the-us-and-canada-pstn-usage"></a>手順 1: "米国とカナダ" の PSTN 使用法を作成する

1. Microsoft Teams管理センターの左側のナビゲーションで **、****VoiceDirect** >  ルーティングに移動し、右上隅にある [**PSTN 使用法レコードの管理**] を選択します。
2. [ **追加]** をクリック **し、「米国」と「カナダ」と** 入力して、[ **適用**] をクリックします。

#### <a name="step-2-create-three-voice-routes-redmond-1-redmond-2-and-other-1"></a>手順 2: 3 つの音声ルート (Redmond 1、Redmond 2、およびその他の +1) を作成する

次の手順では、音声ルートを作成する方法について説明します。 前の表で説明した設定を使用して、この例の Redmond 1、Redmond 2、およびその他の +1 という 3 つの音声ルートを作成するには、次の手順に従います。

1. Microsoft Teams管理センターの左側のナビゲーションで、**VoiceDirect** >  ルーティングに移動し、[**音声ルート**] タブを選択します。
2. [ **追加]** をクリックし、音声ルートの名前と説明を入力します。
3. 優先度を設定し、ダイヤルされた番号パターンを指定します。
4. 音声ルートを使用して SBC を登録するには、[ **SBC が登録されている (省略可能)]** の [ **SBC の追加**] をクリックし、登録する SBC を選択して、[ **適用**] をクリックします。
5. PSTN 使用法レコードを追加するには、[ **PSTN 使用法レコード (省略可能)]** の [ **PSTN 使用法の追加**] をクリックし、追加する PSTN レコードを選択し、[ **適用**] をクリックします。
6. **[保存]** をクリックします。

#### <a name="step-3-create-a-voice-routing-policy-named-us-only-and-add-the-us-and-canada-pstn-usage-to-the-policy"></a>手順 3: "US Only" という名前の音声ルーティング ポリシーを作成し、"US とカナダ" の PSTN 使用法をポリシーに追加する

1. Microsoft Teams管理センターの左側のナビゲーションで、**VoiceVoice** >  **ルーティング ポリシー** に移動し、[**追加**] をクリックします。
2. 名前として **「US のみ** 」と入力し、説明を追加します。
3. **[PSTN 使用法レコード**] の [**PSTN 使用法の追加**] をクリックし、[米国とカナダ] の PSTN 使用法レコードを選択して、[**適用**] をクリックします。
4. **[保存]** をクリックします。

詳細については、「 [音声ルーティング ポリシーの管理](manage-voice-routing-policies.md)」を参照してください。

#### <a name="step-4-assign-the-voice-routing-policy-to-a-user-named-spencer-low"></a>手順 4: 音声ルーティング ポリシーを Spencer Low という名前のユーザーに割り当てる

1. Microsoft Teams 管理センターの左側のナビゲーションで、**[ユーザー]** に移動してユーザーをクリックします。
2. **[ポリシー]** をクリックし、**[割り当てられたポリシー]** の横にある **[編集]** をクリックします。
3. **[音声ルーティング ポリシー**] で [US のみ] ポリシーを選択し、[**保存**] をクリックします。

詳細については、「 [音声ルーティング ポリシーの管理](manage-voice-routing-policies.md)」を参照してください。

### <a name="using-powershell"></a>PowerShell の使用
<a name="powershellexample1"></a>


#### <a name="step-1-create-the-us-and-canada-pstn-usage"></a>手順 1: "米国とカナダ" の PSTN 使用法を作成する

Skype for Business Online のリモート PowerShell セッションで、次のように入力します。

```PowerShell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="US and Canada"}
```

次のように入力して、使用状況が作成されたことを確認します。

```PowerShell
Get-CSOnlinePSTNUsage
``` 

切り捨てられる可能性のある名前の一覧を返します。

```console
Identity    : Global
Usage        : {testusage, US and Canada, International, karlUsage. . .}
```

次の例は、PowerShell コマンドを実行して完全な名前を表示した `(Get-CSOnlinePSTNUsage).usage` 結果を示しています (切り捨てられません)。

```console
 testusage
 US and Canada
 International
 karlUsage
 New test env
 Tallinn Lab Sonus
 karlUsage2
 Unrestricted
 Two trunks
```

#### <a name="step-2-create-three-voice-routes-redmond-1-redmond-2-and-other-1"></a>手順 2: 3 つの音声ルート (Redmond 1、Redmond 2、およびその他の +1) を作成する

"Redmond 1" ルートを作成するには、Skype for Business Online の PowerShell セッションで次のように入力します。

```PowerShell
New-CsOnlineVoiceRoute -Identity "Redmond 1" -NumberPattern "^\+1(425|206)
(\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```

次の値が返されます。

```console
Identity                : Redmond 1
Priority                : 1
Description             :
NumberPattern           : ^\+1(425|206) (\d{7})$
OnlinePstnUsages        : {US and Canada}
OnlinePstnGatewayList   : {sbc1.contoso.biz, sbc2.contoso.biz}
Name                    : Redmond 1
```

Redmond 2 ルートを作成するには、次のように入力します。

```PowerShell
New-CsOnlineVoiceRoute -Identity "Redmond 2" -NumberPattern "^\+1(425|206)
(\d{7})$" -OnlinePstnGatewayList sbc3.contoso.biz, sbc4.contoso.biz -Priority 2 -OnlinePstnUsages "US and Canada"
```

その他の +1 ルートを作成するには、次のように入力します。

```PowerShell
New-CsOnlineVoiceRoute -Identity "Other +1" -NumberPattern "^\+1(\d{10})$"
-OnlinePstnGatewayList sbc5.contoso.biz, sbc6.contoso.biz -OnlinePstnUsages "US and Canada"
```

  > [!CAUTION]
  > NumberPattern 属性の正規表現が有効な式であることを確認します。 この Web サイトを使用してテストできます。 [https://www.regexpal.com](https://www.regexpal.com)

場合によっては、すべての呼び出しを同じ SBC にルーティングする必要があります。use -NumberPattern ".*"

すべての呼び出しを同じ SBC にルーティングします。

```PowerShell
Set-CsOnlineVoiceRoute -id "Redmond 1" -NumberPattern ".*" -OnlinePstnGatewayList sbc1.contoso.biz
```

次に示すように、オプションを使用して PowerShell コマンドを実行して、ルートが `Get-CSOnlineVoiceRoute` 正しく構成されていることを確認します。

```PowerShell
Get-CsOnlineVoiceRoute | Where-Object {($_.priority -eq 1) -or ($_.priority -eq 2) or ($_.priority -eq 4) -Identity "Redmond 1" -NumberPattern "^\+1(425|206) (\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```
次の値を返す必要があります。

```console
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
```

この例では、ルート "Other +1" に優先度 4 が自動的に割り当てられました。 

#### <a name="step-3-create-a-voice-routing-policy-named-us-only-and-add-the-us-and-canada-pstn-usage-to-the-policy"></a>手順 3: "US Only" という名前の音声ルーティング ポリシーを作成し、"US とカナダ" の PSTN 使用法をポリシーに追加する

Skype for Business Online の PowerShell セッションで、次のように入力します。

```PowerShell
New-CsOnlineVoiceRoutingPolicy "US Only" -OnlinePstnUsages "US and Canada"
```

結果を次の例に示します。

```console
Identity            : Tag:US only
OnlinePstnUsages    : {US and Canada}
Description         :
RouteType           : BYOT
```

#### <a name="step-4-assign-the-voice-routing-policy-to-a-user-named-spencer-low"></a>手順 4: 音声ルーティング ポリシーを Spencer Low という名前のユーザーに割り当てる

Skype for Business Online の PowerShell セッションで、次のように入力します。

```PowerShell
Grant-CsOnlineVoiceRoutingPolicy -Identity "Spencer Low" -PolicyName "US Only"
```

次のコマンドを入力して、ポリシーの割り当てを検証します。

```PowerShell
Get-CsOnlineUser "Spencer Low" | select OnlineVoiceRoutingPolicy
```

このコマンドは、次を返します。

```console
OnlineVoiceRoutingPolicy
---------------------
US Only
```

## <a name="example-2-voice-routing-with-multiple-pstn-usages"></a>例 2: 複数の PSTN 使用法を使用する音声ルーティング

例 1 で作成した音声ルーティング ポリシーでは、Microsoft 通話プランライセンスもユーザーに割り当てられていない限り、米国とカナダの電話番号への通話のみが許可されます。

次の例では、"制限なし" 音声ルーティング ポリシーを作成できます。 このポリシーでは、例 1 で作成した "米国とカナダ" の PSTN 使用法と、新しい "国際" PSTN 使用法が再利用されます。 このポリシーは、他のすべての呼び出しを SBC sbc2.contoso.biz および sbc5.contoso.biz にルーティングします。

次に示す例では、米国のみポリシーをユーザー Spencer Low に割り当て、ユーザー John Woods に制限なしポリシーを割り当てて、ルーティングを次のように行います。

- Spencer Low – US Only policy。  通話は米国とカナダの番号にのみ許可されます。 Redmond 番号範囲を呼び出す場合は、特定の SBC のセットを使用する必要があります。 通話プランライセンスがユーザーに割り当てられていない限り、米国以外の番号はルーティングされません。

- John Woods – 国際ポリシー。  任意の番号への呼び出しが許可されます。 Redmond 番号範囲を呼び出す場合は、特定の SBC のセットを使用する必要があります。 米国以外の番号は、sbc2.contoso.biz と sbc5.contoso.biz を使用してルーティングされます。

![ユーザー Spencer Low に割り当てられた音声ルーティング ポリシーを表示します。](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoSpencerLow.png)

その他のすべての呼び出しでは、ユーザーが両方のライセンス (Microsoft 電話 System プランと Microsoft 通話プラン) を持っている場合は、自動ルートが使用されます。 管理者が作成したオンライン音声ルートの番号パターンと一致するものがない場合、通話は Microsoft 通話プランを使用してルーティングされます。  ユーザーにシステムMicrosoft 電話しかない場合は、一致するルールが使用できないため、呼び出しは破棄されます。

![ユーザー John Woods に割り当てられた音声ルーティング ポリシーを表示します。](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoJohnWoods.png)

次の表に、ルーティング ポリシー "制限なし" の使用指定と音声ルートの概要を示します。 

| PSTN 使用法 | 音声ルート | 番号のパターン | Priority | SBC | 説明 |
|:-----|:-----|:-----|:-----|:-----|:-----|
|米国とカナダ|"Redmond 1"|^\\+1(425206\|)(\d{7})$|1|sbc1.contoso.biz<br/>sbc2.contoso.biz|呼び出し先番号のアクティブ ルート +1 425 XXX XX XX または +1 206 XXX XX XX|
|米国とカナダ|"Redmond 2"|^\\+1(425206\|)(\d{7})$|2|sbc3.contoso.biz<br/>sbc4.contoso.biz|呼び出し先番号のバックアップ ルート +1 425 XXX XX XX または +1 206 XXX XX XX|
|米国とカナダ|"その他の +1"|^\\+1(\d{10})$|3|sbc5.contoso.biz<br/>sbc6.contoso.biz|呼び出し先番号のルート +1 XXX XXX XX XX (+1 425 XXX XX XX または +1 206 XXX XX XX を除く)|
|International|International|\d+|4|sbc2.contoso.biz<br/>sbc5.contoso.biz|任意の数値パターンのルート |

  > [!NOTE]
  > - 音声ルーティング ポリシーでの PSTN 使用法の順序は重要です。 使用法は順番に適用され、最初の使用法で一致するものが見つかった場合、他の使用状況は評価されません。 "国際" PSTN 使用法は、"米国とカナダ" の PSTN 使用法の後に配置する必要があります。 PSTN 使用法の順序を変更するには、コマンドを `Set-CSOnlineVoiceRoutingPolicy` 実行します。 <br/>たとえば、順序を "米国とカナダ" の 1 番目と 2 番目の "国際" から逆順の実行に変更するには、次のようにします。<br/> `Set-CsOnlineVoiceRoutingPolicy -id tag:"no Restrictions" -OnlinePstnUsages @{Replace="International", "US and Canada"}`
 > - "その他の +1" および "International" 音声ルートの優先度は自動的に割り当てられます。 "Redmond 1" や "Redmond 2" よりも優先順位が低い限り、それらは関係ありません。

## <a name="example-2-configuration-steps"></a>例 2: 構成手順

次の例は、次の方法を示しています。

1. International という新しい PSTN 使用法を作成します。
2. International という名前の新しい音声ルートを作成します。
3. 制限なしという音声ルーティング ポリシーを作成します。
4. ユーザー John Woods にポリシーを割り当てます。

[Microsoft Teams管理センター](#admincenterexample2)または [PowerShell](#powershellexample2) を使用して、これらの手順を実行できます。

### <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターの使用
<a name="admincenterexample2"></a>

#### <a name="step-1-create-the-international-pstn-usage"></a>手順 1: "International" PSTN 使用法を作成する

1. Microsoft Teams管理センターの左側のナビゲーションで **、****VoiceDirect** >  ルーティングに移動し、右上隅にある [**PSTN 使用法レコードの管理**] を選択します。
2. [ **追加]** をクリックし、「 **国際」** と入力して、[ **適用**] をクリックします。

#### <a name="step-2-create-the-international-voice-route"></a>手順 2: "International" 音声ルートを作成する

1. Microsoft Teams管理センターの左側のナビゲーションで、**VoiceDirect** >  ルーティングに移動し、[**音声ルート**] タブを選択します。
2. [ **追加]** をクリックし、名前として「International」と入力して、説明を追加します。
3. 優先度を 4 に設定し、ダイヤルされた番号パターンを \d+ に設定します。
4. [ **SBC の登録 (省略可能)]** で、[ **SBC の追加**] をクリックし、sbc2.contoso.biz と sbc5.contoso.biz を選択して、[ **適用**] をクリックします。
5. [ **PSTN 使用法レコード (省略可能)] で**、[ **PSTN 使用法の追加**] をクリックし、[国際] PSTN 使用法レコードを選択して、[ **適用**] をクリックします。
6. **[保存]** をクリックします。

#### <a name="step-3-create-a-voice-routing-policy-named-no-restrictions-and-add-the-us-and-canada-and-international-pstn-usages-to-the-policy"></a>手順 3: "制限なし" という名前の音声ルーティング ポリシーを作成し、"米国とカナダ" と "国際" の PSTN 使用法をポリシーに追加する

PSTN 使用法 "米国とカナダ" は、この音声ルーティング ポリシーで再利用され、番号 "+1 425 XXX XX XX" と "+1 206 XXX XX XX XX" をローカルまたはオンプレミスの呼び出しとして呼び出しの特別な処理を保持します。

1. Microsoft Teams管理センターの左側のナビゲーションで、**VoiceVoice** >  **ルーティング ポリシー** に移動し、[**追加**] をクリックします。
2. 名前に **「制限なし」** と入力し、説明を追加します。
3. [ **PSTN 使用法レコード**] で [ **PSTN 使用法の追加**] をクリックし、[米国とカナダ] の PSTN 使用法レコードを選択し、[国際] PSTN 使用法レコードを選択します。 [**適用**] をクリックします。

    PSTN 使用法の順序をメモしておきます。

    - この例のように構成された使用法で "+1 425 XXX XX XX" という番号を呼び出した場合、呼び出しは "米国とカナダ" の使用で設定されたルートに従い、特別なルーティング ロジックが適用されます。 つまり、呼び出しは最初に sbc1.contoso.biz と sbc2.contoso.biz を使用してルーティングされ、次にバックアップ ルートとして sbc3.contoso.biz および sbc4.contoso.biz されます。

    - "米国とカナダ" より前の "国際" PSTN 使用法の場合、+1 425 XXX XX XX への呼び出しは、ルーティング ロジックの一部として sbc2.contoso.biz および sbc5.contoso.biz にルーティングされます。

4. **[保存]** をクリックします。

詳細については、「 [音声ルーティング ポリシーの管理](manage-voice-routing-policies.md)」を参照してください。

#### <a name="step-4-assign-the-voice-routing-policy-to-a-user-named-john-woods"></a>手順 4: John Woods という名前のユーザーに音声ルーティング ポリシーを割り当てる

1. Microsoft Teams 管理センターの左側のナビゲーションで、**[ユーザー]** に移動してユーザーをクリックします。
2. **[ポリシー]** をクリックし、**[割り当てられたポリシー]** の横にある **[編集]** をクリックします。
3. **[音声ルーティング ポリシー**] で [制限なし] ポリシーを選択し、[**保存**] をクリックします。

その結果、John Woods の通話に適用される音声ポリシーは制限されず、米国、カナダ、および国際通話で使用できる通話ルーティングのロジックに従います。

### <a name="using-powershell"></a>PowerShell の使用
<a name="powershellexample2"></a>

#### <a name="step-1-create-the-international-pstn-usage"></a>手順 1: "International" PSTN 使用法を作成する

Skype for Business Online のリモート PowerShell セッションで、次のように入力します。

```PowerShell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="International"}
```

#### <a name="step-2--create-a-new-voice-route-named-international"></a>手順 2: "International" という名前の新しい音声ルートを作成する

```PowerShell
New-CsOnlineVoiceRoute -Identity "International" -NumberPattern ".*" -OnlinePstnGatewayList sbc2.contoso.biz, sbc5.contoso.biz -OnlinePstnUsages "International"
```

次の値が返されます。

```console
Identity                  : International
Priority                  : 5
Description               :
NumberPattern             : .*
OnlinePstnUsages          : {International}
OnlinePstnGatewayList     : {sbc2.contoso.biz, sbc5.contoso.biz}
Name                      : International
```

#### <a name="step-3-create-a-voice-routing-policy-named-no-restrictions"></a>手順 3: "制限なし" という名前の音声ルーティング ポリシーを作成する

PSTN 使用法 "Redmond 1" と "Redmond" は、この音声ルーティング ポリシーで再利用され、番号 "+1 425 XXX XX XX" と "+1 206 XXX XX XX XX" をローカルまたはオンプレミスの呼び出しとして呼び出しの特別な処理を保持します。

  ```PowerShell
  New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"
  ```

PSTN 使用法の順序をメモしておきます。

  - 次の例のように構成された使用法で "+1 425 XXX XX XX" という番号を呼び出した場合、呼び出しは "米国とカナダ" の使用で設定されたルートに従い、特別なルーティング ロジックが適用されます。 つまり、呼び出しは最初に sbc1.contoso.biz と sbc2.contoso.biz を使用してルーティングされ、次にバックアップ ルートとして sbc3.contoso.biz および sbc4.contoso.biz されます。

  - "米国とカナダ" より前の "国際" PSTN 使用法の場合、+1 425 XXX XX XX への呼び出しは、ルーティング ロジックの一部として sbc2.contoso.biz および sbc5.contoso.biz にルーティングされます。 コマンドを入力します。

  ```PowerShell
  New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"
  ```

次の値が返されます。

```console
    Identity              : International 
    OnlinePstnUsages : {US and Canada, International}     
    Description         :  
    RouteType               : BYOT
```

#### <a name="step-4-assign-the-voice-routing-policy-to-the-user-named-john-woods"></a>手順 4: John Woods という名前のユーザーに音声ルーティング ポリシーを割り当てる

```PowerShell
Grant-CsOnlineVoiceRoutingPolicy -Identity "John Woods" -PolicyName "No Restrictions"
```

次に、コマンドを使用して割り当てを確認します。 

```PowerShell
Get-CsOnlineUser "John Woods" | Select OnlineVoiceRoutingPolicy
```

次の値が返されます。

```console
OnlineVoiceRoutingPolicy
------------------------
No Restrictions
```

その結果、John Woods の通話に適用される音声ポリシーは制限されず、米国、カナダ、および国際通話で使用できる通話ルーティングのロジックに従います。

## <a name="run-a-self-diagnostics-tool"></a>自己診断ツールを実行する

管理者ユーザー Microsoft 365、テナント内で実行できる診断にアクセスして、ユーザーがダイレクト ルーティング用に正しく構成されていることを確認できます。 

> [!NOTE]
>この機能は、Microsoft 365政府機関、Microsoft 365 21Vianet、またはMicrosoft 365ドイツでは使用できません。

次のように、[テストの実行] を選択します。 これにより、Microsoft 365 管理 センターに診断が設定されます。
>> [!div class="nextstepaction"]
>> [テストの実行: ダイレクト ルーティングをTeamsする](https://aka.ms/TeamsDirectRoutingDiag)

診断では、さまざまな検証が実行されます。

## <a name="see-also"></a>関連項目

[ダイレクト ルーティングを計画する](direct-routing-plan.md)

[ダイレクト ルーティングを構成する](direct-routing-configure.md)
