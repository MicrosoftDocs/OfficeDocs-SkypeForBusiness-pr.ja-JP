---
title: 'Lync Server 2013: クロスプレミス環境での Lync Server の構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Microsoft Lync Server 2013 in a cross-premises environment
ms:assetid: 700639ec-5264-4449-a8a6-d7386fad8719
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204990(v=OCS.15)
ms:contentKeyID: 48184449
ms.date: 02/21/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6f6399185e045afb56231550abc33ab514db0d04
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48517390"
---
# <a name="configuring-microsoft-lync-server-2013-in-a-cross-premises-environment"></a>クロスプレミス環境での Microsoft Lync Server 2013 の構成

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2017-02-21_

クロスプレミス構成では、一部のユーザーは Microsoft Lync Server 2013 のオンプレミスインストールに所属し、他のユーザーは Lync Server の Microsoft 365 または Office 365 バージョンに所属しています。 クロスプレミス環境でサーバー間認証を構成するには、まず、Microsoft 365 承認サーバーを信頼するように Lync Server 2013 の社内インストールを構成する必要があります。 このプロセスの最初の手順は、次の Lync Server 管理シェルスクリプトを実行することによって実行できます。

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

通常、テナントの領域名は組織名と異なることに注意してください。実際には、領域名はほぼ常にテナント ID と同じです。このため、スクリプトの最初の行を使用して、指定したテナント (この場合は fabrikam.com) の TenantId プロパティの値を取得してから、名前を変数 $TenantId に割り当てます。

    $TenantID = (Get-CsTenant -DisplayName "Fabrikam.com").TenantId

スクリプトが完了したら、Lync Server 2013 と承認サーバー間の信頼関係と、Exchange 2013 と承認サーバー間の2つ目の信頼関係を構成する必要があります。 これは、Microsoft Online Services コマンドレットを使用してのみ行うことができます。

<div>


> [!NOTE]  
> Microsoft Online Services コマンドレットをインストールしていない場合は、先に進む前に 2 つの作業を行う必要があります。 最初に、64 ビット バージョンの Microsoft Online Services サインイン アシスタントをダウンロードしてインストールします。 インストールが完了したら、Windows PowerShell 用 Microsoft Online Services モジュールの64ビット版をダウンロードしてインストールします。 Microsoft Online Services モジュールのインストールおよび使用方法の詳細については、「Microsoft 365 または Office 365 web サイト」を参照してください。 これらの手順では、Microsoft 365 または Office 36 と Active Directory との間でシングルサインオン、フェデレーション、および同期を構成する方法についても説明します。<BR>これらのコマンドレットをインストールしていない場合、Get-CsTenant コマンドレットを使用できないため、スクリプトは失敗します。



</div>

Microsoft 365 を構成した後、Lync Server 2013 および Exchange 2013 に対して Microsoft 365 または Office 365 サービスプリンシパルを作成した後、これらのサービスプリンシパルで資格情報を登録する必要があります。 これを行うには、最初に .CER ファイルとして保存されている X.509 Base64 を入手する必要があります。 この証明書は、Microsoft 365 または Office 365 のサービスプリンシパルに適用されます。

X.509 証明書を取得したら、Microsoft Online Services モジュールを起動します ([ **スタート**]、[ **すべてのプログラム**]、[ **microsoft Online Services**]、[ **microsoft online services モジュール for Windows PowerShell**] の順にクリックします)。 サービスモジュールが開いたら、次のコマンドを入力して、サービスプリンシパルの管理に使用できるコマンドレットを含む Microsoft Online Windows PowerShell モジュールをインポートします。

    Import-Module MSOnlineExtended

モジュールがインポートされたら、次のコマンドを入力し、ENTER キーを押して Microsoft 365 に接続します。

    Connect-MsolService

Enter キーを押すと、資格情報ダイアログ ボックスが表示されます。 ダイアログボックスに Microsoft 365 または Office 365 のユーザー名とパスワードを入力し、[OK] をクリックします。

Microsoft 365 に接続した直後に、次のコマンドを実行してサービスプリンシパルに関する情報を戻すことができます。

    Get-MsolServicePrincipal

すべてのサービス プリンシパルについて次のような情報が返されます。

    ExtensionData        : System.Runtime.Serialization.ExtensionDataObject
    AccountEnabled       : True
    Addresses            : {}
    AppPrincipalId       : 00000004-0000-0ff1-ce00-000000000000
    DisplayName          : Microsoft Lync Server
    ObjectId             : aada5fbd-c0ae-442a-8c0b-36fec40602e2
    ServicePrincipalName : LyncServer/litwareinc.com
    TrustedForDelegation : True

次の手順は、X.509 証明書のインポート、エンコード、および割り当てです。 証明書をインポートおよびエンコードするには、次の Windows PowerShell コマンドを使用します。これには、の完全なファイルパスを指定してください。CER ファイルを使用して、Import メソッドを呼び出します。

    $certificate = New-Object System.Security.Cryptography.X509Certificates.X509Certificate
    $certificate.Import("C:\Certificates\Office365.cer")
    $binaryValue = $certificate.GetRawCertData()
    $credentialsValue = [System.Convert]::ToBase64String($binaryValue)

証明書をインポートしてエンコードした後、証明書を Microsoft 365 サービスプリンシパルに割り当てることができます。 そのためには、まず、Get-MsolServicePrincipal を使用して、Lync Server と Microsoft Exchange サービスプリンシパルの AppPrincipalId プロパティの値を取得します。AppPrincipalId プロパティの値は、証明書を割り当てられているサービスプリンシパルを識別するために使用されます。 Lync Server 2013 の AppPrincipalId プロパティの値を使用して、次のコマンドを使用して、Microsoft 365 バージョンの Lync Server に証明書を割り当てます (StartDate プロパティと EndDate プロパティは、証明書の有効期間に対応している必要があります)。

    New-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -Type Asymmetric -Usage Verify -Value $credentialsValue -StartDate 6/1/2012 -EndDate 5/31/2013

その後、このコマンドを繰り返し実行します。このとき、Exchange 2013 の AppPrincipalId プロパティの値を使用します。

後でその証明書の削除が必要になった場合は、最初に証明書の KeyId を取得することで削除できます。

    Get-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000

そのコマンドは、次のようなデータを返します。

    Type      : Asymmetric
    Value     : 
    KeyId     : bc2795f3-2387-4543-a95d-f92c85c7a1b0
    StartDate : 6/1/2012 8:00:00 AM
    EndDate   : 5/31/2013 8:00:00 AM
    Usage     : Verify

続いて、次のようなコマンドを使用して証明書を削除できます。

    Remove-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -KeyId bc2795f3-2387-4543-a95d-f92c85c7a1b0

証明書の割り当てに加えて、社内バージョンの Lync Server 2013 のサーバープリンシパル名を追加して、Exchange Online の Microsoft 365 サービスプリンシパルを構成する必要もあります。 これを行うには、Microsoft Online Services PowerShell セッションで次の4つの行を実行します。

    Set-MSOLServicePrincipal -AppPrincipalID 00000002-0000-0ff1-ce00-000000000000 -AccountEnabled $true
    
    $lyncSP = Get-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000
    $lyncSP.ServicePrincipalNames.Add("00000004-0000-0ff1-ce00-000000000000/lync.contoso.com")
    Set-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $lyncSP.ServicePrincipalNames

</div>

<span> </span>

</div>

</div>

</div>

