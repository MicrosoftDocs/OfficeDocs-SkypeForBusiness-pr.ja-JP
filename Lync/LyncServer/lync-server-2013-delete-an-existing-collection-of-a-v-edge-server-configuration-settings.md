---
title: 音声ビデオエッジサーバー構成設定の既存コレクションの削除
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
ms.openlocfilehash: 85a5d251124b08e43416ae15d34342af8b12a930
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147610"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="delete-an-existing-collection-of-av-edge-server-configuration-settings-in-lync-server-2013"></a>Lync Server 2013 の音声ビデオエッジサーバー構成設定の既存コレクションの削除

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-11-01_

音声ビデオ エッジ サービスにより、内部ユーザー (組織のネットワークにログオンしているユーザー) は、外部ユーザー (組織のネットワークにログオンしていないユーザー) と音声とビデオを共有することができます。音声ビデオ エッジ サービスは、主に音声ビデオ エッジ構成設定を使用して管理されます。音声ビデオ エッジ構成設定は、サイト スコープまたはサービス スコープで (つまり音声ビデオ エッジ サーバーごとに) 設定できます。

Lync Server をインストールすると、音声ビデオエッジ構成設定のグローバルコレクションが作成されます。 このグローバルコレクションは削除できません。 ただし、Windows PowerShell と Get-csavedgeconfiguration コマンドレットを使用して、グローバルコレクションを "リセット" することができます。これは単に、グローバルコレクション内のすべてのプロパティ値が既定値にリセットされることを意味します。 たとえば、MaxTokenLifetime プロパティを16時間に設定した場合、そのプロパティは既定値の8時間にリセットされます。

ただし、サイト スコープまたはサービス スコープのどちらかで作成したカスタム設定コレクションは、Remove-CsDiagnosticHeaderConfiguration コマンドレットを使用して削除できます。サイト設定を削除すると、そのサイト内の音声ビデオ エッジ サーバーはグローバル設定によって管理されます。サービス スコープの設定を削除すると、サーバーは、サイト設定が存在する場合はサイト設定によって、サイト設定が使用できない場合はグローバル設定によって管理されます。

詳細については、 [get-csavedgeconfiguration](https://technet.microsoft.com/library/Gg398786(v=OCS.15))コマンドレットのヘルプトピックを参照してください。

<div>

## <a name="to-reset-the-global-collection"></a>グローバルコレクションをリセットするには

  - 次のコマンドは、音声ビデオ エッジ構成設定のグローバル コレクションをリセットします。
    
        Remove-CsAVEdgeConfiguration -Identity "global"

</div>

<div>

## <a name="to-remove-a-collection-from-the-site-scope"></a>サイトスコープからコレクションを削除するには

  - 次のコマンドは、Redmond サイトに適用される音声ビデオ エッジ構成設定を削除します。
    
        Remove-CsAVEdgeConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-a-collection-from-the-service-scope"></a>サービススコープからコレクションを削除するには

  - 次のコマンドは、音声ビデオ エッジ サーバー atl-edge-001.litwareinc.com に適用される設定を削除します。
    
        Remove-CsAVEdgeConfiguration -Identity "service:EdgeServer:atl-edge-001.litwareinc.com"

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 での音声ビデオエッジサーバーの構成情報の取得](lync-server-2013-return-a-v-edge-server-configuration-information.md)  
[Lync Server 2013 での音声ビデオエッジサーバー構成設定のコレクションの作成または変更](lync-server-2013-create-or-modify-a-collection-of-a-v-edge-server-configuration-settings.md)  


[Lync Server 2013 の音声ビデオ (A/V) エッジサーバー](lync-server-2013-audio-video-a-v-edge-servers.md)  
[Get-csavedgeconfiguration](https://technet.microsoft.com/library/Gg398786(v=OCS.15))  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

