---
title: Lync Server 2013 会議の負荷分散
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conferencing load distribution
ms:assetid: 5901a076-1b6f-4720-8837-95fc7f3c37f3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204922(v=OCS.15)
ms:contentKeyID: 48184233
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 66cfdab2f59ca29022435a1f7863e8fce79075e6
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42199130"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="conferencing-load-distribution-in-lync-server-2013"></a>Lync Server 2013 での会議の負荷分散

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-22_

その他の専用会議ソリューションとは異なり、Lync Server アーキテクチャは共有ハードウェアモデルです。 つまり、それぞれ異なるリアルタイム通信をサポートする多数のソフトウェア コンポーネントが同じハードウェアを共有します。 各種リアルタイム通信によって、サーバーに一定の負荷がかかります。 たとえば、フロントエンドサーバーでは、セッション開始プロトコル (SIP) ルーティングコンポーネント、web アプリケーション (アドレス帳検索など)、Web 会議サービス、音声ビデオ会議サービス、エンタープライズ Voip アプリケーション (会議アテンダントアプリケーションや応答グループアプリケーションなど)、仲介サーバーを実行できます。 フロントエンドサーバー上のデータベースのセットは、ユーザー、連絡先、プレゼンス、会議、音声ルーティングデータの格納と処理も行います。 このハードウェア共有により、コンポーネント、サービス、プロセスの間で CPU リソースとメモリ リソースの競合が発生するので、電話会議ワークロード以外のワークロードがサーバーの拡張に直接影響を及ぼします。

他のハードウェアポートベースの電話会議ソリューションと比較して、Lync Server 会議アーキテクチャは予約なしモデルです。 ユーザーが会議をスケジュールすると、Lync Server は会議データベースにレコードを作成しますが、会議データを保存しますが、スケジュールされた会議のハードウェアリソースは事前に予約しません。 代わりに、Lync Server には負荷分散ロジックが組み込まれており、プール内のすべてのフロントエンドサーバー間で負荷が均等に分散されるように、フロントエンドサーバーに電話会議リソースを動的に割り当てることができます。 これにより、ハードウェア リソースが効果的にプロビジョニングされて使用されますが、大規模な会議 (特に、適切に計画されていない大規模な会議) のサポートが困難になります。 たとえば、Lync Server 2013 プールが最上位の容量に近い時間に稼働している場合、各フロントエンドサーバーは約125の平均サイズの会議をホストすることがあります。 別の小規模な会議を追加しても問題はありませんが、フロントエンドサーバーが他の125会議と同時にこのような大規模な会議をサポートすることができない可能性があるため、1000ユーザーの会議を追加することは問題になります。

</div>

<span> </span>

</div>

</div>

</div>

