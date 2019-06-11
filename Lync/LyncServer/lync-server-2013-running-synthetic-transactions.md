---
title: 'Lync Server 2013: 代理トランザクションの実行'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Running synthetic transactions
ms:assetid: 2b56c7bd-8956-4fa1-8232-1876b959b258
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720911(v=OCS.15)
ms:contentKeyID: 63969593
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 489b8a02d829f4f12038e3f07559166c1c015b80
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822161"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="running-synthetic-transactions-in-lync-server-2013"></a>Lync Server 2013 での代理トランザクションの実行

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2014-08-18_

通常、代理トランザクションは、次の2つの方法で行われます。 CsHealthMonitoringConfiguration コマンドレットを使用して、各レジストラープールのテストユーザーを設定することができます。 これらのテストユーザーは、代理トランザクションとして使用するように事前に構成されたユーザーのペアです。 (通常、テストアカウントであり、実際のユーザーに属するアカウントではありません)。プールに対して構成されたテストユーザーがいる場合、テストに関係しているユーザーアカウントの id を指定したり、資格情報を指定したりすることなく、そのプールに対して代理トランザクションを実行できます。

または、実際のユーザーアカウントを使用して、代理トランザクションを実行することもできます。 たとえば、2人のユーザーがインスタントメッセージを交換できない場合は、(1 組のテストアカウントではなく) 2 つのユーザーアカウントを使用して代理トランザクションを実行し、問題を診断して解決することができます。 実際のユーザーアカウントを使用して代理トランザクションを実行する場合は、各ユーザーのログオン名とパスワードを指定する必要があります。

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 で監視ノードのテストユーザーと構成設定を構成する](lync-server-2013-configuring-watcher-node-test-users-and-configuration-settings.md)  
[Lync Server 2013 での代理トランザクションの特別なセットアップ手順](lync-server-2013-special-setup-instructions-for-synthetic-transactions.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

