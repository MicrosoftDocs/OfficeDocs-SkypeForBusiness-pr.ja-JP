---
title: 'Lync Server 2013: 監視のためのコンポーネントとトポロジ'
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
ms.openlocfilehash: 76e857d0c80793f61b8e60686cc9455d27bb9f95
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742597"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-monitoring-in-lync-server-2013"></a>Lync Server 2013 における監視のためのコンポーネントとトポロジ

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-09-05_

統合データ収集エージェントは、各フロントエンドサーバーに自動的にインストールされてアクティブ化されるため、監視サーバーとして動作するようにサーバーを構成する必要はありません。各フロントエンドサーバーは、既に監視サーバーとして機能します。 ただし、監視データのバックエンドデータストアとして機能するようにデータベースをインストールして構成する必要があります。 Microsoft Lync Server 2013 では、監視のバックエンドストアとして次のデータベースのいずれかを使用できます。

  - Microsoft SQL Server 2008 R2 Enterprise Edition

  - Microsoft SQL Server 2008 R2 Standard Edition

  - Microsoft SQL Server 2012 Enterprise Edition

  - Microsoft SQL Server 2012 Standard Edition

これらのデータベースの64ビット版を使用する必要があることに注意してください。32ビットバージョンの SQL Server は、監視用のバックエンドストアとして使用することはできません。 同様に、Lync Server 2013 は、SQL Server 2008 または SQL Server 2012 の Express エディションをサポートしていません。 Lync Server 2013 のデータベース要件の詳細については、「lync Server 2013 サポートガイド」の「 [Lync server 2013 でのデータベースソフトウェアのサポート](lync-server-2013-database-software-support.md)」を参照してください。

監視を展開して構成する前に、SQL Server をインストールして構成する必要があることに注意してください。 ただし、SQL Server 自体のみを展開する必要があります。事前に監視データベースを設定する必要はありません。 代わりに、Lync Server トポロジを公開すると、これらのデータベースが自動的に作成されます。

監視データと他の種類のデータで 1 つの SQL Server インスタンスを共有することができます。一般には、通話詳細記録データベース (LcsCdr) と Quality of Experience データベース (QoEMetrics) で同じ SQL インスタンスを共有します。また、2 つの監視データベースを、アーカイブ データベース (LcsLog) として同じ SQL インスタンスに配置するのも一般的です。SQL Server インスタンスに関する実際の唯一の要件は、SQL Server のどのインスタンスについても、次の制限が設けられることです。

  - Lync Server 2013 バックエンドデータベースの1つのインスタンス。 (一般的な規則として、監視データベースを同一の SQL インスタンスまたは同じコンピューター上のバックエンドデータベースとの間で併置することはお勧めしません。 技術的には可能ですが、バックエンドデータベースに必要なディスク領域を使用して、監視データベースのリスクを実行します。

  - 通話詳細記録データベースは 1 インスタンス。

  - Quality of Experience データベースは 1 インスタンス。

  - アーカイブ データベースは 1 インスタンス。

つまり、同じ SQL Server の同じインスタンス内に、複数の LcsCdr データベースのインスタンスを作成することはできません。 LcsCdr データベースの複数のインスタンスが必要な場合は、SQL Server の複数のインスタンスを構成する必要があります。

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 での監視の展開](lync-server-2013-deploying-monitoring.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

