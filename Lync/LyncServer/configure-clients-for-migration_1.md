---
title: 移行のためのクライアントの構成
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Configure clients for migration
ms:assetid: 8f17862b-d9d1-47f6-b248-51f4710f5030
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688130(v=OCS.15)
ms:contentKeyID: 49733729
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 399320fd840391b8d0483b3dc45b62c83311d91f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840082"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-clients-for-migration"></a>移行のためのクライアントの構成

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-11-21_

このトピックでは、Lync Server 2013 に移行する前に推奨されるクライアント展開の手順について説明します。 これらの構成変更は、Office Communications Server 2007 R2 で行う必要があります。 移行する前に、次の手順を実行することが非常に重要です。 詳細については、「 [Lync Server 2013 でのクライアントとデバイスの計画](lync-server-2013-planning-for-clients-and-devices.md)」を参照してください。

<div>

## <a name="to-configure-clients-prior-to-migration"></a>移行前にクライアントを構成するには

1.  最新の Office Communications Server 2007 R2 server、クライアント、およびデバイスの更新プログラム (ホットフィックス) を展開します。
    
      - [Office Communications Server 2007 R2 の更新プログラムを適用する](apply-office-communications-server-2007-r2-updates.md)
    
      - [Communicator 2007 R2 の累積的な更新プログラムパッケージについて](http://go.microsoft.com/fwlink/p/?linkid=335808)
    
      - [デバイスのソフトウェア更新プログラムを入手する](http://go.microsoft.com/fwlink/?linkid=335809)

2.  Office Communications Server 2007 R2 の場合、クライアントのバージョンフィルタリングを使用して、最新の更新プログラムがインストールされている Office Communications Server 2007 R2 クライアントだけにサインインを許可します。

3.  Office Communications Server 2007 R2 で、クライアントのバージョンフィルタリングを使用して、Lync Server 2013 クライアントからのサインインをブロックします。 次の表に記載されているバージョン[http://go.microsoft.com/fwlink/p/?linkId=202488](http://go.microsoft.com/fwlink/p/?linkid=202488)フィルターを追加するには、「**クライアントバージョンフィルターを構成**する」の手順に従ってください。 バージョンフィルターごとに、アクション**ブロック**を割り当てます。
    
    
    <table>
    <colgroup>
    <col style="width: 33%" />
    <col style="width: 33%" />
    <col style="width: 33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>クライアント</th>
    <th>ユーザーエージェントのヘッダー</th>
    <th>バージョン</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>Lync 2013</p></td>
    <td><p>OC</p></td>
    <td><p>15.**..*</p></td>
    </tr>
    <tr class="even">
    <td><p>Lync Web App</p></td>
    <td><p>CWA</p></td>
    <td><p>5.**..*</p></td>
    </tr>
    <tr class="odd">
    <td><p>Lync Phone Edition</p></td>
    <td><p>OCPhone</p></td>
    <td><p>4.**..*</p></td>
    </tr>
    </tbody>
    </table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

