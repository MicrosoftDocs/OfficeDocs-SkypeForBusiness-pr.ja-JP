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
ms.openlocfilehash: 1cc0620b2de14c56a6886a70cd7b977046828786
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42148726"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migration-process"></a>移行のプロセス

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-24_

Lync Server 2013 の推奨およびサポートされている移行手順は、side-by-side 移行の手順です。 ここでは、サイド バイ サイド移行の手順を使用する理由、および共存に関する情報についても説明します。

<div>

## <a name="side-by-side-migration"></a>サイド バイ サイド移行

ほとんどすべての移行では、サイド バイ サイド移行パスの使用をお勧めします。 Side-by-side 移行では、Office Communications Server 2007 R2 を実行している対応するサーバーと共に Lync Server 2013 を使用して新しいサーバーを展開し、新しいサーバーに操作を転送します。 Office Communications Server 2007 R2 にロールバックする必要が生じた場合は、元のサーバーに戻す操作のみを実行する必要があります。 ただし、この状況では、アップグレードされたクライアントによって新しい会議がスケジュールされていた場合、それらの会議がすべて機能しなくなるのでクライアントのダウングレードも必要になります。

</div>

<div>

## <a name="coexistence-testing"></a>共存のテスト

Lync Server 2013 を Office Communications Server 2007 R2 と並行して展開した後、このトポロジは Lync Server 2013 および Office Communications Server 2007 R2 の共存テストの状態を表します。 この状態で、サービスが開始されること、各サイトを管理できること、クライアントが現在のユーザーおよび従来のユーザーと通信できることをテストして確認することが重要です。 すべてのユーザーの移行の前に、各展開の状態を理解し、各展開が正常に機能および動作することを確認することが非常に重要です。 通常、Lync Server 2013 のパイロットテストにおいて、共存のテスト段階が存在します。 従来のユーザーは、アプリケーションの互換性と機能が適切に動作するように、長期間 Lync Server 2013 に移動されます。 パイロットテストの後、ユーザーとアプリケーションが Lync Server 2013 の運用バージョンに移行され、Office Communications Server 2007 R2 の従来のプールとアプリケーションが廃止されました。

</div>

</div>

<span> </span>

</div>

</div>

</div>

