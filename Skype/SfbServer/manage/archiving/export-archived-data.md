---
title: ビジネス サーバーの Skype でのアーカイブ ・ データをエクスポートします。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8214bb0a-baa7-414f-9eee-313b65223fa3
description: '概要: は、Skype のビジネス サーバーのアーカイブ ・ データをエクスポートする方法を説明します。'
ms.openlocfilehash: fd17fda9d36c5739d9d1cab7845921a442a4155d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33884965"
---
# <a name="export-archived-data-in-skype-for-business-server"></a><span data-ttu-id="e0d81-103">ビジネス サーバーの Skype でのアーカイブ ・ データをエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="e0d81-103">Export archived data in Skype for Business Server</span></span>

<span data-ttu-id="e0d81-104">**の概要:** Skype のビジネス サーバーのアーカイブ ・ データをエクスポートする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="e0d81-104">**Summary:** Learn how to export archived data for Skype for Business Server.</span></span>
  
<span data-ttu-id="e0d81-105">アーカイブ データベースにアーカイブされているデータは、読み取り可能な形式ではなく、検索もできませんが、**Export-CsArchivingData** コマンドレットを使用すると、アーカイブ データベースからレコードを抽出して Outlook Electronic Mail (EML) ファイルとして保存できます。</span><span class="sxs-lookup"><span data-stu-id="e0d81-105">Data archived in Archiving databases is not searchable or in a readable format, but you can use the **Export-CsArchivingData** cmdlet to extract records from the database and save them as an Outlook Electronic Mail (EML) file.</span></span>
  
<span data-ttu-id="e0d81-106">データをアーカイブする場合、Microsoft Exchange の統合を有効にすると、Exchange ストアにします。</span><span class="sxs-lookup"><span data-stu-id="e0d81-106">If you enable Microsoft Exchange integration, data is archived in Exchange stores.</span></span> <span data-ttu-id="e0d81-107">Exchange でアーカイブされたデータは、検索で見つけやすいです。</span><span class="sxs-lookup"><span data-stu-id="e0d81-107">Data archived in Exchange is searchable and discoverable.</span></span> <span data-ttu-id="e0d81-108">Exchange でアーカイブされたデータへのアクセスに関する詳細については、Exchange のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e0d81-108">For details about accessing data that is archived in Exchange, see the Exchange documentation.</span></span>
  
## <a name="exporting-archiving-data-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="e0d81-109">Windows PowerShell コマンドレットを使用して、データのアーカイブをエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="e0d81-109">Exporting Archiving Data by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="e0d81-110">Export-CSArchivingData コマンドレットを使用すると、アーカイブ データをエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="e0d81-110">You can export archived data by using the Export-CSArchivingData cmdlet.</span></span> 
  
<span data-ttu-id="e0d81-p102">次のコマンドは、2012 年 6 月 1 日以降にアーカイブ データベース atl-sql-001.contoso.com に書き込まれたすべてのアーカイブ データをエクスポートします。結果として得られる出力ファイルは、フォルダー C:\ArchivingExports に保存されます。</span><span class="sxs-lookup"><span data-stu-id="e0d81-p102">The following command exports all the archiving data written to the archiving database atl-sql-001.contoso.com since June 1, 2012. The resulting output file will be stored in the folder C:\ArchivingExports.</span></span>
  
```
Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.contoso.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports"
```

<span data-ttu-id="e0d81-113">次のコマンドは、kenmyer@contoso.com という 1 人のユーザーのアーカイブ データをエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="e0d81-113">The following command exports archiving data for a single user: kenmyer@contoso.com.</span></span> <span data-ttu-id="e0d81-114">これは、UserUri パラメーターの後に、ユーザーの SIP アドレスを含めることによって行われます。</span><span class="sxs-lookup"><span data-stu-id="e0d81-114">This is done by including the UserUri parameter followed by the user's SIP address.</span></span> <span data-ttu-id="e0d81-115">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="e0d81-115">For example:</span></span> 
  
```
Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.contoso.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports" -UserUri "sip:kenmyer@contoso.com"
```

<span data-ttu-id="e0d81-116">詳細については、 [.eml という](https://docs.microsoft.com/powershell/module/skype/export-csarchivingdata?view=skype-ps)コマンドレットのヘルプ トピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e0d81-116">For more information, see the help topic for the [Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/export-csarchivingdata?view=skype-ps) cmdlet.</span></span>
  

