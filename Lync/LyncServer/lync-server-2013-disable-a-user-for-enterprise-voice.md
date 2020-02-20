---
title: 'Lync Server 2013: エンタープライズ Voip のユーザーの無効化'
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
ms.openlocfilehash: 586f0e699d0cb0cea09b423f25beffd3efe5afdf
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147520"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="disable-a-user-for-enterprise-voice-in-lync-server-2013"></a>Lync Server 2013 でのエンタープライズ Voip のユーザーの無効化

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-21_

Lync Server 2013 に対して有効になっているユーザーアカウントのエンタープライズ Voip を無効にするには、次の手順を使用します。

<div>

## <a name="to-disable-a-user-account-for-enterprise-voice"></a>エンタープライズ Voip のユーザーアカウントを無効にするには

1.  CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。 Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで **[ユーザー]** をクリックします。

4.  **[ユーザーの検索]** ボックスに、有効にするユーザー アカウントの表示名、名、姓、セキュリティ アカウント マネージャー (SAM) のアカウント名、SIP アドレス、または回線 URI (Uniform Resource Identifier) の全体か最初の一部の文字列を入力して、**[検索]** をクリックします。

5.  表で、エンタープライズ Voip を有効にするユーザーアカウントをクリックします。

6.  [**編集**] メニューの [**詳細の表示**] をクリックします。

7.  [**Lync Server ユーザーの編集**] ページの [**テレフォニー**] で、[**エンタープライズ VoIP**] 以外のオプションをクリックします。
    
    <div>
    

    > [!NOTE]  
    > ユーザーが Lync を使用して音声またはビデオ通話を行うことを制限するには、[<STRONG>テレフォニー</STRONG>] で [<STRONG>音声ビデオを無効</STRONG>にする] をクリックします。

    
    </div>

8.  [**確定**] をクリックします。

これで、ユーザーはエンタープライズ Voip 機能を使用できなくなりました。

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 のエンタープライズ Voip でユーザーを有効にする](lync-server-2013-enable-users-for-enterprise-voice.md)  


[Lync Server 2013 でのユーザーのエンタープライズ Voip の管理](lync-server-2013-managing-enterprise-voice-for-users.md)  
[Lync Server 2013 管理シェル](lync-server-2013-lync-server-management-shell.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

