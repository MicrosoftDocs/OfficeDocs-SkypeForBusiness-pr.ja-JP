---
title: Lync Windows ストア アプリの要件
TOCTitle: Lync Windows ストア アプリの要件
ms:assetid: 5f2e0a40-8450-4f61-b6f6-913fc1906020
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ823129(v=OCS.15)
ms:contentKeyID: 52056602
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Windows ストア アプリの要件

 

_**トピックの最終更新日:** 2016-12-08_

Lync Server を社内で展開している組織の場合、Lync Windows ストア アプリをサポートするには、次の要件を満たす必要があります。

> [!NOTE]
> Lync Server 2010 では、Lync Server 2010: 2012 年 2 月の累積更新プログラム (<a href="http://go.microsoft.com/fwlink/?linkid=3052%26kbid=2670352" class="uri">http://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2670352</a>) 以降を、すべてのサーバー上で実行します。ユーザーが会議に参加できるようにするには、Lync Server 2010: 2012 年 10 月の累積更新プログラム (<a href="http://go.microsoft.com/fwlink/?linkid=3052%26kbid=2737915" class="uri">http://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2737915</a>) をサーバー上で実行します。


  - 自動検出、Lync Web App、Web チケットの各サービスをサーバー上で有効にします。

  - フロント エンド サーバーまたはフロント エンド プールで証明書の認証を有効にします (フロント エンド サーバーまたはフロント エンド プールでのユーザー登録プロセスは通常、レジストラーと呼ばれます)。詳しくは、「[レジストラー構成設定の作成](lync-server-2013-create-registrar-configuration-settings.md)」をご覧ください。

  - 自動検出サービス用の DNS エイリアス (CNAME) リソース レコードを発行します。

  - Lync サーバーに発行された証明書の証明書失効リスト (CRL) 配布ポイント (CDP) が、LDAP リソースではなく HTTP リソースを指していることの確認は、要件ではなくなりました。ただし、クライアント コンピューターに最新の Windows の更新プログラムがインストールされていることを確認します。

  - エンタープライズ内の HTTP プロキシを、Lync サーバーに関連した HTTP トラフィックを許可するように構成します。必要に応じて自動検出、Lync Web App、Web チケット サービスの例外を追加します。

  - クライアントに Windows 8.1 と最新バージョンの Lync Windows ストア アプリをインストールして、複数ドメインを使用した場合に通常発生するサインインの問題 (たとえば、SIP URI が <strong>userA@domainZ.com</strong> であるがエッジ サーバーが **sip.domainX.com** の場合など) を解決します。

組織が Lync Online または Office 365 に登録して独自のドメイン名を使っている場合は、Lync サーバーを自動検出するようにネットワークをセットアップするために追加の手順を実行する必要があります。ネットワーク構成の要件は、Lync Windows ストア アプリとモバイル デバイスの Lync で同じです。Office 365 wiki の記事「Set up Lync mobile devices」の「Set up your network」([http://go.microsoft.com/fwlink/?LinkId=271822](http://go.microsoft.com/fwlink/?linkid=271822)) に示されている手順に従ってください。

## 関連項目

#### 概念

[Lync Windows ストア アプリの展開](lync-server-2013-deploying-lync-windows-store-app.md)

