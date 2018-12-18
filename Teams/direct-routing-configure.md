---
title: 直接ルーティングを構成する
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.service:
- msteams
- skype-for-business-online
ms.prod: skype-for-business-itpro
localization_priority: Normal
search.appverid: MET150
ms.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
description: Microsoft 電話システム直接ルーティングを構成する方法について説明します。
ms.openlocfilehash: cf856989cd4f87f4b46e1eb36cbeb403bf92b029
ms.sourcegitcommit: 8279beffec35fe8a75968245c6cb09f1d622370f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/18/2018
ms.locfileid: "27297912"
---
# <a name="configure-direct-routing"></a>直接ルーティングを構成する

> [!Tip]
> ルーティング、それを計画する方法と展開方法は、直接の利点について説明するのには次のセッションを監視する:[マイクロソフトのチームに直接ルーティング](https://aka.ms/teams-direct-routing)

されていない場合は、前提条件の[直接ルーティングの計画](direct-routing-plan.md)が読み込まれ、他の手順を確認する必要があります、Microsoft の電話システムのネットワークを構成する前にします。 

この資料では、マイクロソフト電話システム直接ルーティングを構成する方法について説明します。 ペア、サポートされているセッション ボーダー コント ローラー (SBC) に直接ルーティングする方法とを公衆交換電話網 (PSTN) を接続するのには直接ルーティングを使用するマイクロソフトのチームのユーザーを構成する方法を説明します。 この資料で説明した手順を完了するには、管理者には、PowerShell コマンドレットをある程度が必要があります。 PowerShell を使用の詳細については、 [Windows PowerShell には、コンピューターの設定](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)を参照してください。 

SBC が、SBC の製造元の推奨どおりに構成されて既にいることを確認することをお勧めします。 

- [展開に関するドキュメント](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [リボンの通信の展開に関するドキュメント](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)

マイクロソフト電話システムを構成して、直接ルーティングを使用し、マイクロソフトのチームを次の手順を完了しての優先呼び出し側のクライアントとして設定するユーザーを有効にすることができます。 

- [マイクロソフトの電話システムと SBC のペアし、ペアを検証します。](#pair-the-sbc-to-direct-routing-service-of-phone-system)
- [直接ルーティング サービスのユーザーを有効にします。](#enable-users-for-direct-routing-service)
- [マイクロソフトのチームが、ユーザーの優先呼び出し側のクライアントであることを確認します。](#set-microsoft-teams-as-the-preferred-calling-client-for-users) 

## <a name="pair-the-sbc-to-direct-routing-service-of-phone-system"></a>電話システムのルーティング サービスを指示する SBC をペアします。 

使用すると、接続、または直接ルーティング インターフェイスに SBC とペアにするには次の 3 つの大まかな手順は、次のように。 

- PowerShell を使用して、 **Skype**管理センターへの接続します。 
- SBC のペア 
- ペアを検証します。 

### <a name="connect-to--skype-for-business-online-by-using-powershell"></a>PowerShell を使用して、オンライン ビジネスの Skype に接続します。 

直接ルーティング インターフェイスに SBC をペアにするには、テナントに接続している PowerShell セッションを使用できます。 PowerShell セッションを開くには、するには、 [Windows PowerShell には、コンピューターの設定](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)で説明する手順に従ってください。 
 
リモート PowerShell セッションを確立すると後を検証してください、SBC を管理するためにコマンドを表示することができます。 コマンドを検証するには、入力または PowerShell セッションで次のコピーと貼り付けし Enter キーを押します。 

```
gcm *onlinePSTNGateway*
```

コマンドでは、ここで示すように、半角を管理できるようになる 4 つの関数を返します。 

<pre>
CommandType    Name                       Version    Source 
-----------    ----                       -------    ------ 
Function       Get-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt 
Function       New-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt 
Function       Remove-CsOnlinePSTNGateway 1.0        tmp_v5fiu1no.wxt 
Function       Set-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt
</pre>   


### <a name="pair-the-sbc-to-the-tenant"></a>テナントに SBC の組み合わせ 

テナントに SBC とペアに PowerShell セッションで次を入力し、Enter キーを押します。 

```
New-CsOnlinePSTNGateway -Fqdn <SBC FQDN> -SipSignallingPort <SBC SIP Port> -MaxConcurrentSessions <Max Concurrent Sessions the SBC can handle> -Enabled $true 
```
  > [!NOTE]
  > 1. 強くお勧め、SBC の制限を設定する SBC のドキュメントで使用されている情報を使用します。 SBC の能力のレベルにある場合、制限は通知をトリガーします。
  > 2. FQDN で、名前のドメイン部分と一致する以外は、テナントに登録するドメインのいずれかで SBC はペアのみ\*. onmicrosoft.com。 使用して\*. SBC の FQDN 名では、omicrosoft.com ドメイン名はサポートされていません。 たとえば、2 つのドメイン名があるとします。<br/><br/>
  > **contoso**.com<br/>**contoso**onmicrosoft.com。<br/><br/>
  > SBC 名の名前の sbc.contoso.com を使用できます。 名 sbc.contoso.abc を持つ SBC のペアにしようとすると、システムは動かせません、このテナントは、ドメインを所有していないようです。

```
New-CsOnlinePSTNGateway -Identity sbc.contoso.com -Enabled $true -SipSignallingPort 5067 -MaxConcurrentSessions 100 
```
返します。
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
ペアリング中に設定できるその他のオプションがあります。 前の例では、ただし、のみ、最低限必要なパラメーターが表示されます。 
 
*新規 CsOnlinePstnGateway*のパラメーターを設定するのに使用できる追加のパラメーターを次の表に一覧します。 

|必須。|名前|説明|Default|可能な値|種類と制限|
|:-----|:-----|:-----|:-----|:-----|:-----|
|あり|FQDN|SBC の FQDN 名 |なし|NoneFQDN 名、制限は 63 文字|文字列、[コンピューター、ドメイン、サイト、および Ou の Active Directory の名前付け規則](https://support.microsoft.com/help/909264)で許可の文字の一覧|
|なし|MediaBypass |将来使用するために予約されているパラメーターです。 SBC の示されているパラメーターには、メディア バイ パスがサポートされていて、管理者がそれを使用します。|なし|True<br/>False|ブール型|
|あり|SipSignallingPort |トランスポート層セキュリティ (TLS) プロトコルを使用して直接ルーティング サービスと通信するために使用するポートをリッスンします。|なし|任意のポート|0 から 65535 まで |
|なし|FailoverTimeSeconds |10 (既定値) に設定すると、10 秒以内に、ゲートウェイが応答しない送信の呼び出しにルーティングされる次の使用可能なトランクです。トランクを追加することはありません、し、呼び出しは自動的に削除します。 低速のネットワークとゲートウェイの応答を持つ組織内を可能性があります可能性のある呼び出しが不必要に削除されています。 既定値は 10 です。| 10|数値|Int|
|なし|ForwardCallHistory |通話履歴の情報をトランク経由で転送するかどうかを指定します。 Office 365 の PSTN のプロキシに 2 つのヘッダーが送信が有効な場合: 履歴情報と Referred で。 既定値は**False** ($False) です。 |False|True<br/>False|ブール型|
|なし|ForwardPAI|P-Asserted-Identity (PAI) ヘッダーを通話とともに転送するかどうかを示します。 PAI ヘッダーがあれば、発信者 ID を確認できます。 既定値は**False** ($False) です。|False|True<br/>False|ブール型|
|なし|SendSIPOptions |SBC または SIP オプションを送信しない場合を定義します。 無効にした場合、SBC は、監視と警告のシステムから除外されます。 SIP オプションを有効にすることを強くお勧めします。 既定値は**True**です。 |True|True<br/>False|ブール型|
|なし|MaxConcurrentSessions |警告システムによって使用されます。 同時セッションの数が 90% の場合、アラート ・ システム、テナント管理者にアラートを生成の任意の値を設定すると、この値よりも大きいか。 パラメーターが設定されていない場合、アラートは生成されません。 ただし、監視システムは 24 時間ごとの同時セッションの数を報告します。 |Null|Null<br/>1 ~ 100,000 ||
|なし|有効になっている *|発信呼のこの SBC を有効にする場合に使用されます。 メンテナンス中または更新中に、SBC を一時的に削除するために使用します。 |False|True<br/>False|ブール型|
 
### <a name="verify-the-sbc-pairing"></a>SBC の組み合わせを確認します。 

接続を確認します。 
- SBCs のペアのリストに、SBC があるかを確認してください。 
- SIP オプションを検証します。 
 
#### <a name="validate-if-sbc-is-on-the-list-of-paired-sbcs"></a>SBCs のペアのリストには、SBC の場合を検証します。 

SBC のペアであることを確認、SBC SBCs のペアのリストに存在リモート PowerShell セッションで次のコマンドを実行しています。`Get-CSOnlinePSTNGateway`

ペアのゲートウェイは、次の例に示すように、一覧に表示し、パラメーターを*有効*に**は True**の値が表示されることを確認ください。 入力します。

```
Get-CsOnlinePSTNGateway -Identity sbc.contoso.com  
```
返します。
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

#### <a name="validate-sip-options-flow"></a>SIP オプションのフローを検証します。 

送信 SIP オプションを使用しての組み合わせを検証するには、SBC の管理インターフェイスを使用し、SBC が送信のオプションを 200 OK 応答を取得するを参照してください。
  
直接ルーティングでは、受信オプションが表示される、オプションの受信メッセージの連絡先ヘッダー フィールドで構成されている SBC の FQDN を送信のオプションを送信を開始します。 

着信 SIP オプションを使用しての組み合わせを検証するには、SBC の管理インターフェイスを使用し、SBC がから直接ルーティング オプションのメッセージに応答を取得し、応答コードが 200 [ok] を参照してください。  

## <a name="enable-users-for-direct-routing-service"></a>直接ルーティング サービスのユーザーを有効にします。 

直接ルーティング サービスに対してユーザーを有効にする準備ができたら、次の手順に従います。 

1. Office 365 にユーザーを作成し、電話システムのライセンスを割り当てます。 
2. ビジネス オンラインの Skype のユーザーのホームすることを確認します。 
3. 電話番号を構成し、エンタープライズ ボイスとボイス メールを有効にします。 
4. 音声ルーティングを構成します。 ルートが自動的に検証されます。  

### <a name="create-a-user-in-office-365-and-assign-the-license"></a>Office 365 にユーザーを作成し、ライセンスの割り当てください 

Office 365 で新しいユーザーを作成するための 2 つのオプションがあります。 ただし、組織が選択し、1 つのオプションを使用して、ルーティングの問題を回避することお勧めします。 

- オンプレミスの Active Directory でユーザーを作成し、ユーザーがクラウドを同期します。 [Azure Active Directory と統合、設置ディレクトリ](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect)を参照してください。  
- Office 365 管理者ポータルで直接ユーザーを作成します。 [追加ユーザー個別にまたは一括で Office 365 の管理者のヘルプ](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec)を参照してください。 

  ビジネス 2015年または Lync 2010 と 2013 の設置型の Skype と共存するシステムを構築する場合のみサポートされているオプションは、オンプレミスの Active Directory でユーザーを作成し、(オプション 1) をクラウドに移行するユーザーを同期するのには。 

必須ライセンス: 

- Office 365 エンタープライズ E3 (デバイス Plan2、Plan2 の交換、チームを含む) 電話システム  
- Office 365 エンタープライズ E5 (デバイス Plan2、Plan2 の交換、チーム、および電話システムを含む) 

オプションのライセンス数: 

- 計画を呼び出す 
- 電話会議 

### <a name="ensure-that-the-user-is-homed-in-skype-for-business-online"></a>ビジネス オンラインの Skype のユーザーが所属していることを確認します。 

直接ルーティングでは、Skype でのオンライン ビジネスのホーム ユーザーが必要です。 これを確認するには、RegistrarPool パラメーターを参照しています。 Infra.lync.com ドメイン内の値を設定する必要があります。

1. リモート PowerShell に接続します。
2. コマンドを発行します。 

```
Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool
``` 

### <a name="configure-the-phone-number-and-enable-enterprise-voice-and-voicemail"></a>電話番号を構成し、エンタープライズ ボイスとボイス メールを有効にします。 

ユーザーを作成すると、次の手順は、電話番号やボイス メールを構成するのには、ライセンスが割り当てられています。 これは、1 つのステップで実行できます。 

電話番号を追加し、ボイス メールを有効にします。
 
1. リモート PowerShell セッションに接続します。 
2. コマンドを入力します。 
    
```
Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI tel:+ phone number
```

たとえば、「Spencer 低」のユーザーの電話番号を追加するのにはするは、次のように入力します。 

```
Set-CsUser -Identity “Spencer Low" -OnPremLineURI tel:+14255388797 -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
```

電話番号に国コードを含む完全 E.164 電話番号として構成するのには。 

  > [!NOTE]
  > ユーザーの電話番号が施設内で管理されている場合は、ユーザーの電話番号を構成するのにはビジネス管理シェルまたはコントロール パネルの設置型の Skype を使用します。 

### <a name="configure-voice-routing"></a>音声ルーティングを構成します。 

マイクロソフトの電話システムに基づく特定の SBC に送られる呼び出しを可能にするためのルーティング メカニズムがあります。 

- 番号のパターンと呼ばれる 
- 番号のパターン + 呼び出しでは、特定のユーザーと呼ばれます。
 
SBCs は、アクティブとバックアップとして指定できます。 この番号のパターンまたはパターンの番号 + 特定のユーザーに対してアクティブに設定されている SBC が使用できない場合を意味し、呼び出しは、バックアップの SBC にルーティングされます。
 
通話のルーティングは、次の要素で構成されています。 
- 音声ルーティング ポリシー – PSTN の使用法のためのコンテナーユーザーまたは複数のユーザーに割り当てることができます。 
- PSTN 使用法: ボイス ルートと PSTN の使用法のためのコンテナー別の音声ルーティング ポリシーで共有することができます。 
- ボイス ルート – 番号のパターンと、パターンに一致する番号を呼び出す呼び出しに使用するオンラインの PSTN ゲートウェイの設定 
- オンラインの PSTN ゲートウェイ、SBC、ポインター、前方の P アサートされた Id (PAI) や優先のコーデックなど、SBC を使用して電話をかけるときに適用される設定を格納します。ボイス ルートを追加することができます。 

#### <a name="creating-a-voice-routing-policy-with-one-pstn-usage"></a>PSTN 使用法の 1 つの音声ルーティング ポリシーを作成します。 

次の図は、呼び出しの流れの音声ルーティング ポリシーの 2 つの例を示します。

**(左側) のフロー 1 の呼び出し:** SBC sbc1 に通話をルーティングする場合は +1 425 XXX XX XX または +1 206 XXX XX XX への呼び出しを行うと、<span></span>です。 contoso.biz または sbc2<span></span>です。 contoso.biz です。 場合も sbc1<span></span>です。 contoso.biz や sbc2<span></span>。 contoso.biz がある、呼び出しは破棄されます。 

**(右側) のフロー 2 の呼び出し:**+1 425 XXX XX XX または +1 206 XXX XX XX への呼び出しを行うと、呼び出しが最初にルーティング SBC sbc1 を<span></span>. contoso.biz または sbc2<span></span>です。 contoso.biz です。 SBC のどちらが使用可能な場合は、優先度の低いルートが試行されます (sbc3<span></span>です。 contoso.biz と sbc4<span></span>です。 contoso.biz)。 SBCs の [なし] がある場合、呼び出しは破棄されます。 

![音声ルーティング ポリシーの例を示しています。](media/ConfigDirectRouting-VoiceRoutingPolicyExamples.png)

どちらの例では、ボイス ルートは、優先順位を割り当てられている間、ルートの SBCs はランダムな順序で試行されます。

  > [!NOTE]
  > ユーザーもライセンスを持つ、Microsoft の計画を呼び出すことをしない限り、番号が一致するパターン + +1 425 XXX XX XX または構成の例で +1 206 の XXX XX XX 以外の任意の番号への呼び出しは削除されます。 ユーザーのライセンス計画を呼び出す場合は、呼び出しは自動的にマイクロソフトを呼び出す予定のポリシーに従ってルーティングされます。 

マイクロソフトを呼び出す計画では、Microsoft の計画を呼び出してライセンスを持つすべてのユーザーに最後のルートとしてには、自動的に適用され、追加の呼び出しのルーティングの構成は必要ありません。

例では、次の図に示すように、すべての他の米国およびカナダ番号 (番号のパターンと呼ばれる +1 XXX XXX XX XX に行われる呼び出し) への呼び出しを送信するボイス ルートが追加されます。

![番組音声の 3 つ目のルートをルーティング ポリシー](media/ConfigDirectRouting-VoiceRoutingPolicywith3rdroute.png)

他のすべての呼び出しでは、ユーザーは、(マイクロソフトの電話システムと Microsoft の計画を呼び出す)、両方のライセンスを持っている場合、自動工順が使用されます。 何もには、管理者が作成したオンラインでのボイス ルートの番号のパターンが一致すると、Microsoft の計画を呼び出すを使用してルーティングします。

ユーザーは、マイクロソフトの電話システムのみがある、一致する規則がないために、呼び出しが切断されます。

  > [!NOTE]
  > 「+1 その他の」ルートの優先順位の値 +1 のパターンに一致する 1 つだけのルートがある、この例では、関係ありません XXX XXX XX XX。 +1 324 の 567 89 89 への呼び出しを行うと、sbc5.contoso.biz と sbc6.contoso.biz の両方が使用できない場合は、呼び出しは破棄されます。

次の表では、3 つのボイス ルートを使用して設定をまとめたものです。 この例では、すべての 3 つのルートは、同じ PSTN 使用法米国およびカナダの一部です。

|**PSTN 使用法**|**ボイス ルート**|**番号パターン**|**優先度**|**SBC**|**説明**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|米国のみ|「Redmond 1」|^\\+1 (425\|206)(\d{7})$|1|sbc1<span></span>です contoso.biz。<br/>sbc2<span></span>です contoso.biz。|+1 425 XXX XX XX または +1 206 XXX XX XX の呼び出された番号の有効な工順|
|米国のみ|"Redmond 2"|^\\+1 (425\|206)(\d{7})$|2|sbc3<span></span>です contoso.biz。<br/>sbc4<span></span>です contoso.biz。|+1 425 XXX XX XX または +1 206 XXX XX XX の呼び出された番号のバックアップ ルート|
|米国のみ|「その他の +1」|^\\+1 (\d{10}) $|3|sbc5<span></span>です contoso.biz。<br/>sbc6<span></span>です contoso.biz。|呼ばれる数字の +1 XXX XXX の XX XX (+1 425 XXX XX XX +1 206 XXX XX XX 以外) をルーティングします。|
|||||||

すべてのルートは、米国およびカナダの PSTN 使用法に関連付けられているし、は、音声ルーティング ポリシー「u. s. だけです」に関連付けられている PSTN 使用法 この例では、音声ルーティング ポリシーは Spencer 低のユーザーに割り当てられます。

#### <a name="examples-of-call-routes"></a>呼び出しのルーティングの例

次の例では、ルート、PSTN の使用法、およびルーティング ポリシーを構成する方法について説明し、ユーザーにポリシーを割り当てます。

**手順 1:** PSTN の使用「米国とカナダ」を作成します。

ビジネス リモート PowerShell セッションを Skype では、次のように入力します。

```
Set-CsOnlinePstnUsage  -Identity Global -Usage @{Add="US and Canada"}
```

使用状況が入力することにより作成されたものであることを検証します。 
```
Get-CSOnlinePSTNUsage
``` 
切り捨てられる可能性がありますの名前の一覧を返します。
```
  Identity  : Global
  Usage     : {testusage, US and Canada, International, karlUsage. . .}
```
次の例では、実行中の結果を確認できます PowerShell コマンド*`(Get-CSOnlinePSTNUsage).usage`*(切り捨てではない) 完全な名前を表示します。    
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

**手順 2:** ビジネス オンラインの Skype の PowerShell セッションで次の 3 つのルートを作成: 上記の表に示すとおり、レッドモンド 1、2、およびその他の + 1 のレドモンド。 

「Redmond 1」のルートを作成するには、次コマンドを入力します。

  ```
  New-CsOnlineVoiceRoute -Identity "Redmond 1" -NumberPattern "^\+1(425|206)
  (\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
  ```

返します。
<pre>
Identity                : Redmond 1
Priority            : 1
Description         :
NumberPattern       : ^\+1(425|206) (\d{7})$
OnlinePstnUsages    : {US and Canada}
OnlinePstnGatewayList   : {sbc1.contoso.biz, sbc2.contoso.biz}
Name            : Redmond 1
SuppressCallerId    :
AlternateCallerId   :
</pre>
レドモンド 2 ルートを作成するには、次のコマンドを入力します。

```
New-CsOnlineVoiceRoute -Identity "Redmond 2" -NumberPattern "^\+1(425|206)
(\d{7})$" -OnlinePstnGatewayList sbc3.contoso.biz, sbc4.contoso.biz -Priority 2 -OnlinePstnUsages "US and Canada"
```

+1 で他のルートを作成するには、次のコマンドを入力します。

```
New-CsOnlineVoiceRoute -Identity "Other +1" -NumberPattern "^\+1(\d{10})$"
-OnlinePstnGatewayList sbc5.contoso.biz, sbc6.contoso.biz -OnlinePstnUsages "US and Canada"
```

  > [!CAUTION]
  > [NumberPattern] 属性には、正規表現が有効な式であることを確認してください。 この web サイトを使用することをテストすることができます。[https://www.regexpal.com](https://www.regexpal.com)

場合によっては、同じの SBC はすべての呼び出しをルーティングする必要があります。-NumberPattern を使用してください」. *"

- 同じ SBC へのすべての呼び出しをルーティングします。

    ```
    Set-CsOnlineVoiceRoute -id "Redmond 1" -NumberPattern ".*" 
     -OnlinePstnGatewayList sbc1.contoso.biz
    ```

正しく構成したルートを実行して、検証、 `Get-CSOnlineVoiceRoute` Powershell コマンドのようにオプションを使用します。 

```
Get-CsOnlineVoiceRoute | Where-Object {($_.priority -eq 1) -or ($_.priority -eq 2) or ($_.priority -eq 4) -Identity "Redmond 1" -NumberPattern "^\+1(425|206) (\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```
次の項目を返す必要があります。
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

例では、ルート「その他の +1」が優先順位を自動的に割り当てられます。 

**手順 3:**「私たちだけ」音声ルーティング ポリシーを作成し、「米国とカナダ」PSTN の使用法をポリシーに追加

ビジネス オンラインの Skype の PowerShell セッションで次のように入力します。

```
New-CsOnlineVoiceRoutingPolicy "US Only" -OnlinePstnUsages "US and Canada"
```

結果は、次の使用例で示されます。

<pre>
Identity        : Tag:US only
OnlinePstnUsages    : {US and Canada}
Description         :
RouteType           : BYOT
</pre>

**手順 4:** PowerShell を使用して、音声ルーティング ポリシーを Spence 低のユーザーに付与します。

- ビジネス オンラインの Skype の Powershell セッションで次のように入力します。

    ```Grant-CsOnlineVoiceRoutingPolicy -Identity "Spencer Low" -PolicyName "US Only"```

- このコマンドを入力して、ポリシーの割り当てを検証します。

```
Get-CsOnlineUser "Spencer Low" | select OnlineVoiceRoutingPolicy
```
返します。
<pre>
    OnlineVoiceRoutingPolicy
    ---------------------
    US Only
</pre>

#### <a name="creating-a-voice-routing-policy-with-several-pstn-usages"></a>PSTN 使用法のいくつかの音声ルーティング ポリシーを作成します。

音声ルーティング ポリシーを作成以前のみでは、米国およびカナダ - 電話番号への呼び出し Microsoft の計画を呼び出してライセンスがユーザーにも割り当てられている場合を除き、します。

次の例で作成できます音声ルーティング ポリシー「制限なし」です。 ポリシーは、米国およびカナダで新しい PSTN 使用法国際。」と、前の例では、作成した PSTN 使用法を再利用します。 

SBCs sbc2 他のすべての呼び出しをルーティングするこの<span></span>です。 contoso.biz と sbc5<span></span>です。 contoso.biz です。 示されている例を付ける [Spencer 低"のユーザーにポリシーでは u. s. のみと制限のないユーザー「John 森」です。

Spencer 低: 米国およびカナダの番号にのみ許可される呼び出しです。 レドモンドの番号の範囲を呼び出すと、SBC の特定のセットを使用する必要があります。 計画を呼び出してライセンスがユーザーに割り当てられている場合を除き、米国以外の数値はルーティングされません。

ジョンの森 – 呼び出しは、任意の数を許可しました。 レドモンドの番号の範囲を呼び出すと、SBC の特定のセットを使用する必要があります。 米国以外の番号は、sbc2 経由でルーティングされます<span></span>です。 contoso.biz と sbc5<span></span>です。 contoso.biz です。

![Spencer 低のユーザーに割り当てられている音声のルーティング ポリシーを示しています。](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoSpencerLow.png)

他のすべての呼び出しでは、ユーザーは、(マイクロソフトの電話システムと Microsoft の計画を呼び出す)、両方のライセンスを持っている場合、自動工順が使用されます。 何もには、管理者が作成したオンラインでのボイス ルートの番号のパターンが一致すると、Microsoft の計画を呼び出すを使用してルーティングします。

ユーザーは、マイクロソフトの電話システムのみがある、一致する規則がないために、呼び出しが切断されます。

![音声ルーティング ポリシーのユーザー John の森に割り当てられているを示しています。](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoJohnWoods.png)

次の表は、ルーティング ポリシー「制限なし」の使用の指定、およびボイス ルートをまとめたものです。 

|**PSTN 使用法**|**ボイス ルート**|**番号パターン**|**優先度**|**SBC**|**説明**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|米国のみ|「Redmond 1」|^\\+1 (425\|206)(\d{7})$|1|sbc1<span></span>です contoso.biz。<br/>sbc2<span></span>です contoso.biz。|+1 425 XXX XX XX または +1 206 XXX XX XX 番号が呼び出し先の有効な工順|
|米国のみ|"Redmond 2"|^\\+1 (425\|206)(\d{7})$|2|sbc3<span></span>です contoso.biz。<br/>sbc4<span></span>です contoso.biz。|+1 425 XXX XX XX または +1 206 XXX XX XX 番号が呼び出し先のバックアップ ルート|
|米国のみ|「その他の +1」|^\\+1 (\d{10}) $|3|sbc5<span></span>です contoso.biz。<br/>sbc6<span></span>です contoso.biz。|呼び出し先のルートの番号 +1 XXX XXX の XX XX (+1 425 XXX XX XX または +1 206 XXX XX XX) を除く|
|International|International|\d+|4|sbc2<span></span>です contoso.biz。<br/>sbc5<span></span>です contoso.biz。|任意の番号のパターンのルート |


  > [!NOTE]
  > - 音声ルーティング ポリシーの PSTN 使用法の順序は重要です。 順番については、使用法が適用され、最初の使用で一致が見つかった場合、その他の方法は評価されません。 PSTN 使用法「国際」する必要があります後に配置される PSTN 使用法」ことだけです」 PSTN 使用法の順序を変更するを実行してください、`Set-CSOnlineRouteRoutingPolicy`コマンドです。 <br/>たとえば、米国およびカナダからの順序を変更する順序とは逆に国際化し、最初の 2 番目を実行します。<br/>   `Set-CsOnlineVoiceRoutingPolicy -id tag:"no Restrictions" -OnlinePstnUsages @{Replace="International", "US and Canada"}`
 > - 「その他の +1」と「国際」ボイス ルートの優先順位は自動的に割り当てられます。 「Redmond 1」と「レドモンド 2」よりも低い優先順位がある限り、問題でない

#### <a name="example-of-voice-routing-policy-for-user-john-woods"></a>ユーザー John の森の音声ルーティング ポリシーの例

PSTN 使用法「国際」を作成する手順はルーティング ポリシー制限のなし」、「音声ボイス ルート「国際」とは、次ように、それを「ジョンの森"のユーザーに割り当てます。


1. 国際「PSTN 使用法を最初に、作成 ビジネス オンラインの Skype のリモート PowerShell セッションで次のコマンドを入力します。

   ```
   Set-CsOnlinePstnUsage  -Identity Global -Usage @{Add="International"}
   ```

2. 国際"次に、新しいボイス ルートを作成します。

   ```
   New-CsOnlineVoiceRoute -Identity "International" -NumberPattern "\d+" -OnlinePstnGatewayList sbc2.contoso.biz, sbc5.contoso.biz -OnlinePstnUsages "International"
   ```
   返します。

   <pre>
   Identity                  : International 
   Priority                      : 5
   Description                   : 
   NumberPattern                 : \d+
   OnlinePstnUsages          : {International}    
   OnlinePstnGatewayList           : {sbc2.contoso.biz, sbc5.contoso.biz}
   Name                            : International
   SupressCallerId           :
   AlternateCallerId         :
   </pre>
3. 次に、「制限なし」の音声ルーティング ポリシーを作成します。 ローカルまたはオンプレミスの呼び出しとして「+1 425 XXX XX XX」と"+1 206 XXX XX XX"番号への呼び出しに特別な処理を保持するのにはこの音声ルーティング ポリシーでは、PSTN 使用法"Redmond 1"と"Redmond"が再利用します。

```
New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", ”International”
```

    Take note of the order of PSTN Usages:

    a. If a call made to number “+1425 XXX XX XX” with the usages configured as in the following example, the call follows the route set in “US and Canada” usage and the special routing logic is applied. That is, the call is routed using  sbc1<span></span>.contoso.biz and sbc2<span></span>.contoso.biz first, and then  sbc3<span></span>.contoso.biz and sbc4<span></span>.contoso.biz as the backup routes. 

    b.  If “International” PSTN usage is before “US and Canada,” calls to + 1425 XXX XX XX are routed to sbc2<span></span>.contoso.biz and sbc5<span></span>.contoso.biz as part of the routing logic. Enter the command:

    ```New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", ”International”```

   返します。

  <pre>
   Identity     : International 
   OnlinePstnUsages     : {US and Canada, International}     
   Description      :  
   RouteType        : BYOT
  </pre>

4. ユーザー「John 森」次のコマンドを使用するには、音声ルーティング ポリシーを割り当てます。

   ```
   Grant-CsOnlineVoiceRoutingPolicy -Identity "John Woods" -PolicyName "No Restrictions”
   ```

   コマンドを使用して割り当てを確認します。   

   ```
   Get-CsOnlineUser “John Woods” | Select OnlineVoiceRoutingPolicy
   ```
   返します。

<pre>
    OnlineVoiceRoutingPolicy
    ------------------------
    No Restrictions
</pre>

結果は、ジョンの森の呼び出しに適用されるボイス ポリシーは、制限はありませんしは米国、カナダ、および国際通話に使用できる通話のルーティングのロジックに従います。

## <a name="set-microsoft-teams-as-the-preferred-calling-client-for-users"></a>マイクロソフトのチームを優先する呼び出し元クライアントとユーザーの設定します。

直接ルーティング ルートのみを呼び出しのユーザーとの間のチームのクライアントを使用する場合。 のみ、組織には、チームが使用しているチームのみ] 設定モードでのアップグレードのポリシーを推奨します。 詳細については次の資料を参照してくださいし、適切なオプションを選択する組織は、オンライン ビジネスのビジネス サーバーまたは Skype の Skype を使用する場合:[共存を理解しビジネスとチームの Skype の旅をアップグレード](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype)します。 


## <a name="see-also"></a>関連項目

[ダイレクト ルーティングを計画する](direct-routing-plan.md)
