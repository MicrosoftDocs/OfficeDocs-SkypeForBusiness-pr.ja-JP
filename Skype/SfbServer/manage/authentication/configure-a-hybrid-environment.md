---
title: ビジネス サーバーのハイブリッド環境では Skype のサーバーからサーバーへの認証を構成します。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 700639ec-5264-4449-a8a6-d7386fad8719
description: '概要: ビジネス サーバーのハイブリッド環境では Skype のサーバーからサーバーへの認証を構成します。'
ms.openlocfilehash: 30214e1104617511e15272117cd478c6f4279668
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33913385"
---
# <a name="configure-server-to-server-authentication-for-a-skype-for-business-server-hybrid-environment"></a>ビジネス サーバーのハイブリッド環境では Skype のサーバーからサーバーへの認証を構成します。

**の概要:** ビジネス サーバー ハイブリッド環境の Skype のサーバーからサーバーへの認証を構成します。

ハイブリッド構成では、一部のユーザーが置かれている Skype の設置型インストールのビジネス サーバーのビジネス サーバーの他のユーザーが Skype の Office 365 バージョンに置かれているときにします。 ハイブリッド環境でサーバーからサーバーへの認証を構成するためには、最初にビジネス サーバーは、Office 365 認証サーバーを信頼するのには Skype のオンプレミス インストールを構成する必要があります。 このプロセスの初期手順を実行するには、次の Skype ビジネス サーバー管理シェル スクリプトを実行しています。

```
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

```
$TenantID = (Get-CsTenant -DisplayName "Fabrikam.com").TenantId
```

このスクリプトを実行する必要がありますインストールした Skype ビジネス オンラインの Powershell モジュールのこのモジュールを使用して、テナントに接続します。 これらのコマンドレットがインストールされていない場合、Get-CsTenant コマンドレットを使用できないためにスクリプトは失敗します。 スクリプトが完了すると、Skype のビジネス サーバーと認証サーバー間の信頼関係と Exchange 2013/2016 と認証サーバーとの間の 2 つ目の信頼関係をし、構成しなければなりません。 これは、Microsoft Online Services コマンドレットを使用してのみ行うことができます。

> [!NOTE]
> Powershell コマンドレット リポジトリからインストールする必要がある場合は、Microsoft Online Services のコマンドレットをインストールしていない場合は、インストール モジュールの MSOnline です。 Web サイトで Office 365 をインストールして、Microsoft Online Services のモジュールを使用しての詳細情報をご覧ください。 次の手順もわかりますシングル サイン オン、フェデレーション、および Office 365 と Active Directory 間の同期を構成する方法です。 



、Office 365 を構成した後、およびビジネス サーバーと Exchange 2013 に、Office 365 Skype のサービス ・ プリンシパルを作成した後は、これらのサービス ・ プリンシパルの資格情報を登録する必要がありますが、。 これを行うには、最初に .CER ファイルとして保存されている X.509 Base64 を入手する必要があります。 この証明書は、Office 365 のサービス ・ プリンシパルに適用されます。

X.509 証明書を入手したら、Powershell コンソールを開くし、サービス ・ プリンシパルを管理するために使用できるコマンドレットが含まれている Microsoft オンラインの Windows PowerShell モジュールをインポートします。

```
Import-Module MSOnline
```

モジュールがインポートされるは、次のコマンドを入力し、Office 365 に接続するために ENTER キーを押します。

```
Connect-MsolService
```

Enter キーを押すと、資格情報ダイアログ ボックスが表示されます。 ] ダイアログ ボックスで、Office 365 のユーザー名とパスワードを入力し、し、[OK] をクリックします。

Office 365 に接続するいるとすぐにし、サービス ・ プリンシパルに関する情報を取得するために次のコマンドを実行できます。

```
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

次の手順は、X.509 証明書のインポート、エンコード、および割り当てです。 インポートと証明書のエンコード、ファイルの完全なパスを指定することを確認する、次の Windows PowerShell コマンドを使用して、します。CER ファイル インポート メソッドを呼び出すとします。

```
$certificate = New-Object System.Security.Cryptography.X509Certificates.X509Certificate
$certificate.Import("C:\Certificates\Office365.cer")
$binaryValue = $certificate.GetRawCertData()
$credentialsValue = [System.Convert]::ToBase64String($binaryValue)
```

証明書をインポートし、エンコードされたが後、は、Office 365 のサービス ・ プリンシパルをし証明書を割り当てることができます。 Business Server の Skype とは Microsoft Exchange のサービス ・ プリンシパルの両方の AppPrincipalId プロパティの値を取得するために最初に取得-MsolServicePrincipal を使用します。AppPrincipalId プロパティの値は、証明書を割り当てられているサービス ・ プリンシパルを識別するのには適用されます。 AppPrincipalId プロパティ値の Skype のビジネス サーバーの手動で、ビジネス オンラインの Skype のバージョンの証明書を割り当てるには次のコマンドを使用します。

```
New-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -Type Asymmetric -Usage Verify -Value $credentialsValue 
```

必要がありますし、コマンドを繰り返し実行、Exchange 2013 の AppPrincipalId プロパティの値を使用してこの時間です。

切れている場合、たとえば、その証明書を削除する必要が生じた場合これを行う証明書のキー Id を取得します。

```
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

```
Remove-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -KeyId bc2795f3-2387-4543-a95d-f92c85c7a1b0
```

証明書を割り当てるだけでなくも Exchange のオンライン サービス主体を構成して、Office 365 のサービス プリンシパルとしてビジネス サーバー外部 Web サービス Url の Skype の設置型バージョンを構成する必要があります。 これを行うには、次の 2 つのコマンドを実行します。 

次の例では、Pool1ExternalWebFQDN.contoso.com は、Skype のビジネス サーバー プールの外部 Web サービスの URL です。 展開内のすべての外部 Web サービスの Url を追加するのには次の手順を繰り返す必要があります。

```
Set-MSOLServicePrincipal -AppPrincipalID 00000002-0000-0ff1-ce00-000000000000 -AccountEnabled $true
$lyncSP = Get-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000
$lyncSP.ServicePrincipalNames.Add("00000004-0000-0ff1-ce00-000000000000/Pool1ExternalWebFQDN.contoso.com")
Set-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $lyncSP.ServicePrincipalNames
```
