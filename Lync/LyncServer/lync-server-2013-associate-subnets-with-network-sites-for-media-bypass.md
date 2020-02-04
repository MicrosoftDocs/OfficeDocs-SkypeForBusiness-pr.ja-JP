---
title: 'Lync Server 2013: サブネットをメディアバイパス用のネットワークサイトと関連付ける'
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
ms.openlocfilehash: dd45daa964b51639c7fe1db3ff10e334e21641f2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722797"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="associate-subnets-with-network-sites-for-media-bypass-in-lync-server-2013"></a>Lync Server 2013 で、サブネットをメディアバイパスのネットワークサイトと関連付ける

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-09-12_

<div>


> [!NOTE]  
> このトピックでは、メディアバイパスのグローバル設定を構成しており、メディアをバイパスするためにネットワーク領域とネットワークサイトを構成していることを前提としています。



</div>

ネットワーク内のすべてのサブネットは、特定のネットワークサイトと関連付けられている必要があります。 これは、エンドポイントが配置されているネットワークサイトを特定するためにサブネット情報が使用されるためです。 セッション内の両方の当事者の場所がわかっている場合は、メディアのバイパスによって、処理のためにメディアの送信先を決定することができます。

メディアのバイパスには、サブネットとネットワークサイトを関連付けるための特別な要件はありません。 トポロジのサブネットとネットワークサイトの間の関連付けを作成するには、「 [Lync Server 2013 でサブネットとネットワークサイトを関連付ける](lync-server-2013-associate-a-subnet-with-a-network-site.md)」の手順に従います。

<div>

## <a name="next-steps-create-bandwidth-policy-profiles"></a>次の手順: 帯域幅ポリシープロファイルを作成する

サブネットをメディアバイパス用のネットワークサイトと関連付けると、メディアバイパスの目的で、サブネットを良好な接続性を持つユーザーに分類する1つまたは複数の帯域幅ポリシープロファイルを作成する必要があります。 帯域幅の制約がないネットワークサイトを含むネットワーク領域内のすべてのサブネットは、接続性が高く、そのため、これらのサブネットはメディアのバイパスを使用できます。

帯域幅ポリシープロファイルを構成する手順については、「 [Lync Server 2013 で帯域幅ポリシープロファイルを作成](lync-server-2013-create-bandwidth-policy-profiles.md)する」を参照してください。

</div>

</div>

<span> </span>

</div>

</div>

</div>

