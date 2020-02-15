---
title: 'Lync Server 2013: ユーザー単位の会議ポリシーの割り当て'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a per-user conferencing policy
ms:assetid: 72f12c72-65f7-44fe-ab81-0f57cb2f87d1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521015(v=OCS.15)
ms:contentKeyID: 48184475
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7c4fbef02553d4ba390dcf94f96f55936e2661b1
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043319"
---
# <a name="assign-a-per-user-conferencing-policy-in-lync-server-2013"></a>Lync Server 2013 でユーザー単位の会議ポリシーを割り当てる

 


会議ポリシーは、Lync Server コントロールパネルで構成できるユーザーアカウントの個別の設定の1つです。

ユーザーは 1 つまたは複数のユーザー単位の会議ポリシーを展開できますが、この展開はオプションです。また、グローバルレベルの会議ポリシーまたはサイトレベルの会議ポリシーだけを展開することもできます。ユーザー単位のポリシーを展開する場合は、ポリシーをユーザー、グループ、または連絡先オブジェクトに明示的に割り当てる必要があります。特定のサイトレベルのポリシーやユーザー単位のポリシーが割り当てられていない場合は、会議のユーザー権限やアクセス許可により、グローバルレベルの会議ポリシーで定義された既定の設定が自動的に適用されます。

ユーザー単位の会議ポリシーを 1 つ以上作成した後、このトピックの手順を使用してポリシーを割り当て、特定のユーザーが開催する会議に対してサーバーが許可するユーザー権限とアクセス許可を指定します。

利用可能なすべての電話会議ポリシー設定の一覧については、「 [Lync Server 2013 の会議ポリシー設定リファレンス](lync-server-2013-conferencing-policy-settings-reference.md)」を参照してください。

会議ポリシーの作成の詳細については、「 [Lync Server 2013 で会議ポリシーを作成または変更する](lync-server-2013-create-or-modify-a-conferencing-policy.md)」を参照してください。

## <a name="to-assign-a-per-user-conferencing-policy"></a>ユーザー単位の会議ポリシーを割り当てるには

1.  CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。 Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで [**ユーザー**] をクリックします。

4.  ユーザーを探すには、次のどちらかの方法を使用します。
    
      - [**ユーザーの検索**] ボックスに、表示名、名、姓、セキュリティ アカウント マネージャー (SAM) のアカウント名、SIP アドレス、またはユーザー アカウントの回線 URI (Uniform Resource Identifier) の全体か最初の一部の文字列を入力して、[**検索**] をクリックします。
    
      - 保存したクエリがある場合は、[**クエリを開く**] アイコンをクリックし、[**開く**] ダイアログ ボックスを使用してそのクエリ (.usf ファイル) を取得して、[**検索**] をクリックします。

5.  (オプション) 結果を絞り込むための追加の検索条件を次のように指定します。
    
    1.  [**フィルターの追加**] をクリックします。
    
    2.  ユーザーのプロパティを入力するか、ドロップダウン リストの矢印をクリックして選択し、プロパティを指定します。
    
    3.  [**次の値に等しい**] ドロップダウン リストで、演算子 (例: [**次の値に等しい**]、[**次の値に等しくない**]) をクリックします。
    
    4.  選択したユーザー プロパティによっては、検索結果のフィルターに使用する条件を入力するか、ドロップダウン リストの矢印をクリックして指定します。
        

        > [!TIP]  
        > クエリにその他の検索句を追加するには、[<STRONG>フィルターの追加</STRONG>] をクリックします。

    
    5.  [**検索**] をクリックします。

6.  検索結果のユーザーをクリックし、[**アクション**] をクリックして、[**ポリシーの割り当て**] をクリックします。
    

    > [!TIP]  
    > 同じユーザー単位の会議ポリシーを複数のユーザーに適用する場合は、検索結果で複数のユーザーを選択して、[<STRONG>アクション</STRONG>] をクリックし、[<STRONG>ポリシーの割り当て</STRONG>] をクリックします。



7.  [**ポリシーの割り当て**] の [**会議ポリシー**] で、次のどちらかの手順を実行します。
    

    > [!NOTE]  
    > [<STRONG>ポリシーの割り当て</STRONG>] で構成できるポリシーが複数あるため、ダイアログボックス内のすべてのポリシーに対して、既定で [ <STRONG> &lt;&gt;そのまま保持</STRONG>] が選択されています。 この設定を変更しない場合は、以前にユーザーに割り当てたポリシーを使用して続行します。

    
      - [ ** \<自動\> ** ] を選択すると、Lync Server 2013 でグローバルレベルのポリシーまたはサイトレベルのポリシー (定義されている場合) のいずれかを自動的に選択できるようになります。
    
      - [**会議ポリシー**] ページであらかじめ定義した、ユーザー単位の会議ポリシーの名前をクリックします。
        

        > [!TIP]  
        > 割り当てるポリシーの決定に役立てるために、ポリシー名をクリックしたら [<STRONG>表示</STRONG>] をクリックして、ポリシーで定義されているユーザー権限やアクセス許可を確認します。



8.  終了したら、[**OK**] をクリックします。

## <a name="assigning-a-per-user-conferencing-policy-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用したユーザー単位の会議ポリシーの割り当て

ユーザー単位の会議ポリシーは、Windows PowerShell と Get-csconferencingpolicy コマンドレットを使用して割り当てることができます。 このコマンドレットは、Lync Server 2013 管理シェルから実行するか、Windows PowerShell のリモートセッションから実行できます。 リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を[http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)で参照してください。

## <a name="to-assign-a-per-user-conferencing-policy-to-a-single-user"></a>ユーザー単位の会議ポリシーを1人のユーザーに割り当てるには

  - 次のコマンドは、ユーザー単位の会議ポリシー RedmondConferencingPolicy をユーザー Ken Myer に割り当てます。
    
        Grant-CsConferencingPolicy -Identity "Ken Myer" -PolicyName "RedmondConferencingPolicy"

## <a name="to-assign-a-per-user-conferencing-policy-to-multiple-users"></a>ユーザー単位の会議ポリシーを複数のユーザーに割り当てるには

  - 次のコマンドは、ユーザー単位の会議ポリシー HRConferencingPolicy を "Human Resources/人事" 部門に勤務するすべてのユーザーに割り当てます。 このコマンドで使用されている LdapFilter パラメーターの詳細については、「 [Get-help user](https://technet.microsoft.com/library/gg398125\(v=ocs.15\))コマンドレットのドキュメント」を参照してください。
    
        Get-CsUser -LdapFilter "Department=Human Resources" | Grant-CsConferencingPolicy -PolicyName "HRConferencingPolicy"

## <a name="to-unassign-a-per-user-conferencing-policy"></a>ユーザー単位の会議ポリシーを割り当て解除するには

  - 次のコマンドは、以前に Ken Myer に割り当てたユーザー単位の会議ポリシーのすべての割り当てを解除します。ユーザー単位のポリシーが割り当て解除された後、Ken Myer は自動的にグローバル ポリシーを使用して管理されるか、存在する場合には自身のローカル サイト ポリシーを使用して管理されます。サイト ポリシーはグローバル ポリシーより優先されます。
    
        Grant-CsConferencingPolicy -Identity "Ken Myer" -PolicyName $Null

詳細については、 [get-csconferencingpolicy](https://technet.microsoft.com/library/gg425937\(v=ocs.15\))コマンドレットのヘルプトピックを参照してください。

## <a name="see-also"></a>関連項目


[Lync Server 2013 での会議ポリシーの作成または変更](lync-server-2013-create-or-modify-a-conferencing-policy.md)  


[Lync Server 2013 でのユーザー単位のポリシーの割り当て](lync-server-2013-assigning-per-user-policies.md)

