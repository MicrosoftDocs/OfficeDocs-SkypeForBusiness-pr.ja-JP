---
title: Lync Server 2013 用にオンプレミスパートナーアプリケーションを構成する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring an on-premises partner application for Lync Server 2013
ms:assetid: 696f2b26-e5d0-42b5-9785-a26c2ce25bb7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204975(v=OCS.15)
ms:contentKeyID: 48184412
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6fe3597f873e8f3bcf66eba922624e4c13ab3f3b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726547"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-an-on-premises-partner-application-for-microsoft-lync-server-2013"></a>Microsoft Lync Server 2013 用のオンプレミスパートナーアプリケーションの構成

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-02-04_

OAuthTokenIssuer 証明書を割り当てたら、Microsoft Lync Server 2013 パートナーアプリケーションを構成する必要があります。 (説明する必要がある手順では、Microsoft Exchange Server 2013 と Microsoft SharePoint の両方を、パートナーアプリケーションとして機能するように構成します)。オンプレミスパートナーアプリケーションを構成するには、まず、次の Windows PowerShell スクリプトをコピーし、メモ帳 (またはその他のテキストエディター) にコードを貼り付けます。

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

コードをコピーしたら、を使ってスクリプトを保存します。PS1 ファイル拡張子 (たとえば、C:\\スクリプト\\servertoserverauth. ps1)。 このスクリプトを実行する前に、メタデータの Url https://atl-exchange-001.litwareinc.com/autodiscover/metadata/json/1とhttp://atl-sharepoint-001.litwareinc.com/jsonmetadata.ashx 、Exchange 2013 および SharePoint サーバーで使用されるメタデータ url をそれぞれ置換する必要があることに注意してください。 各製品のメタデータ URL を特定する方法については、Exchange 2013 と SharePoint の製品に関するドキュメントを参照してください。

このスクリプトの最後の行で、Set-CsOAuthConfiguration コマンドレットが次の構文で呼び出されます。

    Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000

Set-CsOAuthConfiguration を呼び出すときに Realm パラメーターが使用されなかったため、領域には組織の完全修飾ドメイン名 (FQDN) が自動的に設定されます (例: litwareinc.com)。領域名が組織名と異なる場合は、次のように領域名を指定する必要があります。

    Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000 -Realm "contoso.com"

これらの変更を加えた後で、Lync Server 2013 Management Shell 内からスクリプトファイルを実行して、スクリプトを実行し、Exchange 2013 と SharePoint の両方をパートナーアプリケーションとして構成できます。 次に例を示します。

    C:\Scripts\ServerToServerAuth.ps1

このスクリプトは、Exchange 2013 と SharePoint Server の両方がインストールされていない場合でも実行できます。 sharepoint Server がインストールされていない場合でも、パートナーアプリケーションとして SharePoint Server を構成すると、問題は発生しません。

このスクリプトを実行したときに、次のようなエラー メッセージが表示されることがあります。

    New-CsPartnerApplication : Cannot bind parameter 'MetadataUrl' to the target. Exception setting "MetadataUrl": "The metadata document could not be downloaded from the URL in the MetadataUrl parameter or downloaded data is not a valid metadata document."

このエラー メッセージは、通常は次の 2 つのどちらかを意味します。1) スクリプトに指定されたいずれかの URL が無効である (いずれかのメタデータ URL が実際のメタデータ URL ではない)。または、2) いずれかのメタデータ URL に接続できない。これが発生した場合は、URL が正しいこと、およびアクセス可能であることを確認し、スクリプトを再実行します。

Lync Server 2013 用パートナーアプリケーションを作成した後で、Lync Server を Exchange 2013 のパートナーアプリケーションとして構成する必要があります。 Configure-EnterprisePartnerApplication を実行して、Exchange 2013 のパートナーアプリケーションを構成することができます。Lync Server のメタデータ URL を指定するだけで、Lync Server が新しいパートナーアプリケーションであることを示す必要があります。

Exchange のパートナーアプリケーションとして Lync Server を構成するには、Exchange 管理シェルを開き、次のようなコマンドを実行します。

    "c:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1" -AuthMetadataUrl "https://lync.contoso.com/metadata/json/1" -ApplicationType "Lync"

</div>

<span> </span>

</div>

</div>

</div>

