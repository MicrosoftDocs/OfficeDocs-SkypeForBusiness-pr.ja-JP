---
title: 'Lync Server 2013: ネットワークの地域情報の表示'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Viewing network region information
ms:assetid: 665740d0-a3ed-460f-8337-5ed945f90589
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688076(v=OCS.15)
ms:contentKeyID: 49733672
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 52baf7c9dca4d663630bbf0cb17384916f5a953e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848170"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="viewing-network-region-information-in-lync-server-2013"></a>Lync Server 2013 でのネットワークの地域情報の表示

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-02-23_

ネットワーク領域は、ネットワークのさまざまな部分を複数の地域で相互接続します。 すべてのネットワーク領域はセントラルサイトと関連付けられている必要があります。 セントラルサイトは、通話受付制御 (CAC) 帯域幅ポリシーサービスが実行されているデータセンターサイトです。 Lync Server コントロールパネルを使用して、ネットワークの領域を表示することができます。 [ネットワーク] 領域には、インターネット経由の代替パスが音声とビデオに接続できるかどうかを決定する設定が含まれます。 既存のネットワーク領域を表示するには、このトピックを参照してください。 既存のネットワーク領域の作成または変更の詳細については、「 [Lync Server 2013 でネットワーク領域を作成または変更](lync-server-2013-creating-or-modifying-network-regions.md)する」を参照してください。

<div>

## <a name="to-view-information-about-a-network-region-with-lync-server-control-panel"></a>Lync Server コントロールパネルを使用してネットワーク領域に関する情報を表示するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。 Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。

3.  左側のナビゲーションバーで [**ネットワーク構成**] をクリックし、[**地域**] をクリックします。

4.  [**領域**] ページで、表示する地域をクリックします。
    
    <div>
    

    > [!NOTE]  
    > 表示できる領域は一度に1つだけです。

    
    </div>

5.  [**編集**] メニューの [**詳細の表示**] をクリックします。

</div>

<div>

## <a name="viewing-network-region-information-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用したネットワーク領域情報の表示

ネットワークの地域情報は、Windows PowerShell と、ユーザーの**入手用の Networkregion**コマンドレットを使って表示できます。 このコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモートセッションから実行できます。 リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、「Lync Server Windows PowerShell のブログ記事」を参照してください[http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。「リモート PowerShell を使用して Microsoft Lync Server 2010 を管理する」を参照してください。

<div>

## <a name="to-view-network-region-information"></a>ネットワークの地域情報を表示するには

  - すべてのネットワーク領域に関する情報を表示するには、Lync Server 管理シェルで次のコマンドを入力し、enter キーを押します。
    
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

詳細については、「 [CsNetworkRegion の取得](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)」コマンドレットのヘルプトピックを参照してください。

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 でのネットワーク領域の作成または変更](lync-server-2013-creating-or-modifying-network-regions.md)  
[Lync Server 2013 で既存のネットワーク領域を削除する](lync-server-2013-deleting-existing-network-regions.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

