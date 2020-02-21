---
title: 'Lync Server 2013: バックアップサービスを使用した会議コンテンツの復元'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring conference contents using the Backup Service
ms:assetid: 3e0f18ec-7319-4c07-a59b-2938e7787bc9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688030(v=OCS.15)
ms:contentKeyID: 49733620
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 22159536999c06c992ace25df51ad6e869e0fd40
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42208593"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="restoring-conference-contents-using-the-backup-service-in-lync-server-2013"></a><span data-ttu-id="4dcb8-102">Lync Server 2013 でのバックアップサービスを使用した会議コンテンツの復元</span><span class="sxs-lookup"><span data-stu-id="4dcb8-102">Restoring conference contents using the Backup Service in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4dcb8-103">_**トピックの最終更新日:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="4dcb8-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="4dcb8-p101">フロントエンド プールのファイル ストアに格納されている会議情報が使用できなくなった場合は、この情報を復元する必要があります。これにより、プールのユーザーが会議データを保持できます。会議データを失ったフロントエンド プールと他のフロントエンド プールがペアになっている場合は、バックアップ サービスを使用してデータを復元できます。</span><span class="sxs-lookup"><span data-stu-id="4dcb8-p101">If the conference information stored in the file store of a Front End pool becomes unavailable. you must restore this information so that users homed on the pool retain their conference data. If the Front End pool which has lost conference data is paired with another Front End pool, you can use the Backup Service to restore the data.</span></span>

<span data-ttu-id="4dcb8-p102">プール全体で障害が発生し、ユーザーをバックアップ プールにフェールオーバーする必要がある場合も、このタスクを実行します。これらのユーザーが元のプールにフェールオーバーされるときに、この手順を使用して、会議コンテンツも元のプールにコピーする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4dcb8-p102">You must also perform this task if an entire pool has failed and you have to fail over its users to a backup pool. When these users are failed back over to their original pool, you must use this procedure to copy their conference content back to their original pool as well.</span></span>

<span data-ttu-id="4dcb8-109">Pool1 と Pool2 がペアで、Pool1 の会議データが失われたとします。</span><span class="sxs-lookup"><span data-stu-id="4dcb8-109">Assume that Pool1 is paired with Pool2, and the conference data in Pool1 is lost.</span></span> <span data-ttu-id="4dcb8-110">次のコマンドレットを使用して、バックアップサービスを呼び出してコンテンツを復元できます。</span><span class="sxs-lookup"><span data-stu-id="4dcb8-110">You can use the following cmdlet to invoke the Backup Service to restore the contents:</span></span>

    Invoke-CsBackupServiceSync -PoolFqdn <Pool2 FQDN> -BackupModule ConfServices.DataConf

<span data-ttu-id="4dcb8-p104">会議コンテンツのサイズによっては、コンテンツを復元するのに時間がかかる場合があります。次のコマンドレットを使用すると、プロセスの状態を確認できます。</span><span class="sxs-lookup"><span data-stu-id="4dcb8-p104">Restoring the conference contents may take some time, depending on their size. You can use the following cmdlet to check the process status:</span></span>

    Get-CsBackupServiceStatus -PoolFqdn <Pool2 FQDN> -BackupModule ConfServices.DataConf

<span data-ttu-id="4dcb8-113">このコマンドレットがデータ会議モジュールに対して安定状態の値を返すと、プロセスは完了です。</span><span class="sxs-lookup"><span data-stu-id="4dcb8-113">The process is done when this cmdlet returns a value of Steady State for the data conference module.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

