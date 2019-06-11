---
title: 1人のユーザーをパイロットプールに移動する
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Move a single user to the pilot pool
ms:assetid: e9de81a8-40dd-4446-81e7-a2b810eaea50
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205401(v=OCS.15)
ms:contentKeyID: 48185905
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e9ee58a49afaa9c1e57689b6a3a87fac1a6a4502
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848041"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-a-single-user-to-the-pilot-pool"></a>1人のユーザーをパイロットプールに移動する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-09-26_

Lync server 2013 コントロールパネルまたは Lync Server 2013 Management Shell を使って、ユーザーを Lync Server 2010 プールから Lync Server 2013 パイロットプールに移動することができます。 次の例では、[レジストラー pool] 列では、 **pool01.contoso.net**は Lync Server 2010 プールであり、これらの6人のユーザーはこのプールに接続されています。 Lync Server 2013 コントロールパネルと Lync Server 管理シェルを使用して、ユーザーを Lync Server 2013 プールに移動するには、次の手順を使用します。

<div>

## <a name="to-move-a-user-by-using-the-lync-server-2013-control-panel"></a>Lync Server 2013 コントロールパネルを使用してユーザーを移動するには

**Lync Server 2013 コントロールパネルに表示されたユーザーのリスト**

![Lync Server コントロールパネルの [ユーザーの移動] ダイアログ](images/JJ721870.a2bce284-0392-4db3-9bb2-9f12699738e7(OCS.15).jpg "Lync Server コントロールパネルの [ユーザーの移動] ダイアログ")

1.  RTCUniversalServerAdmins グループ、CsAdministrator 管理者ロール、または CsUserAdministrator 管理者ロールのメンバーであるアカウントを使用して、フロントエンド サーバーにログオンします。

2.  [**Lync Server コントロール パネル**] を開きます。

3.  [**ユーザー**]、[検索] の順にクリックして、[**ユーザー検索**] をクリックします。

4.  Lync Server 2013 プールに移動するユーザーを選択します。 この例では、Sara Davis というユーザーを移動します。

5.  [**アクション**] メニューの [**選択されたユーザーをプールに移動**] をクリックします。

6.  ドロップダウンリストから、Lync Server 2013 プールを選択します。

7.  [**アクション**] をクリックし、[**選択されたユーザーをプールに移動**] をクリックします。 [**OK**] をクリックします。
    
    ![[ユーザーの移動]、[宛先レジストラー pool] ダイアログボックス](images/JJ205401.8a375003-dc00-4541-b578-4d88f2010601(OCS.15).png "[ユーザーの移動]、[宛先レジストラー pool] ダイアログボックス")  

8.  ユーザーの**レジストラー pool**列に Lync Server 2013 プールが含まれていることを確認します。これは、ユーザーが正常に移動されたことを示します。

</div>

<div>

## <a name="to-move-a-user-by-using-the-lync-server-2013-management-shell"></a>Lync Server 2013 管理シェルを使用してユーザーを移動するには

1.  Lync Server 管理シェルを開きます。

2.  コマンドラインで、次のように入力します。
    
        Move-CsUser -Identity "David Pelton" -Target "pool02.contoso.net"

3.  次に、コマンドラインで次のように入力します。
    
        Get-CsUser -Identity "David Pelton"

4.  **RegistrarPool** Id が Lync Server 2013 プールを指すようになりました。 この id の存在は、ユーザーが正常に移動されたことを確認します。
    
    ![Id フィルターを使用したユーザーのアクセスコマンドレットの出力](images/JJ205401.bc5d4672-8068-4475-b882-dbd305c801a9(OCS.15).jpg "Id フィルターを使用したユーザーのアクセスコマンドレットの出力")  
    
    <div>
    

    > [!NOTE]  
    > <STRONG>ユーザーの取得</STRONG>コマンドレットの詳細については、次を実行してください: <STRONG>get-ヘルプの取得-Csuser –詳細</STRONG>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

