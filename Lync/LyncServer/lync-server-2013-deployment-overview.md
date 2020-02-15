---
title: 'Lync Server 2013: 展開の概要'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment overview
ms:assetid: da67555e-f410-4c37-9996-d511f37da8d1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205305(v=OCS.15)
ms:contentKeyID: 48185555
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 65d5fd5de9a72002d6ee8bd58ef5367b96634b80
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038209"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-overview-for-lync-server-2013"></a>Lync Server 2013 の展開の概要

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-03-12_

Lync Server 2013 Enterprise Edition と Lync Server 2013 Standard Edition の主な違いは、Standard Edition は Enterprise Edition に含まれる高可用性機能をサポートしていないことです。 高可用性を実現するには、複数のフロントエンドサーバーをプールに展開し、SQL Server を実行しているサーバーをミラー化する必要があります。 Enterprise Edition では、スタンドアロンの仲介サーバーを併置するか、定義するかを選択できます。 監視サーバーとアーカイブサーバーは、SQL Server を実行しているスタンドアロンサーバーを使用できます。 または、フロントエンドサーバーおよびプールのデータベースサーバー上で実行されている SQL Server のインスタンスを持つことができます。

Lync Server 2013 Standard Edition を実行しているサーバーは、組織の主要展開から地理的に削除された小規模な組織とリモートの場所を対象としています。 障害が発生した場合にフェールオーバーに使用する2つの Standard Edition サーバーサーバーは、最大5000ユーザーをサポートできます。 Enterprise Edition のフロントエンドサーバーと同様に、Standard Edition サーバーをプールすることはできません。 また、Standard Edition が使用する SQL Server データベースは、SQL Server Express を実行する併置されたサーバーであり、Standard Edition サーバーのワークロードを処理するために設計されています。 これは、すべての役割が Standard Edition サーバー上に存在する必要があるということではありません。 スタンドアロンの仲介サーバーとエッジサーバーを使用できます。 中央管理ストアの SQL Server データベース、および Lync Server 2013 のための目的は、SQL Server を実行しているサーバーに併置された Standard Edition サーバー上に存在する必要があります。 監視サーバーとアーカイブサーバーは、スタンドアロンサーバーと SQL Server データベースを使用します。

</div>

<span> </span>

</div>

</div>

</div>

