---
title: 'Lync Server 2013: ユーザーへのアーカイブポリシーの適用'
description: 'Lync Server 2013: ユーザーへのアーカイブポリシーの適用。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Applying an Archiving policy to users
ms:assetid: 624a7d3e-389d-403a-97e5-f7bb17023ef3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521004(v=OCS.15)
ms:contentKeyID: 48184290
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 54b82a68a75da7b389167097d8b08358cf680e1c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544973"
---
# <a name="applying-an-archiving-policy-to-users-in-lync-server-2013"></a>Lync Server 2013 でのユーザーへのアーカイブポリシーの適用

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-23_

ユーザーが Lync Server 2013 に対して有効になっており、Lync Server 2013 に所属するユーザーに対してアーカイブ用のユーザーポリシーを1つ以上作成している場合は、それらのユーザーまたはユーザーグループに適切なポリシーを適用することによって、特定のユーザーに対してアーカイブサポートを実装できます。 たとえば、内部通信のアーカイブをサポートするポリシーを作成する場合、ユーザーの Lync Server 2013 通信のアーカイブをサポートするために、少なくとも1つのユーザーまたはユーザーグループに適用することができます。

<div>


> [!NOTE]  
> 展開に対して Microsoft Exchange 統合を有効にした場合、Exchange In-Place 保持ポリシーは、Exchange 2013 に所属しているユーザーに対してアーカイブが有効になっているかどうかを制御し、メールボックスを In-Place 保持に配置するかどうかを制御します。 詳細については、「展開」のドキュメントの「 <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Setting up policies For Exchange server integration using The Lync server 2013</A> 」を参照してください。<BR>アーカイブを有効にするには、その前にアーカイブ構成で適切なオプションをすべて指定する必要があります。 詳細については、「操作」のドキュメントの「 <A href="lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md">Lync Server 2013 での組織、サイト、およびプールのアーカイブ構成オプションの管理</A> 」を参照してください。



</div>

このトピックの手順を使用して、作成済みのアーカイブ ユーザー ポリシーを、1 つまたは複数のユーザー アカウントまたはユーザー グループに適用します。

<div>

## <a name="to-apply-an-archiving-user-policy-to-a-user-account"></a>アーカイブ ユーザー ポリシーをユーザー アカウントに適用するには

1.  CsArchivingAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。 Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで [**ユーザー**] をクリックし、構成するユーザー アカウントを検索します。

4.  検索結果一覧の表でユーザー アカウントをクリックし、[**編集**] をクリックして、[**詳細の表示**] をクリックします。

5.  [ **Lync Server ユーザーの編集** ] の [ **アーカイブポリシー**] で、適用するアーカイブユーザーポリシーを選択します。
    
    <div>
    

    > [!NOTE]  
    > [ <STRONG> &lt; 自動 &gt; </STRONG> ] 設定では、既定のサーバーインストールの設定が適用されます。 これらの設定はサーバーによって自動的に適用されます。

    
    </div>

6.  [**確定**] をクリックします。

</div>

<div>

## <a name="assigning-a-per-user-archiving-policy-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用した Per-User アーカイブポリシーの割り当て

ユーザー単位のアーカイブポリシーは、Windows PowerShell と **grant-csarchivingpolicy** コマンドレットを使用して割り当てることができます。 このコマンドレットは、Lync Server 2013 管理シェルまたは Windows PowerShell のリモートセッションから実行できます。 リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を[https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)で参照してください。

<div>

## <a name="to-assign-a-per-user-archiving-policy-to-a-single-user"></a>ユーザー単位のアーカイブポリシーを単一のユーザーに割り当てるには

  - 次のコマンドは、ユーザー単位のアーカイブ ポリシーである RedmondArchivingPolicy をユーザー Ken Myer に割り当てます。
    
        Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName "RedmondArchivingPolicy"

</div>

<div>

## <a name="to-assign-a-per-user-archiving-policy-to-multiple-users"></a>ユーザー単位のアーカイブポリシーを複数のユーザーに割り当てるには

  - 次のコマンドは、ユーザーごとのアーカイブ ポリシーである RedmondArchivingPolicy を、レジストラー プール atl-cs-001.litwareinc.com に所属するアカウントを持つすべてのユーザーに割り当てます。 このコマンドで使用される Filter パラメーターの詳細については、「 [Get-help user](https://docs.microsoft.com/powershell/module/skype/Get-CsUser) コマンドレットのドキュメント」を参照してください。
    
        Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.litwareinc.com"} | Grant-CsArchivingPolicy -PolicyName "RedmondArchivingPolicy"

</div>

<div>

## <a name="to-assign-a-per-user-archiving-policy"></a>ユーザー単位のアーカイブポリシーを割り当てるには

  - 次のコマンドは、Ken Myer に割り当て済みのユーザーごとのアーカイブポリシーの割り当てを解除します。ユーザーごとのポリシーの割り当てが解除された後、Ken Myer は、グローバル ポリシー (存在する場合はローカル サイト ポリシー) を使用して自動的に管理されます。サイト ポリシーがグローバル ポリシーに優先します。
    
        Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName $Null

</div>

詳細については、 [grant-csarchivingpolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsArchivingPolicy) コマンドレットのドキュメントを参照してください。

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 での内部および外部通信のアーカイブの管理](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md)  
[Lync Server 2013 でのユーザー単位のポリシーの割り当て](lync-server-2013-assigning-per-user-policies.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

