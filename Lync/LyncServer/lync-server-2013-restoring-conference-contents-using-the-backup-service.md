---
title: 'Lync Server 2013: バックアップ サービスを使用した会議コンテンツの復元'
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
ms.openlocfilehash: 873ca354ca592eb6bc317b579a0a6f5008e6a172
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733197"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-conference-contents-using-the-backup-service-in-lync-server-2013"></a><span data-ttu-id="bbe2c-102">Lync Server 2013 でのバックアップ サービスを使用した会議コンテンツの復元</span><span class="sxs-lookup"><span data-stu-id="bbe2c-102">Restoring conference contents using the Backup Service in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bbe2c-103">_**最終更新日:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="bbe2c-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="bbe2c-104">フロントエンドプールのファイルストアに保存されている会議情報が利用できなくなった場合。</span><span class="sxs-lookup"><span data-stu-id="bbe2c-104">If the conference information stored in the file store of a Front End pool becomes unavailable.</span></span> <span data-ttu-id="bbe2c-105">この情報を復元すると、プールをホームにしているユーザーが会議データを保持するようになります。</span><span class="sxs-lookup"><span data-stu-id="bbe2c-105">you must restore this information so that users homed on the pool retain their conference data.</span></span> <span data-ttu-id="bbe2c-106">会議データを紛失したフロントエンドプールが別のフロントエンドプールとペアリングされている場合は、バックアップサービスを使ってデータを復元することができます。</span><span class="sxs-lookup"><span data-stu-id="bbe2c-106">If the Front End pool which has lost conference data is paired with another Front End pool, you can use the Backup Service to restore the data.</span></span>

<span data-ttu-id="bbe2c-107">また、プール全体で障害が発生し、ユーザーがバックアッププールにフェールオーバーしなければならない場合は、このタスクを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bbe2c-107">You must also perform this task if an entire pool has failed and you have to fail over its users to a backup pool.</span></span> <span data-ttu-id="bbe2c-108">これらのユーザーが元のプールにフェールバックされた場合は、この手順を使用して、会議のコンテンツを元のプールにもコピーし直す必要があります。</span><span class="sxs-lookup"><span data-stu-id="bbe2c-108">When these users are failed back over to their original pool, you must use this procedure to copy their conference content back to their original pool as well.</span></span>

<span data-ttu-id="bbe2c-109">Pool1 が Pool2 とペアリングされていることを前提としていますが、Pool1 の会議データは失われます。</span><span class="sxs-lookup"><span data-stu-id="bbe2c-109">Assume that Pool1 is paired with Pool2, and the conference data in Pool1 is lost.</span></span> <span data-ttu-id="bbe2c-110">次のコマンドレットを使用して、バックアップサービスを呼び出して内容を復元できます。</span><span class="sxs-lookup"><span data-stu-id="bbe2c-110">You can use the following cmdlet to invoke the Backup Service to restore the contents:</span></span>

    Invoke-CsBackupServiceSync -PoolFqdn <Pool2 FQDN> -BackupModule ConfServices.DataConf

<span data-ttu-id="bbe2c-111">会議の内容の復元には、サイズによっては時間がかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="bbe2c-111">Restoring the conference contents may take some time, depending on their size.</span></span> <span data-ttu-id="bbe2c-112">プロセスの状態を確認するには、次のコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="bbe2c-112">You can use the following cmdlet to check the process status:</span></span>

    Get-CsBackupServiceStatus -PoolFqdn <Pool2 FQDN> -BackupModule ConfServices.DataConf

<span data-ttu-id="bbe2c-113">プロセスは、このコマンドレットがデータ会議モジュールの安定した状態の値を返すときに実行されます。</span><span class="sxs-lookup"><span data-stu-id="bbe2c-113">The process is done when this cmdlet returns a value of Steady State for the data conference module.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

