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
description: オンプレミスの Exchange と Skype for Business Online の間で OAuth 認証を構成すると、「機能のサポート」で説明されている Skype for Business 機能と Exchange 統合機能が有効です。
ms.openlocfilehash: 342362926ad0af169acd6c9af4715008425e71c7
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51109713"
---
# <a name="configure-integration-and-oauth-between-skype-for-business-online-and-exchange-server"></a>Skype for Business Online と Skype の間の統合と OAuth を構成Exchange Server 

Exchange サーバーと Skype for Business Online の統合を構成すると、「機能のサポート」で説明されている Skype for Business 機能と Exchange 統合機能 [が有効になります](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support)。

このトピックは、2013 Exchange Server 2019 との統合に適用されます。

## <a name="what-do-you-need-to-know-before-you-begin"></a>始める前に把握しておくべき情報

- このタスクの予想所要時間:15 分

-  この手順を実行する際は、あらかじめアクセス許可を割り当てる必要があります。 必要なアクセス許可を確認するには、「Exchange インフラストラクチャとシェル インフラストラクチャのアクセス許可 [」トピックを参照](/exchange/exchange-and-shell-infrastructure-permissions-exchange-2013-help) してください。

- このトピックの手順で使用可能なキーボード ショートカットについては、「[Exchange 管理センターのキーボード ショートカット]( https://go.microsoft.com/fwlink/p/?LinkId=746512)」を参照してください。

- 互換性の詳細については [、「Skype for Business とアプリとの互換性」をOfficeしてください](../../plan-your-deployment/clients-and-devices/compatibility-with-office.md)。

## <a name="configure-integration-between-exchange-server-and-o365"></a>O365 と Exchange Serverの統合を構成する

### <a name="step-1-configure-oauth-authentication-between-exchange-server-and-o365"></a>手順 1: OAuth 認証を O365 Exchange Server構成する

次の記事の手順を実行します。

[Exchange と Exchange Online 組織の間の OAuth 認証を構成する](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)

### <a name="step-2-create-a-new-mail-user-account-for-the-skype-for-business-online-partner-application"></a>手順 2: Skype for Business Online パートナー アプリケーション用の新しいメール ユーザー アカウントを作成する

この手順は、Exchange サーバーで行います。 メール ユーザーを作成し、適切な管理役割権限を割り当てる。 このアカウントは、次の手順で使用されます。

Exchange 組織の検証済みドメインを指定します。 このドメインは、オンプレミスの Exchange アカウントで使用されるプライマリ SMTP ドメインと同じドメインである必要があります。 このドメインは、次の \<your Verified Domain\> 手順で参照されます。 また、ドメイン \<DomainControllerFQDN\> コントローラーの FQDN である必要があります。

```powershell
$user = New-MailUser -Name SfBOnline-ApplicationAccount -ExternalEmailAddress SfBOnline-ApplicationAccount@<your Verified Domain> -DomainController <DomainControllerFQDN>
```

このコマンドは、新しいメール ユーザーをアドレス一覧から非表示にします。

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

### <a name="step-4-export-the-on-premises-authorization-certificate"></a>手順 4: オンプレミス認証証明書をエクスポートする

PowerShell スクリプトを実行して、次の手順で Skype for Business Online 組織にインポートするオンプレミス認証証明書をエクスポートします。

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

オンプレミスの Exchange 組織の Exchange PowerShell で、作成した PowerShell スクリプトを実行します。 たとえば、次の.\ExportAuthCert.ps1

### <a name="step-5-upload-the-on-premises-authorization-certificate-to-azure-active-directory-acs"></a>手順 5: オンプレミスの承認証明書を Azure Active Directory ACS にアップロードする

次に、Windows PowerShellを使用して、前の手順でエクスポートしたオンプレミス認証証明書を Azure Active Directory Access Control Services (ACS) にアップロードします。 これを行うには、Azure Active Directory Module for Windows PowerShellがインストールされている必要があります。 インストールされていない場合、[https://aka.ms/aadposh](/previous-versions/azure/jj151815(v=azure.100)) に移動して、Windows PowerShell の Azure Active Directory モジュール をインストールしてください。 Windows PowerShell の Azure Active Directory モジュール のインストール後、以下の手順を実行します。

1. **[Windows PowerShell 用 Azure Active Directory モジュール]** ショートカットをクリックして、Azure AD コマンドレットがインストールされた Windows PowerShell ワークスペースを開きます。この手順のすべてのコマンドは、Azure Active Directory コンソール用の Windows PowerShell を使用して実行されます。

2. 次のテキストを、たとえばという名前の PowerShell スクリプト ファイルに保存します  `UploadAuthCert.ps1` 。

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

### <a name="step-6-verify-that-the-certificate-has-uploaded-to-the-skype-for-business-service-principal"></a>手順 6: 証明書が Skype for Business Service プリンシパルにアップロードされたのを確認する
1. Azure Active Directory で開いて認証された PowerShell で、次のコマンドを実行します。
```powershell
Get-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000
```
2. ReturnKeyValues の入力を求めるメッセージが表示されたら、Enter キーを押します。
3. Exchange Oauth 証明書の開始日と終了日に一致する開始日と終了データが一覧表示されているキーが表示されるのを確認する

### <a name="verify-your-success"></a>成功を確認する

一部の機能が正常に動作していることを確認して、構成が正しいか確認します。 

1. ハイブリッド ボイスメール構成を持つ組織のクラウド ボイスメール サービスを使用する Skype for Business ユーザー Exchange Serverボイスメール案内応答を正常に変更できます。

2. モバイル クライアントの会話履歴が Outlook の会話履歴フォルダーに表示されるのを確認します。

3. アーカイブされたチャット メッセージが [、EWSEditor](/archive/blogs/webdav_101/where-to-get-ewseditor)を使用して Purges フォルダー内のユーザーのオンプレミス メールボックスに保存されるのを確認します。

または、トラフィックを確認します。 OAuth ハンドシェイクのトラフィックは、実際には特徴的です (基本認証とは見なしません)、特に領域の周りでは、次のような発行者トラフィックが表示されます。000000004-00000-0ff1-ce000-000000000@ (@記号の前に / がある場合があります)、渡されるトークンで。 OAuth のポイントであるユーザー名やパスワードは表示できません。 ただし、'Office' 発行者が表示されます 。この場合、'4' は Skype for Business であり、サブスクリプションの領域です。

OAuth が正常に使用されたことを確認する場合は、何を期待し、トラフィックの外観を知る必要があるかを確認してください。 [ここでは、Microsoft](https://download.microsoft.com/download/8/5/8/858F2155-D48D-4C68-9205-29460FD7698F/[MS-SPS2SAUTH].pdf)アプリケーションの OAuth トラフィックの標準的な例を示します (更新トークンは使用しませんが、実際に読むのに役立ちます)、OAuth JWT (JSON Web トークン) を確認できる Fiddler 拡張機能があります。 [](https://tools.ietf.org/html/draft-ietf-oauth-v2-23#page-34)

セットアップの例 [を次](/archive/blogs/kaevans/updated-fiddler-oauth-inspector)に示しますが、このプロセスを実行するには、任意のネットワーク トレース ツールを使用できます。

## <a name="related-topics"></a>関連トピック

[Exchange と Exchange Online 組織の間の OAuth 認証を構成する](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)