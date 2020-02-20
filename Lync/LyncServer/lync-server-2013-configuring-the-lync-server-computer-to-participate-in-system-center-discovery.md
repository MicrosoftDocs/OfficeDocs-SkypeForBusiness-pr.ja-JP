---
title: Lync Server コンピューターをシステムセンターの検出に参加するように構成する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring the Lync Server computer to participate in System Center discovery
ms:assetid: 2f9c9cb0-3120-4571-9cd2-657c2123fe21
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204776(v=OCS.15)
ms:contentKeyID: 48183731
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6b8e95ead01c89f33346a66a8212245c2350894f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154269"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-the-lync-server-2013-computer-to-participate-in-system-center-discovery"></a>Lync Server 2013 コンピューターを System Center discovery に参加するように構成する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-20_

System Center operations Manager の検出プロセスに新しい Lync Server エージェントが参加するようにするには、System Center Operations Manager コンソールがインストールされている各コンピューターで次の手順を実行する必要があります。

1.  [**管理**] タブで、[**管理対象のエージェント**] をクリックします。

2.  コンピューターの名前を右クリックし、[**プロパティ**] をクリックします。[**プロパティ**] ダイアログ ボックスの [**セキュリティ**] タブで、[**このエージェントをプロキシとして動作させ、他のコンピューター上の管理オブジェクトを検出する**] を選択し、[**OK**] をクリックします。

手順 2. が完了したら、正常性エージェント サービスを再起動します (サービスを再起動すると、強制的に新しいコンピューターの検出が実行されます。サービスを再起動しないと、System Center Operations Manager によって新しいコンピューターが検出されるまでに 4 時間かかる場合があります)。サービスを再起動した後、そのコンピューター上の Operations Manager のイベント ログに、エラー イベントが記録されていないことを確認します。

</div>

<span> </span>

</div>

</div>

</div>

