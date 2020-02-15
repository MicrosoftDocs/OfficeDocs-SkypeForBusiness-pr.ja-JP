---
title: Lync Server 2013 のスケーラビリティテスト
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Scalability testing
ms:assetid: bf41bac6-d4ec-4de6-9a44-a82d01a87279
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205226(v=OCS.15)
ms:contentKeyID: 48185289
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b23bd731e123c8dba78c3919f9f2a1ff1a6fd1cf
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049889"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="scalability-testing-in-lync-server-2013"></a>Lync Server 2013 のスケーラビリティテスト

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-01_

Lync Server 2013 には、インスタントメッセージング (IM) とプレゼンス、会議、エンタープライズ Voip など、すべての Lync Server のリアルタイム通信のサーバーインフラストラクチャが用意されています。 これには、Lync Server 2013 プールのハードウェアリソースを使用するすべての機能が含まれるため、パフォーマンスと規模に影響します。 すべての組織がすべての機能を同じように使用するわけではありません。

たとえば、組織によっては、会議で非常に頻繁にビデオを使用している場合がありますが、ビデオの使用状況が少ない、またはまったくない場合があります。 一部の組織では、アプリケーション共有に PowerPoint スライドの共有を優先していますが、反対のものを好むこともあります。 エンタープライズ Voip を展開する組織では、応答グループアプリケーションが頻繁に使用されない場合があります。 ほとんどの組織では、監視サーバーを展開していますが、その多くはアーカイブサーバーを展開していません。 さらに、組織によって、ハードウェアの容量、ネットワークの容量、プールの数と展開されたプールの数を含む、同じインフラストラクチャが存在するわけではありません。 機能とインフラストラクチャの多様性は、スケーラビリティのテストにおいて課題となり、機能とインフラストラクチャのすべての可能な組み合わせをシミュレートすることはできません。

Lync Server のスケーラビリティのサポートを決定するには、平均利用モデル (ユーザーモデル) に基づいて、すべての Lync Server 機能を同時に使用してテストを行います。 Lync Server ワークロードに適したユーザーモデルを決定するために、お客様の調査、Microsoft カスタマーエクスペリエンス向上プログラムからのフィードバック、Microsoft の内部 IT 部門からの Lync Server の使用状況データなど、多くのデータポイントを分析します。およびデータは、Live Meeting サービスからマイニングされます。 多くの場合、組織内の使用に関して十分な余裕を持たせるために、ユーザー モデルは負荷が高い方向に偏っています。

スケーラビリティテストでは、Active Directory ドメインサービス、ハードウェアロードバランサー、ファイアウォールなどのインフラストラクチャコンポーネントを含む、推奨されるハードウェアおよびソフトウェア仕様に従って Lync Server 2013 プールを設定します。 Lync Server 環境は、一般的な実際の環境にできるだけ近づけるようにセットアップされています。 次に、Lync server 2013 ストレスおよびパフォーマンスツールを使用して、Lync Server 2013 の負荷 (ユーザーモデルに基づいて) をシミュレートします。 .

スケーラビリティ テストは複数回繰り返します (3 週間にわたるテストの複数回の実行を含みます)。すべてのテスト結果を使用して、パフォーマンス チューニングに役立てるとともに、ユーザー モデルでのスケーラビリティの数値がサポートされることを検証します。

</div>

<span> </span>

</div>

</div>

</div>

