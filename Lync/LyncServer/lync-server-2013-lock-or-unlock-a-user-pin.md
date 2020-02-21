---
title: 'Lync Server 2013: ユーザー PIN のロックまたはロック解除'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lock or unlock a user PIN
ms:assetid: 3d293a8a-e182-4547-8b06-2603c3c77329
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688028(v=OCS.15)
ms:contentKeyID: 49733618
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 698bbb2138978cea9ca5b2aa75b5370ea7e11c14
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42186400"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="lock-or-unlock-a-user-pin-in-lync-server-2013"></a>Lync Server 2013 でのユーザー PIN のロックまたはロック解除

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-23_

Lync Server 2013 コントロールパネルの [**ユーザー** ] セクションから、ユーザーの PIN をロックまたはロック解除することができます。

<div>

## <a name="to-lock-a-users-pin-in-lync-server-control-panel"></a>Lync Server コントロールパネルでユーザーの PIN をロックするには

1.  CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。 Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで [**ユーザー**] をクリックします。

4.  ユーザーを探すには、次のどちらかの方法を使用します。
    
      - [**ユーザーの検索**] ボックスに、表示名、名、姓、セキュリティ アカウント マネージャー (SAM) のアカウント名、SIP アドレス、またはユーザー アカウントの回線 URI (Uniform Resource Identifier) の全体か最初の一部の文字列を入力して、[**検索**] をクリックします。
    
      - 保存したクエリがある場合は、[**クエリを開く**] アイコンをクリックし、[**開く**] ダイアログ ボックスを使用してそのクエリ (.usf ファイル) を取得して、[**検索**] をクリックします。

5.  (オプション) 結果を絞り込むための追加の検索条件を次のように指定します。
    
    1.  [**フィルターの追加**] をクリックします。
    
    2.  ユーザーのプロパティを入力するか、ドロップダウン リストの矢印をクリックして選択し、プロパティを指定します。
    
    3.  [**次の値に等しい**] ドロップダウン リストで、演算子 (例: [**次の値に等しい**] または [**次の値に等しくない**]) をクリックします。
    
    4.  選択したユーザー プロパティに応じて、検索結果のフィルターに使用する条件を入力するか、ドロップダウン リストの矢印をクリックして指定します。
        
        <div>
        

        > [!TIP]  
        > クエリにその他の検索句を追加するには、[<STRONG>フィルターの追加</STRONG>] をクリックします。

        
        </div>
    
    5.  [**検索**] をクリックします。
    
    6.  ユーザーをクリックし、[**アクション**] をクリックして、[**PIN のロック**] をクリックします。

</div>

<div>

## <a name="to-unlock-a-users-pin-in-lync-server-control-panel"></a>Lync Server コントロールパネルでユーザーの PIN のロックを解除するには

1.  CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。 Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで [**ユーザー**] をクリックします。

4.  ユーザーを探すには、次のどちらかの方法を使用します。
    
      - [**ユーザーの検索**] ボックスに、表示名、名、姓、セキュリティ アカウント マネージャー (SAM) のアカウント名、SIP アドレス、またはユーザー アカウントの回線 URI (Uniform Resource Identifier) の全体か最初の一部の文字列を入力して、[**検索**] をクリックします。
    
      - 保存したクエリがある場合は、[**クエリを開く**] アイコンをクリックし、[**開く**] ダイアログ ボックスを使用してそのクエリ (.usf ファイル) を取得して、[**検索**] をクリックします。

5.  (オプション) 結果を絞り込むための追加の検索条件を次のように指定します。
    
    1.  [**フィルターの追加**] をクリックします。
    
    2.  ユーザーのプロパティを入力するか、ドロップダウン リストの矢印をクリックして選択し、プロパティを指定します。
    
    3.  [**次の値に等しい**] ドロップダウン リストで、演算子 (例: [**次の値に等しい**] または [**次の値に等しくない**]) をクリックします。
    
    4.  選択したユーザー プロパティに応じて、検索結果のフィルターに使用する条件を入力するか、ドロップダウン リストの矢印をクリックして指定します。
        
        <div>
        

        > [!TIP]  
        > クエリにその他の検索句を追加するには、[<STRONG>フィルターの追加</STRONG>] をクリックします。

        
        </div>
    
    5.  [**検索**] をクリックします。
    
    6.  ユーザーをクリックし、[**アクション**] をクリックして、[**PIN のロック解除**] をクリックします。

</div>

<div>

## <a name="locking-and-unlocking-user-pins-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用したユーザー Pin のロックとロック解除

Windows PowerShell および Lock-CsClientPin および Unlock-CsClientPin コマンドレットを使用すると、ユーザー Pin をロックおよびロック解除することができます。 これらのコマンドレットは、Lync Server 2013 管理シェル、または Windows PowerShell のリモートセッションから実行できます。 リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を[https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)で参照してください。

<div>

## <a name="to-lock-a-user-pin"></a>ユーザー PIN をロックするには

  - ユーザー PIN をロックするには、Lock-CsClientPin コマンドレットを使用します。次に例を示します。
    
        Lock-CsClientPin -Identity "Ken Myer"

</div>

<div>

## <a name="to-unlock-a-user-pin"></a>ユーザー PIN のロックを解除するには

  - ユーザー PIN のロックを解除するには、Unlock-CsClientPin コマンドレットを使用します。次に例を示します。
    
        Unlock-CsClientPin -Identity "Ken Myer"

</div>

詳細については、「 [Lock-CsClientPin](https://docs.microsoft.com/powershell/module/skype/Lock-CsClientPin) 」および「 [Unlock-csclientpin](https://docs.microsoft.com/powershell/module/skype/Unlock-CsClientPin) 」のコマンドレットのヘルプトピックを参照してください。

</div>

</div>

<span> </span>

</div>

</div>

</div>

