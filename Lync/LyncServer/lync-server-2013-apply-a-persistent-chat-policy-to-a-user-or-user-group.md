---
title: 'Lync Server 2013: 常設チャットポリシーをユーザーまたはユーザーグループに適用する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Apply a Persistent Chat policy to a user or user group
ms:assetid: 809ef4e0-8d42-4feb-b7c0-3995f39867a7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205038(v=OCS.15)
ms:contentKeyID: 48184652
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 452028e9fb67443d92e244d2d23c65f4efa9e308
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147130"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="apply-a-persistent-chat-policy-to-a-user-or-user-group-in-lync-server-2013"></a>Lync Server 2013 で常設チャットポリシーをユーザーまたはユーザーグループに適用する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-06_

ユーザーが Lync Server 2013 に対して有効になっている場合は、特定のユーザーに適切なポリシーを適用して、常設チャットサーバーに対して有効または無効にすることができます。

<div>


> [!NOTE]  
> 常設チャットサーバーを構成して使用するには、まず、トポロジビルダーを使用して、常設チャットサーバーのサポートをトポロジに追加してから、トポロジを公開する必要があります。 詳細については、「展開」のドキュメントの「 <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Lync server 2013 での展開への常設チャットサーバーの追加</A>」を参照してください。<BR>常設チャットサーバーの構成設定を構成するには、「展開」のドキュメントの「 <A href="lync-server-2013-configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool.md">Configure 常設 Chat server options For Lync server 2013</A>の常設チャットサーバーのオプション」を参照してください。



</div>

このトピックの手順を使用して、以前に作成した常設チャットのユーザーポリシーを1つまたは複数のユーザーアカウントまたはユーザーグループに適用します。

<div>

## <a name="to-apply-a-persistent-chat-user-policy-to-a-user-account"></a>常設チャットのユーザーポリシーをユーザーアカウントに適用するには

1.  CsPersistentChatAdministrator、CsAdministrator、または CsUserAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  [**スタート**] メニューから [Lync Server コントロールパネル] を選択するか、ブラウザーウィンドウを開いて管理 URL を入力します。 Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで [**ユーザー**] をクリックし、構成するユーザー アカウントを検索します。

4.  検索結果一覧の表でユーザー アカウントをクリックし、[**編集**] をクリックして、[**詳細の表示**] をクリックします。

5.  [ **Lync Server ユーザーの編集**] の [**常設チャットポリシー**] で、適用する常設チャットユーザーポリシーを選択します。
    
    <div>
    

    > [!NOTE]  
    > [ <STRONG> &lt;自動&gt; </STRONG> ] 設定では、既定の有効なポリシーが適用されます。 これらの設定はサーバーによって自動的に適用されます。

    
    </div>

6.  [**確定**] をクリックします。

</div>

</div>

<span> </span>

</div>

</div>

</div>

