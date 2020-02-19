---
title: 'Lync Server 2013: ネットワーク地域情報の表示'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Viewing network region information
ms:assetid: 665740d0-a3ed-460f-8337-5ed945f90589
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688076(v=OCS.15)
ms:contentKeyID: 49733672
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8ba46c4ab3ed7fd6930faf359bc964605285a953
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138148"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="viewing-network-region-information-in-lync-server-2013"></a>Lync Server 2013 でのネットワーク地域情報の表示

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-23_

ネットワーク地域は、複数の地理的な領域にまたがるネットワークのさまざまな部分を相互接続します。 すべてのネットワーク地域は、セントラル サイトと関連付ける必要があります。 このセントラル サイトは、通話受付管理 (CAC) 帯域幅ポリシー サービスが実行されているデータ センター サイトです。 Lync Server コントロールパネルを使用して、ネットワーク地域を表示することができます。 ネットワーク地域には、音声とビデオの接続にインターネットを使用する代替パスを許可するかどうかの設定が含まれます。 このトピックを使用して、既存のネットワーク地域を表示します。 既存のネットワーク地域の作成または変更の詳細については、「 [Lync Server 2013 でのネットワーク地域の作成または変更](lync-server-2013-creating-or-modifying-network-regions.md)」を参照してください。

<div>

## <a name="to-view-information-about-a-network-region-with-lync-server-control-panel"></a>Lync Server コントロールパネルを使用してネットワーク地域に関する情報を表示するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。 Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで [**ネットワーク構成**] をクリックし、[**地域**] をクリックします。

4.  [**地域**] ページで、表示する地域をクリックします。
    
    <div>
    

    > [!NOTE]  
    > 一度に 1 つの地域のみを表示できます。

    
    </div>

5.  [**編集**] メニューの [**詳細の表示**] をクリックします。

</div>

<div>

## <a name="viewing-network-region-information-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用したネットワーク地域情報の表示

Windows PowerShell と**Get-CsNetworkRegion**コマンドレットを使用して、ネットワーク地域情報を表示できます。 このコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモートセッションから実行できます。 リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を[https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)で参照してください。

<div>

## <a name="to-view-network-region-information"></a>ネットワーク地域情報を表示するには

  - すべてのネットワーク地域に関する情報を表示するには、Lync Server 管理シェルで次のコマンドを入力し、ENTER キーを押します。
    
        Get-CsNetworkRegion
    
    次のような情報が表示されます。
    
        Identity         : Pacific Northwest
        Description      :
        BypassID         : 3b232b84-2c1d-4da2-8181-e9330bafebe9
        CentralSite      : Site:Redmond1
        BWAlternatePaths : {BWPolicyModality=Audio;AlternatePath=True, 
                           BWPolicyModality=Video;AlternatePath=True}
        NetworkRegionID  : Pacific Northwest

</div>

詳細については、[Get-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink) コマンドレットのヘルプ トピックを参照してください。.

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 でのネットワーク地域の作成または変更](lync-server-2013-creating-or-modifying-network-regions.md)  
[Lync Server 2013 の既存のネットワーク領域の削除](lync-server-2013-deleting-existing-network-regions.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

