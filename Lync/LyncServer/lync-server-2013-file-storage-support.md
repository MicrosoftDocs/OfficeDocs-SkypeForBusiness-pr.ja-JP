---
title: Lync Server 2013 ファイル記憶域のサポート
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: File storage support
ms:assetid: ed66430d-3c19-4267-938c-956a51005073
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399073(v=OCS.15)
ms:contentKeyID: 48185743
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1cc2250020b7456515f06bcb308ca4cea4430a56
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153689"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="file-storage-support-in-lync-server-2013"></a>Lync Server 2013 でのファイル記憶域のサポート

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-16_

Lync Server 2013 は、すべてのファイルストレージに対して同じファイルストアを使用します。 ファイル記憶域のサポートには次のものが含まれます。

  - 直接接続ストレージ (DAS) または記憶域エリアネットワーク (SAN) (分散ファイルシステム (DFS) を含む)、およびファイルストア用の独立したディスク (RAID) の冗長アレイ上にあるファイル共有。 ストレージ要件の詳細については、「計画」のドキュメントの「 [lync server 2013 でのフロントエンドサーバー、インスタントメッセージング、およびプレゼンスの技術要件](lync-server-2013-technical-requirements-for-front-end-servers-instant-messaging-and-presence.md)」および「 [lync Server 2013 のディレクターのハードウェアおよびソフトウェア要件](lync-server-2013-hardware-and-software-requirements-for-the-director.md)」を参照してください。 Windows Server 2008 オペレーティングシステムの DFS の詳細については、「Windows Server 2008 の DFS のステップバイステップガイド[https://go.microsoft.com/fwlink/p/?linkId=202835](https://go.microsoft.com/fwlink/p/?linkid=202835)」を参照してください。

  - ファイル共有の共有クラスター。 共有クラスターを使用する場合は、Windows Server 2008 または Windows Server 2008 R2 を実行しているクラスターサーバーを使用する必要があります。 以前のバージョンの Windows を実行しているクラスターサーバーを使用すると、一部の機能が使用できなくなる可能性があるアクセス許可の問題が発生することがあります。 ファイル共有を作成するには、クラスター アドミニストレーターを使用します。 クラスター管理者の使用の詳細については、Microsoft サポート技術情報の記事284838「cluster.exe を使用してサーバークラスターのファイル共有[https://go.microsoft.com/fwlink/p/?linkId=140899](https://go.microsoft.com/fwlink/p/?linkid=140899)を作成する方法」を参照してください。

</div>

<span> </span>

</div>

</div>

</div>

