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
description: ダイレクト ルーティングのLocation-Based ルーティング用のネットワーク リージョン、サイト、サブネットを作成して設定する方法について説明します。
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: b2686cb0171a6d7725e76ca6de4338c350c3296f
ms.sourcegitcommit: 79dfda39db208cf943d0f7b4906883bb9d034281
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/09/2022
ms.locfileid: "62457217"
---
# <a name="configure-network-settings-for-location-based-routing"></a>場所に基づくルーティングのネットワーク設定を構成する

この記事では、Location-Based ルーティングのネットワーク設定を構成する方法について説明します。 まだ行っていない場合は、「 [ダイレクト ルーティングの計画Location-Basedルーティング](location-based-routing-plan.md) 」を参照して、ネットワーク設定を構成する前に実行する必要があるその他の手順を確認してください。

組織でダイレクト ルーティングを展開した後、次の手順では、ネットワークリージョン、ネットワーク サイト、およびネットワーク サブネットを作成して設定します。

## <a name="define-network-regions"></a>ネットワークリージョンを定義する

ネットワーク リージョンには、ネットワーク サイトのコレクションが含まれており、複数の地理的領域にわたってネットワークのさまざまな部分を相互接続します。 ネットワークリージョンを構成する方法については、「[Teamsでクラウド機能のネットワーク トポロジを管理する」を参照してください](manage-your-network-topology.md)。

## <a name="define-network-sites"></a>ネットワーク サイトを定義する

ネットワーク サイトは、組織がオフィス、建物のセット、キャンパスなどの物理的な会場を持つ場所を表します。 トポロジ内の各ネットワーク サイトをネットワーク リージョンに関連付ける必要があります。 ネットワーク サイトを構成する方法については、「[Teamsでクラウド機能のネットワーク トポロジを管理する](manage-your-network-topology.md)」を参照してください。

Location-Based ルーティングのベスト プラクティスは、一意の公衆交換電話網 (PSTN) 接続を持つ場所ごとに個別のサイトを作成することです。 Location-Based ルーティングが有効になっているサイト、またはLocation-Basedルーティングが有効になっていないサイトを作成できます。 たとえば、Location-Based ルーティングが有効になっていないサイトを作成して、Location-Based ルーティングが有効になっているユーザーが、そのサイトにローミングするときに PSTN 通話を行えるようにすることができます。

## <a name="define-network-subnets"></a>ネットワーク サブネットを定義する

各サブネットは、特定のネットワーク サイトに関連付けられている必要があります。 複数のサブネットを同じネットワーク サイトに関連付けることができますが、同じサブネットに複数のサイトを関連付けることはできません。 ネットワーク サブネットを構成する方法については、「[Teamsでクラウド機能のネットワーク トポロジを管理する](manage-your-network-topology.md)」を参照してください。

Location-Based ルーティングでは、Teams エンドポイントがネットワークに接続できる場所にある IP サブネットを定義し、定義されたネットワークに関連付けて、有料バイパスを適用する必要があります。 このサブネットの関連付けにより、Location-Based ルーティングはエンドポイントを地理的に見つけて、特定の PSTN 通話を許可する必要があるかどうかを判断できます。 IPv6 サブネットと IPv4 サブネットの両方がサポートされています。 Teams エンドポイントがサイトにあるかどうかを判断する場合は、最初にルーティングLocation-Based一致する IPv6 アドレスがチェックされます。 IPv6 アドレスが存在しない場合は、Location-Basedルーティングによって IPv4 アドレスがチェックされます。

## <a name="define-trusted-ip-addresses-external-subnets"></a>信頼された IP アドレス (外部サブネット) を定義する

信頼された IP アドレスは、エンタープライズ ネットワークのインターネット外部 IP アドレスであり、ユーザーのエンドポイントが企業ネットワーク内にあるかどうかを判断するために使用されます。 信頼された IP アドレスを構成する方法については、「[Teamsでクラウド機能のネットワーク トポロジを管理する](manage-your-network-topology.md)」を参照してください。

ユーザーの外部 IP アドレスが信頼された IP アドレスの一覧にある IP アドレスと一致する場合は、ルーティングLocation-Basedチェックして、ユーザーのエンドポイントが配置されている内部サブネットを確認します。 ユーザーの外部 IP アドレスが信頼された IP アドレスの一覧で定義されている IP アドレスと一致しない場合、エンドポイントは不明な場所に分類され、Location-Based ルーティングが有効になっているユーザーとの PSTN 通話はブロックされます。

## <a name="next-steps"></a>次のステップ

[[ダイレクト ルーティングのLocation-Based ルーティングを有効にする] に移動します](location-based-routing-enable.md)。

## <a name="related-topics"></a>関連項目

- [Teamsのクラウド音声機能のネットワーク設定](cloud-voice-network-settings.md)
