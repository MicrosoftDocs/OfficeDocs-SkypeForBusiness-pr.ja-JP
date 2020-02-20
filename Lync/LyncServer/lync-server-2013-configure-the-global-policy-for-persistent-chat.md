---
title: 'Lync Server 2013: 常設チャットのグローバルポリシーの構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure the global policy for Persistent Chat
ms:assetid: 6176eb5c-19de-4c07-bcc0-2e38f8965966
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204951(v=OCS.15)
ms:contentKeyID: 48184323
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c77093e640d51204a7e16b2b32df02afcefe0bd7
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145656"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-the-global-policy-for-persistent-chat-in-lync-server-2013"></a>Lync Server 2013 で常設チャットのグローバルポリシーを構成する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-06_

既定のグローバルポリシーを単独で使用して、展開内のすべてのユーザーの常設チャット設定を有効にすることができます。 また、特定のユーザーやサイトに対して常設チャットを有効または無効にするかどうかを制御するために、サイトおよびユーザーの追加のポリシーを指定することもできます。

グローバル ポリシーは削除できません。 削除しようとすると、構成が既定値にリセットされます。

<div>


> [!NOTE]  
> 常設チャットサーバーを構成して使用するには、まず、トポロジビルダーを使用して、常設チャットサーバーのサポートをトポロジに追加してから、トポロジを公開する必要があります。 詳細については、「展開」のドキュメントの「 <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Lync server 2013 での展開への常設チャットサーバーの追加</A>」を参照してください。<BR>常設チャットサーバーの構成設定を構成するには、「展開」のドキュメントの「 <A href="lync-server-2013-configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool.md">Configure 常設 Chat server options For Lync server 2013</A>の常設チャットサーバーのオプション」を参照してください。



</div>

<div>

## <a name="to-configure-the-global-policy-for-persistent-chat"></a>常設チャットのグローバルポリシーを構成するには

1.  CsPersistentChatAdministrator、CsAdministrator、または CsUserAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  [**スタート**] メニューから [Lync Server コントロールパネル] を選択するか、ブラウザーウィンドウを開いて管理 URL を入力します。 Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「操作」のドキュメントの「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。
    
    <div>
    

    > [!IMPORTANT]  
    > Windows PowerShell コマンドレットを使用することもできます。 詳細については、「展開」のドキュメントの「 <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Windows PowerShell コマンドレットを使用して常設チャットサーバーを構成する</A>」を参照してください。

    
    </div>

3.  Lync Server コントロールパネルで、[**常設チャット**] をクリックし、[**常設チャットのポリシー**] をクリックします。

4.  ポリシーの一覧の [**グローバル**] をクリックし、[**編集**] をクリックしてから、[**詳細の表示**] をクリックします。

5.  [**編集 常設チャットのポリシー - Global**] で、以下の手順を実行します。
    
      - グローバルという既定の名前を使用しない場合は、[**名前**] でグローバル ポリシーの新しい名前を指定します。
    
      - [**説明**] に、ユーザーポリシーの内容に関する詳細を入力します (たとえば、CentralSiteName のグローバルポリシー)。
    
      - サイトポリシーまたはユーザーポリシーによって特に制御されていないすべてのサイトとユーザーの常設チャットを制御するには、[**常設チャットを有効に**する] チェックボックスをオンまたはオフにします。

6.  [**確定**] をクリックします。

</div>

</div>

<span> </span>

</div>

</div>

</div>

