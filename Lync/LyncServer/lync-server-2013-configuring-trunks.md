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
ms.openlocfilehash: f1021295b375e4f28294ffb1ca5738d651f9ced2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734587"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-trunks-in-lync-server-2013"></a>Lync Server 2013 でのトランクの構成

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-11-01_

エンタープライズ Voip の展開の一部として、仲介サーバーと次のピアの1つ以上にトランクを構成して、組織内のエンタープライズボイスクライアントとデバイスの公衆交換電話網 (PSTN) 接続を提供できます。

  - インターネット テレフォニー サービス プロバイダー (ITSP) への SIP トランク接続

  - PSTN ゲートウェイ

  - 構内交換機 (PBX)

詳細については、計画ドキュメントの「 [Lync Server 2013 での PSTN 接続の計画](lync-server-2013-planning-for-pstn-connectivity.md)」を参照してください。

<div>


> [!IMPORTANT]  
> トランクの構成を開始する前に、トポロジが作成され、仲介サーバーとそのピアが構成されて互いに関連付けられていることを確認します。 詳細については、展開ドキュメントの「 <A href="lync-server-2013-define-a-gateway-in-topology-builder.md">Lync Server 2013 でのトポロジビルダーでのゲートウェイの定義</A>」を参照してください。



</div>

<div>


> [!NOTE]  
> トランク構成の一部として、Lync Server 2013 メディアバイパス機能を有効にして、メディアが仲介サーバーをバイパスすることを可能にすることができます。 Trunks は、メディアのバイパスを有効にするかどうかを指定して構成できますが、有効にすることを強くお勧めします。 詳細については、計画ドキュメントの「 <A href="lync-server-2013-planning-for-media-bypass.md">Lync Server 2013 でのメディアのバイパスの計画</A>」を参照してください。



</div>

<div>

## <a name="in-this-section"></a>このセクション中

  - [Lync Server 2013 での複数のトランクのサポート](lync-server-2013-multiple-trunk-support.md)

  - [Lync Server 2013 のクロストランクルーティング](lync-server-2013-inter-trunk-routing.md)

  - [Lync Server 2013 でのトランク構成情報の表示](lync-server-2013-view-trunk-configuration-information.md)

  - [Configure a trunk with media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md)

  - [Lync Server 2013 でメディアをバイパスせずにトランクを構成する](lync-server-2013-configure-a-trunk-without-media-bypass.md)

  - [Lync Server 2013 で、トランク構成設定の新しいコレクションを作成する](lync-server-2013-create-a-new-collection-of-trunk-configuration-settings.md)

  - [Lync Server 2013 で既存の SIP トランク構成設定のコレクションを削除する](lync-server-2013-delete-an-existing-collection-of-sip-trunk-configuration-settings.md)

  - [Lync Server 2013 で SIP トランクの設定を変更する](lync-server-2013-modify-sip-trunk-configuration-settings.md)

  - [Lync Server 2013 で SIP トランクの構成設定をテストする](lync-server-2013-test-sip-trunk-configuration-settings.md)

  - [Lync Server 2013 で個別の SIP trunks に関する情報を表示する](lync-server-2013-view-information-about-individual-sip-trunks.md)

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 でのトポロジビルダーでのゲートウェイの定義](lync-server-2013-define-a-gateway-in-topology-builder.md)  


[Lync Server 2013 での PSTN 接続の計画](lync-server-2013-planning-for-pstn-connectivity.md)  
[Lync Server 2013 でのメディア バイパスの計画](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

