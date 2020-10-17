---
title: 'Lync Server 2013: 音声ルーティング構成に対する保留中の変更の公開'
description: 'Lync Server 2013: 保留中の変更を音声ルーティング構成に公開します。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Publish pending changes to the voice routing configuration
ms:assetid: ff941d0b-fb4b-47d2-b866-6d990ac66b81
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413088(v=OCS.15)
ms:contentKeyID: 48185974
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2a7a56b9a07606932a34dea7149a799dbb60b376
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565453"
---
# <a name="publish-pending-changes-to-the-voice-routing-configuration-in-lync-server-2013"></a>Lync Server 2013 で保留中の変更を音声ルーティング構成に公開する

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-08-07_

**音声ルーティング**グループのページで構成設定を変更した後、次の手順を実行して、保留中の変更を確認、公開、またはキャンセルします。

<div>


> [!IMPORTANT]  
> 一度に1人のユーザーだけが音声ルーティング構成設定を変更するようにしてください。<BR>すべての保留中の変更は、[ <STRONG>すべて確定</STRONG> ] コマンドを実行することによって同時に公開する必要があります。 保留中の変更を選択的に発行することはできません。 保留中の変更を公開する前に、[ <STRONG>未確定の変更の確認</STRONG> ] コマンドを実行して、公開しない構成の変更をキャンセルします。<BR>保留中の変更をコミットする前に、 <STRONG>音声ルーティング</STRONG> グループのページから移動すると、保留中の変更はすべて失われます。 ただし、現在の構成 (保留中の変更を含む) を音声構成ファイルにエクスポートして、更新された構成をインポートして公開することができます。 詳細については、「 <A href="lync-server-2013-export-a-voice-route-configuration-file.md">Lync Server 2013 で音声ルート構成ファイルをエクスポートする</A>」を参照してください。



</div>

<div>

## <a name="to-review-publish-or-cancel-voice-routing-configuration-changes"></a>音声ルーティング構成の変更を確認、公開、または取り消すには

1.  RTCUniversalServerAdmins グループのメンバーとして、または CsVoiceAdministrator、CsServerAdministrator、または CsAdministrator の役割のメンバーとしてコンピューターにログオンします。 詳細については、「 [Lync Server 2013 でのセットアップのアクセス許可の委任](lync-server-2013-delegate-setup-permissions.md)」を参照してください。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。 Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで [**音声ルーティング**] をクリックします。

4.  **音声ルーティング**グループの各ページの設定に対して、必要な構成の変更を行います。

5.  保留中の変更を公開せずに確認するには、[**コミット**] メニューの [**未確定の変更を確認**する] を選択します。

6.  保留中の変更をすべて取り消す場合は、次のいずれかを実行します。
    
      - [**コミット**] メニューから [コミットされていない**変更をすべてキャンセル**] を選択します。
    
      - 保留中の変更がある [ **音声ルーティング** ] ページのタブに移動して、保留中の変更があるアイテムを選択し、[ **確定**] をクリックして、[ **選択した変更のキャンセル**] をクリックします。

7.  保留中の変更をすべて確認し、公開しない変更をすべてキャンセルしたら、[ **確定**] をクリックし、[ **すべて確定**] をクリックします。

8.  保留中の変更すべての一覧を表示する、[コミットされていない **音声構成設定** ] ダイアログボックスで、[ **OK**] をクリックします。
    
    Lync Server コントロールパネルが変更をコミットすると、[ **音声ルーティング構成の発行に成功しまし** た] というメッセージが表示されます。

</div>

</div>

<span> </span>

</div>

</div>

</div>

