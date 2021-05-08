---
title: Connect ボーダー コントローラー (SBC) を直接ルーティングに接続する
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
description: SBC を構成し、直接ルーティングに接続電話システム説明します。
ms.openlocfilehash: 697f426b9c9dc3215d653520658282fab1787001
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51122251"
---
# <a name="connect-your-session-border-controller-sbc-to-direct-routing"></a>Connect ボーダー コントローラー (SBC) を直接ルーティングに接続する

この記事では、セッション ボーダー コントローラー (SBC) を構成し、直接ルーティングに接続電話システム説明します。  これは、ダイレクト ルーティングを構成する次の手順の手順 1 です。

- **手順 1.Connectを使用して SBC を電話システムし、接続を検証します**(この記事)
- 手順 2. [ユーザーに直接ルーティングを有効にする](direct-routing-enable-users.md)
- 手順 3. [通話ルーティングを構成する](direct-routing-voice-routing.md)
- 手順 4. [数値を別の形式に変換する](direct-routing-translate-numbers.md)

ダイレクト ルーティングを設定するために必要なすべての手順については、「ダイレクト ルーティングの構成 [」を参照してください](direct-routing-configure.md)。

管理センターまたは[PowerShell Microsoft Teamsを](#using-the-microsoft-teams-admin-center)使用して[](#using-powershell)、SBC を構成し、直接ルーティングに接続できます。

## <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターの使用

1. 左側のナビゲーションで、[**音声ダイレクト** ルーティング]  >  **に移動し****、[SBC] タブをクリック** します。
2. **[追加]** をクリックします。
3. SBC の FQDN を入力します。 <br><br>FQDN のドメイン名の部分がテナントに登録されているドメインと一致し、ドメイン名が SBC FQDN ドメイン名でサポートされていないことに注意してください `*.onmicrosoft.com` 。 たとえば、 と の 2 つのドメイン名 `contoso.com` がある場合は `contoso.onmicrosoft.com` 、 を `sbc.contoso.com` SBC 名として使用します。 サブドメインを使用する場合は、このサブドメインもテナントに登録されている必要があります。 たとえば、 を使用する場合は `sbc.service.contoso.com` 、 `service.contoso.com` 登録する必要があります。
4. 組織のニーズに基づいて、SBC の次の設定を構成します。 これらの各設定の詳細については [、「SBC の設定」を参照してください](#sbc-settings)。

    ![管理センターの [SBC の追加] ページMicrosoft Teamsスクリーンショット](media/direct-routing-add-sbc.png)

5. 作業を終えたら、**[保存]** をクリックします。

## <a name="using-powershell"></a>PowerShell の使用

SBC をダイレクト ルーティングに接続するには、次の手順を実行する必要があります。

1. [Connect PowerShell Skype for Businessを使用して Online を使用する方法について説明します](#connect-to-skype-for-business-online-by-using-powershell)。
2. [Connect に SBC を追加します](#connect-the-sbc-to-the-tenant)。
3. [SBC 接続を確認します](#verify-the-sbc-connection)。

### <a name="connect-to-skype-for-business-online-by-using-powershell"></a>Connect PowerShell をSkype for Businessして Online を使用する

テナントに接続されている PowerShell セッションを使用して、SBC をダイレクト ルーティング インターフェイスとペアリングできます。 PowerShell セッションを開く場合は、「コンピューターをセットアップする」で説明されている手順[に](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)従Windows PowerShell。
 
リモート PowerShell セッションを確立した後、SBC を管理するコマンドが表示されるのを確認します。 コマンドを確認するには、PowerShell セッションで次のコマンドを入力するか、コピーして貼り付け、Enter キーを押します。 

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

### <a name="connect-the-sbc-to-the-tenant"></a>Connectに SBC を追加する

[New-CsOnlinePSTNGateway](/powershell/module/skype/new-csonlinepstngateway)コマンドレットを使用して、SBC をテナントに接続します。 PowerShell セッションで、次を入力し、Enter キーを押します。

```PowerShell
New-CsOnlinePSTNGateway -Fqdn <SBC FQDN> -SipSignalingPort <SBC SIP Port> -MaxConcurrentSessions <Max Concurrent Sessions the SBC can handle> -Enabled $true
```

  > [!NOTE]
  > 1. SBC のドキュメントに掲載されている情報を使用して、SBC で最大呼び出し制限を設定することをお勧めします。 SBC が容量レベルにある場合、制限によって通知がトリガーされます。
  > 2. SBC を接続できるのは、その FQDN のドメイン部分がテナントに登録されているドメインの 1 つ (.onmicrosoft.com を除く) と一 \* 致する場合のみです。 \*.onmicrosoft.com ドメイン名の使用は、SBC FQDN 名ではサポートされていません。 たとえば **、contoso**.com と **contoso**.onmicrosoft.com という 2 つのドメイン名がある場合は、SBC 名に sbc.contoso.com を使用できます。 sbc.contoso.abc などの名前で SBC を接続しようとしても、ドメインはこのテナントによって所有されていないので、システムによって許可されません。<br/>
  > テナントに登録されているドメインに加えて、そのドメインを持つユーザーと、割り当てられた E3 または E5 ライセンスが必要です。 表示されない場合は、次のエラーが表示されます。<br/>
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
> この例では、最低限必要なパラメーターのみを示します。 接続プロセス中に [New-CsOnlinePSTNGateway](/powershell/module/skype/new-csonlinepstngateway) コマンドレットで設定できる追加のパラメーターがあります。 詳細については [、「SBC の設定」を参照してください](#sbc-settings)。
 
### <a name="verify-the-sbc-connection"></a>SBC 接続を確認する

接続を確認するには:

- [SBC がペアの SBC の一覧にあるかどうかを確認します](#check-whether-the-sbc-is-on-the-list-of-paired-sbcs)。
- [SIP オプションを検証します](#validate-sip-options)。
 
#### <a name="check-whether-the-sbc-is-on-the-list-of-paired-sbcs"></a>SBC がペアの SBC の一覧にあるかどうかを確認する

SBC を接続した後 [、Get-CsOnlinePSTNGateway](/powershell/module/skype/get-csonlinepstngateway) コマンドレットを使用して、SBC がペアの SBC の一覧に存在する必要があります。 リモート PowerShell セッションで次を入力し、Enter キーを押します。

```PowerShell
Get-CsOnlinePSTNGateway -Identity sbc.contoso.com  
```

次の例に示すように、ペアになっているゲートウェイが一覧に表示され **、Enabled** パラメーターに True の値が表示 **されます**。

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

送信 SIP オプションを使用してペアリングを検証するには、SBC 管理インターフェイスを使用し、SBC が送信 OPTIONS メッセージに対して 200 OK 応答を受信します。

ダイレクト ルーティングで受信オプションが表示された場合、着信オプション メッセージの [連絡先ヘッダー] フィールドに構成されている SBC FQDN に送信 SIP オプション メッセージの送信が開始されます。 

着信 SIP オプションを使用してペアリングを検証するには、SBC 管理インターフェイスを使用して、SBC がダイレクト ルーティングから受信した OPTIONS メッセージに応答を送信し、送信する応答コードが 200 OK である必要があります。

## <a name="sbc-settings"></a>SBC の設定

次の表は、Microsoft Teams 管理センターと[New-CsOnlinePSTNGateway](/powershell/module/skype/new-csonlinepstngateway)コマンドレットを使用して SBC に設定できるオプションを示しています。

|必須。|Microsoft Teams管理センターの設定|PowerShell パラメーター|説明|既定値|可能な値|型と制限|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|はい|**SBC の FQDN を追加する**|FQDN |なし|FQDN 名、63 文字以内|文字列。コンピューター、ドメイン、サイト、および OUs の Active Directory での名前付け規則に関するページで、許可および禁止されている文字の一覧[を参照してください](https://support.microsoft.com/help/909264)。|
|いいえ|**有効**|有効|を使用して、発信呼び出しの SBC を有効にします。 これを使用して、更新中またはメンテナンス中に SBC をサービスから一時的に削除できます。 |False|True<br/>False|Boolean|
|はい|**SIP シグナル ポート**|SipSignalingPort |これは、トランスポート層 (TLS) プロトコルを使用して直接ルーティングと通信するために使用されるリッスン ポートです。|なし|任意のポート|0 ~ 65535 |
|いいえ|**SIP オプションを送信する**|SendSIPOptions |SBC が SIP オプション メッセージを送信するかどうかを定義します。 この設定を有効にすることを強くお勧めします。 この設定がオフの場合、SBC は監視およびアラート システムから除外されます。|True|True<br/>False|Boolean|
|いいえ|**通話履歴を転送する**|ForwardCallHistory |通話履歴情報がトランク経由で転送されるかどうかを示します。 これを有効にした場合、Microsoft 365またはOffice 365は履歴情報と参照者ヘッダーを送信します。 |False|True<br/>False|Boolean|
|いいえ|**FORWARD P-Asserted-identity (ASSERTed-identity)ヘッダー**|ForwardPAI|呼び出しと共に、このオブジェクトが転送されるかどうかを示します。 PAI ヘッダーがあれば、発信者 ID を確認できます。 この設定がオンの場合、Privacy:ID ヘッダーも送信されます。|False|True<br/>False|Boolean|
|いいえ|**同時呼び出しの容量**|MaxConcurrentSessions |値を設定すると、同時セッションの数が 90% 以上の場合にアラート システムから通知されます。 値を設定しない場合、アラートは生成されません。 ただし、監視システムは 24 時間ごとに同時セッションの数を報告します。 |Null|Null<br/>1 ~ 100,000 ||
|いいえ|**フェールオーバー応答コード**|FailoverResponseCodes<br>|ダイレクト ルーティングが送信招待に応答して 4xx または 6xx SIP エラー コードを受け取った場合、呼び出しは既定で完了したと見なされます。 送信とは、Teams クライアント -Teams > ダイレクト ルーティング -> SBC -> テレフォニー ネットワーク) を使用して、Teams クライアントから PSTN への通話を意味します。 フェールオーバー応答コードを指定すると、ネットワークなどの問題のために SBC が呼び出しを実行できない場合、指定されたコードを受信するときに、ダイレクト ルーティングは別の SBC を強制的に試します (ユーザーの音声ルーティング ポリシーに別の SBC が存在する場合)。 詳細については、「セッション ボーダー コントローラー (SBC) から受信した特定の SIP コードのフェールオーバー [」を参照してください](direct-routing-trunk-failover-on-outbound-call.md)。|408, 503, 504||Int|
|いいえ|**フェールオーバー時間 (秒)**|FailoverTimeSeconds |値を設定すると、設定した時間内にゲートウェイによって応答されない発信呼び出しは、次に使用可能なトランクにルーティングされます。 追加のトランクがない場合、呼び出しは自動的に破棄されます。 既定値は 10 秒です。 ネットワークとゲートウェイの応答が遅い組織では、これにより、呼び出しが不必要に破棄される可能性があります。|10|数値|Int|
|いいえ|**メディア トラフィックに推奨される国または地域**|MediaRelayRoutingLocationOverride |メディア トラフィックの優先する国または地域を手動で設定する場合に使用します。 これは、通話ログでメディア パスのデータセンターの既定の割り当てが SBC データセンターに最も近いパスを使用しないという明確な場合にのみ設定することをお勧めします。 既定では、ダイレクト ルーティングは SBC のパブリック IP アドレスに基づいてデータセンターを割り当て、常に SBC データセンターに最も近いパスを選択します。 ただし、場合によっては、既定のパスが最適なパスではない可能性があります。 このパラメーターを使用すると、メディア トラフィックの優先リージョンを手動で設定できます。 |なし|ISO 形式の国コード||
|いいえ|**SBC では、緊急通話用の PIDF/LO がサポートされます**|PidfloSupported|SBC が緊急通話に対してプレゼンス情報データ形式の場所オブジェクト (PIDF/LO) をサポートするかどうかを指定します。||||
|いいえ| - |MediaBypass|この設定は、SBC がメディア バイパスをサポートするかどうかと、この SBC に使用するかどうかを示します。 |なし|True<br/>False|Boolean|

## <a name="see-also"></a>関連項目

[ダイレクト ルーティングを計画する](direct-routing-plan.md)

[ダイレクト ルーティングを構成する](direct-routing-configure.md)

[Teams での PowerShell の概要](teams-powershell-overview.md)