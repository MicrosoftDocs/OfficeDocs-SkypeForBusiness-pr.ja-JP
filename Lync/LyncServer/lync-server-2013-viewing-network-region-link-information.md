---
title: 'Lync Server 2013: ネットワーク領域のリンク情報の表示'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Viewing network region link information
ms:assetid: 7b6b2ea2-83d8-4376-afb2-70e5d2cf6444
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688102(v=OCS.15)
ms:contentKeyID: 49733701
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 935d1a98bd4f446ec8861ae8382eb724611a945f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757281"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="viewing-network-region-link-information-in-lync-server-2013"></a>Lync Server 2013 でのネットワーク領域のリンク情報の表示

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-23_

通話受付制御 (CAC) の一部として、2つのネットワーク領域間のリンクを表示することができます。 ネットワーク内の領域は、物理ワイドエリアネットワーク (WAN) 接続によってリンクされています。 Lync Server コントロールパネルを使用して、2つのネットワーク領域間の既存のリンクを表示することができます。 ネットワーク領域へのリンクの作成または変更の詳細については、「 [Lync Server 2013 でのネットワーク領域のリンクの構成](lync-server-2013-configuring-network-region-links.md)」を参照してください。

<div>

## <a name="to-view-a-network-region-link-in-lync-server-control-panel"></a>Lync Server コントロールパネルでネットワーク領域のリンクを表示するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。 Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。

3.  左側のナビゲーションバーで [**ネットワーク構成**] をクリックし、[**地域] リンク**をクリックします。

4.  [**地域] リンク**ページで、表示する地域のリンクをクリックします。
    
    <div>
    

    > [!NOTE]  
    > 一度に表示できるのは、1つの地域のリンクに関する情報だけです。

    
    </div>

5.  [**編集**] メニューの [**詳細の表示**] を選択します。

</div>

<div>

## <a name="viewing-network-region-link-information-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用したネットワーク領域のリンク情報の表示

ネットワークの領域のリンクを表示するには、Windows PowerShell を使用するか、または**CsNetworkRegionLink**コマンドレットを使用します。 このコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモートセッションから実行できます。 リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を[http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)で参照してください。

<div>

## <a name="to-view-network-region-link-information"></a>ネットワーク領域のリンク情報を表示するには

  - すべてのネットワーク領域のリンクに関する情報を表示するには、Lync Server 管理シェルで次のコマンドを入力し、enter キーを押します。
    
        Get-CsNetworkRegionLink
    
    このコマンドは、次のような情報を返します。
    
        Identity            : NorthwestToCalifornia
        BWPolicyProfileID   :
        NetworkRegionLinkID : NorthwestToCalifornia
        NetworkRegionID1    : Pacific Northwest
        NetworkRegionID2    : California

</div>

詳細については、「 [CsNetworkRegionLink の入手](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)」を参照してください。

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 でネットワークサイトリンクを構成する](lync-server-2013-configuring-network-site-links.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

