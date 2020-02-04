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
ms.openlocfilehash: 91e1dca7ffc210e9b44913f21846726f7a776912
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756181"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failing-back-a-pool-in-lync-server-2013"></a><span data-ttu-id="43243-102">Lync Server 2013 でのプールのフェールバック</span><span class="sxs-lookup"><span data-stu-id="43243-102">Failing back a pool in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="43243-103">_**最終更新日:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="43243-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="43243-104">障害が発生したプールがオンラインに戻る (この例では Pool1 である) 場合は、次の手順を実行して、展開を通常の作業状態に戻します。</span><span class="sxs-lookup"><span data-stu-id="43243-104">After the pool that experienced the disaster is back online (that is, Pool1 in this example), take the following steps to restore your deployment to regular working status.</span></span>

<span data-ttu-id="43243-105">フェイルバックプロセスが完了するまでに数分かかることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="43243-105">Note that the failback process takes several minute to complete.</span></span><span data-ttu-id="43243-106">参照の場合、2万ユーザーのプールには最大60分かかることが予想されます。</span><span class="sxs-lookup"><span data-stu-id="43243-106">  For reference, it is expected to take up to 60 minutes for a pool of 20,000 users.</span></span>

1.  <span data-ttu-id="43243-107">最初に Pool1 をホームにし、次のコマンドレットを入力して、Pool2 にフェイルオーバーしているユーザーをフェールバックします。</span><span class="sxs-lookup"><span data-stu-id="43243-107">Fail back the users who were originally homed in Pool1 and have been failed over to Pool2 by typing the following cmdlet:</span></span>
    
        Invoke-CsPoolFailback -PoolFQDN <Pool1 FQDN> -Verbose

<span data-ttu-id="43243-108">その他の手順は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="43243-108">No other steps are necessary.</span></span> <span data-ttu-id="43243-109">中央管理サーバーで障害が発生した場合は、Pool2 にそのままにしておくことができます。</span><span class="sxs-lookup"><span data-stu-id="43243-109">If you failed over the Central Management Server, you can leave it in Pool2.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

