---
title: 'Lync Server 2013: IP アドレスの種類をエッジ サーバーに展開する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploy IP address types on an Edge Server
ms:assetid: 6e2fe7e8-6e90-4d1a-8fc5-e3be92c46571
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204984(v=OCS.15)
ms:contentKeyID: 48184435
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ece4b55f42958916876539f05b951e862e0d493f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729667"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploy-ip-address-types-on-an-edge-server-for-lync-server-2013"></a>IP アドレスの種類を Lync Server 2013 のエッジ サーバーに展開する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-06-14_

トポロジビルダーを使用して、次の手順を実行して、エッジサーバーに IP アドレスの種類を展開します。

<div>

## <a name="to-deploy-ip-address-types-on-an-edge-server"></a>エッジ サーバー上に IP アドレスの種類を展開するには

1.  [トポロジビルダー] の [**エッジプール**] で、プール内のサーバーを右クリックし、[**プロパティの編集**] を選択します。 (または、サーバーを選択し、[**アクション**] メニューの [**プロパティの編集**] をクリックします)。

2.  [**プロパティの編集**] ウィンドウで、サポートする IP アドレス構成を選択します。次の図に、内部インターフェイスおよび外部インターフェイスのデュアル スタック構成を示します。
    
    **デュアル スタック エッジ サーバー内部インターフェイス**
    
    ![Lync Server の [全般] プロパティページ](images/JJ204984.5b0883ee-b9f2-4a21-91a9-3286d0beb63b(OCS.15).png "Lync Server の [全般] プロパティページ")
    
    **デュアル スタック エッジ サーバー外部インターフェイス**
    
    ![Lync Server の次ホップ/外部構成ページ](images/JJ204984.2aa00ce2-ba50-40aa-bbf1-78636016daf9(OCS.15).png "Lync Server の次ホップ/外部構成ページ")

3.  選択したアドレスの種類で、それぞれ適切な内部アドレスと外部アドレスを指定する必要があります。

</div>

</div>

<span> </span>

</div>

</div>

</div>

