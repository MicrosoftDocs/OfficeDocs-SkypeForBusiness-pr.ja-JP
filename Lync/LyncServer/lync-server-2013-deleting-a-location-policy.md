---
title: 'Lync Server 2013: 場所のポリシーの削除'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting a location policy
ms:assetid: 8ca9ba10-f45f-435a-b39c-519d251e9085
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688125(v=OCS.15)
ms:contentKeyID: 49733724
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 34a71670bb9d4ffa9db67b594d17c330880998c3
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048988"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deleting-a-location-policy-in-lync-server-2013"></a>Lync Server 2013 での場所のポリシーの削除

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-10_

Lync Server 2013 では、場所のポリシーを使用して、強化された 9-1-1 (E9-1-1) の機能に関連する設定と、ユーザーまたは連絡先の場所の設定を適用できます。 場所のポリシーには、ユーザーを E9-1-1 に対して有効にするかどうか、および有効にする場合、緊急電話の動作を指定します。 たとえば、場所ポリシーを使用して、緊急電話の番号 (米国の場合は 911)、社内セキュリティに自動的に通知するかどうか、および通話をルーティングする方法を定義できます。

Lync Server 2013 コントロールパネルの [**ネットワーク構成**] グループから、場所のポリシーを構成できます。 Lync Server コントロールパネルから、場所のポリシーを表示、作成、変更、または削除することができます。 場所のポリシーを削除するには次の手順を使用します。 場所ポリシーの作成または変更の詳細については、「 [Lync Server 2013 での場所のポリシーの作成または変更](lync-server-2013-creating-or-modifying-a-location-policy.md)」を参照してください。

<div>

## <a name="to-delete-a-location-policy"></a>場所のポリシーを削除するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。 Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで [**ネットワーク構成**] をクリックし、[**場所のポリシー**] をクリックします。

4.  [**場所のポリシー**] ページで、削除する場所のポリシーを選択します。
    
    <div>
    

    > [!NOTE]  
    > 1 つ以上の場所のポリシーを一度に削除できます。 これを実行するには、Ctrl キーを押しながら、複数のポリシーを選択します。 また、すべてのポリシーを選択するには、[<STRONG>編集</STRONG>] メニューの [<STRONG>すべて選択</STRONG>] をクリックします。

    
    </div>

5.  [**編集**] メニューの [**削除**] をクリックします。

6.  [**OK**] をクリックします。
    
    <div>
    

    > [!IMPORTANT]  
    > グローバルの場所のポリシーを削除することはできません。 グローバルのポリシーの削除を試みると、警告メッセージが表示され、ポリシーはそのポリシーの既定値にリセットされます。

    
    </div>

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 での場所のポリシーの作成または変更](lync-server-2013-creating-or-modifying-a-location-policy.md)  
[Lync Server 2013 での場所ポリシー情報の表示](lync-server-2013-viewing-location-policy-information.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

