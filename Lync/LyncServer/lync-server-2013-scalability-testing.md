---
title: Lync Server 2013 のスケーラビリティテスト
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Scalability testing
ms:assetid: bf41bac6-d4ec-4de6-9a44-a82d01a87279
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205226(v=OCS.15)
ms:contentKeyID: 48185289
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f454ad3d78affb7106bcd0e750adae13624d9c9b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822273"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="scalability-testing-in-lync-server-2013"></a>Lync Server 2013 でのスケーラビリティのテスト

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-01_

Lync Server 2013 は、インスタントメッセージング (IM) とプレゼンス、会議、エンタープライズ Voip など、すべての Lync Server のリアルタイム通信のサーバーインフラストラクチャを提供します。 これには、Lync Server 2013 プールのハードウェアリソースを使用するすべての機能が含まれます。そのため、パフォーマンスと規模が影響を受けます。 すべての組織が同じ機能を使用するわけではありません。

たとえば、一部の組織では、会議でビデオを頻繁に使用することもありますが、ビデオの使用量が少ない、またはまったくない場合もあります。 一部の組織では、PowerPoint スライドの共有をアプリケーション共有に適用していますが、その他の場合は反対のことを好みます。 エンタープライズボイスを展開する組織では、応答グループアプリケーションが多用されている可能性があります。 ほとんどの組織では、監視サーバーを展開していますが、その多くはアーカイブサーバーを展開しています。 さらに、組織には、ハードウェアの容量、ネットワークの容量、プールの数、展開されているプールのサイズなど、同じインフラストラクチャが含まれているわけではありません。 機能とインフラストラクチャの多様性は、スケーラビリティテストの課題となります。機能とインフラストラクチャのすべての可能な組み合わせをシミュレートすることはできません。

Lync Server のスケーラビリティのサポートを判断するには、平均的な利用モデル (ユーザーモデル) に基づいて、すべての Lync Server 機能を同時に使用してテストを実施します。 Lync Server のワークロードに適したユーザーモデルを決定するために、Microsoft の社内の IT 部門からのお客様のアンケート、Microsoft カスタマーエクスペリエンス向上プログラムからのフィードバック、Lync Server の使用状況データなど、さまざまなデータを分析します。また、skype Live Meeting サービスからデータを抽出します。 多くの場合、ユーザーモデルは、組織内での使用に適した余白を提供するために、負荷が高くなるようにバイアスしています。

Skype のスケーラビリティテストでは、Active Directory ドメインサービス、ハードウェアロードバランサー、ファイアウォールなどのインフラストラクチャコンポーネントなど、推奨されるハードウェアとソフトウェア仕様に従って Lync Server 2013 プールをセットアップします。 Lync Server 環境は、実際の一般的な環境にできるだけ近づけるようにセットアップしています。 次に、Lync Server 2013 ストレス/パフォーマンスツールを使用して、Lync Server 2013 のロード (ユーザーモデルに基づく) をシミュレートします。 .

スケーラビリティテスト (複数の3週間テストの実行を含む) を複数回繰り返します。 すべてのテストの結果を使用して、パフォーマンスの調整を行い、ユーザーモデルのスケーラビリティ数のサポートを確認します。

</div>

<span> </span>

</div>

</div>

</div>

