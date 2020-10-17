---
title: 'Lync Server 2013: ネットワーク地域リンク情報の表示'
description: 'Lync Server 2013: ネットワーク地域リンク情報の表示。'
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
ms.openlocfilehash: 0134ded9942ebda91050c1f7b0bbcfef018451a3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565363"
---
# <a name="viewing-network-region-link-information-in-lync-server-2013"></a>Lync Server 2013 でのネットワーク地域リンク情報の表示

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-23_

通話受付管理 (CAC) の一環として、2 つのネットワーク地域間のリンクを表示できます。 ネットワーク内の地域は、物理的なワイド エリア ネットワーク (WAN) 接続を経由してリンクされます。 Lync Server コントロールパネルを使用して、2つのネットワーク地域間の既存のリンクを表示することができます。 ネットワーク地域リンクの作成または変更の詳細については、「 [Lync Server 2013 でのネットワーク地域リンクの構成](lync-server-2013-configuring-network-region-links.md)」を参照してください。

<div>

## <a name="to-view-a-network-region-link-in-lync-server-control-panel"></a>Lync Server コントロールパネルでネットワーク地域リンクを表示するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。 Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで [**ネットワーク構成**] をクリックし、[**地域リンク**] をクリックします。

4.  [**地域リンク**] ページで、表示する地域リンクをクリックします。
    
    <div>
    

    > [!NOTE]  
    > 一度に情報を表示できる地域リンクは 1 つだけです。

    
    </div>

5.  [**編集**] メニューの [**詳細の表示**] を選択します。

</div>

<div>

## <a name="viewing-network-region-link-information-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用してネットワーク地域リンク情報を表示する

Windows PowerShell と **Get-CsNetworkRegionLink** コマンドレットを使用して、ネットワーク地域リンクを表示することができます。 このコマンドレットは、Lync Server 2013 管理シェルまたは Windows PowerShell のリモートセッションから実行できます。 リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を[https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)で参照してください。

<div>

## <a name="to-view-network-region-link-information"></a>ネットワーク地域リンク情報を表示するには

  - すべてのネットワーク地域リンクに関する情報を表示するには、Lync Server 管理シェルで次のコマンドを入力し、enter キーを押します。
    
        Get-CsNetworkRegionLink
    
    このコマンドは、次のような情報を返します。
    
        Identity            : NorthwestToCalifornia
        BWPolicyProfileID   :
        NetworkRegionLinkID : NorthwestToCalifornia
        NetworkRegionID1    : Pacific Northwest
        NetworkRegionID2    : California

</div>

詳細については、「[Get-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)」を参照してください。

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 でのネットワークサイトリンクの構成](lync-server-2013-configuring-network-site-links.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

