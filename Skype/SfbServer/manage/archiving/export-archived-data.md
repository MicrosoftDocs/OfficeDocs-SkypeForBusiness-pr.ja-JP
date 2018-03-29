---
title: Skype for Business Server 2015 でのアーカイブされたデータのエクスポート
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8214bb0a-baa7-414f-9eee-313b65223fa3
description: ': の概要では、Skype のビジネス サーバー 2015 のアーカイブ ・ データをエクスポートする方法について説明します。'
ms.openlocfilehash: f5fe222589efa5ce6e8e21151817042497fb6cc6
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="export-archived-data-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 でのアーカイブされたデータのエクスポート

**の概要:**Skype のビジネス サーバー 2015 のアーカイブ ・ データをエクスポートする方法について説明します。
  
アーカイブ データベースにアーカイブされているデータは、読み取り可能な形式ではなく、検索もできませんが、**Export-CsArchivingData** コマンドレットを使用すると、アーカイブ データベースからレコードを抽出して Outlook Electronic Mail (EML) ファイルとして保存できます。
  
データをアーカイブする場合、Microsoft Exchange の統合を有効にすると、Exchange ストアにします。 Exchange でアーカイブされたデータは、検索で見つけやすいです。 Exchange でアーカイブされたデータへのアクセスに関する詳細については、Exchange のドキュメントを参照してください。
  
## <a name="exporting-archiving-data-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用して、データのアーカイブをエクスポートします。

Export-CSArchivingData コマンドレットを使用すると、アーカイブ データをエクスポートできます。 
  
次のコマンドは、2012 年 6 月 1 日以降にアーカイブ データベース atl-sql-001.contoso.com に書き込まれたすべてのアーカイブ データをエクスポートします。結果として得られる出力ファイルは、フォルダー C:\ArchivingExports に保存されます。
  
```
Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.contoso.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports"
```

次のコマンドを単一のユーザーのデータをアーカイブのエクスポート: kenmyer@contoso.com。これは、UserUri パラメーターの後に、ユーザーの SIP アドレスを含めることによって行われます。 例: 
  
```
Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.contoso.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports" -UserUri "sip:kenmyer@contoso.com"
```

詳細については、 [.eml という](https://docs.microsoft.com/powershell/module/skype/export-csarchivingdata?view=skype-ps)コマンドレットのヘルプ トピックを参照してください。
  

