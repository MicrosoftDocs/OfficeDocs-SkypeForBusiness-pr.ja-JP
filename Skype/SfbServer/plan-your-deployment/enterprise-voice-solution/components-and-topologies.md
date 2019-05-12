---
title: コンポーネントおよびトポロジの受付制御に電話 Skype ビジネス
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 0beec6be-2431-4255-a3d2-512dd030e66a
description: MPLS ネットワーク、SIP トランク、またサードパーティの PSTN ゲートウェイまたは PBX を使用している場合の通話受付管理 (CAC) の計画について説明します。 ビジネス サーバーのエンタープライズ VoIP Skype に適用されます。
ms.openlocfilehash: 1a727805cb298a7ba4059c47990a57e2552a3e55
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33925293"
---
# <a name="components-and-topologies-for-call-admission-control-in-skype-for-business"></a>コンポーネントおよびトポロジの受付制御に電話 Skype ビジネス

MPLS ネットワーク、SIP トランク、またサードパーティの PSTN ゲートウェイまたは PBX を使用している場合の通話受付管理 (CAC) の計画について説明します。 ビジネス サーバーのエンタープライズ VoIP Skype に適用されます。

このセクションのトピックでは、通話受付管理 (CAC) をさまざまな種類のネットワーク トポロジで展開する際に特に考慮する点について説明します。

## <a name="call-admission-control-on-an-mpls-network"></a>MPLS ネットワーク上の通話受付管理

Multiprotocol Label Switching (MPLS) では、すべてのサイトがフル メッシュで接続されます。つまり、すべてのサイトがインターネット サービス プロバイダーの MPLS バックボーンに直接接続され、各サイトが WAN リンクから MPLS クラウドにかけて使用されるプロビジョニングされた帯域幅であるということです。IP ルーティングを制御するネットワーク ハブや中央サイトはありません。次の図に、MPLS トポロジに基づく簡単なネットワークを示します。

**MPLS ネットワークの例**

![MPLS が含まれる CAC](../../media/CAC_MPLS_1.jpg)

MPLS ネットワークで通話受付管理 (CAC) を展開するには、MPLS クラウドを表すネットワーク地域を作成し、MPLS の各サテライト サイトを表すネットワーク サイトを作成します。 次の図で、前の図の MPLS ネットワークの例を表すための、ネットワーク地域およびネットワーク サイトの構成方法について説明します。 全体的な帯域幅および帯域幅セッションの制限は、各ネットワーク サイトから MPLS クラウドを表すネットワーク地域までの WAN リンクの容量に基づきます。

**MPLS ネットワークのネットワーク地域およびネットワーク サイト**

![MPLS が含まれない通話受付管理 (CAC)](../../media/CAC_MPLS_2.jpg)

## <a name="call-admission-control-on-a-sip-trunk"></a>SIP トランク上の通話受付管理

SIP トランクに通話受付管理 (CAC) を展開するには、インターネット テレフォニー サービス プロバイダー (ITSP) を表すためのネットワーク サイトを作成します。SIP トランクに帯域幅ポリシーの値を適用するには、企業内のネットワーク サイトと ITSP を表すために作成するネットワーク サイトのサイト間ポリシーを作成します。

次の図は、SIP トランクの CAC 展開の例を示しています。

**SIP トランクの CAC 構成**

![通話受付管理の SIP トランキングの図](../../media/CAC_SIP_trunk_1.jpg)

SIP トランクに CAC を構成するには、CAC の展開時に次の作業を行う必要があります。

1. ITSP を表すためのネットワーク サイトを作成します。ネットワーク サイトを適切なネットワーク地域に関連付けて、このネットワーク サイトの音声とビデオにゼロの帯域幅を割り当てます。詳細については、「展開」のドキュメントの「[Configure Network Sites for CAC](https://technet.microsoft.com/library/afcea38f-5789-45ec-97af-c6e38364950c.aspx)」を参照してください。

    > [!NOTE]
    > ITSP では、このネットワーク サイト構成は機能しません。 帯域幅ポリシーの値は、手順 2 で実際に適用されます。

2. 手順 1 で作成したサイトの関連するパラメーター値を使用して、SIP トランクのサイト間リンクを作成します。 たとえば、企業内のネットワーク サイトの名前を NetworkSiteID1 パラメーターの値として使用し、ITSP ネットワーク サイトの名前を NetworkSiteID2 パラメーターの値として使用します。 詳細については、展開に関するドキュメント、および[新規 CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/new-csnetworkintersitepolicy?view=skype-ps) [Skype ビジネス サーバー用のネットワーク サイト間ポリシーの作成](../../deploy/deploy-enterprise-voice/create-network-intersite-policies.md)を参照してください。

3. セッション ボーダー コント ローラー (SCB) の IP アドレスを取得、ITSP からメディアの終了点です。 サブネット マスクが 32 の IP アドレスを、ITSP を表すネットワーク サイトに追加します。 詳細については、「[Associate a Subnet with a Network Site](https://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx)」を参照してください。

## <a name="call-admission-control-with-a-third-party-pstn-gateway-or-pbx"></a>サードパーティの PSTN ゲートウェイまたは PBX での通話受付管理

このトピックでは、仲介サーバーのゲートウェイ インターフェイス、およびサードパーティ製の公衆交換電話網 (PSTN) ゲートウェイまたは構内交換 (機 PBX) の間のリンクの呼受付制御 (CAC) を展開する方法の例について説明します。

### <a name="case-1-cac-between-the-mediation-server-and-a-pstn-gateway"></a>ケース 1: 仲介サーバーおよび PSTN ゲートウェイ間の CAC

CAC は、WAN で展開できるサード パーティの PBX または PSTN ゲートウェイに仲介サーバーのゲートウェイ インターフェイスからリンクします。

**ケース 1: 仲介サーバーおよび PSTN ゲートウェイ間の CAC**

![ケース 1: 仲介サーバーと PSTN ゲートウェイ間の CAC](../../media/CAC_gateways_1.jpg)

この例では、CAC は、仲介サーバーと PSTN ゲートウェイとの間に適用されます。 ビジネス ネットワーク サイト 1 のクライアントのユーザーは、Skype では、ネットワーク サイト 2 の PSTN ゲートウェイ経由の PSTN 通話を配置する場合、メディアは WAN リンクを介して送られます。 そのため、PSTN セッションごとに 2 度の CAC チェックが行われます。

- ビジネス ・ クライアント ・ アプリケーションの Skype と仲介サーバーとの間

- 仲介サーバーと PSTN ゲートウェイ間

これは、ネットワーク サイト 1 のクライアントへの PSTN 着信、およびネットワーク サイト 1 のクライアント アプリケーションからの PSTN 発信のどちらでも行われます。

> [!NOTE]
> PSTN ゲートウェイが属する IP サブネットが、確実に構成され、ネットワーク サイト 2 と関連付けられているようにしてください。

> [!NOTE]
> 仲介サーバーの両方のインターフェイスが属する IP サブネットが構成され、ネットワーク サイト 1 に関連付けられていることを確認ください。

> [!NOTE]
> 詳細については、「[Associate a Subnet with a Network Site](https://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx)」を参照してください。

### <a name="case-2-cac-between-the-mediation-server-and-a-third-party-pbx-with-media-termination-point"></a>ケース 2: CAC を仲介サーバーおよびメディア終端ポイントでサード パーティの PBX との間

この構成はケース 1 に類似したものです。 どちらの場合で、仲介サーバーは、どのようなデバイスは、WAN リンクの反対側の端にあるメディアを終了するを知っているし、次ホップとして仲介サーバー、PSTN ゲートウェイまたは PBX メディア終端ポイント (MTP) の IP アドレスが構成されています。

**ケース 2: 仲介サーバーおよび MTP を含むサードパーティ製 PBX 間の CAC**

![ケース 2: 仲介サーバーと PBX (MTP が含まれる) 間の CAC](../../media/CAC_gateways_2.jpg)

この例では、CAC は、仲介サーバーと PBX と MTP との間に適用されます。 ビジネス ネットワーク サイト 1 のクライアントのユーザーは、Skype では、ネットワーク サイト 2 にある PBX と MTP を PSTN の呼び出しを配置する場合、メディアは WAN リンクを通じてフローします。 そのため、それぞれの PSTN セッションごとに 2 度の CAC チェックが行われます。

- ビジネス ・ クライアント ・ アプリケーションの Skype と仲介サーバーとの間

- 仲介サーバーと PBX と MTP との間

これは、ネットワーク サイト 1 のクライアントへの PSTN 着信、およびネットワーク サイト 1 のクライアントからの PSTN 発信のどちらでも行われます。

> [!NOTE]
> MTP が属する IP サブネットが、確実に構成され、ネットワーク サイト 2 と関連付けられているようにしてください。

> [!NOTE]
> 仲介サーバーの両方のインターフェイスが属する IP サブネットが構成され、ネットワーク サイト 1 に関連付けられていることを確認ください。

> [!NOTE]
> 詳細については、「[Associate a Subnet with a Network Site](https://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx)」を参照してください。

### <a name="case-3-cac-between-the-mediation-server-and-a-third-party-pbx-without-a-media-termination-point"></a>ケース 3: CAC を仲介サーバーとメディアの終了ポイントのないサード パーティの PBX との間

ケース 3 は、最初の 2 つのケースとは少し異なります。 サード パーティの PBX に MTP がない場合は、送信セッションのサード ・ パーティ製 PBX、仲介サーバーへの要求を認識しません、メディアが PBX の境界で終了。 この例では、メディアは仲介サーバーおよびサードパーティ製エンドポイント デバイスの間で直接フローします。

**ケース 3: 仲介サーバーおよび MTP が含まれないサードパーティ製 PBX 間の CAC**

![ケース 3: 仲介サーバーと PBX (MTP が含まれない) 間の CAC](../../media/CAC_gateways_3.jpg)

この例では、ビジネス ネットワーク サイト 1 のクライアントのユーザーは、Skype、PBX を使用してユーザーへの呼び出しを配置する場合、仲介サーバーが (ビジネス ・ クライアント ・ アプリケーションの Skype) と仲介サーバー間のプロキシの区間でのみ CAC チェックを実行します。 WAN の CAC チェックを実行できないため、仲介サーバーにはエンドポイント デバイスに関する情報はありません、セッションを要求されているときに、呼び出しを確立する前に (仲介サーバーおよびサードパーティ製エンドポイント) 間のリンクです。 セッションが確立されると、ただし、仲介サーバーはトランクで使用される帯域幅の計算で容易にします。

サードパーティのエンドポイントから発信された通話にセッション要求時にそのエンドポイント デバイスに関する情報があるし、仲介サーバーの両側で CAC チェックを実行することができます。

> [!NOTE]
> エンドポイント デバイスが属する IP サブネットが、確実に構成され、ネットワーク サイト 2 と関連付けられているようにしてください。

> [!NOTE]
> 仲介サーバーの両方のインターフェイスが属する IP サブネットが構成され、ネットワーク サイト 1 に関連付けられていることを確認ください。

> [!NOTE]
> 詳細については、「[Associate a Subnet with a Network Site](https://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx)」を参照してください。


