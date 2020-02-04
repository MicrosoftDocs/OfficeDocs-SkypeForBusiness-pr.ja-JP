---
title: 'Lync Server 2013: 通話受付制御の展開チェックリスト'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call admission control deployment checklist
ms:assetid: d56a525f-3da5-4ac0-a311-0c5efd98c9df
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398928(v=OCS.15)
ms:contentKeyID: 48185525
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e768cdd11d92b3aab5ce849f91cc1a422f119407
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741757"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-admission-control-deployment-checklist-for-lync-server-2013"></a>Lync Server 2013 の通話受付制御の展開チェックリスト

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-22_

次のチェックリストを使用して、通話受付制御 (CAC) を展開するために必要なすべての構成タスクを完了したことを確認します。

  - 1つ以上のエッジサーバーが展開されている場合、各外部インターフェイス IP アドレスは、ネットワーク構成設定のサブネットリストに追加する必要があります。この場合、ビットマスクは32になります。 音声ビデオ エッジ サービスが展開されている地理的な場所のネットワーク サイト ID にこのサブネット (IP アドレス) を関連付ける必要もあります。
    
    <div>
    

    > [!NOTE]  
    > CAC を実装するためにエッジサーバーは必要ありません。

    
    </div>

  - Lync Server コントロールパネルを使用するか、または「 [Lync server 2013 で通話受付制御を有効にする](lync-server-2013-enable-call-admission-control.md)」で指定されているコマンドレットを実行して、CAC が有効になっていることを確認します。

  - すべてのセントラル サイトで CAC が有効化されていることを確認します。 これは、トポロジビルダーで行うことができます。 公開時に警告が生成された場合には、警告を*無視しないでください*。

  - エンタープライズ ネットワークで管理されているすべてのサブネットがネットワーク構成設定で構成されていることを確認します。 また、「 [Lync Server 2013 でのネットワークサイトへのサブネットの関連付け](lync-server-2013-associate-a-subnet-with-a-network-site.md)」で説明されているように、すべてのサブネットをネットワークサイトに関連付けることが重要です。

  - すべてのフロントエンド サーバー、存続可能ブランチ アプライアンス (SBA)、音声ビデオ会議サーバー (別プールの場合)、および仲介サーバーのサブネットまたは IP アドレスがネットワーク構成設定で構成されていることを確認します。

</div>

<span> </span>

</div>

</div>

</div>

