---
title: Skype for Business Server の高度エンタープライズ VoIP機能のネットワーク設定
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 7f6de9e4-c8a4-44e4-8d14-21fe8c45283a
description: ネットワーク地域、ネットワーク サイト、IP サブネットについて学習します。 これらすべては、Skype for Business でのメディア バイパスの計画、Skype for Business Server での通話受付管理の計画、または Skype for Business Server エンタープライズ VoIP の Skype for Business Server での緊急サービスの計画を展開するように構成する必要があります。
ms.openlocfilehash: 4cedfa6b425bd120a62997d02548d57ce5d619b4
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51101293"
---
# <a name="network-settings-for-the-advanced-enterprise-voice-features-in-skype-for-business-server"></a>Skype for Business Server の高度エンタープライズ VoIP機能のネットワーク設定

ネットワーク地域、ネットワーク サイト、IP サブネットについて学習します。 これらすべては [、Skype for Business](media-bypass.md)でのメディア バイパスの計画 [、Skype for Business Server](call-admission-control.md)での通話受付管理の計画、または Skype for Business Server エンタープライズ VoIP の Skype for Business [Server](emergency-services.md) での緊急サービスの計画を展開するように構成する必要があります。

Skype for Business Server には [、3](call-admission-control.md)つの高度な エンタープライズ VoIP 機能があります。Skype for Business Server での通話受付制御の計画 [、Skype for Business Server](emergency-services.md)での緊急サービスの計画、および Skype for [Business](media-bypass.md)でのメディア バイパスの計画。 これらの機能は、ネットワーク地域、ネットワーク サイト、および Skype for Business Server トポロジ内の各サブネットとネットワーク サイトとの関連付けに関する特定の構成要件を共有します。

このトピックでは、これら 3 つの高度な機能すべてで一般的な構成要件エンタープライズ VoIPします。

## <a name="network-regions"></a>ネットワーク地域

ネットワーク地域は、通話受付管理 (CAC)、E9-1-1、およびメディア バイパスの構成でのみ使用されるネットワーク ハブまたはネットワーク バックボーンです。

> [!NOTE]
> ネットワーク領域は、Skype for Business Server ダイヤルイン会議地域と同じではありません。これは、ダイヤルイン会議アクセス番号を 1 つ以上の Skype for Business Server ダイヤル プランに関連付ける場合に必要です。 ダイヤルイン会議地域の詳細については、「ダイヤルイン会議の計画 [」を参照してください](/previous-versions/office/lync-server-2013/lync-server-2013-dial-in-conferencing-requirements)。

CAC では、すべてのネットワーク領域に、地域内のメディア トラフィックを管理する Skype for Business Server セントラル サイトが関連付けられている必要があります (つまり、リアルタイムのオーディオセッションまたはビデオ セッションを確立できるかどうかに関して、構成したポリシーに基づいて決定します)。 Skype for Business Server の中央サイトは地理的な場所を表すのではなく、プールまたはプールのセットとして構成されているサーバーの論理的なグループを表します。

ネットワーク領域を構成するには、Skype for Business  Server コントロールパネルの [ネットワーク構成] セクションの [地域] タブを使用するか **、New-CsNetworkRegion** または **Set-CsNetworkRegion** Skype for Business Server Management Shell コマンドレットを実行します。 手順については、「展開」のドキュメントの [「Skype for Business](../../deploy/deploy-enterprise-voice/deploy-network.md) でネットワーク地域、サイト、サブネットを展開する」を参照するか、Skype for Business Server 管理シェルのドキュメントを参照してください。

同じネットワーク領域定義は、3 つの高度な機能エンタープライズ VoIPされます。 いずれかの機能にネットワーク地域を既に作成している場合、他の機能に新しいネットワーク地域を作成する必要はありません。 ただし、機能固有の設定を適用するために、既存のネットワーク地域定義を変更することが必要になる場合があります。 たとえば、E9-1-1 (関連付けられた中央サイトは不要) にネットワーク地域を作成しており、通話受付管理を後で展開する場合、中央サイトを指定するには、各ネットワーク地域定義を変更する必要があります。

Skype for Business Server の中央サイトをネットワーク領域に関連付ける場合は、Skype for  Business Server コントロール パネルの [ネットワーク構成] セクションを使用するか **、New-CsNetworkRegion** コマンドレットまたは **Set-CsNetworkRegion** コマンドレットを実行して、中央サイト名を指定します。 手順については、「展開」のドキュメントの [「Skype for Business](../../deploy/deploy-enterprise-voice/deploy-network.md) でネットワーク地域、サイト、サブネットを展開する」を参照するか、Skype for Business Server 管理シェルのドキュメントを参照してください。

## <a name="network-sites"></a>ネットワーク サイト

ネットワーク サイトは、ブランチ オフィス、支社、本社などの地理的場所を表します。各ネットワーク サイトは、特定のネットワーク地域に関連付けられている必要があります。

> [!NOTE]
> ネットワーク サイトは、高度な機能によってのみエンタープライズ VoIPされます。 これらは、Skype for Business Server トポロジで構成するブランチ サイトと同じではありません。

ネットワーク サイトを構成してネットワーク領域に関連付けるには、Skype for  Business Server コントロール パネルの [ネットワーク構成] セクションを使用するか、Skype for Business Server 管理シェル **New-CsNetworkSite コマンドレットまたは Set-CsNetworkSite** コマンドレットを実行します。  詳細については、「展開」のドキュメントの「Create [or Modify a Network Site」](/previous-versions/office/lync-server-2013/lync-server-2013-create-or-modify-a-network-site) を参照するか、Skype for Business Server Management Shell のドキュメントを参照してください。

## <a name="identify-ip-subnets"></a>IP サブネットの特定

ネットワーク管理者と連携して各ネットワーク サイトに割り当てる IP サブネットを決定する必要があります。ネットワーク管理者が既に IP サブネットをネットワーク地域およびネットワーク サイトに分類している場合、作業は大幅に簡略化されます。

この例では、North America 地域の New York サイトに 172.29.80.0/23、157.57.216.0/25、172.29.91.0/23、172.29.81.0/24 の IP サブネットを割り当てることができます。通常はデトロイトで仕事をしている Bob が、トレーニングのためにニューヨークのオフィスに出張する場合、コンピューターを起動してネットワークに接続すると、New York に割り当てられている 4 つの範囲のいずれか (172.29.80.103 など) の IP アドレスがコンピューターで取得されます。

> [!CAUTION]
> メディア バイパスに適切に使用するには、サーバー上のネットワーク構成中に指定された IP サブネットが、クライアント コンピューターによって提供される形式と一致している必要があります。 Skype for Business クライアントはローカル IP アドレスを取得し、IP アドレスを関連付けられたサブネット マスクでマスクします。 各クライアントに関連付けられているバイパス ID を決定する場合、レジストラーは、各ネットワーク サイトに関連付けられている IP サブネットの一覧と、クライアントが完全に一致するために提供するサブネットとを比較します。 このため、サーバーのネットワーク構成中に入力されたサブネットは、仮想サブネットではなく実際のサブネットである必要があります。 (通話受付管理を展開するが、メディア バイパスを展開しない場合は、仮想サブネットを構成しても通話受付制御が正しく機能します)。たとえば、IP サブネット マスクが 255.255.255.0 の IP アドレスが 172.29.81.57 のコンピューターに Skype for Business クライアントがサインインすると、サブネット 172.29.81.0 に関連付けられているバイパス ID が要求されます。 クライアントが仮想サブネットに属していても、サブネットが 172.29.0.0/16 として定義される場合、レジストラーは 172.29.81.0 のサブネットのみを検索するため、これを一致とは見なしません。 したがって、管理者が Skype for Business クライアントによって提供されるとおりにサブネットを入力することが重要です (これは、静的または動的ホスト構成プロトコル (DHCP) によって、ネットワーク構成中にサブネットでプロビジョニングされます)。

## <a name="associating-subnets-with-network-sites"></a>サブネットとネットワーク サイトの関連付け

エンタープライズ ネットワーク内のすべてのサブネットは、ネットワーク サイトに関連付ける必要があります (つまり、すべてのサブネットを地理的場所に関連付ける必要があります)。 このサブネットの関連付けにより、高度なエンタープライズ VoIP機能を使用してエンドポイントを地理的に特定できます。 たとえば、エンドポイントを見つけることにより、CAC では、ネットワーク サイトとの間で送受信されるリアルタイムの音声およびビデオのデータ フローを調整できます。

サブネットをネットワーク サイトに関連付けるには、Skype  for Business Server コントロール パネルの [ネットワーク構成] セクションを使用するか、Skype for Business Server 管理シェルを使用できます。 手順については、「展開」の [ドキュメントの「](/previous-versions/office/lync-server-2013/lync-server-2013-associate-a-subnet-with-a-network-site) サブネットをネットワーク サイトに関連付ける」を参照するか、Skype for Business Server 管理シェルのドキュメントを参照してください。

## <a name="see-also"></a>関連項目

[Skype for Business Server で通話受付管理を計画する](call-admission-control.md)

[Skype for Business Server で緊急サービスを計画する](emergency-services.md)

[Skype for Business でメディア バイパスを計画する](media-bypass.md)