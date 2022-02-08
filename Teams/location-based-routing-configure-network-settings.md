---
title: ネットワーク設定の構成 - 場所ベースのルーティング
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.reviewer: roykuntz
audience: admin
ms.service: msteams
search.appverid: MET150
description: 直接ルーティングのルーティングに使用するネットワーク リージョン、サイト、サブネットを作成Location-Based設定する方法について説明します。
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 2c6c0c317d934439acc5413f44b508a22b5cd8d3
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/05/2022
ms.locfileid: "62393499"
---
# <a name="configure-network-settings-for-location-based-routing"></a>場所に基づくルーティングのネットワーク設定を構成する

まだ行っていない場合は、「直接ルーティングのための [Location-Based](location-based-routing-plan.md) ルーティングの計画」を参照して、Location-Based ルーティングのネットワーク設定を構成する前に実行する必要があるその他の手順を確認してください。

この記事では、ルーティングのネットワーク設定を構成する方法についてLocation-Basedします。 組織に直接ルーティング電話システムデプロイした後、次の手順では、ネットワーク リージョン、ネットワーク サイト、ネットワーク サブネットを作成して設定します。

## <a name="define-network-regions"></a>ネットワーク リージョンを定義する

ネットワーク リージョンには、ネットワーク サイトのコレクションが含まれているので、ネットワークのさまざまな部分が複数の地理的領域にわたって相互接続されます。 ネットワーク リージョンを構成する方法の手順については、「Manage [your network topology for cloud features in](manage-your-network-topology.md) Teams」を参照してください。

## <a name="define-network-sites"></a>ネットワーク サイトを定義する

ネットワーク サイトは、オフィス、ビルのセット、キャンパスなど、組織が物理的な会場を持つ場所を表します。 トポロジ内の各ネットワーク サイトをネットワーク リージョンに関連付ける必要があります。 ネットワーク サイトを構成する方法の手順については、「Manage [your network topology for cloud features in](manage-your-network-topology.md) Teams」 (クラウド機能のネットワーク トポロジを管理する) を参照Teams。

ルーティングのベスト プラクティスはLocation-Based PSTN 接続を持つ場所ごとに個別のサイトを作成することです。 カスタム ルーティングが有効になっているサイトLocation-Based、またはルーティングに対して有効になっていないサイトLocation-Basedできます。 たとえば、Location-Based ルーティングが有効になっていないサイトを作成して、Location-Based ルーティングが有効になっているユーザーが、そのサイトにローミングするときに PSTN 通話を発信できます。

## <a name="define-network-subnets"></a>ネットワーク サブネットを定義する

各サブネットは、特定のネットワーク サイトに関連付けられている必要があります。 複数のサブネットを同じネットワーク サイトに関連付けできますが、複数のサイトを同じサブネットに関連付けは行いません。 ネットワーク サブネットを構成する方法の手順については、「クラウド のクラウド機能のネットワーク トポロジを管理する[」を参照Teams](manage-your-network-topology.md)。

ルーティングLocation-Based、Teams エンドポイントがネットワークに接続できる場所にある IP サブネットを定義し、定義されたネットワークに関連付け、有料バイパスを強制する必要があります。 このサブネットの関連付Location-Basedルーティングを使用して、特定の PSTN 呼び出しを許可するかどうかを判断するために、エンドポイントを地理的に特定できます。 IPv6 サブネットと IPv4 サブネットの両方がサポートされています。 エンドポイントがサイトにあるTeams判断する場合は、Location-Based一致する IPv6 アドレスが最初にチェックされます。 IPv6 アドレスが存在しない場合は、Location-Basedが IPv4 アドレスをチェックします。

## <a name="define-trusted-ip-addresses-external-subnets"></a>信頼できる IP アドレス (外部サブネット) を定義する

信頼できる IP アドレスは、エンタープライズ ネットワークのインターネット外部 IP アドレスであり、ユーザーのエンドポイントが企業ネットワーク内にあるかどうかを判断するために使用されます。 信頼できる IP アドレスを構成する方法の手順については、「Manage [your network topology for cloud features in](manage-your-network-topology.md) Teams」 (クラウド機能のネットワーク トポロジの管理) を参照してください。

ユーザーの外部 IP アドレスが信頼済み IP アドレス一覧にある IP アドレスと一致する場合、Location-Based ルーティングはユーザーのエンドポイントが位置する内部サブネットを確認します。 ユーザーの外部 IP アドレスが信頼済み IP アドレス一覧で定義されている IP アドレスと一致しない場合、エンドポイントは不明な場所にあると分類され、Location-Based ルーティングが有効になっているユーザーとの間の PSTN 通話はブロックされます。

## <a name="next-steps"></a>次の手順

「ダイレクト ルーティング [のルーティングLocation-Based有効にする」を参照してください](location-based-routing-enable.md)。

## <a name="related-topics"></a>関連項目

- [Teams のクラウド音声機能のネットワーク設定](cloud-voice-network-settings.md)
