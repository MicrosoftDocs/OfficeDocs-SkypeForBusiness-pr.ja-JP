---
title: セッション境界のコントローラー (SBC) を直接ルーティングに接続する
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
description: Microsoft Phone システムのダイレクトルーティングを構成する方法について説明します。
ms.openlocfilehash: e86b0397e4c00b892d99a0814579f20ba14e8b59
ms.sourcegitcommit: 0289062510f0791906dab2791c5db8acb1cf849a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/20/2020
ms.locfileid: "42157987"
---
# <a name="connect-your-session-border-controller-sbc-to-direct-routing"></a>セッション境界のコントローラー (SBC) を直接ルーティングに接続する 

この記事では、セッションボーダーコントローラー (SBC) を電話システムのダイレクトルーティングに接続する方法について説明します。  これは、次の手順の手順1で、直接ルーティングを構成します。

- **手順1お使いの SBC を電話システムに接続して接続を検証する**(この記事)
- 手順2 [ユーザーが直接ルーティングできるようにする](direct-routing-enable-users.md)
- 手順3 [通話ルーティングの構成](direct-routing-voice-routing.md)
- 手順4。 [数値を別の形式に変換する](direct-routing-translate-numbers.md) 

直接ルーティングを設定するために必要なすべての手順については、「[直接ルーティングを構成する](direct-routing-configure.md)」を参照してください。

SBC をダイレクトルーティングに接続するには、次の操作を行う必要があります。 

1. PowerShell を使用して、 **Skype For Business Online**管理センターに接続します。            
2. SBC をテナントに接続します。
3. 接続を確認します。 

## <a name="connect-to-skype-for-business-online-by-using-powershell"></a>PowerShell を使用して Skype for Business Online に接続する 

テナントに接続された PowerShell セッションを使って、SBC とダイレクトルーティングインターフェイスをペアリングすることができます。 PowerShell セッションを開くには、「 [Windows powershell 用にコンピューターを](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)セットアップする」の手順に従ってください。 
 
リモート PowerShell セッションを確立したら、SBC を管理するためのコマンドが表示されることを確認します。 コマンドを検証するには、PowerShell セッションで次のコマンドを入力するか、コピーして貼り付け、enter キーを押します。 

```PowerShell
Get-Command *onlinePSTNGateway*
```

このコマンドは、SBC を管理できるように、次の4つの関数を返します。 

<pre>
CommandType    Name                       Version    Source 
-----------    ----                       -------    ------ 
Function       Get-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt 
Function       New-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt 
Function       Remove-CsOnlinePSTNGateway 1.0        tmp_v5fiu1no.wxt 
Function       Set-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt
</pre>   


## <a name="connect-the-sbc-to-the-tenant"></a>SBC をテナントに接続する 

SBC をテナントに接続するには、PowerShell セッションで次のように入力し、enter キーを押します。 

```PowerShell
New-CsOnlinePSTNGateway -Fqdn <SBC FQDN> -SipSignalingPort <SBC SIP Port> -MaxConcurrentSessions <Max Concurrent Sessions the SBC can handle> -Enabled $true 
```
  > [!NOTE]
  > 1. Microsoft は、sbc ドキュメントに記載されている情報を使用して、SBC で最大限の通話制限を設定することをお勧めします。 SBC がキャパシティレベルにある場合、制限によって通知がトリガーされます。
  > 2. SBC をペアリングできるのは、その FQDN のドメイン部分が、テナントに登録されているドメインのいずれ\*かに一致している場合のみです。 onmicrosoft.com を除きます。 \*Onmicrosoft.com ドメイン名は、SBC FQDN 名ではサポートされていません。 たとえば、2つのドメイン名がある場合は、次のようになります。<br/><br/>
  > **contoso**.com<br/>**** onmicrosoft.com<br/><br/>
  > SBC 名には、sbc.contoso.com という名前を使用できます。 SBC と名前 sbc をペアリングしようとしても、ドメインはこのテナントによって所有されていないため、システムによっては許可されません。<br/>
  > テナントに登録されているドメインに加えて、そのドメインを持つユーザーと E3 または E5 ライセンスが割り当てられていることが重要です。 存在しない場合、次のエラーが表示されます。<br/>
  `Can not use the “sbc.contoso.com” domain as it was not configured for this tenant`.

```PowerShell
New-CsOnlinePSTNGateway -Identity sbc.contoso.com -Enabled $true -SipSignalingPort 5067 -MaxConcurrentSessions 100 
```
返し
<pre>
Identity              : sbc.contoso.com 
Fqdn                  : sbc.contoso.com 
SipSignalingPort     : 5067 
FailoverTimeSeconds   : 10 
ForwardCallHistory    : False 
ForwardPai            : False 
SendSipOptions        : True 
MaxConcurrentSessions : 100 
Enabled               : True   
</pre>
接続プロセス中に設定できるその他のオプションがあります。 ただし、前の例では、必須の最小パラメーターのみが表示されています。 
 
次の表は、の```New-CsOnlinePstnGateway```パラメーターの設定に使用できるその他のパラメーターを示しています。

|必須。|名前|説明|既定|可能な値|種類と制限|
|:-----|:-----|:-----|:-----|:-----|:-----|
|はい|FQDN|SBC の FQDN 名 |なし|NoneFQDN 名、63文字を制限する|[コンピューター、ドメイン、サイト、および ou の Active Directory の名前付け規則](https://support.microsoft.com/help/909264)での文字列、許可されている文字および禁止されている文字の一覧|
|いいえ|MediaBypass |は、SBC でサポートされているメディアバイパスのパラメーターであり、管理者はこのパラメーターを使いたいと考えています。|なし|True<br/>False|Boolean|
|はい|SipSignalingPort |トランスポート層セキュリティ (TLS) プロトコルを使用した、直接ルーティングサービスとの通信に使用するリスニングポート。|なし|任意のポート|0 ~ 65535 |
|いいえ|FailoverTimeSeconds |10 (既定値) に設定すると、ゲートウェイによって応答されない送信通話は、次の利用可能なトランクにルーティングされます。追加の trunks がない場合、通話は自動的に切断されます。 低速のネットワークとゲートウェイ応答を使用している組織では、通話が不必要に削除される可能性があります。 既定値は10です。|常用|数値|Int|
|いいえ|ForwardCallHistory |通話履歴の情報をトランク経由で転送するかどうかを指定します。 有効になっている場合、Office 365 PSTN プロキシは、2つのヘッダー (履歴-情報と参照) を送信します。 既定値は**False** ($False) です。 |False|True<br/>False|Boolean|
|いいえ|ForwardPAI|P-Asserted-Identity (PAI) ヘッダーを通話とともに転送するかどうかを示します。 PAI ヘッダーがあれば、発信者 ID を確認できます。 有効になっている場合、プライバシー: ID ヘッダーも送信されます。 既定値は**False** ($False) です。|False|True<br/>False|Boolean|
|いいえ|SendSIPOptions |SBC が SIP オプションを送信するかどうかを定義します。 無効にした場合、SBC は、監視および警告システムから除外されます。 SIP オプションを有効にすることを強くお勧めします。 既定値は**True**です。 |True|True<br/>False|Boolean|
|いいえ|MaxConcurrentSessions |アラートシステムで使用されます。 いずれかの値が設定されると、同時セッション数が90% 以上である場合、またはこの値よりも高い場合に、通知システムによってテナント管理者に通知が生成されます。 このパラメーターが設定されていない場合、アラートは生成されません。 ただし、監視システムでは、24時間ごとに同時セッション数が報告されます。 |空|空<br/>1 ~ 10万 ||
|いいえ|MediaRelayRoutingLocationOverride |メディアのパスを手動で選ぶことができます。 直接ルーティングでは、SBC のパブリック IP に基づいて、メディアパスのデータセンターが割り当てられます。 常に、SBC データセンターに最も近いものを選択します。 ただし、場合によっては、たとえば、米国の範囲をヨーロッパの SBC に割り当てることができます。 この場合は、最適なメディアパスを使用しないようにします。 このパラメーターを使うと、メディアトラフィックの優先領域を手動で設定できます。 このパラメーターを設定することは、メディアパスのデータセンターの自動割り当てで SBC データセンターに最も近い値が割り当てられていないことを示すために、このパラメーターを設定することをお勧めします。 |なし|ISO 形式の国コード||
|いいえ|有効|この SBC を発信通話に対して有効にします。 更新中またはメンテナンス中に、SBC を一時的に削除するために使用できます。 |False|True<br/>False|Boolean|
 
## <a name="verify-the-sbc-connection"></a>SBC 接続を確認する 

接続を確認するには: 
- SBC が、ペアリングされた SBCs のリストにあるかどうかを確認します。 
- SIP オプションを確認します。 
 
### <a name="check-if-the-sbc-is-on-the-list-of-paired-sbcs"></a>SBC が、ペアリングされた SBCs のリストにあるかどうかを確認する 

SBC を接続した後、リモート PowerShell セッションで次のコマンドを実行して、SBC が [ペアリングされた SBCs] のリストに存在することを確認します。 

```PowerShell
Get-CsOnlinePSTNGateway -Identity sbc.contoso.com  
```

次の例に示すように、ペアリングされたゲートウェイがリストに表示され、**有効になっている**パラメーターに**True**の値が表示されます。 


戻り値:
<pre>
Identity              : sbc.contoso.com  
Fqdn                  : sbc.contoso.com 
SipSignalingPort     : 5067 
CodecPriority         : SILKWB,SILKNB,PCMU,PCMA 
ExcludedCodecs        :  
FailoverTimeSeconds   : 10 
ForwardCallHistory    : False 
ForwardPai            : False 
SendSipOptions        : True 
MaxConcurrentSessions : 100 
Enabled               : True 
</pre>

### <a name="validate-sip-options-flow"></a>SIP オプションのフローを検証する 

発信 SIP オプションを使用してペアリングを検証するには、SBC 管理インターフェイスを使用して、SBC が送信オプションメッセージに対する 200 OK 応答を受信することを確認します。

ダイレクトルーティングでは、着信オプションが表示され、着信のオプションメッセージの [連絡先ヘッダー] フィールドに設定された SBC FQDN への送信 SIP オプションメッセージの送信が開始されます。 

着信 SIP オプションを使用してペアリングを検証するには、SBC 管理インターフェイスを使用します。また、SBC は直接ルーティングからのオプションメッセージに返信を送信し、送信する応答コードは 200 OK であることを確認します。


## <a name="see-also"></a>関連項目

[ダイレクト ルーティングを計画する](direct-routing-plan.md)

[ダイレクト ルーティングを構成する](direct-routing-configure.md)
