---
title: 'Lync Server 2013: 通話受付管理の展開チェックリスト'
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
ms.openlocfilehash: fd1de11f9d169babc8a4367f429d9d99559d6aa6
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42187060"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="call-admission-control-deployment-checklist-for-lync-server-2013"></a>Lync Server 2013 の通話受付管理の展開チェックリスト

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-22_

次のチェック リストを使用して、通話受付管理サービス (CAC) を展開するために必要なすべての構成タスクを完了したことを確認してください。

  - 1 つまたは複数のエッジ サーバーが展開されている場合には、32 ビット マスクのすべての外部インターフェイス IP アドレスがネットワーク構成設定のサブネット リストに追加されている必要があります。音声ビデオ エッジ サービスが展開されている地理的な場所のネットワーク サイト ID にこのサブネット (IP アドレス) を関連付ける必要もあります。
    
    <div>
    

    > [!NOTE]  
    > エッジ サーバーは CAC を実装する必要はありません。

    
    </div>

  - Lync Server コントロールパネルを使用するか、または「 [Lync server 2013 で通話受付管理を有効にする](lync-server-2013-enable-call-admission-control.md)」で指定されているコマンドレットを実行して、CAC が有効になっていることを確認します。

  - すべてのセントラル サイトで CAC が有効化されていることを確認します。 これはトポロジビルダーを使用して行うことができます。 公開時に警告が生成された場合には、警告を無視しないでください。

  - エンタープライズ ネットワークで管理されているすべてのサブネットがネットワーク構成設定で構成されていることを確認します。 また、「 [Lync Server 2013 でのネットワークサイトへのサブネットの関連付け](lync-server-2013-associate-a-subnet-with-a-network-site.md)」の説明に従って、すべてのサブネットがネットワークサイトに関連付けられている必要があります。

  - すべてのフロントエンド サーバー、存続可能ブランチ アプライアンス (SBA)、音声ビデオ会議サーバー (別プールの場合)、および仲介サーバーのサブネットまたは IP アドレスがネットワーク構成設定で構成されていることを確認します。

</div>

<span> </span>

</div>

</div>

</div>

