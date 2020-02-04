---
title: 'Lync Server 2013: ファイル記憶域のサポート'
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
ms.openlocfilehash: 000f3357c8b30b83a2d2cecf74bdbec44d867d96
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743407"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="file-storage-support-in-lync-server-2013"></a>Lync Server 2013 のファイル記憶域のサポート

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-16_

Lync Server 2013 では、すべてのファイルストレージに同じファイルストアが使用されます。 ファイル記憶域のサポートには、次のものが含まれます。

  - 直接接続型記憶域 (DAS) またはストレージエリアネットワーク (SAN) (分散ファイルシステム (DFS) を含む)、またはファイルストア用の独立したディスク (RAID) の冗長アレイ上にあるファイル共有。 記憶域の要件の詳細については、「計画ドキュメントの[Lync server 2013 のディレクターのための](lync-server-2013-hardware-and-software-requirements-for-the-director.md)、lync server 2013 およびハードウェアとソフトウェアの要件」の「[フロントエンドサーバーの技術要件」、「インスタントメッセージング」](lync-server-2013-technical-requirements-for-front-end-servers-instant-messaging-and-presence.md) 、「プレゼンス」を参照してください。 Windows Server 2008 オペレーティングシステム向けの DFS の詳細については、Windows Server 2008 の DFS ステップバイステップガイドを[http://go.microsoft.com/fwlink/p/?linkId=202835](http://go.microsoft.com/fwlink/p/?linkid=202835)参照してください。

  - ファイル共有の共有クラスター。 共有クラスターを使用する場合は、Windows Server 2008 または Windows Server 2008 R2 を実行しているクラスターサーバーを使用する必要があります。 以前のバージョンの Windows を実行しているクラスターサーバーを使用すると、一部の機能が使用できなくなる可能性がある権限の問題が発生する場合があります。 クラスター管理者を使用して、ファイル共有を作成します。 クラスター管理者の使用について詳しくは、Microsoft サポート技術情報の記事284838「cluster.exe でサーバークラスターのファイル共有を作成する方法[http://go.microsoft.com/fwlink/p/?linkId=140899](http://go.microsoft.com/fwlink/p/?linkid=140899)」を参照してください。

</div>

<span> </span>

</div>

</div>

</div>

