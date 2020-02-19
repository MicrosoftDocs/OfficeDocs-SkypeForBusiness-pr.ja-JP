---
title: 移行用にクライアントを構成する
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure clients for migration
ms:assetid: 8f17862b-d9d1-47f6-b248-51f4710f5030
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688130(v=OCS.15)
ms:contentKeyID: 49733729
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 542ee4d581d4df26a528a14fda5de792c2a2ad09
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136123"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-clients-for-migration"></a>移行用にクライアントを構成する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-11-21_

このトピックでは、Lync Server 2013 に移行する前に実行する必要のある推奨クライアント展開手順について説明します。 これらの構成の変更は、Office Communications Server 2007 R2 で行う必要があります。 移行の前にこれらの手順を実行することが非常に重要です。 詳細については、「 [Lync Server 2013 でのクライアントとデバイスの計画](lync-server-2013-planning-for-clients-and-devices.md)」を参照してください。

<div>

## <a name="to-configure-clients-prior-to-migration"></a>移行の前にクライアントを構成するには

1.  最新の Office Communications Server 2007 R2 サーバー、クライアント、およびデバイスの更新プログラム (ホットフィックス) を展開します。
    
      - [Office Communications Server 2007 R2 の更新プログラムを適用する](apply-office-communications-server-2007-r2-updates.md)
    
      - [Communicator 2007 R2 の累積的な更新プログラムパッケージの説明](https://go.microsoft.com/fwlink/p/?linkid=335808)
    
      - [デバイスのソフトウェア更新プログラムの取得](https://go.microsoft.com/fwlink/?linkid=335809)

2.  Office Communications Server 2007 R2 では、クライアントバージョンフィルターを使用して、Office Communications Server 2007 R2 クライアントのみに最新の更新プログラムをインストールしてサインインできるようにします。

3.  Office Communications Server 2007 R2 では、クライアントバージョンフィルタリングを使用して Lync Server 2013 クライアントのサインインをブロックします。 次の表に記載されているバージョン[https://go.microsoft.com/fwlink/p/?linkId=202488](https://go.microsoft.com/fwlink/p/?linkid=202488)フィルターを追加するには、「**クライアントバージョンフィルター**をで構成する」で説明されている手順に従います。 各バージョン フィルターで、[**ブロック**] のアクションを割り当てます。
    
    
    <table>
    <colgroup>
    <col style="width: 33%" />
    <col style="width: 33%" />
    <col style="width: 33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>クライアント</th>
    <th>ユーザー エージェントのヘッダー</th>
    <th>バージョン</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>Lync 2013</p></td>
    <td><p>OC</p></td>
    <td><p>15.*..**</p></td>
    </tr>
    <tr class="even">
    <td><p>Lync Web App</p></td>
    <td><p>NM-CWA-NO-VERSION</p></td>
    <td><p>5.*..**</p></td>
    </tr>
    <tr class="odd">
    <td><p>Lync Phone Edition</p></td>
    <td><p>OCPhone</p></td>
    <td><p>4.*..**</p></td>
    </tr>
    </tbody>
    </table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

