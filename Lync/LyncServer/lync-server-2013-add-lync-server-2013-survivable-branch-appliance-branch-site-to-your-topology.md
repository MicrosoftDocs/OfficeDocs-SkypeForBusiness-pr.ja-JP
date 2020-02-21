---
title: Lync Server 2013 存続可能 Branch Appliance ブランチサイトをトポロジに追加する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Add Lync Server 2013 Survivable Branch Appliance branch site to your topology
ms:assetid: d3142a37-4606-456d-8ea9-6cc0e51e55f3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721896(v=OCS.15)
ms:contentKeyID: 49733830
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6b43272cc5ca054f913d51ec157802dc8f847461
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42179964"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="add-lync-server-2013-survivable-branch-appliance-branch-site-to-your-topology"></a>Lync Server 2013 存続可能 Branch Appliance ブランチサイトをトポロジに追加する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-07_

Microsoft Lync Server 2013 存続可能 Branch アプライアンス (SBA) は、バックアップレジストラーとして Microsoft Lync Server 2010 フロントエンドプールに関連付けることはできません。 SBA は、Microsoft Lync Server 2013 フロントエンドプールに関連付けられている必要があります。 これらの手順では、Microsoft Lync Server 2013 SBA を想定しています。 中央サイトでこの手順を実行します。

<div>

## <a name="to-add-branch-sites-with-microsoft-lync-server-2013-sba-to-your-topology"></a>Microsoft Lync Server 2013 SBA を使用してトポロジにブランチサイトを追加するには

1.  トポロジ ビルダーを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server トポロジ ビルダー**] の順にクリックします。

2.  コンソールツリーでセントラルサイトを展開し、[**ブランチサイト**] を展開して、[**新しいブランチサイト**] をクリックします。

3.  [**新しいブランチサイトの定義**] ダイアログボックスで、[**名前**] をクリックし、新しいブランチサイトの名前を入力します。

4.  (オプション) **[説明]** をクリックし、ブランチ サイトの分かりやすい説明を入力します。

5.  **[次へ]** をクリックします。

6.  (オプション) 次の **[新しいブランチ サイトの定義]** ダイアログ ボックスで、以下のいずれかの操作を行います。
    
      - **[市区町村]** をクリックし、ブランチ サイトが所在する市区町村の名前を入力します。
    
      - **[都道府県/地域]** をクリックし、ブランチ サイトが所在する都道府県または地域の名前を入力します。
    
      - **[国番号]** をクリックし、ブランチ サイトが所在する国または地域の 2 桁番号を入力します。

7.  **[次へ]** をクリックし、次のいずれかを実行します。
    
      - このサイトで存続可能 Branch Appliance または存続可能ブランチサーバーを使用している場合は、[**このウィザードを閉じるときに新しい存続可能ウィザードを開く**] チェックボックスがオンになっていることを確認してください。
    
      - このサイトで存続可能 Branch Appliance または存続可能ブランチサーバーを使用していない場合は、[**このウィザードを閉じるときに新しい存続可能ウィザードを開く**] チェックボックスをオフにします。
    
      - [**完了**] をクリックし、表示されるウィザードの指示に従います。 ウィザード項目の詳細については、「 [Define a 存続可能 Branch Appliance Or Server In Lync server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)」を参照してください。

8.  トポロジに追加する各ブランチ サイトに対して、前のステップを繰り返します。

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 での存続可能ブランチアプライアンスまたはサーバーの定義](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)  
[Lync Server 2013 でのブランチサイト用の PSTN ゲートウェイの定義](lync-server-2013-define-a-pstn-gateway-for-a-branch-site.md)  
[Lync Server 2013 でメディアバイパスを使用してトランクを構成する](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[Lync Server 2013 でメディアバイパスを使用せずにトランクを構成する](lync-server-2013-configure-a-trunk-without-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

