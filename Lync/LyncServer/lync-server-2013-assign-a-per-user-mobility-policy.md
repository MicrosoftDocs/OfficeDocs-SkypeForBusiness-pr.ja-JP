---
title: 'Lync Server 2013: ユーザー単位のモビリティポリシーの割り当て'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a per-user mobility policy
ms:assetid: d8bf997f-4bc7-48d3-973b-323505f55e9d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721902(v=OCS.15)
ms:contentKeyID: 49733836
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7b9a5a1bf5132fb78086fdd424714e03af2caab5
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134423"
---
# <a name="assign-a-per-user-mobility-policy-in-lync-server-2013"></a>Lync Server 2013 でユーザー単位のモビリティポリシーを割り当てる

 


モビリティポリシーは、Lync Server コントロールパネルまたは Lync Server 管理シェルで構成できるユーザーアカウントの個別の設定の1つです。

## <a name="to-assign-a-per-user-mobility-policy-with-lync-server-control-panel"></a>Lync Server コントロールパネルを使用してユーザー単位のモビリティポリシーを割り当てるには

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
    > 同じユーザー単位のモビリティ ポリシーを複数のユーザーに適用する場合は、検索結果で複数のユーザーを選択して、[<STRONG>アクション</STRONG>] をクリックし、[<STRONG>ポリシーの割り当て</STRONG>] をクリックします。



7.  [**ポリシーの割り当て**] の [**モビリティ ポリシー**] で、次のどちらかの手順を実行します。
    

    > [!NOTE]  
    > [<STRONG>ポリシーの割り当て</STRONG>] で構成できるポリシーが複数あるため、ダイアログボックス内のすべてのポリシーに対して、既定で [ <STRONG> &lt;&gt;そのまま保持</STRONG>] が選択されています。 この設定を変更しない場合は、以前にユーザーに割り当てたポリシーを使用して続行します。

    
      - [ ** \<自動\> ** ] を選択すると、Lync Server 2013 でグローバルレベルのポリシーまたはサイトレベルのポリシー (定義されている場合) のいずれかを自動的に選択できるようになります。
    
      - [**モビリティ ポリシー**] ページであらかじめ定義した、ユーザー単位のモビリティ ポリシーの名前をクリックします。
        

        > [!TIP]  
        > 割り当てるポリシーの決定に役立てるために、ポリシー名をクリックしたら [<STRONG>表示</STRONG>] をクリックして、ポリシーで定義されているユーザー権限やアクセス許可を確認します。



8.  終了したら、[**OK**] をクリックします。

## <a name="assigning-a-per-user-mobility-policy-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用したユーザー単位のモビリティポリシーの割り当て

Windows PowerShell と**get-csmobilitypolicy**コマンドレットを使用して、ユーザー単位のモビリティポリシーを割り当てることができます。 このコマンドレットは、Lync Server 2013 管理シェルまたは Windows PowerShell のリモートセッションから実行できます。 リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を[https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)で参照してください。

## <a name="to-assign-a-per-user-mobility-policy-to-a-single-user"></a>ユーザー単位のモビリティ ポリシーを単一のユーザーに割り当てるには

  - 次のコマンドは、ユーザー単位のモビリティ ポリシー RedmondMobilityPolicy をユーザー「Ken Myer」に割り当てます。
    
        Grant-CsMobilityPolicy -Identity "Ken Myer" -PolicyName "RedmondMobilityPolicy"

## <a name="to-assign-a-per-user-mobility-policy-to-multiple-users"></a>ユーザー単位のモビリティ ポリシーを複数のユーザーに割り当てるには

  - 次のコマンドは、ユーザー単位のモビリティ ポリシー RedmondMobilityPolicy を、ポリシー NorthAmericaMobilityPolicy が現在割り当てられているすべてのユーザーに割り当てます。 このコマンドで使用されるフィルターパラメーターの詳細については、「 [Get-help user](https://technet.microsoft.com/library/gg398125\(v=ocs.15\))」を参照してください。
    
        Get-CsUser -Filter {MobilityPolicy -eq "NorthAmericaMobilityPolicy"} | Grant-CsMobilityPolicy -PolicyName "RedmondMobilityPolicy"

## <a name="to-unassign-a-per-user-mobility-policy"></a>ユーザー単位のモビリティ ポリシーを割り当て解除するには

  - 次のコマンドは、Ken Myer に割り当てられたユーザー単位のモビリティ ポリシーを割り当て解除します。ユーザー単位のポリシーが割り当て解除された後、Ken Myer は、グローバル ポリシー、または存在する場合は Ken Myer のローカル サイト ポリシーによって、自動的に管理されます。サイト ポリシーは、グローバル ポリシーよりも優先されます。
    
        Grant-CsMobilityPolicy -Identity "Ken Myer" -PolicyName $Null

詳細については、「[Grant-CsMobilityPolicy](https://technet.microsoft.com/library/hh690038\(v=ocs.15\))」を参照してください。

## <a name="see-also"></a>関連項目


[Lync Server 2013 でのモビリティポリシーの構成](lync-server-2013-configuring-mobility-policy.md)

