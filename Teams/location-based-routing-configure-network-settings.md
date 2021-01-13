---
title: ネットワーク設定の構成 - 場所に基づくルーティング
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.reviewer: roykuntz
audience: admin
ms.service: msteams
search.appverid: MET150
description: 直接ルーティング用のネットワーク領域、サイト、サブネットを作成および設定するLocation-Based方法について説明します。
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: a7dd707a6066cfe9a8dfcbcc9b3ae36d450d1dd1
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49822947"
---
# <a name="configure-network-settings-for-location-based-routing"></a>場所に基づくルーティングのネットワーク設定を構成する

まだ行っていない場合は、「直接ルーティングの計画 [Location-Based](location-based-routing-plan.md) ルーティング」を参照して、Location-Based ルーティングのネットワーク設定を構成する前に実行する必要があるその他の手順を確認してください。

この記事では、ネットワーク ルーティングのネットワーク設定を構成するLocation-Based説明します。 組織に電話システム ダイレクト ルーティングを展開した後、次の手順は、ネットワーク領域、ネットワーク サイト、ネットワーク サブネットを作成してセットアップします。

## <a name="define-network-regions"></a>ネットワーク領域を定義する

ネットワーク領域には、ネットワーク サイトのコレクションが含まれるので、ネットワークのさまざまな部分が複数の地理的領域にわたって相互接続されます。 ネットワーク領域を構成する方法の手順については、「Teams でクラウド機能のネットワーク トポロジを管理する」を [参照してください](manage-your-network-topology.md)。

## <a name="define-network-sites"></a>ネットワーク サイトを定義する

ネットワーク サイトは、オフィス、建物のセット、キャンパスなど、組織が物理的な会場を持つ場所を表します。 トポロジ内の各ネットワーク サイトをネットワーク領域に関連付ける必要があります。 ネットワーク サイトを構成する手順については、「Teams でクラウド機能のネットワーク トポロジを管理する」 [を参照してください](manage-your-network-topology.md)。

ルーティングのベスト プラクティスLocation-Basedは、一意の PSTN 接続を持つ場所ごとに個別のサイトを作成することです。 カスタム ルーティングに対して有効になっているサイトLocation-Based、またはサイト のルーティングが有効になっていないLocation-Basedできます。 たとえば、Location-Based ルーティングが有効になっていないサイトを作成して、Location-Based ルーティングが有効になっているユーザーがサイトにローミングするときに PSTN 通話を発信できる場合があります。

## <a name="define-network-subnets"></a>ネットワーク サブネットを定義する

各サブネットは、特定のネットワーク サイトに関連付けられている必要があります。 複数のサブネットを同じネットワーク サイトに関連付けできますが、複数のサイトを同じサブネットに関連付け設定できない。 ネットワーク サブネットを構成する方法の手順については、「Teams でクラウド機能のネットワーク トポロジを管理する」  [を参照してください](manage-your-network-topology.md)。

ルーティングLocation-Based、有料バイパスを適用するには、Teams のエンドポイントがネットワークに接続できる場所の IP サブネットを定義し、定義されたネットワークに関連付けられている必要があります。 このサブネットの関連付けにより、Location-Basedルーティングでエンドポイントを地理的に特定し、特定の PSTN 通話を許可するかどうかを決定できます。 IPv6 サブネットと IPv4 サブネットの両方がサポートされます。 Teams エンドポイントがサイトにあるかどうかを判断する場合、最初にルーティングLocation-Based IPv6 アドレスが一致するかどうかを確認します。 IPv6 アドレスが存在しない場合は、Location-Basedが IPv4 アドレスをチェックします。

## <a name="define-trusted-ip-addresses-external-subnets"></a>信頼できる IP アドレス (外部サブネット) を定義する

信頼済み IP アドレスは、エンタープライズ ネットワークのインターネット外部 IP アドレスであり、ユーザーのエンドポイントが企業ネットワーク内にあるかどうかを判断するために使用されます。 信頼できる IP アドレスを構成する方法の手順については、「Teams でクラウド機能のネットワーク トポロジを管理する」を  [参照してください](manage-your-network-topology.md)。

ユーザーの外部 IP アドレスが信頼済み IP アドレス一覧内の IP アドレスと一致する場合、Location-Based ルーティングはユーザーのエンドポイントがある内部サブネットを確認します。 ユーザーの外部 IP アドレスが信頼済み IP アドレス一覧で定義されている IP アドレスと一致しない場合、エンドポイントは不明な場所にあると分類され、Location-Based ルーティングが有効になっているユーザーとの間の PSTN 通話はブロックされます。

## <a name="next-steps"></a>次の手順

「ダイレクト ルーティング [のLocation-Basedを有効にする」を参照してください](location-based-routing-enable.md)。

## <a name="related-topics"></a>関連項目

- [Teams のクラウド音声機能のネットワーク設定](cloud-voice-network-settings.md)
