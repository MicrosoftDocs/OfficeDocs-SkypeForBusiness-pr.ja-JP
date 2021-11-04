---
title: アーカイブされたデータをエクスポートSkype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 8214bb0a-baa7-414f-9eee-313b65223fa3
description: '概要: アーカイブされたデータをエクスポートする方法についてSkype for Business Server。'
ms.openlocfilehash: e78ec210e993a11bf0ae17d4e41270602d2bf24a
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/04/2021
ms.locfileid: "60740653"
---
# <a name="export-archived-data-in-skype-for-business-server"></a>アーカイブされたデータをエクスポートSkype for Business Server

**概要:** アーカイブされたデータをエクスポートする方法についてSkype for Business Server。
  
アーカイブ データベースにアーカイブされたデータは、検索可能または読み取り可能な形式では使用できませんが **、Export-CsArchivingData** コマンドレットを使用してデータベースからレコードを抽出し、Outlook 電子メール (EML) ファイルとして保存できます。
  
Microsoft アプリの統合を有効Exchange、データはストアにExchangeされます。 このデータは、Exchange検索および検出可能です。 ドキュメントにアーカイブされているデータへのアクセスの詳細については、ExchangeドキュメントをExchangeしてください。
  
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
