---
title: セッション ボーダー コントローラー (SBC) を直接ルーティングに接続する
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
description: SBC を構成して電話システム ダイレクト ルーティングに接続する方法について説明します。
ms.openlocfilehash: 4240eb4000e813df51b2678ad2e9c37f6bc0c2ac
ms.sourcegitcommit: 414d077b16a0ae4ea6a49e3b3d0082858174cacb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/17/2021
ms.locfileid: "50278707"
---
# <a name="connect-your-session-border-controller-sbc-to-direct-routing"></a>セッション ボーダー コントローラー (SBC) を直接ルーティングに接続する

この記事では、セッション ボーダー コントローラー (SBC) を構成し、電話システム ダイレクト ルーティングに接続する方法について説明します。  これは、直接ルーティングを構成するための次の手順の手順 1 です。

- **手順 1.SBC と電話システムを接続し、接続を検証する** (この記事)
- 手順 2. [ユーザーに直接ルーティングを有効にする](direct-routing-enable-users.md)
- 手順 3. [通話ルーティングを構成する](direct-routing-voice-routing.md)
- 手順 4. [数値を別の形式に翻訳する](direct-routing-translate-numbers.md)

ダイレクト ルーティングを設定するために必要なすべての手順については、「ダイレクト ルーティングを構成する」を [参照してください](direct-routing-configure.md)。

[Microsoft Teams](#using-the-microsoft-teams-admin-center)管理センターまたは[PowerShell](#using-powershell)を使用して、SBC を構成して直接ルーティングに接続できます。

## <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターの使用

1. 左側のナビゲーションで、[**音声ダイレクト** ルーティング]  >  **に移動** し **、[SPC] タブをクリック** します。
2. **[追加]** をクリックします。
3. SBC の FQDN を入力します。 <br><br>FQDN のドメイン名の部分がテナントに登録されているドメインと一致し、ドメイン名が SBC FQDN ドメイン名でサポートされていないことに注意してください。 `*.onmicrosoft.com` たとえば、2 つのドメイン名がある場合 `contoso.com` は `contoso.onmicrosoft.com` `sbc.contoso.com` 、SBC 名として使用します。 サブドメインを使用している場合は、このサブドメインもテナントに登録されている必要があります。 たとえば、使用する場合は `sbc.service.contoso.com` 、 `service.contoso.com` 登録する必要があります。
4. 組織のニーズに基づいて、SBC の次の設定を構成します。 これらの各設定の詳細については [、SBC の設定を参照してください](#sbc-settings)。

    ![Microsoft Teams 管理センターの [SBC の追加] ページのスクリーンショット](media/direct-routing-add-sbc.png)

5. 作業を終えたら、**[保存]** をクリックします。

## <a name="using-powershell"></a>PowerShell の使用

SBC をダイレクト ルーティングに接続するには、次の手順を実行する必要があります。

1. [PowerShell を使用して Skype for Business Online に接続します](#connect-to-skype-for-business-online-by-using-powershell)。
2. [SBC をテナントに接続します](#connect-the-sbc-to-the-tenant)。
3. [SBC 接続を確認します](#verify-the-sbc-connection)。

### <a name="connect-to-skype-for-business-online-by-using-powershell"></a>PowerShell を使用して Skype for Business Online に接続する

テナントに接続されている PowerShell セッションを使用して、SBC をダイレクト ルーティング インターフェイスにペアリングできます。 PowerShell セッションを開く場合は、「PowerShell セッション用にコンピューターをセットアップする」で説明されている手順[にWindows PowerShell。](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
 
リモート PowerShell セッションを確立した後、SBC を管理するためのコマンドが表示されるのを確認します。 コマンドを確認するには、PowerShell セッションで次のコマンドを入力するか、コピーして貼り付け、Enter キーを押します。 

```PowerShell
Get-Command *onlinePSTNGateway*
```

このコマンドは、SBC を管理できる 4 つの関数を返します。

<pre>
CommandType    Name                       Version    Source 
-----------    ----                       -------    ------ 
Function       Get-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt 
Function       New-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt 
Function       Remove-CsOnlinePSTNGateway 1.0        tmp_v5fiu1no.wxt 
Function       Set-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt
</pre>

### <a name="connect-the-sbc-to-the-tenant"></a>SBC をテナントに接続する

[New-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway)コマンドレットを使用して、SBC をテナントに接続します。 PowerShell セッションで、次を入力し、Enter キーを押します。

```PowerShell
New-CsOnlinePSTNGateway -Fqdn <SBC FQDN> -SipSignalingPort <SBC SIP Port> -MaxConcurrentSessions <Max Concurrent Sessions the SBC can handle> -Enabled $true
```

  > [!NOTE]
  > 1. SBC のドキュメントにある情報を使用して、SBC で最大通話制限を設定することをお勧めします。 SBC が容量レベルにある場合、この制限によって通知がトリガーされます。
  > 2. SBC を接続できるのは、FQDN のドメイン部分がテナントに登録されているドメインの 1 つ (.onmicrosoft.com を除く) と一致する場合のみです \* 。 \*.onmicrosoft.comドメイン名の使用は、SBC FQDN 名ではサポートされていません。 たとえば **、contoso**.com と **contoso**.onmicrosoft.com という 2 つのドメイン名がある場合は、SBC 名に sbc.contoso.com を使用できます。 SBC を sbc.contoso.abc などの名前で接続しようとしても、ドメインはテナントによって所有されていないので、システムは許可されません。<br/>
  > テナントに登録されているドメインに加えて、そのドメインを持つユーザーと、E3 または E5 のライセンスが割り当てられている必要があります。 表示されない場合は、次のエラーが表示されます。<br/>
  `Can not use the "sbc.contoso.com" domain as it was not configured for this tenant`.

以下は、実行例です。

```PowerShell
New-CsOnlinePSTNGateway -Identity sbc.contoso.com -Enabled $true -SipSignalingPort 5067 -MaxConcurrentSessions 100 
```

次の値が返されます。

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
> この例では、必要最小限のパラメーターのみを示します。 接続プロセス中に [New-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway) コマンドレットで設定できる追加のパラメーターがあります。 詳細については [、SBC の設定を参照してください](#sbc-settings)。
 
### <a name="verify-the-sbc-connection"></a>SBC 接続を確認する

接続を確認するには、次の手順を実行します。

- [SBC がペアリングされた SBC のリストにあるかどうかを確認します](#check-whether-the-sbc-is-on-the-list-of-paired-sbcs)。
- [SIP オプションを検証します](#validate-sip-options)。
 
#### <a name="check-whether-the-sbc-is-on-the-list-of-paired-sbcs"></a>SBC がペアリングされた SBC のリストにあるかどうかを確認する

SBC を接続した後 [、Get-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/get-csonlinepstngateway) コマンドレットを使用して、SBC がペアリングされた SBC のリストに存在しているか確認します。 リモート PowerShell セッションで次を入力し、Enter キーを押します。

```PowerShell
Get-CsOnlinePSTNGateway -Identity sbc.contoso.com  
```

次の例に示すように、ペアリングされたゲートウェイが一覧に表示され **、Enabled** パラメーターには True の値が表示 **されます**。

次の値が返されます。

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

#### <a name="validate-sip-options"></a>SIP オプションを検証する

送信 SIP オプションを使用してペアリングを検証するには、SBC 管理インターフェイスを使用して、SBC が送信オプション メッセージに対して 200 OK 応答を受信します。

直接ルーティングで受信オプションが表示された場合、着信オプション メッセージの [連絡先] ヘッダー フィールドで構成された SBC FQDN に送信 SIP オプション メッセージの送信が開始されます。 

着信 SIP オプションを使用してペアリングを検証するには、SBC 管理インターフェイスを使用して、SBC が直接ルーティングから受信する OPTIONS メッセージに返信を送信し、送信する応答コードが 200 OK であるのを確認します。

## <a name="sbc-settings"></a>SBC の設定

次の表は、Microsoft Teams 管理センターと [New-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway) コマンドレットを使用して SBC に設定できるオプションの一覧です。

|必須。|Microsoft Teams 管理センターの設定|PowerShell パラメーター|説明|既定値|可能な値|種類と制限|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|はい|**SBC の FQDN を追加する**|FQDN |なし|FQDN 名、63 文字まで|String、コンピューター、ドメイン、サイト、[および OUs](https://support.microsoft.com/help/909264)の Active Directory の名前付け規則で許可および禁止されている文字の一覧を参照してください。|
|いいえ|**有効**|有効|発信通話の SBC を有効にする場合に使用します。 この機能を使用すると、SBC を更新中またはメンテナンス中にサービスから一時的に削除できます。 |False|True<br/>False|Boolean|
|はい|**SIP シグナリング ポート**|SipSignalingPort |これは、トランスポート層 (TLS) プロトコルを使用してダイレクト ルーティングと通信するために使用されるリッスン ポートです。|なし|任意のポート|0 から 65535 |
|いいえ|**SIP の送信オプション**|SendSIPOptions |SBC が SIP オプション メッセージを送信するかどうかを定義します。 この設定を有効にすることを強くお勧めします。 この設定をオフにすると、SBC は監視および通知システムから除外されます。|True|True<br/>False|Boolean|
|いいえ|**通話履歴を転送する**|ForwardCallHistory |通話履歴情報がトランク経由で転送されるかどうかを示します。 これを有効にした場合、Microsoft 365 または Office 365 プロキシは履歴情報と参照者ヘッダーを送信します。 |False|True<br/>False|Boolean|
|いいえ|**FORWARD P アサート ID (HEADER) ヘッダー**|ForwardPAI|呼び出しと共に、この HEADER ヘッダーを転送するかどうかを示します。 PAI ヘッダーがあれば、発信者 ID を確認できます。 この設定がオンの場合は、Privacy:ID ヘッダーも送信されます。|False|True<br/>False|Boolean|
|いいえ|**同時通話容量**|MaxConcurrentSessions |値を設定すると、同時セッションの数がこの値より 90% 以上多い場合、通知システムによって通知されます。 値を設定しない場合、通知は生成されません。 ただし、監視システムは 24 時間ごとに同時セッションの数を報告します。 |Null|Null<br/>1 ~ 100,000 ||
|いいえ|**フェールオーバー応答コード**|FailoverResponseCodes<br>|ダイレクト ルーティングが送信の招待に応答して 4xx または 6xx SIP エラー コードを受け取った場合、通話は既定で完了したと見なされます。 送信とは、トラフィック フローを含む Teams クライアントから PSTN への通話を意味します。Teams クライアント -> ダイレクト ルーティング -> SBC -> テレフォニー ネットワーク)。 フェールオーバー応答コードを指定すると、ネットワークまたは他の問題のために SBC が呼び出しを実行できない場合、指定されたコードを受け取った場合、ダイレクト ルーティングは別の SBC を強制的に試用します (ユーザーの音声ルーティング ポリシーに別の SBC が存在する場合)。 詳細については、セッション ボーダー コントローラー (SBC) から受信した特定の SIP コードの [フェールオーバーを参照してください](direct-routing-trunk-failover-on-outbound-call.md)。|408, 503, 504||Int|
|いいえ|**フェールオーバー時間 (秒)**|FailoverTimeSeconds |値を設定すると、設定した時間内にゲートウェイによって応答されない発信通話は、次に使用可能なトランクにルーティングされます。 追加のトランクがない場合、通話は自動的にドロップされます。 既定値は 10 秒です。 ネットワークとゲートウェイの応答が遅い組織では、これにより、通話が不必要にドロップされる可能性があります。|10|数値|Int|
|いいえ|**メディア トラフィックに推奨される国または地域**|MediaRelayRoutingLocationOverride |メディア トラフィックに優先する国または地域を手動で設定するために使用します。 これは、通話ログがメディア パスに対するデータセンターの既定の割り当てが SBC データセンターに最も近いパスを使用しない場合にのみ設定することをお勧めします。 既定では、ダイレクト ルーティングは SBC のパブリック IP アドレスに基づいてデータセンターを割り当て、常に SBC データセンターに最も近いパスを選択します。 ただし、場合によっては、既定のパスが最適なパスではない可能性があります。 このパラメーターを使用すると、メディア トラフィックの優先領域を手動で設定できます。 |なし|ISO 形式の国コード||
|いいえ|**SBC は緊急通話に PIDF/LO をサポートします**|PidfloSupported|SBC で緊急通話のプレゼンス情報データ形式の場所オブジェクト (PIDF/LO) をサポートするかどうかを指定します。||||
|いいえ|**ユーザーの検索中に電話を鳴らします**|GenerateRingingWhileLocatingUser|音声信号を呼び出し元に再生するかどうかを設定して、Teams が通話の確立中を示します。 この設定は、メディア 以外のバイパス モードのダイレクト ルーティングにのみ適用されます。 PSTN から Teams クライアントへの着信通話は、確立が予想よりも長くなる場合があります。 この場合、発信者は何も聞こえない、Teams クライアントが呼び出されない、通話が一部の通信プロバイダーによって取り消される可能性があります。 この設定は、これらのシナリオで発生する可能性がある予期しない無音を回避するのに役立ちます。|True|True<br/>False|Boolean|
|いいえ| - |MediaBypass|この設定は、SBC がメディア バイパスをサポートするかどうか、およびこの SBC に使用するかどうかを示します。 |なし|True<br/>False|Boolean|

## <a name="see-also"></a>関連項目

[ダイレクト ルーティングを計画する](direct-routing-plan.md)

[ダイレクト ルーティングを構成する](direct-routing-configure.md)

[Teams での PowerShell の概要](teams-powershell-overview.md)
