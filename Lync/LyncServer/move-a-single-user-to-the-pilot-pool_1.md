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
ms.openlocfilehash: 7320f55b88786ccf4e1a1a26c28483f3ccbd7d77
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42148676"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="move-a-single-user-to-the-pilot-pool"></a>1人のユーザーをパイロットプールに移動する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-28_

Lync Server 2013 コントロールパネルまたは Lync Server 2013 管理シェルを使用して、ユーザーを Office Communications Server 2007 R2 プールから Lync Server 2013 パイロットプールに移動することができます。 次の例では、レジストラープール列の** \<office communications server\> **は office communications server 2007 R2 プールで、これらのユーザーの6人すべてがこのプールに接続されています。 Lync Server 2013 コントロールパネルおよび Lync Server 管理シェルを使用して、ユーザーを Lync Server 2013 プールに移動するには、次の手順を使用します。

![Lync Server コントロールパネルでの OCS ユーザーの検索](images/JJ688109.d2008fd6-868b-4f26-84cf-57bb69e073d3(OCS.15).jpg "Lync Server コントロールパネルでの OCS ユーザーの検索")

<div>

## <a name="to-move-a-user-by-using-the-lync-server-2013-control-panel"></a>Lync Server 2013 コントロールパネルを使用してユーザーを移動するには

1.  RTCUniversalServerAdmins グループのメンバーであるか、CsAdministrator または CsUserAdministrator 管理者ロールのメンバーであるアカウントを使用して、フロントエンド サーバーにログオンします。

2.  [Lync Server コントロール パネル] を開きます。

3.  [**ユーザー**] をクリックします。

4.  [**ユーザー検索**] タブで、[**検索**] ボタンをクリックします。

5.  次に、[**フィルターの追加**] をクリックします。

6.  [**Office Communications Server ユーザー**] が [**True**] のフィルターを作成します。

7.  [**検索**] をクリックして、従来の Office Communications Server 2007 R2 ユーザーを検索します。
    
    ![Lync Server コントロールパネルでの OCS ユーザーの検索](images/JJ688109.09528349-7915-41e1-91b4-6ab5c12b1b38(OCS.15).jpg "Lync Server コントロールパネルでの OCS ユーザーの検索")  

8.  Lync Server 2013 プールに移動するユーザーを選択します。 この例では、Sara Davis というユーザーを移動します。

9.  [**アクション**]メニューの [**選択されたユーザーをプールに移動**] をクリックします。

10. ドロップダウンリストから、[Lync Server 2013] プールを選択します。

11. [**アクション**] をクリックし、[**選択されたユーザーをプールに移動**] をクリックします。 [**OK**] をクリックします。
    
    ![[ユーザーの移動] ダイアログでの転送先プールの設定](images/JJ688109.d7dc0759-87c5-4c23-938f-361576621504(OCS.15).jpg "[ユーザーの移動] ダイアログでの転送先プールの設定")  

12. ユーザーの [**レジストラー pool** ] 列に Lync Server 2013 プールが含まれるようになっていることを確認します。これは、ユーザーが正常に移動されたことを示します。

</div>

<div>

## <a name="to-move-a-user-by-using-the-lync-server-2013-management-shell"></a>Lync Server 2013 管理シェルを使用してユーザーを移動するには

1.  Lync Server 管理シェルを開きます。

2.  コマンドラインで、次のように入力します。
    
        Move-CsLegacyUser -Identity "David Pelton" -Target "pool02.contoso.net"

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

