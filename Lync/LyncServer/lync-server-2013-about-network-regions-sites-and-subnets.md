---
title: 'Lync Server 2013: ネットワーク領域、サイト、およびサブネットの構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: About network regions, sites, and subnets
ms:assetid: 6662123a-d011-408c-a290-92b2a8589943
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398467(v=OCS.15)
ms:contentKeyID: 48184335
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ef6601a0baafd1226f4e283d62a8cbdb410064ff
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840979"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="about-network-regions-sites-and-subnets-in-lync-server-2013"></a>Lync Server 2013 ネットワーク領域、サイト、およびサブネットの構成

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-02-24_

このセクションで説明されている高度なエンタープライズ Voip 機能は、ネットワーク領域、ネットワークサイト、サブネットの特定の構成要件を共有します。 たとえば、3つの高度な機能を使用するには、トポロジの各サブネットが特定の*ネットワークサイト*と関連付けられ、各ネットワークサイトが*ネットワーク領域*に関連付けられている必要があります。

<div>


> [!IMPORTANT]  
> 通話受付制御、E9、またはメディアバイパスのネットワーク構成を始める前に、 <A href="lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md">「Lync Server 2013 の高度なエンタープライズ voip 機能のネットワーク設定</A>」のネットワーク設定に関する追加情報を確認したことを確認してください。計画ドキュメントのトピックです。 ネットワーク構成の詳細については、主に通話受付制御について詳しくは、「計画ドキュメントの<A href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">Lync Server 2013 での通話受付制御の要件の定義</A>」をご覧ください。



</div>

通話受付管理および E9-1-1 には、ネットワーク サイトの追加構成要件があります。

  - 通話受付管理では、WAN の帯域幅が制限されているサイトごとに*帯域幅ポリシー プロファイル*を指定する必要があります。 通話受付制御の展開を計画している場合は、ネットワークサイトを構成する前に、 [Lync Server 2013 で帯域幅ポリシープロファイルを作成](lync-server-2013-create-bandwidth-policy-profiles.md)する必要があります。

  - E9-1-1 では、サイトごとに *場所のポリシー*を指定する必要があります。 E9 の展開を計画している場合は、ネットワークサイトを構成する前に、 [Lync Server 2013 で位置情報ポリシーを作成](lync-server-2013-create-location-policies.md)する必要があります。

<div>

## <a name="create-or-modify-network-regions-network-sites-and-subnets"></a>ネットワーク領域、ネットワークサイト、サブネットを作成または変更する

次のトピックでは、ネットワーク領域とネットワークサイトを作成または変更し、サブネットをネットワークサイトに関連付ける手順について説明します。 これらのトピックは、特定の高度なエンタープライズ Voip 機能に固有のものではありません。

  - [Lync Server 2013 でネットワークの領域を作成または変更する](lync-server-2013-create-or-modify-a-network-region.md)

  - [Lync Server 2013 でのネットワーク サイトの作成または変更](lync-server-2013-create-or-modify-a-network-site.md)

  - [Lync Server 2013 でのネットワーク サイトとサブネットの関連付け](lync-server-2013-associate-a-subnet-with-a-network-site.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

