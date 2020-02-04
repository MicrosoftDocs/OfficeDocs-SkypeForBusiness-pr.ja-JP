---
title: 'Lync Server 2013: Lync Room System 管理 Web ポータルをインストールする'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing the Lync Room System Administrative Web Portal
ms:assetid: dd19e368-c338-4e21-a40d-6439d46a9748
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn436326(v=OCS.15)
ms:contentKeyID: 56737622
ms.date: 04/09/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dcfc78429ef021afcb0ed286ad86a39e63bfbf62
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725987"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-the-lync-room-system-administrative-web-portal-in-lync-server-2013"></a>Installing the Lync Room System Administrative Web Portal in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2015-04-09_

Microsoft Lync Room System 管理 Web ポータルは、Microsoft ダウンロードセンターからダウンロードでき[http://go.microsoft.com/fwlink/p/?LinkId=324044](http://go.microsoft.com/fwlink/p/?linkid=324044)ます。

Lync Room System 管理 Web ポータルをインストールするには、次の手順を使用します。

1.  Lync Server 管理シェルで次のコマンドレットを実行して、信頼されているアプリケーションポートを構成します。
    
        Set-CsWebServer -Identity POOLFQDN -MeetingRoomAdminPortalInternalListeningPort 4456 -MeetingRoomAdminPortalExternalListeningPort 4457

2.  会議室ポータルをインストールするには、 **LyncRoomAdminPortal**をダウンロードしてから、管理者として実行します。

3.  Web.config ファイルを次の場所から開きます。
    
    % Program Files%\\Microsoft Lync Server 2013\\Web コンポーネント\\会議室ポータル\\の\\Int ハンドラー\\

4.  Web.config ファイルで、「Lync Room System 管理ポータルの前提条件を設定する」のセクションの手順2で作成したユーザー名に PortalUserName を変更します (手順は LRSApp の推奨名)。
    
        <add key="PortalUserName" value="sip:LRSApp@domain.com" />

5.  LRS 管理ポータルは信頼できるアプリケーションであるため、ポータル構成でパスワードを入力する必要はありません。 このユーザーがローカル レジストラーとは別のレジストラーを使用している場合、Web.Config ファイルで次の行を追加してレジストラを指定する必要があります。
    
        <add key="PortalUserRegistrarFQDN" value="pool-xxxx.domain.com" />

6.  5061 以外のポートが使用されている場合は、Web.Config ファイルに次の行を追加します。
    
        <add key="PortalUserRegistrarPort" value="5061" />

<div>

## <a name="verifying-installation-of-the-lync-room-system-administrative-web-portal"></a>Lync Room System 管理 Web ポータルのインストールを確認する

Lync Room System 管理 Web ポータルのインストールを確認するには、次の操作を行います。


1.  フロントエンド サーバーで、次の URL を参照します。
    
    https://\<fe-サーバー\>/lrs
    
    下記の画像のように、エラーが表示されないようにします。
    
    ![Lync Room System、管理用ポータル サインイン画面](images/Dn436326.050bcf70-2f3b-46b2-9b96-ebd12679b713(OCS.15).png "Lync Room System、管理用ポータル サインイン画面")

2.  エラーが表示されない場合は、トポロジ内の他のいずれかのコンピューターから次の URL へのアクセスを試行します。
    
    https://\<fe-サーバー\>/lrs
    
    このページにアクセスするには、「」の「自動クライアントサインイン用の DNS レコード」の説明に従って DNS レコードを[http://go.microsoft.com/fwlink/p/?LinkId=318056](http://go.microsoft.com/fwlink/p/?linkid=318056)追加する必要があります。

</div>

</div>

<span> </span>

</div>

</div>

</div>

