---
title: ダイヤルイン アクセス番号を移行する
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrate dial-in access numbers
ms:assetid: e0dfaed2-64c7-45cb-aaa9-d6117a26625d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721909(v=OCS.15)
ms:contentKeyID: 49733843
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0a56dbb90c65bdbb4e26d289c289b6ccc9054d0e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029128"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-dial-in-access-numbers"></a>ダイヤルイン アクセス番号を移行する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-19_

Lync Server 2010 から Lync Server 2013 へのダイヤルインアクセス番号の移行では、contact オブジェクトを移行するために、 **Move-CsApplicationEndpoint**コマンドレットを実行する必要があります。 Lync server 2010 および Lync Server 2013 の共存期間の間、lync server 2013 で作成したダイヤルインアクセス番号は、このセクションで説明するように、Lync Server 2010 で作成したダイヤルインアクセス番号と同じように動作します。

Lync server 2010 で作成したが、Lync Server 2013 に移動した、または移行中または移行後に lync server 2013 で作成したダイヤルインアクセス番号は、次の特徴があります。

  - Office Communications Server 2007 R2 の会議への招待およびダイヤルインアクセス番号ページには表示されません。

  - Lync Server 2010 の会議への招待およびダイヤルインアクセス番号ページに表示されます。

  - Lync Server 2013 の会議への招待およびダイヤルインアクセス番号ページに表示されます。

  - Office Communications Server 2007 R2 管理ツールで表示または変更することはできません。

  - Lync Server 2010 コントロールパネルおよび Lync Server 2010 管理シェルで表示および変更できます。

  - Lync Server 2013 コントロールパネルおよび Lync Server 2013 管理シェルで表示および変更できます。

  - Set-CsDialinConferencingAccessNumber コマンドレットで Priority パラメーターを指定して、地域内で並べ直すことができます。

Lync server 2010 プールを使用停止にする前に、Lync Server 2010 プールをポイントするダイヤルインアクセス番号の移行を完了する必要があります。 記載されている以下の手順でダイヤルイン アクセス番号の移行を完了しないと、そのアクセス番号への着信通話が失敗します。

<div>


> [!IMPORTANT]  
> Lync Server 2010 プールを使用停止にする前に、この手順を実行する必要があります。



</div>

<div>


> [!NOTE]  
> サービスが短時間停止される場合に備えて、ネットワークの使用率が低いときに、ダイヤルイン アクセス番号を移動することをお勧めします。



</div>

**ダイヤルイン アクセス番号を識別し、移動するには**

1.  Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。

2.  各ダイヤルインアクセス番号を Lync Server 2013 でホストされているプールに移動するには、コマンドラインから次を実行します。
    
        Move-CsApplicationEndpoint -Identity <SIP URI of the access number to be moved> -Target <FQDN of the pool to which the access number is moving>

3.  [Lync Server コントロール パネル] を開きます。

4.  左側のナビゲーション バーで **[会議]** をクリックします。

5.  [**ダイヤルインアクセス番号**] タブをクリックします。

6.  移行元の Lync Server 2010 プールに対して、ダイヤルインアクセス番号が残っていないことを確認します。
    
    <div>
    

    > [!NOTE]  
    > すべてのダイヤルインアクセス番号が Lync Server 2013 プールをポイントしている場合は、Lync Server 2010 プールを使用停止にすることができます。

    
    </div>

**Lync Server コントロールパネルを使用してダイヤルインアクセス番号の移行を確認する**

1.  **Csuseradministrator**または**csadministrator**の役割に割り当てられているユーザーアカウントから、内部展開の任意のコンピューターにログオンします。

2.  [Lync Server コントロール パネル] を開きます。

3.  左側のナビゲーション バーで **[会議]** をクリックします。

4.  [**ダイヤルインアクセス番号**] タブをクリックします。

5.  すべてのダイヤルインアクセス番号が、Lync Server 2013 でホストされているプールに移行されることを確認します。

**Lync Server 管理シェルを使用してダイヤルインアクセス番号の移行を確認する**

1.  Lync Server 管理シェルを開きます。

2.  移行されたすべてのダイヤルイン会議アクセス番号を戻すには、コマンドラインで次のコマンドを実行します。
    
        Get-CsDialInConferencingAccessNumber -Filter {Pool -eq "<FQDN of the pool to which the access number is moved>"}

3.  すべてのダイヤルインアクセス番号が、Lync Server 2013 でホストされているプールに移行されることを確認します。

</div>

<span> </span>

</div>

</div>

</div>

