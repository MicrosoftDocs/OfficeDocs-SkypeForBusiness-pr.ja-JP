---
title: 'Lync Server 2013: ユーザー単位の PIN ポリシーの割り当て'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a per-user PIN policy
ms:assetid: d8211c64-0b63-4193-a074-673da7d14287
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182594(v=OCS.15)
ms:contentKeyID: 48185475
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9523794808ca3b689cf1f3213c1f4ad657c83c25
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030120"
---
# <a name="assign-a-per-user-pin-policy-in-lync-server-2013"></a>Lync Server 2013 でユーザー単位の PIN ポリシーを割り当てる

 


ダイヤルイン会議の個人識別番号 (PIN) ポリシーは、Lync Server 2013 コントロールパネルで構成できるユーザーアカウントの個別の設定の1つです。

ユーザーは 1 つまたは複数のユーザー単位の PIN ポリシーを展開できますが、この展開はオプションです。 また、グローバルレベルの PIN ポリシーまたはサイトレベルの PIN ポリシーだけを展開することもできます。 ユーザー単位のポリシーを展開する場合は、ポリシーをユーザー、グループ、または連絡先オブジェクトに明示的に割り当てる必要があります。 特定のサイトレベルのポリシーやユーザー単位のポリシーが割り当てられていない場合は、ダイヤルイン会議での PIN の使用に関するユーザーの権限およびアクセス許可により、グローバルレベルの PIN ポリシーで定義された既定の設定が自動的に適用されます。

ユーザー単位の PIN ポリシーを 1 つ以上作成した後、このトピックの手順を使用してポリシーを割り当て、特定のユーザーが作成したか、特定のユーザーが使用する PIN にサーバーが課す制約を指定します。

ユーザー単位のダイヤルイン会議 PIN ポリシーの作成の詳細については、「 [Lync Server 2013 のダイヤルイン会議 pin 設定を作成または変更する (サイトまたはユーザーのグループ](lync-server-2013-create-or-modify-dial-in-conferencing-pin-settings-for-a-site-or-group-of-users.md))」を参照してください。

## <a name="to-assign-a-per-user-pin-policy"></a>ユーザー単位の PIN ポリシーを割り当てるには

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
    > 同じユーザー単位の PIN ポリシーを複数のユーザーに適用する場合は、検索結果で複数のユーザーを選択して、[<STRONG>アクション</STRONG>] をクリックしてから [<STRONG>ポリシーの割り当て</STRONG>] をクリックします。



7.  [**ポリシーの割り当て**] の [**PIN ポリシー**] で、次のいずれかの手順を実行します。
    

    > [!NOTE]  
    > [<STRONG>ポリシーの割り当て</STRONG>] ダイアログボックスを使用して複数のポリシーを構成できるので、ダイアログボックスのすべてのポリシーに対して、既定で [ <STRONG> &lt;&gt;そのまま保持</STRONG>] が選択されています。 この設定を変更しない場合は、以前にユーザーに割り当てたポリシーを使用して続行します。

    
      - Lync Server 2013 でグローバルレベルのポリシーまたはサイトレベルのポリシー (定義されている場合) のいずれかを自動的に選択できるようにします。
    
      - [**PIN ポリシー**] ページであらかじめ定義した、ユーザー単位の PIN ポリシーの名前をクリックします。
        

        > [!TIP]  
        > 割り当てるポリシーの決定に役立てるために、ポリシー名をクリックしたら [<STRONG>表示</STRONG>] をクリックして、ポリシーで定義されているユーザー権限やアクセス許可を確認します。



8.  終了したら、[**OK**] をクリックします。

## <a name="assigning-a-per-user-pin-policy-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用したユーザー単位の PIN ポリシーの割り当て

Windows PowerShell と**get-cspinpolicy**コマンドレットを使用して、ユーザー単位の PIN ポリシーを割り当てることができます。 このコマンドレットは、Lync Server 2013 管理シェルまたは Windows PowerShell のリモートセッションから実行できます。 リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を[http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)で参照してください。

## <a name="to-assign-a-per-user-pin-policy-to-a-single-user"></a>ユーザー単位の PIN ポリシーを単一のユーザーに割り当てるには

  - 次のコマンドは、ユーザー単位の PIN ポリシー RedmondPinPolicy をユーザー「Ken Myer」に割り当てます。
    
        Grant-CsPinPolicy -Identity "Ken Myer" -PolicyName "RedmondPinPolicy"

## <a name="to-assign-a-per-user-pin-policy-to-multiple-users"></a>ユーザー単位の PIN ポリシーを複数のユーザーに割り当てるには

  - 次のコマンドは、ユーザー単位の PIN ポリシー RedmondUsersPinPolicy を Redmond 市で働くすべてのユーザーに割り当てます。 このコマンドで使用する LdapFilter パラメーターの詳細については、「 [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\))」を参照してください。
    
        Get-CsUser -LdapFilter "l=Redmond" | Grant-CsPinPolicy -PolicyName "RedmondUsersPinPolicy"

## <a name="to-unassign-a-per-user-pin-policy"></a>ユーザー単位の PIN ポリシーを割り当て解除するには

  - 次のコマンドは、Ken Myer に割り当てられたユーザー単位の PIN ポリシーを割り当て解除します。ユーザー単位の PIN ポリシーが割り当て解除された後、Ken Myer は、グローバル ポリシー、または存在する場合は Ken Myer のローカル サイト ポリシーによって、自動的に管理されます。サイト ポリシーは、グローバル ポリシーよりも優先されます。
    
        Grant-CsPinPolicy -Identity "Ken Myer" -PolicyName $Null

詳細については、「 [get-cspinpolicy](https://technet.microsoft.com/library/gg398871\(v=ocs.15\))」を参照してください。

## <a name="see-also"></a>関連項目


[Lync Server 2013 で新しい PIN ポリシーを作成する](lync-server-2013-create-a-new-pin-policy.md)  


[Lync Server 2013 でのユーザー単位のポリシーの割り当て](lync-server-2013-assigning-per-user-policies.md)

