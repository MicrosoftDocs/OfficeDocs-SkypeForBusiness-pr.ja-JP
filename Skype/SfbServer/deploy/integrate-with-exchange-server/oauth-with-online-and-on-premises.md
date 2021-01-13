---
title: Skype for Business Online と Exchange サーバーの統合
ms.reviewer: cbland
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 4/2/2019
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ffe4c3ba-7bab-49f1-b229-5142a87f94e6
description: オンプレミスの Exchange と Skype for Business Online の間で OAuth 認証を構成すると、機能のサポートで説明されている Skype for Business と Exchange 統合の機能が有効です。
ms.openlocfilehash: ac8bfe2f30e813e47a0256a68e4e81852d5bae68
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49833977"
---
# <a name="configure-integration-and-oauth-between-skype-for-business-online-and-exchange-server"></a>Skype for Business Online と Skype for Business Online の間の統合と OAuth のExchange Server 

Exchange サーバーと Skype for Business Online の統合を構成すると、機能のサポートで説明されている Skype for Business と Exchange の統合 [機能が有効になります](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support)。

このトピックは、2013 年から 2019 年Exchange Server統合に適用されます。

## <a name="what-do-you-need-to-know-before-you-begin"></a>始める前に把握しておくべき情報

- このタスクの予想所要時間:15 分

-  この手順を実行する際は、あらかじめアクセス許可を割り当てる必要があります。 必要なアクセス許可の一覧については、Exchange およびシェル インフラストラクチャのアクセス許可のトピック [を参照](https://go.microsoft.com/fwlink/p/?LinkId=746511) してください。

- このトピックの手順で使用可能なキーボード ショートカットについては、「[Exchange 管理センターのキーボード ショートカット]( https://go.microsoft.com/fwlink/p/?LinkId=746512)」を参照してください。

- 互換性の詳細については [、「Skype for Business と Office」を参照してください](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/compatibility-with-office)。

## <a name="configure-integration-between-exchange-server-and-o365"></a>O365 と Exchange Serverの統合を構成する

### <a name="step-1-configure-oauth-authentication-between-exchange-server-and-o365"></a>手順 1: O365 と Exchange Server OAuth 認証を構成する

次の記事の手順を実行します。

[Exchange と Exchange Online 組織の間の OAuth 認証を構成する](https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)

### <a name="step-2-create-a-new-mail-user-account-for-the-skype-for-business-online-partner-application"></a>手順 2: Skype for Business Online パートナー アプリケーションの新しいメール ユーザー アカウントを作成する

この手順は、Exchange サーバーで実行します。 メール ユーザーを作成し、適切な管理役割の権限を割り当てる。 このアカウントは、次の手順で使用されます。

Exchange 組織の確認済みドメインを指定します。 このドメインは、オンプレミスの Exchange アカウントで使用されるプライマリ SMTP ドメインと同じドメインである必要があります。 このドメインは、次の \<your Verified Domain\> 手順で参照されます。 また、 \<DomainControllerFQDN\> ドメイン コントローラーの FQDN である必要があります。

```powershell
$user = New-MailUser -Name SfBOnline-ApplicationAccount -ExternalEmailAddress SfBOnline-ApplicationAccount@<your Verified Domain> -DomainController <DomainControllerFQDN>
```

このコマンドを実行すると、新しいメール ユーザーがアドレス一覧で非表示にされます。

```powershell
Set-MailUser -Identity $user.Identity -HiddenFromAddressListsEnabled $True -DomainController <DomainControllerFQDN>
```

次の 2 つのコマンドは、UserApplication および ArchiveApplication 管理役割をこの新しいアカウントに割り当てる予定です。

```powershell
New-ManagementRoleAssignment -Role UserApplication -User $user.Identity -DomainController <DomainControllerFQDN>
```

```powershell
New-ManagementRoleAssignment -Role ArchiveApplication -User $user.Identity -DomainController <DomainControllerFQDN>
```

### <a name="step-3-create-and-enable-a-partner-application-for-skype-for-business-online"></a>手順 3: Skype for Business Online のパートナー アプリケーションを作成して有効にする 

新しいパートナー アプリケーションを作成し、作成したアカウントを使用します。 社内 Exchange 組織の Exchange PowerShell で、次のコマンドを実行します。

```powershell
New-PartnerApplication -Name SfBOnline -ApplicationIdentifier 00000004-0000-0ff1-ce00-000000000000 -Enabled $True -LinkedAccount $user.Identity
```

### <a name="step-4-export-the-on-premises-authorization-certificate"></a>手順 4: オンプレミスの承認証明書をエクスポートする

PowerShell スクリプトを実行してオンプレミスの認証証明書をエクスポートします。この証明書は、次の手順で Skype for Business Online 組織にインポートします。

次のテキストを、たとえば ExportAuthCert.ps1 という名前の PowerShell スクリプト ファイルに保存します。

```powershell
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

オンプレミスの Exchange 組織の Exchange PowerShell で、作成した PowerShell スクリプトを実行します。 例: .\ExportAuthCert.ps1

### <a name="step-5-upload-the-on-premises-authorization-certificate-to-azure-active-directory-acs"></a>手順 5: オンプレミスの認証証明書を Azure Active Directory ACS にアップロードする

次に、Windows PowerShellを使用して、前の手順でエクスポートしたオンプレミスの認証証明書を Azure Active Directory アクセス制御サービス (ACS) にアップロードします。 これを行うには、Azure Active Directory Module for Windows PowerShellコマンドレットが既にインストールされている必要があります。 インストールされていない場合、[https://aka.ms/aadposh](https://aka.ms/aadposh) に移動して、Windows PowerShell の Azure Active Directory モジュール をインストールしてください。 Windows PowerShell の Azure Active Directory モジュール のインストール後、以下の手順を実行します。

1. **[Windows PowerShell 用 Azure Active Directory モジュール]** ショートカットをクリックして、Azure AD コマンドレットがインストールされた Windows PowerShell ワークスペースを開きます。この手順のすべてのコマンドは、Azure Active Directory コンソール用の Windows PowerShell を使用して実行されます。

2. 次のテキストを PowerShell スクリプト ファイルに保存します(例: `UploadAuthCert.ps1`

   ```powershell
   Connect-MsolService;
   Import-Module msonlineextended;
   $CertFile = "$env:SYSTEMDRIVE\OAuthConfig\OAuthCert.cer"
   $objFSO = New-Object -ComObject Scripting.FileSystemObject;
   $CertFile = $objFSO.GetAbsolutePathName($CertFile);
   $cer = New-Object System.Security.Cryptography.X509Certificates.X509Certificate
   $cer.Import($CertFile);
   $binCert = $cer.GetRawCertData();
   $credValue = [System.Convert]::ToBase64String($binCert);
   $ServiceName = "00000004-0000-0ff1-ce00-000000000000";
   $p = Get-MsolServicePrincipal -ServicePrincipalName $ServiceName
   New-MsolServicePrincipalCredential -AppPrincipalId $p.AppPrincipalId -Type asymmetric -Usage Verify -Value $credValue
   ```

3. 直前の手順で作成した PowerShell スクリプトを実行します。 例:  `.\UploadAuthCert.ps1`

4. スクリプトを起動した後に、[資格情報] ダイアログ ボックスが表示されます。 Microsoft Online Azure 組織のテナント管理者アカウントの資格情報ADします。 スクリプトの実行後、Azure AD 用 Windows PowerShell セッションを開いたままにします。 これは、次のステップで PowerShell スクリプトを実行するために使用します。

### <a name="step-6-verify-that-the-certificate-has-uploaded-to-the-skype-for-business-service-principal"></a>手順 6: 証明書が Skype for Business サービス プリンシパルにアップロードされたのを確認する
1. Azure Active Directory で開いて認証された PowerShell で、次のコマンドを実行します。
```powershell
Get-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000
```
2. ReturnKeyValues の入力を求めるメッセージが表示されたら、Enter キーを押します。
3. Exchange Oauth 証明書の開始日と終了日に一致する開始日と終了日のデータが一覧表示されているキーが表示される

### <a name="verify-your-success"></a>成功を確認する

一部の機能が正常に動作していることを確認して、構成が正しいか確認します。 

1. クラウド ボイスメール サービスを使用している Skype for Business ユーザーが、ハイブリッド Exchange Server 構成を持つ組織で、ボイスメールの案内応答を正常に変更できる必要があります。

2. モバイル クライアントの会話履歴が Outlook の [会話履歴] フォルダーに表示されるのを確認します。

3. アーカイブされたチャット メッセージが [、EWSEditor](https://blogs.msdn.microsoft.com/webdav_101/2018/03/12/where-to-get-ewseditor/)を使用して Purges フォルダー内のユーザーのオンプレミス メールボックスに保存されるのを確認します。

または、トラフィックを確認します。 OAuth ハンドシェイクのトラフィックは、渡されるトークンで、特に領域を中心に、非常に独特な (基本認証とは見なされない) ので、次のような発行者トラフィックが表示されます。00000004-0000-0ff1-ce00-000000000000@ (@ 記号の前に / がある場合があります)。 OAuth のポイントであるユーザー名やパスワードは表示できません。 ただし、'Office' 発行者 (この場合は '4' は Skype for Business) とサブスクリプションの領域が表示されます。

OAuth が正常に使用されたことを確認する場合は、期待される機能を知り、トラフィックの外観を知っている必要があります。 Microsoft[](https://tools.ietf.org/html/draft-ietf-oauth-v2-23#page-34)アプリケーションの[OAuth](https://download.microsoft.com/download/8/5/8/858F2155-D48D-4C68-9205-29460FD7698F/[MS-SPS2SAUTH].pdf)トラフィックの標準的な例を次に示します (更新トークンを使用しませんが、実際に読み取りが役立ちます)、OAuth JWT (JSON Web トークン) を確認できる Fiddler 拡張機能があります。

セットアップの例 [を次](https://blogs.msdn.microsoft.com/kaevans/2015/03/30/updated-fiddler-oauth-inspector/)に示しますが、このプロセスを実行する任意のネットワーク トレース ツールを使用できます。

## <a name="related-topics"></a>関連項目

[Exchange と Exchange Online 組織の間の OAuth 認証を構成する](https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)
