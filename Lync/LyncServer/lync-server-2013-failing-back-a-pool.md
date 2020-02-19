---
title: 'Lync Server 2013: プールのフェールバック'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Failing back a pool
ms:assetid: 6232b644-ef57-4c9c-abec-14ff8ffc9fe7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204945(v=OCS.15)
ms:contentKeyID: 48184289
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e14cca1c42e6e8ab6a0b64c883658cfc5c6a5374
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134583"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="failing-back-a-pool-in-lync-server-2013"></a><span data-ttu-id="a39e7-102">Lync Server 2013 でのプールのフェールバック</span><span class="sxs-lookup"><span data-stu-id="a39e7-102">Failing back a pool in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a39e7-103">_**トピックの最終更新日:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="a39e7-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="a39e7-104">障害が起きたプール (この例では Pool1) がオンラインに戻ったら、次の手順を実行して、展開を通常の状態に稼働状態に戻します。</span><span class="sxs-lookup"><span data-stu-id="a39e7-104">After the pool that experienced the disaster is back online (that is, Pool1 in this example), take the following steps to restore your deployment to regular working status.</span></span>

<span data-ttu-id="a39e7-p101">フェールバック プロセスは完了するまで数分かかることに注意してください。参考として、20,000 名のユーザーのプールでは、最大 60 分かかることが予想されます。</span><span class="sxs-lookup"><span data-stu-id="a39e7-p101">Note that the failback process takes several minute to complete.  For reference, it is expected to take up to 60 minutes for a pool of 20,000 users.</span></span>

1.  <span data-ttu-id="a39e7-107">次のコマンドレットを入力して、もともと Pool1 に属していて Pool2 にフェールオーバーされたユーザーをフェールバックします。</span><span class="sxs-lookup"><span data-stu-id="a39e7-107">Fail back the users who were originally homed in Pool1 and have been failed over to Pool2 by typing the following cmdlet:</span></span>
    
        Invoke-CsPoolFailback -PoolFQDN <Pool1 FQDN> -Verbose

<span data-ttu-id="a39e7-108">それ以外の操作は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="a39e7-108">No other steps are necessary.</span></span> <span data-ttu-id="a39e7-109">中央管理サーバーで障害が発生した場合は、Pool2 のままにしておくことができます。</span><span class="sxs-lookup"><span data-stu-id="a39e7-109">If you failed over the Central Management Server, you can leave it in Pool2.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

