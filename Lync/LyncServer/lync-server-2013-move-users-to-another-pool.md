---
title: 'Lync Server 2013: ユーザーを別のプールに移動する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Move users to another pool
ms:assetid: e7b4968c-0e9d-4d56-b5f1-9edf0f7206f8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182600(v=OCS.15)
ms:contentKeyID: 48185879
ms.date: 02/09/2018
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1feda518b1a15ce5b4622659b9e5df45044bcefa
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050359"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-users-to-another-pool-in-lync-server-2013"></a>Lync Server 2013 でユーザーを別のプールに移動する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2018-02-09_

Lync Server コントロールパネルを使用して、ユーザーを特定のサーバーまたはプールに割り当てることができます。

<div>


> [!TIP]  
> Lync Server 2010 以前のバージョンを実行しているソースプールから、複雑な Active Directory 環境にある Lync Server 2013 移行先プールにある既存のユーザーをすべて移動すると、Active Directory のレプリケーションが遅くなることがあります。 これを避けるために、検索フィルターを使用して、Lync Server 2010 またはそれ以前のバージョンを実行しているプールからユーザーを移動したり、Lync Server 管理シェルを使用してユーザーをコマンドレットで移動したりすることができます。 また、フィルター機能は Lync Server 2013 ユーザーと連携して動作します。



</div>

<div>

## <a name="to-move-selected-users-to-a-different-server-or-pool"></a>選択したユーザーを別のサーバーまたはプールに移動するには

1.  CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。 Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで **[ユーザー]** をクリックします。

4.  [**ユーザーの検索**] ボックスに、検索するユーザー アカウントの表示名、名、姓、セキュリティ アカウント マネージャー (SAM) のアカウント名、SIP アドレス、または回線 URI (Uniform Resource Identifier) の全部または最初の一部を入力して、[**検索**] をクリックします。

5.  表の一覧で、特定のユーザーまたは複数のユーザーを選択します。

6.  [**アクション**] メニューの [**選択したユーザーをプールに移動する**] をクリックします。

7.  [**ユーザーの移動**] の [**移動先レジストラ プール**] で、ユーザーの移動先のプールを選択します。

8.  (オプション) 移動先のサーバーまたはプールを使用できない場合は、[**強制**] チェック ボックスをオンにします。
    
    <div>
    

    > [!Caution]  
    > [<STRONG>強制</STRONG>] を選択すると、ユーザーアカウントは移動されますが、スケジュールされた会議や連絡先などの関連付けられたユーザーデータは移動されません。

    
    </div>

</div>

<div>

## <a name="to-move-all-users-from-one-server-or-pool-to-a-different-server-or-pool"></a>サーバー間またはプール間ですべてのユーザーを移動するには

1.  CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。 Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで [**ユーザー**] をクリックします。

4.  [**アクション**] メニューの [**すべてのユーザーをプールに移動する**] をクリックします。

5.  [**ユーザーの移動**] の [**移動元レジストラ プール**] で、移動するユーザー アカウントが入っているプールを選択します。

6.  [**移動先レジストラ プール**] で、ユーザーの移動先のプールを選択します。

7.  (オプション) 移動先のサーバーまたはプールを使用できない場合は、[**強制移動**] チェック ボックスをオンにします。
    
    <div>
    

    > [!Caution]  
    > [<STRONG>強制</STRONG>] を選択すると、ユーザーアカウントは移動されますが、スケジュールされた会議や連絡先などの関連付けられたユーザーデータは移動されません。

    
    </div>

</div>

<div>

## <a name="to-move-users-from-one-pool-to-a-different-pool-by-using-a-filter"></a>フィルターを使用してユーザーをプール間で移動するには

1.  CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。 Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで **[ユーザー]** をクリックします。

4.  [**ユーザー検索**] で、[**検索**] をクリックし、[**フィルターの追加**] をクリックします。

5.  検索条件で [**レジストラー プール**] を選択し、[**が次の値に等しい**] を選択して、[**現在のプールの FQDN**] を選択し、[**検索**] をクリックします。

6.  [**アクション**] メニューの [**すべてのユーザーをプールに移動**] をクリックします。
    
    <div>
    

    > [!NOTE]  
    > 既存のユーザーセットにフィルターが適用されている場合、[<STRONG>すべてのユーザーをプールに移動</STRONG>] オプションは、すべてのユーザーでは<STRONG><EM>なく、</EM></STRONG>フィルター処理されたユーザーのサブセットのコンテキストになります。

    
    </div>

7.  [**ユーザーの移動**] の [**移動元レジストラー プール**] で、移動するユーザー アカウントが入っているプールを選択します。

8.  [**移動先レジストラー プール**] で、ユーザーの移動先のプールを選択します。

9.  (オプション) 移動先のサーバーまたはプールを使用できない場合は、[**強制**] チェック ボックスをオンにします。
    
    <div>
    

    > [!Caution]  
    > [<STRONG>強制</STRONG>] を選択すると、ユーザーアカウントは移動されますが、スケジュールされた会議や連絡先などの関連付けられたユーザーデータは移動されません。

    
    </div>

</div>

<div>

## <a name="to-move-users-from-one-pool-to-another-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用してユーザーをあるプールから別のプールに移動するには

1.  Windows PowerShell コマンドの実行方法 (ローカルまたはリモート) に応じて、次のようにして、適切な Lync Server 2013 管理役割のメンバーとしてログオンする必要があります。
    
    1.  ローカルコンピューター上でコマンドを実行している場合 (たとえば、フロントエンドサーバーに直接ログオンしている場合) は、Lync Server 管理シェルがインストールされているコンピューターに、RTCUniversalServerAdmins グループのメンバーとして、または「 [Delegate setup permissions In Lync server 2013](lync-server-2013-delegate-setup-permissions.md)」に説明されている必要なユーザー権限を使用してログオンします。
    
    2.  他のコンピューターでリモートでコマンドを実行している場合 (たとえば、コンピューターにログオンして、Standard Edition フロントエンドサーバーでリモートでコマンドを実行する場合)、CsUserAdministrator または CsAdministrator に割り当てられているユーザーアカウントから。役割を使用して、内部展開の任意のコンピューターにログオンします。

2.  Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。

3.  単一のユーザーを移動するには、Move-CsUser コマンドレットを次のように使用します。
    
        Move-CsUser -Identity "Pilar Ackerman" -Target "pool01.contoso.net"
    
    この場合、移動するユーザーは Pilar Ackerman で、現在割り当てられているホーム プールから、プール pool01.contoso.net に移動します。

4.  大量のユーザーを移動するには、フィルターと **Get-CsUser** コマンドレットを使用し、ユーザーの結果セットを **Move-CsUser** に渡します。
    
        Get-CsUser -Filter {RegistrarPool -eq "CurrentPoolFqdn"} | Move-CsUser -Target "TargetPoolFQDN"
    
    **Get-CsUser** と **Move-CsUser** を組み合わせたコマンドを実行すると、たとえば、次のような結果が得られます。
    
        Get-CsUser -Filter {RegistrarPool -eq "pool02.contoso.net"} | Move-CsUser -Target "pool01.contoso.net"

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 でユーザーアカウントのプロパティを変更する](lync-server-2013-modifying-user-account-properties.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

