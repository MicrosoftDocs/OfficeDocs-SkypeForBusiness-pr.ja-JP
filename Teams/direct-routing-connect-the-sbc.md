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
description: SBC to Phone システムのダイレクトルーティングを構成して接続する方法について説明します。
ms.openlocfilehash: 900c8c50f60842465ae6a636d5953be81c83af84
ms.sourcegitcommit: c8b5d4dd70d183f7ca480fb735a19290a3457b30
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/08/2020
ms.locfileid: "45077622"
---
# <a name="connect-your-session-border-controller-sbc-to-direct-routing"></a>セッション境界のコントローラー (SBC) を直接ルーティングに接続する

この記事では、セッション境界コントローラー (SBC) を構成し、電話システムのダイレクトルーティングに接続する方法について説明します。  これは、次の手順の手順1で、ダイレクトルーティングを構成します。

- **手順1お使いの SBC を電話システムに接続して接続を検証する**(この記事)
- 手順2 [ユーザーが直接ルーティングできるようにする](direct-routing-enable-users.md)
- 手順3 [通話ルーティングの構成](direct-routing-voice-routing.md)
- 手順4。 [数値を別の形式に変換する](direct-routing-translate-numbers.md) 

直接ルーティングを設定するために必要なすべての手順については、「[直接ルーティングを構成](direct-routing-configure.md)する」を参照してください。

[Microsoft Teams 管理センター](#using-the-microsoft-teams-admin-center)または[PowerShell](#using-powershell)を使用して、SBC を直接ルーティングするように構成し、接続することができます。

## <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターの使用

1. 左側のナビゲーションで、[**音声**の直接ルーティング] に移動し、[  >  **Direct Routing** **SBCs** ] タブをクリックします。
2. **[追加]** をクリックします。
3. SBC の FQDN を入力します。 <br><br>FQDN のドメイン名の部分がテナントに登録されているドメインと一致していることを確認し、その `*.onmicrosoft.com` ドメイン名が SBC FQDN ドメイン名でサポートされていないことに注意してください。 たとえば、2つのドメイン名がある場合は、 `contoso.com` `contoso.onmicrosoft.com` `sbc.contoso.com` SBC 名として使用します。
4. 組織のニーズに基づいて、SBC の次の設定を構成します。 各設定の詳細については、「 [SBC 設定](#sbc-settings)」を参照してください。

    ![Microsoft Teams 管理センターの [SBC の追加] ページのスクリーンショット](media/direct-routing-add-sbc.png)

5. 作業を終えたら、**[保存]** をクリックします。

## <a name="using-powershell"></a>PowerShell を使用する場合

SBC をダイレクトルーティングに接続するには、次の操作を行う必要があります。

1. [PowerShell を使用して、Skype For Business Online に接続し](#connect-to-skype-for-business-online-by-using-powershell)ます。
2. [SBC をテナントに接続](#connect-the-sbc-to-the-tenant)します。
3. [SBC 接続を確認](#verify-the-sbc-connection)します。

### <a name="connect-to-skype-for-business-online-by-using-powershell"></a>PowerShell を使用して Skype for Business Online に接続する

テナントに接続された PowerShell セッションを使って、SBC とダイレクトルーティングインターフェイスをペアリングすることができます。 PowerShell セッションを開くには、「 [Windows powershell 用にコンピューターを](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)セットアップする」の手順に従ってください。
 
リモート PowerShell セッションを確立したら、SBC を管理するためのコマンドが表示されることを確認します。 コマンドを確認するには、PowerShell セッションで次のコマンドを入力するか、コピーして貼り付け、enter キーを押します。 

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

### <a name="connect-the-sbc-to-the-tenant"></a>SBC をテナントに接続する

[CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway)コマンドレットを使用して、SBC をテナントに接続します。 PowerShell セッションで、次のように入力し、enter キーを押します。

```PowerShell
New-CsOnlinePSTNGateway -Fqdn <SBC FQDN> -SipSignalingPort <SBC SIP Port> -MaxConcurrentSessions <Max Concurrent Sessions the SBC can handle> -Enabled $true
```

  > [!NOTE]
  > 1. Sbc では、SBC ドキュメントに記載されている情報を使用して、最大限の通話制限を設定することをお勧めします。 SBC がキャパシティレベルにある場合、制限によって通知がトリガーされます。
  > 2. SBC のドメイン部分がテナントに登録されているドメインのいずれかと一致している場合にのみ、SBC を接続できます (onmicrosoft.com を除く) \* 。 \*Onmicrosoft.com ドメイン名は、SBC FQDN 名ではサポートされていません。 たとえば **、2**つのドメイン名が onmicrosoft.com である場合は、sbc**名とし**て sbc を使うことができます。 Sbc を sbc などの名前で接続しようとしても、ドメインはこのテナントが所有していないため、システムによってこのようなことは許可されません。<br/>
  > テナントに登録されているドメインに加えて、そのドメインと E3 または E5 ライセンスが割り当てられているユーザーもいる必要があります。 存在しない場合、次のエラーが表示されます。<br/>
  `Can not use the "sbc.contoso.com" domain as it was not configured for this tenant`.

以下は、実行例です。

```PowerShell
New-CsOnlinePSTNGateway -Identity sbc.contoso.com -Enabled $true -SipSignalingPort 5067 -MaxConcurrentSessions 100 
```

戻り値:

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

> [!NOTE]
> 次の例は、最低限必要なパラメーターのみを示しています。 接続プロセス中に[CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway)コマンドレットを使用して設定できる追加のパラメーターがあります。 詳細については、「 [SBC 設定](#sbc-settings)」を参照してください。
 
### <a name="verify-the-sbc-connection"></a>SBC 接続を確認する

接続を確認するには:

- [SBC が、ペアリングされた SBCs のリストにあるかどうかを確認](#check-whether-the-sbc-is-on-the-list-of-paired-sbcs)します。
- [SIP オプションを確認](#validate-sip-options)します。
 
#### <a name="check-whether-the-sbc-is-on-the-list-of-paired-sbcs"></a>この SBC が、ペアリングされた SBCs のリストにあるかどうかを確認します。

SBC を接続したら、 [CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/get-csonlinepstngateway)コマンドレットを使用して、ペアリングされている SBCs の一覧に sbc が存在することを確認します。 リモート PowerShell セッションで次のように入力し、enter キーを押します。

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

#### <a name="validate-sip-options"></a>SIP オプションの検証

発信 SIP オプションを使用してペアリングを検証するには、SBC 管理インターフェイスを使用して、SBC が送信オプションメッセージに対する 200 OK 応答を受信することを確認します。

ダイレクトルーティングでは、着信オプションが表示され、着信のオプションメッセージの [連絡先ヘッダー] フィールドに設定された SBC FQDN への送信 SIP オプションメッセージの送信が開始されます。 

着信 SIP オプションを使用してペアリングを検証するには、SBC 管理インターフェイスを使用します。また、SBC は直接ルーティングからのオプションメッセージに返信を送信し、送信する応答コードは 200 OK であることを確認します。

## <a name="sbc-settings"></a>SBC の設定

次の表は、Microsoft Teams 管理センターで SBC 用に設定できるオプションと、 [CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway)コマンドレットを使用する方法を示しています。

|必須。|Microsoft Teams 管理センターの設定|PowerShell パラメーター|説明|既定|可能な値|種類と制限|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|はい|**SBC の FQDN を追加する**|FQDN |なし|FQDN 名、63文字を制限する|文字列。[コンピューター、ドメイン、サイト、および ou の Active Directory の名前付け規則](https://support.microsoft.com/help/909264)で許可されている文字と許可されていない文字の一覧を参照してください。|
|X|**有効**|有効|送信通話の SBC をオンにします。 これを使用して、更新中またはメンテナンス中に、SBC をサービスから一時的に削除することができます。 |False|True<br/>False|Boolean|
|はい|**SIP シグナリングポート**|SipSignalingPort |これは、トランスポート層 (TLS) プロトコルを使用した直接ルーティングと通信するために使用されるリッスンポートです。|なし|任意のポート|0 ~ 65535 |
|X|**SIP オプションの送信**|SendSIPOptions |SBC が SIP オプションメッセージを送信するかどうかを定義します。 この設定を有効にすることを強くお勧めします。 この設定をオフにすると、SBC は監視およびアラートシステムから除外されます。|True|True<br/>False|Boolean|
|X|**通話履歴の転送**|ForwardCallHistory |通話履歴情報がトランクを通じて転送されるかどうかを示します。 この機能を有効にすると、Microsoft 365 または Office 365 プロキシによって履歴情報と参照ヘッダーが送信されます。 |False|True<br/>False|Boolean|
|X|**Forward P-identity (PAI) ヘッダー**|ForwardPAI|PAI ヘッダーが通話と共に転送されるかどうかを示します。 PAI ヘッダーがあれば、発信者 ID を確認できます。 この設定をオンにすると、プライバシー: ID ヘッダーも送信されます。|False|True<br/>False|Boolean|
|X|**同時通話の容量**|MaxConcurrentSessions |値を設定すると、同時セッション数が90% 以上であるか、またはこの値よりも大きい場合に、警告システムによって通知されます。 値を設定しないと、アラートは生成されません。 ただし、監視システムでは、24時間ごとに同時セッション数が報告されます。 |空|空<br/>1 ~ 10万 ||
|X|**フェールオーバー応答コード**|FailoverResponseCodes<br>|直接ルーティングで、発信した招待に応答して4xx または 6xx SIP のエラーコードが送信された場合、通話は既定で完了したと見なされます。 [発信] は、トラフィックフローを使用してチームクライアントから PSTN への通話を指します。 Teams クライアント-> ダイレクトルーティング-> SBC-> テレフォニーネットワーク)。 フェールオーバー応答コードを指定すると、ネットワークまたはその他の問題により、SBC が電話をかけることができない場合に、指定されたコードを受信したときに、別の sbc (ユーザーの音声ルーティングポリシーに別の SBC が存在する場合) に対して直接ルーティングが行われます。 詳細については、「[セッションボーダーコントローラー (SBC) で受信した特定の SIP コードのフェイルオーバー](direct-routing-trunk-failover-on-outbound-call.md)」を参照してください。|408、503、504||Int|
|X|**フェールオーバー時間 (秒)**|FailoverTimeSeconds |値を設定すると、設定した時間内にゲートウェイによって応答されない送信通話は、次に利用可能なトランクにルーティングされます。 追加の trunks がない場合、通話は自動的に切断されます。 既定値は10秒です。 低速のネットワークとゲートウェイ応答がある組織では、これにより、不必要な通話が削除される可能性があります。|常用|数値|Int|
|X|**メディアトラフィック用の優先国または地域**|MediaRelayRoutingLocationOverride |メディアトラフィックに適した国または地域を手動で設定する場合に使用します。 メディアパスのデータセンターの既定の割り当てが、SBC データセンターに最も近いパスを使用しないことを示す場合にのみ、この設定を行うことをお勧めします。 既定では、直接ルーティングでは、SBC のパブリック IP アドレスに基づいてデータセンターが割り当てられ、SBC データセンターに最も近いパスが常に選択されます。 ただし、場合によっては、既定のパスが最適なパスでない可能性があります。 このパラメーターを使うと、メディアトラフィックの優先領域を手動で設定できます。 |なし|ISO 形式の国コード||
|X|**SBC は緊急通話のために PIDF/安値をサポートしています**|PidfloSupported|PIDF のプレゼンス情報のデータ形式の場所 (/LO) で緊急通話をサポートするかどうかを指定します。||||
|X|**ユーザーを検索しているときに電話を鳴らす**|GenerateRingingWhileLocatingUser|発信者に対して音声信号が再生されるかどうかを設定し、チームが通話の確立プロセス中であることを示します。 この設定は、メディア以外のバイパスモードでのダイレクトルーティングにのみ適用されます。 PSTN から Teams への着信通話は、確立に予想以上に時間がかかることがあります。 この問題が発生すると、呼び出し元は何も聞こえないため、Teams クライアントは呼び出しを行わず、通信プロバイダーによって通話がキャンセルされる可能性があります。 この設定は、これらのシナリオで発生する可能性のある予期しない silences を回避するのに役立ちます。|True|True<br/>False|Boolean|
|X| - |MediaBypass|この設定は、SBC でメディアのバイパスがサポートされているかどうか、およびこの SBC で使用するかどうかを示します。 |なし|True<br/>False|Boolean|

## <a name="see-also"></a>関連項目

[ダイレクト ルーティングを計画する](direct-routing-plan.md)

[ダイレクト ルーティングを構成する](direct-routing-configure.md)

[Teams での PowerShell の概要](teams-powershell-overview.md)
