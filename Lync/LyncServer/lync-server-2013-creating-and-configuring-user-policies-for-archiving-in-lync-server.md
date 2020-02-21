---
title: Lync Server でのアーカイブ用のユーザーポリシーの作成と構成
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
ms.openlocfilehash: f772119bac58f9ddd436289c8f1df210665d858d
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42198950"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="creating-and-configuring-user-policies-for-archiving-in-lync-server-2013"></a>Lync Server 2013 でのアーカイブ用のユーザーポリシーの作成と構成

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-09_

Lync Server に所属している特定のユーザーに対してアーカイブを有効または無効にするには、まずユーザーポリシーを作成し、そのポリシーを1人以上のユーザーまたはユーザーグループに適用する必要があります。 特定のユーザーおよびユーザーグループへのユーザーポリシーの適用の詳細については、「展開」のドキュメントの「lync server の[アーカイブポリシーの2013ユーザーへの適用](lync-server-2013-applying-a-lync-server-archiving-policy-to-a-user.md)」を参照してください。

グローバルポリシー、サイトポリシー、およびユーザーポリシーの階層を含むアーカイブポリシーのしくみの詳細については、「計画」、「展開」、または「操作」のドキュメントの「 [Lync Server 2013 でのアーカイブの仕組み](lync-server-2013-how-archiving-works.md)」を参照してください。

<div>


> [!NOTE]
> 展開に対して Microsoft Exchange 統合を有効にした場合、Exchange のインプレース保持ポリシーによって、Exchange 2013 に所属しているユーザーに対してアーカイブを有効にし、そのメールボックスをインプレース保持の対象にするかどうかを制御します。 詳細については、「展開」のドキュメントの「 <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Setting up policies For Exchange server integration using The Lync server 2013</A> 」を参照してください。<BR>アーカイブを有効にするには、その前にアーカイブ構成で適切なオプションをすべて指定する必要があります。 詳細については、「展開」のドキュメントの「 <A href="lync-server-2013-configuring-archiving-options.md">Lync Server 2013 のアーカイブオプションの構成</A>」を参照してください。



</div>

<div>

## <a name="to-configure-an-archiving-policy-for-users-homed-on-lync-server"></a>Lync Server に所属するユーザーのアーカイブポリシーを構成するには

1.  CsArchivingAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザーウィンドウを開き、管理 URL を入力して Lync Server 2013 コントロールパネルを開きます。 Lync Server 2013 コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで、**[監視とアーカイブ]** をクリックし、**[アーカイブ ポリシー]** をクリックします。

4.  **[新規]** をクリックし、**[ユーザー ポリシー]** をクリックします。

5.  [**新しいアーカイブ ポリシー**] で、次の操作を実行します。
    
      - [**名前**] にユーザー ポリシーの名前を指定します。
    
      - [**説明**] に、ユーザー ポリシーの内容に関する情報を入力します (「法務部門のユーザー ポリシー」など)。
    
      - ユーザー ポリシーの内部通信のアーカイブを制御するには、[**内部通信をアーカイブする**] チェック ボックスをオンまたはオフにします。
    
      - ユーザー ポリシーの外部通信のアーカイブを制御するには、[**外部通信をアーカイブする**] チェック ボックスをオンまたはオフにします。

6.  [**確定**] をクリックします。

ユーザー ポリシーは、そのポリシーを割り当てたユーザーにのみ適用されます。 ユーザーポリシーを特定のユーザーに適用する方法の詳細については、「展開」のドキュメントの「 [2013 ユーザーへの Lync Server アーカイブポリシーの適用](lync-server-2013-applying-a-lync-server-archiving-policy-to-a-user.md)」を参照してください。

</div>

</div>

<span> </span>

</div>

</div>

</div>

