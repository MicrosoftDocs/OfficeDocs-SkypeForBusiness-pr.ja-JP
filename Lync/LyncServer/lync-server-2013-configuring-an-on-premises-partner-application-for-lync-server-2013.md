---
title: Lync Server 2013 用のオンプレミスパートナーアプリケーションの構成
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
ms.openlocfilehash: f61d1e5ef7edc8414ee16eaa90ee31a69744af18
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029688"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-an-on-premises-partner-application-for-microsoft-lync-server-2013"></a>Microsoft Lync Server 2013 用のオンプレミスパートナーアプリケーションの構成

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-04_

OAuthTokenIssuer 証明書を割り当てたら、Microsoft Lync Server 2013 パートナーアプリケーションを構成する必要があります。 (説明する手順では、Microsoft Exchange Server 2013 と Microsoft SharePoint の両方をパートナーアプリケーションとして動作するように構成します)。オンプレミスパートナーアプリケーションを構成するには、まず、次の Windows PowerShell スクリプトをコピーして、コードをメモ帳 (またはその他のテキストエディター) に貼り付ける必要があります。

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

コードをコピーした後、を使用してスクリプトを保存します。PS1 ファイルの拡張子 (たとえば、C:\\Scripts\\servertoserverauth. ps1)。 このスクリプトを実行する前に、メタデータ Url https://atl-exchange-001.litwareinc.com/autodiscover/metadata/json/1とhttp://atl-sharepoint-001.litwareinc.com/jsonmetadata.ashx 、Exchange 2013 サーバーおよび SharePoint サーバーで使用されるメタデータ url をそれぞれ置き換える必要があります。 各製品のメタデータ URL を特定する方法については、「Exchange 2013 と SharePoint の製品ドキュメント」を参照してください。

このスクリプトの最後の行で、Set-CsOAuthConfiguration コマンドレットが次の構文で呼び出されます。

    Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000

Set-CsOAuthConfiguration を呼び出すときに Realm パラメーターが使用されなかったため、領域には組織の完全修飾ドメイン名 (FQDN) が自動的に設定されます (例: litwareinc.com)。領域名が組織名と異なる場合は、次のように領域名を指定する必要があります。

    Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000 -Realm "contoso.com"

これらの変更を行った後、スクリプトを実行して、Exchange 2013 と SharePoint の両方をパートナーアプリケーションとして構成できるようにするには、Lync Server 2013 管理シェル内からスクリプトファイルを実行します。 例:

    C:\Scripts\ServerToServerAuth.ps1

このスクリプトは、Exchange 2013 と SharePoint Server の両方がインストールされていない場合でも実行できることに注意してください。たとえば、sharepoint Server がインストールされていない場合でも、SharePoint Server をパートナーアプリケーションとして構成しても問題はありません。

このスクリプトを実行したときに、次のようなエラー メッセージが表示されることがあります。

    New-CsPartnerApplication : Cannot bind parameter 'MetadataUrl' to the target. Exception setting "MetadataUrl": "The metadata document could not be downloaded from the URL in the MetadataUrl parameter or downloaded data is not a valid metadata document."

このエラー メッセージは、通常は次の 2 つのどちらかを意味します。1) スクリプトに指定されたいずれかの URL が無効である (いずれかのメタデータ URL が実際のメタデータ URL ではない)。または、2) いずれかのメタデータ URL に接続できない。これが発生した場合は、URL が正しいこと、およびアクセス可能であることを確認し、スクリプトを再実行します。

Lync Server 2013 のパートナーアプリケーションを作成した後、Lync Server を Exchange 2013 のパートナーアプリケーションとして構成する必要があります。 スクリプト Configure-EnterprisePartnerApplication を実行して、Exchange 2013 のパートナーアプリケーションを構成できます。必要なのは、Lync Server のメタデータ URL を指定し、Lync Server が新しいパートナーアプリケーションであることを示すことだけです。

Exchange のパートナーアプリケーションとして Lync Server を構成するには、Exchange 管理シェルを開き、次のようなコマンドを実行します。

    "c:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1" -AuthMetadataUrl "https://lync.contoso.com/metadata/json/1" -ApplicationType "Lync"

</div>

<span> </span>

</div>

</div>

</div>

