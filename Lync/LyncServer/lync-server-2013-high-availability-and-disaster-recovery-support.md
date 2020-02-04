---
title: 'Lync Server 2013: 高可用性および障害復旧のサポート'
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
ms.openlocfilehash: b73f6605f2fff063858a0180d61a306f7dd2d746
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729987"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="high-availability-and-disaster-recovery-support-in-lync-server-2013"></a>Lync Server 2013 での高可用性および障害復旧のサポート

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-09-25_

Lync Server 2013 は、プールによるサーバーの冗長性による高可用性を実現します。 特定のサーバーの役割を実行するサーバーで障害が発生した場合は、プール内の同じ役割を実行する他のサーバーがそのサーバーの負荷を引き受けます。 同じことが、フロントエンド サーバー、エッジ サーバー、仲介サーバー、およびディレクターでも実行されます。 サーバーの役割の詳細については、「 [Lync server 2013 のサーバーの役割](lync-server-2013-server-roles.md)」を参照してください。

また、Lync Server 2013 は、プールのペアリングを有効にすることで、障害回復手段を提供します。 このトポロジを展開する場合、フロントエンドプールのペアを指定します。各プールは、別々のデータセンターにあり、各プールは別々の地理的領域に配置されています。 1つのプールまたはサイトがダウンした場合は、サービスの中断を最小限に抑えて、そのプールのユーザーを、ペア内の他のプールを使用するようにリダイレクトすることができます。

Lync Server 2013 では、バックエンドサーバーの高可用性もサポートされています。 これは、フロントエンドプール用に2つのバックエンドサーバーを展開し、バックエンドサーバーで実行されているすべての Lync データベースの同期 SQL Server ミラーリングを設定する、オプションのトポロジです。

プールのペアリングとバックエンドサーバーのミラーリングの詳細については、「 [Lync Server 2013 での高可用性と障害回復の計画](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)」を参照してください。

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

