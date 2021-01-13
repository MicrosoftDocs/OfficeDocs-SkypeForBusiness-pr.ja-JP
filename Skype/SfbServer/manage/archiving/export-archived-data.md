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
# <a name="export-archived-data-in-skype-for-business-server"></a><span data-ttu-id="1422d-103">Skype for Business Server でアーカイブされたデータをエクスポートする</span><span class="sxs-lookup"><span data-stu-id="1422d-103">Export archived data in Skype for Business Server</span></span>

<span data-ttu-id="1422d-104">**概要:** Skype for Business Server のアーカイブ データをエクスポートする方法について学習します。</span><span class="sxs-lookup"><span data-stu-id="1422d-104">**Summary:** Learn how to export archived data for Skype for Business Server.</span></span>
  
<span data-ttu-id="1422d-105">アーカイブ データベースにアーカイブされたデータは、検索可能または読み取り可能な形式ではありません。ただし **、Export-CsArchivingData** コマンドレットを使用して、データベースからレコードを抽出し、それらを Outlook Electronic Mail (EML) ファイルとして保存できます。</span><span class="sxs-lookup"><span data-stu-id="1422d-105">Data archived in Archiving databases is not searchable or in a readable format, but you can use the **Export-CsArchivingData** cmdlet to extract records from the database and save them as an Outlook Electronic Mail (EML) file.</span></span>
  
<span data-ttu-id="1422d-106">Microsoft Exchange 統合を有効にした場合、データは Exchange ストアにアーカイブされます。</span><span class="sxs-lookup"><span data-stu-id="1422d-106">If you enable Microsoft Exchange integration, data is archived in Exchange stores.</span></span> <span data-ttu-id="1422d-107">Exchange にアーカイブされたデータは検索可能で検出可能です。</span><span class="sxs-lookup"><span data-stu-id="1422d-107">Data archived in Exchange is searchable and discoverable.</span></span> <span data-ttu-id="1422d-108">Exchange にアーカイブされているデータへのアクセスの詳細については、Exchange のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="1422d-108">For details about accessing data that is archived in Exchange, see the Exchange documentation.</span></span>
  
## <a name="exporting-archiving-data-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="1422d-109">Windows PowerShell コマンドレットを使用したアーカイブ データのエクスポート</span><span class="sxs-lookup"><span data-stu-id="1422d-109">Exporting Archiving Data by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="1422d-110">アーカイブされたデータは、次のコマンドレットを使用Export-CSArchivingDataできます。</span><span class="sxs-lookup"><span data-stu-id="1422d-110">You can export archived data by using the Export-CSArchivingData cmdlet.</span></span> 
  
<span data-ttu-id="1422d-111">次のコマンドは、2012 年 6 月 1 atl-sql-001.contoso.comアーカイブ データベースに書き込まれたすべてのアーカイブ データをエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="1422d-111">The following command exports all the archiving data written to the archiving database atl-sql-001.contoso.com since June 1, 2012.</span></span> <span data-ttu-id="1422d-112">結果として得られる出力ファイルは、フォルダー C:\ArchivingExports に保存されます。</span><span class="sxs-lookup"><span data-stu-id="1422d-112">The resulting output file will be stored in the folder C:\ArchivingExports.</span></span>
  
```PowerShell
Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.contoso.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports"
```

<span data-ttu-id="1422d-113">次のコマンドは、1 人のユーザーのアーカイブ データをエクスポートします。kenmyer@contoso.com。</span><span class="sxs-lookup"><span data-stu-id="1422d-113">The following command exports archiving data for a single user: kenmyer@contoso.com.</span></span> <span data-ttu-id="1422d-114">これを実行するには、UserUri パラメーターの後にユーザーの SIP アドレスを指定します。</span><span class="sxs-lookup"><span data-stu-id="1422d-114">This is done by including the UserUri parameter followed by the user's SIP address.</span></span> <span data-ttu-id="1422d-115">例:</span><span class="sxs-lookup"><span data-stu-id="1422d-115">For example:</span></span> 
  
```PowerShell
Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.contoso.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports" -UserUri "sip:kenmyer@contoso.com"
```

<span data-ttu-id="1422d-116">詳細については [、Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/export-csarchivingdata?view=skype-ps) コマンドレットのヘルプ トピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="1422d-116">For more information, see the help topic for the [Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/export-csarchivingdata?view=skype-ps) cmdlet.</span></span>
  

