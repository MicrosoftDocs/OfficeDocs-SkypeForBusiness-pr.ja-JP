---
title: 'Lync Server 2013: ファイルストアのバックアップ'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Backing up file stores
ms:assetid: 1a7f4e93-aa3d-461e-878e-2c572baa1293
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202167(v=OCS.15)
ms:contentKeyID: 51541449
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e61c9a70477d18ebdacaf9233bbbb0693bb74a2e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044999"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backing-up-file-stores-in-lync-server-2013"></a><span data-ttu-id="7d3bb-102">Lync Server 2013 でのファイルストアのバックアップ</span><span class="sxs-lookup"><span data-stu-id="7d3bb-102">Backing up file stores in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7d3bb-103">_**トピックの最終更新日:** 2013-02-17_</span><span class="sxs-lookup"><span data-stu-id="7d3bb-103">_**Topic Last Modified:** 2013-02-17_</span></span>

<span data-ttu-id="7d3bb-104">Lync Server ファイルストアのバックアップには、Lync Server コンポーネントによって使用されるすべてのファイルとフォルダーが含まれます。</span><span class="sxs-lookup"><span data-stu-id="7d3bb-104">Backing up the Lync Server File Stores includes all the files and folders used by Lync Server components.</span></span>

<div>

## <a name="to-back-up-file-stores"></a><span data-ttu-id="7d3bb-105">ファイル ストアをバックアップするには</span><span class="sxs-lookup"><span data-stu-id="7d3bb-105">To back up File Stores</span></span>

1.  <span data-ttu-id="7d3bb-106">Lync Server ファイルストアの特定の場所を検索するには、トポロジビルダーを開き、[**ファイルストア**] ノードを確認します。</span><span class="sxs-lookup"><span data-stu-id="7d3bb-106">To find the specific locations of your Lync Server File Stores, open Topology Builder and look in the **File stores** node.</span></span>

2.  <span data-ttu-id="7d3bb-107">Robocopy または別のファイルシステム管理ツールを使用して、各\\ファイルストアを $Backup ファイルストアにコピーします。</span><span class="sxs-lookup"><span data-stu-id="7d3bb-107">Use Robocopy or another file system management tool to copy each File Store to $Backup\\filestore.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

