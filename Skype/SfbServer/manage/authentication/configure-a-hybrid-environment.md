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
# <a name="configure-server-to-server-authentication-for-a-skype-for-business-server-hybrid-environment"></a><span data-ttu-id="0b887-103">Skype for Business Server ハイブリッド環境用のサーバー間認証を構成します。</span><span class="sxs-lookup"><span data-stu-id="0b887-103">Configure server-to-server authentication for a Skype for Business Server hybrid environment.</span></span>

<span data-ttu-id="0b887-104">**概要:** Skype for Business Server ハイブリッド環境用のサーバー間認証を構成します。</span><span class="sxs-lookup"><span data-stu-id="0b887-104">**Summary:** Configure server-to-server authentication for Skype for Business Server hybrid environment.</span></span>

<span data-ttu-id="0b887-105">ハイブリッド構成では、一部のユーザーは Skype for business server のオンプレミスインストールに所属し、他のユーザーは Skype for Business Server の Microsoft 365 または Office 365 バージョンに所属しています。</span><span class="sxs-lookup"><span data-stu-id="0b887-105">In a hybrid configuration, some of your users are homed on an on-premises installation of Skype for Business Server while other users are homed on the Microsoft 365 or Office 365 version of Skype for Business Server.</span></span> <span data-ttu-id="0b887-106">ハイブリッド環境でサーバー間認証を構成するには、最初に、認証サーバーを信頼するように Skype for Business Server のオンプレミスインストールを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0b887-106">In order to configure server-to-server authentication in a hybrid environment, you must first configure your on-premises installation of Skype for Business Server to trust the authorization server.</span></span> <span data-ttu-id="0b887-107">このプロセスの最初の手順は、次の Skype for Business Server 管理シェルスクリプトを実行することによって実行できます。</span><span class="sxs-lookup"><span data-stu-id="0b887-107">The initial step in this process can be carried out by running the following Skype for Business Server Management Shell script:</span></span>

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

<span data-ttu-id="0b887-p102">通常、テナントの領域名は組織名と異なることに注意してください。実際には、領域名はほぼ常にテナント ID と同じです。このため、スクリプトの最初の行を使用して、指定したテナント (この場合は fabrikam.com) の TenantId プロパティの値を取得してから、名前を変数 $TenantId に割り当てます。</span><span class="sxs-lookup"><span data-stu-id="0b887-p102">Keep in mind that the realm name for a tenant is typically different than the organization name; in fact, the realm name is almost always the same as the tenant ID. Because of that, the first line in the script is used to return the value of the TenantId property for the specified tenant (in this case, fabrikam.com) and then assign that name to the variable $TenantId:</span></span>

```PowerShell
$TenantID = (Get-CsTenant -Filter {DisplayName -eq "Fabrikam.com"}).TenantId
```

<span data-ttu-id="0b887-110">このスクリプトを実行するには、このモジュールを使用して Skype for Business Online PowerShell モジュールをインストールし、テナントに接続する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0b887-110">To execute this script, you must have installed Skype for Business Online PowerShell module and connect to your tenant with this module.</span></span> <span data-ttu-id="0b887-111">これらのコマンドレットをインストールしていない場合、Get-cstenant コマンドレットは使用できないため、スクリプトは失敗します。</span><span class="sxs-lookup"><span data-stu-id="0b887-111">If you have not installed these cmdlets your script will fail because the Get-CsTenant cmdlet will not be available.</span></span> <span data-ttu-id="0b887-112">スクリプトが完了したら、Skype for Business Server と承認サーバー間の信頼関係と、Exchange 2013/2016 と承認サーバー間の2つ目の信頼関係を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0b887-112">After the script completes, you must then configure a trust relationship between Skype for Business Server and the authorization server, and a second trust relationship between Exchange 2013/2016 and the authorization server.</span></span> <span data-ttu-id="0b887-113">これは、Microsoft Online Services コマンドレットを使用してのみ行うことができます。</span><span class="sxs-lookup"><span data-stu-id="0b887-113">This can only be done by using the Microsoft Online Services cmdlets.</span></span>

> [!NOTE]
> <span data-ttu-id="0b887-114">Microsoft Online Services コマンドレットをインストールしていない場合は、コマンドレットを使用して PowerShell リポジトリからインストールする必要があり `install-module MSOnline` ます。</span><span class="sxs-lookup"><span data-stu-id="0b887-114">If you have not installed the Microsoft Online Services cmdlets, you will need to install it from the PowerShell repository with the cmdlet `install-module MSOnline`.</span></span> <span data-ttu-id="0b887-115">Microsoft Online Services モジュールのインストールおよび使用方法の詳細については、Microsoft 365 web サイトを参照してください。</span><span class="sxs-lookup"><span data-stu-id="0b887-115">Detailed information for installing and using the Microsoft Online Services Module can be found on the Microsoft 365 web site.</span></span> <span data-ttu-id="0b887-116">これらの手順では、Microsoft 365 または Office 365 と Active Directory との間でシングルサインオン、フェデレーション、および同期を構成する方法についても説明します。</span><span class="sxs-lookup"><span data-stu-id="0b887-116">These instructions will also tell you how to configure single sign-on, federation, and synchronization between Microsoft 365 or Office 365 and Active Directory.</span></span> 



<span data-ttu-id="0b887-117">Microsoft 365 または Office 365 を構成した後、Skype for Business Server と Exchange の2013に Microsoft 365 または Office 365 サービスプリンシパルを作成した後は、これらのサービスプリンシパルで資格情報を登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0b887-117">After you have configured Microsoft 365 or Office 365, and after you have created Microsoft 365 or Office 365 service principals for Skype for Business Server and Exchange 2013, you will then need to register your credentials with these service principals.</span></span> <span data-ttu-id="0b887-118">そのためには、まず、として保存された x.509 Base64 証明書を取得する必要があります。CER ファイル。</span><span class="sxs-lookup"><span data-stu-id="0b887-118">In order to do this, you must first obtain an X.509 Base64 certificate saved as a .CER file.</span></span> <span data-ttu-id="0b887-119">この証明書は、Microsoft 365 または Office 365 のサービスプリンシパルに適用されます。</span><span class="sxs-lookup"><span data-stu-id="0b887-119">This certificate will then be applied to the Microsoft 365 or Office 365 service principals.</span></span>

<span data-ttu-id="0b887-120">X.509 証明書を取得したら、PowerShell コンソールを開いて、サービスプリンシパルの管理に使用できるコマンドレットを含む Microsoft Online Windows PowerShell モジュールをインポートします。</span><span class="sxs-lookup"><span data-stu-id="0b887-120">When you have obtained the X.509 certificate, open PowerShell console and import the Microsoft Online Windows PowerShell module containing the cmdlets that can be used to manage service principals:</span></span>

```PowerShell
Import-Module MSOnline
```

<span data-ttu-id="0b887-121">モジュールがインポートされたら、次のコマンドを入力して enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="0b887-121">When the module has been imported, type the following command and then press ENTER:</span></span>

```PowerShell
Connect-MsolService
```

<span data-ttu-id="0b887-122">Enter キーを押すと、資格情報ダイアログ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0b887-122">After you press ENTER, a credentials dialog box will appear.</span></span> <span data-ttu-id="0b887-123">ダイアログボックスに Microsoft 365 または Office 365 のユーザー名とパスワードを入力し、[OK] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0b887-123">Enter your Microsoft 365 or Office 365 user name and password in the dialog box, and then click OK.</span></span>

<span data-ttu-id="0b887-124">Microsoft 365 または Office 365 に接続した直後に、次のコマンドを実行してサービスプリンシパルに関する情報を戻すことができます。</span><span class="sxs-lookup"><span data-stu-id="0b887-124">As soon as you are connected to Microsoft 365 or Office 365, you can then run the following command in order to return information about your service principals:</span></span>

```PowerShell
Get-MsolServicePrincipal
```

<span data-ttu-id="0b887-125">すべてのサービス プリンシパルについて次のような情報が返されます。</span><span class="sxs-lookup"><span data-stu-id="0b887-125">You should get back information similar to this for all your service principals:</span></span>

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

<span data-ttu-id="0b887-126">次の手順は、X.509 証明書のインポート、エンコード、および割り当てです。</span><span class="sxs-lookup"><span data-stu-id="0b887-126">The next step is to import, encode, and assign the X.509 certificate.</span></span> <span data-ttu-id="0b887-127">証明書をインポートおよびエンコードするには、次の Windows PowerShell コマンドを使用します。これには、の完全なファイルパスを指定してください。CER ファイルを使用して、Import メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="0b887-127">To import and encode the certificate, use the following Windows PowerShell commands, being sure to specify the complete file path to your .CER file when you call the Import method:</span></span>

```PowerShell
$certificate = New-Object System.Security.Cryptography.X509Certificates.X509Certificate
$certificate.Import("C:\Certificates\Office365.cer")
$binaryValue = $certificate.GetRawCertData()
$credentialsValue = [System.Convert]::ToBase64String($binaryValue) 
```

<span data-ttu-id="0b887-128">証明書をインポートしてエンコードした後、証明書を Microsoft 365 または Office 365 のサービスプリンシパルに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="0b887-128">After the certificate has been imported and encoded, you can then assign the certificate to your Microsoft 365 or Office 365 service principals.</span></span> <span data-ttu-id="0b887-129">そのためには、最初に New-msolserviceprincipal を使用して、Skype for Business サーバーと Microsoft Exchange サービスプリンシパルの AppPrincipalId プロパティの値を取得します。AppPrincipalId プロパティの値は、証明書を割り当てられているサービスプリンシパルを識別するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="0b887-129">To do that, first use the Get-MsolServicePrincipal to retrieve the value of the AppPrincipalId property for both the Skype for Business Server and the Microsoft Exchange service principals; the value of the AppPrincipalId property will be used to identify the service principal being assigned the certificate.</span></span> <span data-ttu-id="0b887-130">Skype for Business Server の AppPrincipalId プロパティの値を使用して、次のコマンドを使用して、証明書を Skype For Business Online のバージョンに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="0b887-130">With the AppPrincipalId property value for Skype for Business Server in hand, use the following command to assign the certificate to Skype For Business Online version:</span></span>

```PowerShell
New-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -Type Asymmetric -Usage Verify -Value $credentialsValue 
```

<span data-ttu-id="0b887-131">その後、このコマンドを繰り返し実行します。このとき、Exchange 2013 の AppPrincipalId プロパティの値を使用します。</span><span class="sxs-lookup"><span data-stu-id="0b887-131">You should then repeat the command, this time using the AppPrincipalId property value for Exchange 2013.</span></span>

<span data-ttu-id="0b887-132">後でその証明書を削除する必要がある場合 (たとえば、期限が切れている場合)、最初に証明書のキー Id を取得します。</span><span class="sxs-lookup"><span data-stu-id="0b887-132">If you later need to delete that certificate, for example if it has expired, you can do so by first retrieving the KeyId for the certificate:</span></span>

```PowerShell
Get-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000
```

<span data-ttu-id="0b887-133">そのコマンドは、次のようなデータを返します。</span><span class="sxs-lookup"><span data-stu-id="0b887-133">That command will return data like this one:</span></span>

<pre>
Type      : Asymmetric
Value     : 
KeyId     : bc2795f3-2387-4543-a95d-f92c85c7a1b0
StartDate : 6/1/2012 8:00:00 AM
EndDate   : 5/31/2013 8:00:00 AM
Usage     : Verify
</pre>

<span data-ttu-id="0b887-134">続いて、次のようなコマンドを使用して証明書を削除できます。</span><span class="sxs-lookup"><span data-stu-id="0b887-134">You can then delete the certificate by using a command similar to this:</span></span>

```PowerShell
Remove-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -KeyId bc2795f3-2387-4543-a95d-f92c85c7a1b0
```

<span data-ttu-id="0b887-135">証明書を割り当てるだけでなく、Exchange Online サービスプリンシパルを構成して、社内バージョンの Skype for Business Server の外部 Web サービス Url を Microsoft 365 または Office 365 サービスプリンシパルとして構成する必要もあります。</span><span class="sxs-lookup"><span data-stu-id="0b887-135">In addition to assigning a certificate, you must also configure the Exchange Online Service Principal and configure your on-premises version of Skype for Business Server external Web services URLs as a Microsoft 365 or Office 365 service principal.</span></span> <span data-ttu-id="0b887-136">そのためには、次の2つのコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="0b887-136">That can be done by carrying out the following two commands.</span></span> 

<span data-ttu-id="0b887-137">次の例では、Pool1ExternalWebFQDN.contoso.com は、Skype for Business Server プールの外部 Web サービスの URL です。</span><span class="sxs-lookup"><span data-stu-id="0b887-137">In the following example, Pool1ExternalWebFQDN.contoso.com is the external Web services URL for the Skype for Business Server pool.</span></span> <span data-ttu-id="0b887-138">これらの手順を繰り返して、展開内のすべての外部 Web サービス Url を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0b887-138">You should repeat these steps to add all the external Web services URLs in the deployment.</span></span>

```PowerShell
Set-MSOLServicePrincipal -AppPrincipalID 00000002-0000-0ff1-ce00-000000000000 -AccountEnabled $true
$lyncSP = Get-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000
$lyncSP.ServicePrincipalNames.Add("00000004-0000-0ff1-ce00-000000000000/Pool1ExternalWebFQDN.contoso.com")
Set-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $lyncSP.ServicePrincipalNames
```
