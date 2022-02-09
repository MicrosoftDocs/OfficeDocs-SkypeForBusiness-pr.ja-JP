---
title: エッジ設定エキスパンダー
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.EdgeSettingsExpander
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: c73780cd-0033-4287-9ecd-ecf65ca61e62
ROBOTS: NOINDEX, NOFOLLOW
description: 既存の単一サーバー エッジ プールまたは複数サーバー エッジ プールの設定を編集するために、次のセクションが表示されます。
ms.openlocfilehash: 89e23125182f5f413fbad8cbdc3e2a3651f878aa
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/05/2022
ms.locfileid: "62396921"
---
# <a name="edge-settings-expander"></a>エッジ設定エキスパンダー

既存の単一サーバー エッジ プールまたは複数サーバー エッジ プールの設定を編集するために、次のセクションが表示されます。

- 全般設定

- 次ホップ選択設定

- エッジ サーバー構成


## <a name="general-settings"></a>全般設定

エッジ サーバー プールの内部プールの完全修飾ドメイン名 (FQDN)。この設定を変更するには、プールの FQDN を編集します。

2015 サーバーとフェデレーションをセットアップする場合は、このエッジ プールのフェデレーションを有効にする **(ポート 5061)** チェック ボックスをオンSkype for Business Serverします。

[**内部構成レプリケーション ポート (HTTPS)**] に対してポート番号を指定します。

## <a name="next-hop-selection-settings"></a>次ホップ選択設定

エッジ サーバーが内部インフラストラクチャとの通信に使用する次ホップ プールを設定または変更するには、ドロップダウン リスト ボックスからディレクター、ディレクター プール、フロント エンド サーバー、またはフロント エンド サーバー プールを選択します。 トポロジ ビルダーで構成されているディレクターまたはフロントエンドだけが選択用に表示されます。

## <a name="edge-server-configuration"></a>エッジ サーバー構成

エッジ サーバーの [**外部設定**] の設定を編集または指定するには、まず、SIP アクセス、Web 会議、および音声ビデオ サービスに個別の IP アドレスを使用するかどうかを判断する必要があります。

各サービスで別々の IP アドレスを使用する場合は、[**Web 会議と音声ビデオで別々の FQDN と IP アドレスを有効にする**] チェック ボックスをオンにします。各サービスに、それぞれに作成された対応する DNS ホスト (A) レコードがある必要があります。

各外部サービスについて、FQDN および関連付けられたポートを指定します。たとえば、**[SIP アクセス]** に sip.contoso.com および関連付けられたポート 5061 を使用します。

> [!IMPORTANT]
> 外部に提供される各サービスで別々の FQDN を使用する場合は、各サービスに固有のポート値を関連付ける必要があります。 既定では、SIP はポート 5061/TLS、Web 会議エッジ サービスはポート 444/TLS、音声ビデオ会議サーバーはポート 443/TLS にあります。 別々の FQDN と IP アドレス、またはポートを使用することを含め、これらの設定に変更を加える場合は、最初に構成された値に依存する他のすべてのサービスを更新する必要があります。

外部に提供されるサービスのために、組織では 1 つの FQDN と IP アドレスを使用することを決定した場合は、[**Web 会議と音声ビデオで別々の FQDN と IP アドレスを有効にする**] チェック ボックスをオフにします。必要に応じて、[**SIP アクセス**] のプールの FQDN とポート値を編集できます。

> [!IMPORTANT]
> 別々の FQDN および IP アドレスまたはポートを使用することを含め、これらの設定のいずれかに変更を加える場合は、最初に構成された値に依存する他のすべてのサービスを更新する必要があります。

## <a name="see-also"></a>関連項目

エッジ サービスの設定の定義および構成の詳細については、「[Define Your Edge Topology](/previous-versions/office/lync-server-2013/lync-server-2013-define-your-edge-topology)」を参照してください。