---
title: Cloud Connector と Office 365 テナントの統合を構成する
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 0e2f2395-b890-4d16-aa2d-99d52438b89c
description: Cloud Connector と Office 365 テナントの統合を構成する方法を説明します。
ms.openlocfilehash: 01e5135a4b0ac6de391140bc6fc0d80bcc00e2ce
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/04/2018
ms.locfileid: "25375770"
---
# <a name="configure-cloud-connector-integration-with-your-office-365-tenant"></a>Cloud Connector と Office 365 テナントの統合を構成する
 
Cloud Connector と Office 365 テナントの統合を構成する方法を説明します。
  
Skype for Business Cloud Connector エディションのインストールが完成したら、このセクションの手順を実行して展開を設定し、Office 365 テナントに接続します。
  
## <a name="configure-firewall-settings"></a>ファイアウォール設定を構成する

境界領域のネットワーク[ポートおよびプロトコル](plan-skype-for-business-cloud-connector-edition.md#BKMB_Ports)で[ビジネス クラウド コネクタ ・ エディションの Skype の計画](plan-skype-for-business-cloud-connector-edition.md)に従って、必要なポートを開く、内部および外部のファイアウォールの設定のファイアウォール設定を構成します。
  
## <a name="set-up-public-switched-telephone-network-pstn-gateways"></a>公衆交換電話網 (PSTN) ゲートウェイをセットアップする

すべてのアプライアンスで仲介サーバーをポイントするように、各 PSTN ゲートウェイのトランクを設定します。プール FQDN はプール内のすべてのサーバーで同じであるため、各トランクは、仲介サーバー プール FQDN ではなく、1 つの仲介サーバーの FQDN または IP アドレスをポイントする必要があります。トランクは同じ優先順位で設定する必要があります。
  
仲介サーバーとゲートウェイ間で TLS を使用している場合は、ゲートウェイと仲介サーバーが MTLS をサポートするように、次のように構成する必要があります。
  
1. ルート CA を Cloud Connector Active Directory コンピューターからエクスポートします。
    
2. ルート CA のインポートについては、PSTN ゲートウェイ ベンダーの指示に従ってください。
    
3. ゲートウェイ用に発行された証明書のルート CA 証明書を仲介サーバーにインポートします。ゲートウェイ用の SSL 証明書を入手する必要がある場合は、次のように Cloud Connector Active Directory コンピューターで証明機関サービスを使用して行うことができます。
    
   - 既存の Web Server テンプレートを変更して認証済みユーザーを登録できるようにするか、新しい Web Server テンプレートを作成して別のプロパティを構成して認証済みユーザーが登録できるようにします。 詳細については、[証明書テンプレート](https://technet.microsoft.com/en-us/library/cc730705.aspx)を参照してください。
    
   - 有効にした Web Server テンプレートを選択して、証明書スナップインを使用して証明書を要求します。 件名に共通名を追加し、別名に DNS 名とゲートウェイの FQDN を追加して、[キー] オプションで秘密キーをエクスポート可能にする [秘密キー] が選択されていることを確認します。 
    
4. 秘密キーを使用して SSL 証明書をエクスポートし、PSTN ゲートウェイ ベンダーから提供された指示に従って、証明書をインポートします。
    
## <a name="update-the-domain-for-your-tenant"></a>テナントのドメインを更新する

Office 365 でドメインを更新する手順を完了し、DNS レコードを追加できることを確認します。 Office 365 でドメインを設定する方法の詳細については、 [Office 365 にドメインの追加](https://support.office.com/en-us/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611)を参照してください。
  
## <a name="add-dns-records-in-office-365-for-your-edge"></a>Office 365 でのエッジに必要な DNS レコードの追加

以下の DNS レコードを Office 365 テナントに追加します。 DNS レコードを Office 365 テナントに追加する方法の詳細については、[追加または編集カスタムの DNS レコード](https://support.office.com/en-us/article/Add-or-edit-custom-DNS-records-in-Office-365-AF00A516-DD39-4EDA-AF3E-1EAF686C8DC9?ui=en-US&amp;rs=en-US&amp;ad=US&amp;fromAR=1)を参照してください。
  
1. アクセス エッジの DNS A レコードを追加します。
    
2. SRV レコードは Office 365 と展開スクリプトで自動的に作成されます。エッジ サーバーで _sip と _sipfederationtls の 2 つの SIP サービスを検索できることを確認します。
    
     ![SRV レコードの確認](../../media/3c353a29-6dcc-4ed3-98db-3a6bed3e929e.png)
  
## <a name="set-up-hybrid-connectivity-between-cloud-connector-edition-and-office-365"></a>Cloud Connector エディションと Office 365 との間でのハイブリッド接続をセットアップする

ビジネス クラウド コネクタのエディションの展開では、Skype と、Office 365 テナントとの間のハイブリッドの接続を構成するには、リモート PowerShell セッションで次のコマンドレットを実行します。 リモート PowerShell セッションを確立する方法についてを参照してください: [Windows PowerShell には、コンピューターを設定](https://technet.microsoft.com/en-us/library/dn362831%28v=ocs.15%29.aspx)します。
  
このコマンドレットでは、アクセス エッジ外部 FQDN が設定されます。 コマンドの最初に、\<アクセス エッジの外部 FQDN\> SIP アクセス エッジ ロールの 1 つにする必要があります。 既定では、この必要があります ap.\<ドメイン名\>。
  
```
Set-CsTenantHybridConfiguration -PeerDestination <External Access Edge FQDN> -UseOnPremDialPlan $false
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $True
```

> [!NOTE]
> ユーザーが PSTN のサイトに割り当てられていない場合にだけ、フォールバックとしてに使用される PSTN のサイトには、ピア ・ ターゲットに使用される外部アクセス エッジの FQDN を設定してください。 詳細については、[クラウドのコネクタで 1 つのサイトを展開](deploy-a-single-site-in-cloud-connector.md)し、[クラウドのコネクタで複数のサイトを展開](deploy-multiple-sites-in-cloud-connector.md)を参照してください。 
  
## <a name="set-up-pstn-gateways"></a>PSTN ゲートウェイの設定

すべてのアプライアンスで仲介サーバーをポイントするように、各 PSTN ゲートウェイのトランクを設定します。プール FQDN はプール内のすべてのサービス プロファイルバージョンで同じであるため、各トランクは、仲介サーバー プール FQDN ではなく、1 つの仲介サーバーの FQDN または IP アドレスをポイントする必要があります。トランクは、同じ優先順位で設定する必要があります。
  
仲介サーバーとゲートウェイ間で TLS を使用している場合は、ゲートウェイと仲介サーバーが MTLS をサポートするように、次のように構成する必要があります。
  
1. ルート CA を Cloud Connector Active Directory コンピューターからエクスポートします。
    
2. ルート CA のインポートについては、PSTN ゲートウェイ ベンダーの指示に従ってください。
    
3. ゲートウェイ用に発行された証明書のルート CA 証明書を仲介サーバーにインポートします。ゲートウェイ用の SSL 証明書を入手する必要がある場合は、次のように Cloud Connector Active Directory コンピューターで証明機関サービスを使用して行うことができます。
    
   - 既存の Web Server テンプレートを変更して認証済みユーザーを登録できるようにするか、新しい Web Server テンプレートを作成して別のプロパティを構成して認証済みユーザーが登録できるようにします。 詳細については、[証明書テンプレート](https://technet.microsoft.com/library/cc730705.aspx)を参照してください。
    
   - 有効にした Web Server テンプレートを選択して、証明書スナップインを使用して証明書を要求します。 件名に共通名を追加し、別名に DNS 名とゲートウェイの FQDN を追加して、[キー] オプションで秘密キーをエクスポート可能にする [秘密キー] が選択されていることを確認します。 
    
4. 秘密キーを使用して SSL 証明書をエクスポートし、PSTN ゲートウェイ ベンダーから提供された指示に従って、証明書をインポートします。
    
5. 1 つの PSTN サイトの PSTN ゲートウェイは、必ず同じサイトの仲介サーバーのみに接続します。
    
## <a name="set-up-your-users-in-office-365"></a>Office 365 でユーザーを設定する

Office 365 管理ポータルにログインし、オンラインの音声サービスに対応するユーザーを追加し、これらのユーザーに E5 ライセンスまたは、E3 ライセンスへの Office 365 の電話システム アドオンを割り当てます。 ユーザーを追加する方法の詳細については、[ビジネス向けの Office 365 のユーザーの追加](https://support.office.com/en-US/article/Add-users-to-Office-365-for-business-435ccec3-09dd-4587-9ebd-2f3cad6bc2bc)を参照してください。
  
## <a name="enable-users-for-phone-system-in-office-365-voice-and-voicemail-services"></a>Office 365 の電話システムの音声およびボイスメール サービスを利用できるようにする

ユーザーを Office 365 に追加したら、ボイス メールを含む、Office 365 の電話システムの音声サービスを利用できるようにします。 これらの機能を有効にするには、Office 365 Global Administrator ロールのアカウントを使用して Office 365 テナントにログ インし、リモート PowerShell を実行できる必要があります。 リモート PowerShell セッションを確立する方法についてを参照してください: [Windows PowerShell には、コンピューターを設定します](https://technet.microsoft.com/en-us/library/dn362831%28v=ocs.15%29.aspx)
  
- ユーザーに、ポリシーを設定し、ユーザーのビジネス電話番号、 **Id**パラメーターの値を指定するを構成します。
    
  ```
  Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI <tel:+phonenumber>
  ```

    > [!NOTE]
    > また、SIP アドレス、ユーザー プリンシパル名 (UPN)、ドメイン名とユーザー名 (domain\username)、および Active Directory での表示名 ("小林 良太") でユーザーの ID を指定することもできます。 
  
これで、次のスクリプトを使ってユーザーが追加され有効化されたことを確認できます。
  
```
# Input the user name you want to verify
$user = Get-CsOnlineUser <User name>

# For a hybrid user, the value of $user.EnterpriseVoiceEnabled should be True
$user.EnterpriseVoiceEnabled

# For a hybrid user, the value of $user.HostedVoiceMail should be True
$user.HostedVoiceMail

# For a hybrid user, the value of $user.VoicePolicy should be "HybridVoice"
$user.VoicePolicy
```

ユーザーが国際通話を使えるようにするかどうかを決める必要があります。デフォルトでは、国際通話は有効です。オンラインの Skype for Business 管理センターを使ってユーザーの国際電話を無効化または有効化できます。
  
ユーザー単位で国際電話を無効にするには、Skype for Business Online PowerShell で次のコマンドレットを実行します。
  
```
Grant-CsVoiceRoutingPolicy -PolicyName InternationalCallsDisallowed -Identity $user
```

国際ユーザーごとに無効になっていますが後に呼び出すことを再度有効に、同じコマンドレットを実行、**グループ**の値を*InternationalCallsAllowed*に変更します。
  
## <a name="assign-users-to-pstn-sites"></a>ユーザーを PSTN サイトに割り当てる

サイトを 1 つだけ展開した場合でも、テナントのリモート PowerShell を使用して、サイトをユーザーに割り当てます。 リモート PowerShell セッションを確立する方法についてを参照してください: [Windows PowerShell には、コンピューターを設定](https://technet.microsoft.com/en-us/library/dn362831%28v=ocs.15%29.aspx)します。
  
```
# Set the site to users
Set-CsUserPstnSettings -Identity <User Name> -HybridPstnSite <PSTN Site Name>

# Review the site setting for a user
Get-CsUserPstnSettings -Identity <User Name> 

# See all the user settings in one tenant
Get-CsOnlineUser | Get-CsUserPstnSettings
```

> [!NOTE]
> ユーザーに PSTN サイトを割り当てないと、Skype for Business Cloud Connector エディションの展開と Office 365 テナント間のハイブリッド接続がフォールバックし、通話が完了できるようにテナント レベルの既定のもの (ピア ターゲット) が使用されることになります。 
  
## <a name="configure-online-hybrid-mediation-server-settings"></a>オンラインのハイブリッド仲介サーバーの設定を構成する
<a name="BKMK_ConfigureMediationServer"> </a>

P2P の呼び出しは、PSTN 会議にエスカレートされ、オンライン ビジネスの会議サーバーの Skype は招待をクラウド コネクタの仲介サーバーに送信されます。 Office 365 のルーティングで招待が正常に処理できることを確認するには、次のように、オンラインのテナント クラウド コネクタの仲介サーバーごとに設定を構成する必要があります。 
  
1. Office 365 管理ポータルでユーザーを作成します。 」MediationServer1。」などの必要な任意のユーザー名を使用します。
    
    クラウド コネクタ (.ini ファイルの最初の SIP ドメイン) の既定の SIP ドメインをユーザー ドメインとして使用します。
    
    なお、ライセンスの割り当てはのみ、ユーザーに伝達、Skype のビジネスのオンライン ディレクトリに必要な。 アカウントを作成、変更を反映するためには、最大で 1 時間を許可し、このアカウントからライセンスを削除するには、(E5) などの Office 365 のライセンスを割り当てます。
    
2. グローバルを使用してテナント Azure AD リモート PowerShell セッションまたはユーザー管理者の資格情報を起動し、Azure AD ユーザー アカウントの部門を設定するのには次のコマンドレットのように構成しの実行はステップ 1 を"HybridMediationServer"にします。

   ```
   Set-MsolUser -UserPrincipalName <UserPrincipalName> -Department "HybridMediationServer"
   ```

3. テナント Skype をビジネス テナント管理者の資格情報、し、そのユーザーに、仲介サーバーとエッジ サーバーの FQDN を設定するのには次のコマンドレットのアカウント、交換用の Skype を使用してビジネス リモート PowerShell セッションを開始\<表示名\>アカウントのユーザーの表示名では、手順 1 で作成します。
    
   ```
   Set-CsHybridMediationServer -Identity <DisplayName> -Fqdn <MediationServerFQDN> -AccessProxyExternalFqdn <EdgeServerExternalFQDN>
   ```

    ID については、仲介サーバーに対して作成した Office 365 ユーザー　アカウントの表示名を使用してください。
    
    *MediationServerFQDN* 、仲介サーバーの定義の内部 FQDN を使用します。
    
    *EdgeServerExternalFQDN* 、エッジ サーバーのアクセス プロキシに定義されている外部 FQDN を使用します。 複数の Cloud Connector　PSTN サイトがある場合は、仲介サーバーが配置されているサイトに割り当てられているエッジ サーバー アクセス プロキシ の FQDN を選択します。
    
4. 複数の Cloud Connector 仲介サーバー (マルチサイト、HA) がある場合は、前述の手順を各サーバーに対して繰り返してください。
    

