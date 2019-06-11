---
title: 'Lync Server 2013: データの収集'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Data collection
ms:assetid: e40b03e5-455d-4bbc-831a-c61b1380db53
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399008(v=OCS.15)
ms:contentKeyID: 48185722
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: df4f19df012dfeac7576cc5b39d749564a4350a1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833740"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="data-collection-in-lync-server-2013"></a>Lync Server 2013 のデータの収集

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-09-08_

Microsoft Lync Server 2013 通信ソフトウェアでは、既存および提案された IP アドレスとエッジサーバーの完全修飾ドメイン名 (Fqdn) を文書化することなく、Microsoft Lync Server 2013、計画ツールを実行できますが、これは非常に困難です。そのため、構成エラーが発生することはありません。 たとえば、一定の期間共存が必要な場合は、Lync Server 2013 Edge の展開のために既存のエッジ展開から Fqdn を再利用することがよくあります。 既存の IP アドレスと Fqdn をスプレッドシート、表、またはその他の視覚的な形式で書き留めておくと、インストール時のセットアップの問題を防ぐのに役立ちます。

<div>


> [!WARNING]  
> 計画ツールの以前のバージョンを使用したことがある場合は、トポロジの作成にこのツールを使用し、トポロジビルダーで使用するトポロジドキュメントをエクスポートしてトポロジを公開している可能性があります。 トポロジのエクスポート機能が計画ツールから削除されました。 以前のバージョンの計画ツールを使用して、Lync Server 2013 のトポロジドキュメントを作成することはお勧めできません。予期しない結果が生成されます。



</div>

したがって、推奨される方法は、次のデータコレクションテンプレートを使用することです。これは、Edge トポロジに対応しており、計画ツールに入力する必要があるさまざまな FQDN と IP アドレスを収集します。 現在の構成と提案された構成を文書化することで、実稼働環境の適切なコンテキストに値を配置することができます。 また、単純な Url、ファイル共有、負荷分散などの共存と機能をどのように構成するかを考える必要があります。

Microsoft Lync Server 2013 を正常に展開するには、個々のコンポーネントに対する操作と依存関係を理解している必要があります。 既存のネットワークとサーバーインフラストラクチャからデータを収集し、計画ガイダンスを適用することで、Lync Server 2013 エッジサーバーコンポーネントをインフラストラクチャに統合することができます。

「 [Lync Server 2013 でのトポロジの選択](lync-server-2013-choosing-a-topology.md)」で説明した3つの主要なアーキテクチャには、合計5つの展開シナリオが含まれています。 これらのシナリオのいずれかが、データ収集の出発点になります。 IP アドレス、サーバー名、ドメイン名は、完全な計画ソリューションに必要な情報について説明する、一致する証明書、ファイアウォール、DNS ダイアグラムと一致する例です。 必要な証明書、DNS、ファイアウォールの値の図と入力は、チーム間通信では特に重要であり、証明機関、ファイアウォール構成、DNS はチーム以外のチームによって管理されます。展開を計画します。 これらの図は、チーム間での共同作業のためにこれらの要件を伝えるために使用できる必須コンポーネントについて説明しています。

提供されているダイアグラムは意図的に標準であり、ネットワーク、ファイアウォール、証明書の作成と管理、サーバーなど、チーム間での要件の通信に必要なすべての関連データを収集することを許可します。展開とサーバー管理は、さまざまなグループで処理されます。 Lync Server の展開が進行中の場合は、ネットワーク、ファイアウォール、ポート、プロトコル、証明書、サーバーの構成に必要な詳細情報が非常に重要になります。

**エッジサーバーとエッジプール**

![7624717a-ce99-4ae8-a929-2c4d74a2e47d](images/Gg399008.7624717a-ce99-4ae8-a929-2c4d74a2e47d(OCS.15).jpg "7624717a-ce99-4ae8-a929-2c4d74a2e47d")

**リバースプロキシ**

![cf63fc50-2d11-4334-afc8-2d664ba1b6bb](images/Gg399008.cf63fc50-2d11-4334-afc8-2d664ba1b6bb(OCS.15).jpg "cf63fc50-2d11-4334-afc8-2d664ba1b6bb")

**ディレクターまたはディレクタープール**

![56 ba29ff001 130916d5d56 72169e・]デ・・・・・・・・・・ライド7(images/Gg399008.56ba29ff-1309-4d5d-bf5c-35372169e947(OCS.15).jpg "56 ba29ff001 130916d5d56 72169e・")デ・・・・・・・・・・ライド7

</div>

<span> </span>

</div>

</div>

</div>

