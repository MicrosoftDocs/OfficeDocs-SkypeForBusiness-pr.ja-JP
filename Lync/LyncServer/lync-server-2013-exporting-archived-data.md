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
ms.openlocfilehash: 4bb0bcb30c49a44fe92920d4db77d6bf9697cd9e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2020
ms.locfileid: "42008699"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="exporting-archived-data-from-lync-server-2013"></a>Lync Server 2013 からのアーカイブされたデータのエクスポート

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-23_

アーカイブ データベースにアーカイブされているデータは、読み取り可能な形式ではなく、検索もできませんが、Export-CsArchivingData コマンドレットを使用すると、アーカイブ データベースからレコードを抽出して Outlook Electronic Mail (EML) ファイルとして保存できます。 アーカイブされたデータのエクスポートの詳細については、「操作」のドキュメントの「[Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData)」を参照してください。

Microsoft Exchange 統合を有効にすると、データは Exchange 2013 ストアにアーカイブされます。 Exchange 2013 でアーカイブされたデータは検索可能で、検出可能です。 Exchange 2013 および Lync Server 2013 の統合コミュニケーションのサポートの詳細については、「サポート」のドキュメントの「 [Lync server 2013 での Exchange Server と SharePoint の統合のサポート](lync-server-2013-exchange-and-sharepoint-integration-support.md)」を参照してください。 Exchange にアーカイブされているデータへのアクセスに関する詳細については、Exchange 2013 のドキュメントを参照してください。

<div>

## <a name="exporting-archiving-data-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用してアーカイブデータをエクスポートする

アーカイブ データは、Export-CSArchivingData コマンドレットを使用してエクスポートできます。 このコマンドレットは、Lync Server 2013 管理シェルから実行するか、Windows PowerShell のリモートセッションから実行できます。 リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を[http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)で参照してください。

**アーカイブデータをエクスポートするには**

  - このコマンドは、2012 年 6 月 1 日以降にアーカイブ データベース atl-sql-001.litwareinc.com に書き込まれたすべてのアーカイブ データをエクスポートします。 結果の出力ファイルは、フォルダー C:\\ArchivingExports に保存されます。
    
        Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.litwareinc.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports"

**単一ユーザーのアーカイブデータをエクスポートするには**

  - 次のコマンドは、kenmyer@litwareinc.com という 1 人のユーザーのアーカイブ データをエクスポートします。こうした処理を行うには、UserUri パラメーターの後にユーザーの SIP アドレスを指定します。次に例を示します。
    
        Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.litwareinc.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports" -UserUri "sip:kenmyer@litwareinc.com"

詳細については、 [export-csarchivingdata](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData)コマンドレットのヘルプトピックを参照してください。

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 での Exchange Server および SharePoint の統合のサポート](lync-server-2013-exchange-and-sharepoint-integration-support.md)  


[Export-csarchivingdata](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData)  
[Lync Server 2013 アーカイブの管理](lync-server-2013-managing-archiving.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

