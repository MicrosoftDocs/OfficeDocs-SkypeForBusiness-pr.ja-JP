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
ms.openlocfilehash: 3d237e0ba3f94f81ce3988e2ce8994d49f97087d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762665"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-overview-for-lync-server-2013"></a>Lync Server 2013 の展開の概要

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-03-12_

Lync Server 2013 Enterprise Edition と Lync Server 2013 Standard Edition の主な違いは、Standard Edition は Enterprise Edition に含まれる高可用性機能をサポートしていないことです。 高可用性を実現するには、複数のフロントエンドサーバーをプールに展開する必要があります。その後、SQL Server を実行しているサーバーをミラー化することができます。 Enterprise Edition では、スタンドアロンの仲介サーバーを選ぶか、定義することができます。 監視サーバーとアーカイブサーバーは、SQL Server を実行しているスタンドアロンサーバーを使用できます。 または、フロントエンドサーバーとプール用にデータベースサーバー上で実行されている SQL Server のインスタンスを持つことができます。

Lync Server 2013 Standard Edition を実行しているサーバーは、組織の主要展開から地理的に削除される小規模の組織およびリモートの場所を対象としています。 障害が発生した場合のフェイルオーバーのために、2つの標準的なエディションのサーバーサーバーが、最大5000ユーザーをサポートします。 Enterprise Edition では、フロントエンドサーバーと同じように Standard Edition サーバーをプールすることはできません。 また、Standard Edition で使用される SQL Server データベースは、Standard Edition server のワークロードを処理するように設計された、SQL Server Express を実行している併置されたサーバーです。 これは、すべての役割が標準エディションのサーバーに存在する必要があるということではありません。 スタンドアロンの仲介サーバーとエッジサーバーを使用できます。 中央管理ストアの SQL Server データベースおよび Lync Server 2013 の目的には、SQL Server を実行しているサーバーと連携している Standard Edition サーバー上に存在している必要があります。 監視サーバーとアーカイブサーバーでは、スタンドアロンサーバーと SQL Server データベースを使用しています。

</div>

<span> </span>

</div>

</div>

</div>

