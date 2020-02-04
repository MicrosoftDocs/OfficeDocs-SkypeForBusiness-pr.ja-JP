---
title: 'Lync Server 2013: ユーザーのダイヤルイン会議 PIN を設定する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Set a user's dial-in conferencing PIN
ms:assetid: 4252b5a5-4267-4513-b18e-0253a8d66f72
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520985(v=OCS.15)
ms:contentKeyID: 48183970
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ab97b3efe350ef82527262103e9b00104990245a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764693"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="set-a-users-dial-in-conferencing-pin-in-lync-server-2013"></a>Lync Server 2013 でユーザーのダイヤルイン会議の PIN を設定する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2014-06-10_

認証されたユーザーとしてダイヤルイン会議に参加するには、Lync Server 2013 ユーザーの Active Directory ドメインサービス (AD DS) の資格情報に暗証番号 (PIN) が必要です。 ユーザーがダイヤルイン会議の PIN を忘れた場合、または Lync Server を使用して PIN を設定していない場合は、ユーザーの PIN を Lync Server コントロールパネルから設定できます。 PIN は自動で生成することも手動で作成することもできます。

<div>


> [!NOTE]  
> 最小サイズなど、PIN の具体的な特性は、ポリシーとして構成できます。 グローバル ポリシーに加えて、個々のサイトまたはユーザーを対象にした PIN ポリシーを構成できます。 PIN ポリシーの構成の詳細については、「 <A href="lync-server-2013-configure-dial-in-conferencing-personal-identification-number-pin-rules.md">Lync Server 2013 でダイヤルイン会議の暗証番号 (PIN) ルールを構成する</A>」を参照してください。



</div>

<div>

## <a name="to-set-a-users-pin"></a>ユーザーの PIN を設定するには

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

6.  検索結果のユーザーをクリックし、[**アクション**] をクリックして、[**暗証番号 (PIN) の設定**] をクリックします。

7.  [**暗証番号 (PIN) の設定**] ダイアログ ボックスで、次のどちらかの手順を実行します。
    
      - Lync Server 2013 でユーザーの PIN を生成できるようにするには、[**自動的に有効な pin を生成**する] (既定) を選択します。
    
      - 自分の PIN を作成するには、[**特定の PIN を手動で入力**] をクリックして、テキスト ボックスをクリックし、PIN のポリシー設定で指定されている PIN の要件を満たす PIN を入力します。

8.  [**OK**] をクリックします。

9.  [**暗証番号 (PIN) の設定**] で、次のどちらかの手順を実行します。
    
      - [**PIN の表示**] チェック ボックスをオンにして PIN を表示し、PIN をコピーし、組織で推奨される方法を使用しているユーザーに伝えます。
    
      - PIN を電子メールで送信するには、[**新しい PIN をユーザーに送信するために電子メール アプリケーションを開く**] をクリックします。使用している電子メール クライアントが Microsoft Office Outlook の場合、PIN は新しい電子メール メッセージに自動的にコピーされます。他の電子メール クライアントを使用している場合は、[**PIN の表示**] チェック ボックスをオンにして PIN を表示し、電子メール メッセージにコピーしてください。

10. [**閉じる**] をクリックします。

</div>

<div>

## <a name="assigning-a-user-pin-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用してユーザー PIN を割り当てる

Set-CsClientPin コマンドレットを使用して、PIN 番号を割り当てることができます。 このコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモートセッションから実行できます。 リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を[http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)で参照してください。

<div>

## <a name="to-auto-assign-a-pin-number-to-a-user"></a>PIN 番号をユーザーに割り当てるには

  - 次のコマンドでは、PIN 番号を Ken Myer というユーザーに割り当てます。 Pin パラメーターが含まれていないため、Lync Server によって PIN 番号が自動的に生成され、割り当てられます。
    
        Set-CsClientPin -Identity "Ken Myer" 

</div>

<div>

## <a name="to-assign-a-specific-pin-number-to-a-user"></a>特定の PIN 番号をユーザーに割り当てるには

  - このコマンドでは、Pin パラメーターを使用して PIN 番号 121989 を Ken Myer というユーザーに割り当てます。
    
        Set-CsClientPin -Identity "Ken Myer" -Pin 121989

</div>

詳細については、「 [Set-CsClientPin](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPin) 」コマンドレットのヘルプトピックを参照してください。

</div>

<div>

## <a name="see-also"></a>関連項目


[ダイヤルイン アクセス番号](https://technet.microsoft.com/en-us/library/gg133674\(v=ocs.15\))  


[Lync Server 2013 でダイヤルイン会議の暗証番号 (PIN) ルールを構成する](lync-server-2013-configure-dial-in-conferencing-personal-identification-number-pin-rules.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

