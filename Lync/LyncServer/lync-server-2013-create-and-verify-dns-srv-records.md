---
title: 'Lync Server 2013: DNS SRV レコードの作成と確認'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create and verify DNS SRV records
ms:assetid: 86888c7e-1401-458f-9a7b-08ac726deeec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398680(v=OCS.15)
ms:contentKeyID: 48184714
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c7faf0cd00b59d5df5bab1650a28eff8b9563f91
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42205683"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-and-verify-dns-srv-records-in-lync-server-2013"></a>Lync Server 2013 で DNS SRV レコードを作成および確認する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-21_

この手順を正常に完了するには、最低限でも Domain Admins グループまたは DnsAdmins グループのメンバーとしてサーバーまたはドメインにログオンしている必要があります。

このトピックでは、Lync Server 2013 の展開で作成する必要があるドメインネームシステム (DNS) レコード、および自動クライアントサインインに必要なドメインネームシステム (DNS) レコードを構成する方法について説明します。 フロントエンドプールを作成すると、プールの完全修飾ドメイン名 (FQDN) を含む、プールの Active Directory オブジェクトと設定がセットアップによって作成されます。 Standard Edition サーバー用に、同様のオブジェクトと設定が作成されます。 クライアントがプールまたは Standard Edition サーバーに接続できるようにするには、プールまたは Standard Edition サーバーの FQDN を DNS に登録する必要があります。 すべての SIP ドメインについて、内部 DNS に DNS SRV レコードを作成する必要があります。 この手順では、内部 DNS に SIP ユーザードメインのゾーンがあることを前提としています。

<div>

## <a name="to-configure-a-dns-srv-record"></a>DNS SRV レコードを構成するには

1.  DNS サーバー上で、[**スタート**] をクリックし、[**管理ツール**] をクリックします。次に、[**DNS**] をクリックします。

2.  SIP ドメインのコンソールツリーで、[**前方参照ゾーン**] を展開し、Lync Server 2013 をインストールする SIP ドメインを右クリックします。

3.  [**その他の新しいレコード**] をクリックします。

4.  [**リソース レコードの種類を選択**] の [**サービス ロケーション (SRV)**] をクリックし、[**レコードの作成**] をクリックします。

5.  [**サービス**] をクリックし、「 ** \_sipinternaltls**」と入力します。

6.  [**プロトコル**] をクリックし、「 ** \_tcp**」と入力します。

7.  "**ポート番号**" フィールドをクリックし、「**5061**」と入力します。

8.  [**このサービスを提供**しているホスト] をクリックし、プールまたは Standard Edition サーバーの FQDN を入力します。

9.  [**OK**] をクリックしてから、[**完了**] をクリックします。

</div>

<div>

## <a name="to-verify-the-creation-of-a-dns-srv-record"></a>DNS SRV レコードの作成を確認するには

1.  Authenticated Users グループのメンバーであるアカウントまたは同等のアクセス許可を持つアカウントを使用して、ドメインのクライアント コンピューターにログオンします。

2.  [**スタート**] ボタンをクリックし、[**ファイル名を指定して実行**] をクリックします。

3.  [**名前**] ボックスに「**cmd**」と入力し、[**OK**] をクリックします。

4.  コマンド プロンプトに「**nslookup**」と入力し、Enter キーを押します。

5.  「**set type=srv**」と入力し、Enter キーを押します。

6.  「 ** \_Sipinternaltls」\_と入力します。tcp.contoso.com**と入力し、enter キーを押します。 トランスポート層セキュリティ (TLS) レコードに対して表示される出力は次のとおりです。
    
    サーバー: \<dns サーバー\>. contoso.com
    
    アドレス: \<DNS サーバーの IP アドレス\>
    
    Non-authoritative answer:
    
    \_sipinternaltls.\_tcp.contoso.com SRV サービスの場所:
    
    priority = 0
    
    ウエイト = 0
    
    ポート = 5061
    
    svr hostname = poolname.contoso.com (または Standard Edition サーバー A レコード)
    
    poolname.contoso.com internet address = \<enterprise edition サーバー\> \>また\<は Standard Edition サーバー \<の ip アドレスが1つしかないプールの場合は、1つの enterprise edition サーバーの仮想 ip アドレス\>

7.  終了したら、コマンド プロンプトに「**exit**」と入力し、Enter キーを押します。

</div>

<div>

## <a name="to-verify-that-the-fqdn-of-the-front-end-pool-or-standard-edition-server-can-be-resolved"></a>フロントエンド プールまたは Standard Edition サーバーの FQDN が解決できることを確認するには

1.  ドメイン内のクライアント コンピューターにログオンします。

2.  [**スタート**] ボタンをクリックし、[**ファイル名を指定して実行**] をクリックします。

3.  [**名前**] ボックスに「**cmd**」と入力し、[**OK**] をクリックします。

4.  コマンドプロンプトで、Standard Edition サーバー \<\>のフロントエンドプール\>または fqdn の「 **nslookup** \<fqdn」と入力し、enter キーを押します。

5.  受け取る応答が、FQDN の適切な IP アドレスに解決しているのを確認します。

</div>

</div>

<span> </span>

</div>

</div>

</div>

