---
title: 'Lync Server 2013: MPLS ネットワーク上の通話受付管理'
TOCTitle: MPLS ネットワーク上の通話受付管理
ms:assetid: 0beec6be-2431-4255-a3d2-512dd030e66a
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg398168(v=OCS.15)
ms:contentKeyID: 48271228
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 による MPLS ネットワーク上の通話受付管理

 

_**トピックの最終更新日:** 2012-09-22_

Multiprotocol Label Switching (MPLS) では、すべてのサイトがフル メッシュで接続されます。つまり、すべてのサイトがインターネット サービス プロバイダーの MPLS バックボーンに直接接続され、各サイトが WAN リンクから MPLS にかけて使用されるプロビジョニングされた帯域幅であるということです。IP ルーティングを制御するネットワーク ハブやセントラル サイトはありません。次の図に、MPLS トポロジに基づく簡単なネットワークを示します。

**MPLS ネットワークの例**

![MPLS が含まれる CAC](images/Gg398168.54602e6e-ec11-4dae-936d-b01acda8a179(OCS.15).jpg "MPLS が含まれる CAC")

MPLS ネットワークで通話受付管理 (CAC) を展開するには、MPLS クラウドを表すネットワーク地域を作成し、MPLS の各サテライト サイトを表すネットワーク サイトを作成します。 次の図で、前の図の MPLS ネットワークの例を表すための、ネットワーク地域およびネットワーク サイトの構成方法について説明します。 全体的な帯域幅および帯域幅セッションの制限は、各ネットワーク サイトから MPLS クラウドを表すネットワーク地域までの WAN リンクの容量に基づきます。

**MPLS ネットワークのネットワーク地域およびネットワーク サイト**

![MPLS が含まれない通話受付管理 (CAC)](images/Gg398168.f8f76283-5c0c-4133-8a78-3fbbfd016dc4(OCS.15).jpg "MPLS が含まれない通話受付管理 (CAC)")

