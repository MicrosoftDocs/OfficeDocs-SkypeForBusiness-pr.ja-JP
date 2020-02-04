---
title: 'Lync Server 2013: フロント エンド プールに関連付けられたエッジ プールの変更'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Changing the Edge pool associated with a Front End pool
ms:assetid: 369468c7-2c0b-48cc-bbc3-825dad7b85aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688023(v=OCS.15)
ms:contentKeyID: 49733613
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 736ed552a51182102310f4e10eb28472b251eb22
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729897"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changing-the-edge-pool-associated-with-a-front-end-pool-in-lync-server-2013"></a>Lync Server 2013 でのフロント エンド プールに関連付けられたエッジ プールの変更

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-09-21_

エッジプールがダウンしていても、同じサイトのフロントエンドプールがまだ実行されている場合は、失敗したエッジプールが復元されるまで、別のサイトでエッジプールを使用するようにフロントエンドプールを設定する必要があります。

<div>

## <a name="changing-the-edge-pool-associated-with-a-front-end-pool"></a>フロントエンドプールに関連付けられているエッジプールの変更

1.  [Topology Builder] で、変更する必要があるフロントエンドプールの名前に移動します。

2.  プールを右クリックし、[プロパティの**編集**] をクリックします。

3.  [**関連付け**] セクションの [ **Edge プールの関連付け (メディアコンポーネントの場合)**] で、ドロップダウンボックスを使用して、このフロントエンドプールを関連付けるエッジプールを選択します。

4.  **[OK]** をクリックします。

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 でのエッジ サーバーの障害復旧](lync-server-2013-edge-server-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

