---
title: オンプレミスの Exchange と Skype for Business Online 間での OAuth の構成
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 8/8/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ffe4c3ba-7bab-49f1-b229-5142a87f94e6
description: OAuth を構成するオンライン ビジネスの社内の Exchange と Skype との間の認証は、ビジネスおよび Exchange の統合機能の機能のサポート」に記載の Skype を使用できます。
ms.openlocfilehash: adb811a8934fdc6ea574dc934efa57ee28e6fba6
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="configure-oauth-between-skype-for-business-online-and-exchange-on-premises"></a>オンプレミスの Exchange と Skype for Business Online 間での OAuth の構成
 
OAuth を構成するオンライン ビジネスの社内の Exchange と Skype との間の認証は、Skype の[機能のサポート](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support)」で説明されているビジネスと Exchange の統合の機能を使用できます。
  
2016 の Exchange Server および Exchange Server 2013 に、このトピックに適用されます。
  
## <a name="what-do-you-need-to-know-before-you-begin"></a>事前に必要な知識

- このタスクを完了するまでの予想所要時間: 15 分
    
-  この手順を実行するには、アクセス許可が割り当てられている必要があります。 必要なアクセス許可を表示するには、 [Exchange およびシェル インフラストラクチャのアクセス許可](https://go.microsoft.com/fwlink/p/?LinkId=746511)を参照してください。
    
- このトピックの手順に適用されるキーボード ショートカットの詳細については、 [Exchange 管理センターでのキーボード ショートカット]( https://go.microsoft.com/fwlink/p/?LinkId=746512)を参照してください。
    
## <a name="configure-oauth-authentication-between-your-on-premises-exchange-and-skype-for-business-organizations"></a>オンプレミスの Exchange と Skype for Business 組織の間で OAuth 認証を構成する

### <a name="step-1-create-an-authorization-server-object-for-your-skype-for-business-online-organization"></a>手順 1:  Skype for Business Online 組織の承認サーバー オブジェクトを作成する

オンライン ビジネスの組織は、Skype の検証済みのドメインを指定します。 このドメインは、クラウド ベースのアカウントに使用したプライマリ SIP ドメインと同じドメインであることが必要です。 このドメインと呼ばれる\<、検証済みのドメイン\>、次の手順にします。
  
設置型で、Exchange 管理シェル (Exchange の PowerShell) Exchange 組織で次のコマンドを実行します。
  
```
New-AuthServer -Name "WindowsAzureACS" -AuthMetadataUrl "https://accounts.accesscontrol.windows.net/<your Verified Domain>/metadata/json/1" 
```

### <a name="step-2-enable-the-partner-application-for-your-skype-for-business-online-organization"></a>手順 2:  Skype for Business Online 組織に対してパートナー アプリケーションを有効にする

設置型で、Exchange の PowerShell Exchange 組織で次のコマンドを実行します。
  
```
Get-PartnerApplication | ?{$_.ApplicationIdentifier -eq "00000002-0000-0ff1-ce00-000000000000" -and $_.Realm -eq ""} | Set-PartnerApplication -Enabled $true
```

### <a name="step-3-create-a-new-mail-user-account-for-the-skype-for-business-online-partner-application"></a>手順 3: Skype for Business Online のパートナー アプリケーションの新しいメール ユーザー アカウントを作成する

この手順は、オンプレミスで実行します。これによって、メール ユーザーを作成し、適切な管理役割の権限を割り当てます。このアカウントは、次の手順で使用します。
  
Exchange 組織用の検証済みのドメインを指定します。 このドメインは、オンプレミスの Exchange アカウントを使用するプライマリ SMTP ドメインとして使用する同じドメインにする必要があります。 このドメインと呼ばれる\<、検証済みのドメイン\>、次の手順にします。 また、 \<DomainControllerFQDN\>ドメイン コント ローラーの FQDN である必要があります。 
  
```
$user = New-MailUser -Name SfBOnline-ApplicationAccount -ExternalEmailAddress SfBOnline-ApplicationAccount@<your Verified Domain> -DomainController <DomainControllerFQDN> 
```

このコマンドによって、アドレス一覧で新しいメール ユーザーが非表示になります。
  
```
Set-MailUser -Identity $user.Identity -HiddenFromAddressListsEnabled $True -DomainController <DomainControllerFQDN> 
```

次の 2 つのコマンドでは、この新しいアカウントに UserApplication および ArchiveApplication の管理役割を割り当てます。
  
```
New-ManagementRoleAssignment -Role UserApplication -User $user.Identity -DomainController <DomainControllerFQDN> 

```

```
New-ManagementRoleAssignment -Role ArchiveApplication -User $user.Identity -DomainController <DomainControllerFQDN> 
```

### <a name="step-4-create-and-enable-a-partner-application-for-skype-for-business-online"></a>手順 4: Skype for Business Online のパートナー アプリケーションを作成して有効にする

新しいパートナー アプリケーションを作成し、先に作成したアカウントを使用します。 設置型で、Exchange の PowerShell Exchange 組織で次のコマンドを実行します。 
  
```
New-PartnerApplication -Name SfBOnline -ApplicationIdentifier 00000004-0000-0ff1-ce00-000000000000 -Enabled $True -LinkedAccount $user.Identity
```

### <a name="step-5-export-the-on-premises-authorization-certificate"></a>手順 5: オンプレミスの認証証明書をエクスポートする

設置承認証明書をエクスポート、インポート、次の手順でオンライン ビジネスの組織は、Skype をする PowerShell スクリプトを実行します。
  
次のテキストを、たとえば ExportAuthCert.ps1 という名前の PowerShell スクリプト ファイルに保存します。
  
```
$thumbprint = (Get-AuthConfig).CurrentCertificateThumbprint 
if((test-path $env:SYSTEMDRIVE\OAuthConfig) -eq $false) 
{ 
md $env:SYSTEMDRIVE\OAuthConfig 
} 
cd $env:SYSTEMDRIVE\OAuthConfig 
$oAuthCert = (dir Cert:\LocalMachine\My) | where {$_.Thumbprint -match $thumbprint} 
$certType = [System.Security.Cryptography.X509Certificates.X509ContentType]::Cert 
$certBytes = $oAuthCert.Export($certType) 
$CertFile = "$env:SYSTEMDRIVE\OAuthConfig\OAuthCert.cer" 
[System.IO.File]::WriteAllBytes($CertFile, $certBytes) 
```

Exchange、オンプレミスの Exchange 組織内の PowerShell では、作成した PowerShell のスクリプトを実行します。 例:.\ExportAuthCert.ps1
  
### <a name="step-6-upload-the-on-premises-authorization-certificate-to-azure-active-directory-acs"></a>手順 6: Azure Active Directory ACS にオンプレミス認証証明書をアップロードする

次に、Windows PowerShell を使用して、先の手順でエクスポートしたオンプレミス認証証明書を Azure Active Directory アクセス制御サービス (ACS) にアップロードします。 このためには、Windows PowerShell コマンドレット用の Azure Active Directory モジュールが既にインストールされていることが必要です。 インストールされていない場合に、 [https://aka.ms/aadposh](https://aka.ms/aadposh) 、Azure Active Directory モジュールを Windows PowerShell をインストールするのには。 Windows PowerShell 用 Azure Active Directory モジュールのインストール後、次の手順を完了します。
  
1. **Windows PowerShell 用 Azure Active Directory モジュール**のショートカットをクリックして、Azure AD コマンドレットがインストールされた Windows PowerShell ワークスペースを開きます。この手順のすべてのコマンドは、Azure Active Directory コンソール用 Windows PowerShell を使用して実行します。
    
2. たとえば、PowerShell スクリプト ファイルに次のテキストを保存`UploadAuthCert.ps1`。
    
  ```
  Connect-MsolService; 
Import-Module msonlineextended; 
$CertFile = "$env:SYSTEMDRIVE\OAuthConfig\OAuthCert.cer" 
$objFSO = New-Object -ComObject Scripting.FileSystemObject; 
$CertFile = $objFSO.GetAbsolutePathName($CertFile); 
$cer = New-Object System.Security.Cryptography.X509Certificates.X509Certificate 
$cer.Import($CertFile); 
$binCert = $cer.GetRawCertData(); 
$credValue = [System.Convert]::ToBase64String($binCert); 
$ServiceName = "00000002-0000-0ff1-ce00-000000000000"; 
$p = Get-MsolServicePrincipal -ServicePrincipalName $ServiceName 
New-MsolServicePrincipalCredential -AppPrincipalId $p.AppPrincipalId -Type asymmetric -Usage Verify -Value $credValue 
  ```

3. 先の手順で作成した PowerShell スクリプトを実行します。 例えば：`.\UploadAuthCert.ps1`
    
4. スクリプトの開始後、[資格情報] ダイアログ ボックスが表示されます。Microsoft Online Azure AD 組織のテナント管理者アカウントの資格情報を入力します。スクリプトを実行した後に、Azure AD セッションで Windows PowerShell を開いたままにします。次の手順では、これを使用して PowerShell スクリプトを実行します。
    
### <a name="step-7-register-the-hostname-authorities-for-the-smtp-domain"></a>手順 7: SMTP ドメインに対するホスト名の機関を登録する

Exchange 組織用の検証済みのドメインを指定します。 このドメインは、オンプレミスの Exchange アカウントを使用するプライマリ SMTP ドメインとして使用する同じドメインにする必要があります。 このドメインと呼ばれる\<、検証済みのドメイン\>、次の手順にします。
  
> [!NOTE]
> 次のスクリプトを正常に実行するには、先のセクションの手順 4 で説明したように、Azure Active Directory 用 Windows PowerShell を Microsoft Online Azure AD テナントに接続することが必要です。 
  
1. 次のテキストを、たとえば RegisterEndpoints.ps1 という名前の PowerShell スクリプト ファイルに保存します。 この例では、ワイルドカードを使用して、contoso.com のすべてのエンドポイントを登録します。Contoso.com を交換して、オンプレミスの Exchange 組織のホスト名の権限を持つ
    
  ```
  $externalAuthority="*.<your Verified Domain>" 
$ServiceName = "00000002-0000-0ff1-ce00-000000000000"; 
$p = Get-MsolServicePrincipal -ServicePrincipalName $ServiceName; 
$spn = [string]::Format("{0}/{1}", $ServiceName, $externalAuthority); 
$p.ServicePrincipalNames.Add($spn); 
Set-MsolServicePrincipal -ObjectID $p.ObjectId -ServicePrincipalNames $p.ServicePrincipalNames; 
  ```

2.  Azure Active Directory 用 Windows PowerShell で、先の手順で作成した Windows PowerShell スクリプトを実行します。 たとえば、`.\RegisterEndpoints.ps1` などです
    
### <a name="verify-your-success"></a>成否を確認する

Outlook の [会話履歴] フォルダーにモバイル クライアントの会話履歴が表示されるかなど、いくつかの機能が正常に動作するかどうかを調べ、OAuth 構成が正しいことを確認します。
  
1. Windows Phone または iOS デバイスのモバイル アプリケーションのビジネス用の Skype を起動し、Exchange 2016 またはオンプレミスのメールボックスを Exchange 2013 を使用してオンライン ビジネスのユーザーは、Skype にサインインします。
    
2. オンライン ビジネスのユーザーに別の Skype のインスタント メッセージ会話があります。
    
3. [IM 会話] ウィンドウを閉じます。
    
4. このユーザーに対して Outlook を起動し、Outlook の [会話履歴] フォルダーに会話が表示されることを確認します。
    

