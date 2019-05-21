---
title: Skype for Business Server でアーカイブデータをエクスポートする
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8214bb0a-baa7-414f-9eee-313b65223fa3
description: '概要: Skype for Business Server のアーカイブデータをエクスポートする方法について説明します。'
ms.openlocfilehash: 6914b4c32c22165b551bb56ece8d7b3b9c21fdbe
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34286138"
---
# <a name="export-archived-data-in-skype-for-business-server"></a>Skype for Business Server でアーカイブデータをエクスポートする

**概要:** Skype for Business Server のアーカイブデータをエクスポートする方法について説明します。
  
アーカイブ データベースにアーカイブされているデータは、読み取り可能な形式ではなく、検索もできませんが、**Export-CsArchivingData** コマンドレットを使用すると、アーカイブ データベースからレコードを抽出して Outlook Electronic Mail (EML) ファイルとして保存できます。
  
Microsoft Exchange の統合を有効にすると、データは Exchange ストアにアーカイブされます。 Exchange でアーカイブされたデータは、検索と検出が可能です。 Exchange でアーカイブされたデータへのアクセスに関する詳細については、Exchange のドキュメントを参照してください。
  
## <a name="exporting-archiving-data-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用してアーカイブデータをエクスポートする

Export-CSArchivingData コマンドレットを使用すると、アーカイブ データをエクスポートできます。 
  
次のコマンドは、2012 年 6 月 1 日以降にアーカイブ データベース atl-sql-001.contoso.com に書き込まれたすべてのアーカイブ データをエクスポートします。結果として得られる出力ファイルは、フォルダー C:\ArchivingExports に保存されます。
  
```
Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.contoso.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports"
```

次のコマンドは、kenmyer@contoso.com という 1 人のユーザーのアーカイブ データをエクスポートします。 これは、UserUri パラメーターに続けてユーザーの SIP アドレスを含めることで行われます。 次に例を示します。 
  
```
Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.contoso.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports" -UserUri "sip:kenmyer@contoso.com"
```

詳細については、 [CsArchivingData](https://docs.microsoft.com/powershell/module/skype/export-csarchivingdata?view=skype-ps)コマンドレットのヘルプトピックを参照してください。
  

