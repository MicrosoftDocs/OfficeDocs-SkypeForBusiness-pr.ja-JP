---
title: 'Lync Server 2013: 高度なエンタープライズ Voip 機能のネットワーク設定'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Network settings for the advanced Enterprise Voice features
ms:assetid: 7f6de9e4-c8a4-44e4-8d14-21fe8c45283a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398637(v=OCS.15)
ms:contentKeyID: 48184632
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f1d6b01009aac5fdaf3d69e24b4137897e70051b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049329"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="network-settings-for-the-advanced-enterprise-voice-features-in-lync-server-2013"></a>Lync Server 2013 の高度なエンタープライズ Voip 機能のネットワーク設定

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-10_

Lync Server には、通話受付管理 (CAC)、緊急サービス (E9-1-1)、メディアバイパスという3つの高度なエンタープライズ Voip 機能があります。 これらの機能は、ネットワーク地域、ネットワークサイト、および Lync Server トポロジ内の各サブネットとネットワークサイトとの関連付けについて、特定の構成要件を共有します。 これらの機能の展開の計画の詳細については、以下を参照してください。

  - [Lync Server 2013 での通話受付管理の計画](lync-server-2013-planning-for-call-admission-control.md)

  - [Lync Server 2013 での緊急サービス (E9-1-1) の計画](lync-server-2013-planning-for-emergency-services-e9-1-1.md)

  - [Lync Server 2013 でのメディアバイパスの計画](lync-server-2013-planning-for-media-bypass.md)

これらの各機能の展開の詳細については、「展開」のドキュメントの「 [Advanced Enterprise Voice features In Lync Server 2013](lync-server-2013-deploying-advanced-enterprise-voice-features.md) 」を参照してください。

このトピックでは、3つの高度なエンタープライズ Voip 機能すべてに共通する構成要件の概要について説明します。

<div>

## <a name="network-regions"></a>ネットワーク地域

ネットワーク地域は、通話受付管理 (CAC)、E9-1-1、およびメディア バイパスの構成でのみ使用されるネットワーク ハブまたはネットワーク バックボーンです。

<div>


> [!NOTE]  
> ネットワーク地域は、Lync server のダイヤルイン会議の地域と同じではありません。これは、ダイヤルイン会議アクセス番号を1つまたは複数の Lync Server ダイヤルプランに関連付けるために必要です。 ダイヤルイン会議の地域の詳細については、「計画」のドキュメントの「 <A href="lync-server-2013-dial-in-conferencing-requirements.md">Lync Server 2013 のダイヤルイン会議の要件</A>」を参照してください。



</div>

CAC では、すべてのネットワーク地域に Lync Server 中央サイトが関連付けられていることが必要です。これは、地域内のメディアトラフィックを管理します (つまり、構成したポリシーに基づいて、リアルタイムの音声またはビデオセッションであるかどうかに関する決定を行います)。確立されます)。 Lync Server 中央サイトは、地理的な場所ではなく、プールまたはプールのセットとして構成されたサーバーの論理グループを表します。 中央サイトの詳細については、「計画」のドキュメントの「 [Reference トポロジ In Lync Server 2013](lync-server-2013-reference-topologies.md) 」を参照してください。 また、「サポート」のドキュメントの「 [Lync Server 2013 でサポートされるトポロジ](lync-server-2013-supported-topologies.md)」を参照してください。

ネットワーク地域を構成するには、Lync Server コントロールパネルの [**ネットワーク構成**] セクションの [**地域**] タブを使用するか、または**新しい-Csnetworkregion**または**Set-csnetworkregion** Lync Server 管理シェルコマンドレットを実行します。 手順については、「展開」のドキュメントの「 [Lync server 2013 でネットワーク地域を作成または変更](lync-server-2013-create-or-modify-a-network-region.md)する」または「Lync Server Management Shell」のドキュメントを参照してください。

同じネットワーク地域定義は、3つの高度なエンタープライズ Voip 機能によって共有されます。 いずれかの機能にネットワーク地域を既に作成している場合、他の機能に新しいネットワーク地域を作成する必要はありません。 ただし、機能固有の設定を適用するために、既存のネットワーク地域定義を変更することが必要になる場合があります。 たとえば、E9-1-1 (関連付けられた中央サイトは不要) にネットワーク地域を作成しており、通話受付管理を後で展開する場合、中央サイトを指定するには、各ネットワーク地域定義を変更する必要があります。

Lync Server 中央サイトをネットワーク地域に関連付けるには、[Lync Server コントロールパネル] の [**ネットワーク構成**] セクションを使用するか、または**新しい-Csnetworkregion**または**Set-Csnetworkregion** Lync Server 管理シェルコマンドレットを実行して、中央サイト名を指定します。 手順については、「展開」のドキュメントの「 [Lync server 2013 でネットワーク地域を作成または変更](lync-server-2013-create-or-modify-a-network-region.md)する」または「Lync Server Management Shell」のドキュメントを参照してください。

</div>

<div>

## <a name="network-sites"></a>ネットワーク サイト

ネットワーク サイトは、ブランチ オフィス、支社、本社などの地理的場所を表します。各ネットワーク サイトは、特定のネットワーク地域に関連付けられている必要があります。

<div>


> [!NOTE]  
> ネットワークサイトは、高度なエンタープライズ Voip 機能によってのみ使用されます。 これらは、Lync Server トポロジで構成したブランチサイトとは異なります。 ブランチサイトの詳細については、「計画」のドキュメントの「 <A href="lync-server-2013-reference-topologies.md">Reference トポロジ In Lync Server 2013</A> 」を参照してください。 また、「サポート」のドキュメントの「 <A href="lync-server-2013-supported-topologies.md">Lync Server 2013 でサポートされるトポロジ</A>」を参照してください。



</div>

ネットワークサイトを構成してネットワーク地域に関連付けるには、Lync Server コントロールパネルの [**ネットワーク構成**] セクションを使用するか、Lync Server 管理シェルの**新しい-Csnetworksite**または**Set-csnetworksite**コマンドレットを実行します。 詳細については、「展開」のドキュメントの「 [Create or modify a network site 2013](lync-server-2013-create-or-modify-a-network-site.md) 」または「Lync Server Management Shell」のドキュメントを参照してください。

</div>

<div>

## <a name="identify-ip-subnets"></a>IP サブネットの特定

ネットワーク管理者と連携して各ネットワーク サイトに割り当てる IP サブネットを決定する必要があります。ネットワーク管理者が既に IP サブネットをネットワーク地域およびネットワーク サイトに分類している場合、作業は大幅に簡略化されます。

この例では、North America 地域の New York サイトに 172.29.80.0/23、157.57.216.0/25、172.29.91.0/23、172.29.81.0/24 の IP サブネットを割り当てることができます。通常はデトロイトで仕事をしている Bob が、トレーニングのためにニューヨークのオフィスに出張する場合、コンピューターを起動してネットワークに接続すると、New York に割り当てられている 4 つの範囲のいずれか (172.29.80.103 など) の IP アドレスがコンピューターで取得されます。

<div>


> [!WARNING]  
> サーバー上のネットワーク構成中に指定された IP サブネットは、メディアバイパスに適切に使用するために、クライアントコンピューターから提供される形式と一致している必要があります。 Lync クライアントは、ローカルの IP アドレスを取得し、関連付けられたサブネットマスクを使用して IP アドレスをマスクします。 各クライアントに関連付けられているバイパス ID を決定するとき、レジストラーは、各ネットワークサイトに関連付けられた IP サブネットと、完全一致のためにクライアントによって提供されたサブネットとを比較します。 このため、サーバー上のネットワーク構成中に入力されたサブネットは、仮想サブネットではなく実際のサブネットであることが重要です。 (通話受付管理を展開し、メディアバイパスを展開しない場合、仮想サブネットを構成していても、通話受付管理が適切に機能します。)<BR>たとえば、IP サブネットマスクが255.255.255.0 の172.29.81.57 の IP アドレスを持つコンピューター上で Lync クライアントがサインインすると、サブネット172.29.81.0 に関連付けられているバイパス ID が要求されます。 クライアントが仮想サブネットに属していても、サブネットが 172.29.0.0/16 として定義される場合、レジストラーは 172.29.81.0 のサブネットのみを検索するため、これを一致とは見なしません。 そのため、管理者は、(静的または動的ホスト構成プロトコル (DHCP) によってネットワーク構成中にサブネットでプロビジョニングされた) Lync クライアントによって提供されるとおりにサブネットを入力することが重要です。



</div>

</div>

<div>

## <a name="associating-subnets-with-network-sites"></a>サブネットとネットワーク サイトの関連付け

エンタープライズ ネットワーク内のすべてのサブネットは、ネットワーク サイトに関連付ける必要があります (つまり、すべてのサブネットを地理的場所に関連付ける必要があります)。 このサブネットの関連付けにより、高度なエンタープライズ Voip 機能がエンドポイントを地理的に特定できるようになります。 たとえば、エンドポイントを見つけることにより、CAC では、ネットワーク サイトとの間で送受信されるリアルタイムの音声およびビデオのデータ フローを調整できます。

サブネットをネットワークサイトに関連付けるには、Lync Server コントロールパネルの [**ネットワーク構成**] セクションを使用するか、または Lync Server 管理シェルを使用できます。 手順については、「展開」のドキュメントの「 [Lync server 2013 でのネットワークサイトへのサブネットの関連付け](lync-server-2013-associate-a-subnet-with-a-network-site.md)」または「Lync Server Management Shell」のドキュメントを参照してください。

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 での通話受付管理の計画](lync-server-2013-planning-for-call-admission-control.md)  
[Lync Server 2013 での緊急サービス (E9-1-1) の計画](lync-server-2013-planning-for-emergency-services-e9-1-1.md)  
[Lync Server 2013 でのメディアバイパスの計画](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

