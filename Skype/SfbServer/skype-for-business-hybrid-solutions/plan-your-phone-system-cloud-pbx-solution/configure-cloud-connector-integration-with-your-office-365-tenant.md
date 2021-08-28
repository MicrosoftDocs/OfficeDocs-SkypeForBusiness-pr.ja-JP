---
title: クラウド コネクタの統合を組織または組織Microsoft 365構成Office 365する
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 0e2f2395-b890-4d16-aa2d-99d52438b89c
description: クラウド コネクタの統合を組織または組織Microsoft 365構成Office 365します。
ms.openlocfilehash: 5e6cf8033a4207b79ff2f7d0915849b19eec2b65
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58628529"
---
# <a name="configure-cloud-connector-integration-with-your-microsoft-365-or-office-365-organization"></a>クラウド コネクタの統合を組織または組織Microsoft 365構成Office 365する

> [!Important] 
> Cloud Connector Edition は、2021 年 7 月 31 日にオンライン版と共Skype for Business廃止されます。 組織がネットワーク にアップグレードしたらTeamsルーティングを使用してオンプレミスのテレフォニー ネットワークをネットワークに接続するTeams[説明します](/MicrosoftTeams/direct-routing-landing-page)。

クラウド コネクタの統合を組織または組織Microsoft 365構成Office 365します。
  
インストールがSkype for Business クラウド コネクタ エディションしたら、このセクションの手順を実行して展開を構成し、組織の Microsoft 365またはOffice 365します。
  
## <a name="configure-firewall-settings"></a>ファイアウォール設定の構成

「Plan for Skype for Business クラウド コネクタ エディション」の「ポートとプロトコル」の説明に従って、境界ネットワークの内部[](plan-skype-for-business-cloud-connector-edition.md#BKMB_Ports)および外部ファイアウォール設定のファイアウォール設定を構成して、必要なポート[を開きます](plan-skype-for-business-cloud-connector-edition.md)。
  
## <a name="set-up-public-switched-telephone-network-pstn-gateways"></a>公衆交換電話網 (PSTN) ゲートウェイのセットアップ

すべてのアプライアンスの仲介サーバーを指し示すトランクを各 PSTN ゲートウェイに設定します。 プールの FQDN はプール内のすべてのサーバーで同じなので、各トランクは仲介サーバー プールの FQDN ではなく 1 つの仲介サーバー FQDN または IP アドレスを指す必要があります。 トランクは同じ優先度で設定する必要があります。
  
仲介サーバーとゲートウェイの間で TLS を使用している場合は、MTLS をサポートするためにゲートウェイと仲介サーバーを次のように構成する必要があります。
  
1. クラウド コネクタ Active Directory コンピューターからルート CA をエクスポートします。
    
2. ルート CA のインポートについては、PSTN ゲートウェイ ベンダーの指示に従います。
    
3. 仲介サーバー上のゲートウェイに発行された証明書のルート CA 証明書をインポートします。 ゲートウェイの SSL 証明書を取得する必要がある場合は、次のようにクラウド コネクタ Active Directory コンピューターで実行されている証明機関サービスを使用してこれを行うことができます。
    
   - 既存の Web Server テンプレートを変更して、認証済みユーザーが登録を有効にするか、新しい Web Server テンプレートを作成して他のプロパティを構成し、認証済みユーザーが登録を有効にします。 詳細な手順については、「証明書テンプレート [」を参照してください](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc730705(v=ws.11))。
    
   - 有効にした Web サーバー テンプレートを選択する証明書スナップインを使用して証明書を要求します。 ゲートウェイの FQDN を持つ代替名のサブジェクトと DNS 名に共通名を必ず追加し、キー オプションの下で [プライベート キーをエクスポート可能にする] が選択されている [プライベート キー] で確認します。 
    
4. プライベート キーを使用して SSL 証明書をエクスポートし、PSTN ゲートウェイ ベンダーの指示に従って証明書をインポートします。
    
## <a name="update-the-domain-for-your-tenant"></a>テナントのドメインを更新する

ドメインを更新する手順が完了した後で、Microsoft 365またはOffice 365 DNS レコードを追加する機能を持っている必要があります。 ドメインを Microsoft 365 または Office 365 で設定する方法の詳細については、「add a domain to Microsoft 365 または Office 365」 を[参照してください](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611)。
  
## <a name="add-dns-records-for-your-edge"></a>エッジの DNS レコードを追加する

次の DNS レコードを組織または組織Microsoft 365追加Office 365します。 DNS レコードを追加する方法の詳細については、「カスタム DNS レコードを追加または編集する」を参照Microsoft 365[またはOffice 365。](https://support.office.com/article/Add-or-edit-custom-DNS-records-in-Office-365-AF00A516-DD39-4EDA-AF3E-1EAF686C8DC9?ui=en-US&amp;rs=en-US&amp;ad=US&amp;fromAR=1)
  
1. アクセス エッジの DNS A レコードを追加します。
    
2. SRV レコードは、ユーザーまたはユーザーのMicrosoft 365展開Office 365によって自動的に作成されます。 エッジで次の 2 つの SIP サービス (sip と \_ \_ sipfederationtls) を参照できる点を確認します。
    
     ![SRV レコードの確認](../../media/3c353a29-6dcc-4ed3-98db-3a6bed3e929e.png)
  
## <a name="set-up-hybrid-connectivity-between-cloud-connector-edition-and-microsoft-365-or-office-365"></a>クラウド コネクタエディションとクラウド コネクタエディション間のハイブリッド接続をMicrosoft 365またはOffice 365

Skype for Business クラウド コネクタ エディション展開と Microsoft 365 または Office 365組織とのハイブリッド接続を構成するには、リモート PowerShell セッションで次のコマンドレットを実行します。 リモート PowerShell セッションを確立する方法については、「コンピューターのセットアップ」を参照[Windows PowerShell。](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
  
コマンドレットは、Access Edge 外部 FQDN を設定します。 最初のコマンドでは \<External Access Edge FQDN\> 、SIP アクセス エッジの役割の 1 つが必要です。 既定では、これは ap である必要があります \<Domain Name\> 。
  
```powershell
Set-CsTenantHybridConfiguration -PeerDestination <External Access Edge FQDN> -UseOnPremDialPlan $false
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $True
```

> [!NOTE]
> ピア宛先に使用される外部アクセス エッジ FQDN は、ユーザーが PSTN サイトに割り当てられていない場合にのみフォールバックとして使用される PSTN サイトに設定する必要があります。 詳細については、「単一サイト [をクラウド コネクタに展開](deploy-a-single-site-in-cloud-connector.md) する」および「Cloud Connector で複数のサイトを展開する」 [を参照してください](deploy-multiple-sites-in-cloud-connector.md)。 
  
## <a name="set-up-pstn-gateways"></a>PSTN ゲートウェイのセットアップ

すべてのアプライアンスの仲介サーバーを指し示すトランクを各 PSTN ゲートウェイに設定します。 プール FQDN はプール内のすべてのサーバーで同じなので、各トランクは仲介サーバー プールの FQDN ではなく 1 つの仲介サーバー FQDN または IP アドレスを指す必要があります。 トランクは同じ優先度で設定する必要があります。
  
仲介サーバーとゲートウェイの間で TLS を使用している場合は、MTLS をサポートするためにゲートウェイと仲介サーバーを次のように構成する必要があります。
  
1. クラウド コネクタ Active Directory コンピューターからルート CA をエクスポートします。
    
2. ルート CA のインポートについては、PSTN ゲートウェイ ベンダーの指示に従います。
    
3. 仲介サーバー上のゲートウェイに発行された証明書のルート CA 証明書をインポートします。 ゲートウェイの SSL 証明書を取得する必要がある場合は、次のようにクラウド コネクタ Active Directory コンピューターで実行されている証明機関サービスを使用してこれを行うことができます。
    
   - 既存の Web Server テンプレートを変更して、認証済みユーザーが登録を有効にするか、新しい Web サーバー テンプレートを作成して他のプロパティを構成し、認証済みユーザーが登録できます。 詳細な手順については、「証明書テンプレート [」を参照してください](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc730705(v=ws.11))。
    
   - 有効にした Web サーバー テンプレートを選択する証明書スナップインを使用して証明書を要求します。 ゲートウェイの FQDN を持つ代替名のサブジェクトと DNS 名に共通名を必ず追加し、キー オプションの下で [プライベート キーをエクスポート可能にする] が選択されている [プライベート キー] で確認します。 
    
4. プライベート キーを使用して SSL 証明書をエクスポートし、PSTN ゲートウェイ ベンダーの指示に従って証明書をインポートします。
    
5. 1 つの PSTN サイトの PSTN ゲートウェイは、同じサイト内の仲介サーバーにのみ接続する必要があります。
    
## <a name="set-up-your-users"></a>ユーザーを設定する

Microsoft 365 管理センター にログインし、オンライン 音声サービスを有効にするユーザーを追加し、E5 ライセンスまたは 電話システム アドオンをこれらのユーザーに E3 ライセンスに割り当てる。 ユーザーの追加の詳細については、「ビジネス向けユーザー[にユーザーをMicrosoft 365する」を参照してください](https://support.office.com/article/Add-users-to-Office-365-for-business-435ccec3-09dd-4587-9ebd-2f3cad6bc2bc)。
  
## <a name="enable-users-for-phone-system-voice-and-voicemail-services"></a>音声サービスとボイスメール 電話システムユーザーを有効にする
 
ユーザーをボイス メールまたはMicrosoft 365にOffice 365、ボイスメールを含む音声サービス電話システムアカウントを有効にしてください。 これらの機能を有効にするには、グローバル管理者の役割であるアカウントを使用して Microsoft 365 または Office 365 組織にログインし、リモート PowerShell を実行できる必要があります。 リモート PowerShell セッションを確立する方法については、「デバイス用にコンピューターをセットアップする」[を参照Windows PowerShell](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
  
- ポリシーをユーザーに割り当て、Identity パラメーターの値で指定するユーザーのビジネス音声電話番号を **構成** します。
    
  ```powershell
  Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI <tel:+phonenumber>
  ```

    > [!NOTE]
    > ユーザー ID は、ユーザーの SIP アドレス、ユーザー プリンシパル名 (UPN)、またはユーザーの Active Directory 表示名 ("Bob Kelly" など) を使用して指定できます。 アスタリスク ( \* ) 文字は、ユーザー ID として表示名と一緒に使用できます。 たとえば、Identity " Smith" は、文字列値 "Smith" で終わる表示名を持つすべてのユーザー \* を返します。
  
次のスクリプトを使用して、ユーザーが追加され、有効にされたと確認できます。
  
```powershell
# Input the user name you want to verify
$user = Get-CsOnlineUser <User name>

# For a hybrid user, the value of $user.EnterpriseVoiceEnabled should be True
$user.EnterpriseVoiceEnabled

# For a hybrid user, the value of $user.HostedVoiceMail should be True
$user.HostedVoiceMail

# For a hybrid user, the value of $user.VoicePolicy should be "HybridVoice"
$user.VoicePolicy
```

ユーザーが国際通話を行えるかどうかを決定する必要があります。 既定では、国際通話は有効になっています。 オンライン 管理センターを使用して、ユーザーが国際ダイヤルを無効またはSkype for Businessできます。
  
ユーザー単位で国際通話を無効にするには、オンライン PowerShell で次Skype for Business実行します。
  
```powershell
Grant-CsVoiceRoutingPolicy -PolicyName InternationalCallsDisallowed -Identity $user
```

無効にした後にユーザーごとに国際通話を再び有効にするには、同じコマンドレットを実行しますが **、PolicyName** の値を *InternationalCallsAllowed に変更します*  。
  
## <a name="assign-users-to-pstn-sites"></a>PSTN サイトへのユーザーの割り当て

1 つのサイトのみを展開した場合でも、テナントリモート PowerShell を使用してサイトをユーザーに割り当てる。 リモート PowerShell セッションを確立する方法については、「コンピューターのセットアップ」を参照[Windows PowerShell。](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
  
```powershell
# Set the site to users
Set-CsUserPstnSettings -Identity <User Name> -HybridPstnSite <PSTN Site Name>

# Review the site setting for a user
Get-CsUserPstnSettings -Identity <User Name> 

# See all the user settings in one tenant
Get-CsOnlineUser | Get-CsUserPstnSettings
```

> [!NOTE]
> PSTN サイトがユーザーに割り当てられていない場合、Skype for Business クラウド コネクタ エディション 展開と Microsoft 365 または Office 365 組織間のハイブリッド接続は、テナント レベルの既定の 1 (ピア宛先) を使用して呼び出しを完了するために戻ります。 
  
## <a name="configure-online-hybrid-mediation-server-settings"></a>オンライン ハイブリッド仲介サーバー の構成設定
<a name="BKMK_ConfigureMediationServer"> </a>

P2P 呼び出しが PSTN 会議にエスカレートすると、Skype for Business オンライン会議サーバーはクラウド コネクタ仲介サーバーに招待を送信します。 この招待をMicrosoft 365またはOffice 365するには、次のように、クラウド コネクタ 仲介サーバーごとにオンライン テナントの設定を構成する必要があります。 
  
1. ユーザーを作成するには、Microsoft 365 管理センター。 "MediationServer1" など、必要なユーザー名を使用します。
    
    ユーザー ドメインとして、クラウド コネクタの既定の SIP ドメイン (.ini ファイルの最初の SIP ドメイン) を使用します。
    
    ライセンスの割り当ては、ユーザーがオンライン ディレクトリにSkype for Business注意してください。 作成したアカウントに Microsoft 365 ライセンスまたは Office 365 ライセンス (E5 など) を割り当て、変更を反映するために最大 1 時間を許可し、次のコマンドレットを実行してユーザー アカウントが Skype for Business オンライン ディレクトリに正しくプロビジョニングされていることを確認してから、このアカウントからライセンスを削除します。
    ```powershell
   Get-CsOnlineUser -Identity <UserPrincipalName>
   ```
    
2. グローバルまたはユーザー管理者の資格情報を使用してテナント Azure AD リモート PowerShell セッションを開始し、次のコマンドレットを実行して、手順 1 で構成された Azure AD ユーザー アカウントの部門を "HybridMediationServer" に設定します。

   ```powershell
   Set-MsolUser -UserPrincipalName <UserPrincipalName> -Department "HybridMediationServer"
   ```

3. Skype for Business テナント管理者資格情報を使用してテナント Skype for Business リモート PowerShell セッションを開始し、次のコマンドレットを実行して仲介サーバーとエッジ サーバーの FQDN をそのユーザー アカウントに設定し、手順 1 で作成したアカウントのユーザーの表示名に置き換える。 \<DisplayName\>
    
   ```powershell
   Set-CsHybridMediationServer -Identity <DisplayName> -Fqdn <MediationServerFQDN> -AccessProxyExternalFqdn <EdgeServerExternalFQDN>
   ```

    Identity の場合は、この仲介サーバー用に作成したユーザー アカウントの表示名を使用します。
    
    *MediationServerFQDN の* 場合は、仲介サーバーに定義されている内部 FQDN を使用します。
    
    *EdgeServerExternalFQDN の* 場合は、エッジ サーバー アクセス プロキシ用に定義されている外部 FQDN を使用します。 複数のクラウド コネクタ PSTN サイトがある場合は、仲介サーバーがあるサイトに割り当てられているエッジ サーバー アクセス プロキシ FQDN を選択します。
    
4. 複数のクラウド コネクタ 仲介サーバー (複数サイト、HA) がある場合は、それぞれの手順を繰り返してください。
