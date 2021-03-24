---
title: Skype for Business Server でアーカイブ データをエクスポートする
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
description: '概要: Skype for Business Server のアーカイブ データをエクスポートする方法について学習します。'
ms.openlocfilehash: e69c283304395d697e99ef0607e2aec1eb7960e4
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095381"
---
# <a name="export-archived-data-in-skype-for-business-server"></a>Skype for Business Server でアーカイブ データをエクスポートする

**概要:** Skype for Business Server のアーカイブ データをエクスポートする方法について学習します。
  
アーカイブ データベースにアーカイブされたデータは、検索可能または読み取り可能な形式では使用できませんが **、Export-CsArchivingData** コマンドレットを使用してデータベースからレコードを抽出し、Outlook 電子メール (EML) ファイルとして保存できます。
  
Microsoft Exchange 統合を有効にした場合、データは Exchange ストアにアーカイブされます。 Exchange にアーカイブされたデータは検索可能で検出可能です。 Exchange でアーカイブされているデータへのアクセスの詳細については、Exchange のドキュメントを参照してください。
  
## <a name="exporting-archiving-data-by-using-windows-powershell-cmdlets"></a>コマンドレットを使用したアーカイブ データWindows PowerShellする

アーカイブされたデータは、このコマンドレットを使用Export-CSArchivingDataできます。 
  
次のコマンドは、2012 年 6 月 1 日からアーカイブ データベースに書き込 atl-sql-001.contoso.com をエクスポートします。 結果として得られる出力ファイルは、フォルダー C:\ArchivingExports に保存されます。
  
```PowerShell
Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.contoso.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports"
```

次のコマンドは、1 人のユーザーのアーカイブ データをエクスポートします。kenmyer@contoso.com。 これは、UserUri パラメーターの後にユーザーの SIP アドレスを含めて行います。 例: 
  
```PowerShell
Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.contoso.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports" -UserUri "sip:kenmyer@contoso.com"
```

詳細については [、Export-CsArchivingData コマンドレットのヘルプ トピックを参照](/powershell/module/skype/export-csarchivingdata?view=skype-ps) してください。
