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
ms.openlocfilehash: 58cfee7b89d2e7e66bd39b28a6d3361b4521cdc2
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42207573"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-an-on-premises-partner-application-for-microsoft-lync-server-2013"></a><span data-ttu-id="0676e-102">Microsoft Lync Server 2013 用のオンプレミスパートナーアプリケーションの構成</span><span class="sxs-lookup"><span data-stu-id="0676e-102">Configuring an on-premises partner application for Microsoft Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0676e-103">_**トピックの最終更新日:** 2013-02-04_</span><span class="sxs-lookup"><span data-stu-id="0676e-103">_**Topic Last Modified:** 2013-02-04_</span></span>

<span data-ttu-id="0676e-104">OAuthTokenIssuer 証明書を割り当てたら、Microsoft Lync Server 2013 パートナーアプリケーションを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0676e-104">After you have assigned the OAuthTokenIssuer certificate you must then configure your Microsoft Lync Server 2013 partner applications.</span></span> <span data-ttu-id="0676e-105">(説明する手順では、Microsoft Exchange Server 2013 と Microsoft SharePoint の両方をパートナーアプリケーションとして動作するように構成します)。オンプレミスパートナーアプリケーションを構成するには、まず、次の Windows PowerShell スクリプトをコピーして、コードをメモ帳 (またはその他のテキストエディター) に貼り付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="0676e-105">(The procedure about to be discussed configures both Microsoft Exchange Server 2013 and Microsoft SharePoint to act as partner applications.) To configure an on-premises partner application, you must start by copying the following Windows PowerShell script and pasting the code into Notepad (or any other text editor):</span></span>

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

<span data-ttu-id="0676e-106">コードをコピーした後、を使用してスクリプトを保存します。PS1 ファイルの拡張子 (たとえば、C:\\Scripts\\servertoserverauth. ps1)。</span><span class="sxs-lookup"><span data-stu-id="0676e-106">After copying the code, save the script using a .PS1 file extension (for example, C:\\Scripts\\ServerToServerAuth.ps1).</span></span> <span data-ttu-id="0676e-107">このスクリプトを実行する前に、メタデータ Url https://atl-exchange-001.litwareinc.com/autodiscover/metadata/json/1とhttp://atl-sharepoint-001.litwareinc.com/jsonmetadata.ashx 、Exchange 2013 サーバーおよび SharePoint サーバーで使用されるメタデータ url をそれぞれ置き換える必要があります。</span><span class="sxs-lookup"><span data-stu-id="0676e-107">Note that, before you run this script, you must replace the metadata URLs https://atl-exchange-001.litwareinc.com/autodiscover/metadata/json/1 and http://atl-sharepoint-001.litwareinc.com/jsonmetadata.ashx with the metadata URLs used by your Exchange 2013 and SharePoint servers, respectively.</span></span> <span data-ttu-id="0676e-108">各製品のメタデータ URL を特定する方法については、「Exchange 2013 と SharePoint の製品ドキュメント」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0676e-108">See the product documentation for Exchange 2013 and SharePoint for information on how you can identify the respective product's metadata URL.</span></span>

<span data-ttu-id="0676e-109">このスクリプトの最後の行で、Set-CsOAuthConfiguration コマンドレットが次の構文で呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="0676e-109">If you look at the last line of the script you will notice that the Set-CsOAuthConfiguration cmdlet is called using this syntax:</span></span>

    Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000

<span data-ttu-id="0676e-p103">Set-CsOAuthConfiguration を呼び出すときに Realm パラメーターが使用されなかったため、領域には組織の完全修飾ドメイン名 (FQDN) が自動的に設定されます (例: litwareinc.com)。領域名が組織名と異なる場合は、次のように領域名を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0676e-p103">Because the Realm parameter was not used when calling Set-CsOAuthConfiguration the realm will automatically be set to the fully qualified domain name (FQDN) of your organization (for example, litwareinc.com). If your realm name is different from your organization name then you should include the realm name, like this:</span></span>

    Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000 -Realm "contoso.com"

<span data-ttu-id="0676e-112">これらの変更を行った後、スクリプトを実行して、Exchange 2013 と SharePoint の両方をパートナーアプリケーションとして構成できるようにするには、Lync Server 2013 管理シェル内からスクリプトファイルを実行します。</span><span class="sxs-lookup"><span data-stu-id="0676e-112">After making these changes you can then execute the script, and configure both Exchange 2013 and SharePoint as partner applications, by running the script file from within the Lync Server 2013 Management Shell.</span></span> <span data-ttu-id="0676e-113">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="0676e-113">For example:</span></span>

    C:\Scripts\ServerToServerAuth.ps1

<span data-ttu-id="0676e-114">このスクリプトは、Exchange 2013 と SharePoint Server の両方がインストールされていない場合でも実行できることに注意してください。たとえば、sharepoint Server がインストールされていない場合でも、SharePoint Server をパートナーアプリケーションとして構成しても問題はありません。</span><span class="sxs-lookup"><span data-stu-id="0676e-114">Note that you can run this script even if you do not have both Exchange 2013 and SharePoint Server installed:, no problems will occur if you, say, configure SharePoint Server as a partner application even though you do not have SharePoint Server installed.</span></span>

<span data-ttu-id="0676e-115">このスクリプトを実行したときに、次のようなエラー メッセージが表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="0676e-115">When you run this script you might receive an error message similar to the following:</span></span>

    New-CsPartnerApplication : Cannot bind parameter 'MetadataUrl' to the target. Exception setting "MetadataUrl": "The metadata document could not be downloaded from the URL in the MetadataUrl parameter or downloaded data is not a valid metadata document."

<span data-ttu-id="0676e-p105">このエラー メッセージは、通常は次の 2 つのどちらかを意味します。1) スクリプトに指定されたいずれかの URL が無効である (いずれかのメタデータ URL が実際のメタデータ URL ではない)。または、2) いずれかのメタデータ URL に接続できない。これが発生した場合は、URL が正しいこと、およびアクセス可能であることを確認し、スクリプトを再実行します。</span><span class="sxs-lookup"><span data-stu-id="0676e-p105">This error message typically means one of two things: 1) that one of the URLs specified in the script is not valid (that is, one of your metadata URLs is not an actual metadata URL); or, 2) one of the metadata URLs could not be contacted. If this happens, verify that the URLs are correct and are accessible, and the re-run the script.</span></span>

<span data-ttu-id="0676e-118">Lync Server 2013 のパートナーアプリケーションを作成した後、Lync Server を Exchange 2013 のパートナーアプリケーションとして構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0676e-118">After creating the partner application for Lync Server 2013 you must then configure Lync Server to be a partner application for Exchange 2013.</span></span> <span data-ttu-id="0676e-119">スクリプト Configure-EnterprisePartnerApplication を実行して、Exchange 2013 のパートナーアプリケーションを構成できます。必要なのは、Lync Server のメタデータ URL を指定し、Lync Server が新しいパートナーアプリケーションであることを示すことだけです。</span><span class="sxs-lookup"><span data-stu-id="0676e-119">You can configure partner applications for Exchange 2013 by running the script Configure-EnterprisePartnerApplication.ps1; all you need to do is specify the metadata URL for Lync Server and indicate that Lync Server is the new partner application.</span></span>

<span data-ttu-id="0676e-120">Exchange のパートナーアプリケーションとして Lync Server を構成するには、Exchange 管理シェルを開き、次のようなコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="0676e-120">To configure Lync Server as a partner application for Exchange, open the Exchange Management Shell and run a command similar to this</span></span>

    "c:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1" -AuthMetadataUrl "https://lync.contoso.com/metadata/json/1" -ApplicationType "Lync"

</div>

<span> </span>

</div>

</div>

</div>

