---
title: 'Lync Server 2013: ユーザー単位のアーカイブポリシーの割り当て'
description: 'Lync Server 2013: ユーザー単位のアーカイブポリシーを割り当てます。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a per-user archiving policy
ms:assetid: a12ca483-b235-460f-b3fe-130fb3087264
ms:mtpsurl: https://technet.microsoft.com/library/Gg182560(v=OCS.15)
ms:contentKeyID: 48185014
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6c81d7e426f16c298196aba733d720a92d0854bd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559993"
---
# <a name="assign-a-per-user-archiving-policy-in-lync-server-2013"></a>Lync Server 2013 でユーザー単位のアーカイブポリシーを割り当てる

 


アーカイブポリシーは、Lync Server 2013 コントロールパネルで構成できるユーザーアカウントの個別の設定の1つです。

1つまたは複数のユーザー単位のアーカイブポリシーの展開はオプションです。 また、グローバルレベルのアーカイブポリシーまたはサイトレベルのアーカイブポリシーのみを展開することもできます。 ユーザー単位のポリシーを展開する場合は、ポリシーをユーザー、グループ、または連絡先オブジェクトに明示的に割り当てる必要があります。 特定のサイトレベルまたはユーザーごとのポリシーが割り当てられていない場合、グローバルレベルの電話会議ポリシーで定義されているものに自動的にアーカイブ要件が設定されます。

ユーザーごとのアーカイブポリシーを1つ以上作成した後、このトピックの手順を使用して、特定のユーザーの内部通信、外部通信、またはその両方がサーバーによってアーカイブされるかどうかを適切に指定するポリシーを割り当てます。

ユーザー単位のアーカイブポリシーの作成の詳細については、「 [Lync Server 2013 でのアーカイブポリシーの作成」を参照して、特定のサイトまたはユーザーの内部通信または外部通信のアーカイブを有効または無効に](lync-server-2013-create-archiving-policy-sites-users.md)します。

## <a name="to-assign-a-per-user-archiving-policy"></a>ユーザー単位のアーカイブポリシーを割り当てるには

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
    > 同じユーザー単位のアーカイブポリシーを複数のユーザーに適用する場合は、検索結果で複数のユーザーを選択し、[ <STRONG>アクション</STRONG>] をクリックして、[ <STRONG>ポリシーの割り当て</STRONG>] をクリックします。



7.  [ **ポリシーの割り当て**] の [ **アーカイブポリシー**] で、次のいずれかの手順を実行します。
    

    > [!NOTE]  
    > [<STRONG>ポリシーの割り当て</STRONG>] ダイアログボックスを使用して複数のポリシーを構成できるので、ダイアログボックスのすべてのポリシーに対して、既定で [ <STRONG> &lt; その &gt; まま保持</STRONG>] が選択されています。 この設定を変更しない場合は、以前にユーザーに割り当てたポリシーを使用して続行します。

    
      - Lync Server 2013 でグローバルレベルのポリシーまたはサイトレベルのポリシー (定義されている場合) のいずれかを自動的に選択できるようにします。
    
      - [ **アーカイブポリシー** ] ページで事前に定義した、ユーザー単位のアーカイブポリシーの名前をクリックします。
        

        > [!TIP]  
        > 割り当てるポリシーの決定に役立てるために、ポリシー名をクリックしたら、[<STRONG>表示</STRONG>] をクリックして、ポリシーで定義されているユーザーの権限やアクセス許可を確認します。



8.  終了したら、[**OK**] をクリックします。

## <a name="assigning-a-per-user-archiving-policy-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用した Per-User アーカイブポリシーの割り当て

Windows PowerShell と **grant-csarchivingpolicy** コマンドレットを使用して、ユーザー単位のアーカイブポリシーを割り当てることができます。 このコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモートセッションから実行できます。 リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を[https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)で参照してください。

## <a name="to-assign-a-per-user-archiving-policy-to-a-single-user"></a>ユーザー単位のアーカイブポリシーを単一のユーザーに割り当てるには

  - 次のコマンドは、ユーザー単位のアーカイブ ポリシーである RedmondArchivingPolicy をユーザー Ken Myer に割り当てます。
    
        Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName "RedmondArchivingPolicy"

## <a name="to-assign-a-per-user-archiving-policy-to-multiple-users"></a>ユーザー単位のアーカイブポリシーを複数のユーザーに割り当てるには

  - このコマンドは、ユーザーごとのアーカイブポリシー RedmondArchivingPolicy を、レジストラープール atl-cs-001.litwareinc.com に所属するアカウントを持つすべてのユーザーに割り当てます。 このコマンドで使用される Filter パラメーターの詳細については、「 [Get-help user](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) コマンドレットのドキュメント」を参照してください。
    
        Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.litwareinc.com"} | Grant-CsArchivingPolicy -PolicyName "RedmondArchivingPolicy"

## <a name="to-unassign-a-per-user-archiving-policy"></a>ユーザー単位のアーカイブポリシーを割り当て解除するには

  - 次のコマンドは、Ken Myer に割り当て済みのユーザーごとのアーカイブポリシーの割り当てを解除します。ユーザーごとのポリシーの割り当てが解除された後、Ken Myer は、グローバル ポリシー (存在する場合はローカル サイト ポリシー) を使用して自動的に管理されます。サイト ポリシーがグローバル ポリシーに優先します。
    
        Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName $Null

詳細については、 [grant-csarchivingpolicy](https://technet.microsoft.com/library/gg398475\(v=ocs.15\)) コマンドレットのヘルプトピックを参照してください。

## <a name="see-also"></a>関連項目


[Lync Server 2013 のアーカイブポリシーを作成して、特定のサイトまたはユーザーの内部通信または外部通信のアーカイブを有効または無効にする](lync-server-2013-create-archiving-policy-sites-users.md)  


[Lync Server 2013 でのユーザー単位のポリシーの割り当て](lync-server-2013-assigning-per-user-policies.md)

