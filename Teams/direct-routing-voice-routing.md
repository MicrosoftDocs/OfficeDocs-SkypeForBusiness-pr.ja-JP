---
title: ダイレクト ルーティングの音声ルーティングを構成する
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
description: システム ダイレクト ルーティングを使用して音声ルーティングをMicrosoft 電話する方法について説明します。
ms.openlocfilehash: 9330c3bf8200ed84fa9f7c534e794af887097b8d
ms.sourcegitcommit: 3fc6fb528806f967bdc80671761cd45c32db6516
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/26/2021
ms.locfileid: "51383981"
---
# <a name="configure-voice-routing-for-direct-routing"></a>ダイレクト ルーティングの音声ルーティングを構成する

この記事では、ダイレクト ルーティングの音声ルーティングを構成する電話システム説明します。  これは、ダイレクト ルーティングを構成するための次の手順の手順 3 です。

- 手順 1. [Connect システムを使用して SBC Microsoft 電話し、接続を検証する](direct-routing-connect-the-sbc.md) 
- 手順 2. [ダイレクト ルーティング、音声、ボイスメールのユーザーを有効にする](direct-routing-enable-users.md)
- **手順 3.音声ルーティングの構成** (この記事)
- 手順 4. [数値を別の形式に変換する](direct-routing-translate-numbers.md) 

ダイレクト ルーティングを設定するために必要なすべての手順については、「ダイレクト ルーティングの構成 [」を参照してください](direct-routing-configure.md)。

## <a name="voice-routing-overview"></a>音声ルーティングの概要

Microsoft 電話システムには、次に基づいて特定のセッション ボーダー コントローラー (SBC) に呼び出しを送信できるルーティング メカニズムがあります。 

- 呼び出された番号パターン 
- 呼び出された番号パターンに、呼び出しを行う特定のユーザーを加えたもの
 
SBC は、アクティブおよびバックアップとして指定できます。 アクティブとして構成されている SBC が特定の呼び出しルートで使用できない場合、呼び出しはバックアップ SBC にルーティングされます。
 
音声ルーティングは、次の要素で構成されます。 

- **音声ルーティング ポリシー** – PSTN 使用法のコンテナー。ユーザーまたは複数のユーザーに割り当てることができます。 

- **PSTN 使用法** – 音声ルートと PSTN 使用法のコンテナー。これは、さまざまな音声ルーティング ポリシーで共有できます。 

- **音声ルート** – 発信番号がパターンと一致する通話に使用する番号パターンとオンライン PSTN ゲートウェイのセット。

- **オンライン PSTN ゲートウェイ** - SBC を介して呼び出しが行った場合に適用される構成 (FORWARD P-Asserted-Identity (PSTN) や優先コーデックなど) を格納する SBC へのポインター。を音声ルートに追加できます。

## <a name="voice-routing-policy-considerations"></a>音声ルーティング ポリシーに関する考慮事項

ユーザーが通話プランライセンスを持っている場合、そのユーザーの発信通話は Microsoft 通話プラン PSTN インフラストラクチャを介して自動的にルーティングされます。 オンライン音声ルーティング ポリシーを構成して通話プランユーザーに割り当てる場合、そのユーザーの発信呼び出しがチェックされ、ダイヤルされた番号がオンライン音声ルーティング ポリシーで定義されている番号パターンと一致するかどうかを判断します。 一致する場合、呼び出しはダイレクト ルーティング トランクを介してルーティングされます。 一致しない場合、通話は通話プラン PSTN インフラストラクチャを介してルーティングされます。

> [!CAUTION]
> グローバル (組織全体の既定) オンライン音声ルーティング ポリシーを構成して適用した場合、組織内のすべての音声対応ユーザーは、そのポリシーを継承します。その結果、通話プランユーザーからの PSTN 通話が誤って直接ルーティング トランクにルーティングされる可能性があります。 すべてのユーザーがグローバル オンライン音声ルーティング ポリシーを使用しない場合は、カスタム オンライン音声ルーティング ポリシーを構成し、それを個々の音声対応ユーザーに割り当てる必要があります。

## <a name="example-1-voice-routing-with-one-pstn-usage"></a>例 1: 1 つの PSTN 使用法を使用した音声ルーティング

次の図は、通話フローにおける音声ルーティング ポリシーの 2 つの例を示しています。

**1 Flow (左側) を呼び出します。** ユーザーが +1 425 XXX XX XX または +1 206 XXX XX XX を呼び出した場合、呼び出しは SBC sbc1.contoso.biz または sbc2.contoso.biz にルーティングされます。 使用できる sbc1.contoso.biz も sbc2.contoso.biz 場合、呼び出しは破棄されます。 

**2 Flow (右側) を呼び出します。** ユーザーが +1 425 XXX XX XX または +1 206 XXX XX XX を呼び出した場合、呼び出しは最初に SBC sbc1.contoso.biz または sbc2.contoso.biz にルーティングされます。 どちらの SBC も使用できない場合は、優先順位の低いルートが試 sbc3.contoso.biz し、sbc4.contoso.biz。 使用できる SBC が存在しない場合、呼び出しは破棄されます。 

![音声ルーティング ポリシーの例を示す](media/ConfigDirectRouting-VoiceRoutingPolicyExamples.png)

どちらの例でも、音声ルートには優先順位が割り当てられますが、ルート内の SBC はランダムな順序で試されます。

  > [!NOTE]
  > ユーザーも Microsoft 通話プラン のライセンスを持たない限り、サンプル構成のパターン +1 425 XXX XX XX または +1 206 XXX XX XX に一致する番号を除く任意の番号を呼び出します。 ユーザーが通話プランのライセンスを持つ場合、通話は Microsoft 通話プランのポリシーに従って自動的にルーティングされます。 Microsoft 通話プランは、Microsoft 通話プラン ライセンスを持つすべてのユーザーに対する最後のルートとして自動的に適用され、追加の通話ルーティング構成は必要とされません。

次の図に示す例では、他のすべての米国およびカナダの番号に通話を送信する音声ルートが追加されています (番号パターン +1 XXX XXX XX XX という番号パターンに移動する呼び出し)。

![3 つ目のルートを含む音声ルーティング ポリシーを表示する](media/ConfigDirectRouting-VoiceRoutingPolicywith3rdroute.png)

その他のすべての呼び出しでは、ユーザーが両方のライセンス (Microsoft 電話 システムと Microsoft 通話プラン) を持つ場合は、自動ルートが使用されます。 管理者が作成したオンライン音声ルートの番号パターンと一致しない場合、通話は Microsoft 通話プランを介してルーティングされます。 ユーザーがシステムに対してMicrosoft 電話場合、一致する規則が利用できないので、呼び出しは破棄されます。

  > [!NOTE]
  > ルート "Other +1" の Priority 値は、パターン +1 XXX XXX XX XX に一致するルートが 1 つしか存在しないので、この場合は重要ではありません。 ユーザーが +1 324 567 89 89 を呼び出し、sbc5.contoso.biz と sbc6.contoso.biz の両方が使用できない場合、呼び出しは破棄されます。

次の表は、3 つの音声ルートを使用した構成の概要を示しています。 この例では、3 つのルートはすべて、同じ PSTN 使用法 "米国とカナダ" の一部です。  すべてのルートは "米国とカナダ" の PSTN 使用法に関連付けられているので、PSTN の使用は "米国のみ" の音声ルーティング ポリシーに関連付けされます。

|**PSTN 使用法**|**音声ルート**|**番号パターン**|**Priority**|**SBC**|**説明**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|米国とカナダ|"Redmond 1"|^\\+1(425 \| 206)(\d {7} )$|1|sbc1.contoso.biz<br/>sbc2.contoso.biz|呼び出し番号 +1 425 XXX XX XX または +1 206 XXX XX XX のアクティブ ルート|
|米国とカナダ|"Redmond 2"|^\\+1(425 \| 206)(\d {7} )$|2|sbc3.contoso.biz<br/>sbc4.contoso.biz|呼び出し番号のバックアップ ルート + 1 425 XXX XX XX または +1 206 XXX XX XX|
|米国とカナダ|"Other +1"|^\\+1(\d {10} )$|3|sbc5.contoso.biz<br/>sbc6.contoso.biz|呼び出された番号のルート +1 XXX XXX XX XX (+1 425 XXX XX XX または +1 206 XXX XX XX を除く)|
|||||||

## <a name="example-1-configuration-steps"></a>例 1: 構成手順

次の例は、次の方法を示しています。

1. 1 つの PSTN 使用法を作成します。
2. 3 つの音声ルートを構成します。
3. 音声ルーティング ポリシーを作成します。
4. Spencer Low というユーザーにポリシーを割り当てる。

管理センターまたは[PowerShell Microsoft Teamsを使用](#admincenterexample1)[して、これらの](#powershellexample1)手順を実行できます。

### <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターの使用
<a name="admincenterexample1"></a>

#### <a name="step-1-create-the-us-and-canada-pstn-usage"></a>手順 1: "米国とカナダ" PSTN の使用を作成する

1. Microsoft Teams 管理センターの左側のナビゲーションで、[音声ダイレクト ルーティング]に移動し、右上隅の [PSTN 使用レコードの管理]  >  **を選択します**。
2. [追加 **] をクリック** し **、「US」と「Canada」と入力し**、[適用] を **クリックします**。

#### <a name="step-2-create-three-voice-routes-redmond-1-redmond-2-and-other-1"></a>手順 2: 3 つの音声ルートを作成する (Redmond 1、Redmond 2、Other +1)

次の手順では、音声ルートを作成する方法について説明します。 前の表で説明した設定を使用して、この例では Redmond 1、Redmond 2、Other +1 という名前の 3 つの音声ルートを作成するには、次の手順を使用します。

1. 管理センターの左側のナビゲーションMicrosoft Teams [**音声ダイレクト** ルーティング] に移動し、[音声ルート]  >  **タブを選択** します。
2. [ **追加]** をクリックし、音声ルートの名前と説明を入力します。
3. 優先順位を設定し、ダイヤルされた番号パターンを指定します。
4. SBC を音声ルートに登録するには、[登録されている **SBC (省略可能)**] で **、[SBC** の追加] をクリックし、登録する SBC を選択し、[適用] を **クリックします**。
5. PSTN 使用レコードを追加するには、[PSTN 使用状況レコード **(省略可能)**] で **、[PSTN** 使用法の追加] をクリックし、追加する PSTN レコードを選択し、[適用] を **クリックします**。
6. **[保存]** をクリックします。

#### <a name="step-3-create-a-voice-routing-policy-named-us-only-and-add-the-us-and-canada-pstn-usage-to-the-policy"></a>手順 3: "米国のみ" という名前の音声ルーティング ポリシーを作成し、"米国とカナダ" の PSTN 使用法をポリシーに追加する

1. 管理センターの左側のナビゲーションMicrosoft Teams Voice Voiceルーティング ポリシー] に移動し、[  >  追加] を **クリックします**。
2. 名前 **として「US のみ** 」と入力し、説明を追加します。
3. [PSTN **使用状況レコード] の** **[PSTN** 使用法の追加] をクリックし、[米国とカナダ] PSTN 使用レコードを選択し、[適用] を **クリックします**。
4. **[保存]** をクリックします。

詳細については、「音声ルーティング ポリシー [の管理」を参照してください](manage-voice-routing-policies.md)。

#### <a name="step-4-assign-the-voice-routing-policy-to-a-user-named-spencer-low"></a>手順 4: Spencer Low というユーザーに音声ルーティング ポリシーを割り当てる

1. Microsoft Teams 管理センターの左側のナビゲーションで、**[ユーザー]** に移動してユーザーをクリックします。
2. **[ポリシー]** をクリックし、**[割り当てられたポリシー]** の横にある **[編集]** をクリックします。
3. [ **音声ルーティング ポリシー] で**、[米国のみ] ポリシーを選択し、[保存] を **クリックします**。

詳細については、「音声ルーティング ポリシー [の管理」を参照してください](manage-voice-routing-policies.md)。

### <a name="using-powershell"></a>PowerShell の使用
<a name="powershellexample1"></a>


#### <a name="step-1-create-the-us-and-canada-pstn-usage"></a>手順 1: "米国とカナダ" PSTN の使用を作成する

Skype for Business Online のリモート PowerShell セッションで、次Skype for Business入力します。

```PowerShell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="US and Canada"}
```

次を入力して、使用状況が作成されたと確認します。

```PowerShell
Get-CSOnlinePSTNUsage
``` 

切り捨てられる可能性がある名前の一覧を返します。

```console
Identity    : Global
Usage        : {testusage, US and Canada, International, karlUsage. . .}
```

次の例は、PowerShell コマンドを実行してフル ネームを表示 `(Get-CSOnlinePSTNUsage).usage` した結果を示しています (切り捨てはされません)。

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

#### <a name="step-2-create-three-voice-routes-redmond-1-redmond-2-and-other-1"></a>手順 2: 3 つの音声ルートを作成する (Redmond 1、Redmond 2、Other +1)

"Redmond 1" ルートを作成するには、Skype for Business Online の PowerShell セッションで次のコマンドを入力します。

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

Redmond 2 ルートを作成するには、次のコマンドを入力します。

```PowerShell
New-CsOnlineVoiceRoute -Identity "Redmond 2" -NumberPattern "^\+1(425|206)
(\d{7})$" -OnlinePstnGatewayList sbc3.contoso.biz, sbc4.contoso.biz -Priority 2 -OnlinePstnUsages "US and Canada"
```

[その他 + 1] ルートを作成するには、次のコマンドを入力します。

```PowerShell
New-CsOnlineVoiceRoute -Identity "Other +1" -NumberPattern "^\+1(\d{10})$"
-OnlinePstnGatewayList sbc5.contoso.biz, sbc6.contoso.biz -OnlinePstnUsages "US and Canada"
```

  > [!CAUTION]
  > NumberPattern 属性の正規表現が有効な式である必要があります。 この Web サイトを使用してテストできます。 [https://www.regexpal.com](https://www.regexpal.com)

場合によっては、すべての呼び出しを同じ SBC にルーティングする必要があります。use -NumberPattern ".*"

すべての呼び出しを同じ SBC にルーティングします。

```PowerShell
Set-CsOnlineVoiceRoute -id "Redmond 1" -NumberPattern ".*" -OnlinePstnGatewayList sbc1.contoso.biz
```

次に示すように、オプションを使用して PowerShell コマンドを実行して、ルートが正しく `Get-CSOnlineVoiceRoute` 構成されていることを確認します。

```PowerShell
Get-CsOnlineVoiceRoute | Where-Object {($_.priority -eq 1) -or ($_.priority -eq 2) or ($_.priority -eq 4) -Identity "Redmond 1" -NumberPattern "^\+1(425|206) (\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```
次の値が返されます。

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

この例では、ルート "Other +1" に優先度 4 が自動的に割り当て済みでした。 

#### <a name="step-3-create-a-voice-routing-policy-named-us-only-and-add-the-us-and-canada-pstn-usage-to-the-policy"></a>手順 3: "米国のみ" という名前の音声ルーティング ポリシーを作成し、"米国とカナダ" の PSTN 使用法をポリシーに追加する

Skype for Business Online の PowerShell セッションで、次Skype for Business入力します。

```PowerShell
New-CsOnlineVoiceRoutingPolicy "US Only" -OnlinePstnUsages "US and Canada"
```

結果は次の例に示されています。

```console
Identity            : Tag:US only
OnlinePstnUsages    : {US and Canada}
Description         :
RouteType           : BYOT
```

#### <a name="step-4-assign-the-voice-routing-policy-to-a-user-named-spencer-low"></a>手順 4: Spencer Low というユーザーに音声ルーティング ポリシーを割り当てる

Skype for Business Online の PowerShell セッションで、次Skype for Business入力します。

```PowerShell
Grant-CsOnlineVoiceRoutingPolicy -Identity "Spencer Low" -PolicyName "US Only"
```

次のコマンドを入力して、ポリシーの割り当てを検証します。

```PowerShell
Get-CsOnlineUser "Spencer Low" | select OnlineVoiceRoutingPolicy
```

コマンドは次を返します。

```console
OnlineVoiceRoutingPolicy
---------------------
US Only
```

## <a name="example-2-voice-routing-with-multiple-pstn-usages"></a>例 2: 複数の PSTN 使用法を使用した音声ルーティング

例 1 で作成した音声ルーティング ポリシーでは、Microsoft 通話プランのライセンスもユーザーに割り当てられていない限り、米国とカナダの電話番号への通話のみを許可します。

次の例では、"制限なし" 音声ルーティング ポリシーを作成できます。 このポリシーは、例 1 で作成した "米国とカナダ" の PSTN 使用法と、新しい "国際" PSTN 使用法を再利用します。 このポリシーは、他のすべての呼び出しを SBC にルーティングし、sbc2.contoso.biz を sbc5.contoso.biz。

次に示す例では、ルーティングが次のように行われるので、米国のみポリシーをユーザーの Spencer Low に割り当て、制限なしポリシーをユーザーの John Woods に割り当てるとします。

- スペンサー低 – 米国のみポリシー。  呼び出しは、米国およびカナダの番号にのみ許可されます。 Redmond 番号範囲を呼び出す場合は、特定の SBC セットを使用する必要があります。 通話プランのライセンスがユーザーに割り当てられていない限り、米国以外の番号はルーティングされません。

- John Woods – 国際ポリシー。  呼び出しは任意の数に対して許可されます。 Redmond 番号範囲を呼び出す場合は、特定の SBC セットを使用する必要があります。 米国以外の番号は、sbc2.contoso.biz と sbc5.contoso.biz を使用してルーティングされます。

![ユーザー Spencer Low に割り当てられている音声ルーティング ポリシーを示します](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoSpencerLow.png)

その他のすべての呼び出しでは、ユーザーが両方のライセンス (Microsoft 電話 システムと Microsoft 通話プラン) を持つ場合は、自動ルートが使用されます。 管理者が作成したオンライン音声ルートの番号パターンと一致しない場合、通話は Microsoft 通話プランを使用してルーティングされます。  ユーザーがシステムに対してMicrosoft 電話場合、一致する規則が使用できないので、呼び出しは破棄されます。

![ユーザー John Woods に割り当てられている音声ルーティング ポリシーを示します](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoJohnWoods.png)

次の表に、ルーティング ポリシー "制限なし" の使用指定と音声ルートの概要を示します。 

| PSTN 使用法 | 音声ルート | 番号のパターン | Priority | SBC | 説明 |
|:-----|:-----|:-----|:-----|:-----|:-----|
|米国とカナダ|"Redmond 1"|^\\+1(425 \| 206)(\d {7} )$|1|sbc1.contoso.biz<br/>sbc2.contoso.biz|呼び出し先番号のアクティブなルート + 1 425 XXX XX または +1 206 XXX XX XX|
|米国とカナダ|"Redmond 2"|^\\+1(425 \| 206)(\d {7} )$|2|sbc3.contoso.biz<br/>sbc4.contoso.biz|呼び出し先番号のバックアップ ルート + 1 425 XXX XX XX または +1 206 XXX XX XX|
|米国とカナダ|"Other +1"|^\\+1(\d {10} )$|3|sbc5.contoso.biz<br/>sbc6.contoso.biz|呼び出し先番号のルート +1 XXX XXX XX XX (+1 425 XXX XX XX または +1 206 XXX XX XX を除く)|
|International|International|\d+|4|sbc2.contoso.biz<br/>sbc5.contoso.biz|任意の番号パターンのルート |

  > [!NOTE]
  > - 音声ルーティング ポリシーでの PSTN の使用順序は重要です。 使用状況は順番に適用され、最初の使用状況で一致が見つかった場合、他の使用状況は評価されません。 "国際" PSTN の使用は、"米国およびカナダ" PSTN の使用後に配置する必要があります。 PSTN の使用状況の順序を変更するには、 コマンドを実行 `Set-CSOnlineVoiceRoutingPolicy` します。 <br/>たとえば、最初に "米国とカナダ" から 2 番目の "国際" から逆順の実行に順序を変更するには、次のコマンドを実行します。<br/> `Set-CsOnlineVoiceRoutingPolicy -id tag:"no Restrictions" -OnlinePstnUsages @{Replace="International", "US and Canada"}`
 > - "その他 +1" および "国際" 音声ルートの優先度が自動的に割り当てられます。 "Redmond 1" と "Redmond 2" よりも優先順位が低い限り、重要ではありません。

## <a name="example-2-configuration-steps"></a>例 2: 構成手順

次の例は、次の方法を示しています。

1. 国際と呼ばれる新しい PSTN 使用法を作成します。
2. International という名前の新しい音声ルートを作成します。
3. "制限なし" という音声ルーティング ポリシーを作成します。
4. ポリシーをユーザー John Woods に割り当てる。

管理センターまたは[PowerShell Microsoft Teamsを使用](#admincenterexample2)[して、これらの](#powershellexample2)手順を実行できます。

### <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターの使用
<a name="admincenterexample2"></a>

#### <a name="step-1-create-the-international-pstn-usage"></a>手順 1: "国際" PSTN 使用法を作成する

1. Microsoft Teams 管理センターの左側のナビゲーションで、[音声ダイレクト ルーティング]に移動し、右上隅の [PSTN 使用レコードの管理]  >  **を選択します**。
2. [追加 **] をクリック** し、「 **国際」と入力** し、[適用] を **クリックします**。

#### <a name="step-2-create-the-international-voice-route"></a>手順 2: "国際" 音声ルートを作成する

1. 管理センターの左側のナビゲーションMicrosoft Teams [**音声ダイレクト** ルーティング] に移動し、[音声ルート]  >  **タブを選択** します。
2. [ **追加]** をクリックし、名前として「International」と入力し、説明を追加します。
3. 優先順位を 4 に設定し、ダイヤルされた番号パターンを \d+ に設定します。
4. [ **登録されている SBC (省略可能)**] で **、[SBC** の追加] をクリックし、[sbc2.contoso.biz] を sbc5.contoso.biz し、[適用] を **クリックします**。
5. [PSTN **使用レコード (省略可能)**] で **、[PSTN** 使用法の追加] をクリックし、[国際] PSTN 使用レコードを選択し、[適用] を **クリックします**。
6. **[保存]** をクリックします。

#### <a name="step-3-create-a-voice-routing-policy-named-no-restrictions-and-add-the-us-and-canada-and-international-pstn-usages-to-the-policy"></a>手順 3: "制限なし" という名前の音声ルーティング ポリシーを作成し、"米国とカナダ" と "国際" の PSTN 使用法をポリシーに追加する

PSTN の使用 "米国とカナダ" は、この音声ルーティング ポリシーで再利用され、番号 "+1 425 XXX XX XX" および "+1 206 XXX XX XX" の呼び出しに対する特別な処理をローカルまたはオンプレミスの通話として保持します。

1. 管理センターの左側のナビゲーションMicrosoft Teams Voice Voiceルーティング ポリシー] に移動し、[  >  追加] を **クリックします**。
2. 名前 **として「制限なし** 」と入力し、説明を追加します。
3. **[PSTN 使用レコード**] の **[PSTN** 使用法の追加] をクリックし、[米国とカナダ] PSTN 使用レコードを選択し、[国際] PSTN 使用レコードを選択します。 [**適用**] をクリックします。

    PSTN の使用状況の順序をメモします。

    - この例のように構成された使用法で番号 "+1 425 XXX XX XX" を呼び出した場合、呼び出しは "米国とカナダ" で設定されたルートに従い、特殊なルーティング ロジックが適用されます。 つまり、最初に sbc1.contoso.biz と sbc2.contoso.biz を使用して呼び出しがルーティングされ、次 sbc3.contoso.biz バックアップ sbc4.contoso.biz としてルーティングされます。

    - "国際" PSTN の使用が "米国およびカナダ" より前の場合、+1 425 XXX XX XX の呼び出しはルーティング ロジックの一部として sbc2.contoso.biz および sbc5.contoso.biz にルーティングされます。

4. **[保存]** をクリックします。

詳細については、「音声ルーティング ポリシー [の管理」を参照してください](manage-voice-routing-policies.md)。

#### <a name="step-4-assign-the-voice-routing-policy-to-a-user-named-john-woods"></a>手順 4: John Woods というユーザーに音声ルーティング ポリシーを割り当てる

1. Microsoft Teams 管理センターの左側のナビゲーションで、**[ユーザー]** に移動してユーザーをクリックします。
2. **[ポリシー]** をクリックし、**[割り当てられたポリシー]** の横にある **[編集]** をクリックします。
3. [ **音声ルーティング ポリシー] で**、[制限なし] ポリシーを選択し、[保存] を **クリックします**。

その結果、John Woods の呼び出しに適用される音声ポリシーは無制限であり、米国、カナダ、および国際通話で使用できる通話ルーティングのロジックに従います。

### <a name="using-powershell"></a>PowerShell の使用
<a name="powershellexample2"></a>

#### <a name="step-1-create-the-international-pstn-usage"></a>手順 1: "国際" PSTN 使用法を作成する

Skype for Business Online のリモート PowerShell セッションで、次を入力します。

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

PSTN の使用法 "Redmond 1" と "Redmond" は、この音声ルーティング ポリシーで再利用され、番号 "+1 425 XXX XX XX" および "+1 206 XXX XX XX" の呼び出しに対する特別な処理をローカルまたはオンプレミスの通話として保持します。

  ```PowerShell
  New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"
  ```

PSTN の使用状況の順序をメモします。

  - 次の例に示す使用法が構成された番号 "+1 425 XXX XX XX" に対する呼び出しが行われた場合、呼び出しは "米国とカナダ" で設定されたルートに従い、特殊なルーティング ロジックが適用されます。 つまり、最初に sbc1.contoso.biz と sbc2.contoso.biz を使用して呼び出しがルーティングされ、次 sbc3.contoso.biz バックアップ sbc4.contoso.biz としてルーティングされます。

  - "国際" PSTN の使用が "米国およびカナダ" より前の場合、+1 425 XXX XX XX の呼び出しはルーティング ロジックの一部として sbc2.contoso.biz および sbc5.contoso.biz にルーティングされます。 コマンドを入力します。

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

次に、 コマンドを使用して割り当てを確認します。 

```PowerShell
Get-CsOnlineUser "John Woods" | Select OnlineVoiceRoutingPolicy
```

次の値が返されます。

```console
OnlineVoiceRoutingPolicy
------------------------
No Restrictions
```

その結果、John Woods の呼び出しに適用される音声ポリシーは無制限であり、米国、カナダ、および国際通話で使用できる通話ルーティングのロジックに従います。

## <a name="see-also"></a>関連項目

[ダイレクト ルーティングを計画する](direct-routing-plan.md)

[ダイレクト ルーティングを構成する](direct-routing-configure.md)
