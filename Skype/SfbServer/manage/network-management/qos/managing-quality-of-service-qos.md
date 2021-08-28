---
title: サービスの品質 (QoS) の管理
ms.reviewer: ''
ms:assetid: ab1051c3-8380-4d72-86df-37a61b1e4a41
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg405409(v=OCS.15)
ms:contentKeyID: 48185049
mtps_version: v=OCS.15
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: サービス品質 (QoS) は、オーディオおよびビデオ通信に最適なエンド ユーザー エクスペリエンスを提供するために、一部の組織で使用されるネットワーク テクノロジです。
ms.openlocfilehash: 33c580e61be0dcd2a5a193a654294a5ea9087d12
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58612166"
---
# <a name="managing-quality-of-service-qos-in-skype-for-business-server"></a>サービス品質 (QoS) の管理 (Skype for Business Server


サービスの品質 (QoS) は、一部の組織で使用されているネットワーク テクノロジであり、音声やビデオによる通信で最適なエンドユーザー エクスペリエンスを提供するために役立ちます。QoS は、帯域幅が制限されているネットワークで特によく使用されます。大量のネットワーク パケットが比較的少量の使用可能な帯域幅を取り合うため、サービスの品質によって、管理者が音声またはビデオのデータを伝送するパケットに高い優先順位を割り当てる方法が提供されます。このようなパケットに高い優先順位を付与すると、音声やビデオによる通信は、ファイルの転送、Web 閲覧、またはデータベース バックアップのようなネットワーク セッションよりも迅速かつ少ない中断で完了する可能性が高まります。このため、ファイルの転送またはデータベース バックアップに使用されるネットワーク パケットには "ベスト エフォート型" の優先順位が割り当てられます。


> [!NOTE]  
> 一般に、サービスの品質は、内部ネットワーク上のセッションとの通信にのみ適用されます。QoS を実装する場合は、パケットのマーキングをサポートするようにサーバーおよびルーターを構成します。ただし、これらのデバイスの構成では、特定の方法でパケットのマーキングをサポートするようにします。サービスの品質はインターネットまたはその他のネットワークでサポートされることを前提にしてはいけません。サービスの品質がその他のネットワークでサポートされる場合であっても、ネットワークでサービスを構成した方法と同じ方法で QoS が構成される保証はありません。

Skype for Business Serverサービスの品質は必要ない。現在 QoS を使用していない場合は、サービスをインストールする前にサービスをインストールする必要Skype for Business Server。 ネットワークで相当量のパケット損失が発生した場合、この問題を軽減するために推奨される方法は、帯域幅を追加する方法です。 帯域幅を追加できない場合は、代わりにサービスの品質を実装する必要があります。

Skype for Business Server QoS を使用している組織は、QoS を使用している組織が既存のネットワーク インフラストラクチャにSkype for Business Server統合できます。 これを行うには、次のタスクを実行する必要があります。

  - [デバイスに基づいておりないデバイスで QoS を有効](enabling-qos-for-devices-that-are-not-based-on-windows.md)Windows。 既定では、その他のオペレーティング システムを実行するコンピューターおよびその他のデバイス (iPhone など) では QoS は無効です。 Skype for Business Serverを使用してデバイスのサービス品質を有効または無効にすることもできますが、通常、製品を使用してこれらのデバイスで使用される DSCP コードを変更することはできません。

  - [会議、アプリケーション、仲介サーバー](configuring-port-ranges-for-your-conferencing-application-and-mediation-servers.md)のポート範囲とサービス品質ポリシーの構成。 音声とビデオなどの異なるパケットの種類に対して独自のポート セットを予約する必要があります。 このSkype for Business Server、プロパティ値を True または False に設定することで、サービス品質を有効または無効にしない必要があります。 そうではなく、ポート範囲を構成してからグループ ポリシーを作成および適用することによってサービスの品質を有効にします。 後で QoS を使用しないことにする場合は、単に該当するグループ ポリシー オブジェクトを削除することによってサービスの品質を無効にすることができます。

  - [エッジ サーバーのポート範囲とサービス品質ポリシーの構成](configuring-port-ranges-for-your-edge-servers.md)。 必須ではありませんが、その他のサーバーと同じポート範囲を使用するようにエッジ サーバーを構成することができます。 サービス品質ポリシーの構成は、エッジ サーバーの内部側でのみ行う必要があります。 サービスの品質はインターネットではなく内部ネットワークで使用するために設計されているためです。

- [クライアントのポート範囲とサービス](configuring-port-ranges-for-your-skype-clients.md)品質ポリシーの構成Skype for Business Server これらのポート範囲はクライアント コンピューターにのみ適用され、通常はサーバーで構成されているポート範囲とは異なります。 ただし、Skype for Business Server以外のオペレーティング システムWindows QoS はサポートWindows 10。


