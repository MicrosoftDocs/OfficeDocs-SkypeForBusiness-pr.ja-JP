---
title: 'Lync Server 2013: ネットワーク地域リンクの構成'
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
ms.openlocfilehash: 5cf838e59c95528a1c32870d90f5c2e2babf10fc
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42198400"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-network-region-links-in-lync-server-2013"></a>Lync Server 2013 でのネットワーク地域リンクの構成

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-11-01_

通話受付管理 (CAC) の一環として、2 つのネットワーク地域間のリンクを公正できます。 ネットワーク内の地域は、物理的なワイド エリア ネットワーク (WAN) 接続を経由してリンクされます。 Lync Server コントロールパネルを使用して、2つのネットワーク地域間のリンクを定義し、これらの地域間の音声およびビデオ接続に対する帯域幅制限を設定することができます。 既存のネットワーク地域リンクの削除の詳細については、「 [Lync Server 2013 でのネットワーク地域リンクの削除](lync-server-2013-deleting-network-region-links.md)」を参照してください。

<div>

## <a name="to-create-a-network-region-link"></a>ネットワーク地域リンクを作成するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。 Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで [**ネットワーク構成**] をクリックし、[**地域リンク**] をクリックします。

4.  [**地域リンク**] ページで、[**新規**] をクリックします。

5.  [**新しい地域] リンク**で、[**名前**] フィールドに値を入力します。
    
    <div>
    

    > [!NOTE]  
    > この値は、Lync Server 2013 展開内で一意である必要があります。

    
    </div>

6.  [**ネットワーク地域\#1** ] ドロップダウンリストから、リンクする2つの地域のいずれかを選択します。

7.  [**ネットワーク地域\#2** ] ドロップダウンリストから、リンクする他の地域を選択します。 この地域は、[ネットワーク地域\#1 に選択した地域とは別のものにする必要があります。

8.  オプションこれらの地域間の音声またはビデオ通話に帯域幅制限を設定する場合は、[**帯域幅ポリシー** ] ドロップダウンリストから帯域幅ポリシーのプロファイルを選択します。

9.  [**確定**] をクリックします。

</div>

<div>

## <a name="to-modify-a-network-region-link"></a>ネットワーク地域リンクを変更するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。 Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで [**ネットワーク構成**] をクリックし、[**地域リンク**] をクリックします。

4.  [**地域リンク**] ページで、変更する地域リンクをクリックします。

5.  [**編集**] メニューの [**詳細の表示**] をクリックします。

6.  [**地域の編集] リンク**では、リンクされている地域またはこのリンクの帯域幅ポリシープロファイルを変更できます。

7.  [**確定**] をクリックします。

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 でのネットワーク地域リンクの削除](lync-server-2013-deleting-network-region-links.md)  


[新しい-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegionLink)  
[設定-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegionLink)  
[-CsNetworkRegionLink の削除](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegionLink)  
[Get-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>
