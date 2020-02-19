---
title: 'Lync Server 2013: Lync が有効なユーザーへの外部ユーザーアクセスポリシーの割り当て'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign an external user access policy to a Lync enabled user
ms:assetid: 736fcaad-9f95-4896-b767-e199d86a00a4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398551(v=OCS.15)
ms:contentKeyID: 48184483
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 28d8dffe68b9eb1e4c21bc937075f5fcb5ff23f5
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134383"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="assign-an-external-user-access-policy-to-a-lync-enabled-user-in-lync-server-2013"></a>Lync Server 2013 での Lync が有効なユーザーへの外部ユーザーアクセスポリシーの割り当て

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-22_

ユーザーが Lync Server に対して有効になっている場合は、特定のユーザーに適切なポリシーを適用することによって、Lync Server コントロールパネルで SIP フェデレーション、XMPP フェデレーション、リモートユーザーアクセス、およびパブリックインスタントメッセージング (IM) 接続を構成できます。 たとえば、リモートユーザーアクセスをサポートするポリシーを作成した場合、ユーザーがリモートの場所から Lync Server に接続して、リモートの場所から内部ユーザーと共同で作業できるようにするには、そのポリシーをユーザーに適用する必要があります。

<div>


> [!NOTE]  
> 外部ユーザー アクセスをサポートするには、サポートする各種類の外部ユーザー アクセスのサポートを有効にし、適切なポリシーとその他の使用制御オプションを構成する必要があります。 詳細については、「展開」のドキュメントの「 <A href="lync-server-2013-configuring-support-for-external-user-access.md">Lync server 2013 での外部ユーザーアクセスのサポートの構成</A>」または「操作」のドキュメントの「 <A href="lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md">lync server 2013 へのフェデレーションと外部アクセスの管理</A>」を参照してください。



</div>

このトピックの手順を使用して、あらかじめ作成した外部ユーザー アクセス ポリシーを、1 つまたは複数のユーザー アカウントに適用します。

<div>

## <a name="to-apply-an-external-user-policy-to-a-user-account"></a>外部ユーザー ポリシーをユーザー アカウントに適用するには

1.  CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。 Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで [**ユーザー**] をクリックし、構成するユーザー アカウントを検索します。

4.  検索結果一覧の表でユーザー アカウントをクリックし、[**編集**] をクリックして、[**詳細の表示**] をクリックします。

5.  [**Lync Server ユーザーの編集**] の [**外部アクセス ポリシー**] で、適用するユーザー ポリシーを選択します。
    
    <div>
    

    > [!NOTE]  
    > [ <STRONG> &lt;自動&gt; </STRONG> ] 設定では、既定のサーバーまたはグローバルポリシーの設定が適用されます。

    
    </div>

</div>

<div>

## <a name="assigning-per-user-external-access-policies-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用したユーザー単位の外部アクセスポリシーの割り当て

ユーザー単位の外部アクセスポリシーは、Windows PowerShell と Get-csexternalaccesspolicy コマンドレットを使用して割り当てることができます。 このコマンドレットは、Lync Server 2013 管理シェルまたは Windows PowerShell のリモート セッションから実行できます。 リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を[https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)で参照してください。

<div>

## <a name="to-assign-a-per-user-external-access-policy-to-a-single-user"></a>ユーザーごとの外部アクセスポリシーを単一のユーザーに割り当てるには

  - 次のコマンドは、ユーザーごとの外部アクセス ポリシー RedmondExternalAccessPolicy をユーザー Ken Myer に割り当てます。
    
        Grant-CsExternalAccessPolicy -Identity "Ken Myer" -PolicyName "RedmondExternalAccessPolicy"

</div>

<div>

## <a name="to-assign-a-per-user-external-access-policy-to-multiple-users"></a>ユーザーごとの外部アクセスポリシーを複数のユーザーに割り当てるには

  - 次のコマンドは、ユーザーごとの外部アクセス ポリシー USAExternalAccessPolicy を、Active Directory の UnitedStates OU にアカウントを持っているすべてのユーザーに割り当てます。 このコマンドで使用されている OU パラメーターの詳細については、「 [Get-help user](https://docs.microsoft.com/powershell/module/skype/Get-CsUser)コマンドレットのドキュメント」を参照してください。
    
        Get-CsUser -OU "ou=UnitedStates,dc=litwareinc,dc=com" | Grant-CsExternalAccessPolicy -PolicyName "USAExternalAccessPolicy"

</div>

<div>

## <a name="to-unassign-a-per-user-external-access-policy"></a>ユーザーごとの外部アクセスポリシーの割り当てを解除するには

  - 次のコマンドは、以前に Ken Myer に割り当てたユーザーごとの外部アクセス ポリシーのすべての割り当てを解除します。ユーザーごとのポリシーの割り当てを解除された後の Ken Myer は、グローバル ポリシーまたは存在する場合はローカル サイト ポリシーを使用して、自動的に管理されます。サイト ポリシーの方がグローバル ポリシーより優先されます。
    
        Grant-CsExternalAccessPolicy -Identity "Ken Myer" -PolicyName $Null

</div>

詳細については、 [get-csexternalaccesspolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy)コマンドレットのヘルプトピックを参照してください。

</div>

</div>

<span> </span>

</div>

</div>

</div>

