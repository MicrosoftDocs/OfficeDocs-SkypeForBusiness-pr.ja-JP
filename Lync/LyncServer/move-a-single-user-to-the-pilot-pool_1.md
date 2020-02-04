---
title: 1人のユーザーをパイロットプールに移動する
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Move a single user to the pilot pool
ms:assetid: 80d5b365-f153-4c61-a148-f9e18ce6e027
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688109(v=OCS.15)
ms:contentKeyID: 49733708
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e8cb89fde2a62858c3bd9a402207f4b23fd51643
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756051"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-a-single-user-to-the-pilot-pool"></a>1人のユーザーをパイロットプールに移動する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-09-28_

Lync Server 2013 コントロールパネルまたは Lync Server 2013 Management Shell を使用して、Office Communications Server 2007 R2 プールから Lync Server 2013 パイロットプールにユーザーを移動することができます。 次の例では、[レジストラー pool] 列では、 ** \<office communications server\> **は office communications server 2007 R2 プールであり、これらのユーザーの6人はこのプールに接続されています。 Lync Server 2013 コントロールパネルと Lync Server 管理シェルを使用して、ユーザーを Lync Server 2013 プールに移動するには、次の手順を使用します。

![Lync Server コントロールパネルで OCS ユーザーを検索する](images/JJ688109.d2008fd6-868b-4f26-84cf-57bb69e073d3(OCS.15).jpg "Lync Server コントロールパネルで OCS ユーザーを検索する")

<div>

## <a name="to-move-a-user-by-using-the-lync-server-2013-control-panel"></a>Lync Server 2013 コントロールパネルを使用してユーザーを移動するには

1.  RTCUniversalServerAdmins グループ、CsAdministrator 管理者ロール、または CsUserAdministrator 管理者ロールのメンバーであるアカウントを使用して、フロントエンド サーバーにログオンします。

2.  [Lync Server コントロール パネル] を開きます。

3.  [**ユーザー**] をクリックします。

4.  [**ユーザー検索**] タブで、[**検索**] ボタンをクリックします。

5.  次に、[**フィルターの追加**] をクリックします。

6.  **Office Communications Server ユーザー**が**True**に等しいフィルターを作成します。

7.  [**検索**] をクリックして、従来の Office Communications Server 2007 R2 ユーザーを検索します。
    
    ![Lync Server コントロールパネルで OCS ユーザーを検索する](images/JJ688109.09528349-7915-41e1-91b4-6ab5c12b1b38(OCS.15).jpg "Lync Server コントロールパネルで OCS ユーザーを検索する")  

8.  Lync Server 2013 プールに移動するユーザーを選択します。 この例では、Sara Davis というユーザーを移動します。

9.  [**アクション**] メニューの [**選択されたユーザーをプールに移動**] をクリックします。

10. ドロップダウンリストから、Lync Server 2013 プールを選択します。

11. [**アクション**] をクリックし、[**選択されたユーザーをプールに移動**] をクリックします。 [**OK**] をクリックします。
    
    ![[ユーザーの移動] ダイアログで送信先プールを設定する](images/JJ688109.d7dc0759-87c5-4c23-938f-361576621504(OCS.15).jpg "[ユーザーの移動] ダイアログで送信先プールを設定する")  

12. ユーザーの**レジストラー pool**列に Lync Server 2013 プールが含まれていることを確認します。これは、ユーザーが正常に移動されたことを示します。

</div>

<div>

## <a name="to-move-a-user-by-using-the-lync-server-2013-management-shell"></a>Lync Server 2013 管理シェルを使用してユーザーを移動するには

1.  Lync Server 管理シェルを開きます。

2.  コマンドラインで、次のように入力します。
    
        Move-CsLegacyUser -Identity "David Pelton" -Target "pool02.contoso.net"

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

