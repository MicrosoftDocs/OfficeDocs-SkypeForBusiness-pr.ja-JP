---
title: 'Lync Server 2013: 保留中の変更を音声ルーティング構成に公開する'
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
ms.openlocfilehash: aac5c30cb73ef428d0571a1a0fe6853dbf70db4c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724617"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="publish-pending-changes-to-the-voice-routing-configuration-in-lync-server-2013"></a>Lync Server 2013 の音声ルーティング構成に保留中の変更を発行する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-08-07_

[**音声ルーティング**] グループの各ページで会議設定のいずれかを変更した後は、ここでの手順を実行して、保留中の変更を確認、公開、またはキャンセルします。

<div>


> [!IMPORTANT]  
> 必ず、一度に 1 人のユーザーだけが音声ルーティング構成の設定を変更するようにしてください。<BR>保留中の変更すべては、[<STRONG>すべて確定</STRONG>] コマンドを実行することによって同時に公開する必要があります。保留中の変更のどれかを選択して公開することはできません。保留中の変更を公開する前に、[<STRONG>未確定の変更の確認</STRONG>] コマンドを実行し、公開しない保留中の変更をすべてキャンセルしてください。<BR>保留中の変更を確定する前に [<STRONG>音声ルーティング</STRONG>] グループのページから移動して離れると、すべての保留中の変更が失われます。 ただし、現在の構成 (保留中の変更を含む) を音声構成ファイルにエクスポートしておき、後でインポートして更新された構成を公開することができます。 詳細については、「 <A href="lync-server-2013-export-a-voice-route-configuration-file.md">Lync Server 2013 でボイスルート構成ファイルをエクスポートする</A>」を参照してください。



</div>

<div>

## <a name="to-review-publish-or-cancel-voice-routing-configuration-changes"></a>音声ルーティング構成の変更を確認、公開、または取り消すには

1.  RTCUniversalServerAdmins グループのメンバーとして、あるいは CsVoiceAdministrator、CsServerAdministrator、または CsAdministrator の役割のメンバーとしてコンピューターにログオンします。 詳細については、「 [Lync Server 2013 でセットアップのアクセス許可を委任](lync-server-2013-delegate-setup-permissions.md)する」を参照してください。

2.  ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。 Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。

3.  左側のナビゲーション バーで [**音声ルーティング**] をクリックします。

4.  [**音声ルーティング**] グループの各ページの設定について、必要な構成の変更を加えます。

5.  公開せずに保留中の変更を確認するには、[**確定**] メニューで [**未確定の変更の確認**] を選択します。

6.  保留中の変更のいずれかを取り消す場合は、次のいずれかの操作を行います。
    
      - [**確定**] メニューで [**すべての未確定の変更のキャンセル**] を選択します。
    
      - 取り消す保留中の変更が含まれる [**音声ルーティング**] ページのタブに移動し、保留中の変更を含む項目を選択し、[**確定**] をクリックして、[**選択した変更のキャンセル**] をクリックします。

7.  保留中の変更をすべて確認し、公開しない変更をすべてキャンセルしたら、[**確定**] をクリックして、[**すべて確定**] をクリックします。

8.  保留中の変更すべての一覧が表示された [**未確定の音声構成設定**] ダイアログ ボックスで、[**OK**] をクリックします。
    
    Lync Server コントロールパネルで変更をコミットすると、**正常に公開された音声ルーティング構成**のメッセージが表示されます。

</div>

</div>

<span> </span>

</div>

</div>

</div>

