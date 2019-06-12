---
title: 'Lync Server 2013: アーカイブポリシーをユーザーに適用する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Applying an Archiving policy to users
ms:assetid: 624a7d3e-389d-403a-97e5-f7bb17023ef3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521004(v=OCS.15)
ms:contentKeyID: 48184290
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 56bb6705187172888c9fdac33532e25a210e8246
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848837"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="applying-an-archiving-policy-to-users-in-lync-server-2013"></a>Lync Server 2013 のユーザーにアーカイブポリシーを適用する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-02-23_

ユーザーが Lync Server 2013 用に有効になっていて、Lync Server 2013 を使用しているユーザーのアーカイブ用に1つ以上のユーザーポリシーを作成している場合、これらのユーザーまたはユーザーグループに適切なポリシーを適用することで、特定のユーザーのアーカイブサポートを実装できます。 たとえば、内部通信のアーカイブをサポートするポリシーを作成する場合、ユーザーの Lync Server 2013 通信のアーカイブをサポートするために、少なくとも1人のユーザーまたはユーザーグループに適用することができます。

<div>


> [!NOTE]  
> 展開に対して Microsoft Exchange の統合を有効にしている場合、Exchange 2013 を使っているユーザーに対してアーカイブが有効になっているかどうか、およびそのメールボックスがインプレースホールドに組み込まれているかどうかを Exchange のインプレースホールドポリシーで制御します。 詳細については、展開ドキュメントで<A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Exchange Server との統合を使用する場合の「Lync server 2013 でアーカイブするためのポリシーを設定する</A>」を参照してください。<BR>アーカイブを有効にする前に、アーカイブ構成ですべての適切なオプションを指定する必要があります。 詳細については、「 <A href="lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md">Lync Server 2013 でアーカイブ構成オプションを管理</A>する」を参照してください。この操作のドキュメントでは、組織、サイト、プールについて説明します。



</div>

このトピックの手順を使用して、以前に作成したアーカイブユーザーポリシーを1つ以上のユーザーアカウントまたはユーザーグループに適用します。

<div>

## <a name="to-apply-an-archiving-user-policy-to-a-user-account"></a>ユーザーアカウントにアーカイブユーザーポリシーを適用するには

1.  CsArchivingAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。 Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。

3.  左側のナビゲーション バーで [**ユーザー**] をクリックして、構成するユーザー アカウントを検索します。

4.  検索結果一覧の表でユーザー アカウントをクリックし、[**編集**] をクリックして、[**詳細の表示**] をクリックします。

5.  [**アーカイブポリシー**] の [ **Lync Server ユーザーの編集**] で、適用するアーカイブユーザーポリシーを選択します。
    
    <div>
    

    > [!NOTE]  
    > <STRONG> &lt;自動&gt; </STRONG>設定では、既定のサーバーインストール設定が適用されます。 これらの設定はサーバーにより自動的に適用されます。

    
    </div>

6.  [**コミット**] をクリックします。

</div>

<div>

## <a name="assigning-a-per-user-archiving-policy-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用して、ユーザーごとのアーカイブポリシーを割り当てる

ユーザーごとのアーカイブポリシーは、Windows PowerShell と**Grant-CsArchivingPolicy**コマンドレットを使用して割り当てることができます。 このコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモートセッションから実行できます。 リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、「Lync Server Windows PowerShell のブログ記事」を参照してください[http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。「リモート PowerShell を使用して Microsoft Lync Server 2010 を管理する」を参照してください。

<div>

## <a name="to-assign-a-per-user-archiving-policy-to-a-single-user"></a>ユーザーごとのアーカイブポリシーを1人のユーザーに割り当てるには

  - 次のコマンドは、ユーザー単位のアーカイブ ポリシー RedmondArchivingPolicy をユーザー Ken Myer に割り当てます。
    
        Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName "RedmondArchivingPolicy"

</div>

<div>

## <a name="to-assign-a-per-user-archiving-policy-to-multiple-users"></a>ユーザーごとのアーカイブポリシーを複数のユーザーに割り当てるには

  - このコマンドを実行すると、ユーザーごとのアーカイブポリシー RedmondArchivingPolicy が、レジストラー pool atl-cs-001.litwareinc.com に所属するアカウントを持つすべてのユーザーに割り当てられます。 このコマンドで使用される Filter パラメーターの詳細については、「 [CsUser](https://docs.microsoft.com/powershell/module/skype/Get-CsUser)コマンドレットのドキュメント」を参照してください。
    
        Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.litwareinc.com"} | Grant-CsArchivingPolicy -PolicyName "RedmondArchivingPolicy"

</div>

<div>

## <a name="to-assign-a-per-user-archiving-policy"></a>ユーザーごとのアーカイブポリシーを割り当てるには

  - 次のコマンドは、Ken Myer に以前割り当てられていたユーザーごとのアーカイブポリシーを割り当て解除します。 ユーザー単位の PIN ポリシーが割り当て解除された後、Ken Myer は、グローバル ポリシー、または存在する場合は Ken Myer のローカル サイト ポリシーによって、自動的に管理されます。 サイト ポリシーは、グローバル ポリシーよりも優先されます。
    
        Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName $Null

</div>

詳細については、「 [Grant-CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsArchivingPolicy)コマンドレットのドキュメント」を参照してください。

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 での内部および外部通信のアーカイブの管理](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md)  
[Lync Server 2013 でのユーザーごとのポリシーの割り当て](lync-server-2013-assigning-per-user-policies.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

