---
title: Lync Connectivity Analyzer を使用する
TOCTitle: Lync Connectivity Analyzer を使用する
ms:assetid: 954953fb-0c7a-4fd5-8acd-68ecb59b20af
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ907302(v=OCS.15)
ms:contentKeyID: 52056644
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Connectivity Analyzer を使用する

 

_**トピックの最終更新日:** 2016-12-08_

Microsoft Lync Connectivity Analyzer により、Lync 管理者は、Office 365 または社内の Lync Server 環境の展開と構成が、Lync Windows ストア アプリとモバイル デバイス上の Lync アプリからの接続をサポートする要件を満たすかどうかを判定できます。

Lync Connectivity Analyzer は、Lync Windows ストア アプリ と Lync のモバイル アプリが使用しているものと同じサービスおよびプロトコルを使用して、社内の Lync Server または Skype for Business Online への接続を試みます。接続テストは、内部ネットワーク、または Lync Server や Skype for Business Online に接続する外部ネットワーク経由で実行できます。Lync Connectivity Analyzer は、各接続手順の情報について詳しく記述するレポートを作成します。これにより、構成を検証して、接続問題をトラブルシューティングできます。

Lync Connectivity Analyzer は、以下の Lync Server コンポーネントをテストします。

  - 自動検出サービス

  - 認証ブローカー (リーチ) サービス

  - Mobility (MCX) Service

  - Mobility (UCWA) Service

  - WebTicket サービス

Lync Connectivity Analyzer は、以下のその他のコンポーネントの構成をテストします。

  - Autodiscover URL の DNS レコードの発行

  - 証明書

  - プロキシ サーバー

Lync Connectivity Analyzer は、Microsoft ダウンロード センター (<http://go.microsoft.com/fwlink/?linkid=277056>) からダウンロードできます。

## 接続を解析するには

1.  ツールでの接続テストに使用する、有効な Lync アカウント (社内の Lync アカウントまたは Office 365Lync アカウント) の資格情報を入力します。
    
      - \[**Lync Account Type**\] で、\[**Office 365**\] または \[**On-Premises**\] を選択します。
    
      - \[**SIP URI**\] に、<strong>user@domain.com</strong> の書式で、Lync 接続の SIP サインイン アドレスを入力します。
    
      - \[**Password**\] に、このアカウントに関連付けられたパスワードを入力します。
    
      - \[**User name (optional)**\] に、該当する場合は、ユーザー名を入力します。ユーザー名は、ユーザー プリンシパル名 (UPN) とも呼ばれます。ユーザー名と SIP URI が同じである場合、ユーザー名を入力する必要はありません。これらが同じではない場合は、必要に応じて、<strong>user@domain.com</strong> または **domain\\user** の書式で、ユーザー名を入力します。
    
      - 内部ネットワークに接続されたコンピューターから Lync Connectivity Analyzer を実行中の場合は、\[**Network access**\] で \[**From inside my organization**\] を選択します。その他の場合には、\[**External (Internet)**\] を選択します。Lync Connectivity Analyzer は、常に内部および外部テストの両方を行います。しかし、自分がネットワークの外側にいるか内側にいるかを指定することは、特定の障害が予測されるかどうかをツールが解釈するのに役立ちます。
    
      - \[**Client**\] で、\[**Lync Windows Store App**\]、\[**Lync Mobile 2010 App**\]、または \[**Lync Mobile 2013 App**\] のどの接続テストを実行するか選択します。
    
      - \[**Server Discovery**\] で、実行するテストの種類を選択します。
        
          - ツールに自動的に Lync サーバーを検出させるには、\[**Automatic**\] を選択します。
        
          - ツールに自動検出テストをバイパスさせるには、または接続するサーバーの名前を知っている場合は、\[**Manual using address:**\] を選択し、たとえば、\[**lync.company.com**\] のように、Lync サーバーの完全修飾ドメイン名前 (FQDN) を指定します。

2.  (オプション) 指定したパスにログ ファイルを作成する場合は、\[**Log File**\] の下でチェック ボックスをオンにします。ログが有効な場合、\[**Clear**\] をクリックするとログ ファイルが消去され、\[**Open**\] をクリックするとログ ファイルが開いて表示され、\[**Email**\] をクリックすると結果をサポート チームに送信するためのメール メッセージが開きます (指定したパスからログ ファイルを手動で添付する必要があります)。

3.  \[**Start**\] をクリックします。

以下の図は Lync Connectivity Analyzer からのサンプル結果を示します。

**Lync Connectivity Analyzer**

![Lync Connectivity Analyzer のスクリーン ショット](images/JJ907302.a7cc0abe-fac2-4691-a7d8-9ffef59cdee5(OCS.15).png "Lync Connectivity Analyzer のスクリーン ショット")

## Lync Connectivity Analyzer によってテストされるコンポーネント

Lync Connectivity Analyzer は、Lync サーバーを検出して、Lync Windows ストア アプリと Lync モバイル アプリによって使用されるものと同じ手順を使用して接続の確立を試行します。このセクションで説明する方法でテストを行います。

\[**Automatic discovery**\] を選択した場合、Lync Connectivity Analyzer は以下のことを行います。

  - 自動検出 URL のドメイン ネーム サービス (DNS) に対してクエリを実行します。

  - セキュリティ保護された内部チャンネルを使用して検出を行います。たとえば、**HTTPS://lyncdiscoverinternal.company.com/** のようになります。

  - セキュリティ保護されていない内部チャンネルを使用して検出を行います。たとえば、**HTTP://lyncdiscoverinternal.company.com/** のようになります。

  - セキュリティ保護された外部チャンネルを使用して検出を行います。たとえば、**HTTPS://lyncdiscover.company.com/** のようになります。

  - セキュリティ保護されていない外部チャンネルを使用して検出を行います。たとえば、**HTTP://lyncdiscover.company.com/** のようになります。

\[**Use the following server discovery address**\] を選択した場合、Lync Connectivity Analyzer は以下のことを行います。

  - サーバーの FQDN の DNS に対してクエリを実行します。

  - セキュリティ保護されたチャンネルを使用して検出を行います。たとえば、**HTTPS://serverFQDN/** のようになります。

  - セキュリティ保護されていないチャンネルを使用して検出を行います。たとえば、**HTTP://serverFQDN/** のようになります。

\[**Test the requirements for**\] の下で、\[**Lync Windows Store app**\] が選択された場合、Lync Connectivity Analyzer は以下のことを行います。

  - WebTicket サービスを使用できることを検証し、Lync アカウントの資格情報の認証をテストします。

  - 認証ブローカー (リーチ) サービスが使用可能であることを確認します。

\[**Client**\] の下で \[**Lync Mobile 2010 App**\] を選択した場合、Lync Connectivity Analyzer は以下のことを行います。

  - WebTicket サービスを使用できることを検証し、Lync アカウントの資格情報の認証をテストします。

  - Mobility (MCX) Service が使用可能であることを確認します。

\[**Client**\] の下で、\[**Lync Mobile 2013 App**\] を選択した場合、Lync Connectivity Analyzer は以下のことを行います。

  - WebTicket サービスを使用できることを検証し、Lync アカウントの資格情報の認証をテストします。

  - Mobility (UCWA) Service が使用可能であることを確認します。

Lync Connectivity Analyzer は、これらのテストの実行中に、Lync Server、ロード バランサー機器、プロキシ サーバー、およびテストを実行中のコンピューターにインストールされた証明書を検証します。

## その他のリソース

また、Microsoft は、Web ベースの接続テスト ツールである Microsoft Remote Connectivity Analyzer を提供しており、<https://testconnectivity.microsoft.com/> で使用できます。Lync Connectivity Analyzer と Remote Connectivity Analyzer は、以下の点で異なります。

  - Remote Connectivity Analyzer は、Microsoft Lync に加えて、Microsoft Exchange および Outlook への接続をテストできます。

  - Remote Connectivity Analyzer は SIP サインインを行うのに対して、Lync Connectivity Analyzer は、サインインせずに、アカウント資格情報を検証するだけです。

  - Remote Connectivity Analyzer は、公開の Web サーバーから実行されるため、組織のネットワークの外側からのみ接続をテストします。

  - Remote Connectivity Analyzer は、認証ブローカー (リーチ)、Mobility (MCX)、および WebTicket サービスの可用性をテストしません。

  - Lync Connectivity Analyzer は、自動検出サービスをテストします。

  - Remote Connectivity Analyzer は、Lync Server のすべてのバージョンに接続できるに対して、Lync Connectivity Analyzer は、(少なくとも) Lync Server 2010 の累積した更新プログラム (2012 年 2 月) を適用した Lync Server 2010、または Lync Server の最新のバージョンにのみ接続できます。

以下のドキュメントは、Lync Windows ストア アプリと Lync モバイル クライアントをサポートする目的で、Lync Server を展開して、構成する要件と手順を説明します。

  - [Lync Server 2013 でのクライアントおよびデバイスの展開](lync-server-2013-deploying-clients-and-devices.md)

  - [Lync Server 2013 でのモビリティの計画](lync-server-2013-planning-for-mobility.md)

  - [Lync Server 2013 でのモビリティの展開](lync-server-2013-deploying-mobility.md)

