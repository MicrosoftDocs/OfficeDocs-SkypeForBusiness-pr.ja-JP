---
title: トポロジへの Lync Server 2013 存続可能ブランチ アプライアンスのブランチ サイトの追加
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
ms.openlocfilehash: b4fc2dd7426006d0c8f19b38b85ba778744fff2e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735017"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="add-lync-server-2013-survivable-branch-appliance-branch-site-to-your-topology"></a>トポロジへの Lync Server 2013 存続可能ブランチ アプライアンスのブランチ サイトの追加

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-07_

Microsoft Lync Server 2013 Survivable Branch アプライアンス (SBA) は、バックアップレジストラーとして Microsoft Lync Server 2010 フロントエンドプールに関連付けることはできません。 SBA は、Microsoft Lync Server 2013 フロントエンドプールに関連付けられている必要があります。 以下の手順では、Microsoft Lync Server 2013 SBA を前提としています。 セントラルサイトでこの手順を実行します。

<div>

## <a name="to-add-branch-sites-with-microsoft-lync-server-2013-sba-to-your-topology"></a>Microsoft Lync Server 2013 SBA の分岐サイトをトポロジに追加するには

1.  トポロジビルダーを開始します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server Topology Builder**] の順にクリックします。

2.  コンソールツリーで、セントラルサイトを展開し、[**ブランチサイト**] を展開して、[**新しいブランチサイト**] をクリックします。

3.  [**新しい分岐サイトの定義**] ダイアログボックスで、[**名前**] をクリックし、新しいブランチサイトの名前を入力します。

4.  省略[**説明**] をクリックし、ブランチサイトにわかりやすい説明を入力します。

5.  [ **次へ**] をクリックします。

6.  省略[次の**新しいブランチサイトの定義**] ダイアログボックスで、次のいずれかの操作を行います。
    
      - [**市区町村**] をクリックし、ブランチサイトが配置されている都市の名前を入力します。
    
      - [**状態/地域**] をクリックして、ブランチサイトが配置されている状態または地域の名前を入力します。
    
      - [**国コード**] をクリックし、ブランチサイトが配置されている国/地域の2桁の通話コードを入力します。

7.  [**次へ**] をクリックし、次のいずれかの操作を行います。
    
      - このサイトで Survivable Branch Appliance または Survivable Branch Server を使用している場合は、[**このウィザードを閉じるときに、新しい Survivable ウィザードを開く**] チェックボックスがオンになっていることを確認してください。
    
      - このサイトで Survivable Branch Appliance または Survivable Branch Server を使っていない場合は、[**このウィザードを閉じるときに、新しい Survivable ウィザードを開く**] チェックボックスをオフにします。
    
      - [**完了**] をクリックし、表示されるウィザードの指示に従います。 ウィザード項目の詳細について[は、「Lync Server 2013 で Survivable Branch Appliance または Server を定義する](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)」を参照してください。

8.  トポロジに追加する各ブランチサイトについて、前の手順を繰り返します。

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 での存続可能ブランチ アプライアンスまたは存続可能ブランチ サーバーの定義](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)  
[Lync Server 2013 でのブランチ サイト用の PSTN ゲートウェイの定義](lync-server-2013-define-a-pstn-gateway-for-a-branch-site.md)  
[Configure a trunk with media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[Lync Server 2013 でメディアをバイパスせずにトランクを構成する](lync-server-2013-configure-a-trunk-without-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

