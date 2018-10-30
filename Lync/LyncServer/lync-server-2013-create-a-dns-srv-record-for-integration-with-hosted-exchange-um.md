---
title: 'Lync Server 2013: Hosted Exchange UM との統合のための DNS SRV レコードを作成する'
TOCTitle: Hosted Exchange UM との統合のための DNS SRV レコードを作成する
ms:assetid: 8ea590ae-58ea-4ca5-9853-e0708b3ea760
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Hh500728(v=OCS.15)
ms:contentKeyID: 48272803
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Hosted Exchange UM との統合のための DNS SRV レコードを作成する

 

_**トピックの最終更新日:** 2016-12-08_

このトピックでは、Microsoft Exchange Online など、Hosted Exchange サービスに Lync Server 2013  エッジ サーバーをルーティングするために必要とされる、ドメイン ネーム システム (DNS) の SRV レコードを構成する方法について説明します。

## Hosted Exchange サービス用の外部 DNS SRV レコードを作成するには

1.  DnsAdmins グループのメンバーとして外部 DNS サーバーにログオンします。

2.  \[**スタート**\]、\[**管理ツール**\]、\[**DNS**\] の順にクリックします。

3.  SIP ドメインのコンソール ツリーで、\[**前方参照ゾーン**\] を展開し、 Lync Server 2013 をインストールする SIP ドメインを選択します。
    

    > [!IMPORTANT]
    > Lync Server がインストールされているか Lync Server がインストールされる SIP ドメインに DNS SRV レコードを作成する必要があります。SRV レコードを作成するときに、[このサービスを提供しているホスト] フィールドで使用する FQDN には、エッジ プールの外部 FQDN を指定する必要があります。たとえば、エッジ プールの外部 FQDN が edge01.contoso.net の場合、その値を入力します。また、これは、DNS ホスト (A) レコードと同じドメインに含まれる必要があります。



4.  選択したドメインを右クリックし、\[**その他の新しいレコード**\] をクリックします。

5.  \[**リソース レコードの種類**\] で、\[**サービス ロケーション (SRV)**\]、\[**レコードの作成**\] の順にクリックします。

6.  \[**新しいリソース レコード**\] で、\[**サービス**\] をクリックし、「**\_sipfederationtls** 」と入力します。

7.  "**プロトコル**" フィールドをクリックし、「**\_tcp**」と入力します。

8.  "**ポート番号**" フィールドをクリックし、「**5061**」と入力します。

9.  \[**このサービスを提供しているホスト**\] をクリックし、信頼される外部クライアントに Lync Server 2013 システムへのアクセスを提供する Lync Server 2013  エッジ プールの完全修飾ドメイン名 (FQDN) を入力します。
    
    > [!NOTE]
    > このドメインを、Exchange Online 設定内で権限のある承認済みドメインとしてセットアップする必要もあります。詳細については、「承認済みドメインの作成 - Office 365 Beta for enterprises」( <a href="http://go.microsoft.com/fwlink/?linkid=229762%26clcid=0x411" class="uri">http://go.microsoft.com/fwlink/?linkid=229762&amp;clcid=0x411</a>) を参照してください。


10. \[**OK**\] をクリックしてから、\[**完了**\] をクリックします。

## DNS SRV レコードが正常に作成されたことを確認するには

1.  ドメイン内のクライアント コンピューターにログオンします。

2.  \[**スタート**\] ボタンをクリックし、\[**ファイル名を指定して実行**\] をクリックします。

3.  コマンド プロンプトで、次のコマンドを実行します。
    
        nslookup <FQDN Lync Edge Pool>

4.  受け取る応答が、FQDN の適切な IP アドレスに解決していることを確認します。

## 関連項目

#### 概念

[Lync Server 2013 でのリバース プロキシ サーバーの DNS レコードの作成](lync-server-2013-create-dns-records-for-reverse-proxy-servers.md)

