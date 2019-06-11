---
title: 'Lync Server 2013: 高度なエンタープライズ Voip 機能のネットワーク設定'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Network settings for the advanced Enterprise Voice features
ms:assetid: 7f6de9e4-c8a4-44e4-8d14-21fe8c45283a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398637(v=OCS.15)
ms:contentKeyID: 48184632
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d633d111e9df09cde57b91f32f4592b7f80c9f26
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826508"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="network-settings-for-the-advanced-enterprise-voice-features-in-lync-server-2013"></a>Network settings for the advanced Enterprise Voice features in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-10_

Lync Server には、通話受付制御 (CAC)、緊急サービス (E9)、メディアバイパスという3つの高度なエンタープライズ Voip 機能があります。 これらの機能は、ネットワークサイトを使用して、Lync Server トポロジのネットワーク領域、ネットワークサイト、および各サブネットの特定の構成要件を共有します。 これらの機能の展開の計画について詳しくは、以下をご覧ください。

  - [Lync Server 2013 での通話受付管理の計画](lync-server-2013-planning-for-call-admission-control.md)

  - [Lync Server 2013 での緊急サービス (E9-1-1) の計画](lync-server-2013-planning-for-emergency-services-e9-1-1.md)

  - [Lync Server 2013 でのメディア バイパスの計画](lync-server-2013-planning-for-media-bypass.md)

これらの各機能の展開の詳細については、展開ドキュメントの「 [Lync Server 2013 での高度なエンタープライズ voip 機能の展開](lync-server-2013-deploying-advanced-enterprise-voice-features.md)」を参照してください。

このトピックでは、3つの高度なエンタープライズボイス機能すべてに共通する構成要件の概要について説明します。

<div>

## <a name="network-regions"></a>ネットワーク地域

ネットワーク地域は、通話受付管理 (CAC)、E9-1-1、およびメディア バイパスの構成でのみ使用されるネットワーク ハブまたはネットワーク バックボーンです。

<div>


> [!NOTE]  
> ネットワーク領域は、Lync Server のダイヤルイン会議領域と同じではありません。これは、ダイヤルイン会議アクセス番号を1つまたは複数の Lync Server ダイヤルプランに関連付けるために必要となります。 ダイヤルイン会議の地域の詳細については、計画ドキュメントの「 <A href="lync-server-2013-dial-in-conferencing-requirements.md">Lync Server 2013 でのダイヤルイン会議の要件</A>」を参照してください。



</div>

CAC では、すべてのネットワーク領域に、その地域内のメディアトラフィックを管理する関連付けられた Lync Server セントラルサイトが必要です (つまり、構成したポリシーに基づいて、リアルタイムの音声またはビデオセッションが可能かどうかに関する決定が行われます)。確立されます)。 Lync Server のセントラルサイトは、地理的な場所を示すのではなく、プールまたは一連のプールとして構成されているサーバーの論理グループを表します。 セントラルサイトの詳細については、計画ドキュメントの「 [Lync Server 2013 のリファレンストポロジ](lync-server-2013-reference-topologies.md)」を参照してください。 [サポートされているトポロジ](lync-server-2013-supported-topologies.md)については、サポートドキュメントの「Lync Server 2013」を参照してください。

ネットワークの領域を構成するには、Lync Server コントロールパネルの [**ネットワーク構成**] セクションの [**地域**] タブを使用するか、または、**新しい (** Csnetworkregion) lync Server 管理シェルを実行します。 **** cmdlet. 手順については、展開ドキュメントの「 [Lync server 2013 でネットワーク領域を作成または変更](lync-server-2013-create-or-modify-a-network-region.md)する」を参照するか、「Lync Server 管理シェルのドキュメント」を参照してください。

同じネットワーク領域の定義は、3つの高度なエンタープライズ音声機能によって共有されます。 いずれかの機能にネットワーク地域を既に作成している場合、他の機能に新しいネットワーク地域を作成する必要はありません。 ただし、機能固有の設定を適用するために、既存のネットワーク地域定義を変更することが必要になる場合があります。 たとえば、E9-1-1 (関連付けられた中央サイトは不要) にネットワーク地域を作成しており、通話受付管理を後で展開する場合、中央サイトを指定するには、各ネットワーク地域定義を変更する必要があります。

Lync Server のセントラルサイトをネットワーク領域と関連付けるには、Lync Server コントロールパネルの [**ネットワーク構成**] セクションを使用するか、または**新しい**csnetworkregion を実行するか、またはをセットアップして、[セントラルサイト名] を指定します。 **** Lync Server Management Shell コマンドレット。 手順については、展開ドキュメントの「 [Lync server 2013 でネットワーク領域を作成または変更](lync-server-2013-create-or-modify-a-network-region.md)する」を参照するか、「Lync Server 管理シェルのドキュメント」を参照してください。

</div>

<div>

## <a name="network-sites"></a>ネットワーク サイト

ネットワーク サイトは、ブランチ オフィス、支社、本社などの地理的場所を表します。各ネットワーク サイトは、特定のネットワーク地域に関連付けられている必要があります。

<div>


> [!NOTE]  
> ネットワークサイトは、高度なエンタープライズ Voip 機能によってのみ使用されます。 Lync Server トポロジで構成したブランチサイトとは異なります。 ブランチサイトの詳細については、計画ドキュメントの「 <A href="lync-server-2013-reference-topologies.md">Lync Server 2013 のリファレンストポロジ</A>」を参照してください。 <A href="lync-server-2013-supported-topologies.md">サポートされているトポロジ</A>については、サポートドキュメントの「Lync Server 2013」を参照してください。



</div>

ネットワークサイトを構成し、ネットワーク領域に関連付けるには、Lync Server コントロールパネルの [**ネットワーク構成**] セクションを使用するか、または Lync Server 管理シェルの [**新しい-** csnetworksite] または [ **Set-csnetworksite** ] を実行します。cmdlet. 詳細については、展開ドキュメントの「 [Lync server 2013 でネットワークサイトを作成または変更](lync-server-2013-create-or-modify-a-network-site.md)する」を参照するか、「Lync Server 管理シェルのドキュメント」を参照してください。

</div>

<div>

## <a name="identify-ip-subnets"></a>IP サブネットの特定

ネットワーク管理者と連携して各ネットワーク サイトに割り当てる IP サブネットを決定する必要があります。ネットワーク管理者が既に IP サブネットをネットワーク地域およびネットワーク サイトに分類している場合、作業は大幅に簡略化されます。

この例では、North America 地域の New York サイトに 172.29.80.0/23、157.57.216.0/25、172.29.91.0/23、172.29.81.0/24 の IP サブネットを割り当てることができます。通常はデトロイトで仕事をしている Bob が、トレーニングのためにニューヨークのオフィスに出張する場合、コンピューターを起動してネットワークに接続すると、New York に割り当てられている 4 つの範囲のいずれか (172.29.80.103 など) の IP アドレスがコンピューターで取得されます。

<div>


> [!WARNING]  
> サーバー上のネットワーク構成中に指定された IP サブネットは、メディアのバイパスに適切に使用するために、クライアントコンピューターによって提供される形式と一致する必要があります。 Lync クライアントはローカルの IP アドレスを受け取り、関連付けられたサブネットマスクで IP アドレスをマスクします。 各クライアントに関連付けられているバイパス ID を判断するとき、レジストラーは、各ネットワークサイトに関連付けられた IP サブネットの一覧と、完全一致のためにクライアントによって提供されるサブネットとを比較します。 このため、サーバー上のネットワーク構成中に入力されたサブネットは、仮想サブネットではなく実際のサブネットであることが重要です。 (通話受付制御を展開して、メディアをバイパスしない場合は、仮想サブネットを構成しても、通話受付制御が適切に機能します)。<BR>たとえば、ip アドレスが255.255.255.0 の IP アドレスが172.29.81.57 のコンピューターで Lync クライアントがサインインすると、サブネット172.29.81.0 に関連付けられているバイパス ID が要求されます。 クライアントが仮想サブネットに属していても、サブネットが 172.29.0.0/16 として定義される場合、レジストラーは 172.29.81.0 のサブネットのみを検索するため、これを一致とは見なしません。 そのため、管理者は、Lync クライアント (静的または動的ホスト構成プロトコル (DHCP) によって、ネットワーク構成中にサブネットでプロビジョニングされる) とまったく同じサブネットを入力することが重要です。



</div>

</div>

<div>

## <a name="associating-subnets-with-network-sites"></a>サブネットとネットワーク サイトの関連付け

エンタープライズ ネットワーク内のすべてのサブネットは、ネットワーク サイトに関連付ける必要があります (つまり、すべてのサブネットを地理的場所に関連付ける必要があります)。 サブネットの関連付けを使用すると、高度なエンタープライズボイス機能で、エンドポイントを地理的に見つけることができます。 たとえば、エンドポイントを見つけることにより、CAC では、ネットワーク サイトとの間で送受信されるリアルタイムの音声およびビデオのデータ フローを調整できます。

サブネットとネットワークサイトを関連付けるには、Lync Server コントロールパネルの [**ネットワーク構成**] セクションを使用するか、または Lync Server 管理シェルを使用することができます。 手順については、「展開ドキュメントの[Lync server 2013 でのサブネットのネットワークサイト](lync-server-2013-associate-a-subnet-with-a-network-site.md)への関連付け」を参照するか、「Lync Server 管理シェルのドキュメント」を参照してください。

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 での通話受付管理の計画](lync-server-2013-planning-for-call-admission-control.md)  
[Lync Server 2013 での緊急サービス (E9-1-1) の計画](lync-server-2013-planning-for-emergency-services-e9-1-1.md)  
[Lync Server 2013 でのメディア バイパスの計画](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

