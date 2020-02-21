---
title: 'Lync Server 2013: 音声ルート構成ファイルのインポート'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Import a voice route configuration file
ms:assetid: 4bac05e5-ed8b-4f10-96b0-b8a65ff356ec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398301(v=OCS.15)
ms:contentKeyID: 48184049
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f9ce55c56c2b3df9907adb4df2da5dd951f31979
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42196740"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="import-a-voice-route-configuration-file-in-lync-server-2013"></a>Lync Server 2013 でのボイスルート構成ファイルのインポート

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-11-01_

音声ルーティング構成を公開せずに保存する場合は、次の手順に従って、Lync Server コントロールパネルの [構成のエクスポート] および [インポート] コマンドを使用して、音声ルーティング構成のスナップショットを保存および取得します。 音声ルーティング構成ファイル (vcfg) をインポートするときに、その間にサーバー上の音声ルーティング構成に変更が加えられた場合、Lync Server コントロールパネルの [**音声ルーティング**] グループのページには、音声ルーティングにコミットされていない変更があることが示されます。 これらの未確定の変更は、調整が必要な 2 つの構成間の相違です。

グループ内の任意のページの設定に対して変更をコミットしていない場合、変更はエクスポートされた音声構成ファイル (vcfg) に保存されます。 これにより、変更を公開する前に、複数のセッションで音声ルーティング構成の変更を行うことができます。

<div>

## <a name="to-import-a-voice-routing-configuration"></a>音声ルーティング構成をインポートするには

1.  RTCUniversalServerAdmins グループのメンバーとして、または CsVoiceAdministrator、CsServerAdministrator、または CsAdministrator の役割のメンバーとしてコンピューターにログオンします。 詳細については、「 [Lync Server 2013 でのセットアップのアクセス許可の委任](lync-server-2013-delegate-setup-permissions.md)」を参照してください。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。 Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで [**音声ルーティング**] をクリックします。

4.  [**操作**] メニューの [**構成のインポート**] をクリックします。

5.  インポートする構成ファイルを検索し、[**開く**] をクリックします。

6.  [**確定**] をクリックし、[**すべて確定**] をクリックします。
    
    <div>
    

    > [!NOTE]  
    > 音声構成ファイルをインポートする場合は、必ず [<STRONG>すべて確定</STRONG>] コマンドを実行して構成変更を公開する必要があります。 詳細については、「操作」のドキュメントの「 <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Lync Server 2013 での音声ルーティング構成に対する保留中の変更の公開</A>」を参照してください。

    
    </div>

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 での音声ルート構成ファイルのエクスポート](lync-server-2013-export-a-voice-route-configuration-file.md)  
[Lync Server 2013 で保留中の変更を音声ルーティング構成に公開する](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

