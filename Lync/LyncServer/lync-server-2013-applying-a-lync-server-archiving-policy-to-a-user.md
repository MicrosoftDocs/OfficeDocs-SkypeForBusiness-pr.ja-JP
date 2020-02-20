---
title: 'Lync Server 2013: Lync Server アーカイブポリシーのユーザーへの適用'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Applying a Lync Server Archiving policy to a user
ms:assetid: a23e4876-aa8d-4f49-a3bd-3696616e8290
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205143(v=OCS.15)
ms:contentKeyID: 48185024
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d8fa30d5610d3b5e890fb909628ba9d8759ecfeb
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147350"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="applying-a-lync-server-archiving-policy-to-a-user-in-lync-server-2013"></a>Lync server 2013 のユーザーへの Lync Server アーカイブポリシーの適用

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-10_

Lync Server ユーザーポリシーを作成した後は、Lync Server 2013 に所属している特定のユーザーまたはユーザーグループに適用してから、有効にする必要があります。 特定のユーザーのユーザーポリシーの作成の詳細については、「展開」のドキュメントの「 [Lync Server 2013 でアーカイブ用のユーザーポリシーを作成および構成](lync-server-2013-creating-and-configuring-user-policies-for-archiving-in-lync-server.md)する」を参照してください。

グローバルポリシー、サイトポリシー、およびユーザーポリシーの階層を含むアーカイブポリシーのしくみの詳細については、「計画」、「展開」、または「操作」のドキュメントの「 [Lync Server 2013 でのアーカイブの仕組み](lync-server-2013-how-archiving-works.md)」を参照してください。

<div>


> [!NOTE]  
> アーカイブを構成して使用するためには、まずアーカイブを展開する必要があります。 詳細については、「展開」のドキュメントの「<A href="lync-server-2013-deploying-archiving.md">展開アーカイブ (Lync Server 2013</A> )」を参照してください。<BR>展開に対して Microsoft Exchange 統合を有効にした場合、Exchange のインプレース保持ポリシーによって、Exchange 2013 に所属しているユーザーに対してアーカイブを有効にし、そのメールボックスをインプレース保持の対象にするかどうかを制御します。 詳細については、「展開」のドキュメントの「 <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Setting up policies For Exchange server integration using The Lync server 2013</A> 」を参照してください。<BR>アーカイブを有効にするには、その前にアーカイブ構成で適切なオプションをすべて指定する必要があります。 詳細については、「展開」のドキュメントの「 <A href="lync-server-2013-configuring-archiving-options.md">Lync Server 2013 のアーカイブオプションの構成</A>」を参照してください。



</div>

<div>

## <a name="to-apply-a-lync-server-archiving-policy-to-a-user"></a>Lync Server アーカイブポリシーをユーザーに適用するには

1.  CsArchivingAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザーウィンドウを開き、管理 URL を入力して Lync Server 2013 コントロールパネルを開きます。 Lync Server 2013 コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで [**ユーザー**] をクリックし、構成するユーザー アカウントを検索します。

4.  検索結果一覧の表でユーザー アカウントをクリックし、[**編集**] をクリックして、[**詳細の表示**] をクリックします。

5.  [ **Lync Server ユーザーの編集**] の [**アーカイブポリシー**] で、適用するアーカイブユーザーポリシーを選択します。
    
    <div>
    

    > [!NOTE]  
    > [ <STRONG> &lt;自動&gt; </STRONG> ] 設定では、既定のサーバーインストールの設定が適用されます。 これらの設定はサーバーによって自動的に適用されます。

    
    </div>

6.  [**確定**] をクリックします。

</div>

</div>

<span> </span>

</div>

</div>

</div>

