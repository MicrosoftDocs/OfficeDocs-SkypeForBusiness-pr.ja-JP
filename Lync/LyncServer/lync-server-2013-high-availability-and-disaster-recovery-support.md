---
title: 'Lync Server 2013: 高可用性および障害復旧のサポート'
description: 'Lync Server 2013: 高可用性および障害復旧のサポート。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: High availability and disaster recovery support
ms:assetid: 47e77e85-c7c3-4ade-8db7-a34c71aeafd7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204866(v=OCS.15)
ms:contentKeyID: 48184053
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a8113c6b54cbb55e8149f8d6dd1b53ccbdc9436d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552793"
---
# <a name="high-availability-and-disaster-recovery-support-in-lync-server-2013"></a>Lync Server 2013 での高可用性および障害復旧のサポート

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-25_

Lync Server 2013 では、プールによるサーバー冗長性による高可用性が提供されます。 あるサーバーの役割を実行しているサーバーが失敗すると、プール内で同じサーバーの役割を実行している別のサーバーがそのサーバーの負荷を引き継ぎます。 これはフロントエンド サーバー、エッジ サーバー、仲介サーバー、およびディレクターに適用されます。 サーバーの役割の詳細については、「 [Lync server 2013 のサーバーの役割](lync-server-2013-server-roles.md)」を参照してください。

Lync Server 2013 では、プールのペアリングを有効にすることで、障害復旧の手段を提供します。 このトポロジを展開する場合は、フロントエンドプールのペアを指定し、各プールを別々のデータセンターに配置し、個別の地理的領域に配置します。 1つのプールまたはサイトに障害が発生した場合は、サービスの中断を最小限に抑えて、そのプールのユーザーがペアの他のプールを使用するようにリダイレクトすることができます。

Lync Server 2013 では、バックエンドサーバーの高可用性もサポートしています。 これは、フロントエンドプール用に2台のバックエンドサーバーを展開し、バックエンドサーバーで実行されているすべての Lync データベースに対して同期 SQL Server ミラーリングをセットアップする、オプションのトポロジです。

プールのペアリングとバックエンドサーバーのミラーリングの詳細については、「 [Lync Server 2013 での高可用性と障害復旧の計画](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)」を参照してください。

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 のサーバーの役割](lync-server-2013-server-roles.md)  
[Lync Server 2013 での高可用性および障害復旧の計画](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

