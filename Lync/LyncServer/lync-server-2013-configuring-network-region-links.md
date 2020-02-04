---
title: 'Lync Server 2013: ネットワーク領域のリンクを構成する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring network region links
ms:assetid: 952bc93e-e6aa-4539-85c7-2b15f14eb382
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182551(v=OCS.15)
ms:contentKeyID: 48184829
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5d069bb5215fc977a35481a916f49e86fa644284
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743477"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-network-region-links-in-lync-server-2013"></a>Lync Server 2013 でのネットワーク領域のリンクの構成

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-11-01_

通話受付制御 (CAC) の一部として、2つのネットワーク領域間のリンクを構成することができます。 ネットワーク内の領域は、物理ワイドエリアネットワーク (WAN) 接続によってリンクされています。 Lync Server コントロールパネルを使用して、2つのネットワーク領域間のリンクを定義し、これらの地域間の音声およびビデオ接続の帯域幅の制限を設定することができます。 既存のネットワーク領域へのリンクの削除の詳細については、「 [Lync Server 2013 でのネットワーク領域のリンクの削除](lync-server-2013-deleting-network-region-links.md)」を参照してください。

<div>

## <a name="to-create-a-network-region-link"></a>ネットワーク領域のリンクを作成するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。 Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。

3.  左側のナビゲーションバーで [**ネットワーク構成**] をクリックし、[**地域] リンク**をクリックします。

4.  [**地域] リンク**ページで、[**新規**] をクリックします。

5.  [**新しい地域] リンク**で、[**名前**] フィールドに値を入力します。
    
    <div>
    

    > [!NOTE]  
    > この値は、Lync Server 2013 の展開内で一意である必要があります。

    
    </div>

6.  [ **Network region \#1** ] ボックスの一覧で、リンクする2つの領域のいずれかを選択します。

7.  [ **Network region \#2** ] ボックスの一覧で、リンクする他の地域を選択します。 この領域は、ネットワーク領域\#1 で選択した地域とは異なる必要があります。

8.  省略これらの地域間の音声通話やビデオ通話に帯域幅の制限を設定する場合は、[**帯域幅ポリシー** ] ドロップダウンリストから帯域幅ポリシーのプロファイルを選択します。

9.  [**コミット**] をクリックします。

</div>

<div>

## <a name="to-modify-a-network-region-link"></a>ネットワーク領域のリンクを変更するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。 Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。

3.  左側のナビゲーションバーで [**ネットワーク構成**] をクリックし、[**地域] リンク**をクリックします。

4.  [**地域] リンク**ページで、変更する地域のリンクをクリックします。

5.  [**編集**] メニューの [**詳細の表示**] をクリックします。

6.  [**範囲の編集] リンク**では、リンクされている地域、またはこのリンクの帯域幅ポリシープロファイルを変更することができます。

7.  [**コミット**] をクリックします。

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 でのネットワーク領域リンクの削除](lync-server-2013-deleting-network-region-links.md)  


[新しい-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegionLink)  
[Set-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegionLink)  
[CsNetworkRegionLink を削除する](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegionLink)  
[Get-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>
