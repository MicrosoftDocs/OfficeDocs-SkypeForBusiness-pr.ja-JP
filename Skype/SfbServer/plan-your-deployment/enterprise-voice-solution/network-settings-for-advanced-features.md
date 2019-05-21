---
title: Skype for Business Server の高度なエンタープライズ Voip 機能のネットワーク設定
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 7f6de9e4-c8a4-44e4-8d14-21fe8c45283a
description: ネットワーク領域、ネットワーク サイト、および IP サブネットについて説明します。 これらはすべて、Skype for Business でメディアバイパスの計画を展開するか、skype for business Server での通話受付制御を計画するように構成するか、skype for business server Enterprise Voice の Skype for Business Server で緊急サービスを計画するように構成する必要があります。
ms.openlocfilehash: 1c652edd2d3f1898742656c9e12448386e680675
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34276576"
---
# <a name="network-settings-for-the-advanced-enterprise-voice-features-in-skype-for-business-server"></a>Skype for Business Server の高度なエンタープライズ Voip 機能のネットワーク設定

ネットワーク領域、ネットワーク サイト、および IP サブネットについて説明します。 Skype for [business でメディアバイパスの計画](media-bypass.md)を展開するか、skype For business [server の通話受付制御を計画](call-admission-control.md)するか、skype For business Server の[skype for business Server の緊急サービスを計画](emergency-services.md)するように、これらすべてを構成する必要があります。エンタープライズ Voip。

Skype for Business Server には、3つの高度なエンタープライズ音声機能があります。 [skype For Business server での通話受付制御の計画](call-admission-control.md)、skype [for business server の緊急サービスの計画](emergency-services.md)、 [skype for business でのメディアのバイパスの計画](media-bypass.md). これらの機能は、ネットワークサイトでの Skype for Business Server トポロジの各サブネットのネットワーク領域、ネットワークサイト、および各サブネットの特定の構成要件を共有します。

このトピックでは、これらの高度なエンタープライズボイス機能の3つに共通する構成要件の概要について説明します。

## <a name="network-regions"></a>ネットワーク地域

ネットワーク地域は、通話受付管理 (CAC)、E9-1-1、およびメディア バイパスの構成でのみ使用されるネットワーク ハブまたはネットワーク バックボーンです。

> [!NOTE]
> ネットワーク領域は、Skype for Business Server のダイヤルイン会議領域とは異なります。これは、ダイヤルイン会議アクセス番号を1つまたは複数の Skype for Business Server のダイヤルプランに関連付けるために必要となります。 ダイヤルイン会議の地域の詳細については、「[Planning for Dial-In Conferencing](https://technet.microsoft.com/library/9aff949e-3dac-481a-be46-a180c72e8066.aspx)」を参照してください。

CAC では、すべてのネットワーク領域に、関連する Skype for Business Server セントラルサイトが必要です。これは、その領域内のメディアトラフィックを管理します (つまり、設定済みのポリシーに基づいて、リアルタイムのオーディオを管理するかどうかについての決定を行います)。ビデオセッションを確立できます)。 Skype for Business Server のセントラルサイトは、地理的な場所を示すのではなく、プールまたは一連のプールとして構成されているサーバーの論理グループを表します。

ネットワーク領域を構成するには、Skype for Business Server コントロールパネルの [**ネットワーク構成**] セクションの [**地域**] タブを使用するか、または**新しい-** csnetworkregion を実行するか、skype for business を**設定**することができます。サーバー管理シェルコマンドレット。 手順については、展開ドキュメントの「 [skype For business でのネットワーク領域、サイト、サブネットの展開](../../deploy/deploy-enterprise-voice/deploy-network.md)」を参照するか、「Skype For Business Server 管理シェルのドキュメント」を参照してください。

同じネットワーク領域の定義は、3つの高度なエンタープライズ音声機能によって共有されます。 いずれかの機能にネットワーク地域を既に作成している場合、他の機能に新しいネットワーク地域を作成する必要はありません。 ただし、機能固有の設定を適用するために、既存のネットワーク地域定義を変更することが必要になる場合があります。 たとえば、E9-1-1 (関連付けられた中央サイトは不要) にネットワーク地域を作成しており、通話受付管理を後で展開する場合、中央サイトを指定するには、各ネットワーク地域定義を変更する必要があります。

Skype for business Server のセントラルサイトをネットワーク領域と関連付けるには、[Skype for Business Server] コントロールパネルの [**ネットワーク構成**] セクションを使用するか、または**新しい csnetworkregion**を実行して、セントラルサイト名を指定します。または **、CsNetworkRegion**コマンドレットを設定する 手順については、展開ドキュメントの「 [skype For business でのネットワーク領域、サイト、サブネットの展開](../../deploy/deploy-enterprise-voice/deploy-network.md)」を参照するか、「Skype For Business Server 管理シェルのドキュメント」を参照してください。

## <a name="network-sites"></a>ネットワーク サイト

ネットワーク サイトは、ブランチ オフィス、支社、本社などの地理的場所を表します。各ネットワーク サイトは、特定のネットワーク地域に関連付けられている必要があります。

> [!NOTE]
> ネットワークサイトは、高度なエンタープライズ Voip 機能によってのみ使用されます。 Skype for Business Server のトポロジで構成したブランチサイトとは異なります。

ネットワークサイトを構成し、ネットワーク領域に関連付けるには、Skype for Business Server コントロールパネルの [**ネットワーク構成**] セクションを使用するか、または Skype For Business Server 管理シェルの**新しい (csnetworksite) サイト****を実行するか、CsNetworkSite**コマンドレットを設定します。 詳細については、「展開ドキュメントで[ネットワークサイトを作成または変更](https://technet.microsoft.com/library/14e24856-9996-4da4-9f31-300940bdf5aa.aspx)する」を参照するか、「Skype For Business Server 管理シェルのドキュメント」を参照してください。

## <a name="identify-ip-subnets"></a>IP サブネットの特定

ネットワーク管理者と連携して各ネットワーク サイトに割り当てる IP サブネットを決定する必要があります。ネットワーク管理者が既に IP サブネットをネットワーク地域およびネットワーク サイトに分類している場合、作業は大幅に簡略化されます。

この例では、North America 地域の New York サイトに 172.29.80.0/23、157.57.216.0/25、172.29.91.0/23、172.29.81.0/24 の IP サブネットを割り当てることができます。通常はデトロイトで仕事をしている Bob が、トレーニングのためにニューヨークのオフィスに出張する場合、コンピューターを起動してネットワークに接続すると、New York に割り当てられている 4 つの範囲のいずれか (172.29.80.103 など) の IP アドレスがコンピューターで取得されます。

> [!CAUTION]
> サーバー上のネットワーク構成中に指定された IP サブネットは、メディアのバイパスに適切に使用するために、クライアントコンピューターによって提供される形式と一致する必要があります。 Skype for Business クライアントはローカル IP アドレスを受け取り、関連するサブネットマスクを使って IP アドレスをマスクします。 各クライアントに関連付けられているバイパス ID を判断するとき、レジストラーは、各ネットワークサイトに関連付けられた IP サブネットの一覧と、完全一致のためにクライアントによって提供されるサブネットとを比較します。 このため、サーバー上のネットワーク構成中に入力されたサブネットは、仮想サブネットではなく実際のサブネットであることが重要です。 (通話受付制御を展開して、メディアをバイパスしない場合は、仮想サブネットを構成しても、通話受付制御が適切に機能します)。たとえば、Skype for Business クライアントが ip サブネットマスク255.255.255.0 を持つ172.29.81.57 の IP アドレスを持つコンピューターでサインインすると、サブネット172.29.81.0 に関連付けられているバイパス ID が要求されます。 クライアントが仮想サブネットに属していても、サブネットが 172.29.0.0/16 として定義される場合、レジストラーは 172.29.81.0 のサブネットのみを検索するため、これを一致とは見なしません。 そのため、管理者は、Skype for Business クライアントによって提供されるものとまったく同じサブネットを入力することが重要です (静的または動的ホスト構成プロトコル (DHCP) によって、ネットワーク構成中にサブネットでプロビジョニングされます)。

## <a name="associating-subnets-with-network-sites"></a>サブネットとネットワーク サイトの関連付け

エンタープライズ ネットワーク内のすべてのサブネットは、ネットワーク サイトに関連付ける必要があります (つまり、すべてのサブネットを地理的場所に関連付ける必要があります)。 サブネットの関連付けを使用すると、高度なエンタープライズボイス機能で、エンドポイントを地理的に見つけることができます。 たとえば、エンドポイントを見つけることにより、CAC では、ネットワーク サイトとの間で送受信されるリアルタイムの音声およびビデオのデータ フローを調整できます。

サブネットとネットワークサイトを関連付けるには、Skype for Business Server コントロールパネルの [**ネットワーク構成**] セクションを使用するか、または Skype For Business Server 管理シェルを使用します。 手順については、「展開ドキュメントの[サブネットとネットワークサイトを関連付ける](https://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx)」を参照するか、「Skype For Business Server 管理シェルのドキュメント」を参照してください。

## <a name="see-also"></a>関連項目

[Skype for Business Server での通話受付制御の計画](call-admission-control.md)

[Skype for Business Server の緊急サービスの計画](emergency-services.md)

[Skype for Business でのメディアのバイパスの計画](media-bypass.md)

