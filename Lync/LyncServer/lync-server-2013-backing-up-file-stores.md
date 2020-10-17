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
ms.openlocfilehash: f4971b5df8646f20843569ba653cd7a0c274d501
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48523164"
---
# <a name="backing-up-file-stores-in-lync-server-2013"></a><span data-ttu-id="54d31-102">Lync Server 2013 でのファイルストアのバックアップ</span><span class="sxs-lookup"><span data-stu-id="54d31-102">Backing up file stores in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="54d31-103">_**トピックの最終更新日:** 2013-02-17_</span><span class="sxs-lookup"><span data-stu-id="54d31-103">_**Topic Last Modified:** 2013-02-17_</span></span>

<span data-ttu-id="54d31-104">Lync Server ファイルストアのバックアップには、Lync Server コンポーネントによって使用されるすべてのファイルとフォルダーが含まれます。</span><span class="sxs-lookup"><span data-stu-id="54d31-104">Backing up the Lync Server File Stores includes all the files and folders used by Lync Server components.</span></span>

<div>

## <a name="to-back-up-file-stores"></a><span data-ttu-id="54d31-105">ファイル ストアをバックアップするには</span><span class="sxs-lookup"><span data-stu-id="54d31-105">To back up File Stores</span></span>

1.  <span data-ttu-id="54d31-106">Lync Server ファイルストアの特定の場所を検索するには、トポロジビルダーを開き、[ **ファイルストア** ] ノードを確認します。</span><span class="sxs-lookup"><span data-stu-id="54d31-106">To find the specific locations of your Lync Server File Stores, open Topology Builder and look in the **File stores** node.</span></span>

2.  <span data-ttu-id="54d31-107">Robocopy または別のファイルシステム管理ツールを使用して、各ファイルストアを $Backup ファイルストアにコピーし \\ ます。</span><span class="sxs-lookup"><span data-stu-id="54d31-107">Use Robocopy or another file system management tool to copy each File Store to $Backup\\filestore.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

