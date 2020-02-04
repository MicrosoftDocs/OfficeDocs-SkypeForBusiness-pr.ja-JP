---
title: 'Lync Server 2013: トポロジへのブランチ サイトの追加'
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
ms.openlocfilehash: 2df1871956b33b3781128e2b62af13bdd875d10b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735047"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="add-branch-sites-to-your-topology-in-lync-server-2013"></a>Lync Server 2013 でのトポロジへのブランチ サイトの追加

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-05_

ブランチサイトは、WAN リンク経由でメインオフィスに接続されている物理的な支店を表します。 Lync トポロジにブランチサイトを追加するには、セントラルサイトで次の手順を実行します。

<div>

## <a name="to-add-branch-sites-to-your-topology"></a>トポロジにブランチサイトを追加するには

1.  [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server**]、[ **lync server Topology Builder**] の順にクリックします。

2.  コンソールツリーで、セントラルサイトを展開し、[**ブランチサイト**] を右クリックして、[**新しいブランチサイト**] をクリックします。

3.  [**新しい分岐サイトの定義**] ダイアログボックスで、[**名前**] をクリックし、ブランチサイトの名前を入力します。

4.  省略[**説明**] をクリックし、ブランチサイトにわかりやすい説明を入力します。

5.  [ **次へ**] をクリックします。

6.  省略[次の**新しいブランチサイトの定義**] ダイアログボックスで、次のいずれかの操作を行います。
    
      - [**市区町村**] をクリックし、ブランチサイトが配置されている都市の名前を入力します。
    
      - [**状態/地域**] をクリックして、ブランチサイトが配置されている状態または地域の名前を入力します。
    
      - [**国コード**] をクリックし、ブランチサイトが配置されている国/地域の2桁の通話コードを入力します。

7.  [**次へ**] をクリックし、次のいずれかの操作を行います。
    
      - このサイトで Survivable Branch アプライアンスまたはサーバーを使用している場合は、[**このウィザードを閉じるときに新しい Survivable ウィザードを開く**] チェックボックスがオンになっていることを確認し、[**完了**] をクリックして、表示されたウィザードの指示に従います。 ウィザード項目の詳細について[は、「Lync Server 2013 で Survivable Branch Appliance または Server を定義する](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)」を参照してください。
    
      - このサイトで Survivable Branch アプライアンスまたはサーバーを使っていない場合は、[**このウィザードを終了するときに、新しい Survivable ウィザードを開く**] チェックボックスをオフにして、[**完了**] をクリックします。

8.  トポロジに追加する各ブランチサイトについて、前の手順を繰り返します。

**次のステップ:**

Survivable ブランチのアプライアンスまたはサーバーの場合: [Lync Server 2013 で Survivable Branch Appliance または Server を定義する](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)

回復不能な PSTN 接続の場合: [Lync server 2013 でブランチサイトの pstn ゲートウェイを定義](lync-server-2013-define-a-pstn-gateway-for-a-branch-site.md)する、lync server [2013 でメディアバイパスを使用してトランクを構成](lync-server-2013-configure-a-trunk-with-media-bypass.md)する、または[lync server 2013 でメディアをバイパスして構成](lync-server-2013-configure-a-trunk-without-media-bypass.md)する

</div>

</div>

<span> </span>

</div>

</div>

</div>

