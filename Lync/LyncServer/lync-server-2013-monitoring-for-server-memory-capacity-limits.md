---
title: サーバーのメモリ容量制限の監視
TOCTitle: サーバーのメモリ容量制限の監視
ms:assetid: 1697ea71-6fcf-480d-b4e9-cd79f94d247e
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Hh689982(v=OCS.15)
ms:contentKeyID: 48271381
ms.date: 12/28/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# サーバーのメモリ容量制限の監視

 

_**トピックの最終更新日:** 2016-12-08_

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.


> [!WARNING]
> 処理能力計画を参照するこのトピックの情報は Lync 2010 Mobile クライアントおよび Mobility Service (Mcx) にのみ関係します。Lync 2013 Mobile クライアントで使用する統合コミュニケーション Web API (UCWA) の処理能力計画は、Lync Server 2013、計画ツールによって提供されます。



Lync Server 2013 Mobility Service (Mcx) の現在の使用状況の確認や処理能力の計画だけでなく、UCWA のメモリ使用量の監視を行うには、2 つのモビリティ パフォーマンス カウンターが役立つ可能性があります。UCWA の場合、カウンターのカテゴリは \[**LS:WEB – UCWA**\] です。Mobility Service (Mcx) の場合、カウンターはカテゴリ \[**LS:WEB - Mobile Communication Service**\] の下にあります。監視するカウンターを以下に示します。

  - **Currently Active Session Count with Active Presence Subscriptions**。これは、UCWA または Mobility Service (Mcx) 経由で登録されたエンドポイントのうち、アクティブなプレゼンス サブスクリプションを持つエンドポイントの現在数 (常時接続されたモバイル ユーザーの数) です。

  - **Currently Active Session Count**。これは、UCWA または Mobility Service 経由で登録されたエンドポイントの現在数です。

時間が経過しても \[**Currently Active Session Count with Active Presence Subscriptions**\] と \[**Currently Active Session Count**\] の差が小さい場合、ほとんどのモバイル デバイス ユーザーが、Android、Nokia のモバイル デバイスなど、常時接続されたデバイスを持っていることを意味します (Mcx のみ)。UCWA の常時接続デバイスには、Lync 2013 Mobile クライアントを実行する Apple および Android デバイスが含まれます。\[**Currently Active Session Count**\] が \[**Currently Active Session Count with Active Presence Subscriptions**\] よりも大幅に多い場合、より多くのユーザーが、Mcx 下の Apple iOS デバイス、Windows Phone など、バックグラウンドのエンドポイント デバイスを使用していることを示します (Windows Phone がこのように登録される唯一の Lync 2013 Mobile クライアントです)。

\[**Currently Active Session Count with Active Presence Subscriptions**\] および \[**Currently Active Session Count**\] のパフォーマンス カウンターには、予想される使用量、容量計画の結果、および Mobility Service とその他のフロント エンド サーバー カウンターの進行中の監視に基づいて、制限を設定する必要があります。設定した制限によってサーバー容量を評価できる必要があります。また、容量が超過したときに、設定した制限によって警告することができる必要があります。

適切な制限を決定するには、まず、フロント エンド サーバーで Mobility Service 用に使用可能なメモリの容量を確認する必要があります。カウンターを監視し、次の式に従って、追加容量の計画が必要な時期を確認します。

Mcx Mobility Service で使用される合計メモリ (MB) = 164 + (400 + 134) / 1024 \* \[**Currently Active Session Count with Active Presence Subscriptions**\] + 400 / 1024 \* (\[**Currently Active Session Count**\] ? \[**Currently Active Session Count with Active Presence Subscriptions**\])


> [!IMPORTANT]
> Microsoft Lync Server 2010 Capacity Calculator は、CPU、メモリ、ハード ドライブなど、計画担当者がサーバーの要件を決定するのに使用できるすべての式があらかじめ設定されたスプレッドシートです。このスプレッドシートおよび関連するドキュメントは、<A class=uri href="http://go.microsoft.com/fwlink/?linkid=212657">http://go.microsoft.com/fwlink/?linkid=212657</A> でダウンロードできます。



フロント エンド サーバーには、フェールオーバーの状況で Mobility Service をサポートできる十分なメモリが必要です。\[**Memory\\Available Mbytes**\] カウンターを使用して、フロント エンド サーバーで現在使用可能なメモリを監視したり、上記の式を使用して、Mobility Service での使用が予想されるメモリ容量を計画したりできます。

予想されるモビリティ ユーザー数を計画するときにフロント エンド サーバーで使用可能なメモリ容量が 1,500 MB を下回る場合、Mobility Service をサポートできるようにハードウェアを追加する必要があります。詳細については、「操作」のドキュメントの「[モビリティのパフォーマンスの監視](lync-server-2013-monitoring-mobility-for-performance.md)」を参照してください。

## 関連項目

#### その他のリソース

[モビリティのパフォーマンスの監視](lync-server-2013-monitoring-mobility-for-performance.md)

