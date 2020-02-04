---
title: 移行のプロセス
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migration process
ms:assetid: b2bd9c76-2f4b-4d14-a5c4-157bbff75de0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205181(v=OCS.15)
ms:contentKeyID: 48185157
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2771a7a8b29cf410f9da5155e8f379bd7efe0e4e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41766098"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migration-process"></a>移行のプロセス

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-09-24_

Lync Server 2013 の推奨およびサポートされている移行手順は、並列移行の手順です。 このトピックでは、サイドバイサイド移行を使用する必要がある理由と、共存に関する情報も含まれている理由について説明します。

<div>

## <a name="side-by-side-migration"></a>サイドバイサイド移行

ほぼすべての移行では、並列移行パスを使用する必要があります。 サイドバイサイドの移行では、Office Communications Server 2007 R2 を実行している対応サーバーと共に、Lync Server 2013 と共に新しいサーバーを展開して、新しいサーバーに操作を転送します。 Office Communications Server 2007 R2 にロールバックする必要がある場合は、元のサーバーに戻す操作のみを行うことができます。 この状況では、アップグレードされたクライアントによってスケジュールされた新しい会議が機能しなくなり、クライアントもダウングレードされる必要があることに注意してください。

</div>

<div>

## <a name="coexistence-testing"></a>共存テスト

Office Communications Server 2007 R2 と並行して Lync Server 2013 を展開した後、トポロジは Lync Server 2013 と Office Communications Server 2007 R2 の共存テストの状態を表します。 この状態では、サービスが開始されていることを確認し、各サイトを管理し、クライアントが現在のユーザーと従来のユーザーと通信できるようにすることが重要です。 すべてのユーザーを移行する前に、展開の状態を理解し、各展開が正常に機能して動作していることを確認することが非常に重要です。 通常、[共存テスト] フェーズは、Lync Server 2013 のパイロットテストを通じて行われます。 従来のユーザーは、アプリケーションの互換性と機能が適切に動作するように、しばらくの間 Lync Server 2013 に移動されます。 パイロットテストの後、ユーザーとアプリケーションは Lync Server 2013 の運用バージョンに移動され、Office Communications Server 2007 R2 の従来のプールとアプリケーションは廃止されます。

</div>

</div>

<span> </span>

</div>

</div>

</div>

