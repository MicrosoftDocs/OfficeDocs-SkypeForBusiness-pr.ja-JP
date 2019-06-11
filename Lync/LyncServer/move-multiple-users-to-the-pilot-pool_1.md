---
title: 複数のユーザーをパイロットプールに移動する
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Move multiple users to the pilot pool
ms:assetid: 9492797f-2a26-4773-8ad2-97cb53fa68fc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688143(v=OCS.15)
ms:contentKeyID: 49733745
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2ffc3e01df30f4a8e1b9c9b9aeca2b2013003980
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848031"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-multiple-users-to-the-pilot-pool"></a>複数のユーザーをパイロットプールに移動する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-02_

Lync Server 2013 コントロールパネルまたは Lync Server 2013 Management Shell を使用して、Office Communications Server 2007 R2 プールから Lync Server 2013 パイロットプールに複数のユーザーを移動することができます。

<div>

## <a name="to-move-multiple-users-by-using-the-lync-server-2013-control-panel"></a>Lync Server 2013 コントロールパネルを使用して複数のユーザーを移動するには

1.  [**Lync Server コントロール パネル**] を開きます。

2.  [**ユーザー検索**] タブで、[**検索**] ボタンをクリックします。

3.  次に、[**フィルターの追加**] をクリックします。

4.  **Office Communications Server ユーザー**が**True**に等しいフィルターを作成します。

5.  [**検索**] をクリックして、従来の Office Communications Server 2007 R2 ユーザーを検索します。

6.  Lync Server 2013 プールに移動する2人のユーザーを選びます。 この例では、Chen Yang sold と Claus というユーザーを移動します。
    
    ![OCS ユーザーを検索するときに表示されるユーザーリスト](images/JJ688143.76beb4fa-72e0-41ef-b96e-3553e96645c0(OCS.15).jpg "OCS ユーザーを検索するときに表示されるユーザーリスト")  

7.  [**アクション**] メニューで、[**選択したユーザーをプールに移動**] を選択します。

8.  ドロップダウンリストから、Lync Server 2013 プールを選択します。

9.  [**アクション**] をクリックし、[**選択されたユーザーをプールに移動**] をクリックします。 [OK] をクリックします。
    
    ![[ユーザーの移動]、[宛先レジストラー pool] ダイアログボックス](images/JJ205401.8a375003-dc00-4541-b578-4d88f2010601(OCS.15).png "[ユーザーの移動]、[宛先レジストラー pool] ダイアログボックス")  

10. ユーザーの**レジストラー pool**列に Lync Server 2013 プールが含まれていることを確認します。これは、ユーザーが正常に移動されたことを示します。

</div>

<div>

## <a name="to-move-multiple-users-by-using-the-lync-server-2013-management-shell"></a>Lync Server 2013 管理シェルを使用して複数のユーザーを移動するには

1.  Lync Server 2013 管理シェルを開きます。

2.  コマンドラインで、次のように入力し、移動する特定のユーザー名で**User1**と**User2**を置き換えて、**プール\_の FQDN**を移行先プールの名前で置き換えます。 この例では、ユーザーの Hao Chen と Katie ヨルダンを移動します。
    
        Get-CsUser -Filter {DisplayName -eq "User1" -or DisplayName - eq "User2"} | Move-CsLegacyUser -Target "pool_FQDN"
    
    ![従来のユーザーを移動するコマンドレットの例](images/JJ688143.57cfc28e-3df5-459f-83ef-8b0edf182a25(OCS.15).jpg "従来のユーザーを移動するコマンドレットの例")  

3.  コマンドラインで、次のように入力します。
    
        Get-CsUser -Identity "User1"

4.  これで、**レジストラープール**id が、前の手順で**プール\_の FQDN**として指定したプールをポイントするようになります。 この id の存在は、ユーザーが正常に移動されたことを確認します。 「 **User2**が移動されたことを確認する」の手順を繰り返します。
    
    ![PowerShell Get-UsUser Identity コマンドレットの出力](images/JJ205096.8ff04c67-37a0-4156-bfbc-28f9f7b137c8(OCS.15).jpg "PowerShell Get-UsUser Identity コマンドレットの出力")  

</div>

<div>

## <a name="to-move-all-users-at-the-same-time-by-using-the-lync-server-2013-management-shell"></a>Lync Server 2013 管理シェルを使用してすべてのユーザーを同時に移動するには

この例では、すべてのユーザーが Office Communications Server 2007 R2 pool (pool01.contoso.net) に戻されています。 Lync Server 2013 管理シェルを使用して、すべてのユーザーを Lync Server 2013 プール (pool02.contoso.net) に同時に移行します。

1.  **Lync Server 2013 管理シェル**を開きます。

2.  コマンドラインで、次のように入力します。
    
        Get-CsUser -OnOfficeCommunicationServer | Move-CsLegacyUser -Target "pool_FQDN"
    
    ![プール内のすべてのレガシユーザーを移動するコマンドレットの例](images/JJ688143.e6a2d578-296e-476c-bd45-d757917ea853(OCS.15).jpg "プール内のすべてのレガシユーザーを移動するコマンドレットの例")  

3.  次に、パイロットユーザーの1人に対して、**ユーザーの取得-CsUser**を実行します。
    
        Get-CsUser -Identity "Hao Chen"

4.  各ユーザーの**レジストラープール**id は、前の手順で "プール\_FQDN" として指定したプールを指すようになりました。 この id の存在は、ユーザーが正常に移動されたことを確認します。

5.  さらに、Lync Server 2013 コントロールパネルでユーザーの一覧を表示し、[レジストラー Pool] の値が Lync Server 2013 プールを指すようになったことを確認します。
    
    ![Lync Server 2013 コントロールパネルのユーザーリスト](images/JJ205096.3f2e87a7-ec59-43c5-82cb-e770108bfb04(OCS.15).jpg "Lync Server 2013 コントロールパネルのユーザーリスト")  

</div>

</div>

<span> </span>

</div>

</div>

</div>

