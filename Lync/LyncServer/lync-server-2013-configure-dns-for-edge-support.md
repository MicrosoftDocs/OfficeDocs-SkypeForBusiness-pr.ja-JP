---
title: 'Lync Server 2013: エッジサポートの DNS の構成'
description: 'Lync Server 2013: エッジサポートの DNS を構成します。'
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
ms.openlocfilehash: 706f4915adda58dbb72b8dd8921e0cc612833718
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555893"
---
# <a name="configure-dns-for-edge-support-in-lync-server-2013"></a>Lync Server 2013 でエッジサポートの DNS を構成する

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-15_

エッジ サーバーおよびリバース プロキシ インターフェイスを含んだ、内部および外部エッジ インターフェイスのドメイン ネーム システム (DNS) レコードを構成する必要があります。 既定では、エッジサーバーはドメインには参加せず、完全修飾ドメイン名 (完全修飾ドメイン名) はありません。 エッジサーバーは、完全修飾ドメイン名ではなく、short (マシン) 名のみによって参照されます。 ただし、トポロジビルダーでは、短い名前ではなく Fqdn を使用します。 エッジサーバーの名前は、トポロジビルダーで使用される FQDN と一致している必要があります。 これを行うには、コンピューター名と組み合わせて、予期される FQDN を検索する DNS サフィックスを定義します。 コンピューター名に DNS サフィックスを追加するには、「ドメインに参加していないコンピューター名とエッジサーバーに DNS サフィックスを追加するには」の手順を使用します。

<div>


> [!NOTE]  
> 既定では、DNS はラウンドロビンアルゴリズムを使用して、クエリ応答で返されたリソースレコードデータの順序を循環させます。クエリ応答には、クエリの対象となる DNS ドメイン名に対して同じ種類のリソースレコードが複数存在します。 Lync Server 2013 DNS 負荷分散は、dns 負荷分散メカニズムの一部として DNS ラウンドロビンに依存します。 ラウンドロビン設定が無効になっていないことを確認します。 Windows オペレーティングシステムを実行していない DNS サーバーを使用している場合は、ラウンドロビンリソースレコードの順序が有効になっていることを確認してください。



</div>

各 DNS SRV レコードを作成して確認するには、「**DNS srv レコードを作成するに**は」の手順を使用します。 「**Dns a レコードを作成するに**は」の手順を使用して、外部ユーザーアクセスに必要な dns a レコードを定義します。 レコードが正しく構成され、動作していることを確認するには、このトピックの「**DNS レコードを確認するに**は」を参照してください。 外部ユーザーアクセスをサポートするために必要な各レコードの詳細については、「 [Lync Server 2013 の DNS 要件を決定](lync-server-2013-determine-dns-requirements.md)する」を参照してください。

<div>

## <a name="to-add-the-dns-suffix-to-the-computer-name-on-an-edge-server-that-is-not-joined-to-a-domain"></a>ドメインに参加していないエッジ サーバーのコンピューター名に DNS サフィックスを追加するには

1.  コンピューターで、**[スタート]** メニューの **[コンピューター]** を右クリックし、**[プロパティ]** をクリックします。

2.  **[コンピューター名、ドメインおよびワークグループの設定]** で、**[設定の変更]** をクリックします。

3.  **[コンピューター名]** タブで、**[変更]** をクリックします。

4.  **[コンピューター名/ドメイン名の変更]** で、**[その他]** をクリックします。

5.  **[DNS サフィックスと NetBIOS コンピューター名]** の **[このコンピューターのプライマリ DNS サフィックス]** で、内部ドメイン名 (corp.contoso.com など) を入力し、**[OK]** を 3 回クリックします。

6.  コンピューターを再起動します。

</div>

<div>

## <a name="to-create-a-dns-srv-record"></a>DNS SRV レコードを作成するには

1.  適切な DNS サーバー上で、**[スタート]** ボタンをクリックし、**[コントロール パネル]** をクリックします。次に **[管理ツール]** をクリックし、**[DNS]** をクリックします。
    
    <div>
    

    > [!IMPORTANT]  
    > リモートユーザーとフェデレーションパートナーによる外部 DNS 参照用の外部 dns エントリがあるように DNS を構成する必要があります。2) 境界ネットワーク (DMZ、非武装地帯、スクリーンサブネットとも呼ばれます) 内のエッジサーバーが使用する DNS 参照のエントリ。 Lync Server 2013 を実行している内部サーバーのレコードを含みます。および 3) Lync Server 2013 を実行している内部クライアントおよびサーバーによる参照用の内部 DNS エントリ。

    
    </div>

2.  SIP ドメインのコンソールツリーで、[ **前方参照ゾーン**] を展開し、Lync Server 2013 がインストールされているドメインを右クリックします。

3.  **[その他の新しいレコード]** をクリックします。

4.  **[リソース レコードの種類を選択]** の **[サービス ロケーション (SRV)]** を入力し、**[レコードの作成]** をクリックします。

5.  DNS SRV レコードに必要な情報をすべて提供します。

</div>

<div>

## <a name="to-create-a-dns-a-record"></a>DNS A レコードを作成するには

1.  DNS サーバー上で、**[スタート]** ボタンをクリックし、**[コントロール パネル]** をクリックします。次に、**[管理ツール]** をクリックし、**[DNS]** をクリックします。

2.  SIP ドメインのコンソールツリーで、[ **前方参照ゾーン**] を展開し、Lync Server 2013 がインストールされているドメインを右クリックします。

3.  **[新しいホスト (A)]** をクリックします。

4.  DNS SRV レコードに必要な情報をすべて提供します。

</div>

<div>

## <a name="to-verify-a-dns-record"></a>DNS レコードを確認するには

1.  ドメイン内のクライアント コンピューターにログオンします。

2.  **[スタート]** ボタンをクリックし、**[ファイル名を指定して実行]** をクリックします。

3.  コマンド プロンプトで、次のコマンドを実行します。
    
        nslookup <FQDN edge interface>

4.  受け取る応答が、FQDN の適切な IP アドレスに解決しているのを確認します。

</div>

<div>

## <a name="see-also"></a>関連項目


[Hosted Exchange UM との統合のための DNS SRV レコードを作成する](lync-server-2013-create-a-dns-srv-record-for-integration-with-hosted-exchange-um.md)  


[Lync Server 2013 の DNS 要件を決定する](lync-server-2013-determine-dns-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

