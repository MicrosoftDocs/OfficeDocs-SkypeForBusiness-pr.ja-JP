---
title: 'Lync Server 2013: DNS SRV レコードの作成と確認'
TOCTitle: DNS SRV レコードの作成と確認
ms:assetid: 86888c7e-1401-458f-9a7b-08ac726deeec
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg398680(v=OCS.15)
ms:contentKeyID: 48272776
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 での DNS SRV レコードの作成と確認

 

_**トピックの最終更新日:** 2013-02-21_

この手順を正常に完了するには、最低限でも Domain Admins グループまたは DnsAdmins グループのメンバーとしてサーバーまたはドメインにログオンしている必要があります。

ここでは、Lync Server 2013 展開で作成する必要があるドメイン ネーム システム (DNS) レコード、および自動クライアント サインインに必要な DNS レコードを構成する方法について説明します。フロント エンド プールの作成時に、セットアップによってプール用の Active Directory オブジェクトおよび設定が作成されます。これには、プールの完全修飾ドメイン名 (FQDN) も含まれます。Standard Edition サーバーの場合も同様のオブジェクトおよび設定が作成されます。クライアントがプールまたは Standard Edition サーバーに接続するには、プールまたは Standard Edition サーバーの FQDN が DNS に登録されている必要があります。SIP ドメインごとに DNS SRV レコードを内部 DNS に作成する必要があります。ここでは、SIP ユーザー ドメインに対応するゾーンが内部 DNS にあることを前提としています。

## DNS SRV レコードを構成するには

1.  DNS サーバー上で、\[**スタート**\] をクリックし、\[**管理ツール**\] をクリックします。次に、\[**DNS**\] をクリックします。

2.  SIP ドメインのコンソール ツリーで、\[**前方参照ゾーン**\] を展開し、 Lync Server 2013 をインストールする SIP ドメインを右クリックします。

3.  \[**その他の新しいレコード**\] をクリックします。

4.  \[**リソース レコードの種類を選択**\] の \[**サービス ロケーション (SRV)**\] をクリックし、\[**レコードの作成**\] をクリックします。

5.  " **サービス**" フィールドをクリックし、「**\_sipinternaltls** 」と入力します。

6.  " **プロトコル**" フィールドをクリックし、「**\_tcp** 」と入力します。

7.  " **ポート番号**" フィールドをクリックし、「**5061** 」と入力します。

8.  " **このサービスを提供しているホスト**" フィールドをクリックし、プールまたは Standard Edition サーバーの FQDN を入力します。

9.  \[**OK**\] をクリックしてから、\[**完了**\] をクリックします。

## DNS SRV レコードの作成を確認するには

1.  Authenticated Users グループのメンバーであるアカウントまたは同等のアクセス許可を持つアカウントを使用して、ドメインのクライアント コンピューターにログオンします。

2.  \[**スタート**\] ボタンをクリックし、\[**ファイル名を指定して実行**\] をクリックします。

3.  \[**名前**\] ボックスに「**cmd** 」と入力し、\[**OK**\] をクリックします。

4.  コマンド プロンプトに「**nslookup** 」と入力し、Enter キーを押します。

5.  「**set type=srv** 」と入力し、Enter キーを押します。

6.  「**\_sipinternaltls.\_tcp.contoso.com** 」と入力し、Enter キーを押します。トランスポート層セキュリティ (TLS) レコードに対して表示される出力は次のとおりです。
    
    Server: *\<dns server\>*.contoso.com
    
    Address: *\<IP address of DNS server\>*
    
    Non-authoritative answer:
    
    \_sipinternaltls.\_tcp.contoso.com SRV service location:
    
    priority = 0
    
    weight = 0
    
    port = 5061
    
    svr hostname = poolname.contoso.com (Standard Edition サーバーの A レコード)
    
    poolname.contoso.com internet address = *\<virtual IP Address of the load balancer\>* または *\<IP address of a single Enterprise Edition server for pools with only one Enterprise Edition server\>* または *\<IP address of the Standard Edition server\>*

7.  終了したら、コマンド プロンプトに「**exit** 」と入力し、Enter キーを押します。

## フロントエンド プールまたは Standard Edition サーバーの FQDN が解決できることを確認するには

1.  ドメイン内のクライアント コンピューターにログオンします。

2.  \[**スタート**\] ボタンをクリックし、\[**ファイル名を指定して実行**\] をクリックします。

3.  \[**名前**\] ボックスに「**cmd** 」と入力し、\[**OK**\] をクリックします。

4.  コマンド プロンプトに「**nslookup** *\<FQDN of the Front End pool\>* または *\<FQDN of the Standard Edition server\>* 」を入力し、Enter キーを押します。

5.  受け取る応答が、FQDN の適切な IP アドレスに解決していることを確認します。

