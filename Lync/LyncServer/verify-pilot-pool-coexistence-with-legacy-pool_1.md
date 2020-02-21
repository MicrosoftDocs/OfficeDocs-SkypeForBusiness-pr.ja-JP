---
title: パイロットプールとレガシプールの共存を確認する
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Verify pilot pool coexistence with legacy pool
ms:assetid: 597d0fa6-ca04-4521-b1c2-72d7f35ecd08
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204914(v=OCS.15)
ms:contentKeyID: 48184209
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4952640d6f6e938b460855118163d98e001f6a77
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42188860"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="verify-pilot-pool-coexistence-with-legacy-pool"></a>パイロットプールとレガシプールの共存を確認する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-28_

<div>

## <a name="verify-the-pool-in-office-communications-server-2007-r2-administrative-tool"></a>Office Communications Server 2007 R2 管理ツールでプールを確認する

1.  Office Communications Server 2007 R2 管理ツールを開きます。

2.  [**フォレスト**] ノード、[**Standard Edition サーバー**] ノードまたは [**エンタープライズ プール**] ノード、プールまたはサーバー名の順に展開します。

3.  Office Communications Server 2007 R2 サービスがプール上で実行されていることを確認します。
    
    ![Office Communications Server 2007 R2 管理コンソール](images/JJ721906.76897b6d-f433-47d2-930d-0816fc30a3c2(OCS.15).jpg "Office Communications Server 2007 R2 管理コンソール")  

</div>

<div>

## <a name="verify-the-pilot-pool-in-lync-server-2013-control-panel"></a>Lync Server 2013 コントロールパネルでパイロットプールを確認する

1.  CsAdministrator の役割のメンバーであるユーザーアカウントから、Lync Server 2013 フロントエンドサーバーにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。 Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  [**トポロジ**] をクリックします。

4.  展開したサーバーがパイロット プール内に存在することを確認します。
    
    ![Lync Server コントロールパネルのトポロジページ](images/JJ204914.a3d1ba5f-c1a7-45e8-b9a5-7cb07b01af8c(OCS.15).jpg "Lync Server コントロールパネルのトポロジページ")  

</div>

<div>

## <a name="verify-lync-server-2013-services-have-started"></a>Lync Server 2013 サービスが開始していることを確認する

1.  Lync Server 2013 のフロントエンドサーバーで、[**管理ツール**] グループから [**サービス**] アプレットを開きます。

2.  一覧表示されるサービスが次の図の一覧と一致することを確認します。
    
    ![Lync services が開始されたサービスページ](images/JJ204914.fd35d54a-2ab6-4c09-b5e9-fd5bf10f6f51(OCS.15).jpg "Lync services が開始されたサービスページ")  

</div>

</div>

<span> </span>

</div>

</div>

</div>

