---
title: Skype for Business Server ハイブリッド環境に対するサーバー間認証を構成する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 700639ec-5264-4449-a8a6-d7386fad8719
description: '概要: Skype for Business Server ハイブリッド環境に対するサーバー間認証を構成します。'
ms.openlocfilehash: d0c82d39c5232ccc3d425bad9533bf23b67dc8a6
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34285534"
---
# <a name="configure-server-to-server-authentication-for-a-skype-for-business-server-hybrid-environment"></a>Skype for Business Server ハイブリッド環境に対するサーバー間認証を構成する。

**概要:** Skype for Business Server ハイブリッド環境のサーバー間認証を構成します。

ハイブリッド構成では、他のユーザーが skype for Business Server の Office 365 バージョンを使っているときに、一部のユーザーが Skype for Business Server のオンプレミスインストールをホームとしています。 ハイブリッド環境でサーバー間認証を構成するには、まず、Office 365 承認サーバーを信頼するように、Skype for Business Server のオンプレミスインストールを構成する必要があります。 このプロセスの最初の手順は、次の Skype for Business Server 管理シェルスクリプトを実行して実行できます。

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

このスクリプトを実行するには、このモジュールを使用して、Skype for Business Online Powershell モジュールをインストールし、テナントに接続している必要があります。 これらのコマンドレットがインストールされていない場合、Get-CsTenant コマンドレットを使用できないためにスクリプトは失敗します。 スクリプトが完了したら、Skype for Business Server と承認サーバー間の信頼関係と、Exchange 2013/2016 と承認サーバーとの間の2番目の信頼関係を構成する必要があります。 これは、Microsoft Online Services コマンドレットを使用してのみ行うことができます。

> [!NOTE]
> Microsoft Online Services コマンドレットをインストールしていない場合は、powershell リポジトリからコマンドレットのインストール-モジュール MSOnline をインストールする必要があります。 Microsoft Online Services モジュールのインストールと使用の詳細については、Office 365 web サイトを参照してください。 この手順では、Office 365 と Active Directory の間でシングルサインオン、フェデレーション、同期を構成する方法についても説明します。 



Office 365 を構成した後、Skype for Business Server および Exchange 2013 の Office 365 サービスプリンシパルを作成した後、これらのサービスプリンシパルに資格情報を登録する必要があります。 これを行うには、最初に .CER ファイルとして保存されている X.509 Base64 を入手する必要があります。 この証明書は、Office 365 サービスプリンシパルに適用されます。

X.509 証明書を取得したら、Powershell コンソールを開き、サービスプリンシパルを管理するために使用できるコマンドレットが含まれている Microsoft Online Windows PowerShell モジュールをインポートします。

```
Import-Module MSOnline
```

モジュールがインポートされたら、次のコマンドを入力し、ENTER キーを押して Office 365 に接続します。

```
Connect-MsolService
```

Enter キーを押すと、資格情報ダイアログ ボックスが表示されます。 ダイアログボックスに Office 365 のユーザー名とパスワードを入力して、[OK] をクリックします。

Office 365 に接続したら、次のコマンドを実行して、サービスプリンシパルに関する情報を返すことができます。

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

次の手順は、X.509 証明書のインポート、エンコード、および割り当てです。 証明書をインポートしてエンコードするには、次の Windows PowerShell コマンドを使用します。そのための完全なファイルパスを指定していることを確認します。インポートメソッドを呼び出すときの CER ファイル:

```
$certificate = New-Object System.Security.Cryptography.X509Certificates.X509Certificate
$certificate.Import("C:\Certificates\Office365.cer")
$binaryValue = $certificate.GetRawCertData()
$credentialsValue = [System.Convert]::ToBase64String($binaryValue)
```

証明書をインポートしてエンコードした後で、その証明書を Office 365 のサービスプリンシパルに割り当てることができます。 そのためには、最初に MsolServicePrincipal を使って、Skype for Business Server と Microsoft Exchange サービスプリンシパルのた appprincipalid プロパティの値を取得します。た appprincipalid プロパティの値は、証明書を割り当てられているサービスプリンシパルを識別するために使用されます。 Skype for Business Server のた appprincipalid プロパティの値を指定して、次のコマンドを使用して、証明書を Skype For Business Online のバージョンに割り当てます。

```
New-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -Type Asymmetric -Usage Verify -Value $credentialsValue 
```

今回は、このコマンドを Exchange 2013 のた appprincipalid プロパティの値を使って実行する必要があります。

有効期限が切れたなど、後でその証明書を削除する必要がある場合は、まず、証明書のキー Id を取得します。

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

証明書を割り当てるだけでなく、Office 365 サービスプリンシパルとして、Exchange Online サービスプリンシパルを構成して、オンプレミスバージョンの Skype for Business Server の外部 Web サービス Url を構成する必要もあります。 これを行うには、次の 2 つのコマンドを実行します。 

次の例では、Pool1ExternalWebFQDN.contoso.com は、Skype for Business Server プールの外部 Web サービスの URL です。 展開内のすべての外部 Web サービスの Url を追加するには、この手順を繰り返す必要があります。

```
Set-MSOLServicePrincipal -AppPrincipalID 00000002-0000-0ff1-ce00-000000000000 -AccountEnabled $true
$lyncSP = Get-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000
$lyncSP.ServicePrincipalNames.Add("00000004-0000-0ff1-ce00-000000000000/Pool1ExternalWebFQDN.contoso.com")
Set-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $lyncSP.ServicePrincipalNames
```
