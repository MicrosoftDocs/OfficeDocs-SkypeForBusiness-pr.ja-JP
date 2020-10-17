---
title: 'Lync Server 2013: ベストプラクティスアナライザーの概要'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of Best Practices Analyzer
ms:assetid: c5fcaa05-eb1c-4092-90ad-177b127e795b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg591349(v=OCS.15)
ms:contentKeyID: 48185364
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4dd3cda0375c7c7e9d15f2ecd31b47a1dee587c6
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48530724"
---
# <a name="overview-of-best-practices-analyzer-in-lync-server-2013"></a>Lync Server 2013 のベストプラクティスアナライザーの概要

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-19_

Lync Server 2013、ベストプラクティスアナライザーを使用して、Lync Server 2013 の展開に関する問題を特定し、解決することができます。 Lync Server 2013、ベストプラクティスアナライザーは、Lync Server 2013 コンポーネントから構成情報を収集します。

適切なネットワークアクセスにより、ベストプラクティスアナライザーは、Active Directory ドメインサービス、Exchange Server ユニファイドメッセージング (UM)、および Lync Server 2013 を実行しているサーバーを調査できます。 ベスト プラクティス アナライザーを使用して実行できるのは、以下の作業です。

  - 事前にチェックを実行して、推奨されるベスト プラクティスに従って構成が設定されていることを確認します。

  - Lync Server 2013 に対する必要な更新プログラムを自動的に検出します。

  - 最適化されていない構成設定、サポートされていないオプション、適用されていない更新プログラム、推奨されないプラクティスなど、問題の一覧を生成します。

  - 特定の問題のトラブルシューティングと修正を支援します。

ベスト プラクティス アナライザーは、以下の特徴を備えています。

  - 最小限のインストールの前提条件。

  - トラブルシューティングのヒントなど、レポートされた問題に関するオンライン ドキュメント。

  - 保存しておいて後で確認できる構成情報。

  - 最先端のシステム分析。

ベストプラクティスアナライザーは、一連の XML 構成ファイルを使用して、Lync Server 2013 環境から収集する情報を決定します。 Active Directory ドメイン サービスのチェックに加えて、Windows Management Instrumentation (WMI) での Windows Server オペレーティング システムのレジストリや設定などのソースをチェックします。

ベストプラクティスアナライザーは、Lync Server 2013 の展開の設定と構成について、定義済みのルールのセットで収集したデータを比較します。

収集したデータと事前定義されたルールを比較した後で、このツールは問題をレポートします。 レポートに含まれるすべての問題について、ベストプラクティスアナライザーは、スキャンされた Lync Server 2013 環境および推奨される構成についての情報を提供します。 また、特定の問題に関するさらに詳細な情報へのリンクも提供します。

<div>


> [!NOTE]  
> Lync Server 2013、ベストプラクティスアナライザーは、Lync Server 2013 コンポーネントからの構成情報のみを収集します。 以前の環境のスキャンには、このツールの以前のバージョンを使用することができます。 詳細については、「 <A href="lync-server-2013-requirements-for-running-best-practices-analyzer.md">Lync Server 2013 でベストプラクティスアナライザーを実行するための要件</A>」を参照してください。



</div>

</div>

<span> </span>

</div>

</div>

</div>

