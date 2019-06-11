---
title: 移行のプロセス
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Migration process
ms:assetid: 13d71f4b-9d5e-4ea3-9e93-29fdad7ac68f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204696(v=OCS.15)
ms:contentKeyID: 48183474
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f48d486332bf03204d25aaadfc2ea351bcf581a7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848061"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migration-process"></a>移行のプロセス

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-09-17_

Lync Server 2013 の推奨およびサポートされる移行手順は、並行して移行されます。 このトピックでは、サイドバイサイド移行を使用する必要がある理由と、共存テストに関する情報も含まれている理由について説明します。

<div>

## <a name="side-by-side-migration"></a>サイドバイサイド移行

ほぼすべての移行では、並列移行パスを使用する必要があります。 サイドバイサイドの移行では、lync server 2010 を実行している対応サーバーと共に、Lync Server 2013 と共に新しいサーバーを展開して、新しいサーバーに操作を転送します。 Lync Server 2010 にロールバックすることが必要になった場合は、元のサーバーに戻す操作のみを行うことができます。 この状況では、アップグレードされたクライアントによってスケジュールされた新しい会議が機能しなくなり、クライアントもダウングレードされる必要があることに注意してください。

</div>

<div>

## <a name="coexistence-testing"></a>共存テスト

Lync server 2010 と同時に Lync Server 2013 を展開した後、展開は Lync Server 2013 および Lync Server 2010 の共存テストの状態を表します。 この状態では、サービスが開始されていること、各サイトが管理可能であること、クライアントが現在のユーザーと従来のユーザーと通信できることをテストして確認することが重要です。 すべてのユーザーを移行する前に、展開の状態を理解し、各展開が正常に機能して動作していることを確認することが非常に重要です。 通常、[共存テスト] フェーズは、Lync Server 2013 のパイロットテストを通じて行われます。 従来のユーザーは、アプリケーションの互換性と機能が適切に動作するように、しばらくの間 Lync Server 2013 に移動されます。 パイロットテストの後、ユーザーとアプリケーションは Lync Server 2013 の運用バージョンに移動され、Lync Server 2010 の従来のプールとアプリケーションは廃止されます。

</div>

</div>

<span> </span>

</div>

</div>

</div>

