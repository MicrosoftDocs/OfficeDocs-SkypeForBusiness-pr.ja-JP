---
title: ネットワーク内の高度なエンタープライズ VoIP機能のネットワークSkype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 7f6de9e4-c8a4-44e4-8d14-21fe8c45283a
description: ネットワーク地域、ネットワーク サイト、IP サブネットについて学習します。 これらのすべては、Skype for Business、Skype for Business Server の通話受付管理の計画、または Skype for Business Server エンタープライズ VoIP の Skype for Business Server での緊急サービスの計画を展開するように構成する必要があります。
ms.openlocfilehash: 97cf81bb3efa9aa5d4b8717018232d479fcbf2c3
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58608004"
---
# <a name="network-settings-for-the-advanced-enterprise-voice-features-in-skype-for-business-server"></a>ネットワーク内の高度なエンタープライズ VoIP機能のネットワークSkype for Business Server

ネットワーク地域、ネットワーク サイト、IP サブネットについて学習します。 これらのすべては、Skype for Business の [メディア バイパスの計画] [、Skype for Business Server](media-bypass.md)での通話受付管理の計画、または Skype for Business Server エンタープライズ VoIP の[Skype for Business Server](call-admission-control.md)での緊急サービスの計画を展開するように構成[する](emergency-services.md)必要があります。

Skype for Business Serverには[、Skype for Business Server エンタープライズ VoIP](call-admission-control.md)での通話受付管理の計画、Skype for Business Server での緊急サービスの計画、および[](emergency-services.md)Skype for Business でのメディア バイパス[の計画](media-bypass.md)という 3 つの高度な機能があります。 これらの機能は、ネットワーク領域、ネットワーク サイト、および Skype for Business Server トポロジ内の各サブネットとネットワーク サイトとの関連付けに関する特定の構成要件を共有します。

このトピックでは、これら 3 つの高度な機能すべてに共通する構成要件エンタープライズ VoIPします。

## <a name="network-regions"></a>ネットワーク地域

ネットワーク地域は、通話受付管理 (CAC)、E9-1-1、およびメディア バイパスの構成でのみ使用されるネットワーク ハブまたはネットワーク バックボーンです。

> [!NOTE]
> ネットワーク領域は、Skype for Business Server ダイヤルイン会議地域と同じではありません。これは、ダイヤルイン会議アクセス番号を 1 つ以上のダイヤル プランに関連付けるSkype for Business Serverです。 ダイヤルイン会議地域の詳細については、「ダイヤルイン会議の計画 [」を参照してください](/previous-versions/office/lync-server-2013/lync-server-2013-dial-in-conferencing-requirements)。

CAC では、すべてのネットワーク領域に、地域内のメディア トラフィックを管理する Skype for Business Server セントラル サイトが関連付けられている必要があります (つまり、リアルタイムのオーディオセッションまたはビデオ セッションを確立できるかどうかに関して、構成したポリシーに基づいて決定されます)。 Skype for Business Serverサイトは地理的な場所ではなく、プールまたはプールのセットとして構成されているサーバーの論理的なグループを表します。

ネットワーク領域を構成するには、Skype for Business Server コントロール パネルの [ネットワーク構成] セクションの [地域] タブを使用するか **、New-CsNetworkRegion** または **Set-CsNetworkRegion** Skype for Business Server Management Shell コマンドレットを実行します。 手順については、「展開」[](../../deploy/deploy-enterprise-voice/deploy-network.md)のドキュメントの「Skype for Business でネットワーク地域、サイト、サブネットを展開する」を参照するか、Skype for Business Server 管理シェルのドキュメントを参照してください。

同じネットワーク領域定義は、3 つの高度な機能エンタープライズ VoIP共有されます。 いずれかの機能にネットワーク地域を既に作成している場合、他の機能に新しいネットワーク地域を作成する必要はありません。 ただし、機能固有の設定を適用するために、既存のネットワーク地域定義を変更することが必要になる場合があります。 たとえば、E9-1-1 (関連付けられた中央サイトは不要) にネットワーク地域を作成しており、通話受付管理を後で展開する場合、中央サイトを指定するには、各ネットワーク地域定義を変更する必要があります。

Skype for Business Server セントラル サイトをネットワーク領域に関連付けるには、Skype for Business Server コントロール パネルの [ネットワーク構成]セクションを使用するか **、New-CsNetworkRegion** コマンドレットまたは **Set-CsNetworkRegion** コマンドレットを実行して、中央サイト名を指定します。 手順については、「展開」[](../../deploy/deploy-enterprise-voice/deploy-network.md)のドキュメントの「Skype for Business でネットワーク地域、サイト、サブネットを展開する」を参照するか、Skype for Business Server 管理シェルのドキュメントを参照してください。

## <a name="network-sites"></a>ネットワーク サイト

ネットワーク サイトは、ブランチ オフィス、支社、本社などの地理的場所を表します。各ネットワーク サイトは、特定のネットワーク地域に関連付けられている必要があります。

> [!NOTE]
> ネットワーク サイトは、高度な機能によってのみエンタープライズ VoIPされます。 これらのサイトは、ネットワーク トポロジで構成するブランチ サイトとSkype for Business Serverではありません。

ネットワーク サイトを構成してネットワーク領域に関連付けるには、Skype for Business Server コントロールパネルの [ネットワーク構成] セクションを使用するか、Skype for Business Server 管理シェル **New-CsNetworkSite コマンドレットまたは Set-CsNetworkSite** コマンドレットを実行します。  詳細については、「展開」の[ドキュメント](/previous-versions/office/lync-server-2013/lync-server-2013-create-or-modify-a-network-site)の「ネットワーク サイトを作成または変更する」を参照するか、管理シェルのSkype for Business Server参照してください。

## <a name="identify-ip-subnets"></a>IP サブネットの特定

ネットワーク管理者と連携して各ネットワーク サイトに割り当てる IP サブネットを決定する必要があります。ネットワーク管理者が既に IP サブネットをネットワーク地域およびネットワーク サイトに分類している場合、作業は大幅に簡略化されます。

この例では、North America 地域の New York サイトに 172.29.80.0/23、157.57.216.0/25、172.29.91.0/23、172.29.81.0/24 の IP サブネットを割り当てることができます。通常はデトロイトで仕事をしている Bob が、トレーニングのためにニューヨークのオフィスに出張する場合、コンピューターを起動してネットワークに接続すると、New York に割り当てられている 4 つの範囲のいずれか (172.29.80.103 など) の IP アドレスがコンピューターで取得されます。

> [!CAUTION]
> メディア バイパスに適切に使用するには、サーバー上のネットワーク構成中に指定された IP サブネットが、クライアント コンピューターによって提供される形式と一致している必要があります。 クライアントSkype for Businessローカル IP アドレスを受け取り、IP アドレスを関連付けられたサブネット マスクでマスクします。 各クライアントに関連付けられているバイパス ID を決定する場合、レジストラーは、各ネットワーク サイトに関連付けられている IP サブネットの一覧と、クライアントが完全に一致するために提供するサブネットとを比較します。 このため、サーバーのネットワーク構成中に入力されたサブネットは、仮想サブネットではなく実際のサブネットである必要があります。 (通話受付管理を展開するが、メディア バイパスを展開しない場合は、仮想サブネットを構成しても通話受付制御が正しく機能します)。たとえば、IP サブネット マスクが 255.255.255.0 の IP アドレスが 172.29.81.57 のコンピューターに Skype for Business クライアントがサインインすると、サブネット 172.29.81.0 に関連付けられているバイパス ID が要求されます。 クライアントが仮想サブネットに属していても、サブネットが 172.29.0.0/16 として定義される場合、レジストラーは 172.29.81.0 のサブネットのみを検索するため、これを一致とは見なしません。 したがって、管理者が Skype for Business クライアントによって提供されるサブネットとまったく同じサブネットを入力することが重要です (これは、静的に、または動的ホスト構成プロトコル (DHCP) によって、ネットワーク構成中にサブネットでプロビジョニングされます)。

## <a name="associating-subnets-with-network-sites"></a>サブネットとネットワーク サイトの関連付け

エンタープライズ ネットワーク内のすべてのサブネットは、ネットワーク サイトに関連付ける必要があります (つまり、すべてのサブネットを地理的場所に関連付ける必要があります)。 このサブネットの関連付けにより、高度なエンタープライズ VoIP機能を使用して、エンドポイントを地理的に特定できます。 たとえば、エンドポイントを見つけることにより、CAC では、ネットワーク サイトとの間で送受信されるリアルタイムの音声およびビデオのデータ フローを調整できます。

サブネットをネットワーク サイトに関連付けるには、Skype for Business Serverコントロール パネルの [ネットワーク構成] セクションを使用するか、Skype for Business Server管理シェルを使用できます。 手順については、「展開」の[ドキュメント](/previous-versions/office/lync-server-2013/lync-server-2013-associate-a-subnet-with-a-network-site)の「サブネットをネットワーク サイトに関連付ける」を参照するか、Skype for Business Serverを参照してください。

## <a name="see-also"></a>関連項目

[通話受付管理の計画を立Skype for Business Server](call-admission-control.md)

[緊急サービスの計画を立Skype for Business Server](emergency-services.md)

[ネットワークでメディア バイパスを計画Skype for Business](media-bypass.md)