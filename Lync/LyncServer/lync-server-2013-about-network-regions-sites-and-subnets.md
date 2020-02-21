---
title: 'Lync Server 2013: ネットワーク地域、サイト、およびサブネットについて'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: About network regions, sites, and subnets
ms:assetid: 6662123a-d011-408c-a290-92b2a8589943
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398467(v=OCS.15)
ms:contentKeyID: 48184335
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c8e4ee7d3f5a8976f8a4eee972be2d995f89c36c
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42199300"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="about-network-regions-sites-and-subnets-in-lync-server-2013"></a>Lync Server 2013 のネットワーク地域、サイト、およびサブネットについて

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-24_

このセクションで説明する高度なエンタープライズ VoIP の各機能は、ネットワーク地域、ネットワーク サイト、およびサブネットの特定の構成要件を共有します。 たとえば、3 つの高度な機能のいずれでも、トポロジの各サブネットが特定の*ネットワーク サイト*に関連付けられていて、各ネットワーク サイトは*ネットワーク地域*に関連付けられている必要があります。

<div>


> [!IMPORTANT]  
> 通話受付管理、E9-1-1、またはメディアバイパスのネットワーク構成を開始する前に、「計画」のドキュメントの「 <A href="lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md">Lync Server 2013 の高度なエンタープライズ voip 機能のネットワーク</A>設定に関するその他の情報を確認してください。 通話受付管理に関する基本的なネットワーク構成の詳細については、「計画」のドキュメントの「 <A href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">Lync Server 2013 での通話受付管理の要件の定義</A>」を参照してください。



</div>

通話受付管理および E9-1-1 には、ネットワーク サイトの追加構成要件があります。

  - 通話受付管理では、WAN の帯域幅が制限されているサイトごとに*帯域幅ポリシー プロファイル*を指定する必要があります。 通話受付管理を展開することを計画している場合は、ネットワークサイトを構成する前に、 [Lync Server 2013 で帯域幅ポリシープロファイルを作成](lync-server-2013-create-bandwidth-policy-profiles.md)する必要があります。

  - E9-1-1 では、サイトごとに*場所のポリシー*を指定する必要があります。 E9-1-1 の展開を計画している場合は、ネットワークサイトを構成する前に、 [Lync Server 2013 で場所のポリシーを作成](lync-server-2013-create-location-policies.md)する必要があります。

<div>

## <a name="create-or-modify-network-regions-network-sites-and-subnets"></a>ネットワーク地域、ネットワーク サイト、サブネットの作成または変更

次のトピックには、ネットワーク地域およびネットワーク サイトを作成または変更するステップや、サブネットをネットワーク サイトに関連付けるステップが記載されています。 これらは、特定の高度なエンタープライズ VoIP 機能に固有のトピックではありません。

  - [Lync Server 2013 でネットワーク地域を作成または変更する](lync-server-2013-create-or-modify-a-network-region.md)

  - [Lync Server 2013 でのネットワークサイトの作成または変更](lync-server-2013-create-or-modify-a-network-site.md)

  - [Lync Server 2013 でのサブネットとネットワークサイトの関連付け](lync-server-2013-associate-a-subnet-with-a-network-site.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

