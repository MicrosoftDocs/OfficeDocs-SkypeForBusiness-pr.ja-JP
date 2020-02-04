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
ms.openlocfilehash: 53e63bf6063803364a679a3cc0724ec1cbeae1a2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755601"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-best-practices-analyzer-in-lync-server-2013"></a>Lync Server 2013 のベストプラクティスアナライザーの概要

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-09-19_

Lync Server 2013 のベストプラクティスアナライザーを使用して、Lync Server 2013 の展開に関する問題を特定して解決することができます。 Lync Server 2013 のベストプラクティスアナライザーは、Lync Server 2013 コンポーネントから構成情報を収集します。

ベストプラクティスアナライザーは、適切なネットワークアクセスで、Active Directory ドメインサービス、Exchange Server ユニファイドメッセージング (UM)、および Lync Server 2013 を実行しているサーバーを調査できます。 ベストプラクティスアナライザーを使用して、次の操作を行うことができます。

  - 事前にチェックを行い、推奨されるベストプラクティスに従って構成が設定されていることを確認します。

  - Lync Server 2013 に必要な更新プログラムを自動的に検出します。

  - 最適の構成設定、サポートされていないオプション、不足している更新、または推奨されないプラクティスなどの問題の一覧を生成します。

  - 特定の問題のトラブルシューティングと解決に役立ちます。

ベストプラクティスアナライザーには、次の機能が用意されています。

  - インストールの最小要件。

  - トラブルシューティングのヒントを含む、報告された問題に関するオンラインドキュメント。

  - 後で確認するために保存できる構成情報。

  - 最新のシステムの分析。

ベストプラクティスアナライザーは、一連の XML 構成ファイルを使用して、Lync Server 2013 環境から収集する情報を決定します。 Active Directory ドメインサービスの確認に加えて、windows Server オペレーティングシステムのレジストリと、Windows Management Instrumentation (WMI) の設定などのソースを確認します。

ベストプラクティスアナライザーは、収集したデータを、Lync Server 2013 展開の設定と構成に関する事前定義されたルールのセットと比較します。

収集したデータと事前定義されたルールを比較した後、ツールによって問題が報告されます。 レポートされるすべての問題について、ベストプラクティスアナライザーは、スキャンされた Lync Server 2013 環境と推奨される構成についての情報を提供します。 ベストプラクティスアナライザーには、特定の問題に関する詳細情報へのリンクも含まれています。

<div>


> [!NOTE]  
> Lync Server 2013 のベストプラクティスアナライザーは、Lync Server 2013 コンポーネントからのみ構成情報を収集します。 以前のバージョンのツールを使用して、以前の環境をスキャンすることができます。 詳細については、「 <A href="lync-server-2013-requirements-for-running-best-practices-analyzer.md">Lync Server 2013 でベストプラクティスアナライザーを実行するための要件</A>」を参照してください。



</div>

</div>

<span> </span>

</div>

</div>

</div>

