---
title: 'Lync Server 2013: ユーザーごとのアーカイブポリシーを割り当てる'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Assign a per-user archiving policy
ms:assetid: a12ca483-b235-460f-b3fe-130fb3087264
ms:mtpsurl: https://technet.microsoft.com/library/Gg182560(v=OCS.15)
ms:contentKeyID: 48185014
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 36d23e44e397a77f0d490d8fda27ee711d1c61c5
ms.sourcegitcommit: 0119af282f53f49c4ab6e01c3319d01bc6fdad2c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/14/2020
ms.locfileid: "41111581"
---
# <a name="assign-a-per-user-archiving-policy-in-lync-server-2013"></a>Lync Server 2013 でユーザーごとのアーカイブポリシーを割り当てる

 


アーカイブポリシーは、Lync Server 2013 コントロールパネルで構成できるユーザーアカウントの個々の設定の1つです。

1つまたは複数のユーザーごとのアーカイブポリシーの展開は任意です。 グローバルレベルのアーカイブポリシーまたはサイトレベルのアーカイブポリシーのみを展開することもできます。 ユーザー単位のポリシーを展開する場合は、ポリシーをユーザー、グループ、または連絡先オブジェクトに明示的に割り当てる必要があります。 特定のサイトレベルまたはユーザーごとのポリシーが割り当てられていない場合、グローバルレベルの会議ポリシーで定義されているアーカイブ要件が自動的に既定になります。

ユーザーごとのアーカイブポリシーを1つ以上作成したら、このトピックの手順を使用して、特定のユーザーの内部通信、外部通信、またはその両方がサーバーによってアーカイブされるかどうかを適切に指定するポリシーを割り当てます。

ユーザーごとのアーカイブポリシーを作成する方法の詳細については、「 [Lync Server 2013 でアーカイブポリシーを作成する」を参照して、特定のサイトまたはユーザーに対する内部または外部の通信のアーカイブを有効または無効に](lync-server-2013-create-archiving-policy-sites-users.md)します。

## <a name="to-assign-a-per-user-archiving-policy"></a>ユーザーごとのアーカイブポリシーを割り当てるには

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
    > ユーザーごとの同じアーカイブポリシーを複数のユーザーに適用する場合は、検索結果で複数のユーザーを選択し、[<STRONG>アクション</STRONG>] をクリックして、[<STRONG>ポリシーの割り当て</STRONG>] をクリックします。



7.  [**ポリシーの割り当て**] の [**アーカイブポリシー**] で、次のいずれかの操作を行います。
    

    > [!NOTE]  
    > [<STRONG>ポリシーの割り当て</STRONG>] ダイアログボックスを使って構成できる複数のポリシーがあるため、ダイアログボックスのすべてのポリシーで既定で [ <STRONG> &lt;その&gt;まま</STRONG>実行する] が選択されています。 この設定を変更しないで、以前にユーザーに割り当てたポリシーを使用して続行します。

    
      - [Lync Server 2013 でグローバルレベルポリシー] または [定義されている場合はサイトレベルポリシー] のいずれかを自動的に選択します。
    
      - [**アーカイブポリシー** ] ページで以前に定義したユーザーごとのアーカイブポリシーの名前をクリックします。
        

        > [!TIP]  
        > 割り当てるポリシーを決定するには、ポリシー名をクリックした後、[<STRONG>表示</STRONG>] をクリックして、ポリシーで定義されたユーザー権限とアクセス許可を表示します。



8.  終了したら、[**OK**] をクリックします。

## <a name="assigning-a-per-user-archiving-policy-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用して、ユーザーごとのアーカイブポリシーを割り当てる

ユーザーごとのアーカイブポリシーを割り当てるには、Windows PowerShell と**Grant-CsArchivingPolicy**コマンドレットを使用します。 このコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモートセッションから実行できます。 リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を[https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)で参照してください。

## <a name="to-assign-a-per-user-archiving-policy-to-a-single-user"></a>ユーザーごとのアーカイブポリシーを1人のユーザーに割り当てるには

  - 次のコマンドは、ユーザー単位のアーカイブ ポリシー RedmondArchivingPolicy をユーザー Ken Myer に割り当てます。
    
        Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName "RedmondArchivingPolicy"

## <a name="to-assign-a-per-user-archiving-policy-to-multiple-users"></a>ユーザーごとのアーカイブポリシーを複数のユーザーに割り当てるには

  - このコマンドを実行すると、ユーザーごとのアーカイブポリシー RedmondArchivingPolicy が、レジストラー pool atl-cs-001.litwareinc.com をホームに持つアカウントを持つすべてのユーザーに割り当てられます。 このコマンドで使用される Filter パラメーターの詳細については、「[ユーザーの取得](https://technet.microsoft.com/library/gg398125\(v=ocs.15\))」コマンドレットのドキュメントを参照してください。
    
        Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.litwareinc.com"} | Grant-CsArchivingPolicy -PolicyName "RedmondArchivingPolicy"

## <a name="to-unassign-a-per-user-archiving-policy"></a>ユーザーごとのアーカイブポリシーを割り当て解除するには

  - 次のコマンドは、Ken Myer に以前割り当てられていたユーザーごとのアーカイブポリシーを割り当て解除します。 ユーザー単位の PIN ポリシーが割り当て解除された後、Ken Myer は、グローバル ポリシー、または存在する場合は Ken Myer のローカル サイト ポリシーによって、自動的に管理されます。 サイト ポリシーは、グローバル ポリシーよりも優先されます。
    
        Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName $Null

詳細については、「 [Grant-CsArchivingPolicy](https://technet.microsoft.com/library/gg398475\(v=ocs.15\))コマンドレットのヘルプトピックを参照してください。

## <a name="see-also"></a>関連項目


[Lync Server 2013 でアーカイブポリシーを作成して、特定のサイトまたはユーザーの内部または外部の通信のアーカイブを有効または無効にする](lync-server-2013-create-archiving-policy-sites-users.md)  


[Lync Server 2013 でのユーザーごとのポリシーの割り当て](lync-server-2013-assigning-per-user-policies.md)

