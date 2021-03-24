---
title: Microsoft 365 または 365 組織とのクラウド コネクタOffice構成する
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
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 0e2f2395-b890-4d16-aa2d-99d52438b89c
description: Microsoft 365 組織または Microsoft 365 組織とのクラウド コネクタOffice説明します。
ms.openlocfilehash: 74696023dcffbc91641bb4e9950f2988a89abbdd
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095091"
---
# <a name="configure-cloud-connector-integration-with-your-microsoft-365-or-office-365-organization"></a>Microsoft 365 または 365 組織とのクラウド コネクタOffice構成する

> [!Important] 
> Cloud Connector Edition は、Skype for Business Online と共に 2021 年 7 月 31 日に廃止されます。 組織が Teams にアップグレードしたら、直接ルーティングを使用してオンプレミスのテレフォニー ネットワークを Teams に接続する方法 [について説明します](/MicrosoftTeams/direct-routing-landing-page)。

Microsoft 365 組織または Microsoft 365 組織とのクラウド コネクタOffice説明します。
  
Skype for Business Cloud Connector Edition のインストールが完了したら、このセクションの手順を実行して展開を構成し、Microsoft 365 または Office 365 組織に接続します。
  
## <a name="configure-firewall-settings"></a>ファイアウォール設定の構成

「Plan [for Skype for Business Cloud Connector Edition」](plan-skype-for-business-cloud-connector-edition.md)の「ポートとプロトコル」[](plan-skype-for-business-cloud-connector-edition.md#BKMB_Ports)の説明に従って、境界ネットワークの内部および外部ファイアウォール設定のファイアウォール設定を構成して、必要なポートを開きます。
  
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

Microsoft 365 または Office 365 でドメインを更新する手順が完了し、DNS レコードを追加する機能を持っている必要があります。 Microsoft 365 または Office 365 でドメインをセットアップする方法の詳細については [、「Add a domain to Microsoft 365 or Office 365」を参照](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611)してください。
  
## <a name="add-dns-records-for-your-edge"></a>エッジの DNS レコードを追加する

Microsoft 365 または 365 組織に次Office追加します。 DNS レコードを追加する方法の詳細については [、「Microsoft 365](https://support.office.com/article/Add-or-edit-custom-DNS-records-in-Office-365-AF00A516-DD39-4EDA-AF3E-1EAF686C8DC9?ui=en-US&amp;rs=en-US&amp;ad=US&amp;fromAR=1)または microsoft 365 または Office 365 のカスタム DNS レコードを追加または編集する」を参照してください。
  
1. アクセス エッジの DNS A レコードを追加します。
    
2. SRV レコードは、Microsoft 365 または 365 Office展開スクリプトによって自動的に作成されます。 エッジで次の 2 つの SIP サービス (sip と \_ \_ sipfederationtls) を参照できる点を確認します。
    
     ![SRV レコードの確認](../../media/3c353a29-6dcc-4ed3-98db-3a6bed3e929e.png)
  
## <a name="set-up-hybrid-connectivity-between-cloud-connector-edition-and-microsoft-365-or-office-365"></a>クラウド コネクタエディションと Microsoft 365 または Microsoft 365 または microsoft 365 Officeセットアップ

Skype for Business Cloud Connector Edition 展開と Microsoft 365 または Office 365 組織とのハイブリッド接続を構成するには、リモート PowerShell セッションで次のコマンドレットを実行します。 リモート PowerShell セッションを確立する方法については、「コンピューターのセットアップ」を参照[Windows PowerShell。](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
  
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

Microsoft 365 管理センターにログインし、オンライン 音声サービスを有効にするユーザーを追加し、E5 ライセンスまたは電話システム アドオンをこれらのユーザーに E3 ライセンスに割り当てる。 ユーザーの追加の詳細については、「 [ビジネス向け Microsoft 365 にユーザーを追加する」を参照してください](https://support.office.com/article/Add-users-to-Office-365-for-business-435ccec3-09dd-4587-9ebd-2f3cad6bc2bc)。
  
## <a name="enable-users-for-phone-system-voice-and-voicemail-services"></a>電話システムの音声およびボイスメール サービスのユーザーを有効にする
 
Microsoft 365 または Office 365 にユーザーを追加した後、ボイスメールを含む電話システム音声サービスのアカウントを有効にしてください。 これらの機能を有効にするには、グローバル管理者の役割であるアカウントを使用して Microsoft 365 または Office 365 組織にログインし、リモート PowerShell を実行できる必要があります。 リモート PowerShell セッションを確立する方法については、「デバイス用にコンピューターをセットアップする」 [を参照Windows PowerShell](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
  
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

ユーザーが国際通話を行えるかどうかを決定する必要があります。 既定では、国際通話は有効になっています。 オンラインの Skype for Business 管理センターを使用して、ユーザーが国際ダイヤルを無効または有効にできます。
  
ユーザー単位で国際通話を無効にするには、Skype for Business Online PowerShell で次のコマンドレットを実行します。
  
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
> PSTN サイトがユーザーに割り当てられていない場合、Skype for Business Cloud Connector Edition 展開と Microsoft 365 または Office 365 組織間のハイブリッド接続は、テナント レベルの既定の 1 (ピア宛先) を使用して通話を完了できます。 
  
## <a name="configure-online-hybrid-mediation-server-settings"></a>オンライン ハイブリッド 仲介サーバーの設定を構成する
<a name="BKMK_ConfigureMediationServer"> </a>

P2P 通話が PSTN 会議にエスカレートすると、Skype for Business Online 会議サーバーはクラウド コネクタ仲介サーバーに招待を送信します。 Microsoft 365 または Office 365 でこの招待を正常にルーティングするには、次のように、クラウド コネクタ 仲介サーバーごとにオンライン テナントの設定を構成する必要があります。 
  
1. Microsoft 365 管理センターでユーザーを作成します。 "MediationServer1" など、必要なユーザー名を使用します。
    
    クラウド コネクタの既定の SIP ドメイン (.ini ファイルの最初の SIP ドメイン) をユーザー ドメインとして使用します。
    
    ライセンスの割り当ては、Skype for Business オンライン ディレクトリへのユーザー伝達にのみ必要です。 作成したアカウントに Microsoft 365 または Office 365 ライセンス (E5 など) を割り当て、変更が反映されるように最大 1 時間を許可し、次のコマンドレットを実行して、Skype for Business オンライン ディレクトリにユーザー アカウントが正しくプロビジョニングされていることを確認し、このアカウントからライセンスを削除します。
    ```powershell
   Get-CsOnlineUser -Identity <UserPrincipalName>
   ```
    
2. グローバルまたはユーザー管理者の資格情報を使用してテナント Azure AD リモート PowerShell セッションを開始し、次のコマンドレットを実行して、手順 1 で構成された Azure AD ユーザー アカウントの部門を "HybridMediationServer" に設定します。

   ```powershell
   Set-MsolUser -UserPrincipalName <UserPrincipalName> -Department "HybridMediationServer"
   ```

3. Skype for Business テナント管理者資格情報を使用してテナント Skype for Business リモート PowerShell セッションを開始し、次のコマンドレットを実行して仲介サーバーとエッジ サーバーの FQDN をそのユーザー アカウントに設定し、手順 1 で作成したアカウントのユーザーの表示名に置き換えてください。 \<DisplayName\>
    
   ```powershell
   Set-CsHybridMediationServer -Identity <DisplayName> -Fqdn <MediationServerFQDN> -AccessProxyExternalFqdn <EdgeServerExternalFQDN>
   ```

    Identity の場合は、この仲介サーバー用に作成したユーザー アカウントの表示名を使用します。
    
    *MediationServerFQDN の* 場合は、仲介サーバーに定義されている内部 FQDN を使用します。
    
    *EdgeServerExternalFQDN の* 場合は、エッジ サーバー アクセス プロキシ用に定義されている外部 FQDN を使用します。 複数のクラウド コネクタ PSTN サイトがある場合は、仲介サーバーがあるサイトに割り当てられているエッジ サーバー アクセス プロキシ FQDN を選択します。
    
4. 複数のクラウド コネクタ 仲介サーバー (複数サイト、HA) がある場合は、それぞれの手順を繰り返してください。
