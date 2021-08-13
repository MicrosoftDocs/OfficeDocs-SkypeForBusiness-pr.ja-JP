---
title: ハイブリッド環境のサーバー間認証Skype for Business Server構成する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 700639ec-5264-4449-a8a6-d7386fad8719
description: '概要: ハイブリッド環境のサーバー間認証Skype for Business Server構成します。'
ms.openlocfilehash: 0a5060f9f40b7887de0b9afefa0b8f43f65f76120d430db01eaf32095af66f84
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54315723"
---
# <a name="configure-server-to-server-authentication-for-a-skype-for-business-server-hybrid-environment"></a>ハイブリッド環境のサーバー間認証Skype for Business Server構成します。

**概要:** ハイブリッド環境用にサーバー間認証Skype for Business Server構成します。

ハイブリッド構成では、一部のユーザーは Skype for Business Server のオンプレミス インストールに組み込まれますが、他のユーザーは Microsoft 365 または Office 365 バージョンの Skype for Business Server にSkype for Business Server。 ハイブリッド環境でサーバー間認証を構成するには、まず、認証サーバーを信頼するために、サーバーのオンプレミス インストールSkype for Business Server構成する必要があります。 このプロセスの最初の手順は、次の管理シェル スクリプトを実行Skype for Business Server実行できます。

```PowerShell
$TenantID = (Get-CsTenant -Filter {DisplayName -eq "Fabrikam.com"}).TenantId

$sts = Get-CsOAuthServer microsoft.sts -ErrorAction SilentlyContinue

   if ($sts -eq $null)
      {
         New-CsOAuthServer microsoft.sts -MetadataUrl "https://accounts.accesscontrol.windows.net/$TenantId/metadata/json/1"
      }
   else
      {
         if ($sts.MetadataUrl -ne  "https://accounts.accesscontrol.windows.net/$TenantId/metadata/json/1")
            {
               Remove-CsOAuthServer microsoft.sts
               New-CsOAuthServer microsoft.sts -MetadataUrl "https://accounts.accesscontrol.windows.net/$TenantId/metadata/json/1"
            }
        }

$exch = Get-CsPartnerApplication microsoft.exchange -ErrorAction SilentlyContinue

if ($exch -eq $null)
   {
      New-CsPartnerApplication -Identity microsoft.exchange -ApplicationIdentifier 00000002-0000-0ff1-ce00-000000000000 -ApplicationTrustLevel Full -UseOAuthServer
    }
else
    {
       if ($exch.ApplicationIdentifier -ne "00000002-0000-0ff1-ce00-000000000000")
          {
             Remove-CsPartnerApplication microsoft.exchange
             New-CsPartnerApplication -Identity microsoft.exchange -ApplicationIdentifier 00000002-0000-0ff1-ce00-000000000000 -ApplicationTrustLevel Full -UseOAuthServer 
          }
       else
          {
             Set-CsPartnerApplication -Identity microsoft.exchange -ApplicationTrustLevel Full -UseOAuthServer
          }
   }

Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000
```

通常、テナントの領域名は組織名と異なることに注意してください。実際には、領域名はほぼ常にテナント ID と同じです。このため、スクリプトの最初の行を使用して、指定したテナント (この場合は fabrikam.com) の TenantId プロパティの値を取得してから、名前を変数 $TenantId に割り当てます。

```PowerShell
$TenantID = (Get-CsTenant -Filter {DisplayName -eq "Fabrikam.com"}).TenantId
```

このスクリプトを実行するには、オンライン PowerShell モジュールSkype for Businessインストールし、このモジュールを使用してテナントに接続する必要があります。 これらのコマンドレットをインストールしていない場合、このコマンドレットを使用できないGet-CsTenantスクリプトは失敗します。 スクリプトが完了したら、Skype for Business Server と承認サーバーの間に信頼関係を構成し、Exchange 2013/2016 と認証サーバーとの間に 2 番目の信頼関係を構成する必要があります。 これは、Microsoft Online Services コマンドレットを使用してのみ行うことができます。

> [!NOTE]
> このコマンドレットをインストールしていないMicrosoft Online Services、コマンドレットを使用して PowerShell リポジトリからインストールする必要があります `install-module MSOnline` 。 モジュールのインストールと使用の詳細については、Microsoft Online Services Web サイトMicrosoft 365参照してください。 また、これらの手順では、シングル サインオン、フェデレーション、および同期を構成する方法について説明しますMicrosoft 365または Office 365 Active Directory。 



Microsoft 365 または Office 365 を構成し、Skype for Business Server および Exchange 2013 の Microsoft 365 または Office 365 サービス プリンシパルを作成した後、これらのサービス プリンシパルに資格情報を登録する必要があります。 これを行うには、まず、 として保存された X.509 Base64 証明書を取得する必要があります。CER ファイル。 この証明書は、サービス プリンシパルまたはサービス Microsoft 365 Office 365されます。

X.509 証明書を取得した後、PowerShell コンソールを開き、サービス プリンシパルの管理に使用できるコマンドレットを含む Microsoft Online Windows PowerShell モジュールをインポートします。

```PowerShell
Import-Module MSOnline
```

モジュールがインポートされると、次のコマンドを入力し、Enter キーを押します。

```PowerShell
Connect-MsolService
```

Enter キーを押すと、資格情報ダイアログ ボックスが表示されます。 ダイアログ ボックスにMicrosoft 365またはOffice 365パスワードを入力し、[OK] をクリックします。

Microsoft 365 または Office 365 に接続すると、サービス プリンシパルに関する情報を返す次のコマンドを実行できます。

```PowerShell
Get-MsolServicePrincipal
```

すべてのサービス プリンシパルについて次のような情報が返されます。

<pre>
ExtensionData        : System.Runtime.Serialization.ExtensionDataObject
AccountEnabled       : True
Addresses            : {}
AppPrincipalId       : 00000004-0000-0ff1-ce00-000000000000
DisplayName          : Skype for Business Server
ObjectId             : aada5fbd-c0ae-442a-8c0b-36fec40602e2
ServicePrincipalName : SkypeForBusinessServer/litwareinc.com
TrustedForDelegation : True
</pre>

次の手順は、X.509 証明書のインポート、エンコード、および割り当てです。 証明書をインポートおよびエンコードするには、次の Windows PowerShell コマンドを使用して、必ずファイルパスを指定します。Import メソッドを呼び出す場合の CER ファイル:

```PowerShell
$certificate = New-Object System.Security.Cryptography.X509Certificates.X509Certificate
$certificate.Import("C:\Certificates\Office365.cer")
$binaryValue = $certificate.GetRawCertData()
$credentialsValue = [System.Convert]::ToBase64String($binaryValue) 
```

証明書をインポートしてエンコードしたら、証明書をサービス プリンシパルまたはサービス Microsoft 365 Office 365できます。 これを行うには、最初に Get-MsolServicePrincipal を使用して、Skype for Business Server と Microsoft Exchange サービス プリンシパルの両方の AppPrincipalId プロパティの値を取得します。AppPrincipalId プロパティの値は、証明書に割り当てられているサービス プリンシパルを識別するために使用されます。 アプリケーションの AppPrincipalId プロパティ値を手Skype for Business Server、次のコマンドを使用して、証明書を For Business Online Skypeに割り当てる。

```PowerShell
New-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -Type Asymmetric -Usage Verify -Value $credentialsValue 
```

次に、2013 年に AppPrincipalId プロパティ値を使用してコマンドExchangeします。

その証明書の有効期限が切れている場合など、後で削除する必要がある場合は、最初に証明書の KeyId を取得します。

```PowerShell
Get-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000
```

そのコマンドは、次のようなデータを返します。

<pre>
Type      : Asymmetric
Value     : 
KeyId     : bc2795f3-2387-4543-a95d-f92c85c7a1b0
StartDate : 6/1/2012 8:00:00 AM
EndDate   : 5/31/2013 8:00:00 AM
Usage     : Verify
</pre>

続いて、次のようなコマンドを使用して証明書を削除できます。

```PowerShell
Remove-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -KeyId bc2795f3-2387-4543-a95d-f92c85c7a1b0
```

証明書の割り当てに加えて、Exchange Online サービス プリンシパルを構成し、Skype for Business Server 外部 Web サービス URL のオンプレミス バージョンを Microsoft 365 または Office 365 サービス プリンシパルとして構成する必要があります。 これは、次の 2 つのコマンドを実行することで実行できます。 

次の例では、Pool1ExternalWebFQDN.contoso.com プールの外部 Web サービス URL をSkype for Business Serverします。 展開内のすべての外部 Web サービス URL を追加するには、これらの手順を繰り返す必要があります。

```PowerShell
Set-MSOLServicePrincipal -AppPrincipalID 00000002-0000-0ff1-ce00-000000000000 -AccountEnabled $true
$lyncSP = Get-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000
$lyncSP.ServicePrincipalNames.Add("00000004-0000-0ff1-ce00-000000000000/Pool1ExternalWebFQDN.contoso.com")
Set-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $lyncSP.ServicePrincipalNames
```
