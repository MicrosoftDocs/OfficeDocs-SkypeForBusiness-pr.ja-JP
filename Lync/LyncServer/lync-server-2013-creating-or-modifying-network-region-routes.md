---
title: 'Lync Server 2013: ネットワーク領域ルートの作成または変更'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Creating or modifying network region routes
ms:assetid: 76993daa-76c2-4cec-8363-de8aebef0145
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521016(v=OCS.15)
ms:contentKeyID: 48184540
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d877de116cc2cf3e0c3354bb6e53d69c211cb482
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740187"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="creating-or-modifying-network-region-routes-in-lync-server-2013"></a>Lync Server 2013 でのネットワーク領域ルートの作成または変更

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-08_

通話受付制御 (CAC) 構成内のすべての領域は、他のすべての領域にアクセスするための何らかの手段を持っている必要があります。 地域のリンクでは、地域間の接続について帯域幅の制限を設定していますが、物理的なリンクも示しています。ルートによって、ある領域から別の領域に接続するリンク先のパスが決定されます。 Lync Server コントロールパネルを使用して、ネットワーク領域ルートを構成することができます。 Lync Server コントロールパネルでは、ネットワーク領域ルートの作成、変更、または削除を行うことができます。 ネットワーク領域ルートを作成または変更するには、このトピックを使用します。 既存のネットワーク領域ルートの削除の詳細については、「 [Lync Server 2013 で既存のネットワーク領域ルートを削除](lync-server-2013-deleting-existing-network-region-routes.md)する」を参照してください。

<div>

## <a name="to-create-a-network-region-route"></a>ネットワーク領域ルートを作成するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。 Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。

3.  左側のナビゲーションバーで [**ネットワーク構成**] をクリックし、[**地域ルート**] をクリックします。

4.  [**地域ルート**] ページで、[**新規**] をクリックします。

5.  [**新しい地域ルート**] で、[**名前**] フィールドに値を入力します。
    
    <div>
    

    > [!NOTE]  
    > この値は、Microsoft Lync Server 2013 の展開内で一意である必要があります。

    
    </div>

6.  [ **Network region \#1** ] ドロップダウンリストから、このルートによって接続される2つの領域のいずれかを選択します。

7.  [ **Network region \#2** ] ドロップダウンリストから、このルートの他の地域を選択します。 この領域は、ネットワーク領域\#1 で選択した地域とは異なる必要があります。

8.  [**ネットワークの領域のリンク**] リストボックスを使って、そのルートに地域のリンクを追加します。 [**追加**] ボタンをクリックして、[**地域] リンク**ページを表示します。 このルートに追加する地域のリンクをクリックして、[ **OK]** をクリックします。
    
    <div>
    

    > [!NOTE]  
    > [<STRONG>追加</STRONG>] ボタンをクリックして、さらにリンクを追加するか、リンクを選択して [<STRONG>削除</STRONG>] をクリックし、リンクを削除します。

    
    </div>

9.  [**コミット**] をクリックします。

</div>

<div>

## <a name="to-modify-a-network-region-route"></a>ネットワークの領域ルートを変更するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。 Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。

3.  左側のナビゲーションバーで [**ネットワーク構成**] をクリックし、[**地域ルート**] をクリックします。

4.  [**地域ルート**] ページで、変更する地域ルートをクリックします。

5.  [**編集**] メニューの [**詳細の表示**] をクリックします。

6.  [**範囲ルートの編集**] で、このルートによって参加している地域と、ルートに関連付けられている地域リンクを変更することができます。

7.  [**コミット**] をクリックします。

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 での既存のネットワーク領域ルートの削除](lync-server-2013-deleting-existing-network-region-routes.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

