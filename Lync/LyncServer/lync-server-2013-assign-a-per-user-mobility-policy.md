---
title: 'Lync Server 2013: ユーザーごとのモバイルポリシーを割り当てる'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Assign a per-user mobility policy
ms:assetid: d8bf997f-4bc7-48d3-973b-323505f55e9d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721902(v=OCS.15)
ms:contentKeyID: 49733836
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e79a9b76ac4774bbbac7772bef19902d6d70f15a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848801"
---
# <a name="assign-a-per-user-mobility-policy-in-lync-server-2013"></a>Lync Server 2013 でユーザーごとのモバイルポリシーを割り当てる

 


モバイルポリシーは、Lync Server コントロールパネルまたは Lync Server 管理シェルで構成できるユーザーアカウントの個々の設定の1つです。

## <a name="to-assign-a-per-user-mobility-policy-with-lync-server-control-panel"></a>Lync Server コントロールパネルを使用してユーザーごとのモバイルポリシーを割り当てるには

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
    > ユーザーごとの同じモバイルポリシーを複数のユーザーに適用する場合は、検索結果で複数のユーザーを選び、[<STRONG>操作</STRONG>] をクリックして、[<STRONG>ポリシーの割り当て</STRONG>] をクリックします。



7.  [**ポリシーの割り当て**] の [**モビリティポリシー**] で、次のいずれかの操作を行います。
    

    > [!NOTE]  
    > [<STRONG>ポリシーの割り当て</STRONG>] で構成できる複数のポリシーがあるため、 <STRONG> &lt;ダイアログ&gt; </STRONG>ボックスのすべてのポリシーで既定で [そのまま保持] が選択されています。 この設定を変更しないで、以前にユーザーに割り当てたポリシーを使用して続行します。

    
      - [ ** \<自動\> ** ] を選択して、Lync Server 2013 でグローバルレベルポリシーを自動的に選ぶか、定義されている場合はサイトレベルポリシーを自動的に選択するように設定します。
    
      - [**モビリティポリシー** ] ページで以前に定義したユーザーごとのモバイルポリシーの名前をクリックします。
        

        > [!TIP]  
        > 割り当てるポリシーの決定に役立てるために、ポリシー名をクリックしたら [<STRONG>表示</STRONG>] をクリックして、ポリシーで定義されているユーザー権限やアクセス許可を確認します。



8.  終了したら、[**OK**] をクリックします。

## <a name="assigning-a-per-user-mobility-policy-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用して、ユーザーごとのモビリティポリシーを割り当てる

ユーザーごとのモバイルポリシーを割り当てるには、Windows PowerShell と**Grant-set-csmobilitypolicy**コマンドレットを使用します。 このコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモートセッションから実行できます。 リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、「Lync Server Windows PowerShell のブログ記事」を参照してください[http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。「リモート PowerShell を使用して Microsoft Lync Server 2010 を管理する」を参照してください。

## <a name="to-assign-a-per-user-mobility-policy-to-a-single-user"></a>ユーザーごとのモバイルポリシーを1人のユーザーに割り当てるには

  - 次のコマンドでは、ユーザーごとのモバイルポリシー RedmondMobilityPolicy が Ken Myer に割り当てられます。
    
        Grant-CsMobilityPolicy -Identity "Ken Myer" -PolicyName "RedmondMobilityPolicy"

## <a name="to-assign-a-per-user-mobility-policy-to-multiple-users"></a>ユーザーごとのモバイルポリシーを複数のユーザーに割り当てるには

  - 次のコマンドは、現在ポリシー NorthAmericaMobilityPolicy を割り当てられているすべてのユーザーに対して、ユーザーごとのモバイルポリシー RedmondMobilityPolicy を割り当てます。 このコマンドで使用される Filter パラメーターの詳細については、「[ユーザーの取得](https://technet.microsoft.com/en-us/library/gg398125\(v=ocs.15\))」を参照してください。
    
        Get-CsUser -Filter {MobilityPolicy -eq "NorthAmericaMobilityPolicy"} | Grant-CsMobilityPolicy -PolicyName "RedmondMobilityPolicy"

## <a name="to-unassign-a-per-user-mobility-policy"></a>ユーザーごとのモバイルポリシーを割り当て解除するには

  - 次のコマンドでは、以前に Ken Myer に割り当てられているユーザーごとのモバイルポリシーは割り当てられません。 ユーザー単位の PIN ポリシーが割り当て解除された後、Ken Myer は、グローバル ポリシー、または存在する場合は Ken Myer のローカル サイト ポリシーによって、自動的に管理されます。 サイト ポリシーは、グローバル ポリシーよりも優先されます。
    
        Grant-CsMobilityPolicy -Identity "Ken Myer" -PolicyName $Null

詳細については、「 [Grant-set-csmobilitypolicy](https://technet.microsoft.com/en-us/library/hh690038\(v=ocs.15\))」を参照してください。

## <a name="see-also"></a>関連項目


[Lync Server 2013 でのモビリティ ポリシーの構成](lync-server-2013-configuring-mobility-policy.md)

