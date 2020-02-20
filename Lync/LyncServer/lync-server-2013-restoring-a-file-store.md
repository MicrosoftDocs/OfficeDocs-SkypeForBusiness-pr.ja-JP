---
title: 'Lync Server 2013: ファイルストアの復元'
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
ms.openlocfilehash: 409d22b6a0c2d762e39603a1c8eda5ce11cb5433
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144764"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="restoring-a-file-store-in-lync-server-2013"></a><span data-ttu-id="e4379-102">Lync Server 2013 でのファイルストアの復元</span><span class="sxs-lookup"><span data-stu-id="e4379-102">Restoring a file store in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e4379-103">_**トピックの最終更新日:** 2013-02-18_</span><span class="sxs-lookup"><span data-stu-id="e4379-103">_**Topic Last Modified:** 2013-02-18_</span></span>

<span data-ttu-id="e4379-104">Standard Edition のファイルストアは、通常、Standard Edition サーバーにあります。</span><span class="sxs-lookup"><span data-stu-id="e4379-104">File Stores for Standard Edition are typically located on the Standard Edition server.</span></span> <span data-ttu-id="e4379-105">Enterprise Edition のファイル ストアは、通常、ファイル サーバーまたはクラスター上に配置されています。</span><span class="sxs-lookup"><span data-stu-id="e4379-105">File Stores for Enterprise Edition are typically located on a file server or cluster.</span></span> <span data-ttu-id="e4379-106">次の手順では、ファイルストアを復元する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="e4379-106">The following procedure describes how to restore a File Store.</span></span>

<div>

## <a name="to-restore-a-file-store"></a><span data-ttu-id="e4379-107">ファイル ストアを復元するには</span><span class="sxs-lookup"><span data-stu-id="e4379-107">To restore a File Store</span></span>

1.  <span data-ttu-id="e4379-108">ファイルストアが失敗した場合は、適切なファイルストア\\を $Backup からファイルサーバーまたは Standard Edition サーバー上のファイルストアの場所にコピーして、そのフォルダーを共有します。</span><span class="sxs-lookup"><span data-stu-id="e4379-108">If a File Store fails, copy the appropriate File Store from $Backup\\ to the File Store location on the file server or Standard Edition server, and then share the folder.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="e4379-109">復元されたファイルストアのパスおよびファイル名は、バックアップされたファイルストアと正確に一致する必要があるため、ファイルを使用するコンポーネントはそれらにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="e4379-109">The path and file name for the restored File Store should be exactly the same as the backed up File Store, so that components that use the files can access them.</span></span>

    
    </div>

2.  <span data-ttu-id="e4379-110">必要に応じて、ファイルストアのアクセス制御リスト (Acl) を設定します。</span><span class="sxs-lookup"><span data-stu-id="e4379-110">If necessary, set the access control lists (ACLs) for the File Store.</span></span> <span data-ttu-id="e4379-111">コマンドラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="e4379-111">At the command line, type:</span></span>
    
        Enable-CsTopology
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e4379-112">この手順は、復元処理中にトポロジビルダーを実行しない場合にのみ実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e4379-112">You need to perform this step only if you have not otherwise run Topology Builder during your restoration process.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

