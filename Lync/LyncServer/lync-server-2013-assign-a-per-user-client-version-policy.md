---
title: 'Lync Server 2013: ユーザーごとのクライアントバージョンポリシーの割り当て'
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
ms.openlocfilehash: 77b84c4550d44a09e786d09d093e64cbc1901d91
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134463"
---
# <a name="assign-a-per-user-client-version-policy-in-lync-server-2013"></a>Lync Server 2013 でユーザーごとのクライアントバージョンポリシーを割り当てる

 


クライアントバージョンポリシーは、Lync Server コントロールパネルで構成できるユーザーアカウントの個別の設定の1つです。

1 つ以上のユーザーごとのクライアント バージョン ポリシーを展開するかどうかはオプションです。 グローバル レベルのクライアント バージョン ポリシーのみを展開するか、サイト レベルやプール レベルのクライアント バージョン ポリシーを展開することもできます。 ユーザー単位のポリシーを展開する場合は、ポリシーをユーザー、グループ、または連絡先オブジェクトに明示的に割り当てる必要があります。 特定のサイトレベル、プールレベル、またはユーザーごとのポリシーが割り当てられていない場合、Lync Server 2013 で登録できる既定のクライアントは、グローバルレベルのクライアントバージョンポリシーで定義されています。

ユーザーごとのクライアントバージョンポリシーを1つ以上作成した後、このトピックの手順を使用して、Lync Server への登録を許可するクライアントのバージョンを指定するポリシーを割り当てます。

ユーザーごとのクライアントバージョンポリシーの作成の詳細については、「 [Lync Server 2013 へのログオンに使用できるクライアントアプリケーションを指定](lync-server-2013-specifying-the-client-applications-that-can-be-used-to-log-on-to-lync-server-2013.md)する」を参照してください。

## <a name="to-assign-a-per-user-client-version-policy"></a>ユーザーごとのクライアント バージョン ポリシーを割り当てるには

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
    > 同じユーザーごとのクライアント バージョン ポリシーを複数のユーザーに適用する場合は、検索結果から複数のユーザーを選択し、[<STRONG>アクション</STRONG>] をクリックして、[<STRONG>ポリシーの割り当て</STRONG>] をクリックします。



7.  [**ポリシーの割り当て**] の [**クライアント バージョン ポリシー**] の下で、次のいずれかの操作を行います。
    

    > [!NOTE]  
    > [<STRONG>ポリシーの割り当て</STRONG>] ダイアログボックスを使用して複数のポリシーを構成できるので、ダイアログボックスのすべてのポリシーに対して、既定で [ <STRONG> &lt;&gt;そのまま保持</STRONG>] が選択されています。 この設定を変更しない場合は、以前にユーザーに割り当てたポリシーを使用して続行します。

    
      - Lync Server で、グローバルレベルのポリシーまたは定義されている場合は、サイトレベルのポリシーまたはプールレベルのポリシーのいずれかを自動的に選択できるようにします。
    
      - [**クライアント バージョン ポリシー**] ページで前に定義したユーザーごとのクライアント バージョン ポリシーの名前をクリックします。
        

        > [!TIP]  
        > 割り当てるポリシーの決定に役立てるために、ポリシー名をクリックしたら [<STRONG>表示</STRONG>] をクリックして、ポリシーで定義されているユーザー権限やアクセス許可を確認します。



8.  終了したら、[**OK**] をクリックします。

## <a name="assigning-a-per-user-client-version-policy-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用してユーザーごとのクライアントバージョンポリシーを割り当てる

Grant-CsClientVersionPolicy コマンドレットを使ってユーザーごとのクライアント バージョン ポリシーを割り当てます。 このコマンドレットは、Lync Server 2013 管理シェルまたは Windows PowerShell のリモートセッションから実行できます。 リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を[https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)で参照してください。

## <a name="to-assign-a-per-user-client-version-policy-to-a-single-user"></a>単一のユーザーにユーザーごとのクライアント バージョン ポリシーを割り当てるには


  - 次のコマンドでは、RedmondClientVersionPolicy というユーザーごとのクライアント バージョン ポリシーをユーザー Ken Myer に割り当てます。
    
        Grant-CsClientVersionPolicy -Identity "Ken Myer" -PolicyName "RedmondClientVersionPolicy"

## <a name="to-assign-a-per-user-client-version-policy-to-multiple-users"></a>複数のユーザーにユーザーごとのクライアント バージョン ポリシーを割り当てるには

  - このコマンドでは、RedmondVoicePolicy という音声ポリシーを現在割り当てられているすべてのユーザーに、RedmondClientVersionPolicy というユーザーごとのクライアント バージョン ポリシーを割り当てます。 このコマンドで使用される Filter パラメーターの詳細については、「 [Get-help user](https://technet.microsoft.com/library/gg398125\(v=ocs.15\))コマンドレットのドキュメント」を参照してください。
    
        Get-CsUser -Filter {VoicePolicy -eq "RedmondVoicePolicy"} | Grant-CsClientVersionPolicy -PolicyName "RedmondClientVersionPolicy"

## <a name="to-unassign-a-per-user-client-version-policy"></a>ユーザーごとのクライアント バージョン ポリシーの割り当てを解除するには

  - 次のコマンドは、以前に Ken Myer に割り当てられたすべてのユーザーごとのクライアント バージョン ポリシーを解除します。ユーザーごとのポリシーが解除された後、Ken Myer はグローバル ポリシー、ローカル サイト ポリシー (存在する場合)、またはレジストラーに割り当てられたサービス スコープ ポリシーによって自動的に管理されることになります。サービス スコープ ポリシーはサイト ポリシーより優先され、サイト ポリシーはグローバル ポリシーより優先されます。
    
        Grant-CsClientVersionPolicy -Identity "Ken Myer" -PolicyName $Null

詳細については、 [Grant-CsClientVersionPolicy](https://technet.microsoft.com/library/gg412903\(v=ocs.15\))コマンドレットのヘルプトピックを参照してください。

## <a name="see-also"></a>関連項目


[Lync Server 2013 でのユーザー単位のポリシーの割り当て](lync-server-2013-assigning-per-user-policies.md)  
[Lync Server 2013 でのデバイス、電話、クライアントアプリケーションの管理](lync-server-2013-managing-devices-phones-and-client-applications.md)

