---
title: 'Lync Server 2013: トポロジへのブランチサイトの追加'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Add branch sites to your topology
ms:assetid: b9c35fb0-0081-4aeb-8f95-ac2fcc6c3335
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412905(v=OCS.15)
ms:contentKeyID: 48185216
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9b03a612ba94733d52600af1db775e1bb0ef9b26
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037829"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="add-branch-sites-to-your-topology-in-lync-server-2013"></a>Lync Server 2013 でのトポロジへのブランチサイトの追加

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-05_

ブランチ サイトとは、WAN リンクを経由して本社に接続されている物理的なブランチ オフィスのことを表します。ブランチ サイトを Lync トポロジに追加するには、中央サイトで次の手順を実行します。

<div>

## <a name="to-add-branch-sites-to-your-topology"></a>トポロジにブランチ サイトを追加するには

1.  [**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server**]、[**Lync Server トポロジ ビルダー**] の順にクリックします。

2.  コンソール ツリーで中央サイトを展開し、[**ブランチ サイト**] を右クリックして、[**新しいブランチ サイト**] をクリックします。

3.  [**新しいブランチ サイトの定義**] ダイアログ ボックスで、[**名前**] をクリックし、ブランチ サイトの名前を入力します。

4.  (オプション) **[説明]** をクリックし、ブランチ サイトの分かりやすい説明を入力します。

5.  **[次へ]** をクリックします。

6.  (オプション) 次の **[新しいブランチ サイトの定義]** ダイアログ ボックスで、以下のいずれかの操作を行います。
    
      - **[市区町村]** をクリックし、ブランチ サイトが所在する市区町村の名前を入力します。
    
      - **[都道府県/地域]** をクリックし、ブランチ サイトが所在する都道府県または地域の名前を入力します。
    
      - **[国番号]** をクリックし、ブランチ サイトが所在する国または地域の 2 桁番号を入力します。

7.  **[次へ]** をクリックし、次のいずれかを実行します。
    
      - このサイトで存続可能ブランチアプライアンスまたはサーバーを使用している場合は、[**このウィザードを閉じるときに新しい存続可能ウィザードを開く**] チェックボックスがオンになっていることを確認し、[**完了**] をクリックして、表示されるウィザードの指示に従います。 ウィザード項目の詳細については、「 [Define a 存続可能 Branch Appliance Or Server In Lync server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)」を参照してください。
    
      - このサイトで存続可能ブランチ アプライアンスまたは存続可能ブランチ サーバーを使用していない場合は、**[このウィザードが閉じたら新しい存続可能ウィザードを開く]** チェック ボックスをオフにして、**[完了]** をクリックします。

8.  トポロジに追加する各ブランチ サイトに対して、前のステップを繰り返します。

**次のステップ: **

存続可能ブランチアプライアンスまたはサーバーの場合: [Lync Server 2013 での存続可能ブランチアプライアンスまたはサーバーの定義](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)

回復不能な PSTN 接続の場合: lync server [2013 のブランチサイト用の pstn ゲートウェイを定義](lync-server-2013-define-a-pstn-gateway-for-a-branch-site.md)するか、 [lync server 2013 でメディアバイパスを使用してトランクを構成](lync-server-2013-configure-a-trunk-with-media-bypass.md)するか、 [lync server 2013 でメディアバイパスを構成せずにトランクを構成](lync-server-2013-configure-a-trunk-without-media-bypass.md)する

</div>

</div>

<span> </span>

</div>

</div>

</div>

