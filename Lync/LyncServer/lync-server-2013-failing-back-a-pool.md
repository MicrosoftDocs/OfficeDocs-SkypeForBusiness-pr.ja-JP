---
title: 'Lync Server 2013: プールのフェールバック'
description: 'Lync Server 2013: プールのフェールバック。'
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
ms.openlocfilehash: 1c1fc0ea4514d2f951dd936521590d47b809db38
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567743"
---
# <a name="failing-back-a-pool-in-lync-server-2013"></a>Lync Server 2013 でのプールのフェールバック

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-11-01_

障害が起きたプール (この例では Pool1) がオンラインに戻ったら、次の手順を実行して、展開を通常の状態に稼働状態に戻します。

フェールバック プロセスは完了するまで数分かかることに注意してください。参考として、20,000 名のユーザーのプールでは、最大 60 分かかることが予想されます。

1.  次のコマンドレットを入力して、もともと Pool1 に属していて Pool2 にフェールオーバーされたユーザーをフェールバックします。
    
        Invoke-CsPoolFailback -PoolFQDN <Pool1 FQDN> -Verbose

それ以外の操作は必要ありません。 中央管理サーバーで障害が発生した場合は、Pool2 のままにしておくことができます。

</div>

<span> </span>

</div>

</div>

</div>

