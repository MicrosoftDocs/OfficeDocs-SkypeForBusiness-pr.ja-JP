---
title: 'Lync Server 2013: 常設チャットのユーザーポリシーを作成する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a user policy for Persistent Chat
ms:assetid: aa3774af-d442-4206-8a68-2fbb9102e9d6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205170(v=OCS.15)
ms:contentKeyID: 48185103
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 40e992bbbd5d2559619e2ebe5a0d67c83102e546
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42195880"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-a-user-policy-for-persistent-chat-in-lync-server-2013"></a>Lync Server 2013 で常設チャット用のユーザーポリシーを作成する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-06_

Lync Server コントロールパネルで **、ユーザーに**割り当てることができるユーザーポリシーを定義します。

ユーザー ポリシーはグローバル ポリシーとサイト ポリシーに優先しますが、そのユーザー ポリシーを割り当てられている個々のユーザーにしか適用されません。

<div>


> [!NOTE]  
> 常設チャットサーバーを構成して使用するには、まず、トポロジビルダーを使用して、常設チャットサーバーのサポートをトポロジに追加してから、トポロジを公開する必要があります。 詳細については、「展開」のドキュメントの「 <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Lync server 2013 での展開への常設チャットサーバーの追加</A>」を参照してください。<BR>常設チャットサーバーの構成設定を構成するには、「展開」のドキュメントの「 <A href="lync-server-2013-configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool.md">Configure 常設 Chat server options For Lync server 2013</A>の常設チャットサーバーのオプション」を参照してください。



</div>

<div>

## <a name="to-create-a-user-policy-for-persistent-chat"></a>常設チャットのユーザーポリシーを作成するには

1.  CsPersistentChatAdministrator、CsAdministrator、または CsUserAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  [**スタート**] メニューから [Lync Server コントロールパネル] を選択するか、ブラウザーウィンドウを開いて管理 URL を入力します。 Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。
    
    <div>
    

    > [!IMPORTANT]  
    > Windows PowerShell コマンドレットを使用することもできます。 「展開」のドキュメントの「 <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Windows PowerShell コマンドレットを使用して常設チャットサーバーを構成する</A>」を参照してください。

    
    </div>

3.  左側のナビゲーション バーで [**常設チャット**] をクリックし、[**常設チャットのポリシー**] をクリックします。

4.  [**新規**] をクリックし、[**ユーザー ポリシー**] をクリックします。

5.  [**新規 常設チャットのポリシー**] で、次の操作を実行します。
    
      - [**名前**] で、新しいユーザー ポリシーの名前を指定します。
    
      - [**説明**] に、ユーザーポリシーの内容に関する詳細を入力します (たとえば、特定のユーザーの常設チャットポリシー)。
    
      - ユーザーポリシーによって特に制御されていないすべてのユーザーの常設チャットを制御するには、[**常設チャットを有効に**する] チェックボックスをオンまたはオフにします。

6.  [**確定**] をクリックします。

</div>

</div>

<span> </span>

</div>

</div>

</div>

