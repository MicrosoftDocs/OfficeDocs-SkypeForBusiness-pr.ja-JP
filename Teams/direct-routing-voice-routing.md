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
ms.openlocfilehash: 8889475acda00cf1565f944c7925ba0fb5194ec5
ms.sourcegitcommit: 0289062510f0791906dab2791c5db8acb1cf849a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/20/2020
ms.locfileid: "42157989"
---
# <a name="configure-voice-routing-for-direct-routing"></a>直接ルーティング用のボイスルーティングを構成する

この記事では、電話システムのダイレクトルーティングのボイスルーティングを構成する方法について説明します。  これは、次の手順の手順3で、直接ルーティングを構成します。

- 手順1 [SBC と Microsoft 電話システムを接続して接続を検証する](direct-routing-connect-the-sbc.md) 
- 手順2 [ユーザーが直接ルーティング、音声、ボイスメールを使用できるようにする](direct-routing-enable-users.md)    
- **手順3音声ルーティングを構成する**(この記事)
- 手順4。 [数値を別の形式に変換する](direct-routing-translate-numbers.md) 

直接ルーティングを設定するために必要なすべての手順については、「[直接ルーティングを構成する](direct-routing-configure.md)」を参照してください。

## <a name="voice-routing-overview"></a>音声ルーティングの概要

Microsoft 電話システムには、次のことに基づいて特定のセッションボーダーコントローラー (SBC) に通話を送信できるルーティングメカニズムがあります。 

- 呼び出した番号のパターン 
- 呼び出された番号パターンと、通話を発信した特定のユーザー
 
SBCs は、アクティブなバックアップとして指定できます。 Active として構成されている SBC を特定の通話ルートで利用できない場合、通話はバックアップ SBC にルーティングされます。
 
音声ルーティングは、次の要素で構成されます。 

- **ボイスルーティングポリシー** – PSTN の使用を可能にするコンテナーであり、ユーザーまたは複数のユーザーに割り当てることができます。 

- **Pstn 使用状況**–ボイスルートと pstn 使用のコンテナー。さまざまな音声ルーティングポリシーで共有できます。 

- **ボイスルーティング**–番号パターンとオンライン PSTN ゲートウェイのセットによって、通話番号がパターンと一致する通話に使用されます。

- **オンライン PSTN ゲートウェイ**-sbc を介して通話を発信するときに適用される構成 (たとえば、P-指定された ID (pai) や優先コーデックなど) を保存する sbc へのポインターです。音声ルートに追加することができます。

## <a name="example-1-voice-routing-with-one-pstn-usage"></a>例 1: 1 つの PSTN 利用状況での音声ルーティング

次の図は、通話フローにおけるボイスルーティングポリシーの2つの例を示しています。

**通話フロー 1 (左側):** ユーザーが + 1 425 XXX XX xx または + 1 206 XXX XX xx を呼び出した場合、通話は SBC sbc1.contoso.biz または sbc2.contoso.biz にルーティングされます。 Sbc1.contoso.biz と sbc2.contoso.biz のどちらも使用できない場合は、通話が切断されます。 

**通話フロー 2 (右側):** ユーザーが + 1 425 XXX XX xx または + 1 206 XXX XX xx への通話を発信した場合、通話はまず SBC sbc1.contoso.biz または sbc2.contoso.biz にルーティングされます。 どちらの SBC も使用できない場合は、優先度の低いルートが試されます (sbc3.contoso.biz と sbc4.contoso.biz)。 利用可能な SBCs がない場合は、通話が切断されます。 

![ボイスルーティングポリシーの例を示しています](media/ConfigDirectRouting-VoiceRoutingPolicyExamples.png)

どちらの例でも、ボイスルートには優先順位が割り当てられていますが、ルートの SBCs はランダムな順序で試行されます。

  > [!NOTE]
  > ユーザーに Microsoft の通話プランライセンスも付与されていない限り、そのパターンに一致する番号 (1 425 XXX XX XX または + 1 206 XXX XX xx) は、この構成の例では削除されません。 ユーザーが通話プランライセンスを持っている場合は、Microsoft 通話プランのポリシーに従って、通話が自動的にルーティングされます。 Microsoft 通話プランは、Microsoft 通話プランライセンスを持つすべてのユーザーに対して、最後のルートとして自動的に適用され、追加の通話ルーティング構成は必要ありません。

次の図に示す例では、すべての米国とカナダの電話番号に通話を送信するための音声ルートが追加されています (通話は、番号パターン + 1 XXX XXX XX XX) に移動します。

![ボイスルーティングポリシーを3番目のルートとともに示しています](media/ConfigDirectRouting-VoiceRoutingPolicywith3rdroute.png)

その他の通話:

- ユーザーが両方のライセンス (Microsoft 電話システムと Microsoft 通話プラン) を持っている場合は、自動ルートが使用されます。 
- 管理者が作成したオンラインボイスルートの番号パターンと一致しない場合、その通話は Microsoft の通話プランを介してルーティングされます。
- ユーザーが Microsoft 電話システムしか使用していない場合は、一致するルールがないため、通話が切断されます。

  > [!NOTE]
  > ルート "Other + 1" の優先度の値は、パターン + 1 XXX XXX XX XX と一致するルートが1つだけであるため、この例では問題ありません。 ユーザーが + 1 324 567 89 89 に通話を発信し、sbc5.contoso.biz と sbc6.contoso.biz の両方を利用できない場合は、通話が切断されます。

次の表は、3つのボイスルートを使った構成をまとめたものです。 この例では、3つのルートすべてが同じ PSTN 使用状況 "US とカナダ" に含まれています。  すべてのルートは、PSTN の使用状況 "US およびカナダ" と関連付けられ、PSTN の使用状況はボイスルーティングポリシー "US のみ" に関連付けられています。 

|**PSTN 使用法**|**ボイスルート**|**番号パターン**|**[Priority]**|**SBC**|**説明**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|米国限定|"レドモンド 1"|^\\+ 1 (425\|206) (\d{7}) $|1|sbc1.contoso.biz<br/>sbc2.contoso.biz|呼び出された数値 + 1 425 XXX XX XX または + 1 206 XXX XX xx のアクティブルート|
|米国限定|"Redmond 2"|^\\+ 1 (425\|206) (\d{7}) $|両面|sbc3.contoso.biz<br/>sbc4.contoso.biz|呼び出した数値 + 1 425 XXX XX XX または + 1 206 XXX XX xx のバックアップルート|
|米国限定|"Other + 1"|^\\+ 1 (\d{10}) $|3|sbc5.contoso.biz<br/>sbc6.contoso.biz|"発信番号" のルート + 1 XXX XXX XX XX (+ 1 425 XXX XX xx または + 1 206 XXX XX xx)|
|||||||


### <a name="example-1-configuration-steps"></a>使用例 1: 構成手順

次の例は、次の方法を示しています。

- 単一の PSTN 使用を作成する 
- 3つのボイスルートを構成する
- ボイスルーティングポリシーを作成する
- ユーザー Spencer Low にポリシーを割り当てる

**手順 1:** PSTN 使用量 "US およびカナダ" を作成する

Skype for Business リモート PowerShell セッションで、次のように入力します。

```PowerShell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="US and Canada"}
```

次のように入力して使用が作成されたことを検証します。 
```PowerShell
Get-CSOnlinePSTNUsage
``` 
これは、切り捨てられる可能性がある名前のリストを返します。
```console
Identity    : Global
Usage       : {testusage, US and Canada, International, karlUsage. . .}
```
次の例は、PowerShell コマンド`(Get-CSOnlinePSTNUsage).usage`を実行して完全な名前を表示した場合の結果を示しています (トランケートされません)。

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

**手順 2:** Skype for Business Online の PowerShell セッションで、前の表に示されているように、Redmond 1、レドモンド2、その他の + 1 という3つのルートを作成します。

"Redmond 1" ルートを作成するには、次のように入力します。

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
  > 数値 Pattern 属性の正規表現が有効な式であることを確認します。 次の web サイトを使ってテストできます。[https://www.regexpal.com](https://www.regexpal.com)

場合によっては、すべての通話を同じ SBC にルーティングする必要があります。use-Number パターン ". *"

すべての通話を同じ SBC にルーティングします。

```PowerShell
Set-CsOnlineVoiceRoute -id "Redmond 1" -NumberPattern ".*" -OnlinePstnGatewayList sbc1.contoso.biz
```

次の`Get-CSOnlineVoiceRoute`ようなオプションを使用して PowerShell コマンドを実行して、ルートが正しく構成されていることを確認します。

```PowerShell
Get-CsOnlineVoiceRoute | Where-Object {($_.priority -eq 1) -or ($_.priority -eq 2) or ($_.priority -eq 4) -Identity "Redmond 1" -NumberPattern "^\+1(425|206) (\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```
戻り値:
<pre>
Identity            : Redmond 1 
Priority            : 1
Description     : 
NumberPattern       : ^\+1(425|206) (\d{7})$
OnlinePstnUsages    : {US and Canada}    
OnlinePstnGatewayList   : {sbc1.contoso.biz, sbc2.contoso.biz}
Name            : Redmond 1
Identity        : Redmond 2 
Priority            : 2
Description     : 
NumberPattern       : ^\+1(425|206) (\d{7})$
OnlinePstnUsages    : {US and Canada}    
OnlinePstnGatewayList   : {sbc3.contoso.biz, sbc4.contoso.biz}
Name            : Redmond 2
    
Identity        : Other +1 
Priority            : 4
Description     : 
NumberPattern       : ^\+1(\d{10})$
OnlinePstnUsages    : {US and Canada}    
OnlinePstnGatewayList   : {sbc5.contoso.biz, sbc6.contoso.biz}
Name            : Other +1
</pre>

この例では、ルート "Other + 1" は優先度4を自動的に割り当てられています。 

**手順 3:** ボイスルーティングポリシーを「US 専用」にして、「US とカナダ」という PSTN 使用のポリシーに追加します。

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

**手順 4:** PowerShell を使用して、音声ルーティングポリシーをユーザー Spencer Low に付与します。

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

次の例では、"制限なし" という音声ルーティングポリシーを作成できます。 このポリシーでは、例1で作成した PSTN の使用状況 "US and カナダ" と、新しい PSTN の使用状況 "海外" が再利用されます。  このポリシーは、SBCs sbc2.contoso.biz と sbc5.contoso.biz に対するその他のすべての通話をルーティングします。 

次に示す例では、ユーザー Spencer 低に米国限定ポリシーを割り当て、ユーザー John 森には制限なしのポリシーを割り当てて、ルーティングが次のように行われるようにします。

- Spencer 安値– US のみのポリシー。  通話は米国とカナダの番号のみに許可されています。 Redmond の番号範囲に発信する場合は、特定の SBCs セットを使用する必要があります。 米国以外の番号は、通話プランライセンスがユーザーに割り当てられていない限り、ルーティングされません。

- John 森–国際ポリシー。  通話は任意の番号に許可されています。 Redmond の番号範囲に発信する場合は、特定の SBCs セットを使用する必要があります。 米国以外の番号は、sbc2.contoso.biz と sbc5.contoso.biz を使ってルーティングされます。

![ユーザー Spencer Low に割り当てられている音声ルーティングポリシーを表示します](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoSpencerLow.png)

その他のすべての通話では、ユーザーに両方のライセンス (Microsoft Phone システムと Microsoft 通話プラン) がある場合、自動ルートが使用されます。 管理者が作成したオンラインボイスルートの番号パターンと一致しない場合は、Microsoft 通話プランを使って通話がルーティングされます。  ユーザーが Microsoft 電話システムのみを使用している場合は、一致するルールがないため、通話が切断されます。

![ユーザー John 森に割り当てられているボイスルーティングポリシーを示しています](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoJohnWoods.png)

次の表は、ルーティングポリシーの "制限なし" を使用しています。 

|**PSTN 使用法**|**ボイスルート**|**番号パターン**|**[Priority]**|**SBC**|**説明**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|米国限定|"レドモンド 1"|^\\+ 1 (425\|206) (\d{7}) $|1|sbc1.contoso.biz<br/>sbc2.contoso.biz|呼び出し先の番号 + 1 425 XXX XX XX または + 1 206 XXX XX xx のアクティブルート|
|米国限定|"Redmond 2"|^\\+ 1 (425\|206) (\d{7}) $|両面|sbc3.contoso.biz<br/>sbc4.contoso.biz|呼び出し先の番号のバックアップルート + 1 425 XXX XX XX または + 1 206 XXX XX xx|
|米国限定|"Other + 1"|^\\+ 1 (\d{10}) $|3|sbc5.contoso.biz<br/>sbc6> contoso.biz|呼び出し先の番号のルーティング + 1 XXX XXX XX XX (+ 1 425 XXX XX xx または + 1 206 XXX XX xx)|
|International|International|\d +|4|sbc2.contoso.biz<br/>sbc5.contoso.biz|任意の番号パターンのルート |


  > [!NOTE]
  > - ボイスルーティングポリシーの PSTN 使用の順序は重要です。 使用状況は順番に適用され、最初の使用で一致が見つかった場合は、他の使用法は評価されません。 PSTN の使用は、PSTN の使用の後に「米国専用」として設定する必要があります。 PSTN の使用順序を変更するには、 `Set-CSOnlineVoiceRoutingPolicy`コマンドを実行します。 <br/>たとえば、"US" と "カナダ" の順序を "第 1" と "海外" の順に変更するには、次のようにします。<br/> `Set-CsOnlineVoiceRoutingPolicy -id tag:"no Restrictions" -OnlinePstnUsages @{Replace="International", "US and Canada"}`
 > - "Other + 1" と "海外" のボイスルートの優先度は、自動的に割り当てられます。 "Redmond 1" と "レドモンド 2" よりも優先順位が低い場合は、問題ありません。


### <a name="example-2-configuration-steps"></a>例 2: 構成手順

次の例は、次の方法を示しています。

- 国際通話と呼ばれる新しい PSTN の利用状況を作成する
- 国際電話と呼ばれる新しいボイスルートを作成する
- 制限なしと呼ばれる音声ルーティングポリシーを作成する
- ユーザー John 森にポリシーを割り当てる


**手順 1**: PSTN 使用量「国際」を作成します。 

Skype for Business Online のリモート PowerShell セッションで、次のように入力します。

```PowerShell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="International"}
```

**手順 2**: 新しいボイスルート "国際" を作成します。

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

**手順 3**: 音声ルーティングポリシーを作成する "制限なし"。 

PSTN の利用状況 "レドモンド 1" と "Redmond" は、電話番号 "+ 1 425 XXX XX XX" と "+ 1 206 XXX XX XX" への通話に対する特別な処理を、ローカルまたはオンプレミスの通話として維持するために、この音声ルーティングポリシーで再利用されています。

  ```PowerShell
  New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"
  ```

PSTN の使用順序に注意してください。

  a. 次の例のように、利用状況を設定して、"+ 1 425 XXX XX XX" という数値を指定した場合は、通話は "US およびカナダ" の使用に設定され、特殊なルーティングロジックが適用されます。 つまり、sbc1.contoso.biz と sbc2.contoso.biz を使用して通話がルーティングされ、次にバックアップルートとして sbc3.contoso.biz と sbc4.contoso.biz が送信されます。

  b. "国際" という PSTN の使用が "US とカナダ" よりも前にある場合は、ルーティングロジックの一部として、+ 1 425 XXX XX XX への通話が sbc2.contoso.biz と sbc5.contoso.biz にルーティングされます。 コマンドを入力します。

  ```PowerShell
  New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"
  ```

戻り値:

    <pre>
    Identity              : International 
    OnlinePstnUsages : {US and Canada, International}    
    Description      :  
    RouteType             : BYOT
    </pre>

**手順 4**: 次のコマンドを使用して、ボイスルーティングポリシーをユーザーの "John 森" に割り当てます。

```PowerShell
Grant-CsOnlineVoiceRoutingPolicy -Identity "John Woods" -PolicyName "No Restrictions”
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
