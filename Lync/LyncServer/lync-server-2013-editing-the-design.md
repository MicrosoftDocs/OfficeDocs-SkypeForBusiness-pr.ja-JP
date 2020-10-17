---
title: 'Lync Server 2013: 設計の編集'
description: 'Lync Server 2013: デザインの編集。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Editing the design
ms:assetid: 08f639ba-0e5f-4ae7-9191-c3d96c25b169
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558608(v=OCS.15)
ms:contentKeyID: 51541445
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 20462c1c1813551159e8eeb3b255bd9069e3cce1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48570623"
---
# <a name="editing-the-design-in-lync-server-2013"></a>Lync Server 2013 での設計の編集

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-21_

最初のインタビューの質問を完了したら、サイトの完全修飾ドメイン名 (FQDN) と IP アドレスを編集できます。 これを行うには、**[グローバル トポロジ]** ページで、編集するサイトをダブルクリックします。

計画ツールでは、選択したサイトのサイトトポロジが表示されます。 サイト ページの下部には、次の 4 つのタブがあります。

![計画ツールサイトトポロジ](images/Gg558608.e6189c20-360a-42bd-ba90-11bdb5b7551b(OCS.15).jpg "計画ツールサイトトポロジ")

  - サイト トポロジ – 現在表示されているページで、推奨されるビジュアルなトポロジの概要が含まれます。

  - エッジネットワーク図–エッジネットワークの図のページでは、計画ツールでの作業の大部分がデザイナーによって実行されます。 図は、推奨される Lync Server 2013 トポロジのネットワーク構成を表示します。これには、サーバー、プール、およびハードウェアおよびドメインネームシステム (DNS) ロードバランサーの IP アドレスと Fqdn の編集可能なエントリが含まれています。

  - エッジ管理レポート – 次の合計 4 つのレポートが含まれます。
    
    ![エッジ管理レポートページ](images/Gg558608.0019cc5e-af39-4cb9-82ce-58f6388242ff(OCS.15).jpg "エッジ管理レポートページ")  
    
      - 概要レポート – エッジ ネットワーク構成の設定に関する一般的なレポート。 [ **エッジネットワーク図** ] ページの値を、実際の展開で使用されるトポロジの TCP/IP および FQDN 値に編集すると、それらのアドレスと名前がここに表示されます。 それ以外の場合は、既定のテキストが表示されます。
    
      - 証明書レポート – トポロジで必要な証明書のサブジェクト名とサブジェクトの別名が表示されます。
    
      - ファイアウォール レポート – インフラストラクチャで周辺ファイアウォールを構成するために必要な情報が表示されます。 これには、IP アドレス (既定または編集された値)、サーバーの役割、送信元の IP アドレスとポート、送信先 IP とポート、トランスポートプロトコル、アプリケーションプロトコル、関連メモが含まれます。
    
      - DNS レポート– dns レポートには、作成する必要がある DNS エントリの関連情報が一覧表示されます。 正しい動作に必要なレコードの種類、FQDN、IP アドレス、およびコメントが含まれています。

  - サイトの概要: サイトの概要は、最初のインタビューの質問に回答するか、または **設計サイト**の値を入力することによって、選択した選択の概要を示します。 容量情報も記載されています。
    
    <div>
    

    > [!NOTE]  
    > サイトの概要ページの情報は、設計ごとにカスタマイズされるため、ここで説明しているすべてのセクションや情報が含まれない場合があります。

    
    </div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 でのネットワーク構成ダイアグラムの編集](lync-server-2013-editing-the-network-configuration-diagram.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

