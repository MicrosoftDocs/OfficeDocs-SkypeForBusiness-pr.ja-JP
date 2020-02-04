---
title: 'Lync Server 2013: 設計の編集'
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
ms.openlocfilehash: dfce3bc4242140364005a9a981282ecb90a42d3b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739457"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="editing-the-design-in-lync-server-2013"></a>Lync Server 2013 での設計の編集

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-02-21_

最初のインタビューによる質問を完了すると、サイトの完全修飾ドメイン名 (FQDN) と IP アドレスを編集できます。これを行うには、[**グローバル トポロジ**] ページで、編集するサイトをダブルクリックします。

計画ツールには、選択したサイトのサイトトポロジが表示されます。 サイト ページの下部には、次の 4 つのタブがあります。

![計画ツール、サイト トポロジ](images/Gg558608.e6189c20-360a-42bd-ba90-11bdb5b7551b(OCS.15).jpg "計画ツール、サイト トポロジ")

  - サイト トポロジ - 現在表示されているページで、推奨されるビジュアルなトポロジの概要が含まれます。

  - エッジネットワーク図– [Edge ネットワークダイアグラム] ページでは、計画ツールのほとんどの作業をデザイナーが行います。 この図は、推奨される Lync Server 2013 トポロジのネットワーク構成を示しています。これには、サーバーの IP アドレスと Fqdn 用の編集可能なエントリ、およびハードウェアとドメインネームシステム (DNS) ロードバランサーの両方が含まれています。

  - エッジ管理レポート - 次の合計 4 つのレポートが含まれます。
    
    ![[エッジ管理レポート] ページ](images/Gg558608.0019cc5e-af39-4cb9-82ce-58f6388242ff(OCS.15).jpg "[エッジ管理レポート] ページ")  
    
      - 概要レポート - エッジ ネットワーク構成の設定に関する一般的なレポート。[  **エッジ ネットワーク図  **] ページの値を、実際の展開で使用する、トポロジの TCP/IP および FQDN の値に編集する場合、それらのアドレスと名前がここに表示されます。それ以外の場合、既定のテキストが表示されます。
    
      - 証明書レポート - トポロジで必要な証明書のサブジェクト名とサブジェクトの別名が表示されます。
    
      - ファイアウォール レポート - インフラストラクチャに周辺ファイアウォールを構成するために必要な情報が表示されます。IP アドレス (既定値または編集された値)、サーバーの役割、送信元 IP と送信元ポート、宛先 IP と宛先ポート、トランスポート プロトコル、アプリケーション プロトコル、および関連する注記が表示されます。
    
      - DNS レポート - 作成する必要がある DNS エントリの関連情報が表示されます。正しい動作に必要なレコードの種類、FQDN、IP アドレス、およびコメントが含まれています。

  - サイトの概要 - 最初のインタビューの質問への回答または [  **サイトの設計  **] での値の入力による選択肢の概要が表示されます。処理能力に関する情報も表示されます。
    
    <div>
    

    > [!NOTE]  
    > サイトの概要ページの情報は、設計ごとにカスタマイズされるため、ここで説明しているすべてのセクションや情報が含まれない場合があります。

    
    </div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 でのネットワーク構成図の編集](lync-server-2013-editing-the-network-configuration-diagram.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

