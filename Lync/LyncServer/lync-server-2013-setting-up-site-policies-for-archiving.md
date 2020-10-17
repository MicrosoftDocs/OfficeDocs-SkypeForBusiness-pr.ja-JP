---
title: 'Lync Server 2013: アーカイブ用のサイトポリシーのセットアップ'
description: 'Lync Server 2013: アーカイブ用のサイトポリシーのセットアップ。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up site policies for Archiving
ms:assetid: dc2ea206-8b9c-44dd-a479-efb217593c89
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205325(v=OCS.15)
ms:contentKeyID: 48185613
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 27e5b80b7f62ddc18d418415307457c7f2c4010d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558393"
---
# <a name="setting-up-site-policies-for-archiving-in-lync-server-2013"></a>Lync Server 2013 でのアーカイブ用のサイトポリシーのセットアップ

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-09_

特定のサイトのアーカイブを有効または無効にするには、各サイトのアーカイブポリシーを作成して構成します。 サイトポリシーはグローバルポリシーより優先されますが、ユーザーポリシーはサイトポリシーより優先されます。 アーカイブポリシーは、Microsoft Exchange 統合を使用していない場合、または Microsoft Exchange 統合を使用しているが、Exchange 2013 を使用しておらず、メールボックスを In-Place 保持に配置するユーザーがいる場合にのみ適用されます。

グローバルポリシー、サイトポリシー、およびユーザーポリシーの階層を含むアーカイブポリシーのしくみの詳細については、「 [Lync Server 2013](lync-server-2013-how-archiving-works.md) の計画に関するドキュメント、展開に関するドキュメント、または操作のドキュメントでのアーカイブの仕組み」を参照してください。

<div>


> [!NOTE]  
> 展開に対して Microsoft Exchange 統合を有効にした場合は、exchange 2013 に所属しているユーザーに対してアーカイブを有効にし、メールボックスを In-Place ホールドにするかどうかを Exchange In-Place 保持ポリシーで制御します。 詳細については、「展開」のドキュメントの「 <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Setting up policies For Exchange server integration using The Lync server 2013</A> 」を参照してください。<BR>アーカイブ ポリシーで内部または外部の通信のアーカイブを有効にする前に、アーカイブ構成のすべてのオプションを適切に指定してください。 詳細については、「展開」のドキュメントの「 <A href="lync-server-2013-configuring-archiving-options.md">Lync Server 2013 のアーカイブオプションの構成</A> 」を参照してください。



</div>

<div>

## <a name="to-create-an-archiving-policy-for-a-site"></a>サイトのアーカイブポリシーを作成するには

1.  CsArchivingAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザーウィンドウを開き、管理 URL を入力して Lync Server 2013 コントロールパネルを開きます。

3.  左側のナビゲーション バーで、[**監視とアーカイブ**] をクリックし、[**アーカイブ ポリシー**] をクリックします。
    
    グローバルポリシー、サイトポリシー、およびユーザーポリシーの階層を含むアーカイブポリシーのしくみの詳細については、「 [Lync Server 2013](lync-server-2013-how-archiving-works.md) の計画に関するドキュメント、展開に関するドキュメント、または操作のドキュメントでのアーカイブの仕組み」を参照してください。

4.  [**新規作成**] をクリックし、[**サイト ポリシー**] をクリックします。

5.  [ **サイトの選択**] で、ポリシーを適用するサイトをクリックします。

6.  **[新しいアーカイブ ポリシー]** で、次の操作を実行します。
    
      - [ **名前**] で、サイトポリシーの名前を指定します。
    
      - [ **説明**] に、サイトポリシーの内容に関する情報を入力します (例: Redmond のサイトポリシー)。
    
      - 指定したサイトの内部通信のアーカイブを制御するには、[ **内部通信をアーカイブ** する] チェックボックスをオンまたはオフにします。
    
      - 指定したサイトの外部通信のアーカイブを制御するには、[ **外部通信をアーカイブ** する] チェックボックスをオンまたはオフにします。

7.  [**確定**] をクリックします。

</div>

</div>

<span> </span>

</div>

</div>

</div>

