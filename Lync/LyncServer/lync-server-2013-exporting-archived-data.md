---
title: 'Lync Server 2013: アーカイブデータのエクスポート'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Exporting archived data
ms:assetid: 09450d54-769b-4741-924b-e390664d506f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204657(v=OCS.15)
ms:contentKeyID: 48183347
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4974971912b0b64652aa939368f0a86e2e2484a4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833179"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="exporting-archived-data-from-lync-server-2013"></a><span data-ttu-id="acd0b-102">Lync Server 2013 からアーカイブデータをエクスポートする</span><span class="sxs-lookup"><span data-stu-id="acd0b-102">Exporting archived data from Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="acd0b-103">_**最終更新日:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="acd0b-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="acd0b-104">アーカイブ データベースにアーカイブされているデータは、読み取り可能な形式ではなく、検索もできませんが、Export-CsArchivingData コマンドレットを使用すると、アーカイブ データベースからレコードを抽出して Outlook Electronic Mail (EML) ファイルとして保存できます。</span><span class="sxs-lookup"><span data-stu-id="acd0b-104">Data archived in Archiving databases is not searchable or in a readable format, but you can use the Export-CsArchivingData cmdlet to extract records from the database and save them as an Outlook Electronic Mail (EML) file.</span></span> <span data-ttu-id="acd0b-105">アーカイブデータのエクスポートの詳細については、操作のドキュメントの「 [Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="acd0b-105">For details about exporting archived data, see [Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData) in the Operations documentation.</span></span>

<span data-ttu-id="acd0b-106">Microsoft Exchange の統合を有効にすると、データは Exchange 2013 ストアにアーカイブされます。</span><span class="sxs-lookup"><span data-stu-id="acd0b-106">If you enable Microsoft Exchange integration, data is archived in Exchange 2013 stores.</span></span> <span data-ttu-id="acd0b-107">Exchange 2013 でアーカイブされたデータは、検索可能で見つけやすくなります。</span><span class="sxs-lookup"><span data-stu-id="acd0b-107">Data archived in Exchange 2013 is searchable and discoverable.</span></span> <span data-ttu-id="acd0b-108">Exchange 2013 および Lync Server 2013 の統合通信のサポートの詳細については、サポートドキュメントの「 [Exchange server および Lync server 2013 の SharePoint 統合のサポート](lync-server-2013-exchange-and-sharepoint-integration-support.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="acd0b-108">For details about support for integrated communications for Exchange 2013 and Lync Server 2013, see [Exchange Server and SharePoint integration support in Lync Server 2013](lync-server-2013-exchange-and-sharepoint-integration-support.md) in the Supportability documentation.</span></span> <span data-ttu-id="acd0b-109">Exchange でアーカイブされたデータへのアクセスについて詳しくは、「Exchange 2013 のドキュメント」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="acd0b-109">For details about accessing data that is archived in Exchange, see the Exchange 2013 documentation.</span></span>

<div>

## <a name="exporting-archiving-data-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="acd0b-110">Windows PowerShell コマンドレットを使用してアーカイブデータをエクスポートする</span><span class="sxs-lookup"><span data-stu-id="acd0b-110">Exporting Archiving Data by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="acd0b-111">アーカイブデータをエクスポートするには、CSArchivingData コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="acd0b-111">Archiving data can be exported by using the Export-CSArchivingData cmdlet.</span></span> <span data-ttu-id="acd0b-112">このコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモートセッションから実行できます。</span><span class="sxs-lookup"><span data-stu-id="acd0b-112">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="acd0b-113">リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、「Lync Server Windows PowerShell のブログ記事」を参照してください[http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。「リモート PowerShell を使用して Microsoft Lync Server 2010 を管理する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="acd0b-113">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<span data-ttu-id="acd0b-114">**アーカイブデータをエクスポートするには**</span><span class="sxs-lookup"><span data-stu-id="acd0b-114">**To export archiving data**</span></span>

  - <span data-ttu-id="acd0b-115">このコマンドは、2012年6月1日以降にアーカイブデータベース atl-sql-001.litwareinc.com に書き込まれたすべてのアーカイブデータをエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="acd0b-115">This command exports all the archiving data written to the archiving database atl-sql-001.litwareinc.com since June 1, 2012.</span></span> <span data-ttu-id="acd0b-116">生成される出力ファイルは、フォルダー C:\\ArchivingExports に格納されます。</span><span class="sxs-lookup"><span data-stu-id="acd0b-116">The resulting output file will be stored in the folder C:\\ArchivingExports.</span></span>
    
        Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.litwareinc.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports"

<span data-ttu-id="acd0b-117">**1人のユーザーのアーカイブデータをエクスポートするには**</span><span class="sxs-lookup"><span data-stu-id="acd0b-117">**To export archiving data for a single user**</span></span>

  - <span data-ttu-id="acd0b-118">次のコマンドは、1人のユーザーのアーカイブデータをエクスポートします。 kenmyer@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="acd0b-118">The following command exports archiving data for a single user: kenmyer@litwareinc.com.</span></span> <span data-ttu-id="acd0b-119">こうした処理を行うには、UserUri パラメーターの後にユーザーの SIP アドレスを指定します。</span><span class="sxs-lookup"><span data-stu-id="acd0b-119">This is done by including the UserUri parameter followed by the user’s SIP address.</span></span> <span data-ttu-id="acd0b-120">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="acd0b-120">For example:</span></span>
    
        Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.litwareinc.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports" -UserUri "sip:kenmyer@litwareinc.com"

<span data-ttu-id="acd0b-121">詳細については、 [CsArchivingData](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData)コマンドレットのヘルプトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="acd0b-121">For more information, see the help topic for the [Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="acd0b-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="acd0b-122">See Also</span></span>


[<span data-ttu-id="acd0b-123">Lync Server 2013 の Exchange Server および SharePoint の統合のサポート</span><span class="sxs-lookup"><span data-stu-id="acd0b-123">Exchange Server and SharePoint integration support in Lync Server 2013</span></span>](lync-server-2013-exchange-and-sharepoint-integration-support.md)  


[<span data-ttu-id="acd0b-124">エクスポート-CsArchivingData</span><span class="sxs-lookup"><span data-stu-id="acd0b-124">Export-CsArchivingData</span></span>](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData)  
[<span data-ttu-id="acd0b-125">Lync Server 2013 アーカイブの管理</span><span class="sxs-lookup"><span data-stu-id="acd0b-125">Managing Lync Server 2013 Archiving</span></span>](lync-server-2013-managing-archiving.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

