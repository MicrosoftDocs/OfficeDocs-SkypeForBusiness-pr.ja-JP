---
title: 'Lync Server 2013: 負荷分散のための DNS の構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure DNS for load balancing
ms:assetid: 1b2e8414-8676-4872-8ecf-ea07196f74de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398251(v=OCS.15)
ms:contentKeyID: 48183540
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 257bd8d1d4874bb2483c16c2216c4b76b178a881
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140390"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-dns-for-load-balancing-in-lync-server-2013"></a>Lync Server 2013 での負荷分散の DNS の構成

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-01_

この手順を正常に完了するには、最低限でも Domain Admins グループまたは DnsAdmins グループのメンバーとしてサーバーまたはドメインにログオンしている必要があります。

ドメインネームシステム (DNS) 負荷分散は、SIP トラフィックやメディアトラフィックなど、Lync Server 2013 に固有のネットワークトラフィックのバランスをとります。 DNS 負荷分散は、フロントエンドプール、エッジプール、ディレクタープール、およびスタンドアロンの仲介プールに対してサポートされています。 DNS 負荷分散を使用するように構成されたプールには、2つの完全修飾ドメイン名 (Fqdn) が定義されている必要があります。これは、DNS 負荷分散によって使用される通常のプール FQDN (たとえば、pool1.contoso.com) を使用し、プール内のサーバーの物理 Ip に解決します。、プールの Web サービスの別の FQDN (web1.contoso.net など) を使用して、プールの仮想 IP アドレスに解決されます。 DNS 負荷分散の詳細については、「計画」のドキュメントの「 [dns load balancing In Lync Server 2013](lync-server-2013-dns-load-balancing.md) 」を参照してください。

<div>


> [!NOTE]  
> クライアントからサーバーへの HTTPS トラフィックには、まだハードウェア負荷分散が必要です。



</div>

DNS 負荷分散を使用する前に、次の操作を行う必要があります。

1.  内部 Web サービスプールの FQDN を上書きします。
    
    <div>
    

    > [!WARNING]  
    > 内部 web サービスを自己定義の FQDN で上書きする場合、各 FQDN は他のフロントエンドプール、ディレクター、またはディレクタープールとは一意である必要があります。

    
    </div>

2.  プールの FQDN をプール内のすべてのサーバーの IP アドレスに解決するための DNS A ホスト レコードの作成

3.  IP アドレスのランダム化を有効にする (Windows Server の DNS の場合は、ラウンド ロビンを有効にする)
    
    <div>
    

    > [!NOTE]  
    > ラウンド ロビンは既定で有効になっています。

    
    </div>

<div>

## <a name="to-override-internal-web-services-fqdn"></a>内部 Web サービスの FQDN をオーバーライドするには

1.  トポロジ ビルダーを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server トポロジ ビルダー**] の順にクリックします。

2.  コンソール ツリーから、Enterprise Edition のフロントエンド プールのノードを展開します。

3.  プールを右クリックして [**プロパティの編集**] をクリックし、[**Web サービス**] をクリックします。

4.  [**内部 Web サービス**] で、[**FQDN のオーバーライド**] チェック ボックスをオンにします。

5.  プール内のサーバーの物理 IP アドレスへ解決するプールの FQDN を入力します。

6.  [**外部 Web サービス**] で、プールの仮想 IP アドレスへ解決する外部プールの FQDN を入力し、[**OK**] をクリックします。

7.  コンソールツリーで [ **Lync Server 2013**] をクリックし、[**操作**] ウィンドウで [**トポロジの公開**] をクリックします。

</div>

<div>

## <a name="to-create-dns-host-a-records-for-all-internal-pool-servers"></a>すべての内部プール サーバーの DNS ホスト (A) レコードを作成するには

1.  [**スタート**] をクリックし、[**すべてのプログラム**]、[**管理ツール**] をクリックし、[**DNS**] をクリックします。

2.  [**DNS マネージャー**] で、レコードを管理する DNS サーバーをクリックして展開します。

3.  [**前方参照ゾーン**] をクリックして展開します。

4.  レコードの追加が必要な DNS ドメインを右クリックし、[**新しいホスト (A または AAAA)**] をクリックします。

5.  [**名前**] ボックスに、ホストレコードの名前を入力します (ドメイン名は自動的に追加されます)。

6.  [IP アドレス] ボックスで、個々のフロントエンド サーバーの IP アドレスを入力し、適用可能な場合は [**関連付けられたポインター (PTR) レコードを作成する**] または [**同じ所有者名の DNS レコードの更新を認証されたユーザーに許可する**] を選択します。

7.  引き続き、DNS 負荷分散に参加するすべてのメンバー フロントエンド サーバーのレコードを作成します。
    
    たとえば、pool1.contoso.com という名前のプールと 3 台のフロントエンド サーバーがある場合は、次の DNS エントリを作成します。
    
    
    <table>
    <colgroup>
    <col style="width: 33%" />
    <col style="width: 33%" />
    <col style="width: 33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>FQDN</th>
    <th>型</th>
    <th>データ</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>Pool1.contoso.com</p></td>
    <td><p>ホスト (A)</p></td>
    <td><p>192.168.1.1</p></td>
    </tr>
    <tr class="even">
    <td><p>Pool1.contoso.com</p></td>
    <td><p>ホスト (A)</p></td>
    <td><p>192.168.1.2</p></td>
    </tr>
    <tr class="odd">
    <td><p>Pool1.contoso.com</p></td>
    <td><p>ホスト (A)</p></td>
    <td><p>192.168.1.3</p></td>
    </tr>
    </tbody>
    </table>
    
    DNS ホスト (A) レコードの作成の詳細については、「 [CONFIGURE Dns host records For Lync Server 2013](lync-server-2013-configure-dns-host-records.md)」を参照してください。

</div>

<div>

## <a name="to-enable-round-robin-for-windows-server"></a>Windows Server のラウンド ロビンを有効にするには

1.  [**スタート**] をクリックし、[**すべてのプログラム**]、[**管理ツール**] をクリックし、[**DNS**] をクリックします。

2.  [**DNS**] を展開し、構成する DNS サーバーを右クリックして、[**プロパティ**] をクリックします。

3.  [**詳細設定**] タブをクリックし、[**ラウンド ロビンを有効にする**] と [**ネットマスクの順序を有効にする**] を選択して、[**OK**] をクリックします。
    
    ![DNS ラウンドロビンダイアログボックス](images/Gg398251.e7bf6125-8d78-4460-8401-0a8e7e21d305(OCS.15).jpg "DNS ラウンドロビンダイアログボックス")

<div>


> [!NOTE]  
> この機能は既定で有効になっています。



</div>

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 での DNS 負荷分散](lync-server-2013-dns-load-balancing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

