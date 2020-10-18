---
title: 音声ビデオエッジサーバー構成設定のコレクションを作成または変更する
description: 音声ビデオエッジサーバー構成設定のコレクションを作成または変更します。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a collection of A/V Edge Server configuration settings
ms:assetid: 43899518-59c6-4be4-8892-d6f6207bfaab
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688039(v=OCS.15)
ms:contentKeyID: 49733630
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3cdf7dca19446f4eac584564eed776f7fde47bfe
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48578343"
---
# <a name="create-or-modify-a-collection-of-av-edge-server-configuration-settings-in-lync-server-2013"></a>Lync Server 2013 での音声ビデオエッジサーバー構成設定のコレクションの作成または変更

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-11-01_

音声ビデオ エッジ サービスにより、内部ユーザー (組織のネットワークにログオンしているユーザー) は、外部ユーザー (組織のネットワークにログオンしていないユーザー) と音声とビデオを共有することができます。音声ビデオ エッジ サービスは、主に音声ビデオ エッジ構成設定を使用して管理されます。音声ビデオ エッジ構成設定は、サイト スコープまたはサービス スコープで (つまり音声ビデオ エッジ サーバーごとに) 設定できます。

Lync Server をインストールすると、音声ビデオエッジ構成設定のグローバルコレクションが作成されます。 これに加えて、Windows PowerShell と New-CsAVEdgeConfiguration コマンドレットを使用して、サイトスコープまたはサービススコープ (つまり、個々の音声ビデオエッジサーバー) で新しい設定を作成することもできます。 新しい設定を作成する場合は、次のことに留意してください。

  - サービス スコープで (つまり個々のサーバーに) 構成された設定は、すべてに優先されます。

  - サイト スコープで構成した設定は、グローバル スコープで構成した設定より優先されます。ただし、サービス スコープ設定はサイトスコープ設定を置き換えます。

  - 個々のサーバーでサービス設定が構成されていない場合、およびサーバーが配置されているサイトにサイト設定が存在しない場合に限り、グローバル スコープの設定が使用されます。

すべての設定は、Set-CsAVEdgeConfiguration コマンドレットを使用して変更できます。 詳細については、 [get-csavedgeconfiguration](https://technet.microsoft.com/library/Gg412884(v=OCS.15)) および [get-csavedgeconfiguration](https://technet.microsoft.com/library/Gg412869(v=OCS.15)) コマンドレットのヘルプトピックを参照してください。

<div>

## <a name="to-create-new-av-edge-configuration-settings-at-the-site-scope"></a>サイトスコープで新しい音声ビデオエッジ構成設定を作成するには

  - 以下のコマンドでは、Redmond サイト用の音声ビデオ エッジ構成設定の新しいコレクションを作成します。
    
        New-CsAVEdgeConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-create-custom-av-edge-configuration-settings-at-the-site-scope"></a>サイトスコープでカスタムの音声ビデオエッジ構成設定を作成するには

  - 追加のパラメーターが指定されない場合、これらの新しい設定では、音声ビデオ エッジ サービスに既定値が使用されます。あるいは、追加のパラメーターとパラメーター値を指定してカスタム コレクションを作成できます。たとえばこのコマンドでは、MaxTokenLifetime プロパティを 4 時間 (04 時間 : 00 分 : 00 秒) に設定します。
    
        New-CsAVEdgeConfiguration -Identity "site:Redmond" -MaxTokenLifetime "04:00:00"

</div>

<div>

## <a name="to-create-custom-av-edge-configuration-settings-at-the-service-scope"></a>サービススコープでカスタムの音声ビデオエッジ構成設定を作成するには

  - このコマンドは、音声ビデオ エッジ サーバー atl-edge-001.litwareinc.com に適用される同様のコレクションを作成します。
    
        New-CsAVEdgeConfiguration -Identity "service:EdgeServer:atl-edge-001.litwareinc.com" -MaxTokenLifetime "04:00:00"

</div>

<div>

## <a name="to-modify-existing-av-edge-configuration-settings"></a>既存の音声ビデオエッジ構成設定を変更するには

  - この例では、Redmond サイトの最大トークン存続時間を 12 時間に変更するために、Set-CsAVEdgeConfiguration コマンドレットが使用されます。
    
        Set-CsAVEdgeConfiguration -Identity "site:Redmond" -MaxTokenLifetime "12:00:00"

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 での音声ビデオエッジサーバーの構成情報の取得](lync-server-2013-return-a-v-edge-server-configuration-information.md)  
[Lync Server 2013 の音声ビデオエッジサーバー構成設定の既存コレクションの削除](lync-server-2013-delete-an-existing-collection-of-a-v-edge-server-configuration-settings.md)  


[Lync Server 2013 の音声ビデオ (A/V) エッジサーバー](lync-server-2013-audio-video-a-v-edge-servers.md)  
[Get-csavedgeconfiguration](https://technet.microsoft.com/library/Gg412884(v=OCS.15))  
[Get-csavedgeconfiguration](https://technet.microsoft.com/library/Gg412869(v=OCS.15))  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

