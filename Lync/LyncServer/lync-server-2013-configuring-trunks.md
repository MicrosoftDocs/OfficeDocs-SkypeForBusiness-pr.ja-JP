---
title: 'Lync Server 2013: トランクの構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring trunks
ms:assetid: 0c339511-a185-484e-94f0-dbe918b7e48a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398170(v=OCS.15)
ms:contentKeyID: 48183389
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9c2fd4a79937477edbe01f5550a81e92a663d3d8
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48517344"
---
# <a name="configuring-trunks-in-lync-server-2013"></a>Lync Server 2013 でのトランクの構成

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-11-01_

エンタープライズ Voip の展開の一部として、仲介サーバーと次の1つ以上のピアの間のトランクを構成して、組織内のエンタープライズ Voip クライアントおよびデバイスの公衆交換電話網 (PSTN) 接続を提供することができます。

  - インターネット テレフォニー サービス プロバイダー (ITSP) への SIP トランク接続

  - PSTN ゲートウェイ

  - 構内交換機 (PBX)

詳細については、「計画」のドキュメントの「 [planning FOR PSTN connectivity In Lync Server 2013](lync-server-2013-planning-for-pstn-connectivity.md) 」を参照してください。

<div>


> [!IMPORTANT]  
> トランク構成を開始する前に、トポロジが既に作成済みであること、および仲介サーバーとそのピアが構成され、互いに関連付けられていることを確認します。 詳細については、「展開」のドキュメントの「 <A href="lync-server-2013-define-a-gateway-in-topology-builder.md">Lync Server 2013 のトポロジビルダーでのゲートウェイの定義</A> 」を参照してください。



</div>

<div>


> [!NOTE]  
> トランク構成の一環として、Lync Server 2013 media バイパス機能を有効にして、メディアが仲介サーバーをバイパスできるようにすることができます。 トランクは、メディアバイパスを有効にするかどうかにかかわらず構成できますが、有効にすることを強くお勧めします。 詳細については、「計画」のドキュメントの「 <A href="lync-server-2013-planning-for-media-bypass.md">planning for media バイパス In Lync Server 2013</A> 」を参照してください。



</div>

<div>

## <a name="in-this-section"></a>このセクションの内容

  - [Lync Server 2013 での複数トランクのサポート](lync-server-2013-multiple-trunk-support.md)

  - [Lync Server 2013 でのトランク間ルーティング](lync-server-2013-inter-trunk-routing.md)

  - [Lync Server 2013 でのトランク構成情報の表示](lync-server-2013-view-trunk-configuration-information.md)

  - [Lync Server 2013 でメディアバイパスを使用してトランクを構成する](lync-server-2013-configure-a-trunk-with-media-bypass.md)

  - [Lync Server 2013 でメディアバイパスを使用せずにトランクを構成する](lync-server-2013-configure-a-trunk-without-media-bypass.md)

  - [Lync Server 2013 でのトランク構成設定の新しいコレクションの作成](lync-server-2013-create-a-new-collection-of-trunk-configuration-settings.md)

  - [Lync Server 2013 の SIP トランク構成設定の既存コレクションの削除](lync-server-2013-delete-an-existing-collection-of-sip-trunk-configuration-settings.md)

  - [Lync Server 2013 での SIP トランク構成設定の変更](lync-server-2013-modify-sip-trunk-configuration-settings.md)

  - [Lync Server 2013 での SIP トランク構成設定のテスト](lync-server-2013-test-sip-trunk-configuration-settings.md)

  - [Lync Server 2013 の個々の SIP トランクに関する情報を表示する](lync-server-2013-view-information-about-individual-sip-trunks.md)

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 のトポロジビルダーでゲートウェイを定義する](lync-server-2013-define-a-gateway-in-topology-builder.md)  


[Lync Server 2013 での PSTN 接続の計画](lync-server-2013-planning-for-pstn-connectivity.md)  
[Lync Server 2013 でのメディアバイパスの計画](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

