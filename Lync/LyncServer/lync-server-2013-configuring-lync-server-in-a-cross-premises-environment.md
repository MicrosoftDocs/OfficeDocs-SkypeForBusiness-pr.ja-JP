---
title: クロスプレミス環境での Microsoft Lync Server 2013 の構成
TOCTitle: クロスプレミス環境での Microsoft Lync Server 2013 の構成
ms:assetid: 700639ec-5264-4449-a8a6-d7386fad8719
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ204990(v=OCS.15)
ms:contentKeyID: 48272427
ms.date: 02/21/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# クロスプレミス環境での Microsoft Lync Server 2013 の構成

 

_**トピックの最終更新日:** 2017-02-21_

横断設置型構成では、一部のユーザーが Microsoft Lync Server 2013 の社内インストールに所属し、他のユーザーが Lync Server の Office 365 バージョンに所属します。横断設置型環境でサーバー間認証を構成するには、最初に Office 365 承認サーバーを信頼するように Lync Server 2013 の社内インストールを構成する必要があります。このプロセスの初期手順は、次の Lync Server 管理シェル スクリプトを実行することで実行できます。

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

スクリプトが完了したら、Lync Server 2013 と承認サーバー間の信頼関係と、Exchange 2013 と承認サーバー間の 2 つ目の信頼関係を構成する必要があります。これは、Microsoft Online Services コマンドレットを使用してのみ行うことができます。

> [!NOTE]
> Microsoft Online Services コマンドレットをインストールしていない場合は、先に進む前に 2 つの作業を行う必要があります。最初に、64 ビット バージョンの Microsoft Online Services サインイン アシスタントをダウンロードしてインストールします。インストールの完了後に、64 ビット バージョンの Windows PowerShell 用 Microsoft Online Services モジュールをダウンロードしてインストールします。Microsoft Online Services モジュールのインストールと使用の詳細については、Office 365 Web サイトを参照してください。これらの説明では、Office 365 と Active Directory 間のシングル サインオン、フェデレーション、および同期の構成方法も説明されます。<br />
> これらのコマンドレットがインストールされていない場合、Get-CsTenant コマンドレットを使用できないためにスクリプトは失敗します。


Office 365 を構成し、Lync Server 2013 と Exchange 2013 に対して Office 365 サービス プリンシパルを作成した後で、これらのサービス プリンシパルに資格情報を登録する必要があります。これを行うには、最初に .CER ファイルとして保存されている X.509 Base64 を入手する必要があります。この証明書が Office 365 サービス プリンシパルに適用されます。

X.509 証明書を入手したら、Microsoft Online Services モジュールを開始します (\[**スタート**\]、\[**すべてのプログラム**\]、\[**Microsoft Online Services**\]、\[**Windows PowerShell 用 Microsoft Online Services モジュール**\] の順にクリックします)。Services モジュールが開いたら、次のように入力して、サービス プリンシパルの管理に使用できるコマンドレットを含む Microsoft Online Windows PowerShell モジュールをインポートします。

    Import-Module MSOnlineExtended

モジュールがインポートされたら、次のコマンドを入力し、Enter キーを押して Office 365 に接続します。

    Connect-MsolService

Enter キーを押すと、資格情報ダイアログ ボックスが表示されます。ダイアログ ボックスに Office 365 ユーザー名とパスワードを入力し、\[OK\] をクリックします。

Office 365 に接続するとすぐに、次のコマンドを実行して、サービス プリンシパルに関する情報を取得できます。

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

次の手順は、X.509 証明書のインポート、エンコード、および割り当てです。証明書をインポートおよびエンコードするには、Import メソッドの呼び出し時に .CER ファイルの完全ファイル パスを指定して、次の Windows PowerShell コマンドを使用します。

    $certificate = New-Object System.Security.Cryptography.X509Certificates.X509Certificate
    $certificate.Import("C:\Certificates\Office365.cer")
    $binaryValue = $certificate.GetRawCertData()
    $credentialsValue = [System.Convert]::ToBase64String($binaryValue)

証明書がインポートおよびエンコードされたら、証明書を Office 365 サービス プリンシパルに割り当てることができます。これを行うには、最初に Get-MsolServicePrincipal を使用して、Lync Server と Microsoft Exchange 両方のサービス プリンシパルの AppPrincipalId プロパティの値を取得します。AppPrincipalId プロパティの値は、証明書に割り当てられるサービス プリンシパルの識別に使用されます。Lync Server 2013 の AppPrincipalId プロパティ値を手元に用意し、次のコマンドを使用して Lync Server の Office 365 バージョンに証明書を割り当てます (StartDate プロパティと EndDateプロパティは証明書の有効期間に対応している必要があります)。

    New-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -Type Asymmetric -Usage Verify -Value $credentialsValue -StartDate 6/1/2012 -EndDate 5/31/2013

次に、コマンドを繰り返す必要があります。今回は、Exchange 2013 の AppPrincipalId プロパティ値を使用します。

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

証明書の割り当てに加えて、Exchange Online サービス プリンシパルを構成し、Lync Server 2013 の社内バージョンを Office 365 サービス プリンシパルとして構成する必要もあります。これを行うには、次の 2 つのコマンドを実行します。

    Set-MSOLServicePrincipal -AppPrincipalID 00000002-0000-0ff1-ce00-000000000000 -AccountEnabled $true
    
    $lyncSP = Get-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000
    $lyncSP.ServicePrincipalNames.Add("00000004-0000-0ff1-ce00-000000000000/lync.contoso.com")
    Set-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $lyncSP.ServicePrincipalNames

