---
title: ネットワーク設定の構成 - 場所ベースのルーティング
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.reviewer: roykuntz
audience: admin
ms.service: msteams
search.appverid: MET150
description: ダイレクト ルーティング用のネットワーク リージョン、サイト、サブネットを作成および設定するLocation-Basedについて説明します。
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

まだ行っていない場合は、「直接ルーティングのための [Location-Based](location-based-routing-plan.md) ルーティングの計画」を参照して、Location-Based ルーティングのネットワーク設定を構成する前に実行する必要があるその他の手順を確認してください。

この記事では、ルーティングのネットワーク設定を構成するLocation-Based説明します。 組織に直接ルーティング電話システムデプロイした後、次の手順では、ネットワーク リージョン、ネットワーク サイト、ネットワーク サブネットを作成して設定します。

## <a name="define-network-regions"></a>ネットワーク リージョンを定義する

ネットワーク リージョンには、ネットワーク サイトのコレクションが含まれるので、ネットワークのさまざまな部分が複数の地理的領域にわたって相互接続されます。 ネットワーク リージョンを構成する方法の手順については、クラウド機能のネットワーク トポロジの管理に関するページを[参照](manage-your-network-topology.md)Teams。

## <a name="define-network-sites"></a>ネットワーク サイトを定義する

ネットワーク サイトは、オフィス、ビルのセット、キャンパスなど、組織が物理的な会場を持つ場所を表します。 トポロジ内の各ネットワーク サイトをネットワーク リージョンに関連付ける必要があります。 ネットワーク サイトを構成する方法の手順については、「ネットワーク サイトでクラウド機能のネットワーク トポロジを管理する[」をTeams。](manage-your-network-topology.md)

ルーティングのベスト プラクティスはLocation-Based PSTN 接続を持つ場所ごとに個別のサイトを作成することです。 カスタム ルーティングが有効になっているサイトLocation-Based、またはルーティングに対して有効になっていないサイトLocation-Basedできます。 たとえば、Location-Based ルーティングが有効になっていないサイトを作成して、Location-Based ルーティングが有効になっているユーザーが、そのサイトにローミングするときに PSTN 通話を発信できます。

## <a name="define-network-subnets"></a>ネットワーク サブネットを定義する

各サブネットは、特定のネットワーク サイトに関連付けられている必要があります。 複数のサブネットを同じネットワーク サイトに関連付けできますが、複数のサイトを同じサブネットに関連付けは行いません。 ネットワーク サブネットを構成する方法の手順については、「クラウド機能のネットワーク トポロジを管理する」を参照[Teams。](manage-your-network-topology.md)

ルーティングLocation-Based、Teams エンドポイントがネットワークに接続できる場所にある IP サブネットを定義し、定義されたネットワークに関連付け、有料バイパスを強制する必要があります。 このサブネットの関連付Location-Basedルーティングを使用して、特定の PSTN 呼び出しを許可するかどうかを判断するために、エンドポイントを地理的に特定できます。 IPv6 サブネットと IPv4 サブネットの両方がサポートされています。 エンドポイントがサイトにTeamsかどうかを判断する場合は、Location-Based一致する IPv6 アドレスが最初にチェックされます。 IPv6 アドレスが存在しない場合は、Location-Basedが IPv4 アドレスをチェックします。

## <a name="define-trusted-ip-addresses-external-subnets"></a>信頼できる IP アドレス (外部サブネット) を定義する

信頼できる IP アドレスは、エンタープライズ ネットワークのインターネット外部 IP アドレスであり、ユーザーのエンドポイントが企業ネットワーク内にあるかどうかを判断するために使用されます。 信頼できる IP アドレスを構成する手順については、「クラウド機能のネットワーク トポロジを管理する」を参照[Teams。](manage-your-network-topology.md)

ユーザーの外部 IP アドレスが信頼済み IP アドレス一覧にある IP アドレスと一致する場合、Location-Based ルーティングはユーザーのエンドポイントが位置する内部サブネットを確認します。 ユーザーの外部 IP アドレスが信頼済み IP アドレス一覧で定義されている IP アドレスと一致しない場合、エンドポイントは不明な場所にあると分類され、Location-Based ルーティングが有効になっているユーザーとの間の PSTN 通話はブロックされます。

## <a name="next-steps"></a>次の手順

「Enable Location-Based Routing for Direct Routing (ダイレクト [ルーティングのルーティングを有効にする)」を参照してください](location-based-routing-enable.md)。

## <a name="related-topics"></a>関連トピック

- [Teams のクラウド音声機能のネットワーク設定](cloud-voice-network-settings.md)
