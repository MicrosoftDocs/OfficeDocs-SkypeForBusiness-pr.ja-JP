---
title: 'Lync Server 2013: データ収集'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Data collection
ms:assetid: e40b03e5-455d-4bbc-831a-c61b1380db53
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399008(v=OCS.15)
ms:contentKeyID: 48185722
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1e198ecb80bbe0616422e10e1df18a8778196761
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138338"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="data-collection-in-lync-server-2013"></a>Lync Server 2013 のデータ収集

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-08_

Microsoft Lync Server 2013 communications software では、既存の IP アドレスとエッジサーバーの完全修飾ドメイン名 (Fqdn) を文書化することなく、Microsoft Lync Server 2013、計画ツールを実行できますが、これは非常に困難です。構成エラーが発生することはありません。 たとえば、長期間に共存が必要な場合は、Lync Server 2013 エッジ展開の既存のエッジ展開から Fqdn を再利用することがよくあります。 既存の IP アドレスと Fqdn を、スプレッドシート、テーブル、またはその他のビジュアルフォームに書き込まれるようにすることで、インストール時のセットアップの問題を防止するのに役立ちます。

<div>


> [!WARNING]  
> 以前のバージョンの計画ツールを使用していた場合は、トポロジを作成するためにツールを使用し、トポロジビルダーで使用するトポロジドキュメントをエクスポートしてトポロジを公開している可能性があります。 トポロジをエクスポートする機能は、計画ツールから削除されました。 以前のバージョンの計画ツールを使用して Lync Server 2013 のトポロジドキュメントを作成することはお勧めしません。予期しない結果が生じることがあります。



</div>

そのため、推奨される方法は、エッジトポロジに対応する次のデータ収集テンプレートを使用して、計画ツールに入力する必要のあるさまざまな FQDN と IP アドレスを収集することです。 現在の構成と提案されている構成を記録して、運用環境の適切なコンテキストに値を入力できます。 また、簡単な URL、ファイル共有、負荷分散などの新機能および共存をどのように構成するかを検討できます。

Microsoft Lync Server 2013 を正常に展開するには、個々のコンポーネントに対する相互作用とその依存について理解する必要があります。 既存のネットワークおよびサーバーインフラストラクチャからデータを収集し、これらのセクションの計画ガイダンスを適用することで、Lync Server 2013 エッジサーバーコンポーネントをインフラストラクチャに統合することができます。

[「Lync Server 2013 でのトポロジの選択](lync-server-2013-choosing-a-topology.md)」で導入された3つの主要なアーキテクチャには、合計5つの展開シナリオがあります。 これらのシナリオの1つは、データコレクションの開始点となります。 IP アドレス、サーバー名、およびドメイン名は、完全な計画ソリューションに必要な情報を詳述した、一致する証明書、ファイアウォール、および DNS の図と一致する例です。 必要な証明書、DNS、およびファイアウォールの値を図に記入することは、特に、証明機関の管理、ファイアウォールの構成および DNS がチーム以外のチームによって管理されているチーム間の通信で特に重要です。展開を計画します。 これらの図は、チーム間のグループ作業のためにこれらの要件を伝えるために使用できる必要なコンポーネントについての情報を提供します。

示されているダイアグラムには、意図的に汎用性を持たせていますが、ネットワーク、ファイアウォール、証明書の作成と管理、サーバーの展開、およびサーバーの管理が異なるグループによって処理される複数チームにわたるシナリオでの、要件の伝達に必要なすべての関連データの収集が可能です。 Lync Server の展開時には、ネットワーク、ファイアウォール、ポート、プロトコル、証明書、およびサーバーの構成について必要な詳細情報が非常に役立ちます。

**エッジサーバーとエッジプール**

![7624717a-ce99-4ae8-a929-2c4d74a2e47d](images/Gg399008.7624717a-ce99-4ae8-a929-2c4d74a2e47d(OCS.15).jpg "7624717a-ce99-4ae8-a929-2c4d74a2e47d")

**リバース プロキシ**

![cf63fc50-2d11-4334-afc8-2d664ba1b6bb](images/Gg399008.cf63fc50-2d11-4334-afc8-2d664ba1b6bb(OCS.15).jpg "cf63fc50-2d11-4334-afc8-2d664ba1b6bb")

**ディレクターまたはディレクター プール**

![56ba29ffe130947 d5debf5ce353 72169ebtx 7](images/Gg399008.56ba29ff-1309-4d5d-bf5c-35372169e947(OCS.15).jpg "56ba29ffe130947 d5debf5ce353 72169ebtx 7")

</div>

<span> </span>

</div>

</div>

</div>

