---
title: 'Lync Server 2013: 場所のポリシーをネットワークサイトに追加する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Add a location policy to a network site
ms:assetid: 43bfab8a-3d6b-4ca4-8425-879fd910502e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425936(v=OCS.15)
ms:contentKeyID: 48183980
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c9ee6b5ba89cef592e137104df9e80d9373b5f02
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840955"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="add-a-location-policy-to-a-network-site-in-lync-server-2013"></a>Lync Server 2013 でネットワークサイトに位置情報ポリシーを追加する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-02-24_

次の例は、 [Lync Server 2013 の [場所ポリシーの作成](lync-server-2013-create-location-policies.md)] で定義されている**redmond**の場所ポリシーを既存のネットワークサイトに追加する方法と、 **redmond**の場所ポリシーを使用する新しいネットワークサイトを作成する方法を示しています。

ネットワークサイトの操作の詳細については、次のコマンドレットの Lync Server 管理シェルに関するドキュメントを参照してください。

  - **新しい-CsNetworkSite**

  - **Get-CsNetworkSite**

  - **Set-CsNetworkSite**

  - **CsNetworkSite の削除**

<div>

## <a name="to-assign-a-location-policy-to-an-existing-network-site"></a>場所のポリシーを既存のネットワーク サイトに割り当てるには

1.  Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。

2.  既存のネットワーク サイトを変更するには、以下のコマンドレットを実行します。
    
    **Redmond** とマークされている場所のポリシーを、**Redmond** という名前の既存のネットワーク サイトに割り当てます。
    
        Set-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"

</div>

<div>

## <a name="to-assign-a-location-policy-to-a-new-network-site"></a>場所のポリシーを新しいネットワーク サイトに割り当てるには

1.  Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。

2.  新しいネットワーク サイトを作成するには、以下のコマンドレットを実行します。
    
    ネットワーク地域の新しいネットワーク サイトを作成して、**Redmond** とマークされた場所のポリシーを割り当てます。
    
        New-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"

</div>

</div>

<span> </span>

</div>

</div>

</div>

