---
title: 'Lync Server 2013: メディアバイパスのためにサブネットをネットワークサイトに関連付ける'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Associate subnets with network sites for media bypass
ms:assetid: 5bc632b7-1446-470f-b332-48ea0ca4d1fd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398401(v=OCS.15)
ms:contentKeyID: 48184244
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e74f007accc53158a1f541dbe4ac6aa821cd8be4
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149186"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="associate-subnets-with-network-sites-for-media-bypass-in-lync-server-2013"></a>Lync Server 2013 でのメディアバイパスのためにサブネットをネットワークサイトに関連付ける

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-12_

<div>


> [!NOTE]  
> ここでは、メディア バイパス グローバル設定を構成しており、メディア バイパスのネットワーク地域とネットワーク サイトを構成していることを前提としています。



</div>

ネットワーク内のすべてのサブネットが、特定のネットワーク サイトに関連付けられている必要があります。 これは、サブネット情報を使用して、エンドポイントが存在するネットワーク サイトを判断するためです。 セッション内の両方のユーザーの場所が認識されている場合、メディア バイパスはメディアの送信先を判断して処理を進めることができます。

メディア バイパスには、サブネットをネットワーク サイトに関連付けるための特別な要件はありません。 トポロジ内のサブネットとネットワークサイトの間の関連付けを作成するには、「 [Lync Server 2013 のネットワークサイトにサブネットを関連付ける](lync-server-2013-associate-a-subnet-with-a-network-site.md)」の手順に従ってください。

<div>

## <a name="next-steps-create-bandwidth-policy-profiles"></a>次のステップ:  帯域幅ポリシー プロファイルの作成

サブネットをメディア バイパスのネットワーク サイトに関連付けたら、メディア バイパスのために、サブネットを接続が良好なサブネットと良好でないサブネットに区分する、1 つ以上の帯域幅ポリシー プロファイルを作成する必要があります。帯域幅制限のないネットワーク サイトが含まれたネットワーク地域内のサブネットはすべて接続が良好であるため、それらのサブネットではメディア バイパスを使用できます。

帯域幅ポリシープロファイルを構成する手順については、「 [Lync Server 2013 での帯域幅ポリシープロファイルの作成](lync-server-2013-create-bandwidth-policy-profiles.md)」を参照してください。

</div>

</div>

<span> </span>

</div>

</div>

</div>

