---
title: モビリティのパフォーマンスの監視
TOCTitle: モビリティのパフォーマンスの監視
ms:assetid: 9c831c63-9a7d-48ec-9118-f8a7e80ddd04
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Hh690033(v=OCS.15)
ms:contentKeyID: 48272981
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# モビリティのパフォーマンスの監視

 

_**トピックの最終更新日:** 2013-02-14_

Lync Server Mobility Service によって、フロント エンド サーバーおよびフロント エンド プールの負荷が増大します。モバイル アプリケーションが最小化されてもサーバーへの接続を維持するモバイル デバイス (Android デバイス、Nokia デバイスなど) は、モバイル アプリケーションが最小化されたときにサーバーへの接続を終了するデバイスよりも大きい負荷がかかります。モビリティの使用量が増加するにつれて、モビリティのパフォーマンスを監視し、容量の増加が必要な時期を決定する必要があります。

モビリティのパフォーマンスに影響を与えるいくつかの制限値があります。

  - 使用可能なメモリ

  - 要求キューの制限

  - 同時接続数

  - IIS キューの長さ

モビリティのパフォーマンスに影響する可能性のある、サーバーへのその他の制限値として、最大 12 の同時サインイン数、認証数、セッションの更新数、およびセッションの終了数があります。ただし、ほとんどの展開でこれらの最大値を変更する必要はありません。

## このセクション中

  - [サーバーのメモリ容量制限の監視](lync-server-2013-monitoring-for-server-memory-capacity-limits.md)

  - [モビリティ サービスおよび UCWA の使用状況の監視](lync-server-2013-monitoring-mobility-service-and-ucwa-usage.md)

  - [高いパフォーマンスを実現する Mobility Service の構成](lync-server-2013-configuring-mobility-service-for-high-performance.md)

  - [IIS 要求トレース ログ ファイルの監視](lync-server-2013-monitoring-iis-request-tracing-log-files.md)

  - [モビリティ パフォーマンス カウンター](lync-server-2013-mobility-performance-counters.md)

