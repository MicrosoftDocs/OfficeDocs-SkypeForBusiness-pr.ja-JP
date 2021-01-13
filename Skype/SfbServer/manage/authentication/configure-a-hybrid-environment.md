---
title: Skype for Business Server ハイブリッド環境のサーバー間認証を構成する
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
description: '概要: Skype for Business Server ハイブリッド環境のサーバー間認証を構成します。'
ms.openlocfilehash: 6f4e11b54f0292b1ccb91ab486e2e638a4dcceb6
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828487"
---
# <a name="configure-server-to-server-authentication-for-a-skype-for-business-server-hybrid-environment"></a>Skype for Business Server ハイブリッド環境のサーバー間認証を構成します。

**概要:** Skype for Business Server ハイブリッド環境のサーバー間認証を構成します。

ハイブリッド構成では、一部のユーザーは Skype for Business Server のオンプレミス インストールに、他のユーザーは Microsoft 365 または Office 365 バージョンの Skype for Business Server にホームとして使用されます。 ハイブリッド環境でサーバー間認証を構成するには、まず、認証サーバーを信頼する Skype for Business Server のオンプレミス インストールを構成する必要があります。 このプロセスの最初の手順は、次の Skype for Business Server 管理シェル スクリプトを実行することで実行できます。

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

このスクリプトを実行するには、Skype for Business Online PowerShell モジュールをインストールし、このモジュールを使用してテナントに接続する必要があります。 これらのコマンドレットをインストールしていない場合、このコマンドレットを使用Get-CsTenantスクリプトは失敗します。 スクリプトが完了したら、Skype for Business Server と認証サーバーの間の信頼関係と、Exchange 2013/2016 と認証サーバーの間の 2 番目の信頼関係を構成する必要があります。 これは、Microsoft Online Services コマンドレットを使用してのみ行うことができます。

> [!NOTE]
> Microsoft Online Services コマンドレットをインストールしていない場合は、PowerShell リポジトリからコマンドレットを使用してインストールする必要があります `install-module MSOnline` 。 Microsoft Online Services モジュールのインストールと使用の詳細については、Microsoft 365 Web サイトを参照してください。 これらの手順では、Microsoft 365 または Office 365 と Active Directory の間でシングル サインオン、フェデレーション、同期を構成する方法も説明します。 



Microsoft 365 または Office 365 を構成し、Skype for Business Server と Exchange 2013 の Microsoft 365 または Office 365 サービス プリンシパルを作成した後、これらのサービス プリンシパルに資格情報を登録する必要があります。 これを行うには、まず X.509 Base64 証明書を取得して、次のように保存する必要があります。CER ファイル。 この証明書は、Microsoft 365 または 365 Officeに適用されます。

X.509 証明書を取得した後、PowerShell コンソールを開き、サービス プリンシパルの管理に使用できるコマンドレットを含む Microsoft Online Windows PowerShell モジュールをインポートします。

```PowerShell
Import-Module MSOnline
```

モジュールがインポートされた後、次のコマンドを入力し、Enter キーを押します。

```PowerShell
Connect-MsolService
```

Enter キーを押すと、資格情報ダイアログ ボックスが表示されます。 ダイアログ ボックスに Microsoft 365 または Office 365 のユーザー名とパスワードを入力し、[OK] をクリックします。

Microsoft 365 または Office 365 に接続するとすぐに、次のコマンドを実行してサービス プリンシパルに関する情報を戻します。

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

次の手順は、X.509 証明書のインポート、エンコード、および割り当てです。 証明書をインポートしてエンコードするには、次の Windows PowerShell コマンドを使用して、ファイルへの完全なパスを指定してください。Import メソッドを呼び出す場合の CER ファイル:

```PowerShell
$certificate = New-Object System.Security.Cryptography.X509Certificates.X509Certificate
$certificate.Import("C:\Certificates\Office365.cer")
$binaryValue = $certificate.GetRawCertData()
$credentialsValue = [System.Convert]::ToBase64String($binaryValue) 
```

証明書をインポートしてエンコードしたら、証明書を Microsoft 365 または Office 365 サービス プリンシパルに割り当てできます。 これを行うには、まず Get-MsolServicePrincipal を使用して、Skype for Business Server と Microsoft Exchange サービス プリンシパルの両方の AppPrincipalId プロパティの値を取得します。AppPrincipalId プロパティの値は、証明書が割り当てられているサービス プリンシパルを識別するために使用されます。 Skype for Business Server の AppPrincipalId プロパティ値を手にして、次のコマンドを使用して Skype For Business Online バージョンに証明書を割り当てる。

```PowerShell
New-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -Type Asymmetric -Usage Verify -Value $credentialsValue 
```

次に、このコマンドを繰り返す必要があります。今回は、Exchange 2013 の AppPrincipalId プロパティ値を使用します。

後で証明書を削除する必要がある場合 (有効期限が切れている場合など)、最初に証明書の KeyId を取得することで削除できます。

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

証明書の割り当てに加えて、Exchange Online サービス プリンシパルを構成し、オンプレミス バージョンの Skype for Business Server 外部 Web サービス URL を Microsoft 365 または Office 365 サービス プリンシパルとして構成する必要があります。 これは、次の 2 つのコマンドを実行することで実行できます。 

次の例では、Pool1ExternalWebFQDN.contoso.com Skype for Business Server プールの外部 Web サービス URL を指定します。 これらの手順を繰り返して、展開内のすべての外部 Web サービス URL を追加する必要があります。

```PowerShell
Set-MSOLServicePrincipal -AppPrincipalID 00000002-0000-0ff1-ce00-000000000000 -AccountEnabled $true
$lyncSP = Get-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000
$lyncSP.ServicePrincipalNames.Add("00000004-0000-0ff1-ce00-000000000000/Pool1ExternalWebFQDN.contoso.com")
Set-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $lyncSP.ServicePrincipalNames
```
