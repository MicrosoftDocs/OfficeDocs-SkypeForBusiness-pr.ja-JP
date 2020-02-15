---
title: 'Lync Server 2013: Lync Room System 管理 Web ポータルのインストール'
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
ms.openlocfilehash: 6af0f52b940e9bcfb78048ef3a2c60f09d265073
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045239"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-the-lync-room-system-administrative-web-portal-in-lync-server-2013"></a>Lync Server 2013 での Lync Room System 管理 Web ポータルのインストール

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2015-04-09_

Microsoft Lync Room System 管理 Web ポータルは、Microsoft ダウンロードセンターからダウンロードでき[http://go.microsoft.com/fwlink/p/?LinkId=324044](http://go.microsoft.com/fwlink/p/?linkid=324044)ます。

Lync Room System 管理 Web ポータルをインストールするには、次の手順を実行します。

1.  Lync Server 管理シェルで次のコマンドレットを実行して、信頼されたアプリケーションポートを構成します。
    
        Set-CsWebServer -Identity POOLFQDN -MeetingRoomAdminPortalInternalListeningPort 4456 -MeetingRoomAdminPortalExternalListeningPort 4457

2.  会議室ポータルをインストールするには、 **LyncRoomAdminPortal**をダウンロードして、管理者として実行します。

3.  Web.config ファイルを次の場所から開きます。
    
    % Program Files%\\Microsoft Lync Server 2013\\Web コンポーネント\\ミーティングルームポータル\\の\\Int ハンドラー\\

4.  Web.config ファイルで、「Lync Room System 管理ポータルの前提条件の構成」のセクションの「手順2で作成したユーザー名に PortalUserName を変更します (この手順で推奨される名前は LRSApp です)。
    
        <add key="PortalUserName" value="sip:LRSApp@domain.com" />

5.  LRS 管理ポータルは信頼されたアプリケーションであるため、ポータル構成でパスワードを指定する必要はありません。 このユーザーがローカルレジストラーとは別のレジストラーを使用している場合は、Web.config ファイルに次の行を追加して、レジストラーを指定する必要があります。
    
        <add key="PortalUserRegistrarFQDN" value="pool-xxxx.domain.com" />

6.  使用しているポートが5061以外の場合は、web.config ファイルに次の行を追加します。
    
        <add key="PortalUserRegistrarPort" value="5061" />

<div>

## <a name="verifying-installation-of-the-lync-room-system-administrative-web-portal"></a>Lync Room System 管理 Web ポータルのインストールの確認

Lync Room System 管理 Web ポータルのインストールを確認するには、次の手順を実行します。


1.  フロントエンドサーバーで、次の URL を参照します。
    
    https://\<fe-サーバー\>/lrs
    
    次の図に示すように、エラーは表示されません。
    
    ![Lync Room System 管理者ポータルのサインイン画面](images/Dn436326.050bcf70-2f3b-46b2-9b96-ebd12679b713(OCS.15).png "Lync Room System 管理者ポータルのサインイン画面")

2.  エラーが表示されない場合は、トポロジ内の他のコンピュータから次の URL にアクセスしてみてください。
    
    https://\<fe-サーバー\>/lrs
    
    ページにアクセスするには、「」の「自動クライアントサインインに必要な DNS レコード」で説明されているように[http://go.microsoft.com/fwlink/p/?LinkId=318056](http://go.microsoft.com/fwlink/p/?linkid=318056)、dns レコードを追加する必要があります。

</div>

</div>

<span> </span>

</div>

</div>

</div>

