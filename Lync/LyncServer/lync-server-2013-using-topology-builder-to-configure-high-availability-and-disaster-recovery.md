---
title: トポロジ ビルダーを使用して高可用性と障害回復を構成する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using Topology Builder to configure high availability and disaster recovery
ms:assetid: abc1a25d-1f5e-46ef-91d2-0144fc847206
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205172(v=OCS.15)
ms:contentKeyID: 48185113
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 73bcd2c2892e4e121512ae852d5920d600af91ff
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743827"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-topology-builder-to-configure-high-availability-and-disaster-recovery-in-lync-server-2013"></a>Lync Server 2013 でトポロジ ビルダーを使用して高可用性と障害回復を構成する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-06_

[トポロジビルダー] で次の手順を実行して、常設チャットサーバーの高可用性と障害回復を構成します。

1.  ミラーデータベースとログ配布のセカンダリデータベース SQL Server ストアを追加します。

2.  常設チャットサーバーサービスのプロパティを編集するには、次の操作を行います。
    
    1.  プライマリ データベースのミラーリングを有効にします。
    
    2.  プライマリミラー SQL Server ストアを追加します。
    
    3.  SQL Server のログ配布データベースを有効にします。
    
    4.  SQL Server ログ配布のセカンダリ SQL Server ストアを追加します。
    
    5.  セカンダリデータベースの SQL Server ストアミラーを追加します。
    
    6.  トポロジを公開します。

</div>

<span> </span>

</div>

</div>

</div>

