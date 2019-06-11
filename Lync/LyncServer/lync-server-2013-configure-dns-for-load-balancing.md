---
title: 'Lync Server 2013: 負荷分散の DNS 構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure DNS for load balancing
ms:assetid: 1b2e8414-8676-4872-8ecf-ea07196f74de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398251(v=OCS.15)
ms:contentKeyID: 48183540
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7e370d3b66e82b02bd5668fc1c9cab4ee41da759
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840390"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-dns-for-load-balancing-in-lync-server-2013"></a>Lync Server 2013 での負荷分散の DNS 構成

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-01_

この手順を完了するには、ドメイン管理者グループのメンバー、または DnsAdmins グループのメンバーとして、サーバーまたはドメインに最低でもログオンしている必要があります。

ドメインネームシステム (DNS) の負荷分散は、Lync Server 2013 に固有のネットワークトラフィック (SIP トラフィックやメディアトラフィックなど) のバランスを行います。 DNS の負荷分散は、フロントエンドプール、エッジプール、ディレクタープール、スタンドアロンの仲介プールでサポートされています。 DNS ロードバランシングを使用するように構成されているプールには、2つの完全修飾ドメイン名 (Fqdn) が定義されている必要があります。 DNS の負荷分散 (たとえば、pool1.contoso.com) で使用される標準プール FQDN と、プール内のサーバーの物理 Ip に解決されます。プールの Web サービス (たとえば、web1.contoso.net) の別の FQDN がプールの仮想 IP アドレスに解決されます。 DNS の負荷分散の詳細については、計画ドキュメントの「 [Lync Server 2013 での dns の負荷分散](lync-server-2013-dns-load-balancing.md)」を参照してください。

<div>


> [!NOTE]  
> クライアント間の HTTPS トラフィックには、依然としてハードウェア負荷分散が必要です。



</div>

DNS の負荷分散を使用するには、次の手順を実行する必要があります。

1.  内部 Web サービスプールの FQDN を上書きします。
    
    <div>
    

    > [!WARNING]  
    > 自己定義の FQDN を使用して内部 web サービスを上書きする場合、各 FQDN は、他のフロントエンドプール、ディレクター、またはディレクタープールから一意である必要があります。

    
    </div>

2.  DNS A host レコードを作成して、プールの FQDN を解決し、プール内のすべてのサーバーの IP アドレスを解決します。

3.  IP アドレスをランダムに有効にするか、Windows Server DNS の場合は、ラウンドロビンを有効にします。
    
    <div>
    

    > [!NOTE]  
    > ラウンドロビンは既定で有効になっている必要があります。

    
    </div>

<div>

## <a name="to-override-internal-web-services-fqdn"></a>内部 Web サービスの FQDN を上書きするには

1.  トポロジビルダーを開始します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server Topology Builder**] の順にクリックします。

2.  コンソールツリーで、Enterprise Edition の [フロントエンドプール] ノードを展開します。

3.  プールを右クリックし、[**プロパティの編集**] をクリックして、[ **Web サービス**] をクリックします。

4.  [**内部 web サービス**] の下で、[ **FQDN の上書き**] チェックボックスをオンにします。

5.  プール内のサーバーの物理 IP アドレスに解決されるプールの FQDN を入力します。

6.  [**外部 web サービス**] の下に、プールの仮想 IP アドレスに解決される外部プールの FQDN を入力して、[ **OK]** をクリックします。

7.  コンソールツリーで [ **Lync Server 2013**] をクリックし、[**操作**] ウィンドウで [**トポロジの公開**] をクリックします。

</div>

<div>

## <a name="to-create-dns-host-a-records-for-all-internal-pool-servers"></a>すべての内部プールサーバー用の DNS ホスト (A) レコードを作成するには

1.  [**スタート**] をクリックし、[**すべてのプログラム**]、[**管理ツール**]、[ **DNS**] の順にクリックします。

2.  **Dns マネージャー**で、レコードを管理する dns サーバーをクリックして展開します。

3.  [**前方参照ゾーン**] をクリックして展開します。

4.  レコードを追加する必要がある DNS ドメインを右クリックし、[**新しいホスト (A または AAAA)**] をクリックします。

5.  [**名前**] ボックスにホスト レコード名を入力します (ドメイン名は自動的に追加されます)。

6.  [IP アドレス] ボックスに、個々のフロントエンドサーバーの IP アドレスを入力し、[**関連付けられたポインター (PTR) レコードを作成**する] を選択するか、または該当する場合は、認証された**すべてのユーザーが同じ所有者名で DNS レコードを更新できるように**します。

7.  DNS の負荷分散に参加するすべてのメンバーのフロントエンドサーバーのレコードの作成を続けます。
    
    たとえば、pool1.contoso.com と3つのフロントエンドサーバーという名前のプールがある場合は、次の DNS エントリを作成します。
    
    
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
    
    DNS Host (A) レコードの作成の詳細については、「 [Lync Server 2013 の Dns ホストレコードを構成](lync-server-2013-configure-dns-host-records.md)する」を参照してください。

</div>

<div>

## <a name="to-enable-round-robin-for-windows-server"></a>Windows Server のラウンドロビンを有効にするには

1.  [**スタート**] をクリックし、[**すべてのプログラム**]、[**管理ツール**]、[ **DNS**] の順にクリックします。

2.  [ **Dns**] を展開し、構成する dns サーバーを右クリックして、[**プロパティ**] をクリックします。

3.  [**詳細設定**] タブをクリックし、[**ラウンドロビンを有効に**して**ネットマスクの順序を有効**にする] を選び、[ **OK**] をクリックします。
    
    ![[DNS ラウンドロビン] ダイアログボックス](images/Gg398251.e7bf6125-8d78-4460-8401-0a8e7e21d305(OCS.15).jpg "[DNS ラウンドロビン] ダイアログボックス")

<div>


> [!NOTE]  
> この機能は既定で有効になっている必要があります。



</div>

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 での DNS の負荷分散](lync-server-2013-dns-load-balancing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

