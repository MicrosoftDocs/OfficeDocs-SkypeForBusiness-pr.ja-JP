---
title: Lync Room System Administrative Web Portal のインストール
TOCTitle: Lync Room System Administrative Web Portal のインストール
ms:assetid: dd19e368-c338-4e21-a40d-6439d46a9748
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Dn436326(v=OCS.15)
ms:contentKeyID: 59602764
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Room System Administrative Web Portal のインストール

 

_**トピックの最終更新日:** 2016-12-08_

Microsoft Lync Room System Administrative Web Portal は、Microsoft Download Center[http://go.microsoft.com/fwlink/p/?LinkId=324044](http://go.microsoft.com/fwlink/p/?linkid=324044) からダウンロードできます。

Lync Room System Administrative Web Portal をインストールするには、次の手順を使用します。

1.  Lync Server 管理シェル で次のコマンドレットを実行し、信頼されたアプリケーションのポートを構成します。
    
        Set-CsWebServer -Identity POOLFQDN -MeetingRoomAdminPortalInternalListeningPort 4456 -MeetingRoomAdminPortalExternalListeningPort 4457

2.  Meeting Room Portal をインストールするには、**LyncRoomAdminPortal.exe** をダウンロードして管理者として実行します。

3.  次の場所から Web.config ファイルを開きます。
    
    %Program Files%\\Microsoft Lync Server 2013\\Web Components\\Meeting Room Portal\\Int\\Handler\\

4.  Web.Config ファイルで、PortalUserName をセクション「Lync Room System Admin Portal の前提条件の構成」の手順 2. で作成したユーザー名に変更します (この手順での推奨名は LRSApp です)。
    
        <add key="PortalUserName" value="sip:LRSApp@domain.com" />

5.  LRS Admin Portal は信頼されたアプリケーションであるため、ポータル構成でパスワードを入力する必要はありません。このユーザーがローカル レジストラー以外のレジストラーを使用している場合は、Web.Config ファイルに次の行を追加して、このユーザー用のレジストラーを指定する必要があります。
    
        <add key="PortalUserRegistrarFQDN" value="pool-xxxx.domain.com" />

6.  5061 以外のポートが使用されている場合は、Web.Config ファイルに次の行を追加します。
    
        <add key="PortalUserRegistrarPort" value="5061" />

## Lync Room System Administrative Web Portal のインストールの検証

Lync Room System Administrative Web Portal のインストールを検証するには、次の手順を実行します。


1.  フロントエンド サーバーで、次の URL を表示します。
    
    https://\<fe-server\>/lrs
    
    次の画像のように、エラーは表示されません。
    
    ![Lync Room System、管理用ポータル サインイン画面](images/Dn436326.050bcf70-2f3b-46b2-9b96-ebd12679b713(OCS.15).png "Lync Room System、管理用ポータル サインイン画面")

2.  エラーが表示されない場合は、トポロジ内の別のコンピューターから次の URL にアクセスしてみます。
    
    https://\<fe-server\>/lrs
    
    ページにアクセスするには、「クライアントの自動サインインに必要な DNS レコード (英語)」([http://go.microsoft.com/fwlink/p/?LinkId=318056](http://go.microsoft.com/fwlink/p/?linkid=318056)) に記載されている方法で、DNS レコードを追加する必要があります。

