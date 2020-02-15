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
ms.openlocfilehash: dd0a83042415cd2cf919d0fd66fe5309a4cae9e9
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42041166"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="beginning-the-planning-process-for-lync-server-2013"></a>Lync Server 2013 の計画プロセスの開始

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-24_

オンプレミスのユニファイドコミュニケーションの展開を計画する際に、Lync Server には次の2つの重要なツールがあります。

  - **計画ツール**は、組織、有効にする Lync Server 機能、および容量計画についての一連の質問を提供するウィザードです。 次に、回答に基づいて推奨される展開トポロジを作成し、この展開の Microsoft Visio 図面を生成します。

  - **トポロジビルダー**は、Lync Server のインストールコンポーネントです。 トポロジビルダーを使用して、計画したトポロジを作成、調整、および発行します。 また、サーバーのインストールを開始する前にトポロジを検証します。 個々のサーバーに Lync Server をインストールすると、サーバーはインストールプロセスの一環として公開されたトポロジを読み取り、インストールプログラムはトポロジ内で指示されたとおりにサーバーを展開します。

<div>

## <a name="lync-server-planning-tool"></a>Lync Server Planning Tool

計画ツールは、ツールの質問に対する回答を受け取り、Lync Server のガイドラインとベストプラクティスに基づいたトポロジを生成します。 また、解答に基づいて展開の複数のビューを提供します。 この図は、すべてのサイト (セントラルサイトとブランチサイトを含む) のグローバルビューと、各サイトのサーバーとその他のコンポーネントを示す詳細ビューを示しています。

計画ツールを実行しても、特定の展開には反映されません。また、すべてのプロセスが開始されるわけではありません。 実際には、計画プロセスで考慮する必要のある質問の種類を理解するには、非常に有益な計画ツールを使用していることがあります。

計画ツールを複数回実行して、異なる質問に回答し、結果を比較することができます。 設計がほとんど問題なく、変更する必要がある場合は、計画ツールに戻り、設計を読み込んで、変更を行うことができます。 計画ツールを一度に完了するのに15分ほどかかります。

問題がなければ、計画ツールを使用して、計画した展開の図を作成できます。 この図は、トポロジビルダーで展開を作成するときに使用できます。

<div>


> [!NOTE]  
> このリリースの Lync Server 2013 に含まれている計画ツールはプレリリースバージョンです。 計画ツールの処理能力の計画の数値は暫定値であり、最終リリースではサポートされていません。



</div>

</div>

<div>

## <a name="lync-server-topology-builder"></a>Lync Server トポロジビルダー

展開計画を決定したら、トポロジビルダーを使用して展開を開始します。 完了したら、トポロジビルダーを使用してトポロジを検証し、合格した場合はトポロジを公開できます。 トポロジを公開すると、Lync Server はトポロジを中央管理ストアに配置します。これは、この時点でまだ存在していない場合には作成されます。 展開内の各サーバーに Lync Server をインストールすると、サーバーは中央管理ストアからトポロジを読み取り、それ自体を展開内の役割に合わせてインストールします。

または、Lync Server に精通していて、規範となるガイダンスが必要ない場合は、計画ツールをスキップして、展開の初期設計および検証と発行の手順に関するウィザードをトポロジビルダーで使用することもできます。

トポロジビルダーを使用したトポロジの計画と公開は、必要な手順です。 トポロジビルダーをバイパスして、展開内のサーバーに Lync Server を個別にインストールすることはできません。 各サーバーは、中央管理ストア内の公開された検証済みトポロジからトポロジを読み取る必要があります。

</div>

<div>

## <a name="high-level-planning-process"></a>計画プロセスの概要

ドキュメントと計画ツールの両方を使用して Lync Server の展開を計画するには、次の一般的な手順を実行することをお勧めします。

1.  以前のバージョンの Lync Server を使い慣れている場合は、lync server [2013 の新機能](lync-server-2013-new-features.md)を参照して、lync server 2013 の新機能と要件について理解してください。

2.  「Lync server [2013 の計画の前に知っておく必要があるトポロジの基礎](lync-server-2013-topology-basics-you-must-know-before-planning.md)」、「lync server [2013 の参照トポロジ](lync-server-2013-reference-topologies.md)」、「[最初の lync server 2013](lync-server-2013-initial-planning-decisions.md)」、および「 [lync server 2013 のクライアント](lync-server-2013-clients.md)」のドキュメントのこのセクションの他のトピックを参照してください。 [Lync Server 2013 のリファレンストポロジ](lync-server-2013-reference-topologies.md)で示されている計画上の決定事項に注意してください。

3.  Lync Server の機能と応答する必要のある質問の種類について理解したので、計画ツールを実行し、結果のトポロジとその詳細を確認します。 トポロジが組織の固有の要件に適合していることを確認してください。

4.  特定のワークロードまたは機能が必要な場合や、詳細について知りたい場合は、「 [Lync Server 2013 の計画](lync-server-2013-planning.md)」の該当するセクションを参照してください。

5.  計画ツールをもう一度実行します。 手順3で作成した展開から開始して、結果を変更するか、または最初からやり直すことができます。
    
    必要に応じて、計画ツールを3回実行し、出力に問題がなければ繰り返します。

6.  トポロジ計画の最終処理が完了したら、計画ツールを使用して、トポロジの Visio 図面を作成および印刷します。 トポロジビルダーを使用してトポロジを入力するときに、この印刷結果を使用することができます。

7.  展開を開始する前に、「 [lync server 2013 のシステム要件を決定](lync-server-2013-determining-your-system-requirements.md)する」および「lync server [2013 のインフラストラクチャ要件を決定](lync-server-2013-determining-your-infrastructure-requirements.md)して、lync server の前提条件と必要なインフラストラクチャを理解する」をお読みください。 また、展開する予定のワークロードと機能に適用される[Lync Server 2013 の計画に関する](lync-server-2013-planning.md)すべてのセクションを必ずお読みください。

</div>

<div>

## <a name="migrating-from-previous-versions"></a>以前のバージョンからの移行

以前のバージョンから Lync Server に移行する場合は、移行と展開に関する具体的な手順については、[移行](migration.md)に関するドキュメントを参照してください。

</div>

</div>

<span> </span>

</div>

</div>

</div>

