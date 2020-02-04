---
title: 'Lync Server 2013: エッジ サポートの DNS の構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure DNS for edge support
ms:assetid: 955493e6-aa29-424d-bb81-1ef87b3b15e3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398756(v=OCS.15)
ms:contentKeyID: 48184894
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c905c8fff7a67b26a7df8d2c741ce0a16fddce6c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757901"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-dns-for-edge-support-in-lync-server-2013"></a>Lync Server 2013 でのエッジ サポートの DNS の構成

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-02-15_

エッジサーバーとリバースプロキシインターフェイスの両方を含む、内部と外部のエッジインターフェイスに対して、ドメインネームシステム (DNS) レコードを構成する必要があります。 既定では、エッジサーバーはドメインに参加しておらず、完全修飾ドメイン名 (完全修飾ドメイン名) を持ちません。 エッジサーバーは、完全修飾ドメイン名ではなく、短い (マシン) 名でのみ参照されます。 ただし、トポロジビルダーでは、短い名前ではなく Fqdn を使用します。 エッジサーバーの名前は、トポロジビルダーで使用される FQDN と一致する必要があります。 これを行うには、コンピューター名と組み合わせるときに、予期される FQDN が返される DNS サフィックスを定義します。 DNS サフィックスをコンピューター名に追加するには、「ドメインに参加していないコンピューター名とエッジサーバーに DNS サフィックスを追加するには」の手順に従います。

<div>


> [!NOTE]  
> 既定では、クエリの dns ドメイン名に対して同じ種類の複数のリソースレコードが存在する場合、DNS はラウンドロビンアルゴリズムを使って、クエリの応答で返されるリソースレコードデータの順序を入れ替えます。 Lync Server 2013 DNS ロードバランシングは、dns の負荷分散メカニズムの一部として DNS ラウンドロビンによって異なります。 ラウンドロビンの設定が無効になっていないことを確認します。 Windows オペレーティングシステムを実行していない DNS サーバーを使用している場合は、ラウンドロビンリソースレコードの順序が有効になっていることを確認します。



</div>

各 DNS SRV レコードを作成して確認するには、「**DNS srv レコードを作成するには**」の手順に従います。 「**Dns a レコードを作成するに**は」の手順を使用して、外部ユーザーのアクセスに必要な dns a レコードを定義します。 レコードが正しく構成され、正常に動作していることを確認するには、このトピックの「**DNS レコードを確認するに**は」を参照してください。 外部ユーザーアクセスをサポートするために必要なレコードの詳細については、「 [Lync Server 2013 の DNS 要件を確認](lync-server-2013-determine-dns-requirements.md)する」を参照してください。

<div>

## <a name="to-add-the-dns-suffix-to-the-computer-name-on-an-edge-server-that-is-not-joined-to-a-domain"></a>ドメインに参加していないエッジサーバー上のコンピューター名に DNS サフィックスを追加するには

1.  コンピューターで [**スタート**] をクリックし、[**コンピューター**] を右クリックして、[**プロパティ**] をクリックします。

2.  [**コンピューター名、ドメインおよびワークグループの設定**] で [**設定の変更**] をクリックします。

3.  [**コンピューター名**] タブで [**変更**] をクリックします。

4.  [**コンピューター名/ドメインの変更**] で、[**その他**] をクリックします。

5.  [ **DNS サフィックスと NetBIOS コンピューター名**] の [**このコンピューターのプライマリ DNS サフィックス**] に、内部ドメインの名前 (たとえば、corp.contoso.com) を入力し、[ **OK]** を3回クリックします。

6.  コンピューターを再起動します。

</div>

<div>

## <a name="to-create-a-dns-srv-record"></a>DNS SRV レコードを作成するには

1.  適切な DNS サーバーで [**スタート**] をクリックし、[**コントロールパネル**] をクリックして、[**管理ツール**]、[ **DNS**] の順にクリックします。
    
    <div>
    

    > [!IMPORTANT]  
    > リモートユーザーおよびフェデレーションパートナーによる外部 DNS 参照に対して、1つの外部 dns エントリがあることを DNS で構成する必要があります。2) 境界ネットワーク (DMZ、非武装地帯、スクリーンサブネットとも呼ばれます) 内のエッジサーバーで使用される DNS 検索のエントリ。 Lync Server 2013 を実行している内部サーバーのレコードを含みます。および 3) 内部のクライアントと、Lync Server 2013 を実行しているサーバーによる参照用の内部 DNS エントリ。

    
    </div>

2.  SIP ドメインのコンソールツリーで [**前方参照ゾーン**] を展開し、Lync Server 2013 がインストールされているドメインを右クリックします。

3.  [**その他の新しいレコード**] をクリックします。

4.  [**リソースレコードの種類を選択**してください] に「**サービスの場所 (SRV)**」と入力し、[**レコードの作成**] をクリックします。

5.  DNS SRV レコードに必要なすべての情報を入力します。

</div>

<div>

## <a name="to-create-a-dns-a-record"></a>DNS A レコードを作成するには

1.  DNS サーバーで、[**スタート**] をクリックし、[**コントロールパネル**] をクリックして、[**管理ツール**]、[ **dns**] の順にクリックします。

2.  SIP ドメインのコンソールツリーで [**前方参照ゾーン**] を展開し、Lync Server 2013 がインストールされているドメインを右クリックします。

3.  [**新しいホスト (A)**] をクリックします。

4.  DNS SRV レコードに必要なすべての情報を入力します。

</div>

<div>

## <a name="to-verify-a-dns-record"></a>DNS レコードを確認するには

1.  ドメイン内のクライアントコンピューターにログオンします。

2.  [**スタート**] ボタンをクリックし、[**ファイル名を指定して実行**] をクリックします。

3.  コマンドプロンプトで、次のコマンドを実行します。
    
        nslookup <FQDN edge interface>

4.  FQDN の適切な IP アドレスに解決される返信を受信したことを確認します。

</div>

<div>

## <a name="see-also"></a>関連項目


[Hosted Exchange UM との統合のための DNS SRV レコードを作成する](lync-server-2013-create-a-dns-srv-record-for-integration-with-hosted-exchange-um.md)  


[Lync Server 2013 の DNS の要件を確認する](lync-server-2013-determine-dns-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

