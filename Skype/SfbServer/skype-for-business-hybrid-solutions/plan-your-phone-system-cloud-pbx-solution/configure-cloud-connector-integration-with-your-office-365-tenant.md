---
title: Microsoft 365 または Office 365 組織とのクラウドコネクタ統合を構成する
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
description: Office 365 組織とのクラウドコネクタ統合を構成する方法について説明します。
ms.openlocfilehash: 1fecf017f614fc8bdf0f38b5f51c29e4b2774357
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "43780646"
---
# <a name="configure-cloud-connector-integration-with-your-microsoft-365-or-office-365-organization"></a>Microsoft 365 または Office 365 組織とのクラウドコネクタ統合を構成する
 
Office 365 組織とのクラウドコネクタ統合を構成する方法について説明します。
  
Skype for Business Cloud Connector エディションのインストールが完了したら、このセクションの手順を実行して展開を構成し、Office 365 組織に接続します。
  
## <a name="configure-firewall-settings"></a>ファイアウォール設定を構成する

「 [Plan For Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md)」の「[ポートとプロトコル](plan-skype-for-business-cloud-connector-edition.md#BKMB_Ports)」で説明されているように、境界ネットワークの内部および外部ファイアウォール設定のファイアウォール設定を構成し、必要なポートを開きます。
  
## <a name="set-up-public-switched-telephone-network-pstn-gateways"></a>公衆交換電話網 (PSTN) ゲートウェイをセットアップする

すべてのアプライアンスの仲介サーバーをポイントするように、各 PSTN ゲートウェイのトランクを設定します。 プールの FQDN はプール内のすべてのサーバーで同じであるため、各トランクは仲介サーバープールの FQDN ではなく、1つの仲介サーバーの FQDN または IP アドレスをポイントする必要があります。 トランクは同じ優先度で設定する必要があります。
  
仲介サーバーとゲートウェイ間で TLS を使用している場合は、次のように MTLS をサポートするようにゲートウェイと仲介サーバーを構成する必要があります。
  
1. Cloud Connector Active Directory コンピューターからルート CA をエクスポートします。
    
2. ルート CA のインポートについては、PSTN ゲートウェイのベンダーの指示に従ってください。
    
3. 仲介サーバー上のゲートウェイに発行された証明書のルート CA 証明書をインポートします。 ゲートウェイ用の SSL 証明書を取得する必要がある場合は、次のように Cloud Connector Active Directory コンピューター上で実行されている証明機関サービスを使用して、これを行うことができます。
    
   - 既存の Web サーバーテンプレートを変更して認証済みユーザーを登録できるようにするか、新しい Web サーバーテンプレートを作成して他のプロパティを構成し、認証されたユーザーを登録できるようにします。 詳細な手順については、「[証明書テンプレート](https://technet.microsoft.com/library/cc730705.aspx)」を参照してください。
    
   - 有効にした Web サーバーテンプレートを選択して、証明書スナップインを使用して証明書を要求します。 [キーのオプション] で秘密キーをエクスポートできるようにするには、[サブジェクト] と [DNS 名] に、「別名」と「別名」を使用して、秘密キーを確認してください。 
    
4. 秘密キーを使用して SSL 証明書をエクスポートし、PSTN ゲートウェイベンダーからの指示に従って証明書をインポートします。
    
## <a name="update-the-domain-for-your-tenant"></a>テナントのドメインを更新する

Office 365 でドメインを更新する手順が完了しており、DNS レコードを追加できることを確認してください。 Office 365 でドメインをセットアップする方法の詳細については、「 [office 365 にドメインを追加](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611)する」を参照してください。
  
## <a name="add-dns-records-in-office-365-for-your-edge"></a>Office 365 でエッジ用の DNS レコードを追加する

次の DNS レコードを Office 365 組織に追加します。 Office 365 組織に DNS レコードを追加する方法については、「 [office 365 でカスタムの dns レコードを追加または編集](https://support.office.com/article/Add-or-edit-custom-DNS-records-in-Office-365-AF00A516-DD39-4EDA-AF3E-1EAF686C8DC9?ui=en-US&amp;rs=en-US&amp;ad=US&amp;fromAR=1)する」を参照してください。
  
1. アクセスエッジの DNS A レコードを追加します。
    
2. SRV レコードは、Office 365 と展開スクリプトによって自動的に作成されます。 エッジに対して次の2つの SIP サービスを検索できることを確認します。 _sip と _sipfederationtls。
    
     ![SRV レコードの確認](../../media/3c353a29-6dcc-4ed3-98db-3a6bed3e929e.png)
  
## <a name="set-up-hybrid-connectivity-between-cloud-connector-edition-and-office-365"></a>Cloud Connector エディションと Office 365 の間のハイブリッド接続をセットアップする

Skype for Business Cloud Connector エディションの展開と Office 365 組織との間にハイブリッド接続を構成するには、リモート PowerShell セッションで次のコマンドレットを実行します。 リモート PowerShell セッションを確立する方法については、「 [Windows PowerShell 用にコンピューター](https://technet.microsoft.com/library/dn362831%28v=ocs.15%29.aspx)をセットアップする」を参照してください。
  
コマンドレットは、アクセスエッジの外部 FQDN を設定します。 最初のコマンドの場合、 \<外部アクセスエッジの FQDN\>は、SIP アクセスエッジの役割に対応したものにする必要があります。 既定では、これは ap ドメイン\<名\>にする必要があります。
  
```powershell
Set-CsTenantHybridConfiguration -PeerDestination <External Access Edge FQDN> -UseOnPremDialPlan $false
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $True
```

> [!NOTE]
> ピアの宛先に使用される外部アクセスエッジの FQDN は、ユーザーが PSTN サイトに割り当てられていない場合にのみフォールバックとして使用される PSTN サイトに設定する必要があります。 詳細については、「 [deploy a single site In Cloud connector](deploy-a-single-site-in-cloud-connector.md) 」および「 [deploy Multiple Sites in cloud connector](deploy-multiple-sites-in-cloud-connector.md)」を参照してください。 
  
## <a name="set-up-pstn-gateways"></a>PSTN ゲートウェイのセットアップ

すべてのアプライアンスの仲介サーバーをポイントするように、各 PSTN ゲートウェイのトランクを設定します。 プールの FQDN は、プール内のすべてのサーバーで同じであるため、各トランクは仲介サーバーの fqdn ではなく、1つの仲介サーバーの FQDN または IP アドレスをポイントする必要があります。 トランクは同じ優先度で設定する必要があります。
  
仲介サーバーとゲートウェイ間で TLS を使用している場合は、次のように MTLS をサポートするようにゲートウェイと仲介サーバーを構成する必要があります。
  
1. Cloud Connector Active Directory コンピューターからルート CA をエクスポートします。
    
2. ルート CA のインポートについては、PSTN ゲートウェイのベンダーの指示に従ってください。
    
3. 仲介サーバー上のゲートウェイに発行された証明書のルート CA 証明書をインポートします。 ゲートウェイ用の SSL 証明書を取得する必要がある場合は、次のように Cloud Connector Active Directory コンピューター上で実行されている証明機関サービスを使用して、これを行うことができます。
    
   - 既存の Web サーバーテンプレートを変更して認証済みユーザーを登録できるようにするか、新しい Web サーバーテンプレートを作成して他のプロパティを構成し、認証されたユーザーを登録できるようにします。 詳細な手順については、「[証明書テンプレート](https://technet.microsoft.com/library/cc730705.aspx)」を参照してください。
    
   - 有効にした Web サーバーテンプレートを選択して、証明書スナップインを使用して証明書を要求します。 [キーのオプション] で秘密キーをエクスポートできるようにするには、[サブジェクト] と [DNS 名] に、「別名」と「別名」を使用して、秘密キーを確認してください。 
    
4. 秘密キーを使用して SSL 証明書をエクスポートし、PSTN ゲートウェイベンダーからの指示に従って証明書をインポートします。
    
5. 1つの PSTN サイトの PSTN ゲートウェイは、同じサイトの仲介サーバーにのみ接続する必要があります。
    
## <a name="set-up-your-users-in-office-365"></a>Office 365 でユーザーをセットアップする

Microsoft 365 管理センターにログインし、オンライン音声サービスに対して有効にするユーザーを追加し、Office 365 アドオンの E5 ライセンスまたは電話システムをこれらのユーザーに対して E3 ライセンスに割り当てます。 ユーザーの追加の詳細については、「 [Add users To Office 365 to business](https://support.office.com/article/Add-users-to-Office-365-for-business-435ccec3-09dd-4587-9ebd-2f3cad6bc2bc)」を参照してください。
  
## <a name="enable-users-for-phone-system-in-office-365-voice-and-voicemail-services"></a>Office 365 の電話システムでユーザーを有効にする音声およびボイスメールサービス

Office 365 にユーザーを追加した後、ボイスメールを含む Office 365 音声サービスの電話システムに対してアカウントを有効にします。 これらの機能を有効にするには、グローバル管理者の役割であるアカウントを使用して Office 365 組織にログインし、リモート PowerShell を実行できるようにする必要があります。 リモート PowerShell セッションを確立する方法については、「 [Windows PowerShell 用にコンピューター](https://technet.microsoft.com/library/dn362831%28v=ocs.15%29.aspx)をセットアップする」を参照してください。
  
- ユーザーにポリシーを割り当て、ユーザーのビジネスボイス電話番号を構成します。これは、 **Identity**パラメーターの値を使用して指定します。
    
  ```powershell
  Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI <tel:+phonenumber>
  ```

    > [!NOTE]
    > ユーザーの SIP アドレス、ユーザープリンシパル名 (UPN)、またはユーザーの Active Directory 表示名 (たとえば、「Bob 友野」) を使用して、ユーザー id を指定できます。 アスタリスク (\*) 文字をユーザー id として表示名と共に使用することもできます。 たとえば、"\*smith" という id は、"smith" という文字列値で終わる表示名を持つすべてのユーザーを返します。
  
その後、次のスクリプトを使用して、ユーザーが追加され、有効になっていることを確認できます。
  
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

ユーザーが国際電話をかけることができるようにするかどうかを決定する必要があります。 既定では、国際通話は有効になっています。 オンラインの Skype for Business 管理センターを使用して、ユーザーの国際通話を無効または有効にすることができます。
  
ユーザー単位で国際通話を無効にするには、Skype for Business Online PowerShell で次のコマンドレットを実行します。
  
```powershell
Grant-CsVoiceRoutingPolicy -PolicyName InternationalCallsDisallowed -Identity $user
```

無効にした後、ユーザー単位で国際通話を再び有効にするには、同じコマンドレットを実行しますが、 **PolicyName**の値を*InternationalCallsAllowed*に変更します。
  
## <a name="assign-users-to-pstn-sites"></a>ユーザーを PSTN サイトに割り当てる

テナントのリモート PowerShell を使用して、1つのサイトのみを展開した場合でも、ユーザーにサイトを割り当てます。 リモート PowerShell セッションを確立する方法については、「 [Windows PowerShell 用にコンピューター](https://technet.microsoft.com/library/dn362831%28v=ocs.15%29.aspx)をセットアップする」を参照してください。
  
```powershell
# Set the site to users
Set-CsUserPstnSettings -Identity <User Name> -HybridPstnSite <PSTN Site Name>

# Review the site setting for a user
Get-CsUserPstnSettings -Identity <User Name> 

# See all the user settings in one tenant
Get-CsOnlineUser | Get-CsUserPstnSettings
```

> [!NOTE]
> ユーザーに PSTN サイトが割り当てられていない場合、Skype for Business Cloud Connector エディションの展開と Office 365 組織との間のハイブリッド接続は、テナントレベルの既定値 (ピアの宛先) を使用して通話を完了できるようになります。 
  
## <a name="configure-online-hybrid-mediation-server-settings"></a>オンラインのハイブリッド仲介サーバーの設定を構成する
<a name="BKMK_ConfigureMediationServer"> </a>

P2P 電話が PSTN 会議にエスカレートされると、Skype for Business Online 会議サーバーは Cloud Connector 仲介サーバーに招待を送信します。 Office 365 がこの招待を正常にルーティングできるようにするには、次のように、各 Cloud Connector 仲介サーバーのオンラインテナントで設定を構成する必要があります。 
  
1. Microsoft 365 管理センターでユーザーを作成します。 必要なユーザー名 ("MediationServer1" など) を使用します。
    
    ユーザードメインとして、Cloud Connector の既定の SIP ドメイン (.ini ファイルの最初の SIP ドメイン) を使用します。
    
    ライセンスの割り当ては、ユーザーが Skype for Business online ディレクトリに伝播する場合にのみ必要であることに注意してください。 作成したアカウントに Office 365 ライセンス (E5 など) を割り当て、変更が伝達されるまで最大1時間待ちます。次のコマンドレットを実行して、ユーザーアカウントが Skype for Business online ディレクトリに正しくプロビジョニングされていることを確認し、このアカウントからライセンスを削除します。
    ```powershell
   Get-CsOnlineUser -Identity <UserPrincipalName>
   ```
    
2. グローバルまたはユーザーの管理者の資格情報を使用してテナント Azure AD リモート PowerShell セッションを開始し、次のコマンドレットを実行して、手順1で構成した Azure AD ユーザーアカウントの部署を "HybridMediationServer" に設定します。

   ```powershell
   Set-MsolUser -UserPrincipalName <UserPrincipalName> -Department "HybridMediationServer"
   ```

3. Skype for Business のテナント管理者の資格情報を使用して、テナントの Skype for Business リモート PowerShell セッションを開始し、次のコマンドレットを実行して、仲介サーバーと\<エッジ\>サーバーの FQDN を、そのユーザーアカウントに設定します。 DisplayName は、手順1で作成したアカウントのユーザーの表示名に置き換えます。
    
   ```powershell
   Set-CsHybridMediationServer -Identity <DisplayName> -Fqdn <MediationServerFQDN> -AccessProxyExternalFqdn <EdgeServerExternalFQDN>
   ```

    Identity の場合は、この仲介サーバーに対して作成したユーザーアカウントの表示名を使用します。
    
    *Mediationserverfqdn*の場合は、仲介サーバーに対して定義されている内部 FQDN を使用します。
    
    *EdgeServerExternalFQDN*では、エッジサーバーアクセスプロキシに対して定義されている外部 FQDN を使用します。 複数の Cloud Connector PSTN サイトがある場合は、仲介サーバーが配置されているサイトに割り当てられているエッジサーバーアクセスプロキシの FQDN を選択します。
    
4. 複数の Cloud Connector 仲介サーバー (複数サイト、HA) がある場合は、上記の手順をそれぞれに対して繰り返します。
    

