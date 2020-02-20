---
title: 'Lync Server 2013: プライマリ管理サーバーの構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring the primary management server
ms:assetid: 44e2e9a8-c130-4c66-9871-80b1ff11b27c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204844(v=OCS.15)
ms:contentKeyID: 48183986
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 68fc10ba0457b0ad29f6f3850c1d7056d27fd24d
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154219"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-the-primary-management-server-in-lync-server-2013"></a>Lync Server 2013 でのプライマリ管理サーバーの構成

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2014-03-19_

Microsoft Lync Server 2013 に含まれる新しい正常性監視機能を十分に活用するために、管理者はまず、プライマリ管理サーバーとして動作するコンピューターを指定する必要があります。そのコンピューターで、System Center Operations Manager 2007 R2 または System Center Operations Manager 2012 をインストールする必要があります。 また、Operations Manager のバックエンドデータベースとして機能するために、サポートされているバージョンの SQL Server をインストールする必要があります。 System Center Operations Manager 2012 を使用している場合は、次のいずれかのバージョンの SQL Server をバックエンドデータベースとして使用できます。

  - SQL Server 2008 R2 Service Pack 1

  - SQL Server 2008 R2 Service Pack 2

System Center Operations Manager 2007 R2 を使用している場合は、SQL Server 2005 Service Pack 4 または SQL Server 2008 Service Pack 3 をインストールすることをお勧めします。 また、SQL Server 2008 R2 を System Center Operations Manager 2007 R2 のバックエンドデータベースとして使用することもできます。 SQL Server 2008 R2 を System Center Operations Manager 2007 R2 と連携するように構成する方法の詳細については、このドキュメントの「付録1」を参照してください。

System Center Operations Manager 2012 または System Center Operations manager 2007 R2 をインストールする場合は、次のような製品のすべてのコンポーネントをインストールする必要があります。

  - オペレーション データベース

  - サーバー

  - コンソール

  - Windows PowerShell コマンドレット

  - Web コンソール

  - Reporting

  - データ ウェアハウス

これらのコンポーネントとそのインストールの詳細については、このドキュメントでは説明しません。 System Center Operations Manager 2007 R2 の詳細については、Operations Manager 2007 R2 の<https://go.microsoft.com/fwlink/p/?linkid=257526>ドキュメントと、System Center operations manager 2012 の<https://go.microsoft.com/fwlink/p/?linkid=257527>マニュアルを参照してください。 SQL Server 2005 または SQL Server 2008 Service Pack 1 をバックエンドデータベースとして使用する場合は、これらの手順に従う必要があります。

System Center Operations Manager 2012 を使用している場合は、SQL Server 2012 をバックエンドデータベースとして使用できます。 SQL Server 2012 の詳細については、「Books Online for SQL [https://go.microsoft.com/fwlink/p/?LinkId=257528](https://go.microsoft.com/fwlink/p/?linkid=257528)server 2012」を参照してください。

Lync Server の展開ごとに1つのプライマリ管理サーバーしか使用できないことに注意してください。 また、System Center Operations Manager 2012 または System Center Operations Manager 2007 R2 のどちらかを使用できますが、2つのアプリケーションを同時に実行することはできません。どちらか一方を選択する必要があります。 たとえば、System Center Operations Manager 2012 を実行している場合は、すべてのシステムセンターエージェントも System Center Operations Manager 2012 を実行している必要があります。 System Center Operations Manager 2012 と、System Center Operations Manager 2007 R2 を実行している他のエージェントを実行しているエージェントはありません。

</div>

<span> </span>

</div>

</div>

</div>

