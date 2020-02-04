---
title: 'Lync Server 2013: 常設チャットのグローバル ポリシーを構成する'
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
ms.openlocfilehash: 49fb5f329851436e503a9e3e42e144353b70017f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722600"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-the-global-policy-for-persistent-chat-in-lync-server-2013"></a>Lync Server 2013 で常設チャットのグローバル ポリシーを構成する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-06_

既定のグローバルポリシーを単独で使用して、展開内のすべてのユーザーに対して常設チャット設定を有効にすることができます。 また、特定のユーザーやサイトに対して、常設チャットを有効または無効にするかどうかを制御するために、サイトとユーザーに対する追加ポリシーを指定することもできます。

グローバルポリシーは削除できません。 削除しようとすると、構成が既定値にリセットされます。

<div>


> [!NOTE]  
> 常設チャットサーバーを構成して使用するには、最初にトポロジビルダーを使用して、トポロジに常設チャットサーバーサポートを追加してから、トポロジを発行する必要があります。 詳細については、展開ドキュメントの「 <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Lync server 2013 での展開への常設チャットサーバーの追加</A>」を参照してください。<BR>常設チャットサーバーの構成設定を構成するには、展開ドキュメントの「 <A href="lync-server-2013-configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool.md">Lync server 2013 で常設チャットサーバーのオプションをグローバルまたは常設チャットサーバープールに構成</A>する」を参照してください。



</div>

<div>

## <a name="to-configure-the-global-policy-for-persistent-chat"></a>常設チャットのグローバルポリシーを構成するには

1.  CsPersistentChatAdministrator、CsAdministrator、または CsUserAdministrator の役割に割り当てられているユーザーから、内部展開の任意のコンピューターにログオンします。

2.  [**スタート**] メニューから [Lync Server コントロールパネル] を選択するか、ブラウザーウィンドウを開き、管理 URL を入力します。 Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「運用ドキュメントの[Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。
    
    <div>
    

    > [!IMPORTANT]  
    > Windows PowerShell コマンドレットを使うこともできます。 詳細については、「展開ドキュメントで<A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Windows PowerShell コマンドレットを使用して常設チャットサーバーを構成</A>する」を参照してください。

    
    </div>

3.  Lync Server コントロールパネルで、[**常設チャット**] をクリックし、[**常設チャットポリシー**] をクリックします。

4.  ポリシーの一覧の [**グローバル**] をクリックし、[**編集**] をクリックしてから、[**詳細の表示**] をクリックします。

5.  [**編集 常設チャットのポリシー - Global**] で、以下の手順を実行します。
    
      - グローバルという既定の名前を使用しない場合は、[**名前**] でグローバル ポリシーの新しい名前を指定します。
    
      - [**説明**] に、ユーザーポリシーの内容 (CentralSiteName のグローバルポリシーなど) の詳細を入力します。
    
      - サイトポリシーまたはユーザーポリシーを通じて明確に制御されないすべてのサイトとユーザーの常設チャットを制御するには、[**常設チャットを有効に**する] チェックボックスをオンまたはオフにします。

6.  [**コミット**] をクリックします。

</div>

</div>

<span> </span>

</div>

</div>

</div>

