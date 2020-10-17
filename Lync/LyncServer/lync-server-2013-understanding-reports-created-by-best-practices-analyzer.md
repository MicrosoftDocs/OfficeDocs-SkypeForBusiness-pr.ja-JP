---
title: 'Lync Server 2013: ベストプラクティスアナライザーによって作成されたレポートについて'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Understanding reports created by Best Practices Analyzer
ms:assetid: 1386dd6c-7f3e-4da9-905b-cef1468bf14a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg591344(v=OCS.15)
ms:contentKeyID: 48183471
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 24699e685b58c718f6b67306c1eaa2d6974c87c5
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48527724"
---
# <a name="understanding-reports-created-by-best-practices-analyzer-in-lync-server-2013"></a>Lync Server 2013 でのベストプラクティスアナライザーによって作成されたレポートについて

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-10_

Best Practices Analyzer は、問題の分析と解決に役立つさまざまな種類のレポートを提供します。Best Practices Analyzer は、エラー、警告、その他の問題を特定します。

<div>

## <a name="reports"></a>レポート

次の各レポートを表示してスキャン結果を確認できます。

  - **リストレポート**    リストレポートは、特定の条件によって編成されます。 クラス、重要度、問題ごとに結果を整理できます。 たとえば、クラスごとに結果を整理すると、ディレクター関連の問題はレポートのディレクター セクションに表示されます。 すべての問題を表示することも、情報項目のみ表示することもできます。 メモリなど特定の項目についてリスト レポートを検索できます。 レポートを印刷したり、エクスポートしたりすることもできます。

  - **ツリーレポート**    ツリーレポートは、スキャンの実行時に指定したスキャンやその他のオプションを実行するために使用されるルールによって整理されます。 たとえば、テスト トポロジ ルール関連の問題はレポートのテスト トポロジ セクションに表示されます。 すべての問題の詳細を表示することも、問題の概要のみ表示することもできます。 メモリなど特定の項目についてツリー レポートを検索できます。 レポートを印刷したり、エクスポートしたりすることもできます。

  - **その他のレポート**    その他のレポート内の項目には、スキャンに含まれていたタスクの実行時ログが含まれています。 メモリなど特定の項目についてその他のレポートを検索できます。 レポートを印刷したり、エクスポートしたりすることもできます。

</div>

<div>

## <a name="issues"></a>問題

Best Practices Analyzer で生成されるレポートは、環境をスキャンして特定された次の種類の問題を示します。

  - **エラー**    環境に変更を加える必要がある重大な問題。 たとえば、Lync Server 2013 のコアコンポーネントがインストールされていない場合は、エラーがログに記録されます。

    エラーとして分類される問題は、レポート内に赤い X シンボルで示されます。エラーは、[**List Reports**] ビューの [**All Issues**] タブ、および [**Tree Reports**] ビューの [**Detailed View**] タブと [**Summary View**] タブに表示されます。特定のエラーをレポートに表示しないようにするには、レポートにそのエラーの 1 つのインスタンスまたはすべてのインスタンスが表示されないように指定できます。この場合、そのエラーは、設定を変更してレポートに表示されるように指定しない限り、[**Other Reports**] ビューの [**Hidden Items**] タブのみに表示されます。

  - **警告**    ベストプラクティスの実装と一貫性のない問題。 これは、環境に変更を行う必要がある場合とない場合があります。 変更する必要のない特定の設定に関する既知の問題である可能性もあります。 たとえば、サーバーで開始されていないサービスがあると警告として記録されます。

    警告として分類される問題は、レポート内に黄色の三角形の警告シンボルで示されます。警告は、[**List Reports**] ビューの [**All Issues**] タブ、および [**Tree Reports**] ビューの [**Detailed View**] タブと [**Summary View**] タブに表示されます。特定の警告をレポートに表示しないようにするには、レポートにその警告の 1 つのインスタンスまたはすべてのインスタンスが表示されないように指定できます。この場合、その警告は、設定を変更してレポートに表示されるように指定しない限り、[**Other Reports**] ビューの [**Hidden Items**] タブのみに表示されます。

  - **情報**    エラーまたは警告として分類されないすべての問題を含みます。 たとえば、Active Directory ドメインサービス内の Lync Server 2013 Standard Edition サーバーオブジェクトの数は、情報の問題として分類されます。

    情報項目は、[**List Reports**] ビューの [**All Issues**] タブ、および [**Tree Reports**] ビューの [**Detailed View**] タブに表示されます。

Lync Server 2013、ベストプラクティスアナライザーは、問題を解決するために環境を変更することはありません。 スキャンは、潜在的な問題を検出し、各問題の解決方法に関する情報が記載されたレポートを提供するのみです。

問題をクリックすると、特定の問題に関する説明とオプションが表示されます。その後、次のいずれかの操作を実行できます。

  - その問題に関する詳細情報と解決方法を調べます。

  - レポートに問題を表示しないようにします。

      - その問題の選択したインスタンスを表示しないようにします。

      - その問題のすべてのインスタンスを表示しないようにします。

    レポートに表示しないようにした問題を確認するには、[**Other Reports**] ビューの [**Hidden Items**] タブを開きます。そのタブで、レポートへの問題の表示を再開するように指定できます。

特定の問題を解決する方法の詳細については、「 [Lync Server 2013 のベストプラクティスアナライザーによって識別された問題の分析と解決](lync-server-2013-analyzing-and-resolving-issues-identified-by-best-practices-analyzer.md)」を参照してください。

</div>

</div>

<span> </span>

</div>

</div>

</div>
