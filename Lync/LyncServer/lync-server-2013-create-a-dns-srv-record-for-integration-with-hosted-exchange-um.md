---
title: Hosted Exchange UM との統合のための DNS SRV レコードを作成する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a DNS SRV record for integration with hosted Exchange UM
ms:assetid: 8ea590ae-58ea-4ca5-9853-e0708b3ea760
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh500728(v=OCS.15)
ms:contentKeyID: 48184770
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ac215b5a0ba42ff031962e656e72fb355a808bf4
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48507474"
---
# <a name="create-a-dns-srv-record-for-integration-with-hosted-exchange-um"></a>Hosted Exchange UM との統合のための DNS SRV レコードを作成する

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-20_

このトピックでは、Lync Server 2013 エッジサーバーが Microsoft Exchange Online などのホストされた Exchange サービスにルーティングするために必要なドメインネームシステム (DNS) SRV レコードを構成する方法について説明します。

<div>

## <a name="to-create-an-external-dns-srv-record-for-the-hosted-exchange-service"></a>Hosted Exchange サービス用の外部 DNS SRV レコードを作成するには

1.  DnsAdmins グループのメンバーとして外部 DNS サーバーにログオンします。

2.  [**スタート**]、[**管理ツール**]、[**DNS**] の順にクリックします。

3.  SIP ドメインのコンソールツリーで、[ **前方参照ゾーン**] を展開し、Lync Server 2013 をインストールする SIP ドメインを選択します。
    
    <div>
    

    > [!IMPORTANT]
    > Lync Server がインストールされているか Lync Server がインストールされる SIP ドメインに DNS SRV レコードを作成する必要があります。SRV レコードを作成するときに、[このサービスを提供しているホスト] フィールドで使用する FQDN には、エッジ プールの外部 FQDN を指定する必要があります。たとえば、エッジ プールの外部 FQDN が edge01.contoso.net の場合、その値を入力します。また、これは、DNS ホスト (A) レコードと同じドメインに含まれる必要があります。

    
    </div>

4.  選択したドメインを右クリックし、[**その他の新しいレコード**] をクリックします。

5.  [**リソース レコードの種類**] で、[**サービス ロケーション (SRV)**]、[**レコードの作成**] の順にクリックします。

6.  [**新しいリソースレコード**] で、[**サービス**] をクリックし、「 ** \_ sipfederationtls**」と入力します。

7.  [**プロトコル**] をクリックし、「 ** \_ tcp**」と入力します。

8.  "**ポート番号**" フィールドをクリックし、「**5061**」と入力します。

9.  [ **このサービスを提供**しているホスト] をクリックし、lync Server 2013 エッジプールの完全修飾ドメイン名 (FQDN) を入力します。これにより、信頼できる外部クライアントに対して lync server 2013 システムへのアクセスが提供されます。
    
    <div>
    

    > [!NOTE]
    > このドメインを、Exchange Online 設定内で権限のある承認済みドメインとしてセットアップする必要もあります。 詳細については、「の承認済みドメインを作成する」を参照してください <A href="https://go.microsoft.com/fwlink/p/?linkid=229762">https://go.microsoft.com/fwlink/p/?linkId=229762</A> 。

    
    </div>

10. **[OK]** をクリックしてから、**[完了]** をクリックします。

</div>

<div>

## <a name="to-verify-that-the-dns-srv-record-was-created-successfully"></a>DNS SRV レコードが正常に作成されたことを確認するには

1.  ドメイン内のクライアント コンピューターにログオンします。

2.  **[スタート]** ボタンをクリックし、**[ファイル名を指定して実行]** をクリックします。

3.  コマンド プロンプトで、次のコマンドを実行します。
    
        nslookup <FQDN Lync Edge Pool>

4.  受け取る応答が、FQDN の適切な IP アドレスに解決しているのを確認します。

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 でリバースプロキシサーバーの DNS レコードを作成する](lync-server-2013-create-dns-records-for-reverse-proxy-servers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

