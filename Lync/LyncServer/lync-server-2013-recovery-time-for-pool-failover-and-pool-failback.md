---
title: Lync Server 2013 のプールフェールオーバーおよびプールフェールバックの回復時間
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Recovery time for pool failover and pool failback
ms:assetid: 902c658f-8442-4d0d-b3ad-bf795ecd550d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205079(v=OCS.15)
ms:contentKeyID: 48184786
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fb165fa762b23bd271dde56c0846ccb18adfbf7f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42183250"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="recovery-time-for-pool-failover-and-pool-failback-in-lync-server-2013"></a>Lync Server 2013 でのプールのフェールオーバーおよびプールのフェールバックの復旧時間

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-10_

プールのフェールオーバーおよびフェールバックで、エンジニアリング上想定される復旧時間目標 (RTO) は 30 分です。これは、管理者が障害の発生を認知してフェールオーバー手順を開始してから、フェールオーバーが発生するまでに必要な時間です。管理者が状況を評価して意思決定を行う時間は含まれていません。また、フェールオーバーの完了後にユーザーが再度サインインするまでの時間も含まれていません。

プールのフェールオーバーおよびフェールバックで、エンジニアリング上想定される復旧時点目標 (RPO) は 30 分です。 これは、障害が発生したときに、バックアップ サービスのレプリケーション待機時間に起因してデータが消失する可能性がある時間を表すものです。 たとえば、プールが 10:00 A.M. になり、RPO が30分になると、データは 9:30 A.M. からに書き込まれます。 および10:00 は、バックアッププールにレプリケートされていない可能性があり、失われます。

このドキュメントに示す RTO と RPO の数値はすべて、待ち時間の少ない高速接続で 2 つのサイトが結ばれている同じ地域内に 2 つのデータ センターが設置されていることを前提としています。 これらの番号は、データレプリケーションのバックログがない、事前に定義されたユーザーモデルに対して、4万の同時アクティブユーザーと Lync が有効になっている20万ユーザーが使用するプールに対して測定されます。 これらの数値は、パフォーマンス テストおよび検証に基づいて変更される可能性があります。

</div>

<span> </span>

</div>

</div>

</div>

