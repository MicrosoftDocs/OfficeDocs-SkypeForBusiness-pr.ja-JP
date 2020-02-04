---
title: 'Lync Server 2013: エンタープライズ Voip のユーザーを無効にする'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Disable a user for Enterprise Voice
ms:assetid: 462002d8-21df-4d77-bf7f-4d059d6a4bb2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688043(v=OCS.15)
ms:contentKeyID: 49733635
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8f89b40a7398f35efab418fac7be92536ec17270
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762215"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="disable-a-user-for-enterprise-voice-in-lync-server-2013"></a>Lync Server 2013 でエンタープライズ Voip のユーザーを無効にする

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-09-21_

Lync Server 2013 用に有効になっているユーザーアカウントのエンタープライズボイスを無効にするには、次の手順を使用します。

<div>

## <a name="to-disable-a-user-account-for-enterprise-voice"></a>エンタープライズ Voip のユーザーアカウントを無効にするには

1.  CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。 Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。

3.  左側のナビゲーション バーで [**ユーザー**] をクリックします。

4.  [**ユーザーの検索**] ボックスに、有効にするユーザー アカウントの表示名、名、姓、セキュリティ アカウント マネージャー (SAM) のアカウント名、SIP アドレス、または回線 URI (Uniform Resource Identifier) の全体か先頭の部分の文字列を入力して、[**検索**] をクリックします。

5.  表で、エンタープライズ Voip を有効にするユーザーアカウントをクリックします。

6.  [**編集**] メニューの [**詳細の表示**] をクリックします。

7.  [ **Lync Server ユーザーの編集**] ページの [**テレフォニー**] で、[**エンタープライズ voip**] 以外のオプションをクリックします。
    
    <div>
    

    > [!NOTE]  
    > ユーザーが Lync を使って音声またはビデオ通話を発信することを制限するには、[<STRONG>テレフォニー</STRONG>] で [<STRONG>オーディオ/ビデオを無効</STRONG>にする] をクリックします。

    
    </div>

8.  [**コミット**] をクリックします。

これで、ユーザーはエンタープライズ Voip 機能を使用できなくなります。

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 でのエンタープライズ Voip のユーザーの有効化](lync-server-2013-enable-users-for-enterprise-voice.md)  


[Lync Server 2013 でのユーザーのエンタープライズボイスの管理](lync-server-2013-managing-enterprise-voice-for-users.md)  
[Lync Server 2013 管理シェル](lync-server-2013-lync-server-management-shell.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

