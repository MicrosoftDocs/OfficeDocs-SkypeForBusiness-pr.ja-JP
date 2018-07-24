---
title: ビジネス サーバーの Skype でのアーカイブ ・ データをエクスポートします。
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8214bb0a-baa7-414f-9eee-313b65223fa3
description: '概要: は、Skype のビジネス サーバーのアーカイブ ・ データをエクスポートする方法を説明します。'
ms.openlocfilehash: 9b03ea23fd907a386b15005f18c3c0becdb79589
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2018
ms.locfileid: "20975768"
---
# <a name="export-archived-data-in-skype-for-business-server"></a>ビジネス サーバーの Skype でのアーカイブ ・ データをエクスポートします。

**の概要:** Skype のビジネス サーバーのアーカイブ ・ データをエクスポートする方法について説明します。
  
アーカイブ データベースにアーカイブされているデータは、読み取り可能な形式ではなく、検索もできませんが、**Export-CsArchivingData** コマンドレットを使用すると、アーカイブ データベースからレコードを抽出して Outlook Electronic Mail (EML) ファイルとして保存できます。
  
データをアーカイブする場合、Microsoft Exchange の統合を有効にすると、Exchange ストアにします。 Exchange でアーカイブされたデータは、検索で見つけやすいです。 Exchange でアーカイブされたデータへのアクセスに関する詳細については、Exchange のドキュメントを参照してください。
  
## <a name="exporting-archiving-data-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用して、データのアーカイブをエクスポートします。

Export-CSArchivingData コマンドレットを使用すると、アーカイブ データをエクスポートできます。 
  
次のコマンドは、2012 年 6 月 1 日以降にアーカイブ データベース atl-sql-001.contoso.com に書き込まれたすべてのアーカイブ データをエクスポートします。結果として得られる出力ファイルは、フォルダー C:\ArchivingExports に保存されます。
  
```
Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.contoso.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports"
```

次のコマンドは、kenmyer@contoso.com という 1 人のユーザーのアーカイブ データをエクスポートします。 これは、UserUri パラメーターの後に、ユーザーの SIP アドレスを含めることによって行われます。 例: 
  
```
Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.contoso.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports" -UserUri "sip:kenmyer@contoso.com"
```

詳細については、 [.eml という](https://docs.microsoft.com/powershell/module/skype/export-csarchivingdata?view=skype-ps)コマンドレットのヘルプ トピックを参照してください。
  

