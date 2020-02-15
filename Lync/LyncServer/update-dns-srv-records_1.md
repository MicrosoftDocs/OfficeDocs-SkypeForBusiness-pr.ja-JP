---
title: DNS SRV レコードを更新する
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Update DNS SRV records
ms:assetid: a29149aa-30cc-4a59-af98-fb95c2385cce
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688161(v=OCS.15)
ms:contentKeyID: 49733765
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c06bfed0fb3f8ca7e367d523f88ab7795839f817
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049008"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="update-dns-srv-records"></a>DNS SRV レコードを更新する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-29_

この手順を正常に完了するには、Domain Admins グループまたは DnsAdmins グループのメンバーとしてサーバーまたはドメインにログオンしている必要があります。

このトピックでは、Lync Server 2013 に移行した後にドメインネームシステム (DNS) レコードを更新する方法について説明します。 すべてのユーザーが Lync Server 2013 に移動された後、従来の Office Communications Server 2007 R2 プールまたはディレクターが使用停止になる前に、すべての SIP ドメインについて内部 DNS の DNS SRV レコードを更新する必要があります。 この手順では、内部 DNS に SIP ユーザードメインのゾーンがあることを前提としています。

**DNS SRV レコードを構成するには**

1.  DNS サーバー上で、[**スタート**] をクリックし、[**管理ツール**] をクリックします。次に、[**DNS**] をクリックします。

2.  SIP ドメインのコンソールツリーで、[**前方参照ゾーン**] を展開し、Lync Server 2013 がインストールされている SIP ドメインを展開して、[ ** \_tcp** ] 設定に移動します。

3.  右側のウィンドウで、[ ** \_sipinternaltls** ] を右クリックし、[**プロパティ**] を選択します。

4.  [**このサービスを提供**しているホスト] で、Lync Server 2013 プールを指すようにホストの FQDN を更新します。

5.  **[OK]** をクリックします。

**フロントエンド プールまたは Standard Edition サーバーの FQDN が解決できることを確認するには**

1.  ドメイン内のクライアント コンピューターにログオンします。

2.  [**スタート**] ボタンをクリックし、[**ファイル名を指定して実行**] をクリックします。

3.  [**名前**] ボックスに「**cmd**」と入力し、[**OK**] をクリックします。

4.  コマンドプロンプトで、Standard Edition サーバー \<\>のフロントエンドプール\>または fqdn の「 **nslookup** \<fqdn」と入力し、enter キーを押します。

5.  受け取る応答が、FQDN の適切な IP アドレスに解決しているのを確認します。

</div>

<span> </span>

</div>

</div>

</div>

