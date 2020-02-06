---
title: Skype for Business の通話受付制御のコンポーネントとトポロジ
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: MPLS ネットワーク、SIP トランク、またサードパーティの PSTN ゲートウェイまたは PBX を使用している場合の通話受付管理 (CAC) の計画について説明します。 Skype for Business Server Enterprise Voice に適用されます。
ms.openlocfilehash: 7fcbc3e8c7fc7b4139fd9c83718db59af099f47f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803117"
---
# <a name="components-and-topologies-for-call-admission-control-in-skype-for-business"></a>Skype for Business の通話受付制御のコンポーネントとトポロジ

MPLS ネットワーク、SIP トランク、またサードパーティの PSTN ゲートウェイまたは PBX を使用している場合の通話受付管理 (CAC) の計画について説明します。 Skype for Business Server Enterprise Voice に適用されます。

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

2. 手順 1 で作成したサイトの関連するパラメーター値を使用して、SIP トランクのサイト間リンクを作成します。 たとえば、企業内のネットワーク サイトの名前を NetworkSiteID1 パラメーターの値として使用し、ITSP ネットワーク サイトの名前を NetworkSiteID2 パラメーターの値として使用します。 詳細については、展開ドキュメントの「 [Skype For Business Server でネットワークのサイト間ポリシーを作成](../../deploy/deploy-enterprise-voice/create-network-intersite-policies.md)する」と「[新規-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/new-csnetworkintersitepolicy?view=skype-ps)」を参照してください。

3. ITSP からセッション境界コントローラー (SCB) メディア終了ポイントの IP アドレスを取得します。 サブネット マスクが 32 の IP アドレスを、ITSP を表すネットワーク サイトに追加します。 詳細については、「[Associate a Subnet with a Network Site](https://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx)」を参照してください。

## <a name="call-admission-control-with-a-third-party-pstn-gateway-or-pbx"></a>サードパーティの PSTN ゲートウェイまたは PBX での通話受付管理

このトピックでは、仲介サーバーのゲートウェイインターフェイスとサードパーティの公衆交換電話網 (PSTN) ゲートウェイまたはプライベート支店交換 (PBX) との間のリンクに、着信受付制御 (CAC) を展開する方法の例について説明します。

### <a name="case-1-cac-between-the-mediation-server-and-a-pstn-gateway"></a>ケース 1: 仲介サーバーおよび PSTN ゲートウェイ間の CAC

CAC は、仲介サーバーのゲートウェイインターフェイスからサードパーティ PBX または PSTN ゲートウェイへの WAN リンク上に展開できます。

**ケース 1: 仲介サーバーおよび PSTN ゲートウェイ間の CAC**

![ケース 1: 仲介サーバーと PSTN ゲートウェイ間の CAC](../../media/CAC_gateways_1.jpg)

この例では、仲介サーバーと PSTN ゲートウェイの間で CAC が適用されています。 ネットワークサイト1の Skype for Business クライアントユーザーが、ネットワークサイト2の PSTN ゲートウェイ経由で PSTN 通話を発信した場合、メディアは WAN リンクを通じて流れることになります。 そのため、PSTN セッションごとに 2 度の CAC チェックが行われます。

- Skype for Business クライアントアプリケーションと仲介サーバーの間

- 仲介サーバーと PSTN ゲートウェイの間

これは、ネットワーク サイト 1 のクライアントへの PSTN 着信、およびネットワーク サイト 1 のクライアント アプリケーションからの PSTN 発信のどちらでも行われます。

> [!NOTE]
> PSTN ゲートウェイが属する IP サブネットが、確実に構成され、ネットワーク サイト 2 と関連付けられているようにしてください。

> [!NOTE]
> 仲介サーバーの両方のインターフェイスが所属する IP サブネットが構成されていて、ネットワークサイト1に関連付けられていることを確認します。

> [!NOTE]
> 詳細については、「[Associate a Subnet with a Network Site](https://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx)」を参照してください。

### <a name="case-2-cac-between-the-mediation-server-and-a-third-party-pbx-with-media-termination-point"></a>ケース 2: 仲介サーバーとサードパーティ PBX との間の CAC でメディア終了ポイントが使用される

この構成はケース 1 に類似したものです。 どちらの場合も、仲介サーバーは、WAN リンクの反対側でメディアを終了させるデバイスを認識します。また、PSTN ゲートウェイまたは PBX の IP アドレスは、仲介サーバー上で次ホップとして構成されています。

**ケース 2: 仲介サーバーおよび MTP を含むサードパーティ製 PBX 間の CAC**

![ケース 2: 仲介サーバーと PBX (MTP が含まれる) 間の CAC](../../media/CAC_gateways_2.jpg)

この例では、仲介サーバーと PBX/MTP の間で CAC が適用されています。 ネットワークサイト1の Skype for Business クライアントユーザーが、ネットワークサイト2にある PBX または MTP 経由で PSTN 通話を発信した場合、メディアは WAN リンクを通じて流れることになります。 そのため、それぞれの PSTN セッションごとに 2 度の CAC チェックが行われます。

- Skype for Business クライアントアプリケーションと仲介サーバーの間

- 仲介サーバーと PBX/MTP の間

これは、ネットワーク サイト 1 のクライアントへの PSTN 着信、およびネットワーク サイト 1 のクライアントからの PSTN 発信のどちらでも行われます。

> [!NOTE]
> MTP が属する IP サブネットが、確実に構成され、ネットワーク サイト 2 と関連付けられているようにしてください。

> [!NOTE]
> 仲介サーバーの両方のインターフェイスが所属する IP サブネットが構成されていて、ネットワークサイト1に関連付けられていることを確認します。

> [!NOTE]
> 詳細については、「[Associate a Subnet with a Network Site](https://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx)」を参照してください。

### <a name="case-3-cac-between-the-mediation-server-and-a-third-party-pbx-without-a-media-termination-point"></a>ケース 3: メディア終了ポイントのない仲介サーバーとサードパーティ PBX 間の CAC

ケース 3 は、最初の 2 つのケースとは少し異なります。 サードパーティ PBX 上に MTP がない場合、サードパーティ PBX への送信セッション要求については、仲介サーバーが PBX 境界でメディアを終了させる場所を把握していません。 この場合、メディアは、仲介サーバーとサードパーティエンドポイントデバイスの間で直接フローします。

**ケース 3: 仲介サーバーおよび MTP が含まれないサードパーティ製 PBX 間の CAC**

![ケース 3: 仲介サーバーと PBX (MTP が含まれない) 間の CAC](../../media/CAC_gateways_3.jpg)

この例では、ネットワークサイト1の Skype for Business クライアントユーザーが PBX 経由でユーザーに通話を発信した場合、仲介サーバーはプロキシレグ上 (Skype for Business クライアントアプリケーションと仲介サーバーの間) でのみ CAC チェックを実行できます。 仲介サーバーには、セッションが要求されている間、エンドポイントデバイスに関する情報が含まれていないため、発信する前に、(仲介サーバーとサードパーティのエンドポイント間の) WAN リンクで CAC チェックを実行することはできません。 ただし、セッションが確立されると、仲介サーバーによって、トランクで使用される帯域幅のアカウンティングが容易になります。

サードパーティのエンドポイントから発信された通話の場合、そのエンドポイントデバイスに関する情報はセッション要求の時点で利用できます。 CAC のチェックは、仲介サーバーの両方の側で実行できます。

> [!NOTE]
> エンドポイント デバイスが属する IP サブネットが、確実に構成され、ネットワーク サイト 2 と関連付けられているようにしてください。

> [!NOTE]
> 仲介サーバーの両方のインターフェイスが所属する IP サブネットが構成されていて、ネットワークサイト1に関連付けられていることを確認します。

> [!NOTE]
> 詳細については、「[Associate a Subnet with a Network Site](https://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx)」を参照してください。


