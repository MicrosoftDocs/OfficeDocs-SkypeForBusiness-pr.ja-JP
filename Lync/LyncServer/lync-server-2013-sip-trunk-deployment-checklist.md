---
title: 'Lync Server 2013: SIP トランクの展開チェックリスト'
description: 'Lync Server 2013: SIP トランクの展開チェックリスト'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: SIP trunk deployment checklist
ms:assetid: 94f4f03e-19d5-4198-92be-e4076dbb959a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398755(v=OCS.15)
ms:contentKeyID: 48184891
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dbab9647a7146b2478317ab6c020969506f9c0ef
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559043"
---
# <a name="sip-trunk-deployment-checklist-for-lync-server-2013"></a>Lync Server 2013 の SIP トランクの展開チェックリスト

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-21_

SIP トランクを展開する前に、ユーザーとサービスプロバイダーは、それぞれの SIP トランクエンドポイントに関する基本的な接続情報を交換する必要があります。

接続する各 ITSP ゲートウェイについて、次の情報を取得します。

  - IP アドレス

  - 完全修飾ドメイン名 (FQDN)

<div>


> [!NOTE]  
> サービスプロバイダーから、複数の ITSP ゲートウェイに接続するように求められる場合があります。 その場合は、プール内の各 ITSP ゲートウェイと各仲介サーバー間の接続を構成する必要があります。



</div>

サービスプロバイダーに提供する情報は、SIP トランク接続の種類によって異なります。

  - マルチプロトコルラベル切り替え (MPLS) またはプライベートネットワーク接続の場合、ITSP は境界ネットワーク (DMZ、非武装地帯、スクリーンサブネットとも呼ばれます) のルーターのパブリックルーティング可能な IP アドレスを提供します。 ITSP のゲートウェイまたはセッションボーダーコントローラー (SBC) がこのアドレスに到達できることを確認します。 また、ITSP に仲介サーバーの FQDN を指定します。

  - 仮想プライベートネットワーク (VPN) 接続の場合は、ITSP に VPN サーバーの IP アドレスを指定します。

<div>

## <a name="certificate-considerations"></a>証明書に関する考慮事項

SIP トランキング用の証明書が必要かどうかを判断するには、ITSP にプロトコルのサポートがあるかどうかを確認します。

1.  ITSP が伝送制御プロトコル (TCP) のみをサポートしている場合は、証明書は必要ありません。

2.  ITSP がトランスポート層セキュリティ (TLS) をサポートしている場合は、ITSP が証明書を提供する必要があります。

<div>


> [!NOTE]  
> SIP は、リアルタイム転送プロトコル (RTP) またはセキュアリアルタイム転送プロトコル (SRTP) (ボイスオーバー Ip (VoIP) 呼び出しで実際の音声データを管理するプロトコル) と連携して動作します。



</div>

</div>

<div>

## <a name="deployment-process"></a>展開プロセス

SIP トランク接続の Lync Server 側を実装するには、次の手順を実行します。

1.  Lync Server トポロジビルダーを使用して、SIP ドメイントポロジを作成し、構成します。 詳細については、「展開」のドキュメントの「 [Define and configure Topology Builder In Lync Server 2013](lync-server-2013-define-and-configure-a-topology-in-topology-builder.md) 」を参照してください。

2.  Lync Server コントロールパネルを使用して、新しい SIP ドメインの音声ルーティングを構成します。 詳細については、「展開」のドキュメントの「 [構成トランク In Lync Server 2013](lync-server-2013-configuring-trunks.md) 」を参照してください。

3.  **テスト-CsPstnOutboundCall**コマンドレットを使用して、接続をテストします。 詳細については、「lync Server Management Shell」ドキュメントまたは「Lync Server 管理シェルのヘルプ」を参照してください。

</div>

</div>

<span> </span>

</div>

</div>

</div>

