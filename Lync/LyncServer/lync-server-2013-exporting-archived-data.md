---
title: 'Lync Server 2013: アーカイブされたデータのエクスポート'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Exporting archived data
ms:assetid: 09450d54-769b-4741-924b-e390664d506f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204657(v=OCS.15)
ms:contentKeyID: 48183347
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0f06c4208e3830db2e32dc9866747b78a93b567e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48528364"
---
# <a name="exporting-archived-data-from-lync-server-2013"></a><span data-ttu-id="376a2-102">Lync Server 2013 からのアーカイブされたデータのエクスポート</span><span class="sxs-lookup"><span data-stu-id="376a2-102">Exporting archived data from Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="376a2-103">_**トピックの最終更新日:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="376a2-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="376a2-104">アーカイブ データベースにアーカイブされているデータは、読み取り可能な形式ではなく、検索もできませんが、Export-CsArchivingData コマンドレットを使用すると、アーカイブ データベースからレコードを抽出して Outlook Electronic Mail (EML) ファイルとして保存できます。</span><span class="sxs-lookup"><span data-stu-id="376a2-104">Data archived in Archiving databases is not searchable or in a readable format, but you can use the Export-CsArchivingData cmdlet to extract records from the database and save them as an Outlook Electronic Mail (EML) file.</span></span> <span data-ttu-id="376a2-105">アーカイブされたデータのエクスポートの詳細については、「操作」のドキュメントの「[Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="376a2-105">For details about exporting archived data, see [Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData) in the Operations documentation.</span></span>

<span data-ttu-id="376a2-106">Microsoft Exchange 統合を有効にすると、データは Exchange 2013 ストアにアーカイブされます。</span><span class="sxs-lookup"><span data-stu-id="376a2-106">If you enable Microsoft Exchange integration, data is archived in Exchange 2013 stores.</span></span> <span data-ttu-id="376a2-107">Exchange 2013 でアーカイブされたデータは検索可能で、検出可能です。</span><span class="sxs-lookup"><span data-stu-id="376a2-107">Data archived in Exchange 2013 is searchable and discoverable.</span></span> <span data-ttu-id="376a2-108">Exchange 2013 および Lync Server 2013 の統合コミュニケーションのサポートの詳細については、「サポート」のドキュメントの「 [Lync server 2013 での Exchange Server と SharePoint の統合のサポート](lync-server-2013-exchange-and-sharepoint-integration-support.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="376a2-108">For details about support for integrated communications for Exchange 2013 and Lync Server 2013, see [Exchange Server and SharePoint integration support in Lync Server 2013](lync-server-2013-exchange-and-sharepoint-integration-support.md) in the Supportability documentation.</span></span> <span data-ttu-id="376a2-109">Exchange にアーカイブされているデータへのアクセスに関する詳細については、Exchange 2013 のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="376a2-109">For details about accessing data that is archived in Exchange, see the Exchange 2013 documentation.</span></span>

<div>

## <a name="exporting-archiving-data-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="376a2-110">Windows PowerShell コマンドレットを使用してアーカイブデータをエクスポートする</span><span class="sxs-lookup"><span data-stu-id="376a2-110">Exporting Archiving Data by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="376a2-111">アーカイブ データは、Export-CSArchivingData コマンドレットを使用してエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="376a2-111">Archiving data can be exported by using the Export-CSArchivingData cmdlet.</span></span> <span data-ttu-id="376a2-112">このコマンドレットは、Lync Server 2013 管理シェルまたは Windows PowerShell のリモート セッションから実行できます。</span><span class="sxs-lookup"><span data-stu-id="376a2-112">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="376a2-113">リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を[https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)で参照してください。</span><span class="sxs-lookup"><span data-stu-id="376a2-113">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<span data-ttu-id="376a2-114">**アーカイブデータをエクスポートするには**</span><span class="sxs-lookup"><span data-stu-id="376a2-114">**To export archiving data**</span></span>

  - <span data-ttu-id="376a2-115">このコマンドは、2012 年 6 月 1 日以降にアーカイブ データベース atl-sql-001.litwareinc.com に書き込まれたすべてのアーカイブ データをエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="376a2-115">This command exports all the archiving data written to the archiving database atl-sql-001.litwareinc.com since June 1, 2012.</span></span> <span data-ttu-id="376a2-116">結果の出力ファイルは、フォルダー C: ArchivingExports に保存され \\ ます。</span><span class="sxs-lookup"><span data-stu-id="376a2-116">The resulting output file will be stored in the folder C:\\ArchivingExports.</span></span>
    
        Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.litwareinc.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports"

<span data-ttu-id="376a2-117">**単一ユーザーのアーカイブデータをエクスポートするには**</span><span class="sxs-lookup"><span data-stu-id="376a2-117">**To export archiving data for a single user**</span></span>

  - <span data-ttu-id="376a2-p105">次のコマンドは、kenmyer@litwareinc.com という 1 人のユーザーのアーカイブ データをエクスポートします。こうした処理を行うには、UserUri パラメーターの後にユーザーの SIP アドレスを指定します。次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="376a2-p105">The following command exports archiving data for a single user: kenmyer@litwareinc.com. This is done by including the UserUri parameter followed by the user’s SIP address. For example:</span></span>
    
        Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.litwareinc.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports" -UserUri "sip:kenmyer@litwareinc.com"

<span data-ttu-id="376a2-121">詳細については、 [export-csarchivingdata](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData) コマンドレットのヘルプトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="376a2-121">For more information, see the help topic for the [Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="376a2-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="376a2-122">See Also</span></span>


[<span data-ttu-id="376a2-123">Lync Server 2013 での Exchange Server および SharePoint の統合のサポート</span><span class="sxs-lookup"><span data-stu-id="376a2-123">Exchange Server and SharePoint integration support in Lync Server 2013</span></span>](lync-server-2013-exchange-and-sharepoint-integration-support.md)  


[<span data-ttu-id="376a2-124">Export-csarchivingdata</span><span class="sxs-lookup"><span data-stu-id="376a2-124">Export-CsArchivingData</span></span>](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData)  
[<span data-ttu-id="376a2-125">Lync Server 2013 アーカイブの管理</span><span class="sxs-lookup"><span data-stu-id="376a2-125">Managing Lync Server 2013 Archiving</span></span>](lync-server-2013-managing-archiving.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

