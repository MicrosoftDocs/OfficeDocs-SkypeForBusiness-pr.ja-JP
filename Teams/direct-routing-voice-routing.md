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
description: Microsoft Phone System Direct Routing を使用して音声ルーティングを構成する方法について説明します。
ms.openlocfilehash: 9330c3bf8200ed84fa9f7c534e794af887097b8d
ms.sourcegitcommit: 3fc6fb528806f967bdc80671761cd45c32db6516
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/26/2021
ms.locfileid: "51383981"
---
# <a name="configure-voice-routing-for-direct-routing"></a>ダイレクト ルーティングの音声ルーティングを構成する

この記事では、電話システム ダイレクト ルーティングの音声ルーティングを構成する方法について説明します。  これは、ダイレクト ルーティングを構成するための次の手順の手順 3 です。

- 手順 1. [SBC を Microsoft Phone System に接続し、接続を検証する](direct-routing-connect-the-sbc.md) 
- 手順 2. [直接ルーティング、音声、ボイスメールのユーザーを有効にする](direct-routing-enable-users.md)
- **手順 3.音声ルーティングを構成** する (この記事)
- 手順 4. [数値を別の形式に翻訳する](direct-routing-translate-numbers.md) 

ダイレクト ルーティングを設定するために必要なすべての手順については、「ダイレクト ルーティングを構成する」を [参照してください](direct-routing-configure.md)。

## <a name="voice-routing-overview"></a>音声ルーティングの概要

Microsoft Phone System には、次に基づいて通話を特定のセッション ボーダー コントローラー (SBC) に送信できるルーティング メカニズムがあります。 

- 呼び出される番号パターン 
- 呼び出された番号パターンと、呼び出しを行う特定のユーザー
 
SPC はアクティブとバックアップとして指定できます。 アクティブとして構成されている SBC が特定の通話ルートで利用できない場合、通話はバックアップ SBC にルーティングされます。
 
音声ルーティングは、次の要素で構成されています。 

- **音声ルーティング ポリシー** – PSTN 使用状況のコンテナー。ユーザーまたは複数のユーザーに割り当てることができます。 

- **PSTN の使用状況** – 音声ルートと PSTN 使用状況のコンテナーです。これは、異なる音声ルーティング ポリシーで共有できます。 

- **音声ルート** – 発信番号がパターンに一致する通話に使用する番号パターンとオンライン PSTN ゲートウェイのセット。

- **オンライン PSTN ゲートウェイ** - SBC を介して呼び出しが実行された場合に適用される構成 (FORWARD P-Asserted-Identity (CODEC) や Preferred Codecs など) を格納する SBC へのポインター。を音声ルートに追加できます。

## <a name="voice-routing-policy-considerations"></a>音声ルーティング ポリシーに関する考慮事項

ユーザーが通話プラン のライセンスを持っている場合、そのユーザーの発信通話は Microsoft 通話プラン PSTN インフラストラクチャ経由で自動的にルーティングされます。 オンライン音声ルーティング ポリシーを構成して通話プラン ユーザーに割り当てると、そのユーザーの発信通話がチェックされ、ダイヤルされた番号がオンライン音声ルーティング ポリシーで定義されている番号パターンと一致するかどうかを確認します。 一致する場合、通話はダイレクト ルーティング トランクを介してルーティングされます。 一致する通話がない場合、通話は通話プラン PSTN インフラストラクチャを介してルーティングされます。

> [!CAUTION]
> グローバル (組織全体の既定) オンライン 音声ルーティング ポリシーを構成して適用すると、組織内のすべての音声対応ユーザーはポリシーを継承し、そのポリシーを継承すると、通話プランユーザーからの PSTN 通話が誤ってダイレクト ルーティング トランクにルーティングされる可能性があります。 すべてのユーザーがグローバル オンライン音声ルーティング ポリシーを使用しない場合は、カスタム オンライン 音声ルーティング ポリシーを構成し、個々の音声対応ユーザーに割り当てる必要があります。

## <a name="example-1-voice-routing-with-one-pstn-usage"></a>例 1: 1 つの PSTN 使用状況を使用した音声ルーティング

次の図は、コール フローでの音声ルーティング ポリシーの 2 つの例を示しています。

**コール フロー 1 (左側):** ユーザーが +1 425 XXX XX または +1 206 XXX XX XX を呼び出した場合、呼び出しは SBC sbc1.contoso.biz または sbc2.contoso.biz にルーティングされます。 使用できる sbc1.contoso.biz sbc2.contoso.biz、通話はドロップされます。 

**コール フロー 2 (右側):** ユーザーが +1 425 XXX XX または +1 206 XXX XX XX を呼び出した場合、呼び出しは最初に SBC sbc1.contoso.biz または sbc2.contoso.biz にルーティングされます。 どちらの SBC も利用できない場合は、優先度が低いルートが試 sbc3.contoso.biz が試 sbc4.contoso.biz。 使用できる SPC が存在しない場合、通話はドロップされます。 

![音声ルーティング ポリシーの例を示す](media/ConfigDirectRouting-VoiceRoutingPolicyExamples.png)

どちらの例でも、音声ルートには優先度が割り当てられますが、ルート内の SPC はランダムな順序で試されます。

  > [!NOTE]
  > ユーザーが Microsoft 通話プランのライセンスも持たない限り、例の構成でパターン +1 425 XXX XX XX または +1 206 XXX XX XX に一致する番号を除く任意の番号を呼び出します。 ユーザーが通話プランのライセンスを持つ場合、通話は Microsoft 通話プランのポリシーに従って自動的にルーティングされます。 Microsoft 通話プランは、Microsoft 通話プラン ライセンスを持つすべてのユーザーへの最後のルートとして自動的に適用され、追加の通話ルーティング構成は必要ない。

次の図に示す例では、米国およびカナダの他のすべての番号に通話を送信する音声ルートが追加されています (番号パターン +1 XXX XXX XX XX という呼び出しに移動する通話)。

![第 3 ルートでの音声ルーティング ポリシーの表示](media/ConfigDirectRouting-VoiceRoutingPolicywith3rdroute.png)

その他のすべての通話では、ユーザーが両方のライセンス (Microsoft 電話システムと Microsoft 通話プラン) を持つ場合は、自動ルートが使用されます。 管理者が作成したオンライン音声ルートの番号パターンに一致する番号が見当たらない場合、通話は Microsoft 通話プラン経由でルーティングされます。 ユーザーが Microsoft Phone System のみを持つ場合、照合ルールが利用できないので通話は削除されます。

  > [!NOTE]
  > ルート "Other +1" の Priority 値は、パターン +1 XXX XXX XX XX に一致するルートが 1 つしか存在しないので、この場合は問題ありません。 ユーザーが +1 324 567 89 89 に電話をかけ、sbc5.contoso.biz と sbc6.contoso.biz の両方が使用できない場合、通話は停止されます。

次の表は、3 つの音声ルートを使用した構成の概要です。 この例では、3 つのルートはすべて、同じ PSTN 使用状況 ("米国とカナダ") の一部です。  すべてのルートは "米国とカナダ" の PSTN 使用状況に関連付けられているので、PSTN の使用状況は "米国のみ" の音声ルーティング ポリシーに関連付けられている。

|**PSTN 使用法**|**音声ルート**|**番号パターン**|**[Priority]**|**SBC**|**説明**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|米国とカナダ|"Redmond 1"|^\\+1(425 \| 206)(\d {7} )$|1|sbc1.contoso.biz<br/>sbc2.contoso.biz|呼び出された番号のアクティブなルート +1 425 XXX XX または +1 206 XXX XX XX|
|米国とカナダ|"Redmond 2"|^\\+1(425 \| 206)(\d {7} )$|2|sbc3.contoso.biz<br/>sbc4.contoso.biz|呼び出された番号のバックアップ ルート +1 425 XXX XX または +1 206 XXX XX XX|
|米国とカナダ|"Other +1"|^\\+1(\d {10} )$|3|sbc5.contoso.biz<br/>sbc6.contoso.biz|呼び出された番号のルート +1 XXX XXX XX XX (+1 425 XXX XX または +1 206 XXX XX XX を除く)|
|||||||

## <a name="example-1-configuration-steps"></a>例 1: 構成手順

次の例は、次の方法を示しています。

1. 1 つの PSTN 使用状況を作成する。
2. 3 つの音声ルートを構成します。
3. 音声ルーティング ポリシーを作成します。
4. Spencer Low という名前のユーザーにポリシーを割り当てる。

Microsoft Teams 管理センターまたは [PowerShell](#admincenterexample1) を使用して [、これらの](#powershellexample1) 手順を実行できます。

### <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターの使用
<a name="admincenterexample1"></a>

#### <a name="step-1-create-the-us-and-canada-pstn-usage"></a>手順 1: "米国とカナダ" の PSTN 使用状況を作成する

1. Microsoft Teams 管理センターの左側のナビゲーションで、[音声ダイレクト ルーティング] に移動し、右上隅の [PSTN 使用状況レコードの管理] を  >  **選択します**。
2. [追加 **] を** クリックし、 **米国とカナダを入力して、[** 適用] を **クリックします**。

#### <a name="step-2-create-three-voice-routes-redmond-1-redmond-2-and-other-1"></a>手順 2: 3 つの音声ルートを作成する (Redmond 1、Redmond 2、Other +1)

次の手順では、音声ルートを作成する方法について説明します。 前の表で説明した設定を使用して、この例の Redmond 1、Redmond 2、Other +1 という 3 つの音声ルートを作成するには、次の手順を使用します。

1. Microsoft Teams 管理センターの左側のナビゲーションで、[音声ダイレクト ルーティング] に移動し、[音声ルート  >  **] タブを選択** します。
2. [ **追加]** をクリックし、音声ルートの名前と説明を入力します。
3. 優先度を設定し、ダイヤルされた番号パターンを指定します。
4. 音声ルートで SBC を登録するには、[登録済み SBC] **(オプション)** で **[SBC** の追加] をクリックし、登録する SBC を選択し、[適用] をクリック **します。**
5. PSTN 使用状況レコードを追加するには、[PSTN 使用状況レコード] **(省略可能)** で **、[PSTN** 使用状況の追加] をクリックし、追加する PSTN レコードを選択して、[適用] をクリック **します**。
6. **[保存]** をクリックします。

#### <a name="step-3-create-a-voice-routing-policy-named-us-only-and-add-the-us-and-canada-pstn-usage-to-the-policy"></a>手順 3: "米国のみ" という名前の音声ルーティング ポリシーを作成し、"米国とカナダ" の PSTN 使用状況をポリシーに追加する

1. Microsoft Teams 管理センターの左側のナビゲーションで、[**音声** ルーティング ポリシー] に移動し、[追加] を  >  クリック **します**。
2. 名前 **として米国のみ** と入力し、説明を追加します。
3. **[PSTN 使用状況レコード] で****、[PSTN** 使用状況の追加] をクリックし、[米国とカナダ] PSTN 使用状況レコードを選択し、[適用] をクリック **します**。
4. **[保存]** をクリックします。

詳細については、「音声ルーティング [ポリシーを管理する」を参照してください](manage-voice-routing-policies.md)。

#### <a name="step-4-assign-the-voice-routing-policy-to-a-user-named-spencer-low"></a>手順 4: Spencer Low という名前のユーザーに音声ルーティング ポリシーを割り当てる

1. Microsoft Teams 管理センターの左側のナビゲーションで、**[ユーザー]** に移動してユーザーをクリックします。
2. **[ポリシー]** をクリックし、**[割り当てられたポリシー]** の横にある **[編集]** をクリックします。
3. [ **音声ルーティング ポリシー] で**、[米国のみ] ポリシーを選択し、[保存] をクリック **します**。

詳細については、「音声ルーティング [ポリシーを管理する」を参照してください](manage-voice-routing-policies.md)。

### <a name="using-powershell"></a>PowerShell の使用
<a name="powershellexample1"></a>


#### <a name="step-1-create-the-us-and-canada-pstn-usage"></a>手順 1: "米国とカナダ" の PSTN 使用状況を作成する

Skype for Business Online のリモート PowerShell セッションで、次を入力します。

```PowerShell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="US and Canada"}
```

次を入力して、使用状況が作成されたと確認します。

```PowerShell
Get-CSOnlinePSTNUsage
``` 

切り捨て可能な名前のリストを返します。

```console
Identity    : Global
Usage        : {testusage, US and Canada, International, karlUsage. . .}
```

次の例は、PowerShell コマンドを実行して完全な名前を `(Get-CSOnlinePSTNUsage).usage` 表示した結果を示しています (切り捨てはされません)。

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

"Redmond 1" ルートを作成するには、Skype for Business Online の PowerShell セッションで次を入力します。

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

レドモンド 2 ルートを作成するには、次を入力します。

```PowerShell
New-CsOnlineVoiceRoute -Identity "Redmond 2" -NumberPattern "^\+1(425|206)
(\d{7})$" -OnlinePstnGatewayList sbc3.contoso.biz, sbc4.contoso.biz -Priority 2 -OnlinePstnUsages "US and Canada"
```

その他の +1 ルートを作成するには、次を入力します。

```PowerShell
New-CsOnlineVoiceRoute -Identity "Other +1" -NumberPattern "^\+1(\d{10})$"
-OnlinePstnGatewayList sbc5.contoso.biz, sbc6.contoso.biz -OnlinePstnUsages "US and Canada"
```

  > [!CAUTION]
  > NumberPattern 属性の正規表現が有効な式である必要があります。 この Web サイトを使用してテストできます。 [https://www.regexpal.com](https://www.regexpal.com)

場合によっては、すべての通話を同じ SBC にルーティングする必要があります。use -NumberPattern ".*"

すべての通話を同じ SBC にルーティングします。

```PowerShell
Set-CsOnlineVoiceRoute -id "Redmond 1" -NumberPattern ".*" -OnlinePstnGatewayList sbc1.contoso.biz
```

次に示すオプションを使用して PowerShell コマンドを実行して、ルートが正 `Get-CSOnlineVoiceRoute` しく構成されていることを確認します。

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

#### <a name="step-3-create-a-voice-routing-policy-named-us-only-and-add-the-us-and-canada-pstn-usage-to-the-policy"></a>手順 3: "米国のみ" という名前の音声ルーティング ポリシーを作成し、"米国とカナダ" の PSTN 使用状況をポリシーに追加する

Skype for Business Online の PowerShell セッションで、次を入力します。

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

#### <a name="step-4-assign-the-voice-routing-policy-to-a-user-named-spencer-low"></a>手順 4: Spencer Low という名前のユーザーに音声ルーティング ポリシーを割り当てる

Skype for Business Online の PowerShell セッションで、次を入力します。

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

## <a name="example-2-voice-routing-with-multiple-pstn-usages"></a>例 2: 複数の PSTN 使用状況を使用した音声ルーティング

使用例 1 で作成した音声ルーティング ポリシーでは、Microsoft 通話プランライセンスもユーザーに割り当てられていない限り、米国とカナダの電話番号への通話のみを許可します。

次の例では、"制限なし" 音声ルーティング ポリシーを作成できます。 このポリシーは、例 1 で作成した "米国とカナダ" の PSTN 使用状況と、新しい "国際" PSTN 使用状況を再利用します。 このポリシーは、その他のすべての呼び出しを SPC および sbc2.contoso.biz にルーティング sbc5.contoso.biz。

次に示す例では、Us Only policy をユーザー Spencer Low に割り当て、No Restrictions ポリシーをユーザーの John Woods に割り当てると、ルーティングは次のようになります。

- スペンサー 低 – 米国のみポリシー。  通話は米国およびカナダの番号にのみ許可されます。 レドモンド番号範囲に呼び出す場合は、特定のセットの SPC を使用する必要があります。 米国以外の番号は、通話プランライセンスがユーザーに割り当てられていない限り、ルーティングされません。

- John Woods – 国際ポリシー。  通話は任意の番号に対して許可されます。 レドモンド番号範囲に呼び出す場合は、特定のセットの SPC を使用する必要があります。 米国以外の番号は、電話番号と電話番号を sbc2.contoso.biz 使用 sbc5.contoso.biz。

![ユーザー Spencer Low に割り当てられている音声ルーティング ポリシーを示す](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoSpencerLow.png)

その他のすべての通話では、ユーザーが両方のライセンス (Microsoft 電話システムと Microsoft 通話プラン) を持つ場合は、自動ルートが使用されます。 管理者が作成したオンライン音声ルートの番号パターンに一致する番号が見当たらない場合、通話は Microsoft 通話プランを使用してルーティングされます。  ユーザーが Microsoft Phone System のみを使用している場合、照合ルールが利用できないので通話は削除されます。

![ユーザー John Woods に割り当てられた音声ルーティング ポリシーを示す](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoJohnWoods.png)

次の表では、ルーティング ポリシー "制限なし" の使用指定と音声ルートの概要を示します。 

| PSTN 使用法 | 音声ルート | 番号のパターン | [Priority] | SBC | 説明 |
|:-----|:-----|:-----|:-----|:-----|:-----|
|米国とカナダ|"Redmond 1"|^\\+1(425 \| 206)(\d {7} )$|1|sbc1.contoso.biz<br/>sbc2.contoso.biz|呼び出し先番号のアクティブなルート +1 425 XXX XX または +1 206 XXX XX XX|
|米国とカナダ|"Redmond 2"|^\\+1(425 \| 206)(\d {7} )$|2|sbc3.contoso.biz<br/>sbc4.contoso.biz|呼び出し先番号のバックアップ ルート +1 425 XXX XX または +1 206 XXX XX XX|
|米国とカナダ|"Other +1"|^\\+1(\d {10} )$|3|sbc5.contoso.biz<br/>sbc6.contoso.biz|呼び出し先番号のルート +1 XXX XXX XX XX (+1 425 XXX XX XX または +1 206 XXX XX XX を除く)|
|International|International|\d+|4|sbc2.contoso.biz<br/>sbc5.contoso.biz|任意の番号パターンのルーティング |

  > [!NOTE]
  > - 音声ルーティング ポリシーでの PSTN の使用順序は重要です。 使用法は順番に適用され、最初の使用法で一致が見つかった場合、他の使用法は評価されません。 "国際" PSTN の使用は、"米国とカナダ" の PSTN 使用状況の後に配置する必要があります。 PSTN 使用状況の順序を変更するには、コマンドを実行 `Set-CSOnlineVoiceRoutingPolicy` します。 <br/>たとえば、最初の "米国とカナダ" から 2 番目の "国際" から逆順の実行に順序を変更するには、<br/> `Set-CsOnlineVoiceRoutingPolicy -id tag:"no Restrictions" -OnlinePstnUsages @{Replace="International", "US and Canada"}`
 > - "その他 +1" および "国際" の音声ルートの優先度が自動的に割り当てられます。 "Redmond 1" や "Redmond 2" よりも優先度が低い限り、優先順位は関係ありません。

## <a name="example-2-configuration-steps"></a>例 2: 構成手順

次の例は、次の方法を示しています。

1. 国際と呼ばれる新しい PSTN 使用状況を作成します。
2. 「国際」という名前の新しい音声ルートを作成します。
3. [制限なし] という音声ルーティング ポリシーを作成します。
4. ユーザー John Woods にポリシーを割り当てる。

Microsoft Teams 管理センターまたは [PowerShell](#admincenterexample2) を使用して [、これらの](#powershellexample2) 手順を実行できます。

### <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターの使用
<a name="admincenterexample2"></a>

#### <a name="step-1-create-the-international-pstn-usage"></a>手順 1: "国際" PSTN 使用状況を作成する

1. Microsoft Teams 管理センターの左側のナビゲーションで、[音声ダイレクト ルーティング] に移動し、右上隅の [PSTN 使用状況レコードの管理] を  >  **選択します**。
2. [追加 **] をクリックし**、「国際」 **と入力** して、[適用] を **クリックします**。

#### <a name="step-2-create-the-international-voice-route"></a>手順 2: "国際" 音声ルートを作成する

1. Microsoft Teams 管理センターの左側のナビゲーションで、[音声ダイレクト ルーティング] に移動し、[音声ルート  >  **] タブを選択** します。
2. [ **追加]** をクリックし、名前に「国際」と入力して、説明を追加します。
3. 優先度を 4 に設定し、ダイヤルされた番号パターンを \d+ に設定します。
4. [ **登録済み SPC] (オプション)** で **、[SBC** の追加] をクリックし、sbc2.contoso.biz と sbc5.contoso.biz し、[適用] をクリック **します**。
5. **[PSTN 使用状況レコード] (省略可能)** で **、[PSTN** 使用状況の追加] をクリックし、[国際] PSTN 使用状況レコードを選び、[適用] をクリック **します**。
6. **[保存]** をクリックします。

#### <a name="step-3-create-a-voice-routing-policy-named-no-restrictions-and-add-the-us-and-canada-and-international-pstn-usages-to-the-policy"></a>手順 3: "制限なし" という名前の音声ルーティング ポリシーを作成し、"米国とカナダ" と "国際" の PSTN 使用状況をポリシーに追加する

PSTN の使用法 "米国とカナダ" は、この音声ルーティング ポリシーで再利用され、番号 "+1 425 XXX XX XX" および "+1 206 XXX XX XX" をローカルまたはオンプレミスの通話として呼び出す特殊な処理を保持します。

1. Microsoft Teams 管理センターの左側のナビゲーションで、[**音声** ルーティング ポリシー] に移動し、[追加] を  >  クリック **します**。
2. 名前 **に「制限なし** 」と入力し、説明を追加します。
3. **[PSTN 使用状況レコード] で****、[PSTN** 使用状況の追加] をクリックし、[米国とカナダ] PSTN 使用状況レコードを選択し、[国際] PSTN 使用状況レコードを選択します。 [**適用**] をクリックします。

    PSTN の使用状況の順序をメモします。

    - この例のように使用法を構成して番号 "+1 425 XXX XX XX" に対して行われた呼び出しの場合、呼び出しは "US and Canada" の使用で設定されたルートに従い、特殊なルーティング ロジックが適用されます。 つまり、通話は最初に sbc1.contoso.biz sbc2.contoso.biz を使用してルーティングされ、sbc3.contoso.biz と sbc4.contoso.biz として使用されます。

    - "国際" PSTN 使用状況が "米国およびカナダ" より前の場合、ルーティング ロジックの一部として +1 425 XXX XX XX が sbc2.contoso.biz および sbc5.contoso.biz にルーティングされます。

4. **[保存]** をクリックします。

詳細については、「音声ルーティング [ポリシーを管理する」を参照してください](manage-voice-routing-policies.md)。

#### <a name="step-4-assign-the-voice-routing-policy-to-a-user-named-john-woods"></a>手順 4: John Woods という名前のユーザーに音声ルーティング ポリシーを割り当てる

1. Microsoft Teams 管理センターの左側のナビゲーションで、**[ユーザー]** に移動してユーザーをクリックします。
2. **[ポリシー]** をクリックし、**[割り当てられたポリシー]** の横にある **[編集]** をクリックします。
3. 音声 **ルーティング ポリシーで、[** 制限なし] ポリシーを選択し、[保存] をクリック **します**。

その結果、John Woods の通話に適用される音声ポリシーは無制限であり、米国、カナダ、国際通話で利用できる通話ルーティングのロジックに従います。

### <a name="using-powershell"></a>PowerShell の使用
<a name="powershellexample2"></a>

#### <a name="step-1-create-the-international-pstn-usage"></a>手順 1: "国際" PSTN 使用状況を作成する

Skype for Business Online のリモート PowerShell セッションで、次を入力します。

```PowerShell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="International"}
```

#### <a name="step-2--create-a-new-voice-route-named-international"></a>手順 2: "国際" という名前の新しい音声ルートを作成する

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

PSTN の使用法 "Redmond 1" と "Redmond" は、この音声ルーティング ポリシーで再利用され、"+1 425 XXX XX XX" および "+1 206 XXX XX XX" をローカルまたはオンプレミスの通話として呼び出す特殊な処理を保持します。

  ```PowerShell
  New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"
  ```

PSTN の使用状況の順序をメモします。

  - 次の例のように使用法を構成して番号 "+1 425 XXX XX XX" に対して行われた呼び出しの場合、呼び出しは "米国とカナダ" で設定されたルートに従い、特殊なルーティング ロジックが適用されます。 つまり、通話は最初に sbc1.contoso.biz sbc2.contoso.biz を使用してルーティングされ、sbc3.contoso.biz と sbc4.contoso.biz として使用されます。

  - "国際" PSTN 使用状況が "米国およびカナダ" より前の場合、ルーティング ロジックの一部として +1 425 XXX XX XX が sbc2.contoso.biz および sbc5.contoso.biz にルーティングされます。 コマンドを入力します。

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

次に、コマンドを使用して課題を確認します。 

```PowerShell
Get-CsOnlineUser "John Woods" | Select OnlineVoiceRoutingPolicy
```

次の値が返されます。

```console
OnlineVoiceRoutingPolicy
------------------------
No Restrictions
```

その結果、John Woods の通話に適用される音声ポリシーは無制限であり、米国、カナダ、国際通話で利用できる通話ルーティングのロジックに従います。

## <a name="see-also"></a>関連項目

[ダイレクト ルーティングを計画する](direct-routing-plan.md)

[ダイレクト ルーティングを構成する](direct-routing-configure.md)
