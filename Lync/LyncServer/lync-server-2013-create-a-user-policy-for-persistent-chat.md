---
title: 'Lync Server 2013: 常設チャット用のユーザー ポリシーを作成する'
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
ms.openlocfilehash: 5a9bd88dd84b8b5056adf19ebc098daac54cb005
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726397"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-user-policy-for-persistent-chat-in-lync-server-2013"></a>Lync Server 2013 で常設チャット用のユーザー ポリシーを作成する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-06_

Lync Server コントロールパネルでは、ユーザーに割り当てることができるユーザーポリシーを定義することが**できます。**

ユーザー ポリシーは、グローバル ポリシーやサイト ポリシーよりも優先されますが、そのユーザー ポリシーを割り当てられた特定のユーザーのみを対象にします。

<div>


> [!NOTE]  
> 常設チャットサーバーを構成して使用するには、最初にトポロジビルダーを使用して、トポロジに常設チャットサーバーサポートを追加してから、トポロジを発行する必要があります。 詳細については、展開ドキュメントの「 <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Lync server 2013 での展開への常設チャットサーバーの追加</A>」を参照してください。<BR>常設チャットサーバーの構成設定を構成するには、展開ドキュメントの「 <A href="lync-server-2013-configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool.md">Lync server 2013 で常設チャットサーバーのオプションをグローバルまたは常設チャットサーバープールに構成</A>する」を参照してください。



</div>

<div>

## <a name="to-create-a-user-policy-for-persistent-chat"></a>常設チャットのユーザーポリシーを作成するには

1.  CsPersistentChatAdministrator、CsAdministrator、または CsUserAdministrator の役割に割り当てられているユーザーから、内部展開の任意のコンピューターにログオンします。

2.  [**スタート**] メニューから [Lync Server コントロールパネル] を選択するか、ブラウザーウィンドウを開き、管理 URL を入力します。 Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。
    
    <div>
    

    > [!IMPORTANT]  
    > Windows PowerShell コマンドレットを使うこともできます。 展開ドキュメントの「 <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Windows PowerShell コマンドレットを使用して常設チャットサーバーを構成</A>する」を参照してください。

    
    </div>

3.  左側のナビゲーション バーで [**常設チャット**] をクリックし、[**常設チャットのポリシー**] をクリックします。

4.  [**新規**] をクリックし、[**ユーザー ポリシー**] をクリックします。

5.  [**新規 常設チャットのポリシー**] で、次の操作を実行します。
    
      - [**名前**] で、新しいユーザー ポリシーの名前を指定します。
    
      - [**説明**] に、ユーザーポリシーの内容 (特定のユーザーの常設チャットポリシーなど) の詳細を入力します。
    
      - ユーザーポリシーを通じて明確に制御されていないすべてのユーザーの常設チャットを制御するには、[**常設チャットを有効に**する] チェックボックスをオンまたはオフにします。

6.  [**コミット**] をクリックします。

</div>

</div>

<span> </span>

</div>

</div>

</div>

