---
title: Lync Server 2013 会議のロード配布
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Conferencing load distribution
ms:assetid: 5901a076-1b6f-4720-8837-95fc7f3c37f3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204922(v=OCS.15)
ms:contentKeyID: 48184233
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cd78b6dcedc66f5a2235b45066be7faf70d4379b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840466"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferencing-load-distribution-in-lync-server-2013"></a>Lync Server 2013 での会議のロード配布

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-22_

他のいくつかの専用会議ソリューションとは異なり、Lync Server アーキテクチャは共有ハードウェアモデルです。 これは、同じハードウェアが多くのソフトウェアコンポーネントによって共有されていることを意味します。各デバイスでは、リアルタイムのさまざまな通信がサポートされています。 各種類のリアルタイム通信は、サーバーに特定の負荷をかけます。 たとえば、フロントエンドサーバーでは、セッション開始プロトコル (SIP) ルーティングコンポーネント、web アプリケーション (アドレス帳検索など)、Web 会議サービス、A/V 会議サービス、エンタープライズボイスアプリケーション (会議など) を実行できます。アテンダントアプリケーションと応答グループアプリケーション) と仲介サーバー。 フロントエンドサーバー上の一連のデータベースでは、ユーザー、連絡先、プレゼンス、会議、音声ルーティングデータに対するストレージと処理も提供されます。 このハードウェア共有、コンポーネント、サービス、プロセスが CPU とメモリリソースに競合するため、会議以外のワークロードはサーバーのスケーリングに直接影響を与えます。

他のハードウェアポートベースの会議ソリューションと比べて、Lync Server 会議アーキテクチャは、非予約モデルです。 ユーザーが会議をスケジュールすると、Lync Server によって会議データベース内にレコードが作成されます。会議のデータは保存されますが、スケジュールされた会議のハードウェアリソースは事前に予約されません。 代わりに、Lync Server には負荷分散ロジックが組み込まれており、プール内のすべてのフロントエンドサーバー間で均等に負荷を分散するような方法で、フロントエンドサーバー上に会議リソースを動的に割り当てています。 これにより、ハードウェアリソースのプロビジョニングや使用が効果的に行われますが、大規模な会議 (特に適切な計画を必要としない) のサポートが困難になります。 たとえば、Lync Server 2013 プールが最上位の容量に近い状態で実行されている場合、各フロントエンドサーバーは約125の平均サイズの会議をホストしている可能性があります。 別の小規模な会議を追加しても問題はありませんが、1,000 ユーザーの会議を追加した場合、フロントエンド サーバーは他の 125 件の会議と同時にこのような大規模な会議をサポートできない可能性が高いため、問題が発生します。

</div>

<span> </span>

</div>

</div>

</div>

