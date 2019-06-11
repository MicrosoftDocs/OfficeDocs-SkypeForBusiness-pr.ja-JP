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

# <a name="configuring-microsoft-lync-server-2013-in-a-cross-premises-environment"></a>クロスプレミス環境で Microsoft Lync Server 2013 を構成する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2017-02-21_

クロスオフィス構成では、他のユーザーが Office 365 バージョンの Lync Server を使用しているときに、一部のユーザーが Microsoft Lync Server 2013 のオンプレミスインストールをホームとしています。 クロスプレミス環境でサーバー間認証を構成するには、まず、Office 365 承認サーバーを信頼するように Lync Server 2013 のオンプレミスインストールを構成する必要があります。 このプロセスの最初の手順は、次の Lync Server 管理シェルスクリプトを実行して実行できます。

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

スクリプトが完了したら、Lync Server 2013 と承認サーバー間の信頼関係と、Exchange 2013 と承認サーバーの間の2番目の信頼関係を構成する必要があります。 これは、Microsoft Online Services コマンドレットを使用してのみ行うことができます。

<div>


> [!NOTE]  
> Microsoft オンラインサービスのコマンドレットをインストールしていない場合は、続行する前に2つの操作を行う必要があります。 最初に、64 ビット バージョンの Microsoft Online Services サインイン アシスタントをダウンロードしてインストールします。 インストールが完了したら、Windows PowerShell 用 Microsoft Online Services モジュールの64ビットバージョンをダウンロードしてインストールします。 Microsoft Online Services モジュールのインストールと使用の詳細については、Office 365 web サイトを参照してください。 この手順では、Office 365 と Active Directory の間でシングルサインオン、フェデレーション、同期を構成する方法についても説明します。<BR>これらのコマンドレットがインストールされていない場合、Get-CsTenant コマンドレットを使用できないためにスクリプトは失敗します。



</div>

Office 365 を構成して、Lync Server 2013 および Exchange 2013 の Office 365 サービスプリンシパルを作成した後、これらのサービスプリンシパルに資格情報を登録する必要があります。 これを行うには、最初に .CER ファイルとして保存されている X.509 Base64 を入手する必要があります。 この証明書は、Office 365 サービスプリンシパルに適用されます。

X.509 証明書を取得したら、Microsoft Online Services モジュールを起動し ([**スタート**]、[**すべてのプログラム**]、[ **microsoft オンラインサービス**]、[ **microsoft オンラインサービスモジュール] の順にクリックします)PowerShell**)。 サービスモジュールが開いたら、次のように入力して、サービスプリンシパルを管理するために使用できるコマンドレットが含まれている Microsoft Online Windows PowerShell モジュールをインポートします。

    Import-Module MSOnlineExtended

モジュールがインポートされたら、次のコマンドを入力し、ENTER キーを押して Office 365 に接続します。

    Connect-MsolService

Enter キーを押すと、資格情報ダイアログ ボックスが表示されます。 ダイアログボックスに Office 365 のユーザー名とパスワードを入力して、[OK] をクリックします。

Office 365 に接続したら、次のコマンドを実行して、サービスプリンシパルに関する情報を返すことができます。

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

次の手順は、X.509 証明書のインポート、エンコード、および割り当てです。 証明書をインポートしてエンコードするには、次の Windows PowerShell コマンドを使用します。そのための完全なファイルパスを指定していることを確認します。インポートメソッドを呼び出すときの CER ファイル:

    $certificate = New-Object System.Security.Cryptography.X509Certificates.X509Certificate
    $certificate.Import("C:\Certificates\Office365.cer")
    $binaryValue = $certificate.GetRawCertData()
    $credentialsValue = [System.Convert]::ToBase64String($binaryValue)

証明書をインポートしてエンコードした後で、その証明書を Office 365 のサービスプリンシパルに割り当てることができます。 そのためには、最初に MsolServicePrincipal を使用して、Lync Server と Microsoft Exchange のサービスプリンシパルのた appprincipalid プロパティの値を取得します。た appprincipalid プロパティの値は、証明書を割り当てられているサービスプリンシパルを識別するために使用されます。 Lync Server 2013 のた appprincipalid プロパティ値を使って、次のコマンドを使用して、Office 365 バージョンの Lync Server に証明書を割り当てます (StartDate プロパティと EndDate プロパティは、証明書の有効期間に対応する必要があります)。

    New-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -Type Asymmetric -Usage Verify -Value $credentialsValue -StartDate 6/1/2012 -EndDate 5/31/2013

今回は、このコマンドを Exchange 2013 のた appprincipalid プロパティの値を使って実行する必要があります。

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

証明書の割り当てに加えて、オンプレミスバージョンの Lync Server 2013 のサーバープリンシパル名を追加して、Exchange Online の Office 365 サービスプリンシパルを構成する必要もあります。 これを行うには、Microsoft Online Services PowerShell セッションで次の4行を実行します。

    Set-MSOLServicePrincipal -AppPrincipalID 00000002-0000-0ff1-ce00-000000000000 -AccountEnabled $true
    
    $lyncSP = Get-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000
    $lyncSP.ServicePrincipalNames.Add("00000004-0000-0ff1-ce00-000000000000/lync.contoso.com")
    Set-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $lyncSP.ServicePrincipalNames

</div>

<span> </span>

</div>

</div>

</div>

