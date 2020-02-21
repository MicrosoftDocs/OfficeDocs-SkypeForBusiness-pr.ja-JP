---
title: 移行のプロセス
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migration process
ms:assetid: 13d71f4b-9d5e-4ea3-9e93-29fdad7ac68f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204696(v=OCS.15)
ms:contentKeyID: 48183474
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4d941b97080bf4ffd0efc87549c5a4fb80c1275c
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42209813"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migration-process"></a>移行のプロセス

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-17_

Lync Server 2013 の推奨およびサポートされる移行手順は、並行して移行されます。 このトピックでは、サイド バイ サイド移行を使用する理由について説明し、共存のテストに関する情報も示します。

<div>

## <a name="side-by-side-migration"></a>サイド バイ サイド移行

ほとんどすべての移行では、サイド バイ サイド移行パスの使用をお勧めします。 Side-by-side 移行では、Lync Server 2010 を実行している対応するサーバーと共に Lync Server 2013 を使用して新しいサーバーを展開し、次にその操作を新しいサーバーに転送します。 Lync Server 2010 にロールバックする必要が生じた場合は、元のサーバーに戻す操作のみを実行する必要があります。 ただし、この状況では、アップグレードされたクライアントによって新しい会議がスケジュールされていた場合、それらの会議がすべて機能しなくなるのでクライアントのダウングレードも必要になります。

</div>

<div>

## <a name="coexistence-testing"></a>共存のテスト

Lync server 2013 2010 と共に Lync Server を展開した後、展開は Lync Server 2013 と Lync Server 2010 の共存テスト状態を表します。 この状態のときに、サービスが開始されていること、各サイトを管理できること、クライアントが現在および従来のユーザーと通信できることをテストして確認することが重要です。 すべてのユーザーを移行する前に、各展開の状態を把握し、各展開が適切に機能および動作することを確認する必要があります。 通常、Lync Server 2013 のパイロットテストにおいて、共存のテスト段階が存在します。 従来のユーザーは、アプリケーションの互換性と機能が適切に動作するように、長期間 Lync Server 2013 に移動されます。 パイロットテストの後、ユーザーとアプリケーションは Lync Server 2013 の運用バージョンに移行され、Lync Server 2010 の従来のプールとアプリケーションは廃止されました。

</div>

</div>

<span> </span>

</div>

</div>

</div>

