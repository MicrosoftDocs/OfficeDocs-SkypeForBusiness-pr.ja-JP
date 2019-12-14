---
title: ダイレクト ルーティングを構成する
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
description: Microsoft Phone システムのダイレクトルーティングを構成する方法について説明します。
ms.openlocfilehash: 3524d3d41db02dbc123700ae259386bb97257bbd
ms.sourcegitcommit: c15ab82834005b9a19247e06488f1f21161fc426
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/13/2019
ms.locfileid: "40020071"
---
# <a name="configure-direct-routing"></a>ダイレクト ルーティングを構成する

> [!Tip]
> ダイレクトルーティングの利点、計画方法、展開方法については、次のセッションをご覧ください。 [Microsoft Teams での直接ルーティング](https://aka.ms/teams-direct-routing)

まだインストールしていない場合は、「[直接ルーティング](direct-routing-plan.md)の前提条件」を参照してください。また、Microsoft 電話システムネットワークを構成する前に必要なその他の手順を確認してください。 

この記事では、Microsoft Phone システムのダイレクトルーティングを構成する方法について説明します。 サポートされているセッション境界コントローラー (SBC) とダイレクトルーティングをペアリングする方法について説明します。また、Microsoft Teams ユーザーが直接ルーティングを使用して公衆交換電話網 (PSTN) に接続するように構成する方法についても説明します。 この記事で説明されている手順を実行するには、管理者が PowerShell コマンドレットについて理解している必要があります。 PowerShell の使用方法の詳細については、「 [Windows powershell 用にコンピューターをセットアップする](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)」を参照してください。 

Sbc が SBC ベンダーの推奨として既に構成されていることを確認することをお勧めします。 

- [AudioCodes の展開に関するドキュメント](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [Oracle 展開に関するドキュメント](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [リボンの通信展開に関するドキュメント](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [TE システム (anynode) の展開ドキュメント](https://www.anynode.de/anynode-and-microsoft-teams/)

Microsoft 電話システムを構成し、ユーザーが直接ルーティングを使用できるようにすることができます。次の手順を実行して、優先発信クライアントとして Microsoft Teams をセットアップします。 

- [SBC と Microsoft 電話システムをペアリングし、ペアリングを検証する](#pair-the-sbc-to-the-direct-routing-service-of-phone-system)
- [ユーザーのダイレクトルーティングサービスを有効にする](#enable-users-for-direct-routing-service)
- Microsoft Teams が、ユーザーの優先発信クライアントであることを確認する

## <a name="pair-the-sbc-to-the-direct-routing-service-of-phone-system"></a>SBC を電話システムのダイレクトルーティングサービスにペアリングする 

次に、SBC を直接ルーティングインターフェイスに接続するかペアリングする3つの大まかな手順について説明します。 

- PowerShell を使用して**Skype For Business Online**管理センターに接続する 
- SBC をペアリングする 
- ペアリングを検証する 

### <a name="connect-to-skype-for-business-online-by-using-powershell"></a>PowerShell を使用して Skype for Business Online に接続する 

テナントに接続された PowerShell セッションを使って、SBC とダイレクトルーティングインターフェイスをペアリングすることができます。 PowerShell セッションを開くには、「 [Windows powershell 用にコンピューターを](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)セットアップする」の手順に従ってください。 
 
リモート PowerShell セッションを確立したら、SBC を管理するためのコマンドが表示されることを確認します。 コマンドを検証するには、PowerShell セッションで次のように入力するか、コピーして貼り付け、enter キーを押します。 

```
Get-Command *onlinePSTNGateway*
```

このコマンドを実行すると、次に示す4つの関数が返され、SBC を管理できるようになります。 

<pre>
CommandType    Name                       Version    Source 
-----------    ----                       -------    ------ 
Function       Get-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt 
Function       New-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt 
Function       Remove-CsOnlinePSTNGateway 1.0        tmp_v5fiu1no.wxt 
Function       Set-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt
</pre>   


### <a name="pair-the-sbc-to-the-tenant"></a>SBC をテナントにペアリングする 

SBC をテナントにペアリングするには、PowerShell セッションで次のように入力し、enter キーを押します。 

```
New-CsOnlinePSTNGateway -Fqdn <SBC FQDN> -SipSignallingPort <SBC SIP Port> -MaxConcurrentSessions <Max Concurrent Sessions the SBC can handle> -Enabled $true 
```
  > [!NOTE]
  > 1. Sbc ドキュメントに記載されている情報を使って、SBC で最大限の通話制限を設定することを強くお勧めします。 SBC がキャパシティレベルにある場合、制限によって通知がトリガーされます。
  > 2. SBC をペアリングできるのは、その FQDN のドメイン部分が、テナントに登録されているドメインのいずれ\*かに一致している場合のみです。 onmicrosoft.com を除きます。 \*Onmicrosoft.com ドメイン名は、SBC FQDN 名ではサポートされていません。 たとえば、2つのドメイン名がある場合は、次のようになります。<br/><br/>
  > **contoso**.com<br/>**** onmicrosoft.com<br/><br/>
  > SBC 名には、sbc.contoso.com という名前を使用できます。 SBC と名前 sbc をペアリングしようとしても、ドメインはこのテナントによって所有されていないため、システムによっては許可されません。<br/>
  > テナントに登録されているドメインに加えて、そのドメインを持つユーザーと E3 または E5 ライセンスが割り当てられていることが重要です。 存在しない場合、次のエラーが表示されます。<br/>
  `Can not use the “sbc.contoso.com” domain as it was not configured for this tenant`.

```
New-CsOnlinePSTNGateway -Identity sbc.contoso.com -Enabled $true -SipSignallingPort 5067 -MaxConcurrentSessions 100 
```
返し
<pre>
Identity              : sbc.contoso.com 
Fqdn                  : sbc.contoso.com 
SipSignallingPort     : 5067 
FailoverTimeSeconds   : 10 
ForwardCallHistory    : False 
ForwardPai            : False 
SendSipOptions        : True 
MaxConcurrentSessions : 100 
Enabled               : True   
</pre>
ペアリングプロセス中に設定できるその他のオプションがあります。 ただし、前の例では、必須の最小パラメーターのみが表示されています。 
 
次の表は、の```New-CsOnlinePstnGateway```パラメーターの設定に使用できるその他のパラメーターを示しています。

|必須。|名前|説明|既定|可能な値|種類と制限|
|:-----|:-----|:-----|:-----|:-----|:-----|
|はい|FQDN|SBC の FQDN 名 |なし|NoneFQDN 名、63文字を制限する|[コンピューター、ドメイン、サイト、および ou の Active Directory の名前付け規則](https://support.microsoft.com/help/909264)での文字列、許可されている文字および禁止されている文字の一覧|
|いいえ|MediaBypass |は、SBC でサポートされているメディアバイパスのパラメーターであり、管理者はこのパラメーターを使いたいと考えています。|なし|True<br/>False|Boolean|
|はい|SipSignallingPort |トランスポート層セキュリティ (TLS) プロトコルを使用した、直接ルーティングサービスとの通信に使用するリスニングポート。|なし|任意のポート|0 ~ 65535 |
|いいえ|FailoverTimeSeconds |10 (既定値) に設定すると、ゲートウェイによって応答されない送信通話は、次の利用可能なトランクにルーティングされます。追加の trunks がない場合、通話は自動的に切断されます。 低速のネットワークとゲートウェイ応答を使用している組織では、通話が不必要に削除される可能性があります。 既定値は10です。|常用|数値|Int|
|いいえ|ForwardCallHistory |通話履歴の情報をトランク経由で転送するかどうかを指定します。 有効になっている場合、Office 365 PSTN プロキシは、2つのヘッダー (履歴-情報と参照) を送信します。 既定値は**False** ($False) です。 |False|True<br/>False|Boolean|
|いいえ|ForwardPAI|P-Asserted-Identity (PAI) ヘッダーを通話とともに転送するかどうかを示します。 PAI ヘッダーがあれば、発信者 ID を確認できます。 有効になっている場合、プライバシー: ID ヘッダーも送信されます。 既定値は**False** ($False) です。|False|True<br/>False|Boolean|
|いいえ|SendSIPOptions |SBC が SIP オプションを送信するかどうかを定義します。 無効にした場合、SBC は、監視および警告システムから除外されます。 SIP オプションを有効にすることを強くお勧めします。 既定値は**True**です。 |True|True<br/>False|Boolean|
|いいえ|MaxConcurrentSessions |アラートシステムで使用されます。 いずれかの値が設定されると、同時セッション数が90% 以上である場合、またはこの値よりも高い場合に、通知システムによってテナント管理者に通知が生成されます。 パラメーターが設定されていない場合、アラートは生成されません。 ただし、監視システムでは、24時間ごとに同時セッションの数が報告されます。 |空|空<br/>1 ~ 10万 ||
|いいえ|MediaRelayRoutingLocationOverride |メディアのパスを手動で選ぶことができます。 直接ルーティングでは、SBC のパブリック IP に基づいて、メディアパスのデータセンターが割り当てられます。 常に、SBC データセンターに最も近いものを選択します。 ただし、場合によっては、たとえば、米国の範囲を、ヨーロッパにある SBC に割り当てることができます。 この場合は、最適なメディアパスを使用しないようにします。 このパラメーターを使うと、メディアトラフィックの優先領域を手動で設定できます。 このパラメーターを設定することをお勧めします。このパラメーターを設定することは、メディアパスのデータセンターの自動割り当てで SBC データセンターに最も近い値が割り当てられないということを意味します。 |なし|ISO 形式の国コード||
|いいえ|有効|この SBC を発信通話に対して有効にします。 更新中またはメンテナンス中に、SBC を一時的に削除するために使用できます。 |False|True<br/>False|Boolean|
 
### <a name="verify-the-sbc-pairing"></a>SBC ペアリングを確認する 

接続を確認します。 
- SBC が、ペアリングされた SBCs のリストにあるかどうかを確認します。 
- SIP オプションを確認します。 
 
#### <a name="validate-if-the-sbc-is-on-the-list-of-paired-sbcs"></a>SBC が、ペアリングされた SBCs のリストにあるかどうかを検証します 

SBC をペアリングした後、リモート PowerShell セッションで次のコマンドを実行して、SBC が、[ペアリングされた SBCs] のリストに存在することを確認します。`Get-CSOnlinePSTNGateway`

次の例に示すように、ペアリングされたゲートウェイがリストに表示され、**有効になっ**ているパラメーターに**True**の値が表示されていることを確認します。 ください

```
Get-CsOnlinePSTNGateway -Identity sbc.contoso.com  
```
戻り値:
<pre>
Identity              : sbc.contoso.com  
Fqdn                  : sbc.contoso.com 
SipSignallingPort     : 5067 
CodecPriority         : SILKWB,SILKNB,PCMU,PCMA 
ExcludedCodecs        :  
FailoverTimeSeconds   : 10 
ForwardCallHistory    : False 
ForwardPai            : False 
SendSipOptions        : True 
MaxConcurrentSessions : 100 
Enabled               : True 
</pre>

#### <a name="validate-sip-options-flow"></a>SIP オプションのフローを検証する 

発信 SIP オプションを使用してペアリングを検証するには、SBC 管理インターフェイスを使用して、SBC が送信オプションメッセージに対する 200 OK 応答を受信することを確認します。

ダイレクトルーティングでは、着信オプションが表示され、着信のオプションメッセージの [連絡先ヘッダー] フィールドに設定された SBC FQDN への送信 SIP オプションメッセージの送信が開始されます。 

着信 SIP オプションを使用してペアリングを検証するには、SBC 管理インターフェイスを使用します。また、SBC は直接ルーティングからのオプションメッセージに返信を送信し、送信する応答コードは 200 OK であることを確認します。

## <a name="enable-users-for-direct-routing-service"></a>ユーザーのダイレクトルーティングサービスを有効にする 

ユーザーが直接ルーティングサービスを有効にする準備ができたら、次の手順を実行します。 

1. Office 365 でユーザーを作成し、電話システムのライセンスを割り当てます。 
2. ユーザーが Skype for Business Online に所属していることを確認します。 
3. 電話番号を構成し、エンタープライズボイスとボイスメールを有効にします。 
4. 音声ルーティングを構成します。 ルートは、自動的に検証されます。

### <a name="create-a-user-in-office-365-and-assign-the-license"></a>Office 365 でユーザーを作成してライセンスを割り当てる 

Office 365 で新規ユーザーを作成するには、2つのオプションがあります。 ただし、ルーティングの問題を回避するために、次のいずれかのオプションを組織で選択して使用することをお勧めします。 

- オンプレミスの Active Directory でユーザーを作成し、ユーザーをクラウドと同期します。 「[オンプレミスディレクトリと Azure Active Directory の統合」を](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect)参照してください。
- Office 365 管理ポータルに直接ユーザーを作成します。 「 [Office 365 にユーザーを個別に、またはまとめて追加する-管理者向けヘルプ」を](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec)参照してください。 

Skype for business Online の展開が Skype for Business 2015 または Lync 2010/2013 のオンプレミスで共存している場合、サポートされているのは、オンプレミスの Active Directory でユーザーを作成して、ユーザーをクラウドに同期する方法 (オプション 1) だけです。 

必要なライセンス: 

- Office 365 Enterprise E3 (SfB Plan2、Exchange Plan2、Teams など) + 電話システム
- Office 365 Enterprise E5 (SfB Plan2、Exchange Plan2、Teams、電話システムなど) 

オプションのライセンス: 

- 通話プラン 
- 電話会議 

### <a name="ensure-that-the-user-is-homed-in-skype-for-business-online"></a>ユーザーが Skype for Business Online に所属していることを確認する 

直接ルーティングを使用するには、ユーザーが Skype for Business Online を使用している必要があります。 これを確認するには、RegistrarPool パラメーターを参照してください。 Infra.lync.com ドメインに値が含まれている必要があります。

1. リモート PowerShell に接続します。
2. 次のコマンドを実行します。 

```
Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool
``` 

### <a name="configure-the-phone-number-and-enable-enterprise-voice-and-voicemail"></a>電話番号を設定し、エンタープライズボイスとボイスメールを有効にする 

ユーザーを作成してライセンスを割り当てたら、次の手順として、電話番号とボイスメールを構成します。 これは、1つの手順で行うことができます。 

電話番号を追加してボイスメールを有効にするには:
 
1. リモート PowerShell セッションに接続します。 
2. コマンドを入力します。 
 
```
Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI tel:<E.164 phone number>
```

たとえば、"Spencer Low" というユーザーの電話番号を追加するには、次のように入力します。 

```
Set-CsUser -Identity "Spencer Low" -OnPremLineURI tel:+14255388797 -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
```

使用される電話番号は、国コードを含む完全な電子電話番号として構成する必要があります。 

  > [!NOTE]
  > ユーザーの電話番号がオンプレミスで管理されている場合は、オンプレミスの Skype for Business 管理シェルまたはコントロールパネルを使用して、ユーザーの電話番号を構成します。 

### <a name="configure-voice-routing"></a>音声ルーティングを構成する 

Microsoft 電話システムには、以下に基づいて特定の SBC に通話を送信することができるルーティングメカニズムがあります。 

- "番号パターン" と呼ばれる 
- 通話を発信している番号パターンと、特定のユーザー
 
SBCs は、アクティブなバックアップとして指定できます。 つまり、この数値パターンに対してアクティブとして構成されている SBC、または数値パターンと特定のユーザーを使用できない場合、通話はバックアップ SBC にルーティングされます。
 
通話ルーティングは、次の要素で構成されます。 
- 音声ルーティングポリシー– PSTN 使用のコンテナー。ユーザーまたは複数のユーザーに割り当てることができる 
- PSTN 使用状況–ボイスルートと PSTN 使用のコンテナー。異なる音声ルーティングポリシーで共有できる 
- ボイスルーティング–番号パターンとオンライン PSTN ゲートウェイのセットを使用して、通話番号がパターンと一致する通話に使用する 
- オンライン PSTN ゲートウェイ: SBC へのポインターでは、(PAI () forward Identity (PAI) または好ましいコーデックなど、SBC 経由で通話を発信するときに適用される構成も保存します。音声ルートに追加できます 

#### <a name="creating-a-voice-routing-policy-with-one-pstn-usage"></a>単一の PSTN 使用を使用した音声ルーティングポリシーの作成 

次の図は、通話フローのボイスルーティングポリシーの2つの例を示しています。

**通話フロー 1 (左側):** ユーザーが + 1 425 XXX XX xx または + 1 206 XXX XX xx を呼び出した場合、通話は SBC sbc1.contoso.biz または sbc2.contoso.biz にルーティングされます。 Sbc1.contoso.biz と sbc2.contoso.biz のどちらも使用できない場合は、通話が切断されます。 

**通話フロー 2 (右側):** ユーザーが + 1 425 XXX XX xx または + 1 206 XXX XX xx への通話を発信した場合、通話はまず SBC sbc1.contoso.biz または sbc2.contoso.biz にルーティングされます。 どちらの SBC も使用できない場合は、優先度の低いルートが試されます (sbc3.contoso.biz と sbc4.contoso.biz)。 利用可能な SBCs がない場合は、通話が切断されます。 

![ボイスルーティングポリシーの例を示しています](media/ConfigDirectRouting-VoiceRoutingPolicyExamples.png)

どちらの例でも、ボイスルートには優先順位が割り当てられていますが、ルートの SBCs はランダムな順序で試行されます。

  > [!NOTE]
  > ユーザーに Microsoft の通話プランライセンスも付与されていない限り、そのパターンに一致する番号 (1 425 XXX XX XX または + 1 206 XXX XX xx) は、この構成の例では削除されません。 ユーザーが通話プランライセンスを持っている場合は、Microsoft 通話プランのポリシーに従って、通話が自動的にルーティングされます。 

Microsoft 通話プランは、Microsoft 通話プランライセンスを持つすべてのユーザーに対して、最後のルートとして自動的に適用され、追加の通話ルーティング構成は必要ありません。

次の図に示す例では、すべての米国およびカナダの電話番号に通話を送信するための音声ルートが追加されています (通話は、番号パターン + 1 XXX XXX XX XX) に移動します。

![ボイスルーティングポリシーを3番目のルートとともに示しています](media/ConfigDirectRouting-VoiceRoutingPolicywith3rdroute.png)

その他のすべての通話では、ユーザーに両方のライセンス (Microsoft Phone システムと Microsoft 通話プラン) がある場合、自動ルートが使用されます。 管理者が作成したオンラインボイスルートの番号パターンと一致しない場合は、Microsoft 通話プランを使ってルーティングします。

ユーザーが Microsoft 電話システムのみを使用している場合は、一致するルールがないため、通話が切断されます。

  > [!NOTE]
  > ルート "Other + 1" の Priority の値は、この例では関係ありません。パターンは1つだけであり、1 XXX XXX XX XX と一致します。 ユーザーが + 1 324 567 89 89 に通話を発信し、sbc5.contoso.biz と sbc6.contoso.biz の両方を利用できない場合は、通話が切断されます。

次の表は、3つのボイスルートを使った構成をまとめたものです。 この例では、3つのルートすべてが同じ PSTN 使用状況 "US とカナダ" に含まれています。

|**PSTN 使用法**|**ボイスルート**|**番号パターン**|**[Priority]**|**SBC**|**説明**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|米国限定|"レドモンド 1"|^\\+ 1 (425\|206) (\d{7}) $|1|sbc1.contoso.biz<br/>sbc2.contoso.biz|呼び出された数値 + 1 425 XXX XX XX または + 1 206 XXX XX xx のアクティブルート|
|米国限定|"Redmond 2"|^\\+ 1 (425\|206) (\d{7}) $|両面|sbc3.contoso.biz<br/>sbc4.contoso.biz|呼び出した数値 + 1 425 XXX XX XX または + 1 206 XXX XX xx のバックアップルート|
|米国限定|"Other + 1"|^\\+ 1 (\d{10}) $|3|sbc5.contoso.biz<br/>sbc6.contoso.biz|"発信番号" のルート + 1 XXX XXX XX XX (+ 1 425 XXX XX xx または + 1 206 XXX XX xx)|
|||||||

すべてのルートは、PSTN の使用状況 "US およびカナダ" と関連付けられ、PSTN の使用状況はボイスルーティングポリシー "US のみ" に関連付けられています。 この例では、ボイスルーティングポリシーがユーザー Spencer Low に割り当てられています。

#### <a name="examples-of-call-routes"></a>通話ルートの例

次の例では、ルート、PSTN の使用状況、ルーティングポリシーを構成する方法を示しています。これにより、ポリシーがユーザーに割り当てられます。

**手順 1:**「US とカナダ」という PSTN の使用を作成します。

Skype for Business リモート PowerShell セッションで、次のように入力します。

```
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="US and Canada"}
```

次のように入力して使用が作成されたことを検証します。 
```
Get-CSOnlinePSTNUsage
``` 
これは、切り捨てられる可能性がある名前のリストを返します。
```
Identity    : Global
Usage       : {testusage, US and Canada, International, karlUsage. . .}
```
次の例では、PowerShell コマンド`(Get-CSOnlinePSTNUsage).usage`を実行して完全な名前を表示できます (トランケートされません)。

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

**手順 2:** Skype for Business Online の PowerShell セッションで、前の表で説明したように、Redmond 1、レドモンド2、その他の + 1 の3つのルートを作成します。 

"Redmond 1" ルートを作成するには、次のように入力します。

```
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

```
New-CsOnlineVoiceRoute -Identity "Redmond 2" -NumberPattern "^\+1(425|206)
(\d{7})$" -OnlinePstnGatewayList sbc3.contoso.biz, sbc4.contoso.biz -Priority 2 -OnlinePstnUsages "US and Canada"
```

他の + 1 ルートを作成するには、次のように入力します。

```
New-CsOnlineVoiceRoute -Identity "Other +1" -NumberPattern "^\+1(\d{10})$"
-OnlinePstnGatewayList sbc5.contoso.biz, sbc6.contoso.biz -OnlinePstnUsages "US and Canada"
```

  > [!CAUTION]
  > 数値 Pattern 属性の正規表現が有効な式であることを確認します。 次の web サイトを使ってテストできます。[https://www.regexpal.com](https://www.regexpal.com)

場合によっては、すべての通話を同じ SBC にルーティングする必要があります。-番号パターン ". *" を使用してください。

すべての通話を同じ SBC にルーティングします。

```
Set-CsOnlineVoiceRoute -id "Redmond 1" -NumberPattern ".*" -OnlinePstnGatewayList sbc1.contoso.biz
```

次の`Get-CSOnlineVoiceRoute`ようなオプションを使用して PowerShell コマンドを実行して、ルートが正しく構成されていることを確認します。

```
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

```
New-CsOnlineVoiceRoutingPolicy "US Only" -OnlinePstnUsages "US and Canada"
```

結果は、次の例のように表示されます。

<pre>
Identity            : Tag:US only
OnlinePstnUsages    : {US and Canada}
Description         :
RouteType           : BYOT
</pre>

**手順 4:** Spencer には、PowerShell を使用してボイスルーティングポリシーを低いユーザーに付与します。

Skype for Business Online の PowerShell セッションで、次のように入力します。

```
Grant-CsOnlineVoiceRoutingPolicy -Identity "Spencer Low" -PolicyName "US Only"
```

このコマンドを入力して、ポリシーの割り当てを確認します。

```
Get-CsOnlineUser "Spencer Low" | select OnlineVoiceRoutingPolicy
```

戻り値:
<pre>
OnlineVoiceRoutingPolicy
---------------------
US Only
</pre>

#### <a name="creating-a-voice-routing-policy-with-several-pstn-usages"></a>複数の PSTN 使用を使用した音声ルーティングポリシーの作成

以前に作成した音声ルーティングポリシーでは、米国とカナダでの電話番号への通話のみが許可されています。 Microsoft 通話プランライセンスもユーザーに割り当てられている場合を除きます。

次の例では、"制限なし" という音声ルーティングポリシーを作成できます。 このポリシーでは、前の例で作成した PSTN の使用状況 "US and カナダ" も再利用され、新しい PSTN の利用状況 "国際" が使用されます。 

これにより、すべての通話が SBCs sbc2.contoso.biz と sbc5.contoso.biz にルーティングされます。 以下の例では、ユーザー "John 森" に米国限定のポリシーが割り当てられていないことを示しています。

Spencer 安値–米国とカナダの番号のみに許可されています。 Redmond の番号範囲に発信する場合は、特定の SBC のセットを使用する必要があります。 米国以外の番号は、通話プランライセンスがユーザーに割り当てられていない限り、ルーティングされません。

John 森–任意の番号に通話を発信できます。 Redmond の番号範囲に発信する場合は、特定の SBC のセットを使用する必要があります。 米国以外の番号は、sbc2.contoso.biz と sbc5.contoso.biz 経由でルーティングされます。

![ユーザー Spencer Low に割り当てられている音声ルーティングポリシーを表示します](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoSpencerLow.png)

その他のすべての通話では、ユーザーに両方のライセンス (Microsoft Phone システムと Microsoft 通話プラン) がある場合、自動ルートが使用されます。 管理者が作成したオンラインボイスルートの番号パターンと一致しない場合は、Microsoft 通話プランを使ってルーティングします。

ユーザーが Microsoft 電話システムのみを使用している場合は、一致するルールがないため、通話が切断されます。

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

#### <a name="example-of-voice-routing-policy-for-user-john-woods"></a>ユーザー John 森のボイスルーティングポリシーの例

PSTN の使用方法として、"インターナショナル"、音声ルート "インターナショナル"、"ボイスルーティングポリシー" (制限なし)、ユーザーを "John 森" に割り当てる手順は次のとおりです。


**手順 1**: PSTN 使用量「国際」を作成します。 

Skype for Business Online のリモート PowerShell セッションで、次のように入力します。

```
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="International"}
```

**手順 2**: 新しいボイスルート "国際" を作成します。

```
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

   ```
   New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"
   ```

PSTN の使用順序に注意してください。

a. 次の例のように、利用状況を設定して、"+ 1 425 XXX XX XX" という数値を指定した場合は、通話は "US およびカナダ" の使用に設定され、特殊なルーティングロジックが適用されます。 つまり、sbc1.contoso.biz と sbc2.contoso.biz を使用して通話がルーティングされ、次にバックアップルートとして sbc3.contoso.biz と sbc4.contoso.biz が送信されます。

b. "国際" という PSTN の使用が "US とカナダ" よりも前にある場合は、ルーティングロジックの一部として、+ 1 425 XXX XX XX への通話が sbc2.contoso.biz と sbc5.contoso.biz にルーティングされます。 コマンドを入力します。

```
New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"
```

戻り値

<pre>
Identity              : International 
OnlinePstnUsages : {US and Canada, International}    
Description      :  
RouteType             : BYOT
</pre>

**手順 4**: 次のコマンドを使用して、ボイスルーティングポリシーをユーザーの "John 森" に割り当てます。

```
Grant-CsOnlineVoiceRoutingPolicy -Identity "John Woods" -PolicyName "No Restrictions”
```

次に、コマンドを使用して課題を確認します。 

```
Get-CsOnlineUser "John Woods" | Select OnlineVoiceRoutingPolicy
```

戻り値:

<pre>
OnlineVoiceRoutingPolicy
------------------------
No Restrictions
</pre>

結果として、John 森の通話に適用されるボイスポリシーは無制限であり、米国、カナダ、国際通話で利用可能な通話ルーティングのロジックに従うことになります。

## <a name="assign-teams-only-mode-to-users-to-ensure-calls-land-in-microsoft-teams"></a>Microsoft Teams で通話を確実に行うためにチームのみのモードをユーザーに割り当てる

直接ルーティングを使うには、チームクライアントで着信通話を確実にするために、ユーザーが Teams 専用モードになっている必要があります。 ユーザーをチームのみのモードに配置するには、TeamsUpgradePolicy の "UpgradeToTeams" インスタンスを割り当てます。 組織で Skype for Business Server または Skype for Business Online を使用している場合は、次の記事を参照してください。 Skype と Teams の間の相互運用性については、「 [skype For business でチームを使用する](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype)」を参照してください。 

## <a name="configuring-sending-calls-directly-to-voicemail"></a>ボイスメールに直接通話を送信するように設定する

ダイレクトルーティングを使うと、ユーザの通話を終了してユーザのボイスメールに直接送ることができます。 直接ボイスメールに通話を送信するには、符号化 = app: ボイスメールを要求 URI ヘッダーに接続してください。 たとえば、"sip: user@yourdomain、不透明 = アプリ: ボイスメール" です。
この場合、Teams ユーザーは呼び出し通知を受信しません。通話はユーザーのボイスメールに直接接続されます。

## <a name="translate-caller-and-callee-numbers-for-outbound-and-inbound-calls-to-an-alternate-format"></a>送信および着信通話の代わりの形式に対して、発信者と着信者の番号を変換する

テナント管理者は、作成したパターンに基づいて、発信または着信の呼び出し先または着信者番号を変更して、SBCs との相互運用性を実現することができます。 電話番号の翻訳ルールポリシーを設定して、呼び出し元または発信者番号を別の形式に変換することができます。 ポリシーを使用して、次のような数値を翻訳できます。

- 着信通話: PSTN エンドポイントからチームクライアント (呼び出し元) への通話。
- 発信通話: チームクライアント (発信者) から PSTN エンドポイント (呼び出し先) への通話。

ポリシーは、SBC レベルで適用されます。 複数の翻訳ルールを SBC に割り当てることができます。これは、PowerShell でそれらをリストしたときに表示される順序で適用されます。 ポリシーのルールの順序を変更することもできます。

数値操作ルールを作成、変更、表示、削除するには、TeamsTranslationRule、TeamsTranslationRule、TeamsTranslationRule、および TeamsTranslationRule コマンドレットを使用します。

SBCs で番号操作ルールを割り当て、構成、および一覧表示するには、、、、、、、および```OutboundPSTNNumberTranslationRulesList```パラメーターを```InboundTeamsNumberTranslationRules```使用```InboundPSTNNumberTranslationRules```し```OutboundTeamsNumberTranslationRules```て```OutboundPSTNNumberTranslationRules```、 ```InboundTeamsNumberTranslationRulesList```CSOnlinePSTNGateway ```InboundPSTNNumberTranslationRulesList```と```OutboundTeamsNumberTranslationRulesList``` [CSOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway)コマンドレットを併用します。 [](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway)

### <a name="examples"></a>例

#### <a name="example-sbc-configuration"></a>SBC 構成の例

このシナリオの例では、 ```New-CsOnlinePSTNGateway```コマンドレットを実行して、次の SBC 構成を作成します。

```
New-CSOnlinePSTNGateway -Identity sbc1.contoso.com -SipSignallingPort 5061 –InboundTeamsNumberTranslationRulesList ‘AddPlus1’, ‘AddE164SeattleAreaCode’ -InboundPSTNNumberTranslationRulesList ‘AddPlus1’ -OnboundPSTNNumberTranslationRulesList ‘AddSeattleAreaCode’,  -OutboundTeamsNumberTranslationRulesList ‘StripPlus1’
```

SBC に割り当てられている翻訳ルールは、次の表のようにまとめられています。

|名前  |実線 |変換  |
|---------|---------|---------|
|AddPlus1     |^ (\d{10}) $          |+1$1          |
|AddE164SeattleAreaCode      |^ (\d{4}) $          | + 1206555 $ 1         |
|AddSeattleAreaCode    |^ (\d{4}) $          | 425555 $ 1         |
|StripPlus1    |^ + 1 (\d{10}) $          | $1         |

このようなシナリオでは、Alice と Bob の2人のユーザーがいます。 アリスは Teams ユーザーで、この番号は + 1 206 555 0100 です。 ボブは PSTN ユーザーで、その番号は + 1 425 555 0100 です。

#### <a name="example-1-inbound-call-to-a-ten-digit-number"></a>例 1:10 桁の番号への着信通話

ボブの10桁の数字以外の番号を使用してアリスが通話を発信します。 ボブは、アリスに連絡するために2065550100をダイヤルします。
SBC は、RequestURI で2065550100を使用し、From ヘッダーではヘッダーと4255550100を使用します。

|Header  |翻訳元 |翻訳済みヘッダー |パラメーターとルールの適用  |
|---------|---------|---------|---------|
|RequestURI  |Sip:2065550100@sbc.contoso.com を招待する|Sip:+12065550100@sbc.contoso.com を招待する|InboundTeamsNumberTranslationRulesList 'AddPlus1'|
|宛先    |宛先: \<sip:2065550100@sbc.contoso.com>|宛先: \<sip:+12065550100@sbc.contoso.com>|InboundTeamsNumberTranlationRulesList 'AddPlus1'|
|差出人   |差出人: \<sip:4255550100@sbc.contoso.com>|差出人: \<sip:+14255550100@sbc.contoso.com>|InboundPSTNNumberTranslationRulesList 'AddPlus1'|

#### <a name="example-2-inbound-call-to-a-four-digit-number"></a>例 2: 4 桁の番号への着信通話

ボブは、4桁の数字を使って Alice と通話します。 ボブは、アリスに連絡するために0100をダイヤルします。
SBC は、RequestURI で0100を使用し、From ヘッダーではヘッダーと4255550100を使用します。

|Header  |翻訳元 |翻訳済みヘッダー |パラメーターとルールの適用  |
|---------|---------|---------|---------|
|RequestURI  |Sip:0100@sbc.contoso.com を招待する          |Sip:+12065550100@sbc.contoso.com を招待する           |InboundTeamsNumberTranlationRulesList 'AddE164SeattleAreaCode'        |
|宛先    |宛先: \<sip:0100@sbc.contoso.com>|宛先: \<sip:+12065550100@sbc.contoso.com>|InboundTeamsNumberTranlationRulesList 'AddE164SeattleAreaCode'         |
|差出人   |差出人: \<sip:4255550100@sbc.contoso.com>|差出人: \<sip:+14255550100@sbc.contoso.com>|InboundPSTNNumberTranlationRulesList 'AddPlus1'        |

#### <a name="example-3-outbound-call-using-a-ten-digit-non-e164-number"></a>例 3:10 桁の番号を使用した発信通話

アリスは、10桁の数字を使ってボブを呼び出します。 アリスは、425 555 0100 にダイヤルしてボブに連絡します。
SBC は、Teams と PSTN の両方の10桁の10桁の番号を使用するように構成されています。

このシナリオでは、ダイヤルプランによって電話番号がダイレクトルーティングインターフェイスに送信される前に変換されます。 アリスが Teams クライアントに 425 555 0100 を入力すると、その番号は国のダイヤルプランによって + 14255550100 に変換されます。 結果として得られる数値は、ダイヤルプランのルールと Teams の翻訳ルールの累積正規化です。 Teams の翻訳ルールは、ダイヤルプランによって追加された "+ 1" を削除します。

|Header  |翻訳元 |翻訳済みヘッダー |パラメーターとルールの適用  |
|---------|---------|---------|---------|
|RequestURI  |Sip:+14255550100@sbc.contoso.com を招待する          |Sip:4255550100@sbc.contoso.com を招待する       |OutboundPSTNNumberTranlationRulesList 'StripPlus1'         |
|宛先    |宛先: \<sip:+14255550100@sbc.contoso.com>|宛先: \<sip:4255555555@sbc.contoso.com>|OutboundPSTNNumberTranlationRulesList 'StripPlus1'       |
|差出人   |差出人: \<sip:+12065550100@sbc.contoso.com>|差出人: \<sip:2065550100@sbc.contoso.com>|Outboundteamsnumber/Ationルールリスト ' StripPlus1 '         |

#### <a name="example-4-outbound-call-using-a-four-digit-non-e164-number"></a>例 4: 4 桁以外の番号を使用した発信通話

アリスは、4桁の数字を使ってボブを呼び出します。 アリスは、0100を使って、通話から、または連絡先を使ってボブに連絡します。
SBC は、Teams ユーザーと PSTN ユーザー用に10桁の4桁の番号を使用するように構成されています。 このシナリオでは、ダイヤルプランは適用されません。

|Header  |翻訳元 |翻訳済みヘッダー |パラメーターとルールの適用  |
|---------|---------|---------|---------|
|RequestURI  |Sip:0100@sbc.contoso.com を招待する           |Sip:4255550100@sbc.contoso.com を招待する       |InboundTeamsNumberTranlationRulesList 'AddSeattleAreaCode'         |
|宛先    |宛先: \<sip:0100@sbc.contoso.com>|宛先: \<sip:4255555555@sbc.contoso.com>|InboundTeamsNumberTranlationRulesList 'AddSeattleAreaCode'       |
|差出人   |差出人: \<sip:+12065550100@sbc.contoso.com>|差出人: \<sip:2065550100@sbc.contoso.com>| InboundPSTNNumberTranlationRulesList 'StripPlus1' |

## <a name="see-also"></a>関連項目

[ダイレクト ルーティングを計画する](direct-routing-plan.md)
