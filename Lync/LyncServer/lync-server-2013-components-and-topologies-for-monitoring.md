---
title: 'Lync Server 2013: 監視用のコンポーネントとトポロジ'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components and topologies for monitoring
ms:assetid: c1bb36b0-1fb8-4d8e-9cc9-9bef740fe3c6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412952(v=OCS.15)
ms:contentKeyID: 48185313
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bf9724089eeed36d48cbce8e1872078e3940beae
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48502524"
---
# <a name="components-and-topologies-for-monitoring-in-lync-server-2013"></a>Lync Server 2013 で監視するためのコンポーネントとトポロジ

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-05_

ユニファイドデータ収集エージェントは各フロントエンドサーバーに自動的にインストールされ、アクティブ化されるため、監視サーバーとして動作するようにサーバーを構成する必要はありません。各フロントエンドサーバーは、既に監視サーバーとして機能します。 ただし、監視データのバックエンドデータストアとして機能するデータベースをインストールして構成する必要があります。 Microsoft Lync Server 2013 では、監視用のバックエンドストアとして次のいずれかのデータベースを使用できます。

  - Microsoft SQL Server 2008 R2 Enterprise Edition

  - Microsoft SQL Server 2008 R2 Standard Edition

  - Microsoft SQL Server 2012 Enterprise Edition

  - Microsoft SQL Server 2012 Standard Edition

これらのデータベースの64ビット版を使用する必要があることに注意してください。32ビットバージョンの SQL Server を監視用のバックエンドストアとして使用することはできません。 同様に、Lync Server 2013 では、SQL Server 2008 または SQL Server 2012 の Express Edition はサポートされていません。 Lync Server 2013 のデータベース要件の詳細については、「Lync server 2013 サポートガイド」の「 [Lync server 2013 のデータベースソフトウェアサポート](lync-server-2013-database-software-support.md) 」を参照してください。

監視を展開して構成する前に、SQL Server をインストールして構成しておく必要があることに注意してください。 ただし、SQL Server 自体を展開する必要はありません。事前に監視データベースをセットアップする必要はありません。 その代わりに、Lync Server トポロジを公開すると、これらのデータベースが自動的に作成されます。

監視データは、SQL Server インスタンスを他の種類のデータと共有できます。 通常、通話詳細記録データベース (LcsCdr) と Qquality of Experience データベース (QoEMetrics) は同じ SQL インスタンスを共有します。また、2つの監視データベースがアーカイブデータベース (LcsLog) と同じ SQL インスタンスに存在することもよくあります。 SQL Server インスタンスに関する実際の要件については、SQL Server のいずれか1つのインスタンスが以下のように制限されます。

  - Lync Server 2013 バックエンドデータベースの1つのインスタンス。 (一般的な規則として、監視データベースをバックエンドデータベースと同じ SQL インスタンスまたは同じコンピューター上に共存させることはお勧めできません。 技術的には可能ですが、バックエンドデータベースに必要な空きディスク領域を使用して監視データベースのリスクを実行します。

  - 呼び出し詳細記録データベースの1つのインスタンス。

  - Qoe (Quality of Experience) データベースの1つのインスタンス。

  - アーカイブデータベースの1つのインスタンス。

つまり、1つの SQL Server インスタンスに LcsCdr データベースのインスタンスを2つ持つことはできません。 LcsCdr データベースのインスタンスが複数必要な場合は、SQL Server の複数のインスタンスを構成する必要があります。

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 での監視の展開](lync-server-2013-deploying-monitoring.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

