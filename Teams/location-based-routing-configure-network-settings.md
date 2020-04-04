---
title: ネットワーク設定の構成-場所に基づくルーティング
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.reviewer: roykuntz
audience: admin
ms.service: msteams
search.appverid: MET150
description: ダイレクトルーティングの位置情報に基づくルーティング用に、ネットワークの領域、サイト、サブネットを作成してセットアップする方法について説明します。
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: f63ff0191518acf72fd3e4c33abe80b819c3db28
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/03/2020
ms.locfileid: "43141280"
---
# <a name="configure-network-settings-for-location-based-routing"></a>場所に基づくルーティングのネットワーク設定を構成する

> [!INCLUDE [Preview customer token](includes/preview-feature.md)]

まだインストールしていない場合は、「[位置情報に基づくルーティングを計画](location-based-routing-plan.md)する」を参照して、場所に基づくルーティングのネットワーク設定を構成する前に実行する必要があるその他の手順を確認してください。

この記事では、場所に基づくルーティングのネットワーク設定を構成する方法について説明します。 組織で電話システムの直接ルーティングを展開した後、次の手順では、ネットワーク領域、ネットワークサイト、ネットワークサブネットを作成してセットアップします。

## <a name="define-network-regions"></a>ネットワーク領域を定義する

ネットワーク領域には、ネットワークサイトのコレクションが含まれており、複数の地域にわたってネットワークのさまざまな部分を相互接続しています。 ネットワーク領域を構成する手順については、「 [Teams のクラウド機能のネットワークトポロジを管理](manage-your-network-topology.md)する」を参照してください。

## <a name="define-network-sites"></a>ネットワークサイトを定義する

ネットワークサイトとは、オフィス、建物のセット、キャンパスなど、組織が物理的な会場を持っている場所を表します。 トポロジ内の各ネットワークサイトをネットワーク領域と関連付ける必要があります。 ネットワークサイトを構成する手順については、「 [Teams のクラウド機能のネットワークトポロジを管理](manage-your-network-topology.md)する」を参照してください。

場所に基づくルーティングのベストプラクティスは、一意の PSTN 接続がある場所ごとに個別のサイトを作成することです。 場所に基づくルーティングまたは位置情報に基づくルーティング用に有効になっていないサイトのサイトを作成できます。 たとえば、位置情報に基づくルーティングが有効になっていないサイトを作成して、場所ベースのルーティングが有効になっているユーザーがそのサイトに移動したときに PSTN 通話を発信できるようにすることができます。

## <a name="define-network-subnets"></a>ネットワークサブネットを定義する

各サブネットは、特定のネットワークサイトに関連付けられている必要があります。 複数のサブネットを同じネットワークサイトに関連付けることはできますが、複数のサイトを同じサブネットに関連付けることはできません。 ネットワークサブネットを構成する手順については、「 [Teams のクラウド機能のネットワークトポロジを管理](manage-your-network-topology.md)する」を参照してください。

位置情報に基づくルーティングの場合、チームのエンドポイントがネットワークに接続できる場所で、IP サブネットを定義し、定義されたネットワークに関連付けて、有料のバイパスを適用する必要があります。 サブネットの関連付けによって、位置情報に基づくルーティングが、特定の PSTN 通話を許可するかどうかを判断するために、エンドポイントを地理的に見つけることができます。 IPv6 と IPv4 の両方のサブネットがサポートされています。 チームのエンドポイントがサイトに配置されているかどうかを判断するときに、位置ベースのルーティングでは、最初に一致する IPv6 アドレスが確認されます。 IPv6 アドレスが存在しない場合、場所に基づくルーティングで IPv4 アドレスが確認されます。

## <a name="define-trusted-ip-addresses-external-subnets"></a>信頼できる IP アドレス (外部サブネット) を定義する

[信頼された IP アドレス] は、エンタープライズネットワークのインターネット外部 IP アドレスであり、ユーザーのエンドポイントが企業ネットワーク内にあるかどうかを判断するために使用されます。 信頼された IP アドレスを構成する手順については、「 [Teams のクラウド機能のネットワークトポロジを管理](manage-your-network-topology.md)する」を参照してください。

ユーザーの外部 IP アドレスが、信頼された IP アドレス一覧にある IP アドレスと一致する場合、場所ベースのルーティングでは、ユーザーのエンドポイントが配置されている内部サブネットを確認します。 ユーザーの外部 IP アドレスが、信頼できる IP アドレスリストで定義されている IP アドレスと一致しない場合、エンドポイントは不明な場所に分類され、場所に基づくルーティングを有効にしているユーザーへの PSTN 通話はブロックされます。

## <a name="next-steps"></a>次の手順

「[ダイレクトルーティングで位置情報に基づくルーティングを有効](location-based-routing-enable.md)にする」に進みます。

## <a name="related-topics"></a>関連項目

- [Teams でのクラウド音声機能のネットワーク設定](cloud-voice-network-settings.md)
