---
title: 'Lync Server 2013: ユーザーごとの場所ポリシーを割り当てる'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Assign a per-user location policy
ms:assetid: 343f2de3-a0ae-4403-8456-6e520b579d32
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520974(v=OCS.15)
ms:contentKeyID: 48183794
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4a387d0f603addea31bd1e3ee6b591e06a26b2c4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848843"
---
# <a name="assign-a-per-user-location-policy-in-lync-server-2013"></a>Lync Server 2013 でユーザーごとの場所ポリシーを割り当てる

 


場所のポリシーは、Lync Server コントロールパネルで構成できるユーザーアカウントの個別の設定の1つです。

1つまたは複数のユーザーごとの場所のポリシーを展開することは任意です。 グローバルレベルの場所のポリシーまたはサブネットレベルの場所のポリシーのみを展開することもできます。 ユーザー単位のポリシーを展開する場合は、ポリシーをユーザー、グループ、または連絡先オブジェクトに明示的に割り当てる必要があります。 特定のサブネットレベルまたはユーザーごとのポリシーが割り当てられていない場合、9-1-1 (E9) の設定がグローバルレベルのポリシーで定義されているものに自動的に既定で設定されます。

ユーザーごとの場所ポリシーを1つ以上作成したら、このトピックの手順を使用して、特定のユーザーによって設定された緊急通話にサーバーが適用する設定を指定するポリシーに割り当てます。

利用可能なすべての場所のポリシー設定の一覧については、「 [Lync Server 2013 の位置情報ポリシーを定義](lync-server-2013-defining-the-location-policy.md)する」を参照してください。

場所のポリシーの作成について詳しくは、「 [Lync Server 2013 で場所のポリシーを作成](lync-server-2013-create-location-policies.md)する」をご覧ください。

## <a name="to-assign-a-per-user-location-policy-with-the-lync-server-control-panel"></a>Lync Server コントロールパネルを使用して、ユーザーごとの場所のポリシーを割り当てるには

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
    > 複数のユーザーに同じ1つの場所のポリシーを適用する場合は、検索結果で複数のユーザーを選び、[<STRONG>操作</STRONG>] をクリックして、[<STRONG>ポリシーの割り当て</STRONG>] をクリックします。



7.  [**ポリシーの割り当て**] の [**場所のポリシー**] で、次のいずれかの操作を行います。
    

    > [!NOTE]  
    > [<STRONG>ポリシーの割り当て</STRONG>] ダイアログボックスを使って構成できる複数のポリシーがあるため、ダイアログボックスのすべてのポリシーで既定で [ <STRONG> &lt;その&gt;まま</STRONG>実行する] が選択されています。 この設定を変更しないで、以前にユーザーに割り当てたポリシーを使用して続行します。

    
      - [Lync Server 2013 でグローバルレベルポリシー] または [定義されている場合はサブネットレベルポリシー] のいずれかを自動的に選択することを許可します。
    
      - **新しい-CsLocationPolicy**コマンドレットを実行して以前に定義した、ユーザーごとの場所ポリシーの名前をクリックします。
        

        > [!TIP]  
        > 割り当てるポリシーを決定するには、ポリシー名をクリックした後、[<STRONG>表示</STRONG>] をクリックして、ポリシーで定義されたユーザー権限とアクセス許可を表示します。



8.  終了したら、[**OK**] をクリックします。

## <a name="assigning-a-per-user-location-policy-by-using-lync-server-management-shell-cmdlets"></a>Lync Server Management Shell コマンドレットを使用して、ユーザーごとの場所ポリシーを割り当てる

Grant-CsLocationPolicy コマンドレットを使用して、ユーザーごとの場所ポリシーを割り当てることができます。 このコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモートセッションから実行できます。 リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、「Lync Server Windows PowerShell のブログ記事」を参照してください[http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。「リモート PowerShell を使用して Microsoft Lync Server 2010 を管理する」を参照してください。

## <a name="to-assign-a-per-user-location-policy-to-a-single-user"></a>ユーザーごとの場所のポリシーを1人のユーザーに割り当てるには

  - 次のコマンドを実行すると、ユーザーごとの場所ポリシーの RedmondLocationPolicy がユーザー Ken Myer に割り当てられます。
    
        Grant-CsLocationPolicy -Identity "Ken Myer" -PolicyName "RedmondLocationPolicy"

## <a name="to-assign-a-per-user-location-policy-to-multiple-users"></a>ユーザーごとの場所ポリシーを複数のユーザーに割り当てるには

  - このコマンドを実行すると、ユーザーごとの場所のポリシー AccountingDepartmentLocationPolicy が、会計部門で作業するすべてのユーザーに割り当てられます。 このコマンドで使用される LdapFilter パラメーターの詳細については、「[ユーザーの取得](https://technet.microsoft.com/en-us/library/gg398125\(v=ocs.15\))」コマンドレットのドキュメントを参照してください。
    
        Get-CsUser -LdapFilter "Department=Accounting" | Grant-CsLocationPolicy -PolicyName "AccountingDepartmentLocationPolicy"

## <a name="to-unassign-a-per-user-location-policy"></a>ユーザーごとの場所ポリシーを割り当て解除するには

  - 次のコマンドは、以前に Ken Myer に割り当てられているユーザーごとの場所ポリシーを割り当て解除します。 ユーザー単位の PIN ポリシーが割り当て解除された後、Ken Myer は、グローバル ポリシー、または存在する場合は Ken Myer のローカル サイト ポリシーによって、自動的に管理されます。 サイト ポリシーは、グローバル ポリシーよりも優先されます。
    
        Grant-CsLocationPolicy -Identity "Ken Myer" -PolicyName $Null

詳細については、「 [Grant-CsLocationPolicy](https://technet.microsoft.com/en-us/library/gg413049\(v=ocs.15\)) 」コマンドレットのヘルプトピックを参照してください。

