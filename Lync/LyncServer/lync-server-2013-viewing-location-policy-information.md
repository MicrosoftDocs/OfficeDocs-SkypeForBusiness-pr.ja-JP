---
title: 'Lync Server 2013: 場所ポリシー情報の表示'
description: 'Lync Server 2013: 場所ポリシー情報の表示。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Viewing location policy information
ms:assetid: 14e41bcb-ea0a-49c2-99b3-1f61fc34416d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520954(v=OCS.15)
ms:contentKeyID: 48183489
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2fecc5de5fb71014a1641038e9e09afba0e90cdb
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565423"
---
# <a name="viewing-location-policy-information-in-lync-server-2013"></a>Lync Server 2013 での場所ポリシー情報の表示

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-11-01_

Lync Server 2013 では、場所のポリシーを使用して、強化された 9-1-1 (E9-1-1) の機能に関連する設定と、ユーザーまたは連絡先の場所の設定を適用できます。 場所のポリシーには、ユーザーを E9-1-1 に対して有効にするかどうか、および有効にする場合、緊急電話の動作を指定します。 たとえば、場所ポリシーを使用して、緊急電話の番号 (米国の場合は 911)、社内セキュリティに自動的に通知するかどうか、および通話をルーティングする方法を定義できます。

Lync Server 2013 コントロールパネルの [ **ネットワーク構成** ] グループから、場所のポリシーを構成できます。 Lync Server コントロールパネルから、場所のポリシーを表示、作成、変更、または削除することができます。 場所ポリシーに関する情報を表示するには次の手順を使用します。 場所ポリシーの作成または変更の詳細については、「 [Lync Server 2013 での場所のポリシーの作成または変更](lync-server-2013-creating-or-modifying-a-location-policy.md)」を参照してください。

<div>

## <a name="to-view-information-about-a-location-policy"></a>場所ポリシーに関する情報を表示するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。 Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで [**ネットワーク構成**] をクリックし、[**場所のポリシー**] をクリックします。

4.  [**場所のポリシー**] ページで、変更する場所のポリシーを選択します。

5.  [**編集**] メニューの [**詳細の表示**] をクリックします。
    
    <div>
    

    > [!NOTE]  
    > 同時に表示できるのは 1 つの場所ポリシーのみです。

    
    </div>

「グローバル」という名前の単一ポリシーが、既定で存在します。このポリシーは、削除することも名前を変更することもできません。 ただし、グローバル ポリシーの内容を変更することはできます。 このポリシーは、サイト ポリシーまたはユーザー単位のポリシーが作成されていない場合に限り、すべてのユーザーおよび連絡先に適用されます。 ユーザー単位のポリシーは、特定のユーザーに適用する必要があります。

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 での場所のポリシーの作成または変更](lync-server-2013-creating-or-modifying-a-location-policy.md)  
[Lync Server 2013 での場所のポリシーの作成](lync-server-2013-create-location-policies.md)  
[Lync Server 2013 でのネットワークサイトの作成または変更](lync-server-2013-create-or-modify-a-network-site.md)  


[新しい-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsLocationPolicy)  
[設定-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsLocationPolicy)  
[削除-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsLocationPolicy)  
[-CsLocationPolicy の取得](https://docs.microsoft.com/powershell/module/skype/Get-CsLocationPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

