---
title: Skype for Business Server ハイブリッド環境用のサーバー間認証を構成する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 700639ec-5264-4449-a8a6-d7386fad8719
description: '概要: Skype for Business Server ハイブリッド環境用のサーバー間認証を構成します。'
ms.openlocfilehash: 6cc408677af4629d36b577da4ae38cd420195483
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221681"
---
# <a name="configure-server-to-server-authentication-for-a-skype-for-business-server-hybrid-environment"></a>Skype for Business Server ハイブリッド環境用のサーバー間認証を構成します。

**概要:** Skype for Business Server ハイブリッド環境用のサーバー間認証を構成します。

ハイブリッド構成では、一部のユーザーは Skype for business server のオンプレミスインストールに所属し、他のユーザーは Skype for Business Server の Microsoft 365 または Office 365 バージョンに所属しています。 ハイブリッド環境でサーバー間認証を構成するには、最初に、認証サーバーを信頼するように Skype for Business Server のオンプレミスインストールを構成する必要があります。 このプロセスの最初の手順は、次の Skype for Business Server 管理シェルスクリプトを実行することによって実行できます。

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

このスクリプトを実行するには、このモジュールを使用して Skype for Business Online PowerShell モジュールをインストールし、テナントに接続する必要があります。 これらのコマンドレットをインストールしていない場合、Get-cstenant コマンドレットは使用できないため、スクリプトは失敗します。 スクリプトが完了したら、Skype for Business Server と承認サーバー間の信頼関係と、Exchange 2013/2016 と承認サーバー間の2つ目の信頼関係を構成する必要があります。 これは、Microsoft Online Services コマンドレットを使用してのみ行うことができます。

> [!NOTE]
> Microsoft Online Services コマンドレットをインストールしていない場合は、コマンドレットを使用して PowerShell リポジトリからインストールする必要があり `install-module MSOnline` ます。 Microsoft Online Services モジュールのインストールおよび使用方法の詳細については、Microsoft 365 web サイトを参照してください。 これらの手順では、Microsoft 365 または Office 365 と Active Directory との間でシングルサインオン、フェデレーション、および同期を構成する方法についても説明します。 



Microsoft 365 または Office 365 を構成した後、Skype for Business Server と Exchange の2013に Microsoft 365 または Office 365 サービスプリンシパルを作成した後は、これらのサービスプリンシパルで資格情報を登録する必要があります。 そのためには、まず、として保存された x.509 Base64 証明書を取得する必要があります。CER ファイル。 この証明書は、Microsoft 365 または Office 365 のサービスプリンシパルに適用されます。

X.509 証明書を取得したら、PowerShell コンソールを開いて、サービスプリンシパルの管理に使用できるコマンドレットを含む Microsoft Online Windows PowerShell モジュールをインポートします。

```PowerShell
Import-Module MSOnline
```

モジュールがインポートされたら、次のコマンドを入力して enter キーを押します。

```PowerShell
Connect-MsolService
```

Enter キーを押すと、資格情報ダイアログ ボックスが表示されます。 ダイアログボックスに Microsoft 365 または Office 365 のユーザー名とパスワードを入力し、[OK] をクリックします。

Microsoft 365 または Office 365 に接続した直後に、次のコマンドを実行してサービスプリンシパルに関する情報を戻すことができます。

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

次の手順は、X.509 証明書のインポート、エンコード、および割り当てです。 証明書をインポートおよびエンコードするには、次の Windows PowerShell コマンドを使用します。これには、の完全なファイルパスを指定してください。CER ファイルを使用して、Import メソッドを呼び出します。

```PowerShell
$certificate = New-Object System.Security.Cryptography.X509Certificates.X509Certificate
$certificate.Import("C:\Certificates\Office365.cer")
$binaryValue = $certificate.GetRawCertData()
$credentialsValue = [System.Convert]::ToBase64String($binaryValue) 
```

証明書をインポートしてエンコードした後、証明書を Microsoft 365 または Office 365 のサービスプリンシパルに割り当てることができます。 そのためには、最初に New-msolserviceprincipal を使用して、Skype for Business サーバーと Microsoft Exchange サービスプリンシパルの AppPrincipalId プロパティの値を取得します。AppPrincipalId プロパティの値は、証明書を割り当てられているサービスプリンシパルを識別するために使用されます。 Skype for Business Server の AppPrincipalId プロパティの値を使用して、次のコマンドを使用して、証明書を Skype For Business Online のバージョンに割り当てます。

```PowerShell
New-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -Type Asymmetric -Usage Verify -Value $credentialsValue 
```

その後、このコマンドを繰り返し実行します。このとき、Exchange 2013 の AppPrincipalId プロパティの値を使用します。

後でその証明書を削除する必要がある場合 (たとえば、期限が切れている場合)、最初に証明書のキー Id を取得します。

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

証明書を割り当てるだけでなく、Exchange Online サービスプリンシパルを構成して、社内バージョンの Skype for Business Server の外部 Web サービス Url を Microsoft 365 または Office 365 サービスプリンシパルとして構成する必要もあります。 そのためには、次の2つのコマンドを実行します。 

次の例では、Pool1ExternalWebFQDN.contoso.com は、Skype for Business Server プールの外部 Web サービスの URL です。 これらの手順を繰り返して、展開内のすべての外部 Web サービス Url を追加する必要があります。

```PowerShell
Set-MSOLServicePrincipal -AppPrincipalID 00000002-0000-0ff1-ce00-000000000000 -AccountEnabled $true
$lyncSP = Get-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000
$lyncSP.ServicePrincipalNames.Add("00000004-0000-0ff1-ce00-000000000000/Pool1ExternalWebFQDN.contoso.com")
Set-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $lyncSP.ServicePrincipalNames
```
