---
title: 'Lync Server 2013: Lync が有効なユーザーに対する外部ユーザー アクセス ポリシーの割り当て'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Assign an external user access policy to a Lync enabled user
ms:assetid: 736fcaad-9f95-4896-b767-e199d86a00a4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398551(v=OCS.15)
ms:contentKeyID: 48184483
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ec487f8aacdc26f910f30a0864ecead1fdb1a745
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840989"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="assign-an-external-user-access-policy-to-a-lync-enabled-user-in-lync-server-2013"></a>Lync Server 2013 での Lync が有効なユーザーに対する外部ユーザー アクセス ポリシーの割り当て

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-02-22_

ユーザーが Lync Server 用に有効になっている場合は、特定のユーザーに適切なポリシーを適用して、Lync Server のコントロールパネルで SIP フェデレーション、XMPP フェデレーション、リモートユーザーアクセス、およびパブリックインスタントメッセージング (IM) 接続を構成できます。 たとえば、リモートユーザーアクセスをサポートするポリシーを作成した場合、ユーザーがリモートの場所から Lync Server に接続し、リモートの場所から内部ユーザーと共同作業する前に、ユーザーにそのポリシーを適用する必要があります。

<div>


> [!NOTE]  
> 外部ユーザーのアクセスをサポートするには、サポートする外部ユーザーアクセスの種類ごとにサポートを有効にし、その使用を制御するために適切なポリシーとその他のオプションを構成する必要があります。 詳細については、「展開ドキュメントの<A href="lync-server-2013-configuring-support-for-external-user-access.md">Lync server 2013 での外部ユーザーアクセスのサポートの構成</A>」または「操作のドキュメントで<A href="lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md">lync server 2013 へのフェデレーションと外部アクセスを管理する</A>」を参照してください。



</div>

このトピックの手順を使用して、以前に作成した外部ユーザーアクセスポリシーを1つ以上のユーザーアカウントに適用します。

<div>

## <a name="to-apply-an-external-user-policy-to-a-user-account"></a>ユーザーアカウントに外部ユーザーポリシーを適用するには

1.  CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。 Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。

3.  左側のナビゲーション バーで [**ユーザー**] をクリックし、構成するユーザー アカウントを検索します。

4.  検索結果一覧の表でユーザー アカウントをクリックし、[**編集**] をクリックして、[**詳細の表示**] をクリックします。

5.  [**外部アクセスポリシー**] の [ **Lync Server ユーザーの編集**] で、適用するユーザーポリシーを選択します。
    
    <div>
    

    > [!NOTE]  
    > <STRONG> &lt;自動&gt; </STRONG>設定では、既定のサーバーまたはグローバルポリシーの設定が適用されます。

    
    </div>

</div>

<div>

## <a name="assigning-per-user-external-access-policies-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用して、ユーザーごとの外部アクセスポリシーを割り当てる

ユーザーごとの外部アクセスポリシーは、Windows PowerShell と Grant-CsExternalAccessPolicy コマンドレットを使用して割り当てることができます。 このコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモートセッションから実行できます。 リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、「Lync Server Windows PowerShell のブログ記事」を参照してください[http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。「リモート PowerShell を使用して Microsoft Lync Server 2010 を管理する」を参照してください。

<div>

## <a name="to-assign-a-per-user-external-access-policy-to-a-single-user"></a>ユーザーごとの外部アクセスポリシーを1人のユーザーに割り当てるには

  - このコマンドを実行すると、ユーザーごとの外部アクセスポリシー RedmondExternalAccessPolicy が Ken Myer に割り当てられます。
    
        Grant-CsExternalAccessPolicy -Identity "Ken Myer" -PolicyName "RedmondExternalAccessPolicy"

</div>

<div>

## <a name="to-assign-a-per-user-external-access-policy-to-multiple-users"></a>ユーザーごとの外部アクセスポリシーを複数のユーザーに割り当てるには

  - このコマンドによって、Active Directory の米国 OU にアカウントを持つすべてのユーザーに、ユーザーごとの外部アクセスポリシー USAExternalAccessPolicy が割り当てられます。 このコマンドで使用される OU パラメーターの詳細については、「[ユーザーの取得](https://docs.microsoft.com/powershell/module/skype/Get-CsUser)」コマンドレットのドキュメントを参照してください。
    
        Get-CsUser -OU "ou=UnitedStates,dc=litwareinc,dc=com" | Grant-CsExternalAccessPolicy -PolicyName "USAExternalAccessPolicy"

</div>

<div>

## <a name="to-unassign-a-per-user-external-access-policy"></a>ユーザーごとの外部アクセスポリシーを割り当て解除するには

  - このコマンドは、前に Ken Myer に割り当てられているユーザーごとの外部アクセスポリシーを割り当て解除します。 ユーザー単位の PIN ポリシーが割り当て解除された後、Ken Myer は、グローバル ポリシー、または存在する場合は Ken Myer のローカル サイト ポリシーによって、自動的に管理されます。 サイト ポリシーは、グローバル ポリシーよりも優先されます。
    
        Grant-CsExternalAccessPolicy -Identity "Ken Myer" -PolicyName $Null

</div>

詳細については、「 [Grant-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy)コマンドレットのヘルプトピックを参照してください。

</div>

</div>

<span> </span>

</div>

</div>

</div>

