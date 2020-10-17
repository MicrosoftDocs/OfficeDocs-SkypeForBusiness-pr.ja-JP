---
title: バックエンド サーバー上の SQL Server インスタンスとデータベースの削除
description: バックエンドサーバー上の SQL Server インスタンスとデータベースを削除します。
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Remove SQL Server instances and databases on the Back End Server
ms:assetid: 32457df9-7dd9-4fca-9362-ea4de26b0296
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688016(v=OCS.15)
ms:contentKeyID: 49733606
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c87426a3496e6def2ad65775f5dadb1a0141ae3f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48551283"
---
# <a name="remove-sql-server-instances-and-databases-on-the-back-end-server"></a>バックエンド サーバー上の SQL Server インスタンスとデータベースの削除

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-19_

Microsoft SQL Server データベースとインスタンスは、そのサーバーに依存している Lync Server 2010 を実行しているサーバーを削除した後、または別のデータベースを使用するために Lync Server 2010 を実行しているサーバーを再構成した後に削除します。 このトピックの手順を実行する必要があるのは、現在の SQL Server を廃止する場合、または、データベースが使用できなくなった、または利用できないようにするために、Lync Server 2010 を実行している現在のサーバーを再構成する場合です。

アーカイブサーバーまたは監視サーバーのデータベースまたはインスタンスを削除するには、最初にサーバーの役割を削除する必要があります。 同様に、フロントエンドプールのインスタンスまたはデータベースを削除するには、最初に依存サーバーの役割を削除または再構成する必要があります。 これらの手順では、サーバーの併置されたデータベースと個別のインスタンスは区別されません。 データベースの併置によって手順が影響を受けることはありません。

<div>

## <a name="in-this-section"></a>このセクションの内容

  - [フロントエンド プール用の SQL Server データベースの削除](remove-the-sql-server-database-for-a-front-end-pool.md)

  - [監視サーバー用の SQL Server データベースの削除](remove-the-sql-server-database-for-a-monitoring-server.md)

  - [アーカイブ サーバー用の SQL Server データベースの削除](remove-the-sql-server-database-for-an-archiving-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

