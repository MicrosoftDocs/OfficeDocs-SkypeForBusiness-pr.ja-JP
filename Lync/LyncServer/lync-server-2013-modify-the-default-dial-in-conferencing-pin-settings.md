---
title: 'Lync Server 2013: 既定のダイヤルイン会議の PIN 設定の変更'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Modify the default dial-in conferencing PIN settings
ms:assetid: 2d110e94-ad29-4755-b17f-d8c2da9b78a4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425780(v=OCS.15)
ms:contentKeyID: 48183712
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4ee196fae24ba4a6b7bf8e0ede0bbc0b35a7b3fc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826837"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-the-default-dial-in-conferencing-pin-settings-in-lync-server-2013"></a>Lync Server 2013 での既定のダイヤルイン会議の PIN 設定の変更

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-18_

グローバル PIN ポリシーは、ダイヤルイン会議 PIN のルールを、フォレスト レベルで定義します。 ダイヤルイン会議 PIN のグローバルポリシーを変更するには、次の手順を実行します。 サイトまたはユーザーレベルでダイヤルイン会議の PIN ポリシーを作成または変更する方法について詳しくは、「 [Lync Server 2013 でダイヤルイン会議の pin 設定を作成または変更](lync-server-2013-create-or-modify-dial-in-conferencing-pin-settings-for-a-site-or-group-of-users.md)する」をご覧ください。

<div>

## <a name="to-modify-the-global-pin-policy"></a>グローバル PIN ポリシーを変更するには

1.  RTCUniversalServerAdmins グループのメンバーであるか (または同等のユーザー権限を持っている)、または CsServerAdministrator または CsAdministrator の役割に割り当てられているユーザーアカウントで、Lync Server 2013 を展開したネットワーク上のコンピューターにログオンします。

2.  ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。 Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。

3.  左側のナビゲーション バーで [**会議**]、[**PIN ポリシー**] の順にクリックします。

4.  [**PIN ポリシー**] ページで、[**グローバル**] ポリシー、[**編集**]、[**詳細の表示**] の順にクリックします。

5.  [**PIN ポリシーの編集**] の [**最小 PIN サイズ**] で、許可する PIN の最小文字数を入力または選択します。既定の最小サイズは 5 桁です。

6.  ユーザーがロックアウトされるまでに許可される最大ログオン試行回数を指定できるようにするには、[**最大ログオン試行回数を指定する**] チェック ボックスをオンにします。このオプションをオンにしない場合、許可される最大試行回数は、PIN の桁数に応じて自動的に決定されます。既定では、最大試行回数は自動的に決定されます。

7.  [**最大ログオン試行回数を指定する**] チェック ボックスをオンにした場合は、[**最大ログオン試行回数**] に許可するログオンの最大試行回数を入力または選択します。

8.  PIN の有効期限を設定するには、[**PIN の有効期限を有効にする**] チェック ボックスをオンにします。このオプションをオンにしない限り、PIN が期限切れになることはありません。既定では、PIN に有効期限はありません。

9.  [**PIN の有効期限を有効にする**] チェック ボックスをオンにした場合は、[**PIN の有効期限 (日数)**] で、PIN の有効期限が切れるまでの日数を入力または選択します。

10. [**PIN 履歴の数**] に、PIN の数を入力します。作成した PIN の数がこの数を超えると、PIN を再利用できます。既定では、ユーザーは自分の PIN を再利用できます。

11. PIN に、連続番号や同じ数字の繰り返しなどよくあるパターンの番号を許可するには、[**共通のパターンの許可**] チェック ボックスをオンにします。このオプションをオンにしない場合は、複雑な数字パターンのみが許可されます。既定では、複雑なパターンの数字のみが許可されます。
    
    <div>
    

    > [!IMPORTANT]  
    > 共通のパターンは許可しないことをお勧めします。

    
    </div>

12. [**確定**] をクリックします。

</div>

</div>

<span> </span>

</div>

</div>

</div>

