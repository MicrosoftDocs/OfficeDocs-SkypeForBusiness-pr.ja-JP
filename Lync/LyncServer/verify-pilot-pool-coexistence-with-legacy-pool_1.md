---
title: パイロット プールとレガシ プールの共存の確認
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Verify pilot pool coexistence with legacy pool
ms:assetid: 597d0fa6-ca04-4521-b1c2-72d7f35ecd08
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204914(v=OCS.15)
ms:contentKeyID: 48184209
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f67b113a4619d90345df9858f348d663383066d7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847926"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-pilot-pool-coexistence-with-legacy-pool"></a>パイロット プールとレガシ プールの共存の確認

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-09-28_

<div>

## <a name="verify-the-pool-in-office-communications-server-2007-r2-administrative-tool"></a>Office Communications Server 2007 R2 管理ツールでプールを確認する

1.  Office Communications Server 2007 R2 管理ツールを開きます。

2.  [**フォレスト**] ノードを展開し、 **Standard Edition サーバー**または [**エンタープライズプール**] ノードを展開して、プールまたはサーバー名を展開します。

3.  Office Communications Server 2007 R2 サービスがプールで実行されていることを確認します。
    
    ![Office Communications Server 2007 R2 管理コンソール](images/JJ721906.76897b6d-f433-47d2-930d-0816fc30a3c2(OCS.15).jpg "Office Communications Server 2007 R2 管理コンソール")  

</div>

<div>

## <a name="verify-the-pilot-pool-in-lync-server-2013-control-panel"></a>Lync Server 2013 コントロールパネルでパイロットプールを確認する

1.  CsAdministrator ロールのメンバーであるユーザーアカウントから、Lync Server 2013 フロントエンドサーバーにログオンします。

2.  ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。 Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。

3.  [**トポロジ**] をクリックします。

4.  展開したサーバーがパイロットプールに存在することを確認します。
    
    ![Lync Server コントロールパネルのトポロジページ](images/JJ204914.a3d1ba5f-c1a7-45e8-b9a5-7cb07b01af8c(OCS.15).jpg "Lync Server コントロールパネルのトポロジページ")  

</div>

<div>

## <a name="verify-lync-server-2013-services-have-started"></a>Lync Server 2013 サービスが開始されたことを確認する

1.  Lync Server 2013 フロントエンドサーバーで、[**管理ツール**] グループから [**サービス**] アプレットを開きます。

2.  表示されているサービスが、次の図のリストと一致することを確認します。
    
    Lync サービスが開始されたことを![示す [サービス] ページ]Lync サービスが開始されたことを(images/JJ204914.fd35d54a-2ab6-4c09-b5e9-fd5bf10f6f51(OCS.15).jpg "示す [サービス] ページ")  

</div>

</div>

<span> </span>

</div>

</div>

</div>

