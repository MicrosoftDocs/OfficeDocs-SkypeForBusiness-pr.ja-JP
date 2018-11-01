---
title: Microsoft Lync Server 2013 の内部設置型パートナー アプリケーションの構成
TOCTitle: Microsoft Lync Server 2013 の内部設置型パートナー アプリケーションの構成
ms:assetid: 696f2b26-e5d0-42b5-9785-a26c2ce25bb7
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ204975(v=OCS.15)
ms:contentKeyID: 48272391
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Microsoft Lync Server 2013 の内部設置型パートナー アプリケーションの構成

 

_**トピックの最終更新日:** 2013-02-04_

OAuthTokenIssuer 証明書を割り当てた後、Microsoft Lync Server 2013 パートナー アプリケーションを構成する必要があります (説明する手順では、Microsoft Exchange Server 2013 と Microsoft SharePoint の両方がパートナー アプリケーションとして動作するように構成します) 。内部設置型パートナー アプリケーションを構成するには、次の Windows PowerShell スクリプトをコピーしてメモ帳 (またはその他のテキスト エディター) にコードを貼り付けることから始める必要があります。

    if ((Get-CsPartnerApplication -ErrorAction SilentlyContinue) -ne $Null)
       {
           Remove-CsPartnerApplication app
       }
    
    $exch = Get-CsPartnerApplication microsoft.exchange -ErrorAction SilentlyContinue
            
    if ($exch -eq $null)
       {
          New-CsPartnerApplication -Identity microsoft.exchange -MetadataUrl https://atl-exchange-001.litwareinc.com/autodiscover/metadata/json/1 -ApplicationTrustLevel Full 
        }
    else
        {
           if ($exch.ApplicationIdentifier -ne "00000002-0000-0ff1-ce00-000000000000")
              {
                 Remove-CsPartnerApplication microsoft.exchange
    New-CsPartnerApplication -Identity microsoft.exchange -MetadataUrl https://atl-exchange-001.litwareinc.com/autodiscover/metadata/json/1 -ApplicationTrustLevel Full 
               }
            else
               {
                 Set-CsPartnerApplication -Identity microsoft.exchange -ApplicationTrustLevel Full 
               }
         }
    
    $shp = Get-CsPartnerApplication microsoft.sharepoint -ErrorAction SilentlyContinue
            
    if ($shp -eq $null)
       {
          New-CsPartnerApplication -Identity microsoft.sharepoint -MetadataUrl http://atl-sharepoint-001.litwareinc.com/jsonmetadata.ashx -ApplicationTrustLevel Full 
        }
    else
        {
           if ($shp.ApplicationIdentifier -ne "00000003-0000-0ff1-ce00-000000000000")
              {
                 Remove-CsPartnerApplication microsoft.sharepoint
      
                 New-CsPartnerApplication -Identity microsoft.sharepoint -MetadataUrl http://atl-sharepoint-001.litwareinc.com/jsonmetadata.ashx -ApplicationTrustLevel Full 
               }
            else
               {
                 Set-CsPartnerApplication -Identity microsoft.sharepoint -ApplicationTrustLevel Full 
                }
       }
    
    Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000

コードをコピーした後、スクリプトを .PS1 ファイル拡張子を使用して保存します (例: C:\\Scripts\\ServerToServerAuth.ps1)。このスクリプトを実行する前に、メタデータ URL である https://atl-exchange-001.litwareinc.com/autodiscover/metadata/json/1 および http://atl-sharepoint-001.litwareinc.com/jsonmetadata.ashx を、それぞれユーザーの Exchange 2013 および SharePoint サーバーで使用されるメタデータ URL に置き換える必要があります。製品のメタデータ URL の識別方法については、Exchange 2013 および SharePoint の製品ドキュメントを参照してください。

このスクリプトの最後の行で、Set-CsOAuthConfiguration コマンドレットが次の構文で呼び出されます。

    Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000

Set-CsOAuthConfiguration を呼び出すときに Realm パラメーターが使用されなかったため、領域には組織の完全修飾ドメイン名 (FQDN) が自動的に設定されます (例: litwareinc.com)。領域名が組織名と異なる場合は、次のように領域名を指定する必要があります。

    Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000 -Realm "contoso.com"

これらの変更を行った後スクリプトを実行できます。Lync Server 2013 管理シェル内からスクリプト ファイルを実行することで、Exchange 2013 と SharePoint の両方をパートナー アプリケーションとして構成できます。次に例を示します。

    C:\Scripts\ServerToServerAuth.ps1

このスクリプトは、Exchange 2013 および SharePoint Server の両方がインストールされていない場合でも実行できます。たとえば、SharePoint Server がインストールされていない場合でも、SharePoint Server をパートナー アプリケーションとして構成しても問題はありません。

このスクリプトを実行したときに、次のようなエラー メッセージが表示されることがあります。

    New-CsPartnerApplication : Cannot bind parameter 'MetadataUrl' to the target. Exception setting "MetadataUrl": "The metadata document could not be downloaded from the URL in the MetadataUrl parameter or downloaded data is not a valid metadata document."

このエラー メッセージは、通常は次の 2 つのどちらかを意味します。1) スクリプトに指定されたいずれかの URL が無効である (いずれかのメタデータ URL が実際のメタデータ URL ではない)。または、2) いずれかのメタデータ URL に接続できない。これが発生した場合は、URL が正しいこと、およびアクセス可能であることを確認し、スクリプトを再実行します。

Lync Server 2013 用のパートナー アプリケーションを作成した後、Lync Server が Exchange 2013 のパートナー アプリケーションになるように構成する必要があります。Exchange 2013 のパートナー アプリケーションは、Configure-EnterprisePartnerApplication.1 スクリプトを実行することで構成できます。実行する必要があるのは、Lync Server のメタデータ URL を指定し、Lync Server が新しいパートナー アプリケーションであることを示すことだけです。

Lync Server を Exchange のパートナー アプリケーションとして構成するには、Exchange 管理シェルを開き、次のようなコマンドを実行します。

    "c:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1" -AuthMetadataUrl "https://lync.contoso.com/metadata/json/1" -ApplicationType "Lync"

