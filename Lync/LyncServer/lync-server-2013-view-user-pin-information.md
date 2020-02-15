---
title: 'Lync Server 2013: ユーザー PIN 情報の表示'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View user PIN information
ms:assetid: 59e38117-8112-4851-82ac-a746ffa0f89d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688067(v=OCS.15)
ms:contentKeyID: 49733661
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b338691813980130d60cd5424cc87dd9d0220f5f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029148"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-user-pin-information-in-lync-server-2013"></a>Lync Server 2013 でユーザー PIN 情報を表示する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-23_

認証されたユーザーとしてダイヤルイン会議に参加するには、Lync Server 2013 ユーザーに Active Directory ドメインサービス (AD DS) の資格情報が必要です。個人識別番号 (PIN) が必要です。 Lync Server 2013 コントロールパネルからユーザーの PIN 情報を表示することができます。

<div>


> [!NOTE]  
> PIN が設定されているかどうかや PIN の最終変更日時などの PIN 状態情報を表示することはできますが、PIN の状態を調べても最新の PIN は確認できません。 ユーザーが PIN をなくした場合は、「 <A href="lync-server-2013-set-a-user-s-dial-in-conferencing-pin.md">Lync 2013 Server でユーザーのダイヤルイン会議 PIN を設定</A>する」の手順に従って pin をリセットできます。



</div>

<div>

## <a name="to-view-a-users-pin-in-lync-server-control-panel"></a>Lync Server コントロールパネルでユーザーの PIN を表示するには

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
    
    <div>
    

    > [!NOTE]  
    > PIN がロックされている場合は、ロックを解除しないと PIN を設定できません。PIN のロックを解除するには、ユーザーをクリックし、[<STRONG>アクション</STRONG>] をクリックして、[<STRONG>PIN のロック解除</STRONG>] をクリックします。

    
    </div>

6.  検索結果でユーザーをクリックし、[**アクション**] をクリックして、[**PIN の状態を表示**] をクリックします。

</div>

<div>

## <a name="viewing-user-pin-information-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用してユーザー PIN 情報を表示する

Get-CsClientPinInfo コマンドレットを使用して、ユーザーの PIN 情報を表示できます。 このコマンドレットは、Lync Server 2013 管理シェルから実行するか、Windows PowerShell のリモートセッションから実行できます。 リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を[http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)で参照してください。

<div>

## <a name="to-view-user-pin-information"></a>ユーザーの PIN 情報を表示するには

  - ユーザーの PIN 情報を表示するには、Lync Server 管理シェルで次のようなコマンドを入力し、ENTER キーを押します。
    
        Get-CsClientPinInfo -Identity "Ken Myer"
    
    次のような情報が表示されます。
    
        Identity          : sip:kenmyer@litwareinc.com
        IsPinSet          : False
        IsLockedOut       : False
        LastPinChangeTime : 9/25/2012 1:35:03 PM
        PinExpirationTime :

</div>

詳細については、 [get-csconferencedisclaimer](https://docs.microsoft.com/powershell/module/skype/Get-CsConferenceDisclaimer)コマンドレットのヘルプトピックを参照してください。

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 でユーザーのダイヤルイン会議の PIN を設定する](lync-server-2013-set-a-user-s-dial-in-conferencing-pin.md)  
[Lync Server 2013 でのユーザー PIN のロックまたはロック解除](lync-server-2013-lock-or-unlock-a-user-pin.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

