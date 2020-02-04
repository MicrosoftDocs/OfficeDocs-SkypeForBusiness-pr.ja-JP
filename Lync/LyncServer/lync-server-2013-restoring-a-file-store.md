---
title: 'Lync Server 2013: ファイルストアを復元する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring a file store
ms:assetid: 89916fc6-31d3-4c7f-9eaf-c02584761ef4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202180(v=OCS.15)
ms:contentKeyID: 51541491
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c013159de83d258273e381dd54556bcceec056f7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723567"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-a-file-store-in-lync-server-2013"></a><span data-ttu-id="95972-102">Lync Server 2013 でのファイルストアの復元</span><span class="sxs-lookup"><span data-stu-id="95972-102">Restoring a file store in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="95972-103">_**最終更新日:** 2013-02-18_</span><span class="sxs-lookup"><span data-stu-id="95972-103">_**Topic Last Modified:** 2013-02-18_</span></span>

<span data-ttu-id="95972-104">標準エディション用のファイルストアは、通常 Standard Edition サーバーにあります。</span><span class="sxs-lookup"><span data-stu-id="95972-104">File Stores for Standard Edition are typically located on the Standard Edition server.</span></span> <span data-ttu-id="95972-105">Enterprise Edition のファイルストアは、通常はファイルサーバーまたはクラスターにあります。</span><span class="sxs-lookup"><span data-stu-id="95972-105">File Stores for Enterprise Edition are typically located on a file server or cluster.</span></span> <span data-ttu-id="95972-106">次の手順では、ファイルストアを復元する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="95972-106">The following procedure describes how to restore a File Store.</span></span>

<div>

## <a name="to-restore-a-file-store"></a><span data-ttu-id="95972-107">ファイルストアを復元するには</span><span class="sxs-lookup"><span data-stu-id="95972-107">To restore a File Store</span></span>

1.  <span data-ttu-id="95972-108">ファイルストアに障害が発生した場合は、該当する\\ファイルストアを $Backup からファイルサーバーまたは Standard Edition サーバー上のファイルストアの場所にコピーして、フォルダーを共有します。</span><span class="sxs-lookup"><span data-stu-id="95972-108">If a File Store fails, copy the appropriate File Store from $Backup\\ to the File Store location on the file server or Standard Edition server, and then share the folder.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="95972-109">復元されたファイルストアのパスとファイル名は、バックアップされたファイルストアとまったく同じである必要があります。これにより、ファイルを使用するコンポーネントがアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="95972-109">The path and file name for the restored File Store should be exactly the same as the backed up File Store, so that components that use the files can access them.</span></span>

    
    </div>

2.  <span data-ttu-id="95972-110">必要に応じて、ファイルストアのアクセス制御リスト (Acl) を設定します。</span><span class="sxs-lookup"><span data-stu-id="95972-110">If necessary, set the access control lists (ACLs) for the File Store.</span></span> <span data-ttu-id="95972-111">コマンド ラインで次を入力します。</span><span class="sxs-lookup"><span data-stu-id="95972-111">At the command line, type:</span></span>
    
        Enable-CsTopology
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="95972-112">この手順を実行する必要があるのは、復元プロセスでトポロジビルダーを実行していない場合のみです。</span><span class="sxs-lookup"><span data-stu-id="95972-112">You need to perform this step only if you have not otherwise run Topology Builder during your restoration process.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

