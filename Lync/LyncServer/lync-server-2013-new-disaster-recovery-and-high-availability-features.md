---
title: 'Lync Server 2013: 新しい障害復旧および高可用性機能'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New disaster recovery and high availability features
ms:assetid: 4fa7cd0f-784b-4d3f-b839-432c2ecaf7c1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204892(v=OCS.15)
ms:contentKeyID: 48184130
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 33a9039c65d059042d9eb93c9d5437a00ebff266
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48512564"
---
# <a name="new-disaster-recovery-and-high-availability-features-in-lync-server-2013"></a>Lync Server 2013 の新しい障害復旧および高可用性機能

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-20_

Lync Server 2010 の場合と同様に、Lync Server 2013 の主な高可用性 (HA) スキームは、プーリングによるサーバーの冗長性に基づいています。 あるサーバーの役割を実行しているサーバーが失敗すると、プール内で同じサーバーの役割を実行している別のサーバーがそのサーバーの負荷を引き継ぎます。 これはフロントエンド サーバー、エッジ サーバー、仲介サーバー、およびディレクターに適用されます。

Lync Server 2013 は、2つのデータセンターにあるフロントエンドプールをペアにすることによって、新しい障害復旧手段を追加します。 ペアになっているプールのいずれかがダウンすると、管理者はそのプールのユーザーをペアの他のプールにフェールオーバーして、サービスの継続を提供できます。 この機能には、記憶域ネットワークや共有ディスクなど、高価なネットワークやハードウェアソリューションは必要ありません。

Lync Server 2013 では、バックエンドサーバーの高可用性も追加されます。 これは、フロントエンドプール用に2台のバックエンドサーバーを展開し、バックエンドサーバーで実行されているすべての Lync データベースの同期 SQL ミラーリングをセットアップするオプションのトポロジです。 ミラーの監視を展開するかどうかを選択できます。

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 での高可用性および障害復旧の計画](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

