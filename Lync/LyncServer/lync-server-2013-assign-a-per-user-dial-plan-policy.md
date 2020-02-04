---
title: 'Lync Server 2013: ユーザーごとのダイヤルプランポリシーを割り当てる'
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
ms.openlocfilehash: f2bc62981a69b1260ba5f2fbaeabc112553b85f5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722967"
---
# <a name="assign-a-per-user-dial-plan-policy-in-lync-server-2013"></a>Lync Server 2013 でユーザーごとのダイヤルプランポリシーを割り当てる

 


ダイヤルイン会議のエンタープライズボイスまたはユーザーのいずれかのユーザーアカウント構成を完了するには、ユーザーにダイヤルプランを割り当てる必要があります。 既存のユーザーごとのダイヤルプランを明示的に割り当てていない場合、ユーザーアカウントは、グローバルダイヤルプランを自動的に使用するか、存在する場合はサイトレベルのダイヤルプランを使います。 エンタープライズ Voip が有効になっているすべてのユーザーに対してグローバルまたはサイトのダイヤルプランを使用する場合は、このセクションをスキップできます。

## <a name="to-assign-a-dial-plan-by-using-the-lync-server-2013-control-panel"></a>Lync Server 2013 コントロールパネルを使用してダイヤルプランを割り当てるには

1.  CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。 Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。

3.  左側のナビゲーション バーで [**ユーザー**] をクリックします。

4.  [**ユーザーの検索**] ボックスに、有効にするユーザー アカウントの表示名、名、姓、セキュリティ アカウント マネージャー (SAM) のアカウント名、SIP アドレス、または回線 URI (Uniform Resource Identifier) の全体か先頭の部分の文字列を入力して、[**検索**] をクリックします。

5.  表で、ダイヤルプランを割り当てるユーザーアカウントをクリックします。

6.  [**編集**] メニューの [**詳細の表示**] をクリックします。

7.  [ **Lync Server ユーザーの編集**] ページの [**テレフォニー**] で、[**エンタープライズ voip**] をクリックします。

8.  [**ダイヤルプランポリシー**] をクリックし、目的のダイヤルプランを選択します。

9.  [**コミット**] をクリックします。

ダイヤルプランの設定の詳細については、「 [Lync Server 2013 でダイヤルプランを構成する](lync-server-2013-configuring-dial-plans.md)」を参照してください。

## <a name="assign-a-per-user-dial-plan-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用して、ユーザーごとのダイヤルプランを割り当てる

Windows PowerShell と**Grant-CsdialPlan**コマンドレットを使用して、ユーザーごとのダイヤルプランを割り当てることができます。 このコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモートセッションから実行できます。 リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を[http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)で参照してください。

## <a name="to-assign-a-per-user-dial-plan-to-a-single-user"></a>単一のユーザーにユーザー単位のダイヤル プランを割り当てるには

  - 次のコマンドを実行すると、ユーザーごとのダイヤルプラン RedmondDialPlan が Ken Myer に割り当てられます。
    
        Grant-CsDialPlan -Identity "Ken Myer" -PolicyName "RedmondDialPlan"

## <a name="to-assign-a-per-user-dial-plan-to-multiple-users"></a>複数のユーザーにユーザー単位のダイヤル プランを割り当てるには

  - このコマンドは、Redmond 市で勤務するすべてのユーザーに、ユーザーごとのダイヤルプラン RedmondDialPlan を割り当てます。 このコマンドで使用される LdapFilter パラメーターの詳細については、「[ユーザーの取得](https://technet.microsoft.com/en-us/library/gg398125\(v=ocs.15\))」コマンドレットのドキュメントを参照してください。
    
        Get-CsUser -LdapFilter "l=Redmond" | Grant-CsDialPlan -PolicyName "RedmondDialPlan"

## <a name="to-unassign-a-per-user-dial-plan"></a>ユーザー単位のダイヤル プランの割り当てを解除するには

  - 次のコマンドは、以前に Ken Myer に割り当てられているユーザーごとのダイヤルプランを割り当て解除します。 ユーザーごとのダイヤルプランが割り当てられていない場合、Ken Myer は、グローバルダイヤルプラン、彼のローカルサイトダイヤルプラン (存在する場合)、またはレジストラーまたは PSTN ゲートウェイに割り当てられているサービス範囲ダイヤルプランを使って、自動的に管理されます。 サービス範囲ダイヤルプランは、どのサイトダイヤルプランよりも優先され、サイトダイヤルプランはグローバルダイヤルプランより優先されます。
    
        Grant-CsDialPlan -Identity "Ken Myer" -PolicyName $Null

詳細については、「 [Grant-CsDialPlan](https://technet.microsoft.com/en-us/library/gg398547\(v=ocs.15\))コマンドレットのヘルプトピックを参照してください。

## <a name="see-also"></a>関連項目


[Lync Server 2013 でのダイヤル プランの構成](lync-server-2013-configuring-dial-plans.md)  
[Lync Server 2013 で有効になっているユーザーアカウント](lync-server-2013-user-accounts-enabled-for-lync-server.md)

