---
title: 'Lync Server 2013: 音声ビデオエッジサーバーの構成情報を返す'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Return A/V Edge Server configuration information
ms:assetid: b041f5a4-2387-4075-846c-ec4f99640903
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721850(v=OCS.15)
ms:contentKeyID: 49733783
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 920c45abf98678c3e866650e094b9e4a52a418a4
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144633"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="return-av-edge-server-configuration-information-in-lync-server-2013"></a>Lync Server 2013 での音声ビデオエッジサーバーの構成情報の取得

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-11-01_

音声ビデオ エッジ サービスにより、内部ユーザー (組織のネットワークにログオンしているユーザー) は、外部ユーザー (組織のネットワークにログオンしていないユーザー) と音声とビデオを共有することができます。音声ビデオ エッジ サービスは、主に音声ビデオ エッジ構成設定を使用して管理されます。音声ビデオ エッジ構成設定は、サイト スコープまたはサービス スコープで (つまり音声ビデオ エッジ サーバーごとに) 設定できます。

組織で使用されている音声ビデオエッジ構成設定に関する情報を戻すには、Windows PowerShell と Get-csavedgeconfiguration コマンドレットを使用する必要があります。 詳細については、 [get-csavedgeconfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsAVEdgeConfiguration)コマンドレットのヘルプトピックを参照してください。

Get-CsAVEdgeConfiguration コマンドレットからは次のような情報が返されます。

    Identity              : Global
    MaxTokenLifetime      : 08:00:00
    MaxBandwidthPerUserKb : 10000
    MaxBandwidthPerPortKb : 3000

<div>

## <a name="to-return-information-for-all-your-av-edge-configuration-settings"></a>すべての音声ビデオエッジ構成設定に関する情報を戻すには

  - 次のコマンドを実行すると、組織で現在使用中のすべての音声ビデオ エッジ構成設定に関する情報が返されます。
    
        Get-CsAVEdgeConfiguration

</div>

<div>

## <a name="to-return-information-for-site-scoped-av-edge-configuration-settings"></a>サイトスコープの音声ビデオエッジ構成設定に関する情報を戻すには

  - 音声ビデオ エッジ構成設定の特定のコレクションに関する情報を返すには、Get-CsAVEdgeConfiguration コマンドレットの実行時にそのコレクションの識別子を指定します。たとえば、次のコマンドでは、Redmond サイトに適用されている設定に関する情報のみが返されます。
    
        Get-CsAVEdgeConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-return-information-for-service-scoped-av-edge-configuration-settings"></a>サービススコープの音声ビデオエッジ構成設定に関する情報を戻すには

  - 次のコマンドでは、特定の音声ビデオ エッジ サーバーに適用された設定に関する情報のみが返されます。
    
        Get-CsAVEdgeConfiguration -Identity "service:EdgeServer:atl-edge-001.litwareinc.com"

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 での音声ビデオエッジサーバー構成設定のコレクションの作成または変更](lync-server-2013-create-or-modify-a-collection-of-a-v-edge-server-configuration-settings.md)  
[Lync Server 2013 の音声ビデオエッジサーバー構成設定の既存コレクションの削除](lync-server-2013-delete-an-existing-collection-of-a-v-edge-server-configuration-settings.md)  


[Lync Server 2013 の音声ビデオ (A/V) エッジサーバー](lync-server-2013-audio-video-a-v-edge-servers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

