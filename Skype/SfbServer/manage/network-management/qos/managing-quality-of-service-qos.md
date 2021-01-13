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
localization_priority: Normal
description: サービスの品質 (QoS) は、一部の組織で使用されるネットワーク テクノロジであり、音声およびビデオ通信に最適なエンド ユーザー エクスペリエンスを提供するのに役立ちます。
ms.openlocfilehash: 77fae69a6ceeaf65f80dd38e78e42e186786c4ed
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814157"
---
# <a name="managing-quality-of-service-qos-in-skype-for-business-server"></a>Skype for Business Server でのサービスの品質 (QoS) の管理


サービスの品質 (QoS) は、一部の組織で使用されているネットワーク テクノロジであり、音声やビデオによる通信で最適なエンドユーザー エクスペリエンスを提供するために役立ちます。QoS は、帯域幅が制限されているネットワークで特によく使用されます。大量のネットワーク パケットが比較的少量の使用可能な帯域幅を取り合うため、サービスの品質によって、管理者が音声またはビデオのデータを伝送するパケットに高い優先順位を割り当てる方法が提供されます。このようなパケットに高い優先順位を付与すると、音声やビデオによる通信は、ファイルの転送、Web 閲覧、またはデータベース バックアップのようなネットワーク セッションよりも迅速かつ少ない中断で完了する可能性が高まります。このため、ファイルの転送またはデータベース バックアップに使用されるネットワーク パケットには "ベスト エフォート型" の優先順位が割り当てられます。


> [!NOTE]  
> 一般に、サービスの品質は、内部ネットワーク上のセッションとの通信にのみ適用されます。QoS を実装する場合は、パケットのマーキングをサポートするようにサーバーおよびルーターを構成します。ただし、これらのデバイスの構成では、特定の方法でパケットのマーキングをサポートするようにします。サービスの品質はインターネットまたはその他のネットワークでサポートされることを前提にしてはいけません。サービスの品質がその他のネットワークでサポートされる場合であっても、ネットワークでサービスを構成した方法と同じ方法で QoS が構成される保証はありません。

Skype for Business Server はサービスの品質を必要としません。現在 QoS を使用していない場合は、Skype for Business Server をインストールする前にサービスをインストールする必要はありません。 ネットワークで大量のパケット損失が発生した場合、この問題を軽減するために推奨される方法は、帯域幅を追加する方法です。 帯域幅を追加できない場合は、代わりにサービスの品質を実装することもできます。

Skype for Business Server はサービスの品質を完全にサポートします。つまり、QoS を既に使用している組織は、Skype for Business Server を既存のネットワーク インフラストラクチャに簡単に統合できます。 これを行うには、次のタスクを実行する必要があります。

  - [Windows に基づいていないデバイスで QoS を有効にする](enabling-qos-for-devices-that-are-not-based-on-windows.md)。 既定では、その他のオペレーティング システムを実行するコンピューターおよびその他のデバイス (iPhone など) では QoS は無効です。 Skype for Business Server を使用してデバイスのサービスの品質を有効または無効にすることもできますが、通常、この製品を使用して、これらのデバイスで使用される DSCP コードを変更することはできません。

  - [電話会議、アプリケーション、および仲介](configuring-port-ranges-for-your-conferencing-application-and-mediation-servers.md)サーバーのポート範囲とサービス品質ポリシーの構成。 音声とビデオなどの異なるパケットの種類に対して独自のポート セットを予約する必要があります。 Skype for Business Server では、プロパティ値を True または False に設定することで、サービスの品質を有効または無効にしません。 そうではなく、ポート範囲を構成してからグループ ポリシーを作成および適用することによってサービスの品質を有効にします。 後で QoS を使用しないことにする場合は、単に該当するグループ ポリシー オブジェクトを削除することによってサービスの品質を無効にすることができます。

  - [エッジ サーバーのポート範囲とサービス品質ポリシーの構成](configuring-port-ranges-for-your-edge-servers.md)。 必須ではありませんが、その他のサーバーと同じポート範囲を使用するようにエッジ サーバーを構成することができます。 サービス品質ポリシーの構成は、エッジ サーバーの内部側でのみ行う必要があります。 サービスの品質はインターネットではなく内部ネットワークで使用するために設計されているためです。

- Skype for Business Server でのクライアントのポート範囲とサービス[品質ポリシーの構成](configuring-port-ranges-for-your-skype-clients.md) これらのポート範囲はクライアント コンピューターにのみ適用され、通常はサーバーで構成されているポート範囲とは異なります。 Skype for Business Server は、Windows 10 以外の Windows オペレーティング システムの QoS をサポートしません。


