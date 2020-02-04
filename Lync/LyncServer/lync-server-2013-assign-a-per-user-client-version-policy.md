---
title: 'Lync Server 2013: ユーザーごとのクライアントバージョンポリシーを割り当てる'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a per-user client version policy
ms:assetid: f7e8ba2f-62dc-4e7d-8b63-682986f10240
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182607(v=OCS.15)
ms:contentKeyID: 48185868
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e509427b6d2651f84b96a96c87fbe7cfd6177a7d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738377"
---
# <a name="assign-a-per-user-client-version-policy-in-lync-server-2013"></a>Lync Server 2013 でユーザーごとのクライアントバージョンポリシーを割り当てる

 


クライアントバージョンポリシーは、Lync Server コントロールパネルで構成できるユーザーアカウントの個別の設定の1つです。

1つまたは複数のユーザーごとのクライアントバージョンポリシーの展開は任意です。 グローバルレベルのクライアントバージョンポリシー、またはサイトレベルまたはプールレベルのクライアントバージョンポリシーのみを展開することもできます。 ユーザー単位のポリシーを展開する場合は、ポリシーをユーザー、グループ、または連絡先オブジェクトに明示的に割り当てる必要があります。 特定のサイトレベル、プールレベル、またはユーザーごとのポリシーが割り当てられていない場合、Lync Server 2013 への登録が許可されている既定のクライアントは、グローバルレベルクライアントのバージョンポリシーで定義されたものです。

ユーザーごとに1つ以上のバージョンのポリシーを作成した後、このトピックの手順を使用して、Lync Server への登録を許可するクライアントのバージョンを指定するポリシーを割り当てます。

ユーザーごとのクライアントバージョンポリシーの作成について詳しくは、「 [Lync Server 2013 へのログオンに使用できるクライアントアプリケーションの指定](lync-server-2013-specifying-the-client-applications-that-can-be-used-to-log-on-to-lync-server-2013.md)」をご覧ください。

## <a name="to-assign-a-per-user-client-version-policy"></a>ユーザーごとのクライアントバージョンポリシーを割り当てるには

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
    > 同じユーザーごとのクライアントバージョンポリシーを複数のユーザーに適用する場合は、検索結果で複数のユーザーを選び、[<STRONG>操作</STRONG>] をクリックして、[<STRONG>ポリシーの割り当て</STRONG>] をクリックします。



7.  [**ポリシーの割り当て**] の [**クライアントのバージョンポリシー**] で、次のいずれかの操作を行います。
    

    > [!NOTE]  
    > [<STRONG>ポリシーの割り当て</STRONG>] ダイアログボックスを使って構成できる複数のポリシーがあるため、ダイアログボックスのすべてのポリシーで既定で [ <STRONG> &lt;その&gt;まま</STRONG>実行する] が選択されています。 この設定を変更しないで、以前にユーザーに割り当てたポリシーを使用して続行します。

    
      - [グローバルレベルポリシー] または [定義されている場合は、サイトレベルポリシーまたはプールレベルポリシー] のいずれかを Lync Server に自動的に選択させることができます。
    
      - [**クライアントバージョンポリシー** ] ページで以前に定義したユーザーごとのクライアントバージョンポリシーの名前をクリックします。
        

        > [!TIP]  
        > 割り当てるポリシーの決定に役立てるために、ポリシー名をクリックしたら [<STRONG>表示</STRONG>] をクリックして、ポリシーで定義されているユーザー権限やアクセス許可を確認します。



8.  終了したら、[**OK**] をクリックします。

## <a name="assigning-a-per-user-client-version-policy-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用して、ユーザーごとのクライアントバージョンポリシーを割り当てる

Grant-CsClientVersionPolicy コマンドレットを使用して、ユーザーごとのクライアントバージョンポリシーを割り当てることができます。 このコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモートセッションから実行できます。 リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を[http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)で参照してください。

## <a name="to-assign-a-per-user-client-version-policy-to-a-single-user"></a>ユーザーごとのクライアントバージョンポリシーを1人のユーザーに割り当てるには

  - 次のコマンドは、ユーザーごとのバージョンのポリシー RedmondClientVersionPolicy を Ken Myer に割り当てます。
    
        Grant-CsClientVersionPolicy -Identity "Ken Myer" -PolicyName "RedmondClientVersionPolicy"

## <a name="to-assign-a-per-user-client-version-policy-to-multiple-users"></a>ユーザーごとのクライアントバージョンポリシーを複数のユーザーに割り当てるには

  - このコマンドは、ボイスポリシー RedmondVoicePolicy を現在割り当てられているすべてのユーザーに、ユーザー別クライアントバージョンポリシー RedmondClientVersionPolicy を割り当てます。 このコマンドで使用される Filter パラメーターの詳細については、「[ユーザーの取得](https://technet.microsoft.com/en-us/library/gg398125\(v=ocs.15\))」コマンドレットのドキュメントを参照してください。
    
        Get-CsUser -Filter {VoicePolicy -eq "RedmondVoicePolicy"} | Grant-CsClientVersionPolicy -PolicyName "RedmondClientVersionPolicy"

## <a name="to-unassign-a-per-user-client-version-policy"></a>ユーザーごとのクライアントバージョンポリシーを割り当て解除するには

  - 次のコマンドは、以前に Ken Myer に割り当てられていたユーザーごとのクライアントバージョンポリシーを割り当て解除します。 ユーザーごとのポリシーが割り当てられていない場合、Ken Myer はグローバルポリシー、彼のローカルサイトポリシー (存在する場合)、またはレジストラーに割り当てられているサービススコープポリシーを使って、自動的に管理されます。 サービスのスコープポリシーは、どのサイトポリシーよりも優先され、サイトポリシーはグローバルポリシーよりも優先されます。
    
        Grant-CsClientVersionPolicy -Identity "Ken Myer" -PolicyName $Null

詳細については、「 [Grant-CsClientVersionPolicy](https://technet.microsoft.com/en-us/library/gg412903\(v=ocs.15\)) 」コマンドレットのヘルプトピックを参照してください。

## <a name="see-also"></a>関連項目


[Lync Server 2013 でのユーザーごとのポリシーの割り当て](lync-server-2013-assigning-per-user-policies.md)  
[Lync Server 2013 でのデバイス、電話、クライアント アプリケーションの管理](lync-server-2013-managing-devices-phones-and-client-applications.md)

