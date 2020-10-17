---
title: 'Lync Server 2013: 音声ルート構成ファイルのエクスポート'
description: 'Lync Server 2013: 音声ルート構成ファイルをエクスポートします。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Export a voice route configuration file
ms:assetid: 02ce922d-9ca8-4513-b09f-9de51f5c5bdc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398081(v=OCS.15)
ms:contentKeyID: 48183248
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 30bf342e11be41015df3cfd76f6a875381cb8b64
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564793"
---
# <a name="export-a-voice-route-configuration-file-in-lync-server-2013"></a>Lync Server 2013 での音声ルート構成ファイルのエクスポート

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-11-01_

音声ルーティング構成を公開せずに保存する場合は、次の手順に従って、Lync Server コントロールパネルの [構成のエクスポート] および [インポート] コマンドを使用して、音声ルーティング構成のスナップショットを保存および取得します。 音声ルーティング構成ファイル (vcfg) をインポートするときに、その間にサーバー上の音声ルーティング構成に変更が加えられた場合、Lync Server コントロールパネルの [ **音声ルーティング** ] グループのページには、音声ルーティングにコミットされていない変更があることが示されます。 これらの未確定の変更は、調整が必要な 2 つの構成間の相違です。

グループ内の任意のページの設定に対して変更をコミットしていない場合、変更はエクスポートされた音声構成ファイル (vcfg) に保存されます。 これにより、変更を公開する前に、複数のセッションで音声ルーティング構成の変更を行うことができます。

<div>

## <a name="to-export-a-voice-routing-configuration"></a>音声ルーティング構成をエクスポートするには

1.  RTCUniversalServerAdmins グループのメンバーとして、または CsVoiceAdministrator、CsServerAdministrator、または CsAdministrator の役割のメンバーとしてコンピューターにログオンします。 詳細については、「 [Lync Server 2013 でのセットアップのアクセス許可の委任](lync-server-2013-delegate-setup-permissions.md)」を参照してください。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。 Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで [**音声ルーティング**] をクリックします。

4.  [**アクション**] メニューの [**構成のエクスポート**] をクリックします。

5.  場所とファイル名を指定し、[**保存**] をクリックします。

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 でのボイスルート構成ファイルのインポート](lync-server-2013-import-a-voice-route-configuration-file.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

