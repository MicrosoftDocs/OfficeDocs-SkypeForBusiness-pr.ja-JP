---
title: 'Lync Server 2013: 位置情報ポリシー情報の表示'
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
ms.openlocfilehash: 0f68ad38ffbc8bb1b4abdfbf8119add7d9f965e6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757321"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="viewing-location-policy-information-in-lync-server-2013"></a>Lync Server 2013 で位置情報ポリシー情報を表示する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-11-01_

Lync Server 2013 では、位置情報ポリシーを使用して、強化された 9-1-1 (E9) 機能と、ユーザーまたは連絡先の位置設定に関連する設定を適用することができます。 位置情報ポリシーは、ユーザーが E9 に対して有効になっているかどうかを決定し、場合によっては緊急通話の動作を確認します。 たとえば、位置情報ポリシーを使用して、緊急通話 (米国の911など)、企業のセキュリティに自動的に通知するかどうか、および通話のルーティング方法を定義できます。

Lync Server 2013 コントロールパネルの [**ネットワーク構成**] グループから、場所のポリシーを構成できます。 Lync Server コントロールパネルから、場所のポリシーの表示、作成、変更、または削除を行うことができます。 場所のポリシーに関する情報を表示するには、次の手順を使用します。 場所のポリシーの作成または変更の詳細については、「 [Lync Server 2013 で位置情報ポリシーを作成または変更](lync-server-2013-creating-or-modifying-a-location-policy.md)する」を参照してください。

<div>

## <a name="to-view-information-about-a-location-policy"></a>場所のポリシーに関する情報を表示するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。 Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。

3.  左側のナビゲーションバーで [**ネットワーク構成**] をクリックし、[**場所のポリシー**] をクリックします。

4.  [**場所のポリシー** ] ページで、変更する場所のポリシーを選びます。

5.  [**編集**] メニューの [**詳細の表示**] をクリックします。
    
    <div>
    

    > [!NOTE]  
    > 表示できるのは、一度に1つの場所ポリシーに関する情報だけです。

    
    </div>

グローバルと呼ばれる単一のポリシーは既定で存在するため、削除したり名前を変更したりすることはできません。 ただし、グローバルポリシーは変更できます。 このポリシーは、サイトポリシーまたはユーザーごとのポリシーを作成しない限り、すべてのユーザーと連絡先に適用されます。 ユーザーごとのポリシーは、特定のユーザーに適用する必要があります。

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 で位置情報ポリシーを作成または変更する](lync-server-2013-creating-or-modifying-a-location-policy.md)  
[Lync Server 2013 で位置情報のポリシーを作成する](lync-server-2013-create-location-policies.md)  
[Lync Server 2013 でのネットワーク サイトの作成または変更](lync-server-2013-create-or-modify-a-network-site.md)  


[New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsLocationPolicy)  
[Set-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsLocationPolicy)  
[Remove-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsLocationPolicy)  
[Get-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsLocationPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

