---
title: 'Lync Server 2013: ユーザー単位のダイヤルプランポリシーの割り当て'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a per-user dial plan policy
ms:assetid: 9fea861f-7770-4cae-9b1f-2a960595bfc9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688156(v=OCS.15)
ms:contentKeyID: 49733760
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8bd4d46e2cd41c972258a84a1e8fb34549dc8b4e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134443"
---
# <a name="assign-a-per-user-dial-plan-policy-in-lync-server-2013"></a>Lync Server 2013 でのユーザー単位のダイヤルプランポリシーの割り当て

 


エンタープライズ Voip またはダイヤルイン会議のユーザーのいずれかのユーザーアカウント構成を完了するには、ユーザーにダイヤルプランを割り当てる必要があります。 既存のユーザーごとのダイヤルプランが明示的に割り当てられていない場合、ユーザーアカウントはグローバルダイヤルプランを自動的に使用するか、存在する場合はサイトレベルのダイヤルプランを使用します。 エンタープライズ Voip が有効になっているすべてのユーザーに対してグローバルまたはサイトのダイヤルプランを使用する場合は、このセクションを省略できます。

## <a name="to-assign-a-dial-plan-by-using-the-lync-server-2013-control-panel"></a>Lync Server 2013 コントロールパネルを使用してダイヤルプランを割り当てるには

1.  CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。 Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで **[ユーザー]** をクリックします。

4.  **[ユーザーの検索]** ボックスに、有効にするユーザー アカウントの表示名、名、姓、セキュリティ アカウント マネージャー (SAM) のアカウント名、SIP アドレス、または回線 URI (Uniform Resource Identifier) の全体か最初の一部の文字列を入力して、**[検索]** をクリックします。

5.  表で、ダイヤルプランを割り当てるユーザーアカウントをクリックします。

6.  [**編集**] メニューの [**詳細の表示**] をクリックします。

7.  [**Lync Server ユーザーの編集**] ページの [**テレフォニー**] で、[**エンタープライズ VoIP**] をクリックします。

8.  [**ダイヤルプランポリシー**] をクリックし、目的のダイヤルプランを選択します。

9.  [**確定**] をクリックします。

ダイヤルプランの構成の詳細については、トピック「 [Lync Server 2013 でのダイヤルプランの構成](lync-server-2013-configuring-dial-plans.md)」を参照してください。

## <a name="assign-a-per-user-dial-plan-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用してユーザーごとのダイヤルプランを割り当てる

Windows PowerShell と**get-csdialplan**コマンドレットを使用して、ユーザーごとのダイヤルプランを割り当てることができます。 このコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモートセッションから実行できます。 リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を[https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)で参照してください。

## <a name="to-assign-a-per-user-dial-plan-to-a-single-user"></a>ユーザー単位のダイヤルプランを1人のユーザーに割り当てるには

  - 次のコマンドは、ユーザーごとのダイヤルプラン RedmondDialPlan をユーザー Ken Myer に割り当てます。
    
        Grant-CsDialPlan -Identity "Ken Myer" -PolicyName "RedmondDialPlan"

## <a name="to-assign-a-per-user-dial-plan-to-multiple-users"></a>複数のユーザーにユーザー単位のダイヤルプランを割り当てるには

  - このコマンドを実行すると、ユーザーごとのダイヤルプラン RedmondDialPlan が Redmond の市区町村で働くすべてのユーザーに割り当てられます。 このコマンドで使用されている LdapFilter パラメーターの詳細については、「 [Get-help user](https://technet.microsoft.com/library/gg398125\(v=ocs.15\))コマンドレットのドキュメント」を参照してください。
    
        Get-CsUser -LdapFilter "l=Redmond" | Grant-CsDialPlan -PolicyName "RedmondDialPlan"

## <a name="to-unassign-a-per-user-dial-plan"></a>ユーザーごとのダイヤルプランの割り当てを解除するには

  - 次のコマンドを実行すると、既に Ken Myer に割り当てられているユーザーごとのダイヤルプランは割り当てから解放されます。 ユーザーごとのダイヤルプランの割り当てが解除されると、Ken Myer はグローバルダイヤルプラン、自分のローカルサイトのダイヤルプラン (存在する場合)、またはレジストラーまたは PSTN ゲートウェイに割り当てられているサービススコープのダイヤルプランを使用して、自動的に管理されます。 サービススコープのダイヤルプランは、任意のサイトダイヤルプランより優先され、サイトのダイヤルプランはグローバルダイヤルプランより優先されます。
    
        Grant-CsDialPlan -Identity "Ken Myer" -PolicyName $Null

詳細については、 [get-csdialplan](https://technet.microsoft.com/library/gg398547\(v=ocs.15\))コマンドレットのヘルプトピックを参照してください。

## <a name="see-also"></a>関連項目


[Lync Server 2013 でのダイヤルプランの構成](lync-server-2013-configuring-dial-plans.md)  
[Lync Server 2013 に対して有効になっているユーザーアカウント](lync-server-2013-user-accounts-enabled-for-lync-server.md)

