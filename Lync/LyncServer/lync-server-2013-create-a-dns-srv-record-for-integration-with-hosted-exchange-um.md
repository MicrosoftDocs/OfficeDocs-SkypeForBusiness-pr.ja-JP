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
ms.openlocfilehash: c8cc5072e122d553007a2b4e095c58988aca390d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740457"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-dns-srv-record-for-integration-with-hosted-exchange-um"></a>Hosted Exchange UM との統合のための DNS SRV レコードを作成する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-20_

このトピックでは、Lync Server 2013 エッジサーバーが Microsoft Exchange Online などのホストされた Exchange サービスにルーティングするために必要なドメインネームシステム (DNS) SRV レコードを構成する方法について説明します。

<div>

## <a name="to-create-an-external-dns-srv-record-for-the-hosted-exchange-service"></a>ホストされている Exchange サービスの外部 DNS SRV レコードを作成するには

1.  DnsAdmins グループのメンバーとして外部 DNS サーバーにログオンします。

2.  [**スタート**] をクリックし、[**管理ツール**]、[ **DNS**] の順にクリックします。

3.  SIP ドメインのコンソールツリーで [**前方参照ゾーン**] を展開し、Lync Server 2013 をインストールする SIP ドメインを選択します。
    
    <div>
    

    > [!IMPORTANT]
    > Lync Server がインストールされている、またはインストールされる SIP ドメインで DNS SRV レコードを作成する必要があります。 SRV レコードを作成するときに、[このサービスを提供するホスト] フィールドを使う FQDN は、Edge プールの外部 FQDN である必要があります。 たとえば、Edge プールの外部 FQDN が edge01.contoso.net の場合は、その値を入力します。 また、DNS Hosts (A) レコードと同じドメイン内に存在する必要があります。

    
    </div>

4.  選んだドメインを右クリックし、[**その他の新しいレコード**] をクリックします。

5.  [**リソースレコードの種類**] で [**サービスの場所 (SRV)**] をクリックし、[**レコードの作成**] をクリックします。

6.  [**新しいリソースレコード**] で、[**サービス**] をクリックし、「 ** \_sipfederationtls**」と入力します。

7.  [**プロトコル**] をクリックして、「 ** \_tcp**」と入力します。

8.  [**ポート番号**] をクリックし、「**5061**」と入力します。

9.  [**このサービスを提供するホスト**] をクリックして、lync Server 2013 Edge プールの完全修飾ドメイン名 (FQDN) を入力します。これにより、信頼できる外部クライアントの lync server 2013 システムへのアクセスが提供されます。
    
    <div>
    

    > [!NOTE]
    > また、ドメインは、Exchange Online の設定で、権限を持つ承認済みドメインとして設定する必要があります。 詳しくは、「承認された<A href="http://go.microsoft.com/fwlink/p/?linkid=229762">http://go.microsoft.com/fwlink/p/?linkId=229762</A>ドメインをで作成する」をご覧ください。

    
    </div>

10. [**OK**] をクリックしてから、[**完了**] をクリックします。

</div>

<div>

## <a name="to-verify-that-the-dns-srv-record-was-created-successfully"></a>DNS SRV レコードが正常に作成されたことを確認するには

1.  ドメイン内のクライアントコンピューターにログオンします。

2.  [**スタート**] ボタンをクリックし、[**ファイル名を指定して実行**] をクリックします。

3.  コマンドプロンプトで、次のコマンドを実行します。
    
        nslookup <FQDN Lync Edge Pool>

4.  FQDN の適切な IP アドレスに解決される返信を受信したことを確認します。

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 でのリバース プロキシ サーバーの DNS レコードの作成](lync-server-2013-create-dns-records-for-reverse-proxy-servers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

