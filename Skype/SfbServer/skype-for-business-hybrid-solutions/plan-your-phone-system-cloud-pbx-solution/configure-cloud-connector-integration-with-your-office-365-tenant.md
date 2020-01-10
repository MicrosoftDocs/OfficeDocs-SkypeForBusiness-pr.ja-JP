---
title: Cloud Connector と Office 365 テナントの統合を構成する
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 0e2f2395-b890-4d16-aa2d-99d52438b89c
description: Cloud Connector と Office 365 テナントの統合を構成する方法を説明します。
ms.openlocfilehash: ed9437026ddbae07aadbe81585886ed0cb5cb0cc
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/09/2020
ms.locfileid: "41002857"
---
# <a name="configure-cloud-connector-integration-with-your-office-365-tenant"></a>Configure Cloud Connector integration with your Office 365 tenant
 
Cloud Connector と Office 365 テナントの統合を構成する方法を説明します。
  
Skype for Business Cloud Connector エディションのインストールが完成したら、このセクションの手順を実行して展開を設定し、Office 365 テナントに接続します。
  
## <a name="configure-firewall-settings"></a>ファイアウォール設定を構成する

境界ネットワークの内部および外部ファイアウォール設定のファイアウォール設定を構成して、「 [Skype For Business Cloud Connector エディションのプラン](plan-skype-for-business-cloud-connector-edition.md)の[ポートとプロトコル](plan-skype-for-business-cloud-connector-edition.md#BKMB_Ports)」で説明されているように、必要なポートを開きます。
  
## <a name="set-up-public-switched-telephone-network-pstn-gateways"></a>公衆交換電話網 (PSTN) ゲートウェイをセットアップする

すべてのアプライアンスで仲介サーバーをポイントするように、各 PSTN ゲートウェイのトランクを設定します。プール FQDN はプール内のすべてのサーバーで同じであるため、各トランクは、仲介サーバー プール FQDN ではなく、1 つの仲介サーバーの FQDN または IP アドレスをポイントする必要があります。トランクは同じ優先順位で設定する必要があります。
  
仲介サーバーとゲートウェイ間で TLS を使用している場合は、ゲートウェイと仲介サーバーが MTLS をサポートするように、次のように構成する必要があります。
  
1. ルート CA を Cloud Connector Active Directory コンピューターからエクスポートします。
    
2. ルート CA のインポートについては、PSTN ゲートウェイ ベンダーの指示に従ってください。
    
3. ゲートウェイ用に発行された証明書のルート CA 証明書を仲介サーバーにインポートします。ゲートウェイ用の SSL 証明書を入手する必要がある場合は、次のように Cloud Connector Active Directory コンピューターで証明機関サービスを使用して行うことができます。
    
   - 既存の Web Server テンプレートを変更して認証済みユーザーを登録できるようにするか、新しい Web Server テンプレートを作成して別のプロパティを構成して認証済みユーザーが登録できるようにします。 詳細な手順については、「[証明書テンプレート](https://technet.microsoft.com/en-us/library/cc730705.aspx)」を参照してください。
    
   - 有効にした Web Server テンプレートを選択して、証明書スナップインを使用して証明書を要求します。 件名に共通名を追加し、別名に DNS 名とゲートウェイの FQDN を追加して、[キー] オプションで秘密キーをエクスポート可能にする [秘密キー] が選択されていることを確認します。 
    
4. 秘密キーを使用して SSL 証明書をエクスポートし、PSTN ゲートウェイ ベンダーから提供された指示に従って、証明書をインポートします。
    
## <a name="update-the-domain-for-your-tenant"></a>テナントのドメインを更新する

Office 365 でドメインを更新する手順を完了し、DNS レコードを追加できることを確認します。 Office 365 でドメインをセットアップする方法の詳細については、「 [office 365 にドメインを追加](https://support.office.com/en-us/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611)する」を参照してください。
  
## <a name="add-dns-records-in-office-365-for-your-edge"></a>Office 365 でのエッジに必要な DNS レコードの追加

以下の DNS レコードを Office 365 テナントに追加します。 Office 365 テナントに DNS レコードを追加する方法については、「 [office 365 でカスタム dns レコードを追加または編集](https://support.office.com/en-us/article/Add-or-edit-custom-DNS-records-in-Office-365-AF00A516-DD39-4EDA-AF3E-1EAF686C8DC9?ui=en-US&amp;rs=en-US&amp;ad=US&amp;fromAR=1)する」を参照してください。
  
1. アクセス エッジの DNS A レコードを追加します。
    
2. SRV レコードは Office 365 と展開スクリプトで自動的に作成されます。エッジ サーバーで _sip と _sipfederationtls の 2 つの SIP サービスを検索できることを確認します。
    
     ![SRV レコードの確認](../../media/3c353a29-6dcc-4ed3-98db-3a6bed3e929e.png)
  
## <a name="set-up-hybrid-connectivity-between-cloud-connector-edition-and-office-365"></a>Cloud Connector エディションと Office 365 との間でのハイブリッド接続をセットアップする

Skype for Business Cloud Connector エディションの展開と Office 365 テナントの間のハイブリッド接続を構成するには、リモート PowerShell セッションで次のコマンドレットを実行します。 リモート PowerShell セッションを確立する方法については、「 [Windows PowerShell 用にコンピューターを](https://technet.microsoft.com/en-us/library/dn362831%28v=ocs.15%29.aspx)セットアップする」を参照してください。
  
このコマンドレットでは、アクセス エッジ外部 FQDN が設定されます。 コマンドの最初の部分では、 \<外部アクセスエッジ FQDN\>が SIP アクセスエッジロール用である必要があります。 既定では、これは ap の\<ドメイン名\>である必要があります。
  
```powershell
Set-CsTenantHybridConfiguration -PeerDestination <External Access Edge FQDN> -UseOnPremDialPlan $false
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $True
```

> [!NOTE]
> ピアの宛先として使用される外部アクセスエッジの FQDN は、ユーザーが PSTN サイトに割り当てられていない場合にのみフォールバックとして使用される PSTN サイトに設定する必要があります。 詳細については、「[Deploy a single site in Cloud Connector](deploy-a-single-site-in-cloud-connector.md)」および「[Deploy multiple sites in Cloud Connector](deploy-multiple-sites-in-cloud-connector.md)」を参照してください。 
  
## <a name="set-up-pstn-gateways"></a>PSTN ゲートウェイの設定

すべてのアプライアンスで仲介サーバーをポイントするように、各 PSTN ゲートウェイのトランクを設定します。プール FQDN はプール内のすべてのサービス プロファイルバージョンで同じであるため、各トランクは、仲介サーバー プール FQDN ではなく、1 つの仲介サーバーの FQDN または IP アドレスをポイントする必要があります。トランクは、同じ優先順位で設定する必要があります。
  
仲介サーバーとゲートウェイ間で TLS を使用している場合は、ゲートウェイと仲介サーバーが MTLS をサポートするように、次のように構成する必要があります。
  
1. ルート CA を Cloud Connector Active Directory コンピューターからエクスポートします。
    
2. ルート CA のインポートについては、PSTN ゲートウェイ ベンダーの指示に従ってください。
    
3. ゲートウェイ用に発行された証明書のルート CA 証明書を仲介サーバーにインポートします。ゲートウェイ用の SSL 証明書を入手する必要がある場合は、次のように Cloud Connector Active Directory コンピューターで証明機関サービスを使用して行うことができます。
    
   - 既存の Web Server テンプレートを変更して認証済みユーザーを登録できるようにするか、新しい Web Server テンプレートを作成して別のプロパティを構成して認証済みユーザーが登録できるようにします。 詳細な手順については、「[証明書テンプレート](https://technet.microsoft.com/library/cc730705.aspx)」を参照してください。
    
   - 有効にした Web Server テンプレートを選択して、証明書スナップインを使用して証明書を要求します。 件名に共通名を追加し、別名に DNS 名とゲートウェイの FQDN を追加して、[キー] オプションで秘密キーをエクスポート可能にする [秘密キー] が選択されていることを確認します。 
    
4. 秘密キーを使用して SSL 証明書をエクスポートし、PSTN ゲートウェイ ベンダーから提供された指示に従って、証明書をインポートします。
    
5. 1 つの PSTN サイトの PSTN ゲートウェイは、必ず同じサイトの仲介サーバーのみに接続します。
    
## <a name="set-up-your-users-in-office-365"></a>Office 365 でユーザーを設定する

Office 365 管理ポータルにログインし、オンラインの音声サービスに対応するユーザーを追加し、これらのユーザーに E5 ライセンスまたは、E3 ライセンスへの Office 365 の電話システム アドオンを割り当てます。 ユーザーの追加については、「一般[法人向け Office 365 にユーザーを追加する](https://support.office.com/en-US/article/Add-users-to-Office-365-for-business-435ccec3-09dd-4587-9ebd-2f3cad6bc2bc)」を参照してください。
  
## <a name="enable-users-for-phone-system-in-office-365-voice-and-voicemail-services"></a>Office 365 の電話システムの音声およびボイスメール サービスを利用できるようにする

ユーザーを Office 365 に追加したら、ボイス メールを含む、Office 365 の電話システムの音声サービスを利用できるようにします。 これらの機能を有効にするには、Office 365 Global Administrator ロールのアカウントを使用して Office 365 テナントにログ インし、リモート PowerShell を実行できる必要があります。 リモート PowerShell セッションを確立する方法については、「 [Windows PowerShell 用にコンピューターを](https://technet.microsoft.com/en-us/library/dn362831%28v=ocs.15%29.aspx)セットアップする」を参照してください。
  
- ユーザーにポリシーを割り当て、 **Identity**パラメーターの値で指定するユーザーのビジネスボイス電話番号を設定します。
    
  ```powershell
  Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI <tel:+phonenumber>
  ```

    > [!NOTE]
    > ユーザー id は、ユーザーの SIP アドレス、ユーザープリンシパル名 (UPN)、またはユーザーの Active Directory 表示名 (たとえば、"Bob 友野") を使用して指定できます。 アスタリスク (\*) 文字は、ユーザー id として表示名と共に使うこともできます。 たとえば、"\*smith" という id を指定すると、"smith" という文字列で終わる表示名を持つすべてのユーザーが返されます。
  
これで、次のスクリプトを使ってユーザーが追加され有効化されたことを確認できます。
  
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

ユーザーが国際通話を使えるようにするかどうかを決める必要があります。デフォルトでは、国際通話は有効です。オンラインの Skype for Business 管理センターを使ってユーザーの国際電話を無効化または有効化できます。
  
ユーザー単位で国際電話を無効にするには、Skype for Business Online PowerShell で次のコマンドレットを実行します。
  
```powershell
Grant-CsVoiceRoutingPolicy -PolicyName InternationalCallsDisallowed -Identity $user
```

無効にした後で、ユーザーごとに国際通話を再び有効にするには、同じコマンドレットを実行しますが、 **PolicyName**の値を*InternationalCallsAllowed*に変更します。
  
## <a name="assign-users-to-pstn-sites"></a>ユーザーを PSTN サイトに割り当てる

サイトを 1 つだけ展開した場合でも、テナントのリモート PowerShell を使用して、サイトをユーザーに割り当てます。 リモート PowerShell セッションを確立する方法については、「 [Windows PowerShell 用にコンピューターを](https://technet.microsoft.com/en-us/library/dn362831%28v=ocs.15%29.aspx)セットアップする」を参照してください。
  
```powershell
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

P2P 通話が PSTN 会議にエスカレートされると、Skype for Business Online 会議サーバーは、クラウドコネクタ仲介サーバーに招待を送信します。 Office 365 がこの招待を正しくルーティングできることを確認するには、次のようにして、各クラウドコネクタの仲介サーバーのオンラインテナントで設定を構成する必要があります。 
  
1. Office 365 管理ポータルでユーザーを作成します。 "MediationServer1" など、任意のユーザー名を入力します。
    
    クラウドコネクタの既定の SIP ドメイン (.ini ファイル内の最初の SIP ドメイン) をユーザードメインとして使用します。
    
    ライセンスの割り当てが必要になるのは、ユーザーが Skype for Business online ディレクトリに伝播する場合のみです。 作成したアカウントに Office 365 ライセンス (E5 など) を割り当て、その変更が反映されるまで1時間ほどかかります。次のコマンドレットを実行して、ユーザーアカウントが Skype for Business online ディレクトリに正しくプロビジョニングされていることを確認します。このアカウントのライセンス。
    ```powershell
   Get-CsOnlineUser -Identity <UserPrincipalName>
   ```
    
2. グローバルまたはユーザーの管理者資格情報を使用してテナント Azure AD リモート PowerShell セッションを開始し、次のコマンドレットを実行して、手順1で構成された Azure AD ユーザーアカウントの部門を "HybridMediationServer" に設定します。

   ```powershell
   Set-MsolUser -UserPrincipalName <UserPrincipalName> -Department "HybridMediationServer"
   ```

3. Skype for Business テナント管理者の資格情報を使用して、Skype for business のテナントのリモート PowerShell セッションを開始し、次のコマンドレットを実行して、仲介サーバーと\<エッジ\>サーバーの FQDN をそのユーザーアカウントに設定します。ここでは、手順1で作成したアカウントのユーザーの表示名で DisplayName を置き換えます。
    
   ```powershell
   Set-CsHybridMediationServer -Identity <DisplayName> -Fqdn <MediationServerFQDN> -AccessProxyExternalFqdn <EdgeServerExternalFQDN>
   ```

    ID については、仲介サーバーに対して作成した Office 365 ユーザー　アカウントの表示名を使用してください。
    
    *Mediationserverfqdn*の場合は、仲介サーバーに対して定義された内部 FQDN を使用します。
    
    *EdgeServerExternalFQDN*の場合は、Edge Server アクセスプロキシ用に定義された外部 FQDN を使用します。 複数の Cloud Connector　PSTN サイトがある場合は、仲介サーバーが配置されているサイトに割り当てられているエッジ サーバー アクセス プロキシ の FQDN を選択します。
    
4. 複数の Cloud Connector 仲介サーバー (マルチサイト、HA) がある場合は、前述の手順を各サーバーに対して繰り返してください。
    

