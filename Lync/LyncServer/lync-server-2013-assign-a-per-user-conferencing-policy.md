---
title: 'Lync Server 2013: ユーザーごとの会議ポリシーを割り当てる'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Assign a per-user conferencing policy
ms:assetid: 72f12c72-65f7-44fe-ab81-0f57cb2f87d1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521015(v=OCS.15)
ms:contentKeyID: 48184475
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9dbeb129ef58c6993d1cd919b03d7417d35b439a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840918"
---
# <a name="assign-a-per-user-conferencing-policy-in-lync-server-2013"></a>Lync Server 2013 でユーザーごとの会議ポリシーを割り当てる

 


会議ポリシーは、Lync Server コントロールパネルで構成できるユーザーアカウントの個別の設定の1つです。

ユーザーごとの会議のポリシーの展開は任意です。 グローバルレベルの会議ポリシーまたはサイトレベルの会議ポリシーのみを展開することもできます。 ユーザーごとのポリシーを展開する場合は、ユーザー、グループ、または連絡先オブジェクトに明示的に割り当てる必要があります。 特定のサイトレベルまたはユーザーごとのポリシーが割り当てられていないときに、グローバルレベルの会議ポリシーで定義されているユーザーに対して、既定で自動的に会議のユーザー権限と権限が付与されます。

ユーザーごとの会議ポリシーを1つ以上作成したら、このトピックの手順を使用して、特定のユーザーが開催した会議に対してサーバーに付与するユーザー権限と権限を指定するポリシーを割り当てます。

利用可能なすべての会議ポリシー設定の一覧については、「 [Lync Server 2013 の会議ポリシー設定リファレンス](lync-server-2013-conferencing-policy-settings-reference.md)」を参照してください。

会議ポリシーの作成の詳細については、「 [Lync Server 2013 で会議ポリシーを作成または変更](lync-server-2013-create-or-modify-a-conferencing-policy.md)する」を参照してください。

## <a name="to-assign-a-per-user-conferencing-policy"></a>ユーザーごとの会議ポリシーを割り当てるには

1.  CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。 Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。

3.  左側のナビゲーション バーで [**ユーザー**] をクリックします。

4.  ユーザーを探すには、次のいずれかの方法を使用します。
    
      - [**ユーザーの検索**] ボックスに、表示名、名、姓、セキュリティ アカウント マネージャー (SAM) のアカウント名、SIP アドレス、またはユーザー アカウントの回線 URI (Uniform Resource Identifier) の全体か先頭部分の文字列を入力して、[**検索**] をクリックします。
    
      - 保存したクエリがある場合は、[**クエリを開く**] アイコンをクリックして、[**開く**] ダイアログ ボックスを使用してそのクエリ (.usf ファイル) を取得してから、[**検索**] をクリックします。

5.  (オプション) 結果を絞り込むための追加の検索条件を次のように指定します。
    
    1.  [**フィルターの追加**] をクリックします。
    
    2.  ユーザーのプロパティを入力するか、ドロップダウン リストの矢印をクリックして選択し、プロパティを指定します。
    
    3.  [**次の値に等しい**] ドロップダウン リストで、演算子 (例: [**次の値に等しい**]、[**次の値に等しくない**]) をクリックします。
    
    4.  選択したユーザー プロパティによっては、検索結果のフィルターに使用する条件を入力するか、ドロップダウン リストの矢印をクリックして指定します。
        

        > [!TIP]  
        > クエリにその他の検索句を追加するには、[<STRONG>フィルターの追加</STRONG>] をクリックします。

    
    5.  [**検索**] をクリックします。

6.  検索結果のユーザーをクリックして、[**アクション**] をクリックしてから、[**ポリシーの割り当て**] をクリックします。
    

    > [!TIP]  
    > 同じユーザーごとの会議ポリシーを複数のユーザーに適用する場合は、検索結果で複数のユーザーを選び、[<STRONG>操作</STRONG>] をクリックして、[<STRONG>ポリシーの割り当て</STRONG>] をクリックします。



7.  [**ポリシーの割り当て**] の [**会議ポリシー**] で、次のいずれかの操作を行います。
    

    > [!NOTE]  
    > [<STRONG>ポリシーの割り当て</STRONG>] で構成できる複数のポリシーがあるため、 <STRONG> &lt;ダイアログ&gt; </STRONG>ボックスのすべてのポリシーで既定で [そのまま保持] が選択されています。 この設定を変更しないで、以前にユーザーに割り当てたポリシーを使用して続行します。

    
      - [ ** \<自動\> ** ] を選択して、Lync Server 2013 でグローバルレベルポリシーを自動的に選ぶか、定義されている場合はサイトレベルポリシーを自動的に選択するように設定します。
    
      - [**会議ポリシー** ] ページで以前に定義したユーザーごとの会議ポリシーの名前をクリックします。
        

        > [!TIP]  
        > 割り当てるポリシーの決定に役立てるために、ポリシー名をクリックしたら [<STRONG>表示</STRONG>] をクリックして、ポリシーで定義されているユーザー権限やアクセス許可を確認します。



8.  終了したら、[**OK**] をクリックします。

## <a name="assigning-a-per-user-conferencing-policy-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用してユーザーごとの会議ポリシーを割り当てる

ユーザーごとの会議ポリシーは、Windows PowerShell と Grant-Set-csconferencingpolicy コマンドレットを使用して割り当てることができます。 このコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモートセッションから実行できます。 リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、「Lync Server Windows PowerShell のブログ記事」を参照してください[http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。「リモート PowerShell を使用して Microsoft Lync Server 2010 を管理する」を参照してください。

## <a name="to-assign-a-per-user-conferencing-policy-to-a-single-user"></a>ユーザーごとの会議ポリシーを1人のユーザーに割り当てるには

  - 次のコマンドを実行すると、ユーザーごとの会議ポリシー RedmondConferencingPolicy が Ken Myer に割り当てられます。
    
        Grant-CsConferencingPolicy -Identity "Ken Myer" -PolicyName "RedmondConferencingPolicy"

## <a name="to-assign-a-per-user-conferencing-policy-to-multiple-users"></a>ユーザーごとの会議ポリシーを複数のユーザーに割り当てるには

  - このコマンドを実行すると、ユーザーごとの会議ポリシー HRConferencingPolicy が人事部で作業するすべてのユーザーに割り当てられます。 このコマンドで使用される LdapFilter パラメーターの詳細については、「[ユーザーの取得](https://technet.microsoft.com/en-us/library/gg398125\(v=ocs.15\))」コマンドレットのドキュメントを参照してください。
    
        Get-CsUser -LdapFilter "Department=Human Resources" | Grant-CsConferencingPolicy -PolicyName "HRConferencingPolicy"

## <a name="to-unassign-a-per-user-conferencing-policy"></a>ユーザーごとの会議ポリシーを割り当て解除するには

  - 次のコマンドは、以前に Ken Myer に割り当てられているユーザーごとの会議ポリシーを割り当て解除します。 ユーザー単位の PIN ポリシーが割り当て解除された後、Ken Myer は、グローバル ポリシー、または存在する場合は Ken Myer のローカル サイト ポリシーによって、自動的に管理されます。 サイト ポリシーは、グローバル ポリシーよりも優先されます。
    
        Grant-CsConferencingPolicy -Identity "Ken Myer" -PolicyName $Null

詳細については、「 [Grant-set-csconferencingpolicy](https://technet.microsoft.com/en-us/library/gg425937\(v=ocs.15\))コマンドレットのヘルプトピックを参照してください。

## <a name="see-also"></a>関連項目


[Lync Server 2013 で会議ポリシーを作成または変更する](lync-server-2013-create-or-modify-a-conferencing-policy.md)  


[Lync Server 2013 でのユーザーごとのポリシーの割り当て](lync-server-2013-assigning-per-user-policies.md)

