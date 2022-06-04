---
title: Skype for Business Online と Exchange サーバーの統合
ms.reviewer: cbland
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 02/17/2022
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: ffe4c3ba-7bab-49f1-b229-5142a87f94e6
description: Exchange on Premises と Skype for Business Online の間で OAuth 認証を構成すると、機能サポートで説明されている Skype for Business および Exchange 統合機能が有効になります。
ms.openlocfilehash: 0b312dfde144f12a9c2db523ce4526153b445d59
ms.sourcegitcommit: e3931446943684db155bb3edf7d7e52d41775013
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2022
ms.locfileid: "65886644"
---
# <a name="configure-integration-and-oauth-between-skype-for-business-online-and-exchange-server"></a>Skype for Business Online と Exchange Server の間で統合と OAuth を構成する 

Exchange サーバーと Skype for Business Online の統合を構成すると、 [機能サポート](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support)で説明されている Skype for Business と Exchange 統合機能が有効になります。

このトピックは、Exchange Server 2013 ~ 2019 との統合に適用されます。

## <a name="what-do-you-need-to-know-before-you-begin"></a>始める前に把握しておくべき情報

- このタスクの予想所要時間:15 分

-  この手順を実行する際には、あらかじめアクセス許可が割り当てられている必要があります。 必要なアクセス許可を確認するには、 [Exchange および Shell インフラストラクチャのアクセス許可](/exchange/exchange-and-shell-infrastructure-permissions-exchange-2013-help) に関するトピックを参照してください。

- このトピックの手順で使用可能なキーボード ショートカットについては、「[Exchange 管理センターのキーボード ショートカット]( https://go.microsoft.com/fwlink/p/?LinkId=746512)」を参照してください。

- 互換性については、「 [Skype for Business と Office アプリの互換性](../../plan-your-deployment/clients-and-devices/compatibility-with-office.md)」を参照してください。

## <a name="configure-integration-between-exchange-server-and-o365"></a>Exchange Server と O365 の統合を構成する

### <a name="step-1-configure-oauth-authentication-between-exchange-server-and-o365"></a>手順 1: Exchange Server と O365 の間で OAuth 認証を構成する

次の記事の手順を実行します。

[Exchange と Exchange Online 組織の間の OAuth 認証を構成する](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)

### <a name="step-2-create-a-new-mail-user-account-for-the-skype-for-business-online-partner-application"></a>手順 2: Skype for Business Online パートナー アプリケーションの新しいメール ユーザー アカウントを作成する

この手順は、Exchange サーバーで行います。 メール ユーザーを作成し、適切な管理ロール権限を割り当てます。 このアカウントは、次の手順で使用されます。

Exchange 組織の検証済みドメインを指定します。 このドメインは、オンプレミスの Exchange アカウントに使用されるプライマリ SMTP ドメインと同じドメインである必要があります。 このドメインは、次の手順で呼び出されます \<your Verified Domain\> 。 また、 \<DomainControllerFQDN\> ドメイン コントローラーの FQDN を指定する必要があります。

```powershell
$user = New-MailUser -Name SfBOnline-ApplicationAccount -ExternalEmailAddress SfBOnline-ApplicationAccount@<your Verified Domain> -DomainController <DomainControllerFQDN>
```

このコマンドは、新しいメール ユーザーをアドレス一覧から非表示にします。

```powershell
Set-MailUser -Identity $user.Identity -HiddenFromAddressListsEnabled $True -DomainController <DomainControllerFQDN>
```

次の 2 つのコマンドは、この新しいアカウントに UserApplication と ArchiveApplication 管理ロールを割り当てます。

```powershell
New-ManagementRoleAssignment -Role UserApplication -User $user.Identity -DomainController <DomainControllerFQDN>
```

```powershell
New-ManagementRoleAssignment -Role ArchiveApplication -User $user.Identity -DomainController <DomainControllerFQDN>
```

### <a name="step-3-create-and-enable-a-partner-application-for-skype-for-business-online"></a>手順 3: Skype for Business Online のパートナー アプリケーションを作成して有効にする 

新しいパートナー アプリケーションを作成し、先ほど作成したアカウントを使用します。 社内 Exchange 組織の Exchange PowerShell で、次のコマンドを実行します。

```powershell
New-PartnerApplication -Name SfBOnline -ApplicationIdentifier 00000004-0000-0ff1-ce00-000000000000 -Enabled $True -LinkedAccount $user.Identity
```

### <a name="step-4-export-the-on-premises-authorization-certificate"></a>手順 4: オンプレミスの承認証明書をエクスポートする

PowerShell スクリプトを実行してオンプレミス承認証明書をエクスポートします。この証明書は、次の手順で Skype for Business Online 組織にインポートします。

次のテキストを、たとえば ExportAuthCert.ps1 という名前の PowerShell スクリプト ファイルに保存します。

```powershell
$thumbprint = (Get-AuthConfig).CurrentCertificateThumbprint
if((test-path $env:SYSTEMDRIVE\OAuthConfig) -eq $false) {
    md $env:SYSTEMDRIVE\OAuthConfig
}
cd $env:SYSTEMDRIVE\OAuthConfig
$oAuthCert = (dir Cert:\LocalMachine\My) | where {$_.Thumbprint -match $thumbprint}
$certType = [System.Security.Cryptography.X509Certificates.X509ContentType]::Cert
$certBytes = $oAuthCert.Export($certType)
$CertFile = "$env:SYSTEMDRIVE\OAuthConfig\OAuthCert.cer"
[System.IO.File]::WriteAllBytes($CertFile, $certBytes)
```

オンプレミスの Exchange 組織の Exchange PowerShell で、先ほど作成した PowerShell スクリプトを実行します。 たとえば、.\ExportAuthCert.ps1

### <a name="step-5-upload-the-on-premises-authorization-certificate-to-azure-active-directory-acs"></a>手順 5: オンプレミスの承認証明書を Azure Active Directory ACS にアップロードする

次に、Windows PowerShell を使用して、前の手順でエクスポートしたオンプレミス承認証明書を Azure Active Directory Access Control Services (ACS) にアップロードします。 これを行うには、Azure Active Directory Module for Windows PowerShell コマンドレットが既にインストールされている必要があります。 インストールされていない場合、[https://aka.ms/aadposh](/previous-versions/azure/jj151815(v=azure.100)) に移動して、Windows PowerShell の Azure Active Directory モジュール をインストールしてください。 Windows PowerShell の Azure Active Directory モジュール のインストール後、以下の手順を実行します。

1. **[Windows PowerShell 用 Azure Active Directory モジュール]** ショートカットをクリックして、Azure AD コマンドレットがインストールされた Windows PowerShell ワークスペースを開きます。この手順のすべてのコマンドは、Azure Active Directory コンソール用の Windows PowerShell を使用して実行されます。

2. 次のテキストを、次のような  `UploadAuthCert.ps1`名前の PowerShell スクリプト ファイルに保存します。

   ```powershell
   Connect-MsolService
   Import-Module MSOnline
   $CertFile = "$env:SYSTEMDRIVE\OAuthConfig\OAuthCert.cer"
   $objFSO = New-Object -ComObject Scripting.FileSystemObject
   $CertFile = $objFSO.GetAbsolutePathName($CertFile);
   $cer = New-Object System.Security.Cryptography.X509Certificates.X509Certificate
   $cer.Import($CertFile)
   $binCert = $cer.GetRawCertData();
   $credValue = [System.Convert]::ToBase64String($binCert)
   $ServiceName = "00000004-0000-0ff1-ce00-000000000000"
   $p = Get-MsolServicePrincipal -ServicePrincipalName $ServiceName
   New-MsolServicePrincipalCredential -AppPrincipalId $p.AppPrincipalId -Type asymmetric -Usage Verify -Value $credValue
   ```

3. 直前の手順で作成した PowerShell スクリプトを実行します。 例:  `.\UploadAuthCert.ps1`

4. スクリプトを起動した後に、[資格情報] ダイアログ ボックスが表示されます。 Microsoft Online Azure AD 組織のテナント管理者アカウントの資格情報を入力します。 スクリプトの実行後、Azure AD 用 Windows PowerShell セッションを開いたままにします。 これは、次のステップで PowerShell スクリプトを実行するために使用します。

### <a name="step-6-verify-that-the-certificate-has-uploaded-to-the-skype-for-business-service-principal"></a>手順 6: 証明書が Skype for Business サービス プリンシパルにアップロードされたことを確認する
1. Azure Active Directory に対して開いて認証された PowerShell で、次のコマンドを実行します。

   ```powershell
   Get-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000
   ```
2. ReturnKeyValues の入力を求められたら Enter キーを押します
3. Exchange Oauth 証明書の開始日と終了日に一致する開始日と終了日のデータが表示されているキーが表示されることを確認します

### <a name="verify-your-success"></a>成功を確認する

一部の機能が正常に動作していることを確認して、構成が正しいことを確認します。 

1. Cloud ボイスメール サービスを使用する Skype for Business ユーザーが、ハイブリッド Exchange Server 構成の組織でボイスメールのあいさつ文を正常に変更できることを確認します。

2. モバイル クライアントの会話履歴が Outlook 会話履歴フォルダーに表示されていることを確認します。

3. [EWSEditor](/archive/blogs/webdav_101/where-to-get-ewseditor) を使用して、アーカイブされたチャット メッセージが Purges フォルダー内のユーザーのオンプレミス メールボックスに保存されていることを確認します。

または、トラフィックを確認します。 OAuth ハンドシェイクのトラフィックは非常に独特です (特に基本認証のようには見えません)。特に領域を中心に、次のような発行者トラフィック (00000004-0000-0ff1-ce00-0000000-ce00-00000000-ce00-000000000000@ ( @ 記号の前に場合があります) が渡されるトークンで表示されます。 OAuth のポイントであるユーザー名またはパスワードは表示されません。 ただし、"Office" 発行者 (この場合は '4' は Skype for Business) であり、サブスクリプションの領域が表示されます。

OAuth を正常に使用していることを確認する場合は、何を期待するか、トラフィックの外観を把握していることを確認してください。 [そのため、](https://tools.ietf.org/html/draft-ietf-oauth-v2-23#page-34)Microsoft [アプリケーションでの OAuth トラフィックの](https://download.microsoft.com/download/8/5/8/858F2155-D48D-4C68-9205-29460FD7698F/[MS-SPS2SAUTH].pdf)標準的な例を次に示します (更新トークンは使用しませんが、読み取りには非常に役立ちます)、OAuth JWT (JSON Web トークン) を調べることができるように Fiddler 拡張機能があります。

セットアップ [の例](/archive/blogs/kaevans/updated-fiddler-oauth-inspector)を次に示しますが、このプロセスを実行する任意のネットワーク トレース ツールを使用できます。

## <a name="related-topics"></a>関連トピック

[Exchange と Exchange Online 組織の間の OAuth 認証を構成する](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)
