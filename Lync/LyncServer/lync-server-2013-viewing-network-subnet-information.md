---
title: 'Lync Server 2013: ネットワークサブネット情報の表示'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Viewing network subnet information
ms:assetid: 46f165f2-efe3-4cc1-9fee-a78b7f2ed41e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688044(v=OCS.15)
ms:contentKeyID: 49733636
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a157746e40de8f4793fab24e7e91121779d7602e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848159"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="viewing-network-subnet-information-in-lync-server-2013"></a>Lync Server 2013 でのネットワークサブネット情報の表示

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-02-23_

次の手順を使用して、ネットワークサブネットを表示できます。 Lync Server コントロールパネルから、ネットワークサブネットの作成、変更、または削除を行うことができます。 ネットワークサブネットの作成または変更の詳細については、「 [Lync Server 2013 でネットワークサブネットを作成または変更](lync-server-2013-create-or-modify-network-subnets.md)する」を参照してください。

<div>

## <a name="to-view-a-network-subnet"></a>ネットワークサブネットを表示するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。 Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。

3.  左側のナビゲーションバーで [**ネットワーク構成**] をクリックし、[**サブネット**] をクリックします。

4.  [ **Subnet** ] ページで、表示するサブネットをクリックします。
    
    <div>
    

    > [!NOTE]  
    > 一度に1つのサブネットしか表示できません。

    
    </div>

5.  [**編集**] メニューの [**詳細の表示**] をクリックします。

</div>

<div>

## <a name="viewing-network-subnet-configuration-information-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用したネットワークサブネット構成情報の表示

ネットワークサブネットの情報を表示するには、Windows PowerShell を使用するか、または CsNetworkSubnet コマンドレットを使用します。 このコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモートセッションから実行できます。 リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、「Lync Server Windows PowerShell のブログ記事」を参照してください[http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。「リモート PowerShell を使用して Microsoft Lync Server 2010 を管理する」を参照してください。

<div>

## <a name="to-view-network-subnet-information"></a>ネットワークサブネット情報を表示するには

  - すべてのネットワークサブネットに関する情報を表示するには、Lync Server 管理シェルで次のコマンドを入力し、enter キーを押します。
    
        Get-CsNetworkSubnet
    
    次のような情報が表示されます。
    
        Identity      : 172.11.15.0
        MaskBits      : 28
        Description   :
        NetworkSiteID : Redmond
        SubnetID      : 172.11.15.0

</div>

詳細については、「 [CsNetworkSubnet の取得](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet)」コマンドレットのヘルプトピックを参照してください。

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 でネットワークサブネットを作成または変更する](lync-server-2013-create-or-modify-network-subnets.md)  
[Lync Server 2013 でのネットワークサブネットの削除](lync-server-2013-deleting-network-subnets.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

