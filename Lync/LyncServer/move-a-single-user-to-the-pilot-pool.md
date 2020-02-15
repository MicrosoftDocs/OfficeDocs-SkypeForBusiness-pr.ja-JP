---
title: 1人のユーザーをパイロットプールに移動する
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Move a single user to the pilot pool
ms:assetid: e9de81a8-40dd-4446-81e7-a2b810eaea50
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205401(v=OCS.15)
ms:contentKeyID: 48185905
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3cce0a2110c0c40b105bf2b3d26bf4f99b901522
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034427"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-a-single-user-to-the-pilot-pool"></a>1人のユーザーをパイロットプールに移動する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-26_

Lync server 2013 コントロールパネルまたは Lync Server 2013 管理シェルを使用して、ユーザーを lync server 2010 プールから Lync Server 2013 パイロットプールに移動することができます。 次の例では、レジストラープール列の**pool01.contoso.net**は Lync Server 2010 プールで、これらのユーザーの6つすべてがこのプールに接続されています。 Lync Server 2013 コントロールパネルおよび Lync Server 管理シェルを使用して、ユーザーを Lync Server 2013 プールに移動するには、次の手順を使用します。

<div>

## <a name="to-move-a-user-by-using-the-lync-server-2013-control-panel"></a>Lync Server 2013 コントロールパネルを使用してユーザーを移動するには

**Lync Server 2013 コントロール パネル内のユーザー一覧**

![Lync Server コントロールパネル、[ユーザーの移動] ダイアログ](images/JJ721870.a2bce284-0392-4db3-9bb2-9f12699738e7(OCS.15).jpg "Lync Server コントロールパネル、[ユーザーの移動] ダイアログ")

1.  RTCUniversalServerAdmins グループ、CsAdministrator 管理者ロール、または CsUserAdministrator 管理者ロールのメンバーであるアカウントを使用して、フロントエンド サーバーにログオンします。

2.  [**Lync Server コントロール パネル**] を開きます。

3.  [**ユーザー**]、[検索]、[**ユーザー検索**] の順にクリックします。

4.  Lync Server 2013 プールに移動するユーザーを選択します。 この例では、Sara Davis というユーザーを移動します。

5.  [**アクション**]メニューの [**選択されたユーザーをプールに移動**] をクリックします。

6.  ドロップダウンリストから、[Lync Server 2013] プールを選択します。

7.  [**アクション**] をクリックし、[**選択されたユーザーをプールに移動**] をクリックします。 [**OK**] をクリックします。
    
    ![[ユーザーの移動]、[宛先レジストラープール] ダイアログボックス](images/JJ205401.8a375003-dc00-4541-b578-4d88f2010601(OCS.15).png "[ユーザーの移動]、[宛先レジストラープール] ダイアログボックス")  

8.  ユーザーの [**レジストラープール**] 列に Lync Server 2013 プールが含まれるようになっていることを確認します。これは、ユーザーが正常に移動されたことを示します。

</div>

<div>

## <a name="to-move-a-user-by-using-the-lync-server-2013-management-shell"></a>Lync Server 2013 管理シェルを使用してユーザーを移動するには

1.  Lync Server 管理シェルを開きます。

2.  コマンドラインで、次のように入力します。
    
        Move-CsUser -Identity "David Pelton" -Target "pool02.contoso.net"

3.  コマンドラインで、次のように入力します。
    
        Get-CsUser -Identity "David Pelton"

4.  **RegistrarPool** identity は、Lync Server 2013 プールを指すようになります。 この ID が存在していることにより、ユーザーが正常に移動されたことを確認できます。
    
    ![Id フィルターを使用した、CsUser コマンドレットからの出力](images/JJ205401.bc5d4672-8068-4475-b882-dbd305c801a9(OCS.15).jpg "Id フィルターを使用した、CsUser コマンドレットからの出力")  
    
    <div>
    

    > [!NOTE]  
    > <STRONG>Get-CsUser</STRONG> コマンドレットの詳細については、<STRONG>Get-Help Get-CsUser –Detailed</STRONG> を実行してください。

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

