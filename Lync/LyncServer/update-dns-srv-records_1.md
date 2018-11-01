---
title: DNS SRV レコードの更新
TOCTitle: DNS SRV レコードの更新
ms:assetid: a29149aa-30cc-4a59-af98-fb95c2385cce
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ688161(v=OCS.15)
ms:contentKeyID: 49887082
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# DNS SRV レコードの更新

 

_**トピックの最終更新日:** 2012-09-29_

この手順を正常に完了するには、Domain Admins グループまたは DnsAdmins グループのメンバーとしてサーバーまたはドメインにログオンしている必要があります。

ここでは、 Lync Server 2013 に移行した後にドメイン ネーム システム (DNS) レコードを更新する方法について説明します。すべてのユーザーが Lync Server 2013 に移行した後、 Office Communications Server 2007 R2 のレガシ プールやレガシ ディレクターを使用停止にする前に、内部 DNS ですべての SIP ドメインの DNS SRV レコードを更新する必要があります。ここでは、SIP ユーザー ドメインに対応するゾーンが内部 DNS にあることを前提としています。

**DNS SRV レコードを構成するには**

1.  DNS サーバー上で、\[**スタート**\] をクリックし、\[**管理ツール**\] をクリックします。次に、\[**DNS**\] をクリックします。

2.  SIP ドメインのコンソール ツリーで、\[**前方参照ゾーン**\] を展開し、 Lync Server 2013 がインストールされている SIP ドメインを展開して、\[**\_tcp**\] 設定に移動します。

3.  右側のウィンドウで、\[**\_sipinternaltls**\] を右クリックし、\[**プロパティ**\] をクリックします。

4.  \[**このサービスを提供しているホスト**\] で、 Lync Server 2013 プールを参照するようにホストの FQDN を更新します。

5.  \[**OK**\] をクリックします。

**フロントエンド プールまたは Standard Edition サーバーの FQDN が解決できることを確認するには**

1.  ドメイン内のクライアント コンピューターにログオンします。

2.  \[**スタート**\] ボタンをクリックし、\[**ファイル名を指定して実行**\] をクリックします。

3.  \[**名前**\] ボックスに「**cmd** 」と入力し、\[**OK**\] をクリックします。

4.  コマンド プロンプトに「**nslookup** *\<FQDN of the Front End pool\>* または *\<FQDN of the Standard Edition server\>*」を入力し、Enter キーを押します。

5.  受け取る応答が、FQDN の適切な IP アドレスに解決していることを確認します。

