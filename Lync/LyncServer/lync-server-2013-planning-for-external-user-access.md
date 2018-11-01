---
title: 'Lync Server 2013: 外部ユーザー アクセスの計画'
TOCTitle: 外部ユーザー アクセスの計画
ms:assetid: ea098933-eff5-461e-aba3-e7f128784dc2
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg399048(v=OCS.15)
ms:contentKeyID: 48274031
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 の外部ユーザー アクセスの計画

 

_**トピックの最終更新日:** 2013-01-19_

ほとんどの組織の通信には、内部ネットワーク外のサービスやユーザーが関与しています。 これらのサービスやユーザーには、一時的または恒久的にオフサイトにいる従業員、顧客組織やパートナー組織の従業員、パブリック インスタント メッセージング (IM) サービスの利用者、会議やプレゼンテーションに招待した見込み顧客やパートナー、匿名ユーザーなどが含まれます。 このドキュメントでは、これらの人々を総称して外部ユーザー と呼びます。

Microsoft Lync Server 2013 を利用すると、組織内のユーザーは IM やプレゼンスを使用して外部ユーザーと通信したり、オフサイトの従業員やその他のタイプの外部ユーザーとの音声ビデオ (A/V) 会議や Web 会議に参加したりできます。 モバイル デバイスからの外部アクセスや、エンタープライズ VoIP を利用した外部アクセスもサポートできます。 組織のメンバーでない外部ユーザーでも Lync Server 2013 会議に参加できるため、匿名での出席が可能です。

組織のファイアウォールを横断する通信をサポートするために、Lync Server 2013 エッジ サーバーを境界ネットワーク (別名 DMZ、非武装地帯、およびスクリーン サブネット) に展開します。 エッジ サーバーでは、ファイアウォールの外側にいるユーザーが内部の Lync Server 2013 展開に接続する方法が制御されます。 ファイアウォールの内側から発信された外部ユーザーへの通信も制御します。

要件に応じて、1 つまたは複数の場所に、1 つまたは複数のエッジ サーバーを展開できます。 このセクションでは、Lync Server 2013 の外部ユーザー アクセスと、エッジ トポロジおよびリバース プロキシ トポロジの計画方法のシナリオについて説明します。

> [!NOTE]
> エッジ サーバーでは、エンタープライズ VoIP と外部ユーザー アクセスがサポートされている必要がありますが、このセクションでは、IM、プレゼンス、音声ビデオ会議、フェデレーション、Web 会議、および Lync Mobile のサポートに絞って説明します。 エンタープライズ VoIP のサポートの詳細については、「計画」のドキュメントの「<a href="lync-server-2013-planning-for-enterprise-voice.md">Lync Server 2013 でのエンタープライズ VoIP の計画</a>」を参照してください。


## このセクション中

  - [エッジ サーバーの計画に影響する Lync Server 2013 での変更点](lync-server-2013-changes-in-lync-server-that-affect-edge-server-planning.md)

  - [Lync Server 2013 の外部ユーザー アクセス コンポーネントのシステム要件](lync-server-2013-system-requirements-for-external-user-access-components.md)

  - [Lync Server 2013 における外部ユーザー アクセスの概要](lync-server-2013-overview-of-external-user-access.md)

  - [自動検出について](lync-server-2013-understanding-autodiscover.md)

  - [Lync Server 2013 でのトポロジの選択](lync-server-2013-choosing-a-topology.md)

  - [Lync Server 2013 のデータの収集](lync-server-2013-data-collection.md)

  - [Lync Server 2013 の DNS の要件を確認する](lync-server-2013-determine-dns-requirements.md)

  - [Lync Server 2013 の外部の音声ビデオ ファイアウォールおよびポートの要件を決定する](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)

  - [Lync Server 2013 でエッジ サーバー証明書を計画する](lync-server-2013-plan-for-edge-server-certificates.md)

  - [Lync Server 2013 の外部ユーザー アクセスのシナリオ](lync-server-2013-scenarios-for-external-user-access.md)

