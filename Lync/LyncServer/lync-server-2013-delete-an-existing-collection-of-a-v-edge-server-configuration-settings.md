---
title: 既存の A/V Edge サーバー構成設定のコレクションを削除する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete an existing collection of A/V Edge Server configuration settings
ms:assetid: 668d3613-e464-4b68-967a-cfff90b9ce4b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688077(v=OCS.15)
ms:contentKeyID: 49733673
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7cc085cd6ac39c4712647795c5baf06eaa68f77a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737547"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-an-existing-collection-of-av-edge-server-configuration-settings-in-lync-server-2013"></a>Lync Server 2013 での既存の A/V エッジサーバー構成の設定を削除する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-11-01_

A/V Edge サービスは、内部ユーザー (組織のネットワークにログオンしているユーザー) が、外部ユーザー (組織のネットワークにログオンしていないユーザー) とオーディオやビデオを共有できるようにするための手段を提供します。 A/V edge サービスは、主に、A/V Edge 構成設定を使用して管理されます。これは、サイトスコープまたはサービスの範囲で構成できます (つまり、個々の A/V Edge サーバー用に構成できます)。

Lync Server をインストールすると、A/V Edge のグローバルコレクションが設定されます。 このグローバルコレクションは削除できません。 ただし、Windows PowerShell と CsAVEdgeConfiguration コマンドレットを使用して、グローバルコレクションを "リセット" することができます。つまり、グローバルコレクションのすべてのプロパティ値が既定値にリセットされるということです。 たとえば、MaxTokenLifetime プロパティを16時間として設定した場合、そのプロパティは既定値の8時間にリセットされます。

ただし、サイトスコープまたはサービスのスコープで作成したカスタム設定コレクションは、CsAVEdgeConfiguration コマンドレットを使用して削除できます。 サイトの設定を削除すると、そのサイトの A/V エッジサーバーはグローバル設定によって管理されます。 サービス範囲の設定を削除すると、そのサーバーはそのサイトの設定 (存在する場合)、またはサイトの設定がない場合はグローバル設定によって管理されます。

詳細については、 [CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg398786(v=OCS.15))コマンドレットのヘルプトピックを参照してください。

<div>

## <a name="to-reset-the-global-collection"></a>グローバルコレクションをリセットするには

  - 次のコマンドを実行すると、A/V Edge の構成設定のグローバルコレクションがリセットされます。
    
        Remove-CsAVEdgeConfiguration -Identity "global"

</div>

<div>

## <a name="to-remove-a-collection-from-the-site-scope"></a>サイトのスコープからコレクションを削除するには

  - このコマンドは、Redmond サイトに適用されている A/V Edge 構成設定を削除します。
    
        Remove-CsAVEdgeConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-a-collection-from-the-service-scope"></a>サービスのスコープからコレクションを削除するには

  - このコマンドは、A/V Edge サーバー atl-edge-001.litwareinc.com に適用されている設定を削除します。
    
        Remove-CsAVEdgeConfiguration -Identity "service:EdgeServer:atl-edge-001.litwareinc.com"

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 で A/V Edge サーバーの構成情報を返す](lync-server-2013-return-a-v-edge-server-configuration-information.md)  
[Lync Server 2013 での A/V Edge サーバー構成設定のコレクションを作成または変更する](lync-server-2013-create-or-modify-a-collection-of-a-v-edge-server-configuration-settings.md)  


[Lync Server 2013 の音声/ビデオ (A/V) エッジサーバー](lync-server-2013-audio-video-a-v-edge-servers.md)  
[Remove-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg398786(v=OCS.15))  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

