---
title: トポロジビルダーを使用して高可用性と障害復旧を構成する
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
ms.openlocfilehash: fc0f47bf8e0a0aec5d2a2374decd79ce2bae77f2
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007466"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-topology-builder-to-configure-high-availability-and-disaster-recovery-in-lync-server-2013"></a>トポロジビルダーを使用して Lync Server 2013 での高可用性および障害復旧を構成する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-06_

[トポロジビルダー] で次の手順を実行して、常設チャットサーバーの高可用性および障害復旧を構成します。

1.  ミラーデータベースとログ配布セカンダリデータベース SQL Server ストアを追加します。

2.  常設チャットサーバーサービスのプロパティを次のように編集します。
    
    1.  プライマリ データベースのミラーリングを有効にします。
    
    2.  プライマリミラー SQL Server ストアを追加します。
    
    3.  SQL Server ログ配布データベースを有効にします。
    
    4.  SQL Server ログ配布のセカンダリ SQL Server ストアを追加します。
    
    5.  セカンダリデータベースの SQL Server ストアミラーを追加します。
    
    6.  トポロジを公開します。

</div>

<span> </span>

</div>

</div>

</div>

