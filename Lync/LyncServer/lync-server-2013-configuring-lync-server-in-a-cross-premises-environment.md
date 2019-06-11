---
title: 'Lync Server 2013: クロスプレミス環境での Lync Server の構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Microsoft Lync Server 2013 in a cross-premises environment
ms:assetid: 700639ec-5264-4449-a8a6-d7386fad8719
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204990(v=OCS.15)
ms:contentKeyID: 48184449
ms.date: 02/21/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 44a47dc3bf3c832819fe431cb0177bfc1a03f330
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840237"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-microsoft-lync-server-2013-in-a-cross-premises-environment"></a><span data-ttu-id="8f319-102">クロスプレミス環境で Microsoft Lync Server 2013 を構成する</span><span class="sxs-lookup"><span data-stu-id="8f319-102">Configuring Microsoft Lync Server 2013 in a cross-premises environment</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8f319-103">_**最終更新日:** 2017-02-21_</span><span class="sxs-lookup"><span data-stu-id="8f319-103">_**Topic Last Modified:** 2017-02-21_</span></span>

<span data-ttu-id="8f319-104">クロスオフィス構成では、他のユーザーが Office 365 バージョンの Lync Server を使用しているときに、一部のユーザーが Microsoft Lync Server 2013 のオンプレミスインストールをホームとしています。</span><span class="sxs-lookup"><span data-stu-id="8f319-104">In a cross-premise configuration, some of your users are homed on an on-premises installation of Microsoft Lync Server 2013 while other users are homed on the Office 365 version of Lync Server.</span></span> <span data-ttu-id="8f319-105">クロスプレミス環境でサーバー間認証を構成するには、まず、Office 365 承認サーバーを信頼するように Lync Server 2013 のオンプレミスインストールを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8f319-105">In order to configure server-to-server authentication in a cross-premises environment, you must first configure your on-premises installation of Lync Server 2013 to trust the Office 365 Authorization server.</span></span> <span data-ttu-id="8f319-106">このプロセスの最初の手順は、次の Lync Server 管理シェルスクリプトを実行して実行できます。</span><span class="sxs-lookup"><span data-stu-id="8f319-106">The initial step in this process can be carried out by running the following Lync Server Management Shell script:</span></span>

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

<span data-ttu-id="8f319-p102">通常、テナントの領域名は組織名と異なることに注意してください。実際には、領域名はほぼ常にテナント ID と同じです。このため、スクリプトの最初の行を使用して、指定したテナント (この場合は fabrikam.com) の TenantId プロパティの値を取得してから、名前を変数 $TenantId に割り当てます。</span><span class="sxs-lookup"><span data-stu-id="8f319-p102">Keep in mind that the realm name for a tenant is typically different than the organization name; in fact, the realm name is almost always the same as the tenant ID. Because of that, the first line in the script is used to return the value of the TenantId property for the specified tenant (in this case, fabrikam.com) and then assign that name to the variable $TenantId:</span></span>

    $TenantID = (Get-CsTenant -DisplayName "Fabrikam.com").TenantId

<span data-ttu-id="8f319-109">スクリプトが完了したら、Lync Server 2013 と承認サーバー間の信頼関係と、Exchange 2013 と承認サーバーの間の2番目の信頼関係を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8f319-109">After the script completes you must then configure a trust relationship between Lync Server 2013 and the authorization server, and a second trust relationship between Exchange 2013 and the authorization server.</span></span> <span data-ttu-id="8f319-110">これは、Microsoft Online Services コマンドレットを使用してのみ行うことができます。</span><span class="sxs-lookup"><span data-stu-id="8f319-110">This can only be done by using the Microsoft Online Services cmdlets.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8f319-111">Microsoft オンラインサービスのコマンドレットをインストールしていない場合は、続行する前に2つの操作を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="8f319-111">If you have not installed the Microsoft Online Services cmdlets you will need to do two things before proceeding.</span></span> <span data-ttu-id="8f319-112">最初に、64 ビット バージョンの Microsoft Online Services サインイン アシスタントをダウンロードしてインストールします。</span><span class="sxs-lookup"><span data-stu-id="8f319-112">First, download and install the 64-bit version of the Microsoft Online Services Sign-in Assistant.</span></span> <span data-ttu-id="8f319-113">インストールが完了したら、Windows PowerShell 用 Microsoft Online Services モジュールの64ビットバージョンをダウンロードしてインストールします。</span><span class="sxs-lookup"><span data-stu-id="8f319-113">After installation is complete, download and install the 64-bit version of the Microsoft Online Services Module for Windows PowerShell.</span></span> <span data-ttu-id="8f319-114">Microsoft Online Services モジュールのインストールと使用の詳細については、Office 365 web サイトを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8f319-114">Detailed information for installing and using the Microsoft Online Services Module can be found on the Office 365 web site.</span></span> <span data-ttu-id="8f319-115">この手順では、Office 365 と Active Directory の間でシングルサインオン、フェデレーション、同期を構成する方法についても説明します。</span><span class="sxs-lookup"><span data-stu-id="8f319-115">These instructions will also tell you how to configure single sign-on, federation, and synchronization between Office 365 and Active Directory.</span></span><BR><span data-ttu-id="8f319-116">これらのコマンドレットがインストールされていない場合、Get-CsTenant コマンドレットを使用できないためにスクリプトは失敗します。</span><span class="sxs-lookup"><span data-stu-id="8f319-116">If you have not installed these cmdlets your script will fail because the Get-CsTenant cmdlet will not be available.</span></span>



</div>

<span data-ttu-id="8f319-117">Office 365 を構成して、Lync Server 2013 および Exchange 2013 の Office 365 サービスプリンシパルを作成した後、これらのサービスプリンシパルに資格情報を登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8f319-117">After you have configured Office 365, and after you have created Office 365 service principals for Lync Server 2013 and Exchange 2013, you will then need to register your credentials with these service principals.</span></span> <span data-ttu-id="8f319-118">これを行うには、最初に .CER ファイルとして保存されている X.509 Base64 を入手する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8f319-118">In order to do this, you must first obtain an X.509 Base64 saved as a .CER file.</span></span> <span data-ttu-id="8f319-119">この証明書は、Office 365 サービスプリンシパルに適用されます。</span><span class="sxs-lookup"><span data-stu-id="8f319-119">This certificate will then be applied to the Office 365 service principals.</span></span>

<span data-ttu-id="8f319-120">X.509 証明書を取得したら、Microsoft Online Services モジュールを起動し ([**スタート**]、[**すべてのプログラム**]、[ **microsoft オンラインサービス**]、[ **microsoft オンラインサービスモジュール] の順にクリックします)PowerShell**)。</span><span class="sxs-lookup"><span data-stu-id="8f319-120">When you have obtained the X.509 certificate, start the Microsoft Online Services Module (click **Start**, click **All Programs**, click **Microsoft Online Services**, and then click **Microsoft Online Services Module for Windows PowerShell**).</span></span> <span data-ttu-id="8f319-121">サービスモジュールが開いたら、次のように入力して、サービスプリンシパルを管理するために使用できるコマンドレットが含まれている Microsoft Online Windows PowerShell モジュールをインポートします。</span><span class="sxs-lookup"><span data-stu-id="8f319-121">After the Services Module opens, type the following to import the Microsoft Online Windows PowerShell module containing the cmdlets that can be used to manage service principals:</span></span>

    Import-Module MSOnlineExtended

<span data-ttu-id="8f319-122">モジュールがインポートされたら、次のコマンドを入力し、ENTER キーを押して Office 365 に接続します。</span><span class="sxs-lookup"><span data-stu-id="8f319-122">When the module has been imported, type the following command and then press ENTER in order to connect to Office 365:</span></span>

    Connect-MsolService

<span data-ttu-id="8f319-123">Enter キーを押すと、資格情報ダイアログ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8f319-123">After you press ENTER, a credentials dialog box will appear.</span></span> <span data-ttu-id="8f319-124">ダイアログボックスに Office 365 のユーザー名とパスワードを入力して、[OK] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8f319-124">Enter your Office 365 user name and password in the dialog box, and then click OK.</span></span>

<span data-ttu-id="8f319-125">Office 365 に接続したら、次のコマンドを実行して、サービスプリンシパルに関する情報を返すことができます。</span><span class="sxs-lookup"><span data-stu-id="8f319-125">As soon as you are connected to Office 365 you can then run the following command in order to return information about your service principals:</span></span>

    Get-MsolServicePrincipal

<span data-ttu-id="8f319-126">すべてのサービス プリンシパルについて次のような情報が返されます。</span><span class="sxs-lookup"><span data-stu-id="8f319-126">You should get back information similar to this for all your service principals:</span></span>

    ExtensionData        : System.Runtime.Serialization.ExtensionDataObject
    AccountEnabled       : True
    Addresses            : {}
    AppPrincipalId       : 00000004-0000-0ff1-ce00-000000000000
    DisplayName          : Microsoft Lync Server
    ObjectId             : aada5fbd-c0ae-442a-8c0b-36fec40602e2
    ServicePrincipalName : LyncServer/litwareinc.com
    TrustedForDelegation : True

<span data-ttu-id="8f319-127">次の手順は、X.509 証明書のインポート、エンコード、および割り当てです。</span><span class="sxs-lookup"><span data-stu-id="8f319-127">The next step is to import, encode, and assign the X.509 certificate.</span></span> <span data-ttu-id="8f319-128">証明書をインポートしてエンコードするには、次の Windows PowerShell コマンドを使用します。そのための完全なファイルパスを指定していることを確認します。インポートメソッドを呼び出すときの CER ファイル:</span><span class="sxs-lookup"><span data-stu-id="8f319-128">To import and encode the certificate, use the following Windows PowerShell commands, being sure to specify the complete file path to your .CER file when you call the Import method:</span></span>

    $certificate = New-Object System.Security.Cryptography.X509Certificates.X509Certificate
    $certificate.Import("C:\Certificates\Office365.cer")
    $binaryValue = $certificate.GetRawCertData()
    $credentialsValue = [System.Convert]::ToBase64String($binaryValue)

<span data-ttu-id="8f319-129">証明書をインポートしてエンコードした後で、その証明書を Office 365 のサービスプリンシパルに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="8f319-129">After the certificate has been imported and encoded, you can then assign the certificate to your Office 365 service principals.</span></span> <span data-ttu-id="8f319-130">そのためには、最初に MsolServicePrincipal を使用して、Lync Server と Microsoft Exchange のサービスプリンシパルのた appprincipalid プロパティの値を取得します。た appprincipalid プロパティの値は、証明書を割り当てられているサービスプリンシパルを識別するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="8f319-130">To do that, first use the Get-MsolServicePrincipal to retrieve the value of the AppPrincipalId property for both the Lync Server and the Microsoft Exchange service principals; the value of the AppPrincipalId property will be used to identify the service principal being assigned the certificate.</span></span> <span data-ttu-id="8f319-131">Lync Server 2013 のた appprincipalid プロパティ値を使って、次のコマンドを使用して、Office 365 バージョンの Lync Server に証明書を割り当てます (StartDate プロパティと EndDate プロパティは、証明書の有効期間に対応する必要があります)。</span><span class="sxs-lookup"><span data-stu-id="8f319-131">With the AppPrincipalId property value for Lync Server 2013 in hand, use the following command to assign the certificate to the Office 365 version of Lync Server (the StartDate and EndDate properties should correspond to the validity period for the certificate):</span></span>

    New-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -Type Asymmetric -Usage Verify -Value $credentialsValue -StartDate 6/1/2012 -EndDate 5/31/2013

<span data-ttu-id="8f319-132">今回は、このコマンドを Exchange 2013 のた appprincipalid プロパティの値を使って実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8f319-132">You should then repeat the command, this time using the AppPrincipalId property value for Exchange 2013.</span></span>

<span data-ttu-id="8f319-133">後でその証明書の削除が必要になった場合は、最初に証明書の KeyId を取得することで削除できます。</span><span class="sxs-lookup"><span data-stu-id="8f319-133">If you later need to delete that certificate, you can do so by first retrieving the KeyId for the certificate:</span></span>

    Get-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000

<span data-ttu-id="8f319-134">そのコマンドは、次のようなデータを返します。</span><span class="sxs-lookup"><span data-stu-id="8f319-134">That command will return data like this one:</span></span>

    Type      : Asymmetric
    Value     : 
    KeyId     : bc2795f3-2387-4543-a95d-f92c85c7a1b0
    StartDate : 6/1/2012 8:00:00 AM
    EndDate   : 5/31/2013 8:00:00 AM
    Usage     : Verify

<span data-ttu-id="8f319-135">続いて、次のようなコマンドを使用して証明書を削除できます。</span><span class="sxs-lookup"><span data-stu-id="8f319-135">You can then delete the certificate by using a command similar to this:</span></span>

    Remove-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -KeyId bc2795f3-2387-4543-a95d-f92c85c7a1b0

<span data-ttu-id="8f319-136">証明書の割り当てに加えて、オンプレミスバージョンの Lync Server 2013 のサーバープリンシパル名を追加して、Exchange Online の Office 365 サービスプリンシパルを構成する必要もあります。</span><span class="sxs-lookup"><span data-stu-id="8f319-136">In addition to assigning a certificate you must also configure the Office 365 Service Principal for Exchange Online by adding the Server Principal Name for your on-premise version of Lync Server 2013.</span></span> <span data-ttu-id="8f319-137">これを行うには、Microsoft Online Services PowerShell セッションで次の4行を実行します。</span><span class="sxs-lookup"><span data-stu-id="8f319-137">This can be done by running the following four lines in a Microsoft Online Services PowerShell session:</span></span>

    Set-MSOLServicePrincipal -AppPrincipalID 00000002-0000-0ff1-ce00-000000000000 -AccountEnabled $true
    
    $lyncSP = Get-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000
    $lyncSP.ServicePrincipalNames.Add("00000004-0000-0ff1-ce00-000000000000/lync.contoso.com")
    Set-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $lyncSP.ServicePrincipalNames

</div>

<span> </span>

</div>

</div>

</div>

