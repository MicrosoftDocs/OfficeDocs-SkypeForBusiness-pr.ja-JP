---
title: Lync Server 2013 からアーカイブされたデータをエクスポートする
TOCTitle: Lync Server 2013 からアーカイブされたデータをエクスポートする
ms:assetid: 09450d54-769b-4741-924b-e390664d506f
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ204657(v=OCS.15)
ms:contentKeyID: 48271190
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 からアーカイブされたデータをエクスポートする

 

_**トピックの最終更新日:** 2013-02-23_

アーカイブ データベースにアーカイブされているデータは、読み取り可能な形式ではなく、検索もできませんが、Export-CsArchivingData コマンドレットを使用すると、アーカイブ データベースからレコードを抽出して Outlook Electronic Mail (EML) ファイルとして保存できます。アーカイブされたデータのエクスポートの詳細については、「操作」のドキュメントの「[Export-CsArchivingData](https://docs.microsoft.com/en-us/powershell/module/skype/Export-CsArchivingData)」を参照してください。

Microsoft Exchange 統合を有効にすると、データは Exchange 2013 ストアにアーカイブされます。Exchange 2013 にアーカイブされたデータは検索および発見の対象にできます。Exchange 2013 と Lync Server 2013 で統合されたコミュニケーションのサポートの詳細については、「サポート」のドキュメントの「[Lync Server 2013 の Exchange Server および SharePoint の統合のサポート](lync-server-2013-exchange-and-sharepoint-integration-support.md)」を参照してください。Exchange にアーカイブされているデータへのアクセスの詳細については、Exchange 2013 のドキュメントを参照してください。

## Lync Server 管理シェル コマンドレットを使用したアーカイブ データのエクスポート

アーカイブ データは、Export-CSArchivingData コマンドレットを使用してエクスポートできます。このコマンドレットは、Lync Server 2013 管理シェル、または Windows PowerShell のリモート セッションのどちらからでも実行できます。リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell」 ([http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)) を参照してください。

**アーカイブ データのエクスポート**

  - このコマンドは、2012 年 6 月 1 日以降にアーカイブ データベース atl-sql-001.litwareinc.com に書き込まれたすべてのアーカイブ データをエクスポートします。結果として得られる出力ファイルは、フォルダー C:\\ArchivingExports に保存されます。
    
        Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.litwareinc.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports"

**単一ユーザーのアーカイブ データのエクスポート**

  - 次のコマンドは、kenmyer@litwareinc.com という 1 人のユーザーのアーカイブ データをエクスポートします。こうした処理を行うには、UserUri パラメーターの後にユーザーの SIP アドレスを指定します。次に例を示します。
    
        Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.litwareinc.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports" -UserUri "sip:kenmyer@litwareinc.com"

詳細については、[Export-CsArchivingData](https://docs.microsoft.com/en-us/powershell/module/skype/Export-CsArchivingData) コマンドレットのヘルプ トピックを参照してください。

## 関連項目

#### 概念

[Lync Server 2013 の Exchange Server および SharePoint の統合のサポート](lync-server-2013-exchange-and-sharepoint-integration-support.md)  

#### その他のリソース

[Export-CsArchivingData](https://docs.microsoft.com/en-us/powershell/module/skype/Export-CsArchivingData)  
[Lync Server 2013 アーカイブの管理](lync-server-2013-managing-archiving.md)

