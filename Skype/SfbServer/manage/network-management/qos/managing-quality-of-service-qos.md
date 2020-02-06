---
title: QoS (Quality of Service) の管理
ms.reviewer: ''
ms:assetid: ab1051c3-8380-4d72-86df-37a61b1e4a41
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg405409(v=OCS.15)
ms:contentKeyID: 48185049
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: QoS (Quality of Service) は、音声とビデオの通信に最適なエンドユーザーエクスペリエンスを提供するために、組織内で使用されるネットワークテクノロジです。
ms.openlocfilehash: 821ebb1cd6a101856f4fbc4fb3428ecba7674245
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817363"
---
# <a name="managing-quality-of-service-qos-in-skype-for-business-server"></a>Skype for Business Server での QoS (Quality of Service) の管理


QoS (Quality of Service) は、音声とビデオの通信に最適なエンドユーザーエクスペリエンスを提供するために、組織内で使用されるネットワークテクノロジです。 QoS は、帯域幅が制限されているネットワークで一般的に使用されています。大量のネットワークパケットが、使用可能な帯域幅が比較的少ない場合は、管理者がより高い優先順位をパケットに割り当てる方法を提供します。オーディオデータまたはビデオデータを伝送する。 これらのパケットの優先度を高くすることで、音声とビデオによる通信は、ファイル転送、web 閲覧、データベースバックアップなどのネットワークセッションよりもずっと速く、中断される可能性が高くなります。 これは、ファイル転送やデータベースバックアップに使用されるネットワークパケットに "最善の努力" の優先度が割り当てられているためです。


> [!NOTE]  
> 一般的な規則として、サービスの品質は、内部ネットワーク上の通信セッションにのみ適用されます。 QoS を実装するときは、サーバーとルーターがパケットマーキングをサポートするように構成します。ただし、これらのデバイスでは、特定の方法でのパケットマーキングをサポートするように構成します。 サービスの品質は、インターネットやその他のネットワークでサポートされていると想定することはできません。 サービスが他のネットワークでサポートされている場合でも、ネットワーク上のサービスを構成したときと同じ方法で QoS が構成される保証はありません。

Skype for Business Server では、サービスの品質は必要ありません。現在 QoS を使用していない場合は、Skype for Business Server をインストールする前に、サービスをインストールする必要はありません。 ネットワークで大量のパケット損失が発生する場合は、この問題を解決するために推奨される方法は、帯域幅を追加することです。 帯域幅を追加できない場合は、代わりにサービスの品質を実現することをお勧めします。

Skype for Business Server では、サービスの品質を完全にサポートしています。これは、既に QoS を使用している組織では、Skype for Business Server を既存のネットワークインフラストラクチャに簡単に統合できることを意味します。 そのためには、次の作業を行う必要があります。

  - [Windows をベースにしていないデバイスに対して QoS を有効](enabling-qos-for-devices-that-are-not-based-on-windows.md)にします。 既定では、その他のオペレーティング システムを実行するコンピューターおよびその他のデバイス (iPhone など) では QoS は無効です。 Skype for Business Server を使用して、デバイスのサービス品質を有効または無効にすることはできますが、通常は製品を使用して、これらのデバイスで使用される DSCP コードを変更することはできません。

  - [電話会議、アプリケーション、および仲介サーバーのポート範囲とサービス品質ポリシーを構成し](configuring-port-ranges-for-your-conferencing-application-and-mediation-servers.md)ます。 オーディオやビデオなどのさまざまな種類のパケットに対して、専用のポートセットを予約する必要があります。 Skype for Business Server では、プロパティ値を True または False に設定して、サービスの品質を有効または無効にすることはできません。 代わりに、ポート範囲を構成し、グループポリシーを作成して適用することで、サービスの品質を有効にします。 後で QoS を使用しないことにした場合は、適切なグループポリシーオブジェクトを削除することで、"サービスの品質" を無効にすることができます。

  - [ポート範囲を構成し、エッジサーバーのサービス品質ポリシーを設定](configuring-port-ranges-for-your-edge-servers.md)します。 必須ではありませんが、その他のサーバーと同じポート範囲を使用するようにエッジ サーバーを構成することができます。 サービス品質ポリシーの構成は、エッジサーバーの内部側に対してのみ行う必要があります。 サービスの品質は、インターネット上ではなく、内部ネットワークでの使用を目的として設計されているためです。

- [Skype For Business Server でのクライアントのポート範囲とサービス品質ポリシーの構成](configuring-port-ranges-for-your-skype-clients.md) これらのポート範囲はクライアントコンピューターにのみ適用され、通常はサーバー上に構成されているポート範囲とは異なります。 Skype for Business Server では、windows 10 以外の Windows オペレーティングシステムの QoS はサポートされていないことに注意してください。


