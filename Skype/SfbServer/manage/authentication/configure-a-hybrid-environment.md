---
title: ビジネス サーバーのハイブリッド環境では Skype のサーバーからサーバーへの認証を構成します。
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 1/31/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 700639ec-5264-4449-a8a6-d7386fad8719
description: '概要: ビジネス サーバーのハイブリッド環境では Skype のサーバーからサーバーへの認証を構成します。'
ms.openlocfilehash: 889e62cf2c462dc9f1cc9ab4b96ae73f99bc9c6e
ms.sourcegitcommit: 3d1556113ce4050b79ee34c138482b34273b8c1d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/03/2018
ms.locfileid: "20178816"
---
# <a name="configure-server-to-server-authentication-for-a-skype-for-business-server-hybrid-environment"></a>ビジネス サーバーのハイブリッド環境では Skype のサーバーからサーバーへの認証を構成します。
 
**の概要:** ビジネス サーバー ハイブリッド環境の Skype のサーバーからサーバーへの認証を構成します。
  
ハイブリッド構成では、一部のユーザーが置かれている Skype の設置型インストールのビジネス サーバー 2015 のビジネス サーバーの他のユーザーが Skype の Office 365 バージョンに置かれているときにします。 ハイブリッド環境でサーバーからサーバーへの認証を構成するためには、最初に Office 365 の認証サーバーを信頼するようにサーバー 2015 のビジネス用の Skype のオンプレミス インストールを構成する必要があります。 このプロセスの初期手順を実行するには、次の Skype ビジネス サーバー管理シェル スクリプトを実行しています。
  
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

スクリプトが完了するは、ビジネス サーバー 2015 の Skype と認証サーバーとの間に信頼関係と Exchange 2013 と認証サーバーとの間の 2 つ目の信頼関係を構成する必要がありますし。 これは、Microsoft Online Services コマンドレットを使用してのみ行うことができます。
  
> [!NOTE]
> Microsoft Online Services コマンドレットをインストールしていない場合は、先に進む前に 2 つの作業を行う必要があります。 最初に、64 ビット バージョンの Microsoft Online Services サインイン アシスタントをダウンロードしてインストールします。 インストールが完了したらをダウンロードして、Microsoft Online Services モジュールを Windows PowerShell の 64 ビット バージョンをインストールします。 Web サイトで Office 365 をインストールして、Microsoft Online Services のモジュールを使用しての詳細情報をご覧ください。 次の手順もわかりますシングル サイン オン、フェデレーション、および Office 365 と Active Directory 間の同期を構成する方法です。 
  
これらのコマンドレットがインストールされていない場合、Get-CsTenant コマンドレットを使用できないためにスクリプトは失敗します。
  
、Office 365 を構成した後、およびビジネス サーバー 2015」および「Exchange 2013 の、Office 365 Skype のサービス ・ プリンシパルを作成した後は、これらのサービス ・ プリンシパルの資格情報を登録する必要がありますが、。 これを行うには、最初に .CER ファイルとして保存されている X.509 Base64 を入手する必要があります。 この証明書は、Office 365 のサービス ・ プリンシパルに適用されます。
  
X.509 証明書を取得したときは、Microsoft Online Services モジュールを起動 ([**スタート**] ボタン、[**すべてのプログラム**] をクリックして、 **Microsoft Online Services**] をクリックし、 **Microsoft Online Services モジュールの Windows をクリックし、PowerShell**)。 サービス モジュールを開くと後、は、サービス ・ プリンシパルを管理するために使用できるコマンドレットが含まれている Microsoft オンラインの Windows PowerShell モジュールをインポートするのには、次を入力します。
  
```
Import-Module MSOnlineExtended
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

証明書をインポートし、エンコードされたが後、は、Office 365 のサービス ・ プリンシパルをし証明書を割り当てることができます。 Business Server の Skype とは Microsoft Exchange のサービス ・ プリンシパルの両方の AppPrincipalId プロパティの値を取得するために最初に取得-MsolServicePrincipal を使用します。AppPrincipalId プロパティの値は、証明書を割り当てられているサービス ・ プリンシパルを識別するのには適用されます。 AppPrincipalId プロパティ値の Skype のビジネス サーバー 2015 に対し、Skype の Office 365 バージョンにビジネスのサーバーの証明書を割り当てるには次のコマンドを使用します。
  
```
New-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -Type Asymmetric -Usage Verify -Value $credentialsValue 
```

必要がありますし、コマンドを繰り返し実行、Exchange 2013 の AppPrincipalId プロパティの値を使用してこの時間です。
  
後でその証明書の削除が必要になった場合は、最初に証明書の KeyId を取得することで削除できます。
  
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

証明書を割り当てるだけでなくも Exchange のオンライン サービス主体を構成し、Office 365 のサービス主体と外部の Web サービスの Url をビジネス サーバー 2015 の Skype の設置型バージョンを構成する必要があります。 これを行うには、次の 2 つのコマンドを実行します。 
  
次の例では、lync.contoso.com は、Skype のビジネス サーバー プールの外部 Web サービスの URL です。 展開内のすべての外部 Web サービスの Url を追加するのには次の手順を繰り返す必要があります。
  
```
Set-MSOLServicePrincipal -AppPrincipalID 00000002-0000-0ff1-ce00-000000000000 -AccountEnabled $true
$lyncSP = Get-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000
$lyncSP.ServicePrincipalNames.Add("00000004-0000-0ff1-ce00-000000000000/lync.contoso.com")
Set-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $lyncSP.ServicePrincipalNames
```