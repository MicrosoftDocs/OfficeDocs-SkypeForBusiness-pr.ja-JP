---
title: 'Lync Server 2013: 計画プロセスの開始'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Beginning the planning process
ms:assetid: df3722b3-f859-49e1-b3ff-ee6863483731
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398986(v=OCS.15)
ms:contentKeyID: 48185618
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a9da1c5535f190a6f57aa76b78a04845d4a073e2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741727"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="beginning-the-planning-process-for-lync-server-2013"></a>Lync Server 2013 の計画プロセスの開始

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-09-24_

オンプレミスのユニファイドコミュニケーションの展開を計画するときに、Lync Server には次のような便利なツールが2つ用意されています。

  - **計画ツール**は、組織、有効にする Lync Server 機能、キャパシティ計画についての一連の質問を表示するウィザードです。 次に、回答に基づいて推奨される展開トポロジを作成し、この展開の Microsoft Visio 図面を作成します。

  - **トポロジビルダー**は、Lync Server のインストールコンポーネントです。 トポロジビルダーを使用して、計画されたトポロジを作成、調整、および公開します。 また、サーバーのインストールを開始する前にトポロジを検証することもできます。 個々のサーバーに Lync Server をインストールすると、サーバーはインストールプロセスの一環として公開されたトポロジを読み取り、インストールプログラムはトポロジで指示されたとおりにサーバーを配置します。

<div>

## <a name="lync-server-planning-tool"></a>Lync Server 計画ツール

計画ツールは、ツールの質問に対する回答を受け取り、Lync Server のガイドラインとベストプラクティスに基づいたトポロジを生成します。 また、お客様の回答に基づいて展開の複数のビューを提供します。 すべてのサイト (セントラルサイトとブランチサイトを含む) のグローバルビューと、各サイトのサーバーやその他のコンポーネントを示す詳細ビューの両方が表示されます。

計画ツールを実行しても、特定の展開またはプロセスを開始することはできません。 実際に、計画ツールを使用していない場合でも、計画を立てておく必要がある場合は、計画プロセスで考慮する必要がある質問の種類を理解することができます。

計画ツールを複数回実行したり、質問に回答したり、結果を比較したりすることができます。 よく満足しているが、変更を加える必要があるデザインがある場合は、計画ツールに戻り、デザインを読み込んで、変更を加えることができます。 計画ツールの完了には15分ほどかかります。

問題が解決したら、計画ツールを使用して、計画した展開の図を作成することができます。 この図は、トポロジビルダーでの展開の作成時に使用できます。

<div>


> [!NOTE]  
> このリリースの Lync Server 2013 に含まれている計画ツールはプレリリース版です。 計画ツールの処理能力の計画の数値は暫定値であり、最終リリースではサポートされていません。



</div>

</div>

<div>

## <a name="lync-server-topology-builder"></a>Lync Server トポロジビルダー

展開計画を決定したら、トポロジビルダーを使用して展開を開始します。 完了したら、トポロジビルダーを使用してトポロジを検証し、合格した場合はトポロジを公開できます。 トポロジを公開すると、Lync Server によって、トポロジが、まだ存在していない場合は、この時点で作成されたセントラル管理ストアに配置されます。 展開の各サーバーに Lync Server をインストールすると、サーバーは中央管理ストアからトポロジを読み取り、それ自体を展開の役割に合わせてインストールします。

または、Lync Server についてよく理解していて、規範となるガイダンスが必要でない場合は、計画ツールをスキップし、展開の初期設計のためにトポロジビルダーのウィザードを使うことができます。また、検証と発行の手順を行うこともできます。

トポロジの計画と公開にトポロジビルダーを使用することは、必須の手順です。 展開内のサーバーにトポロジビルダーをスキップして Lync Server を個別にインストールすることはできません。 各サーバーは、中央管理ストアの有効な公開トポロジからトポロジを読み取る必要があります。

</div>

<div>

## <a name="high-level-planning-process"></a>高レベルの計画プロセス

ドキュメントと計画ツールの両方を使用して Lync Server の展開を計画する場合は、次の一般的なプロセスをお勧めします。

1.  以前のバージョンの Lync Server を使用している場合は、「lync server [2013 の新機能](lync-server-2013-new-features.md)」を参照して、lync server 2013 の新機能と要件について理解してください。

2.  ドキュメントのこのセクションの他のトピックを参照してください。トポロジの基礎 lync server [2013 の計画](lync-server-2013-topology-basics-you-must-know-before-planning.md)、lync [server 2013 のリファレンストポロジ](lync-server-2013-reference-topologies.md)、lync [server 2013 の最初の計画決定](lync-server-2013-initial-planning-decisions.md)、 [lync server 2013 のクライアント](lync-server-2013-clients.md)について説明します。 [Lync Server 2013 のリファレンストポロジ](lync-server-2013-reference-topologies.md)で採用されている計画の決定に注意してください。

3.  Lync Server の機能と、回答する必要がある質問の種類について詳しく理解したら、計画ツールを実行し、結果として得られたトポロジとその詳細を表示します。 トポロジが組織の固有の要件を満たしていることを確認します。

4.  特定のワークロードや機能が必要な場合、または詳しく知りたい場合は、「 [Lync Server 2013 の計画](lync-server-2013-planning.md)」の該当するセクションを参照してください。

5.  計画ツールをもう一度実行します。 手順3で作成した展開から作業を開始し、結果を変更したり、最初からやり直すことができます。
    
    必要に応じて、計画ツールを3回実行して、出力に問題がなければ繰り返します。

6.  トポロジ計画を完了したら、計画ツールを使用して、トポロジの Visio 図面を作成し、印刷します。 トポロジビルダーを操作しているときに、この印刷イメージを使用してトポロジを入力できます。

7.  展開を開始する前に、「 [lync server 2013 のシステム要件を決定](lync-server-2013-determining-your-system-requirements.md)する」および「lync server [2013 のインフラストラクチャ要件を決定](lync-server-2013-determining-your-infrastructure-requirements.md)する」を参照して、lync server の前提条件と必要なインフラストラクチャについて理解してください。 さらに、展開する予定のワークロードと機能に適用される[Lync Server 2013 の計画に関する](lync-server-2013-planning.md)すべてのセクションを既にお読みになっていることを確認してください。

</div>

<div>

## <a name="migrating-from-previous-versions"></a>以前のバージョンから移行する

以前のバージョンから Lync Server に移行する場合は、移行と展開に関する具体的な手順については、[移行](migration.md)に関するドキュメントを参照してください。

</div>

</div>

<span> </span>

</div>

</div>

</div>

