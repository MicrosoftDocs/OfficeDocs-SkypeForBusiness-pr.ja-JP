---
title: 'Lync Server 2013: SIP トランクの展開チェックリスト'
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
ms.openlocfilehash: ef670fc4ae9e8a9acba3277a00fc0daf6ff766b3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764493"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="sip-trunk-deployment-checklist-for-lync-server-2013"></a>Lync Server 2013 に関する SIP トランクの展開チェックリスト

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-09-21_

SIP トランクを展開する前に、お客様とサービスプロバイダがそれぞれの SIP トランクエンドポイントに関する基本的な接続情報を交換する必要があります。

接続する各 ITSP ゲートウェイについて次の情報を取得します。

  - IP アドレス

  - 完全修飾ドメイン名 (FQDN)

<div>


> [!NOTE]  
> サービスプロバイダーから、複数の ITSP ゲートウェイに接続するように求められる場合があります。 その場合は、各 ITSP ゲートウェイとプール内の各仲介サーバー間の接続を構成する必要があります。



</div>

サービスプロバイダに提供する情報は、SIP トランク接続の種類によって異なります。

  - マルチプロトコルラベル切り替え (MPLS) またはプライベートネットワーク接続の場合は、ITSP に境界ネットワーク (DMZ、非武装地帯、スクリーンサブネットとも呼ばれます) のルーターのパブリックルーティング可能な IP アドレスを指定します。 ITSP のゲートウェイまたはセッション境界コントローラー (SBC) がこのアドレスに到達できることを確認します。 また、ITSP に仲介サーバーの FQDN を指定します。

  - 仮想プライベートネットワーク (VPN) 接続の場合、ITSP に VPN サーバーの IP アドレスを指定します。

<div>

## <a name="certificate-considerations"></a>証明書に関する考慮事項

SIP トランク用の証明書が必要かどうかを判断するには、お使いの ITSP でプロトコルのサポートについて確認してください。

1.  ITSP が伝送制御プロトコル (TCP) のみをサポートしている場合は、証明書は必要ありません。

2.  ITSP がトランスポート層セキュリティ (TLS) をサポートしている場合、ITSP は証明書を提供する必要があります。

<div>


> [!NOTE]  
> SIP は、リアルタイムトランスポートプロトコル (RTP) またはセキュリティで保護されたリアルタイムトランスポートプロトコル (SRTP) と連携し、ボイスオーバーインターネットプロトコル (VoIP) 通話で実際のボイスデータを管理するプロトコルに対応しています。



</div>

</div>

<div>

## <a name="deployment-process"></a>展開プロセス

SIP トランク接続の Lync サーバー側を実装するには、次の手順を実行します。

1.  Lync Server Topology Builder を使用して、SIP ドメイントポロジを作成し、構成します。 詳細については、展開ドキュメントの「トポロジ[ビルダーでの Lync Server 2013 のトポロジの定義と構成](lync-server-2013-define-and-configure-a-topology-in-topology-builder.md)」を参照してください。

2.  Lync Server コントロールパネルを使用して、新しい SIP ドメインの音声ルーティングを構成します。 詳細については、展開ドキュメントの「 [Lync Server 2013 での trunks の構成](lync-server-2013-configuring-trunks.md)」を参照してください。

3.  **テスト-CsPstnOutboundCall**コマンドレットを使用して接続をテストします。 詳細については、「Lync Server 管理シェルのドキュメント」または「Lync Server 管理シェルのヘルプ」を参照してください。

</div>

</div>

<span> </span>

</div>

</div>

</div>

