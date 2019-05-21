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
# <a name="configure-server-to-server-authentication-for-a-skype-for-business-server-hybrid-environment"></a><span data-ttu-id="799b9-103">Skype for Business Server ハイブリッド環境に対するサーバー間認証を構成する。</span><span class="sxs-lookup"><span data-stu-id="799b9-103">Configure server-to-server authentication for a Skype for Business Server hybrid environment.</span></span>

<span data-ttu-id="799b9-104">**概要:** Skype for Business Server ハイブリッド環境のサーバー間認証を構成します。</span><span class="sxs-lookup"><span data-stu-id="799b9-104">**Summary:** Configure server-to-server authentication for Skype for Business Server hybrid environment.</span></span>

<span data-ttu-id="799b9-105">ハイブリッド構成では、他のユーザーが skype for Business Server の Office 365 バージョンを使っているときに、一部のユーザーが Skype for Business Server のオンプレミスインストールをホームとしています。</span><span class="sxs-lookup"><span data-stu-id="799b9-105">In a hybrid configuration, some of your users are homed on an on-premises installation of Skype for Business Server while other users are homed on the Office 365 version of Skype for Business Server.</span></span> <span data-ttu-id="799b9-106">ハイブリッド環境でサーバー間認証を構成するには、まず、Office 365 承認サーバーを信頼するように、Skype for Business Server のオンプレミスインストールを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="799b9-106">In order to configure server-to-server authentication in a hybrid environment, you must first configure your on-premises installation of Skype for Business Server to trust the Office 365 authorization server.</span></span> <span data-ttu-id="799b9-107">このプロセスの最初の手順は、次の Skype for Business Server 管理シェルスクリプトを実行して実行できます。</span><span class="sxs-lookup"><span data-stu-id="799b9-107">The initial step in this process can be carried out by running the following Skype for Business Server Management Shell script:</span></span>

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

<span data-ttu-id="799b9-p102">通常、テナントの領域名は組織名と異なることに注意してください。実際には、領域名はほぼ常にテナント ID と同じです。このため、スクリプトの最初の行を使用して、指定したテナント (この場合は fabrikam.com) の TenantId プロパティの値を取得してから、名前を変数 $TenantId に割り当てます。</span><span class="sxs-lookup"><span data-stu-id="799b9-p102">Keep in mind that the realm name for a tenant is typically different than the organization name; in fact, the realm name is almost always the same as the tenant ID. Because of that, the first line in the script is used to return the value of the TenantId property for the specified tenant (in this case, fabrikam.com) and then assign that name to the variable $TenantId:</span></span>

```
$TenantID = (Get-CsTenant -DisplayName "Fabrikam.com").TenantId
```

<span data-ttu-id="799b9-110">このスクリプトを実行するには、このモジュールを使用して、Skype for Business Online Powershell モジュールをインストールし、テナントに接続している必要があります。</span><span class="sxs-lookup"><span data-stu-id="799b9-110">To execute this script, you must have installed Skype for Business Online Powershell module and connect to your tenant with this module.</span></span> <span data-ttu-id="799b9-111">これらのコマンドレットがインストールされていない場合、Get-CsTenant コマンドレットを使用できないためにスクリプトは失敗します。</span><span class="sxs-lookup"><span data-stu-id="799b9-111">If you have not installed these cmdlets your script will fail because the Get-CsTenant cmdlet will not be available.</span></span> <span data-ttu-id="799b9-112">スクリプトが完了したら、Skype for Business Server と承認サーバー間の信頼関係と、Exchange 2013/2016 と承認サーバーとの間の2番目の信頼関係を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="799b9-112">After the script completes, you must then configure a trust relationship between Skype for Business Server and the authorization server, and a second trust relationship between Exchange 2013/2016 and the authorization server.</span></span> <span data-ttu-id="799b9-113">これは、Microsoft Online Services コマンドレットを使用してのみ行うことができます。</span><span class="sxs-lookup"><span data-stu-id="799b9-113">This can only be done by using the Microsoft Online Services cmdlets.</span></span>

> [!NOTE]
> <span data-ttu-id="799b9-114">Microsoft Online Services コマンドレットをインストールしていない場合は、powershell リポジトリからコマンドレットのインストール-モジュール MSOnline をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="799b9-114">If you have not installed the Microsoft Online Services cmdlets, you will need to install it from powershell repository with cmdlet install-module MSOnline.</span></span> <span data-ttu-id="799b9-115">Microsoft Online Services モジュールのインストールと使用の詳細については、Office 365 web サイトを参照してください。</span><span class="sxs-lookup"><span data-stu-id="799b9-115">Detailed information for installing and using the Microsoft Online Services Module can be found on the Office 365 web site.</span></span> <span data-ttu-id="799b9-116">この手順では、Office 365 と Active Directory の間でシングルサインオン、フェデレーション、同期を構成する方法についても説明します。</span><span class="sxs-lookup"><span data-stu-id="799b9-116">These instructions will also tell you how to configure single sign-on, federation, and synchronization between Office 365 and Active Directory.</span></span> 



<span data-ttu-id="799b9-117">Office 365 を構成した後、Skype for Business Server および Exchange 2013 の Office 365 サービスプリンシパルを作成した後、これらのサービスプリンシパルに資格情報を登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="799b9-117">After you have configured Office 365, and after you have created Office 365 service principals for Skype for Business Server and Exchange 2013, you will then need to register your credentials with these service principals.</span></span> <span data-ttu-id="799b9-118">これを行うには、最初に .CER ファイルとして保存されている X.509 Base64 を入手する必要があります。</span><span class="sxs-lookup"><span data-stu-id="799b9-118">In order to do this, you must first obtain an X.509 Base64 saved as a .CER file.</span></span> <span data-ttu-id="799b9-119">この証明書は、Office 365 サービスプリンシパルに適用されます。</span><span class="sxs-lookup"><span data-stu-id="799b9-119">This certificate will then be applied to the Office 365 service principals.</span></span>

<span data-ttu-id="799b9-120">X.509 証明書を取得したら、Powershell コンソールを開き、サービスプリンシパルを管理するために使用できるコマンドレットが含まれている Microsoft Online Windows PowerShell モジュールをインポートします。</span><span class="sxs-lookup"><span data-stu-id="799b9-120">When you have obtained the X.509 certificate, open Powershell console and import the Microsoft Online Windows PowerShell module containing the cmdlets that can be used to manage service principals:</span></span>

```
Import-Module MSOnline
```

<span data-ttu-id="799b9-121">モジュールがインポートされたら、次のコマンドを入力し、ENTER キーを押して Office 365 に接続します。</span><span class="sxs-lookup"><span data-stu-id="799b9-121">When the module has been imported, type the following command and then press ENTER in order to connect to Office 365:</span></span>

```
Connect-MsolService
```

<span data-ttu-id="799b9-122">Enter キーを押すと、資格情報ダイアログ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="799b9-122">After you press ENTER, a credentials dialog box will appear.</span></span> <span data-ttu-id="799b9-123">ダイアログボックスに Office 365 のユーザー名とパスワードを入力して、[OK] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="799b9-123">Enter your Office 365 user name and password in the dialog box, and then click OK.</span></span>

<span data-ttu-id="799b9-124">Office 365 に接続したら、次のコマンドを実行して、サービスプリンシパルに関する情報を返すことができます。</span><span class="sxs-lookup"><span data-stu-id="799b9-124">As soon as you are connected to Office 365, you can then run the following command in order to return information about your service principals:</span></span>

```
Get-MsolServicePrincipal
```

<span data-ttu-id="799b9-125">すべてのサービス プリンシパルについて次のような情報が返されます。</span><span class="sxs-lookup"><span data-stu-id="799b9-125">You should get back information similar to this for all your service principals:</span></span>

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

<span data-ttu-id="799b9-126">次の手順は、X.509 証明書のインポート、エンコード、および割り当てです。</span><span class="sxs-lookup"><span data-stu-id="799b9-126">The next step is to import, encode, and assign the X.509 certificate.</span></span> <span data-ttu-id="799b9-127">証明書をインポートしてエンコードするには、次の Windows PowerShell コマンドを使用します。そのための完全なファイルパスを指定していることを確認します。インポートメソッドを呼び出すときの CER ファイル:</span><span class="sxs-lookup"><span data-stu-id="799b9-127">To import and encode the certificate, use the following Windows PowerShell commands, being sure to specify the complete file path to your .CER file when you call the Import method:</span></span>

```
$certificate = New-Object System.Security.Cryptography.X509Certificates.X509Certificate
$certificate.Import("C:\Certificates\Office365.cer")
$binaryValue = $certificate.GetRawCertData()
$credentialsValue = [System.Convert]::ToBase64String($binaryValue)
```

<span data-ttu-id="799b9-128">証明書をインポートしてエンコードした後で、その証明書を Office 365 のサービスプリンシパルに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="799b9-128">After the certificate has been imported and encoded, you can then assign the certificate to your Office 365 service principals.</span></span> <span data-ttu-id="799b9-129">そのためには、最初に MsolServicePrincipal を使って、Skype for Business Server と Microsoft Exchange サービスプリンシパルのた appprincipalid プロパティの値を取得します。た appprincipalid プロパティの値は、証明書を割り当てられているサービスプリンシパルを識別するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="799b9-129">To do that, first use the Get-MsolServicePrincipal to retrieve the value of the AppPrincipalId property for both the Skype for Business Server and the Microsoft Exchange service principals; the value of the AppPrincipalId property will be used to identify the service principal being assigned the certificate.</span></span> <span data-ttu-id="799b9-130">Skype for Business Server のた appprincipalid プロパティの値を指定して、次のコマンドを使用して、証明書を Skype For Business Online のバージョンに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="799b9-130">With the AppPrincipalId property value for Skype for Business Server in hand, use the following command to assign the certificate to Skype For Business Online version:</span></span>

```
New-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -Type Asymmetric -Usage Verify -Value $credentialsValue 
```

<span data-ttu-id="799b9-131">今回は、このコマンドを Exchange 2013 のた appprincipalid プロパティの値を使って実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="799b9-131">You should then repeat the command, this time using the AppPrincipalId property value for Exchange 2013.</span></span>

<span data-ttu-id="799b9-132">有効期限が切れたなど、後でその証明書を削除する必要がある場合は、まず、証明書のキー Id を取得します。</span><span class="sxs-lookup"><span data-stu-id="799b9-132">If you later need to delete that certificate, for example if it has expired, you can do so by first retrieving the KeyId for the certificate:</span></span>

```
Get-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000
```

<span data-ttu-id="799b9-133">そのコマンドは、次のようなデータを返します。</span><span class="sxs-lookup"><span data-stu-id="799b9-133">That command will return data like this one:</span></span>

<pre>
Type      : Asymmetric
Value     : 
KeyId     : bc2795f3-2387-4543-a95d-f92c85c7a1b0
StartDate : 6/1/2012 8:00:00 AM
EndDate   : 5/31/2013 8:00:00 AM
Usage     : Verify
</pre>

<span data-ttu-id="799b9-134">続いて、次のようなコマンドを使用して証明書を削除できます。</span><span class="sxs-lookup"><span data-stu-id="799b9-134">You can then delete the certificate by using a command similar to this:</span></span>

```
Remove-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -KeyId bc2795f3-2387-4543-a95d-f92c85c7a1b0
```

<span data-ttu-id="799b9-135">証明書を割り当てるだけでなく、Office 365 サービスプリンシパルとして、Exchange Online サービスプリンシパルを構成して、オンプレミスバージョンの Skype for Business Server の外部 Web サービス Url を構成する必要もあります。</span><span class="sxs-lookup"><span data-stu-id="799b9-135">In addition to assigning a certificate, you must also configure the Exchange Online Service Principal and configure your on-premises version of Skype for Business Server external Web services URLs as an Office 365 service principal.</span></span> <span data-ttu-id="799b9-136">これを行うには、次の 2 つのコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="799b9-136">That can be done by carrying out the following two commands.</span></span> 

<span data-ttu-id="799b9-137">次の例では、Pool1ExternalWebFQDN.contoso.com は、Skype for Business Server プールの外部 Web サービスの URL です。</span><span class="sxs-lookup"><span data-stu-id="799b9-137">In the following example, Pool1ExternalWebFQDN.contoso.com is the external Web services URL for the Skype for Business Server pool.</span></span> <span data-ttu-id="799b9-138">展開内のすべての外部 Web サービスの Url を追加するには、この手順を繰り返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="799b9-138">You should repeat these steps to add all the external Web services URLs in the deployment.</span></span>

```
Set-MSOLServicePrincipal -AppPrincipalID 00000002-0000-0ff1-ce00-000000000000 -AccountEnabled $true
$lyncSP = Get-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000
$lyncSP.ServicePrincipalNames.Add("00000004-0000-0ff1-ce00-000000000000/Pool1ExternalWebFQDN.contoso.com")
Set-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $lyncSP.ServicePrincipalNames
```
