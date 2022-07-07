---
title: セッション ボーダー コントローラー (SBC) をダイレクト ルーティングに接続する
ms.reviewer: fillipse
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
description: SBC を構成して Teams Phone システム ダイレクト ルーティングに接続する方法について説明します。
ms.openlocfilehash: 0423c374e903aab2e283ee45bcabf9ceb31ef869
ms.sourcegitcommit: d87991ed2d3e4d70edb048378763a17ff689b710
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2022
ms.locfileid: "66682666"
---
# <a name="connect-your-session-border-controller-sbc-to-direct-routing"></a>セッション ボーダー コントローラー (SBC) をダイレクト ルーティングに接続する

この記事では、セッション ボーダー コントローラー (SBC) を構成し、ダイレクト ルーティングに接続する方法について説明します。  これは、ダイレクト ルーティングを構成するための次の手順の手順 1 です。

- **手順 1.SBC を電話システムに接続し、接続を検証する** (この記事)
- 手順 2. [ダイレクト ルーティングのユーザーを有効にする](direct-routing-enable-users.md)
- 手順 3. [通話ルーティングを構成する](direct-routing-voice-routing.md)
- 手順 4. [数値を別の形式に変換する](direct-routing-translate-numbers.md)

ダイレクト ルーティングを設定するために必要なすべての手順については、「ダイレクト ルーティングの [構成」を](direct-routing-configure.md)参照してください。

[Microsoft Teams 管理センター](#using-the-microsoft-teams-admin-center)または [PowerShell](#using-powershell) を使用して、SBC を構成してダイレクト ルーティングに接続できます。

## <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターの使用

1. 左側のナビゲーションで、[ **音声** > **ダイレクト ルーティング**] に移動し、[ **SBC** ] タブをクリックします。

2. **[追加]** をクリックします。

3. SBC の FQDN を入力します。 <br><br>FQDN のドメイン名の部分が、テナントに登録されているドメインと一致していることを確認し、ドメイン名が `*.onmicrosoft.com` SBC FQDN ドメイン名でサポートされていないことを確認してください。 たとえば、2 つのドメイン名があり、 `contoso.com` `contoso.onmicrosoft.com`SBC 名として使用 `sbc.contoso.com` します。 サブドメインを使用している場合は、このサブドメインもテナントに登録されていることを確認します。 たとえば、使用 `sbc.service.contoso.com`する場合は、 `service.contoso.com` 登録する必要があります。

4. 組織のニーズに基づいて、SBC の次の設定を構成します。 これらの各設定の詳細については、「 [SBC](#sbc-settings) 設定」を参照してください。

    ![Microsoft Teams 管理センターの [SBC の追加] ページのスクリーンショット。](media/direct-routing-add-sbc.png)

5. 作業を終えたら、**[保存]** をクリックします。

## <a name="using-powershell"></a>PowerShell の使用

SBC をダイレクト ルーティングに接続するには、次のことを行う必要があります。

1. [PowerShell を使用してSkype for Business Online に接続](#connect-to-skype-for-business-online-by-using-powershell)します。

2. [SBC をテナントに接続します](#connect-the-sbc-to-the-tenant)。

3. [SBC 接続を確認します](#verify-the-sbc-connection)。

### <a name="connect-to-skype-for-business-online-by-using-powershell"></a>PowerShell を使用してオンラインSkype for Businessに接続する

SBC をダイレクト ルーティング インターフェイスにペアリングするには、テナントに接続されている PowerShell セッションを使用します。 PowerShell セッションを開くには、「[Windows PowerShell用にコンピューターをセットアップ](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)する」で説明されている手順に従います。
 
リモート PowerShell セッションを確立したら、SBC を管理するコマンドが表示されることを確認します。 コマンドを確認するには、PowerShell セッションで次のコマンドを入力またはコピーして貼り付け、Enter キーを押します。 

```PowerShell
Get-Command *onlinePSTNGateway*
```

このコマンドは、SBC を管理できる次の 4 つの関数を返します。

<pre>
CommandType    Name                       Version    Source 
-----------    ----                       -------    ------ 
Function       Get-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt 
Function       New-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt 
Function       Remove-CsOnlinePSTNGateway 1.0        tmp_v5fiu1no.wxt 
Function       Set-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt
</pre>

### <a name="connect-the-sbc-to-the-tenant"></a>SBC をテナントに接続する

SBC をテナントに接続するには、 [New-CsOnlinePSTNGateway](/powershell/module/skype/new-csonlinepstngateway) コマンドレットを使用します。 PowerShell セッションで、次のように入力し、Enter キーを押します。

```PowerShell
New-CsOnlinePSTNGateway -Fqdn <SBC FQDN> -SipSignalingPort <SBC SIP Port> -MaxConcurrentSessions <Max Concurrent Sessions the SBC can handle> -Enabled $true
```

  > [!NOTE]
  > 1. SBC のドキュメントに記載されている情報を使用して、SBC で最大呼び出し制限を設定することをお勧めします。 SBC が容量レベルにある場合、この制限によって通知がトリガーされます。
  > 2. SBC は、FQDN のドメイン部分がテナントに登録されているドメインのいずれかと一致する場合にのみ接続できます (.onmicrosoft.com を除く \*)。 .onmicrosoft.com ドメイン名の使用 \*は、SBC FQDN 名ではサポートされていません。 たとえば、 **contoso.com** と **contoso.onmicrosoft.com** の 2 つのドメイン名がある場合は、SBC 名に sbc.contoso.com を使用できます。 sbc.contoso.abc などの名前で SBC を接続しようとすると、ドメインがこのテナントによって所有されていないため、システムでは許可されません。<br/>
  > テナントに登録されているドメインに加えて、そのドメインを持つユーザーと E3 または E5 ライセンスが割り当てられていることが重要です。 そうでない場合は、次のエラーが表示されます。<br/>
  `Can not use the "sbc.contoso.com" domain as it was not configured for this tenant`.
  > 3. SBC 側で同じ FQDN でマップされた複数の IP はサポートされていません。
  > 4. お客様にクラス最高の暗号化を提供するために、Microsoft はダイレクト ルーティング SIP インターフェイスに TLS1.2 の使用を強制します。
  > サービスへの影響を回避するには、TLS1.2 をサポートするように SBC が構成されており、次のいずれかの暗号スイートを使用して接続できることを確認します。TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA384つまり。 ECDHE-RSA-AES256-GCM-SHA384 TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA256つまり ECDHE-RSA-AES128-GCM-SHA256 TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA384すなわち ECDHE-RSA-AES256-SHA384 TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA256 i.e. ECDHE-RSA-AES128-SHA2564

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
> この例では、必要な最小パラメーターのみを示します。 接続プロセス中に [New-CsOnlinePSTNGateway](/powershell/module/skype/new-csonlinepstngateway) コマンドレットで設定できる追加のパラメーターがあります。 詳細については、「 [SBC 設定](#sbc-settings)」を参照してください。
 
### <a name="verify-the-sbc-connection"></a>SBC 接続を確認する

接続を確認するには:

- [SBC がペアになっている SBC の一覧に含まれているかどうかを確認します](#check-whether-the-sbc-is-on-the-list-of-paired-sbcs)。
- [SIP オプションを検証します](#validate-sip-options)。
 
#### <a name="check-whether-the-sbc-is-on-the-list-of-paired-sbcs"></a>SBC がペアになっている SBC の一覧に含まれているかどうかを確認する

SBC を接続した後、 [Get-CsOnlinePSTNGateway](/powershell/module/skype/get-csonlinepstngateway) コマンドレットを使用して、SBC がペアになっている SBC の一覧に存在することを確認します。 リモート PowerShell セッションで次のように入力し、Enter キーを押します。

```PowerShell
Get-CsOnlinePSTNGateway -Identity sbc.contoso.com  
```

次の例に示すように、ペアになっているゲートウェイが一覧に表示され、 **Enabled** パラメーターに **True の値** が表示されます。

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

発信 SIP オプションを使用してペアリングを検証するには、SBC 管理インターフェイスを使用し、SBC が送信 OPTIONS メッセージに対して 200 件の OK 応答を受信することを確認します。

ダイレクト ルーティングに受信オプションが表示されると、受信オプション メッセージの [連絡先] ヘッダー フィールドで構成された SBC FQDN に送信 SIP オプション メッセージの送信が開始されます。 

着信 SIP オプションを使用してペアリングを検証するには、SBC 管理インターフェイスを使用して、SBC がダイレクト ルーティングから受信する OPTIONS メッセージに応答を送信し、送信する応答コードが 200 OK であることを確認します。

## <a name="sbc-settings"></a>SBC 設定

次の表に、Microsoft Teams 管理センターの SBC と [New-CsOnlinePSTNGateway](/powershell/module/skype/new-csonlinepstngateway) コマンドレットを使用して設定できるオプションの一覧を示します。

|必須。|Teams 管理センターの設定|PowerShell パラメーター|説明|既定値|可能な値|型と制限|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|はい|**SBC の FQDN を追加する**|FQDN |なし|FQDN 名、制限 63 文字|文字列。[コンピューター、ドメイン、サイト、OU の Active Directory の名前付け規則に関する](https://support.microsoft.com/help/909264)許可文字と禁止文字の一覧を参照してください。|
|いいえ|**有効**|有効|送信呼び出しに対して SBC を有効にするために使用します。 これを使用すると、更新中またはメンテナンス中に SBC をサービスから一時的に削除できます。 |False|True<br/>False|Boolean|
|はい|**SIP シグナリング ポート**|SipSignalingPort |これは、トランスポート層 (TLS) プロトコルを使用してダイレクト ルーティングと通信するために使用されるリッスン ポートです。|なし|任意のポート|0 ~ 65535 |
|いいえ|**SIP オプションを送信する**|SendSIPOptions |SBC が SIP オプション メッセージを送信するかどうかを定義します。 この設定を有効にすることを非常に推奨します。 この設定がオフの場合、SBC は監視およびアラート システムから除外されます。|True|True<br/>False|Boolean|
|いいえ|**転送通話履歴**|ForwardCallHistory |通話履歴情報がトランク経由で転送されるかどうかを示します。 これを有効にすると、Microsoft 365 プロキシによって履歴情報と参照元ヘッダーが送信されます。 |False|True<br/>False|Boolean|
|いいえ|**前方 P アサート ID (PAI) ヘッダー**|ForwardPAI|呼び出しと共に PAI ヘッダーが転送されるかどうかを示します。 PAI ヘッダーがあれば、発信者 ID を確認できます。 この設定がオンの場合は、Privacy:ID ヘッダーも送信されます。|False|True<br/>False|Boolean|
|いいえ|**同時呼び出し容量**|MaxConcurrentSessions |値を設定すると、同時セッションの数がこの値より 90% 以上になると、アラート システムから通知されます。 値を設定しないと、アラートは生成されません。 ただし、監視システムは 24 時間ごとに同時セッション数を報告します。 |Null|Null<br/>1 ~ 100,000 ||
|いいえ|**フェールオーバー応答コード**|FailoverResponseCodes<br>|ダイレクト ルーティングが送信招待に応答して 4xx または 6xx SIP エラー コードを受信した場合、呼び出しは既定で完了したものと見なされます。 発信とは、Teams クライアントから PSTN へのトラフィック フローの呼び出しを意味します。Teams クライアント -> ダイレクト ルーティング -> SBC -> テレフォニー ネットワーク)。 フェールオーバー応答コードを指定すると、ネットワークやその他の問題が原因で SBC が呼び出しを行えない場合、指定したコードを受信したときに、ダイレクト ルーティングで別の SBC (ユーザーの音声ルーティング ポリシーに別の SBC が存在する場合) を試す必要があります。 詳細については、「 [セッション ボーダー コントローラー (SBC)から受信した特定の SIP コードのフェールオーバー](direct-routing-trunk-failover-on-outbound-call.md)」を参照してください。|408, 503, 504||Int|
|いいえ|**フェールオーバー時間 (秒)**|FailoverTimeSeconds |値を設定すると、設定した時間内にゲートウェイから応答されない送信呼び出しは、次に使用可能なトランクにルーティングされます。 追加のトランクがない場合、呼び出しは自動的に削除されます。 既定値は 10 秒です。 ネットワークとゲートウェイ応答が遅い組織では、これにより、通話が不必要に削除される可能性があります。|10|数値|Int|
|いいえ|**メディア トラフィックの優先する国または地域**|MediaRelayRoutingLocationOverride | ダイレクト ルーティングには適用されません。 このパラメーターは、通話プランのマネージドキャリアで使用するために予約されています |なし|||
|いいえ|**SBC では、緊急通報に対して PIDF/LO がサポートされます**|PidfloSupported|緊急通報に対して SBC がプレゼンス情報データ形式の場所オブジェクト (PIDF/LO) をサポートするかどうかを指定します。||||
|いいえ| - |MediaBypass|この設定は、SBC がメディア バイパスをサポートしているかどうか、およびこの SBC に使用するかどうかを示します。 |なし|True<br/>False|Boolean|

## <a name="see-also"></a>関連項目

[ダイレクト ルーティングを計画する](direct-routing-plan.md)

[ダイレクト ルーティングを構成する](direct-routing-configure.md)

[Teams での PowerShell の概要](teams-powershell-overview.md)
