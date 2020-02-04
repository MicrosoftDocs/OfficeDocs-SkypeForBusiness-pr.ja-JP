---
title: Lync Server でアーカイブ用のユーザーポリシーを作成および構成する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Creating and configuring user policies for Archiving in Lync Server
ms:assetid: 5af0e605-3563-4d6f-a3c6-511d204a3165
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204923(v=OCS.15)
ms:contentKeyID: 48184234
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cb4385d219173ca33ae7120dcf3e9d75d4c65f14
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756951"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="creating-and-configuring-user-policies-for-archiving-in-lync-server-2013"></a>Lync Server 2013 でアーカイブ用のユーザーポリシーを作成および構成する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-09_

Lync Server を使用している特定のユーザーに対してアーカイブを有効または無効にするには、まずユーザーポリシーを作成してから、1つ以上のユーザーまたはユーザーグループにポリシーを適用する必要があります。 特定のユーザーとユーザーグループにユーザーポリシーを適用する方法の詳細については、「展開ドキュメントの[Lync server 2013 でユーザーに Lync server のアーカイブポリシーを適用](lync-server-2013-applying-a-lync-server-archiving-policy-to-a-user.md)する」を参照してください。

グローバル、サイト、ユーザーのポリシーの階層など、アーカイブポリシーの動作について詳しくは、「計画のドキュメントでの[Lync Server 2013 でのアーカイブの動作](lync-server-2013-how-archiving-works.md)」をご覧ください。展開ドキュメント、または運用マニュアルを参照してください。

<div>


> [!NOTE]
> 展開に対して Microsoft Exchange の統合を有効にしている場合、Exchange 2013 を使っているユーザーに対してアーカイブが有効になっているかどうか、およびそのメールボックスがインプレースホールドに組み込まれているかどうかを Exchange のインプレースホールドポリシーで制御します。 詳細については、展開ドキュメントで<A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Exchange Server との統合を使用する場合の「Lync server 2013 でアーカイブするためのポリシーを設定する</A>」を参照してください。<BR>アーカイブを有効にする前に、アーカイブ構成ですべての適切なオプションを指定する必要があります。 詳細については、展開ドキュメントの「 <A href="lync-server-2013-configuring-archiving-options.md">Lync Server 2013 でアーカイブオプションを構成する</A>」を参照してください。



</div>

<div>

## <a name="to-configure-an-archiving-policy-for-users-homed-on-lync-server"></a>Lync Server を使用しているユーザーのアーカイブポリシーを構成するには

1.  CsArchivingAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザーウィンドウを開き、管理 URL を入力して Lync Server 2013 コントロールパネルを開きます。 Lync Server 2013 コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。

3.  左側のナビゲーション バーで、[**監視とアーカイブ**] をクリックし、[**アーカイブ ポリシー**] をクリックします。

4.  [**新規**] をクリックし、[**ユーザー ポリシー**] をクリックします。

5.  [**新しいアーカイブ ポリシー**] で、次の操作を実行します。
    
      - [**名前**] にユーザー ポリシーの名前を指定します。
    
      - [**説明**] に、ユーザー ポリシーの内容に関する情報を入力します (「法務部門のユーザー ポリシー」など)。
    
      - ユーザー ポリシーの内部通信のアーカイブを制御するには、[**内部通信をアーカイブする**] チェック ボックスをオンまたはオフにします。
    
      - ユーザー ポリシーの外部通信のアーカイブを制御するには、[**外部通信をアーカイブする**] チェック ボックスをオンまたはオフにします。

6.  [**確定**] をクリックします。

ユーザー ポリシーは、そのポリシーを割り当てたユーザーにのみ適用されます。 特定のユーザーへのユーザーポリシーの適用の詳細については、「展開ドキュメントの[Lync server 2013 でユーザーに Lync server のアーカイブポリシーを適用](lync-server-2013-applying-a-lync-server-archiving-policy-to-a-user.md)する」を参照してください。

</div>

</div>

<span> </span>

</div>

</div>

</div>

