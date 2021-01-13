---
title: Skype for Business Server でアーカイブされたデータをエクスポートする
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8214bb0a-baa7-414f-9eee-313b65223fa3
description: '概要: Skype for Business Server のアーカイブ 済みデータをエクスポートする方法について学習します。'
ms.openlocfilehash: caff65e829b24dc83760c7a505e344905c9e09e1
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817567"
---
# <a name="export-archived-data-in-skype-for-business-server"></a>Skype for Business Server でアーカイブされたデータをエクスポートする

**概要:** Skype for Business Server のアーカイブ データをエクスポートする方法について学習します。
  
アーカイブ データベースにアーカイブされたデータは、検索可能または読み取り可能な形式ではありません。ただし **、Export-CsArchivingData** コマンドレットを使用して、データベースからレコードを抽出し、それらを Outlook Electronic Mail (EML) ファイルとして保存できます。
  
Microsoft Exchange 統合を有効にした場合、データは Exchange ストアにアーカイブされます。 Exchange にアーカイブされたデータは検索可能で検出可能です。 Exchange にアーカイブされているデータへのアクセスの詳細については、Exchange のドキュメントを参照してください。
  
## <a name="exporting-archiving-data-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用したアーカイブ データのエクスポート

アーカイブされたデータは、次のコマンドレットを使用Export-CSArchivingDataできます。 
  
次のコマンドは、2012 年 6 月 1 atl-sql-001.contoso.comアーカイブ データベースに書き込まれたすべてのアーカイブ データをエクスポートします。 結果として得られる出力ファイルは、フォルダー C:\ArchivingExports に保存されます。
  
```PowerShell
Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.contoso.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports"
```

次のコマンドは、1 人のユーザーのアーカイブ データをエクスポートします。kenmyer@contoso.com。 これを実行するには、UserUri パラメーターの後にユーザーの SIP アドレスを指定します。 例: 
  
```PowerShell
Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.contoso.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports" -UserUri "sip:kenmyer@contoso.com"
```

詳細については [、Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/export-csarchivingdata?view=skype-ps) コマンドレットのヘルプ トピックを参照してください。
  

