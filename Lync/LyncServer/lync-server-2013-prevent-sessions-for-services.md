---
title: 'Lync Server 2013: サービスのセッションを禁止する'
description: 'Lync Server 2013: サービスのセッションを禁止します。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Prevent sessions for services
ms:assetid: 977dcc5c-2aac-48ef-86a1-a8d47b4d9e74
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182553(v=OCS.15)
ms:contentKeyID: 48184866
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 846a9da5330c3e64f61c27dfadd883f0c43a0ffa
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579813"
---
# <a name="prevent-sessions-for-services-in-lync-server-2013"></a>Lync Server 2013 でのサービスのセッションを禁止する

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-11-01_

Lync server コントロールパネルを使用して、特定のコンピューターで実行されているすべての Lync Server 2013 サービスの新しいセッションを禁止したり、特定の Lync Server 2013 サービスの新しいセッションを禁止したりすることができます。

<div>

## <a name="to-prevent-new-sessions-for-all-lync-server-services-on-a-computer"></a>コンピューター上のすべての Lync Server サービスの新しいセッションを禁止するには

1.  RTCUniversalServerAdmins グループのメンバーである (または同等のユーザー権限を持つ) ユーザー アカウント、または CsServerAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、Lync Server 2013 を展開したネットワーク内の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。 Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで [**トポロジ**] をクリックし、[**状態**] をクリックします。

4.  [ **状態** ] ページで、必要に応じてリストを並べ替えまたは検索し、新しいセッションを禁止するサービスを実行しているコンピューターを見つけてクリックします。

5.  [**アクション**] をクリックします。

6.  [ **すべてのサービスの新しいセッションを禁止する] を**クリックします。

</div>

<div>

## <a name="to-prevent-new-sessions-for-a-specific-service"></a>特定のサービスの新しいセッションを禁止するには

1.  RTCUniversalServerAdmins グループのメンバーである (または同等のユーザー権限を持つ) ユーザー アカウント、または CsServerAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、Lync Server 2013 を展開したネットワーク内の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。 Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで [**トポロジ**] をクリックし、[**状態**] をクリックします。

4.  [**状態**] ページで、必要に応じて一覧を並べ替えるかまたは検索して、開始または停止するサービスを実行しているコンピューターを確認してクリックします。

5.  [**プロパティ**] をクリックします。

6.  必要に応じてサービスの一覧を並べ替え、新しいセッションを禁止するサービスをクリックします。

7.  [**アクション**] をクリックします。

8.  [ **サービスの新しいセッションを禁止する] を**クリックします。

9.  [閉じる] **** をクリックします。

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 トポロジの管理](lync-server-2013-managing-the-lync-server-topology.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

