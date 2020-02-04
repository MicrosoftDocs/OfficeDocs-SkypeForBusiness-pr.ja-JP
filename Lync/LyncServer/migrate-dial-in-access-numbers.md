---
title: ダイヤルイン アクセス番号の移行
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
ms.openlocfilehash: 0638ae76a9aa1108b11c1d1ff98fdd3eef08c938
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762945"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-dial-in-access-numbers"></a>ダイヤルイン アクセス番号の移行

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-19_

Lync Server 2010 から Lync Server 2013 にダイヤルインアクセス番号を移行するには、 **Move-CsApplicationEndpoint**コマンドレットを実行して、連絡先オブジェクトを移行する必要があります。 Lync server 2010 および Lync Server 2013 の共存期間中、Lync Server 2013 で作成したダイヤルインアクセス番号は、このセクションで説明するように、Lync Server 2010 で作成したダイヤルインアクセス番号と同じように動作します。

Lync server 2010 で作成したが、Lync Server 2013 に移動した、または Lync server 2013 で作成したダイヤルインアクセス番号は、移行中または移行後に次のような特性を持つことになります。

  - Office Communications Server 2007 R2 会議の出席依頼とダイヤルインアクセス番号のページには表示されません。

  - Lync Server 2010 会議の出席依頼とダイヤルインアクセス番号のページに表示されます。

  - Lync Server 2013 会議の出席依頼とダイヤルインアクセス番号のページに表示されます。

  - Office Communications Server 2007 R2 管理ツールでは、表示または変更できません。

  - Lync Server 2010 コントロールパネルと Lync Server 2010 Management Shell で表示および変更できます。

  - Lync Server 2013 コントロールパネルと Lync Server 2013 Management Shell で表示および変更できます。

  - Priority パラメーターを指定して CsDialinConferencingAccessNumber コマンドレットを使用して、地域内で再シーケンスできます。

Lync server 2010 プールを廃止する前に、Lync Server 2010 プールを参照するダイヤルインアクセス番号の移行を完了する必要があります。 次の手順で説明するように、ダイヤルインアクセス番号の移行が完了していない場合は、アクセス番号への着信通話が失敗します。

<div>


> [!IMPORTANT]  
> Lync Server 2010 プールの使用を停止する前に、この手順を実行する必要があります。



</div>

<div>


> [!NOTE]  
> 短時間のサービス停止が発生した場合に備えて、ネットワーク使用量が少ない場合は、ダイヤルインアクセス番号を移動することをお勧めします。



</div>

**ダイヤルインアクセス番号を特定して移動するには**

1.  Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。

2.  Lync Server 2013 でホストされているプールにダイヤルインアクセス番号を移動するには、コマンドラインで次を実行します。
    
        Move-CsApplicationEndpoint -Identity <SIP URI of the access number to be moved> -Target <FQDN of the pool to which the access number is moving>

3.  [Lync Server コントロール パネル] を開きます。

4.  左側のナビゲーション バーで [**会議**] をクリックします。

5.  [**ダイヤルインアクセス番号**] タブをクリックします。

6.  移行元の Lync Server 2010 プールのダイヤルインアクセス番号が残っていないことを確認します。
    
    <div>
    

    > [!NOTE]  
    > すべてのダイヤルインアクセス番号が Lync Server 2013 プールをポイントしている場合は、Lync Server 2010 プールの使用を停止することができます。

    
    </div>

**Lync Server コントロールパネルを使用して、ダイヤルインアクセス番号の移行を確認する**

1.  **Csuseradministrator**ロールまたは**csadministrator**ロールに割り当てられているユーザーアカウントから、社内展開の任意のコンピューターにログオンします。

2.  [Lync Server コントロール パネル] を開きます。

3.  左側のナビゲーション バーで [**会議**] をクリックします。

4.  [**ダイヤルインアクセス番号**] タブをクリックします。

5.  すべてのダイヤルインアクセス番号が、Lync Server 2013 でホストされているプールに移行されていることを確認します。

**Lync Server 管理シェルを使用して、ダイヤルインアクセス番号の移行を確認する**

1.  Lync Server 管理シェルを開きます。

2.  移行されたダイヤルイン会議アクセス番号をすべて返すには、コマンドラインで次を実行します。
    
        Get-CsDialInConferencingAccessNumber -Filter {Pool -eq "<FQDN of the pool to which the access number is moved>"}

3.  すべてのダイヤルインアクセス番号が、Lync Server 2013 でホストされているプールに移行されていることを確認します。

</div>

<span> </span>

</div>

</div>

</div>

