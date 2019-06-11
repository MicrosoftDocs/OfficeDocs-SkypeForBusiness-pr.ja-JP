---
title: 'Lync Server 2013: Hosted Exchange UM 統合のアーキテクチャ'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Hosted Exchange UM integration architecture
ms:assetid: 0094d5dc-1836-441c-b6e2-f88e35203a8d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398067(v=OCS.15)
ms:contentKeyID: 48183222
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2991bb35298534943d030b04c1cae7a438318c62
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833065"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hosted-exchange-um-integration-architecture-in-lync-server-2013"></a>Lync Server 2013 の Hosted Exchange UM 統合のアーキテクチャ

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-09-25_

Lync Server 2013 ExUM ルーティングアプリケーションでは、オンプレミスの Exchange ユニファイドメッセージング (UM) 展開との統合、サービスプロバイダーによってホストされている Exchange UM、またはこの2つの組み合わせをサポートしています。 次の図は、3つのすべての可能性を示しています。

**オンプレミスの Exchange UM 展開と2つのホストされた Exchange プロバイダーとの統合**

![オンプレミスの Lync Server EXCHANGE UM の展開](images/Gg398821.d6498eb9-87ee-40f3-8ecd-852f91546590(OCS.15).jpg "オンプレミスの Lync Server EXCHANGE UM の展開")

次のモードがサポートされています。

  - **オンプレミスの展開:** Lync Server 2013 と Exchange UM は両方とも、エンタープライズ内のローカルサーバーに展開されます。

  - **クロスプレミスの展開:** Lync Server 2013 は企業内のローカルサーバーに展開され、Exchange UM は Microsoft Exchange Online のデータセンターなどのオンラインサービスプロバイダーの機能でホストされます。

  - **混在展開:** Lync Server 2013 の展開では、一部のユーザーのメールボックスが企業内のローカル Exchange サーバー上にあり、一部のメールボックスは、ホスティングされている Exchange service データセンターに置かれています。
    
    <div>
    

    > [!NOTE]  
    > 混在展開は、ユーザーをホストされた Exchange UM に移行するときの移行ソリューションとして使用することができます。また、他のユーザーを転送した後で、一部のユーザーの Exchange UM サービスをオンプレミスのままにしておくと、永続的なソリューションとして使用できます。

    
    </div>

<div>

## <a name="shared-sip-address-space"></a>共有 SIP アドレス空間

Lync Server 2013 をオンプレミスの Exchange UM 展開に統合するには、Lync Server 2013 権限を付与して、Exchange UM Active Directory ドメインサービスオブジェクトを読み取ります。 この方法は、ホストされた Exchange UM との統合には対応していません。ただし、Lync Server 2013 と Exchange UM は別々のフォレストにインストールされているため、信頼関係がありません。

Lync Server 2013 をホストされた Exchange UM と統合するには、*共有 SIP アドレス空間*を構成する必要があります。 この構成では、Lync Server 2013 と hosted Exchange UM サービスプロバイダーの両方で同じ SIP ドメインアドレス空間を利用できます。

<div>


> [!NOTE]  
> 共有 SIP アドレス空間の使用は、クロスプレミスの Lync Server 2013 環境で使用されているアプローチと似ています。一部のユーザーはオンプレミスの展開に所属していて、一部のユーザーは、社内の展開 (Lync Online など) であるためです。 SIP ドメインが分割されます。 Lync Server 2013 をホストされた Exchange UM と統合する場合は、共有 SIP アドレス空間に Exchange UM サービスプロバイダーが含まれていることを確認します。



</div>

Exchange UM サービスプロバイダーと統合するために共有 SIP アドレス空間を構成するには、次のようにエッジサーバーを構成する必要があります。

1.  次のパラメーターを設定するには、 **CsAccessEdgeConfiguration**コマンドレットを実行して、フェデレーション用にエッジサーバーを構成します。
    
      - **UseDnsSrvRouting ** は、エッジ サーバーがフェデレーション要求を送信および受信するときに、DNS SRV レコードを使用するように指定します。
    
      - **AllowFederatedUsers ** は、内部ユーザーとフェデレーション ドメインからのユーザーとの通信を許可するかどうかを指定します。このプロパティは、さらに内部ユーザーが分割ドメインのシナリオでユーザーと通信できるかどうかも決定します。
    
      - **Enablepartnerdiscovery** Lync Server 2013 で DNS レコードを使用して、Active Directory で許可されているドメインの一覧に含まれていないパートナードメインを検出するかどうかを指定します。 False の場合、Lync Server 2013 は、[許可したドメイン] 一覧にあるドメインのみをフェデレーションします。 DNS のサービス ルーティングを使用する場合、このパラメーターは必須です。 ほとんどの展開環境では、すべてのパートナーに対してフェデレーションが開かれることのないように、この値を False に設定します。

2.  中央管理ストアをエッジサーバーにレプリケートし、レプリケーションを確認します。 詳細については、展開ドキュメントの「 [Lync Server 2013 トポロジをエクスポートして、microsoft edge インストール用の外部メディアにコピーする](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md)」を参照してください。

3.  次のパラメーターを設定するには、**新しい-CsHostingProvider**コマンドレットを実行して、エッジサーバーで*ホスティングプロバイダー*を構成します。
    
      - **Id**は、ホストされている**Exchange UM**など、作成しているホスティングプロバイダーの一意の文字列値識別子を指定します。
    
      - **Enabled ** は、ドメインとホスティング プロバイダー間のネットワーク接続が有効になっているかどうかを示します。 **True**に設定する必要があります。
    
      - **EnabledSharedAddressSpace** は、ホスティング プロバイダーが共有 SIP アドレス スペース シナリオで使用されるかどうかを示します。 **True**に設定する必要があります。
    
      - **Hostているユーザー**は、ホスティングプロバイダーが Lync Server 2013 アカウントをホストするために使用されているかどうかを示します。 **False**に設定する必要があります。
    
      - **Proxyfqdn**は、ホスティングプロバイダーによって使用されるプロキシサーバーの完全修飾ドメイン名 (FQDN) を指定します。たとえば、 **proxyserver.fabrikam.com**のように指定します。 この情報については、ホスティングプロバイダーにお問い合わせください。 この値は変更できません。 ホスティングプロバイダーがプロキシサーバーを変更した場合は、そのプロバイダーのエントリを削除してから再作成する必要があります。
    
      - **Islocal**は、ホスティングプロバイダーによって使用されたプロキシサーバーが Lync server 2013 トポロジ内に含まれているかどうかを示します。 **False**に設定する必要があります。

</div>

</div>

<span> </span>

</div>

</div>

</div>

