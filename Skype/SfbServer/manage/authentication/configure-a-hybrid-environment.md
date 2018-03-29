---
title: Skype for Business Server 2015 でハイブリッド環境を構成する
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
description: '概要: ハイブリッド環境でビジネス サーバー 2015 の Skype を構成します。'
ms.openlocfilehash: e31338647338854b260c9f8935cac4dde69df490
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="configure-a-hybrid-environment-in-skype-for-business-server-2015"></a><span data-ttu-id="f2aae-103">Skype for Business Server 2015 でハイブリッド環境を構成する</span><span class="sxs-lookup"><span data-stu-id="f2aae-103">Configure a hybrid environment in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="f2aae-104">**の概要:**ビジネス サーバー 2015 のハイブリッド環境で Skype を構成します。</span><span class="sxs-lookup"><span data-stu-id="f2aae-104">**Summary:** Configure Skype for Business Server 2015 in a hybrid environment.</span></span>
  
<span data-ttu-id="f2aae-105">ハイブリッド構成では、一部のユーザーが置かれている Skype の設置型インストールのビジネス サーバー 2015 のビジネス サーバーの他のユーザーが Skype の Office 365 バージョンに置かれているときにします。</span><span class="sxs-lookup"><span data-stu-id="f2aae-105">In a hybrid configuration, some of your users are homed on an on-premises installation of Skype for Business Server 2015 while other users are homed on the Office 365 version of Skype for Business Server.</span></span> <span data-ttu-id="f2aae-106">ハイブリッド環境でサーバーからサーバーへの認証を構成するためには、最初に Office 365 の認証サーバーを信頼するようにサーバー 2015 のビジネス用の Skype のオンプレミス インストールを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f2aae-106">In order to configure server-to-server authentication in a hybrid environment, you must first configure your on-premises installation of Skype for Business Server 2015 to trust the Office 365 authorization server.</span></span> <span data-ttu-id="f2aae-107">このプロセスの初期手順を実行するには、次の Skype ビジネス サーバー管理シェル スクリプトを実行しています。</span><span class="sxs-lookup"><span data-stu-id="f2aae-107">The initial step in this process can be carried out by running the following Skype for Business Server Management Shell script:</span></span>
  
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

<span data-ttu-id="f2aae-p102">通常、テナントの領域名は組織名と異なることに注意してください。実際には、領域名はほぼ常にテナント ID と同じです。このため、スクリプトの最初の行を使用して、指定したテナント (この場合は fabrikam.com) の TenantId プロパティの値を取得してから、名前を変数 $TenantId に割り当てます。</span><span class="sxs-lookup"><span data-stu-id="f2aae-p102">Keep in mind that the realm name for a tenant is typically different than the organization name; in fact, the realm name is almost always the same as the tenant ID. Because of that, the first line in the script is used to return the value of the TenantId property for the specified tenant (in this case, fabrikam.com) and then assign that name to the variable $TenantId:</span></span>
  
```
$TenantID = (Get-CsTenant -DisplayName "Fabrikam.com").TenantId
```

<span data-ttu-id="f2aae-110">スクリプトが完了するは、ビジネス サーバー 2015 の Skype と認証サーバーとの間に信頼関係と Exchange 2013 と認証サーバーとの間の 2 つ目の信頼関係を構成する必要がありますし。</span><span class="sxs-lookup"><span data-stu-id="f2aae-110">After the script completes, you must then configure a trust relationship between Skype for Business Server 2015 and the authorization server, and a second trust relationship between Exchange 2013 and the authorization server.</span></span> <span data-ttu-id="f2aae-111">これは、Microsoft Online Services コマンドレットを使用してのみ行うことができます。</span><span class="sxs-lookup"><span data-stu-id="f2aae-111">This can only be done by using the Microsoft Online Services cmdlets.</span></span>
  
> [!NOTE]
> <span data-ttu-id="f2aae-112">Microsoft Online Services コマンドレットをインストールしていない場合は、先に進む前に 2 つの作業を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="f2aae-112">If you have not installed the Microsoft Online Services cmdlets, you will need to do two things before proceeding.</span></span> <span data-ttu-id="f2aae-113">最初に、64 ビット バージョンの Microsoft Online Services サインイン アシスタントをダウンロードしてインストールします。</span><span class="sxs-lookup"><span data-stu-id="f2aae-113">First, download and install the 64-bit version of the Microsoft Online Services Sign-in Assistant.</span></span> <span data-ttu-id="f2aae-114">インストールが完了したらをダウンロードして、Microsoft Online Services モジュールを Windows PowerShell の 64 ビット バージョンをインストールします。</span><span class="sxs-lookup"><span data-stu-id="f2aae-114">After installation is complete, download and install the 64-bit version of the Microsoft Online Services Module for Windows PowerShell.</span></span> <span data-ttu-id="f2aae-115">Web サイトで Office 365 をインストールして、Microsoft Online Services のモジュールを使用しての詳細情報をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="f2aae-115">Detailed information for installing and using the Microsoft Online Services Module can be found on the Office 365 web site.</span></span> <span data-ttu-id="f2aae-116">次の手順もわかりますシングル サイン オン、フェデレーション、および Office 365 と Active Directory 間の同期を構成する方法です。</span><span class="sxs-lookup"><span data-stu-id="f2aae-116">These instructions will also tell you how to configure single sign-on, federation, and synchronization between Office 365 and Active Directory.</span></span> 
  
<span data-ttu-id="f2aae-117">これらのコマンドレットがインストールされていない場合、Get-CsTenant コマンドレットを使用できないためにスクリプトは失敗します。</span><span class="sxs-lookup"><span data-stu-id="f2aae-117">If you have not installed these cmdlets your script will fail because the Get-CsTenant cmdlet will not be available.</span></span>
  
<span data-ttu-id="f2aae-118">、Office 365 を構成した後、およびビジネス サーバー 2015」および「Exchange 2013 の、Office 365 Skype のサービス ・ プリンシパルを作成した後は、これらのサービス ・ プリンシパルの資格情報を登録する必要がありますが、。</span><span class="sxs-lookup"><span data-stu-id="f2aae-118">After you have configured Office 365, and after you have created Office 365 service principals for Skype for Business Server 2015 and Exchange 2013, you will then need to register your credentials with these service principals.</span></span> <span data-ttu-id="f2aae-119">これを行うには、最初に .CER ファイルとして保存されている X.509 Base64 を入手する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f2aae-119">In order to do this, you must first obtain an X.509 Base64 saved as a .CER file.</span></span> <span data-ttu-id="f2aae-120">この証明書は、Office 365 のサービス ・ プリンシパルに適用されます。</span><span class="sxs-lookup"><span data-stu-id="f2aae-120">This certificate will then be applied to the Office 365 service principals.</span></span>
  
<span data-ttu-id="f2aae-121">X.509 証明書を取得したときは、Microsoft Online Services モジュールを起動 ([**スタート**] ボタン、[**すべてのプログラム**] をクリックして、 **Microsoft Online Services**] をクリックし、 **Microsoft Online Services モジュールの Windows をクリックし、PowerShell**)。</span><span class="sxs-lookup"><span data-stu-id="f2aae-121">When you have obtained the X.509 certificate, start the Microsoft Online Services Module (click **Start**, click **All Programs**, click **Microsoft Online Services**, and then click **Microsoft Online Services Module for Windows PowerShell**).</span></span> <span data-ttu-id="f2aae-122">サービス モジュールを開くと後、は、サービス ・ プリンシパルを管理するために使用できるコマンドレットが含まれている Microsoft オンラインの Windows PowerShell モジュールをインポートするのには、次を入力します。</span><span class="sxs-lookup"><span data-stu-id="f2aae-122">After the Services Module opens, type the following to import the Microsoft Online Windows PowerShell module containing the cmdlets that can be used to manage service principals:</span></span>
  
```
Import-Module MSOnlineExtended
```

<span data-ttu-id="f2aae-123">モジュールがインポートされるは、次のコマンドを入力し、Office 365 に接続するために ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="f2aae-123">When the module has been imported, type the following command and then press ENTER in order to connect to Office 365:</span></span>
  
```
Connect-MsolService
```

<span data-ttu-id="f2aae-124">Enter キーを押すと、資格情報ダイアログ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f2aae-124">After you press ENTER, a credentials dialog box will appear.</span></span> <span data-ttu-id="f2aae-125">] ダイアログ ボックスで、Office 365 のユーザー名とパスワードを入力し、し、[OK] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f2aae-125">Enter your Office 365 user name and password in the dialog box, and then click OK.</span></span>
  
<span data-ttu-id="f2aae-126">Office 365 に接続するいるとすぐにし、サービス ・ プリンシパルに関する情報を取得するために次のコマンドを実行できます。</span><span class="sxs-lookup"><span data-stu-id="f2aae-126">As soon as you are connected to Office 365, you can then run the following command in order to return information about your service principals:</span></span>
  
```
Get-MsolServicePrincipal
```

<span data-ttu-id="f2aae-127">すべてのサービス プリンシパルについて次のような情報が返されます。</span><span class="sxs-lookup"><span data-stu-id="f2aae-127">You should get back information similar to this for all your service principals:</span></span>
  
```
ExtensionData        : System.Runtime.Serialization.ExtensionDataObject
AccountEnabled       : True
Addresses            : {}
AppPrincipalId       : 00000004-0000-0ff1-ce00-000000000000
DisplayName          : Skype for Business Server
ObjectId             : aada5fbd-c0ae-442a-8c0b-36fec40602e2
ServicePrincipalName : SkypeForBusinessServer/litwareinc.com
TrustedForDelegation : True
```

<span data-ttu-id="f2aae-128">次の手順は、X.509 証明書のインポート、エンコード、および割り当てです。</span><span class="sxs-lookup"><span data-stu-id="f2aae-128">The next step is to import, encode, and assign the X.509 certificate.</span></span> <span data-ttu-id="f2aae-129">インポートと証明書のエンコード、ファイルの完全なパスを指定することを確認する、次の Windows PowerShell コマンドを使用して、します。CER ファイル インポート メソッドを呼び出すとします。</span><span class="sxs-lookup"><span data-stu-id="f2aae-129">To import and encode the certificate, use the following Windows PowerShell commands, being sure to specify the complete file path to your .CER file when you call the Import method:</span></span>
  
```
$certificate = New-Object System.Security.Cryptography.X509Certificates.X509Certificate
$certificate.Import("C:\Certificates\Office365.cer")
$binaryValue = $certificate.GetRawCertData()
$credentialsValue = [System.Convert]::ToBase64String($binaryValue)
```

<span data-ttu-id="f2aae-130">証明書をインポートし、エンコードされたが後、は、Office 365 のサービス ・ プリンシパルをし証明書を割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="f2aae-130">After the certificate has been imported and encoded, you can then assign the certificate to your Office 365 service principals.</span></span> <span data-ttu-id="f2aae-131">Business Server の Skype とは Microsoft Exchange のサービス ・ プリンシパルの両方の AppPrincipalId プロパティの値を取得するために最初に取得-MsolServicePrincipal を使用します。AppPrincipalId プロパティの値は、証明書を割り当てられているサービス ・ プリンシパルを識別するのには適用されます。</span><span class="sxs-lookup"><span data-stu-id="f2aae-131">To do that, first use the Get-MsolServicePrincipal to retrieve the value of the AppPrincipalId property for both the Skype for Business Server and the Microsoft Exchange service principals; the value of the AppPrincipalId property will be used to identify the service principal being assigned the certificate.</span></span> <span data-ttu-id="f2aae-132">AppPrincipalId プロパティ値の Skype のビジネス サーバー 2015 に対し、Skype の Office 365 バージョンにビジネスのサーバーの証明書を割り当てるには次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="f2aae-132">With the AppPrincipalId property value for Skype for Business Server 2015 in hand, use the following command to assign the certificate to the Office 365 version of Skype for Business Server:</span></span>
  
```
New-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -Type Asymmetric -Usage Verify -Value $credentialsValue 
```

<span data-ttu-id="f2aae-133">必要がありますし、コマンドを繰り返し実行、Exchange 2013 の AppPrincipalId プロパティの値を使用してこの時間です。</span><span class="sxs-lookup"><span data-stu-id="f2aae-133">You should then repeat the command, this time using the AppPrincipalId property value for Exchange 2013.</span></span>
  
<span data-ttu-id="f2aae-134">後でその証明書の削除が必要になった場合は、最初に証明書の KeyId を取得することで削除できます。</span><span class="sxs-lookup"><span data-stu-id="f2aae-134">If you later need to delete that certificate, you can do so by first retrieving the KeyId for the certificate:</span></span>
  
```
Get-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000
```

<span data-ttu-id="f2aae-135">そのコマンドは、次のようなデータを返します。</span><span class="sxs-lookup"><span data-stu-id="f2aae-135">That command will return data like this one:</span></span>
  
```
Type      : Asymmetric
Value     : 
KeyId     : bc2795f3-2387-4543-a95d-f92c85c7a1b0
StartDate : 6/1/2012 8:00:00 AM
EndDate   : 5/31/2013 8:00:00 AM
Usage     : Verify
```

<span data-ttu-id="f2aae-136">続いて、次のようなコマンドを使用して証明書を削除できます。</span><span class="sxs-lookup"><span data-stu-id="f2aae-136">You can then delete the certificate by using a command similar to this:</span></span>
  
```
Remove-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -KeyId bc2795f3-2387-4543-a95d-f92c85c7a1b0
```

<span data-ttu-id="f2aae-137">証明書を割り当てるだけでなくも Exchange のオンライン サービス主体を構成し、Office 365 のサービス主体と外部の Web サービスの Url をビジネス サーバー 2015 の Skype の設置型バージョンを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f2aae-137">In addition to assigning a certificate, you must also configure the Exchange Online Service Principal and configure your on-premises version of Skype for Business Server 2015 external Web services URLs as an Office 365 service principal.</span></span> <span data-ttu-id="f2aae-138">これを行うには、次の 2 つのコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="f2aae-138">That can be done by carrying out the following two commands.</span></span> 
  
<span data-ttu-id="f2aae-139">次の例では、lync.contoso.com は、Skype のビジネス サーバー プールの外部 Web サービスの URL です。</span><span class="sxs-lookup"><span data-stu-id="f2aae-139">In the following example, lync.contoso.com is the external Web services URL for the Skype for Business Server pool.</span></span> <span data-ttu-id="f2aae-140">展開内のすべての外部 Web サービスの Url を追加するのには次の手順を繰り返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="f2aae-140">You should repeat these steps to add all the external Web services URLs in the deployment.</span></span>
  
```
Set-MSOLServicePrincipal -AppPrincipalID 00000002-0000-0ff1-ce00-000000000000 -AccountEnabled $true

$lyncSP = Get-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000
$lyncSP.ServicePrincipalNames.Add("00000004-0000-0ff1-ce00-000000000000/lync.contoso.com")
Set-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $lyncSP.ServicePrincipalNames
```