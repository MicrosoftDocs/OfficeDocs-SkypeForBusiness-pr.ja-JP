---
title: Skype for Business での通話受付管理のコンポーネントとトポロジ
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 0beec6be-2431-4255-a3d2-512dd030e66a
description: MPLS ネットワーク、SIP トランク、またはサードパーティの PSTN ゲートウェイまたは PBX を使用している場合の通話受付管理 (CAC) の計画。 Skype for Business Server エンタープライズ VoIP。
ms.openlocfilehash: e40525121020259a40f10d90cd79d70aaa749ac3
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825847"
---
# <a name="components-and-topologies-for-call-admission-control-in-skype-for-business"></a>Skype for Business での通話受付管理のコンポーネントとトポロジ

MPLS ネットワーク、SIP トランク、またはサードパーティの PSTN ゲートウェイまたは PBX を使用している場合の通話受付管理 (CAC) の計画。 Skype for Business Server エンタープライズ VoIP。

このセクションのトピックでは、通話受付管理 (CAC) をさまざまな種類のネットワーク トポロジで展開する際に特に考慮する点について説明します。

## <a name="call-admission-control-on-an-mpls-network"></a>MPLS ネットワーク上の通話受付管理

Multiprotocol Label Switching (MPLS) では、すべてのサイトがフル メッシュで接続されます。つまり、すべてのサイトがインターネット サービス プロバイダーの MPLS バックボーンに直接接続され、各サイトが WAN リンクから MPLS にかけて使用されるプロビジョニングされた帯域幅であるということです。IP ルーティングを制御するネットワーク ハブやセントラル サイトはありません。次の図に、MPLS トポロジに基づく簡単なネットワークを示します。

**MPLS ネットワークの例**

![CAC と MPLS](../../media/CAC_MPLS_1.jpg)

MPLS ネットワークで通話受付管理 (CAC) を展開するには、MPLS クラウドを表すネットワーク地域を作成し、MPLS の各サテライト サイトを表すネットワーク サイトを作成します。 次の図で、前の図の MPLS ネットワークの例を表すための、ネットワーク地域およびネットワーク サイトの構成方法について説明します。 全体的な帯域幅および帯域幅セッションの制限は、各ネットワーク サイトから MPLS クラウドを表すネットワーク地域までの WAN リンクの容量に基づきます。

**MPLS ネットワークのネットワーク地域およびネットワーク サイト**

![MPLS を使用した通話受付管理 (CAC) の図](../../media/CAC_MPLS_2.jpg)

## <a name="call-admission-control-on-a-sip-trunk"></a>SIP トランクでの通話受付管理

SIP トランクに通話受付管理 (CAC) を展開するには、インターネット テレフォニー サービス プロバイダー (ITSP) を表すためのネットワーク サイトを作成します。SIP トランクに帯域幅ポリシーの値を適用するには、企業内のネットワーク サイトと ITSP を表すために作成するネットワーク サイトのサイト間ポリシーを作成します。

次の図は、SIP トランクの CAC 展開の例を示しています。

**SIP トランクの CAC 構成**

![通話受付管理の SIP トランキングの図](../../media/CAC_SIP_trunk_1.jpg)

SIP トランクに CAC を構成するには、CAC の展開時に次の作業を行う必要があります。

1. ITSP を表すためのネットワーク サイトを作成します。 ネットワーク サイトを適切なネットワーク地域に関連付けて、このネットワーク サイトの音声とビデオにゼロの帯域幅を割り当てます。 詳細については、「展開」のドキュメントの「[Configure Network Sites for CAC](https://technet.microsoft.com/library/afcea38f-5789-45ec-97af-c6e38364950c.aspx)」を参照してください。

    > [!NOTE]
    > ITSP では、このネットワーク サイト構成は機能しません。 帯域幅ポリシーの値は、手順 2 で実際に適用されます。

2. 手順 1 で作成したサイトの関連するパラメーター値を使用して、SIP トランクのサイト間リンクを作成します。 たとえば、企業内のネットワーク サイトの名前を NetworkSiteID1 パラメーターの値として使用し、ITSP ネットワーク サイトの名前を NetworkSiteID2 パラメーターの値として使用します。 詳細については、「展開」のドキュメントの [「Skype for Business Server](../../deploy/deploy-enterprise-voice/create-network-intersite-policies.md) でのネットワーク サイト間ポリシーの作成」と [New-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/new-csnetworkintersitepolicy?view=skype-ps)を参照してください。

3. ITSP からセッション ボーダー コントローラー (SCB) メディア終端ポイントの IP アドレスを取得します。 サブネット マスクが 32 の IP アドレスを、ITSP を表すネットワーク サイトに追加します。 詳細については、「[Associate a Subnet with a Network Site](https://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx)」を参照してください。

## <a name="call-admission-control-with-a-third-party-pstn-gateway-or-pbx"></a>サードパーティの PSTN ゲートウェイまたは PBX を使用した通話受付管理

このトピックでは、仲介サーバーのゲートウェイ インターフェイスと、サードパーティの公衆交換電話網 (PSTN) ゲートウェイまたは PBX (Private Branch Exchange) との間のリンクに通話受付管理 (CAC) を展開する方法の例について説明します。

### <a name="case-1-cac-between-the-mediation-server-and-a-pstn-gateway"></a>ケース 1: 仲介サーバーと PSTN ゲートウェイの間の CAC

CAC は、仲介サーバーのゲートウェイ インターフェイスからサードパーティ PBX または PSTN ゲートウェイへの WAN リンクに展開できます。

**ケース 1: 仲介サーバーと PSTN ゲートウェイの間の CAC**

![ケース 1: 仲介サーバー PSTN ゲートウェイ間の CAC](../../media/CAC_gateways_1.jpg)

この例では、仲介サーバーと PSTN ゲートウェイの間に CAC が適用されます。 ネットワーク サイト 1 の Skype for Business クライアント ユーザーがネットワーク サイト 2 の PSTN ゲートウェイを介して PSTN 通話を発信する場合、メディアは WAN リンクを通過します。 したがって、PSTN セッションごとに 2 つの CAC チェックが実行されます。

- Skype for Business クライアント アプリケーションと仲介サーバーの間

- 仲介サーバーと PSTN ゲートウェイの間

これは、ネットワーク サイト 1 のクライアントへの PSTN 通話の着信と、ネットワーク サイト 1 のクライアント アプリケーションからの発信 PSTN 通話の両方で機能します。

> [!NOTE]
> PSTN ゲートウェイが属する IP サブネットが構成され、ネットワーク サイト 2 に関連付けられている必要があります。

> [!NOTE]
> 仲介サーバーの両方のインターフェイスが属する IP サブネットが構成され、ネットワーク サイト 1 に関連付けられている必要があります。

> [!NOTE]
> 詳細については、「[Associate a Subnet with a Network Site](https://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx)」を参照してください。

### <a name="case-2-cac-between-the-mediation-server-and-a-third-party-pbx-with-media-termination-point"></a>ケース 2: 仲介サーバーと、メディア終端ポイントを使用するサードパーティ製 PBX 間の CAC

この構成はケース 1 に似ています。 どちらの場合も、仲介サーバーは WAN リンクの反対側の端でメディアを終端するデバイスを知り、仲介サーバー上で次ホップとして PSTN ゲートウェイまたはメディア終端ポイント (MTP) を使用する PBX の IP アドレスが構成されます。

**ケース 2: 仲介サーバーと MTP を使用するサードパーティ PBX 間の CAC**

![ケース 2: MTP を使用する仲介サーバー PBX 間の CAC](../../media/CAC_gateways_2.jpg)

この例では、仲介サーバーと PBX/MTP の間に CAC が適用されます。 ネットワーク サイト 1 の Skype for Business クライアント ユーザーが、ネットワーク サイト 2 にある PBX/MTP を介して PSTN 通話を行う場合、メディアは WAN リンクを通過します。 したがって、PSTN セッションごとに 2 つの CAC チェックが実行されます。

- Skype for Business クライアント アプリケーションと仲介サーバーの間

- 仲介サーバーと PBX/MTP の間

これは、ネットワーク サイト 1 のクライアントへの PSTN 通話の着信と、ネットワーク サイト 1 のクライアントからの発信 PSTN 通話の両方で機能します。

> [!NOTE]
> MTP が属する IP サブネットが構成され、ネットワーク サイト 2 に関連付けられている必要があります。

> [!NOTE]
> 仲介サーバーの両方のインターフェイスが属する IP サブネットが構成され、ネットワーク サイト 1 に関連付けられている必要があります。

> [!NOTE]
> 詳細については、「[Associate a Subnet with a Network Site](https://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx)」を参照してください。

### <a name="case-3-cac-between-the-mediation-server-and-a-third-party-pbx-without-a-media-termination-point"></a>ケース 3: 仲介サーバーとメディア終端ポイントのないサードパーティ PBX 間の CAC

ケース 3 は、最初の 2 つのケースとは少し異なります。 サードパーティ PBX に MTP がない場合、仲介サーバーは、サード パーティ製 PBX への送信セッション要求に対して、メディアが PBX 境界で終了する場所を知りません。 この場合、メディアは仲介サーバーとサードパーティのエンドポイント デバイスの間を直接流れます。

**ケース 3: 仲介サーバーと MTP を使用しないサードパーティ PBX 間の CAC**

![ケース 3: 仲介サーバー PBX 間の CAC (MTP なし)](../../media/CAC_gateways_3.jpg)

この例では、ネットワーク サイト 1 の Skype for Business クライアント ユーザーが PBX を介してユーザーに電話をかけますが、仲介サーバーはプロキシ レグ (Skype for Business クライアント アプリケーションと仲介サーバーの間) でのみ CAC チェックを実行できます。 セッションが要求されている間、仲介サーバーはエンドポイント デバイスに関する情報を持たないので、通話の確立前に WAN リンク (仲介サーバーとサードパーティのエンドポイントの間) で CAC チェックを実行することはできません。 ただし、セッションが確立されると、仲介サーバーはトランクで使用される帯域幅の計算を容易にします。

サードパーティのエンドポイントから発信された通話の場合、そのエンドポイント デバイスに関する情報はセッション要求時に利用できます。CAC チェックは仲介サーバーの両側で実行できます。

> [!NOTE]
> エンドポイント デバイスが属する IP サブネットが構成され、ネットワーク サイト 2 に関連付けられている必要があります。

> [!NOTE]
> 仲介サーバーの両方のインターフェイスが属する IP サブネットが構成され、ネットワーク サイト 1 に関連付けられている必要があります。

> [!NOTE]
> 詳細については、「[Associate a Subnet with a Network Site](https://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx)」を参照してください。


