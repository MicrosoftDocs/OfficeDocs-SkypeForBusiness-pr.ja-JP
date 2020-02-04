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
ms.openlocfilehash: 7dffa2e7651e056d9dc14b1e261134783d0fd193
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756741"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-users-to-another-pool-in-lync-server-2013"></a>Lync Server 2013 でユーザーを別のプールに移動する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2018-02-09_

Lync Server コントロールパネルを使用して、特定のサーバーまたはプールにユーザーを割り当てることができます。

<div>


> [!TIP]  
> Lync Server 2010 以前を実行しているソースプールの既存のすべてのユーザーを、複雑な Active Directory 環境の Lync Server 2013 移行先プールに移動すると、Active Directory の複製が遅くなることがあります。 これを回避するには、検索フィルターを使用して、Lync Server 2010 以前を実行しているプールからユーザーを移動するか、Lync Server 管理シェルを使用してユーザーをコマンドレットで移動できます。 また、フィルター機能は、Lync Server 2013 ユーザーと連携して動作します。



</div>

<div>

## <a name="to-move-selected-users-to-a-different-server-or-pool"></a>選択したユーザーを別のサーバーまたはプールに移動するには

1.  CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。 Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。

3.  左側のナビゲーション バーで [**ユーザー**] をクリックします。

4.  [**ユーザーの検索**] ボックスに、表示名、名、姓、セキュリティアカウントマネージャー (SAM) アカウント名、SIP アドレス、または必要なユーザーアカウントの行の Uniform resource IDENTIFIER (URI) の最初の部分を入力し、[**検索**] をクリックします。

5.  表で、リスト内の特定のユーザー (複数可) を選びます。

6.  [**操作**] メニューの [**選択したユーザーをプールに移動**] をクリックします。

7.  [**ユーザーの移動**] で、ユーザーを移動**先のレジストラープール**に移動するプールを選択します。

8.  省略移動先のサーバーまたはプールが利用できない場合は、[**強制**] チェックボックスをオンにします。
    
    <div>
    

    > [!Caution]  
    > [<STRONG>強制</STRONG>] を選択すると、ユーザーアカウントは移動されますが、スケジュールされた会議や連絡先など、関連付けられたユーザーデータは移動されません。

    
    </div>

</div>

<div>

## <a name="to-move-all-users-from-one-server-or-pool-to-a-different-server-or-pool"></a>1つのサーバーまたはプールから別のサーバーまたはプールにすべてのユーザーを移動するには

1.  CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。 Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。

3.  左側のナビゲーション バーで [**ユーザー**] をクリックします。

4.  [**操作**] メニューの [**すべてのユーザーをプールに移動**] をクリックします。

5.  [**ユーザーの移動**] で、**ソースレジストラープール**内で移動するユーザーアカウントが含まれているプールを選択します。

6.  [**宛先レジスタプール**] で、ユーザーの移動先のプールを選択します。

7.  省略移動先のサーバーまたはプールが利用できない場合は、[**強制**] チェックボックスをオンにします。
    
    <div>
    

    > [!Caution]  
    > [<STRONG>強制</STRONG>] を選択すると、ユーザーアカウントは移動されますが、スケジュールされた会議や連絡先など、関連付けられたユーザーデータは移動されません。

    
    </div>

</div>

<div>

## <a name="to-move-users-from-one-pool-to-a-different-pool-by-using-a-filter"></a>フィルターを使用して1つのプールから別のプールにユーザーを移動するには

1.  CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。 Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。

3.  左側のナビゲーション バーで [**ユーザー**] をクリックします。

4.  [**ユーザー検索**] で [**検索**] をクリックし、[**フィルターの追加**] をクリックします。

5.  検索条件で、[**レジストラー Pool**]、[指定の**値に等しい**] の順に選択し、[**現在のプールの FQDN**] を選択し、[**検索**] をクリックします。

6.  [**操作**] メニューの [**すべてのユーザーをプールに移動**] をクリックします。
    
    <div>
    

    > [!NOTE]  
    > フィルターが既存のユーザーのセットに適用されている場合、[<STRONG>すべてのユーザーをプールに移動する</STRONG>] オプションは、<STRONG><EM>すべて</EM></STRONG>のユーザーに対してフィルター処理されたユーザーのサブセットのコンテキストで実行されます。

    
    </div>

7.  [**ユーザーの移動**] で、**ソースレジストラープール**内で移動するユーザーアカウントが含まれているプールを選択します。

8.  [**宛先レジストラー pool**] で、ユーザーを移動するプールを選択します。

9.  省略移動先のサーバーまたはプールが利用できない場合は、[**強制**] チェックボックスをオンにします。
    
    <div>
    

    > [!Caution]  
    > [<STRONG>強制</STRONG>] を選択すると、ユーザーアカウントは移動されますが、スケジュールされた会議や連絡先など、関連付けられたユーザーデータは移動されません。

    
    </div>

</div>

<div>

## <a name="to-move-users-from-one-pool-to-another-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用してユーザーを別のプールに移動するには

1.  Windows PowerShell コマンドの実行方法 (ローカルまたはリモート) に応じて、次のようにして、適切な Lync Server 2013 管理者ロールのメンバーとしてログオンする必要があります。
    
    1.  ローカルコンピューターでコマンドを実行している場合 (たとえば、フロントエンドサーバーに直接ログオンしている場合) は、lync Server 管理シェルが RTCUniversalServerAdmins グループのメンバーとしてインストールされているコンピューター、または「 [Lync server 2013 の委任セットアップの権限](lync-server-2013-delegate-setup-permissions.md)」で説明されているように、必要なユーザー権限を持つコンピューターにログオンします。
    
    2.  他のコンピューターでリモートでコマンドを実行している場合 (たとえば、コンピューターにログオンして、標準エディションのフロントエンドサーバーでコマンドをリモートで実行している場合) は、CsUserAdministrator ロールまたは CsAdministrator に割り当てられているユーザーアカウントからの操作を行います。[役割] は、社内展開の任意のコンピューターにログオンします。

2.  Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。

3.  1人のユーザーを移動するには、次のように移動-CsUser コマンドレットを使用します。
    
        Move-CsUser -Identity "Pilar Ackerman" -Target "pool01.contoso.net"
    
    ユーザーの移動先がユーザー Pilar Ackerman であり、ユーザーは現在割り当てられているホームプールからプールに移動されます。 pool01.contoso.net

4.  多数のユーザーを移動するには、ユーザーの**アクセス**コマンドレットを使用してフィルターを実行し、その結果セットのユーザーを**移動**するユーザーを指定します。
    
        Get-CsUser -Filter {RegistrarPool -eq "CurrentPoolFqdn"} | Move-CsUser -Target "TargetPoolFQDN"
    
    次のような操作を行うと、ユーザーと**ムーブグループ**のユーザーの組み合わせコマンドが**表示**されます。
    
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

