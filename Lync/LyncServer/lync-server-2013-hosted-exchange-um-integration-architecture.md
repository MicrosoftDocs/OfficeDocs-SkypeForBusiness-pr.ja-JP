---
title: 'Lync Server 2013: Hosted Exchange UM 統合アーキテクチャ'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hosted Exchange UM integration architecture
ms:assetid: 0094d5dc-1836-441c-b6e2-f88e35203a8d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398067(v=OCS.15)
ms:contentKeyID: 48183222
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9905fa6de1f8461d81ffe9d7e5cf79108c35e80c
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42198680"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="hosted-exchange-um-integration-architecture-in-lync-server-2013"></a>Lync Server 2013 の Hosted Exchange UM 統合アーキテクチャ

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-25_

Lync Server 2013 ExUM ルーティングアプリケーションは、オンプレミスの Exchange ユニファイドメッセージング (UM) 展開、サービスプロバイダーによってホストされる Exchange UM、またはこの2つの組み合わせを使用して統合をサポートします。 次の図は、3つのすべての可能性を示しています。

**内部設置型 Exchange UM 展開環境と 2 社の Hosted Exchange プロバイダーとの統合**

![オンプレミスの Lync Server Exchange UM 展開](images/Gg398821.d6498eb9-87ee-40f3-8ecd-852f91546590(OCS.15).jpg "オンプレミスの Lync Server Exchange UM 展開")

次のモードがサポートされています。

  - **オンプレミス展開:** Lync Server 2013 と Exchange UM は、どちらも企業内のローカルサーバーに展開されています。

  - **クロスプレミス展開:** Lync Server 2013 は、企業内のローカルサーバーに展開され、Exchange UM は Microsoft Exchange Online データセンターなどのオンラインサービスプロバイダーの施設でホストされます。

  - **混在展開:** Lync Server 2013 の展開には、企業内のローカル Exchange サーバーに所属するユーザーメールボックスと、ホストされている Exchange サービスデータセンターに所属する一部のメールボックスがあります。
    
    <div>
    

    > [!NOTE]  
    > 混合展開は、評価のためにユーザーを Hosted Exchange UM に段階的に移行する場合の暫定的なソリューションとして、または、一部のユーザーの Exchange UM サービスを社外に移行した後で、他のユーザーの Exchange UM サービスを内部設置型で維持する場合の恒久的なソリューションとして使用できます。

    
    </div>

<div>

## <a name="shared-sip-address-space"></a>共有 SIP アドレス スペース

Lync Server 2013 を社内 Exchange UM 展開に統合するには、「Lync Server 2013 に Exchange UM Active Directory ドメインサービスオブジェクトを読み取るためのアクセス許可を付与します。 ただし、このアプローチは、ホストされた Exchange UM との統合には対応していません。ただし、Lync Server 2013 と Exchange UM は別々のフォレストにインストールされ、それらの間に信頼関係はありません。

Lync Server 2013 を hosted Exchange UM と統合するには、*共有 SIP アドレススペース*を構成する必要があります。 この構成では、Lync Server 2013 と hosted Exchange UM サービスプロバイダーの両方で同じ SIP ドメインアドレススペースを使用できます。

<div>


> [!NOTE]  
> 共有 SIP アドレススペースの使用は、クロスプレミスの Lync Server 2013 環境で使用されるアプローチと似ています。これは、一部のユーザーが社内展開に所属しており、一部のユーザーがホスト型展開 (Lync Online など) に所属している場合です。 SIP ドメインは、2 者間で分割されています。 Lync Server 2013 を hosted Exchange UM と統合する場合は、共有 SIP アドレススペースに Exchange UM サービスプロバイダーを含めるようにしてください。



</div>

Exchange UM サービス プロバイダーとの統合用に共有 SIP アドレス スペースを構成するには、エッジ サーバーを以下のように構成する必要があります。

1.  エッジ サーバーでフェデレーションを構成するには、**Set-CsAccessEdgeConfiguration** コマンドレットを実行して、以下のパラメーターを設定します。
    
      - **UseDnsSrvRouting** は、エッジ サーバーがフェデレーション要求を送信および受信するときに、DNS SRV レコードを使用するように指定します。
    
      - **AllowFederatedUsers** は、内部ユーザーとフェデレーション ドメインからのユーザーとの通信を許可するかどうかを指定します。 このプロパティは、さらに内部ユーザーが分割ドメインのシナリオでユーザーと通信できるかどうかも決定します。
    
      - **Enablepartnerdiscovery** Lync Server 2013 が DNS レコードを使用して、Active Directory 許可ドメインリストに登録されていないパートナードメインの検出を試行するかどうかを指定します。 False の場合、Lync Server 2013 は、許可されたドメインリストにあるドメインとのみフェデレーションを行います。 DNS のサービス ルーティングを使用する場合、このパラメーターは必須です。 ほとんどの展開環境では、すべてのパートナーに対してフェデレーションが開かれることのないように、この値を False に設定します。

2.  中央管理ストアをエッジサーバーにレプリケートし、レプリケーションを確認します。 詳細については、「展開」のドキュメントの「 [Export The Lync Server 2013 topology」および「external media にコピーする](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md)」を参照してください。

3.  **New-CsHostingProvider** コマンドレットを実行して以下のパラメーターを設定することで、** ホスティング プロバイダーをエッジ サーバー上で構成します。
    
      - **Identity** は、作成しているホスティング プロバイダーの一意の文字列値からなる識別子 (**Hosted Exchange UM** など) を指定します。
    
      - **Enabled** は、ドメインとホスティング プロバイダー間のネットワーク接続が有効になっているかどうかを示します。 **True** に設定する必要があります。
    
      - **EnabledSharedAddressSpace** は、ホスティング プロバイダーが共有 SIP アドレス スペース シナリオで使用されるかどうかを示します。**True** に設定する必要があります。
    
      - **Hostているユーザー**は、ホスティングプロバイダーが Lync Server 2013 アカウントをホストするために使用されるかどうかを示します。 **False** に設定する必要があります。
    
      - **ProxyFQDN** は、ホスティング プロバイダーによって使用されるプロキシ サーバーの完全修飾ドメイン名 (FQDN) (**proxyserver.fabrikam.com** など) を指定します。 この情報については、ホスティング プロバイダーに問い合わせてください。 この値は変更できません。 ホスティング プロバイダーがプロキシ サーバーを変更すると、そのプロバイダーのエントリを削除して再作成する必要があります。
    
      - **Islocal**は、ホスティングプロバイダーによって使用されるプロキシサーバーが Lync server 2013 トポロジ内に含まれているかどうかを示します。 **False** に設定する必要があります。

</div>

</div>

<span> </span>

</div>

</div>

</div>

