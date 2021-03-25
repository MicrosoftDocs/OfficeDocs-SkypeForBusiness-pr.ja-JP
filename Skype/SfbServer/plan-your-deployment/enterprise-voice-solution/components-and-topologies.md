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
description: MPLS ネットワーク、SIP トランク、またはサード パーティの PSTN ゲートウェイまたは PBX がある場合の通話受付管理 (CAC) の計画。 Skype for Business Server エンタープライズ VoIP。
ms.openlocfilehash: 771b98e10c28248bc917bff2b8128b6258c140c5
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51109193"
---
# <a name="components-and-topologies-for-call-admission-control-in-skype-for-business"></a>Skype for Business での通話受付管理のコンポーネントとトポロジ

MPLS ネットワーク、SIP トランク、またはサード パーティの PSTN ゲートウェイまたは PBX がある場合の通話受付管理 (CAC) の計画。 Skype for Business Server エンタープライズ VoIP。

このセクションのトピックでは、通話受付管理 (CAC) をさまざまな種類のネットワーク トポロジで展開する際に特に考慮する点について説明します。

## <a name="call-admission-control-on-an-mpls-network"></a>MPLS ネットワークでの通話受付管理

Multiprotocol Label Switching (MPLS) では、すべてのサイトがフル メッシュで接続されます。つまり、すべてのサイトがインターネット サービス プロバイダーの MPLS バックボーンに直接接続され、各サイトが WAN リンクから MPLS にかけて使用されるプロビジョニングされた帯域幅であるということです。IP ルーティングを制御するネットワーク ハブやセントラル サイトはありません。次の図に、MPLS トポロジに基づく簡単なネットワークを示します。

**MPLS ネットワークの例**

![MPLS を使用した CAC](../../media/CAC_MPLS_1.jpg)

MPLS ネットワークで通話受付管理 (CAC) を展開するには、MPLS クラウドを表すネットワーク地域を作成し、MPLS の各サテライト サイトを表すネットワーク サイトを作成します。 次の図で、前の図の MPLS ネットワークの例を表すための、ネットワーク地域およびネットワーク サイトの構成方法について説明します。 全体的な帯域幅および帯域幅セッションの制限は、各ネットワーク サイトから MPLS クラウドを表すネットワーク地域までの WAN リンクの容量に基づきます。

**MPLS ネットワークのネットワーク地域およびネットワーク サイト**

![MPLS ダイアグラムを使用した通話受付管理 (CAC)](../../media/CAC_MPLS_2.jpg)

## <a name="call-admission-control-on-a-sip-trunk"></a>SIP トランクの通話受付管理

SIP トランクに通話受付管理 (CAC) を展開するには、インターネット テレフォニー サービス プロバイダー (ITSP) を表すためのネットワーク サイトを作成します。SIP トランクに帯域幅ポリシーの値を適用するには、企業内のネットワーク サイトと ITSP を表すために作成するネットワーク サイトのサイト間ポリシーを作成します。

次の図は、SIP トランクの CAC 展開の例を示しています。

**SIP トランクの CAC 構成**

![通話受付管理 SIP トランキング図](../../media/CAC_SIP_trunk_1.jpg)

SIP トランクに CAC を構成するには、CAC の展開時に次の作業を行う必要があります。

1. ITSP を表すためのネットワーク サイトを作成します。 ネットワーク サイトを適切なネットワーク地域に関連付けて、このネットワーク サイトの音声とビデオにゼロの帯域幅を割り当てます。 詳細については、「展開」のドキュメントの「[Configure Network Sites for CAC](/previous-versions/office/lync-server-2013/lync-server-2013-configure-network-sites-for-cac)」を参照してください。

    > [!NOTE]
    > ITSP では、このネットワーク サイト構成は機能しません。 帯域幅ポリシーの値は、手順 2 で実際に適用されます。

2. 手順 1 で作成したサイトの関連するパラメーター値を使用して、SIP トランクのサイト間リンクを作成します。 たとえば、企業内のネットワーク サイトの名前を NetworkSiteID1 パラメーターの値として使用し、ITSP ネットワーク サイトの名前を NetworkSiteID2 パラメーターの値として使用します。 詳細については、「展開」のドキュメントの [「Skype for Business Server](../../deploy/deploy-enterprise-voice/create-network-intersite-policies.md) でネットワーク間サイト ポリシーを作成する」および [「New-CsNetworkInterSitePolicy」を参照してください](/powershell/module/skype/new-csnetworkintersitepolicy?view=skype-ps)。

3. ITSP からセッション ボーダー コントローラー (SCB) メディアターミネーション ポイントの IP アドレスを取得します。 サブネット マスクが 32 の IP アドレスを、ITSP を表すネットワーク サイトに追加します。 詳細については、「[Associate a Subnet with a Network Site](/previous-versions/office/lync-server-2013/lync-server-2013-associate-a-subnet-with-a-network-site)」を参照してください。

## <a name="call-admission-control-with-a-third-party-pstn-gateway-or-pbx"></a>サード パーティの PSTN ゲートウェイまたは PBX を使用した通話受付管理

このトピックでは、仲介サーバーのゲートウェイ インターフェイスとサードパーティの公衆交換電話網 (PSTN) ゲートウェイまたはプライベート ブランチ 交換 (PBX) の間のリンクに通話受付制御 (CAC) を展開する方法の例について説明します。

### <a name="case-1-cac-between-the-mediation-server-and-a-pstn-gateway"></a>ケース 1: 仲介サーバーと PSTN ゲートウェイの間の CAC

CAC は、仲介サーバーのゲートウェイ インターフェイスからサードパーティ PBX または PSTN ゲートウェイへの WAN リンクに展開できます。

**ケース 1: 仲介サーバーと PSTN ゲートウェイの間の CAC**

![ケース 1: 仲介サーバー PSTN ゲートウェイ間の CAC](../../media/CAC_gateways_1.jpg)

この例では、仲介サーバーと PSTN ゲートウェイの間に CAC が適用されます。 ネットワーク サイト 1 の Skype for Business クライアント ユーザーがネットワーク サイト 2 の PSTN ゲートウェイを介して PSTN 通話を行う場合、メディアは WAN リンクを流れます。 したがって、PSTN セッションごとに 2 つの CAC チェックが実行されます。

- Skype for Business クライアント アプリケーションと仲介サーバーの間

- 仲介サーバーと PSTN ゲートウェイの間

これは、ネットワーク サイト 1 のクライアントへの着信 PSTN 呼び出しと、ネットワーク サイト 1 のクライアント アプリケーションから発信される発信 PSTN 通話の両方で機能します。

> [!NOTE]
> PSTN ゲートウェイが属する IP サブネットが構成され、ネットワーク サイト 2 に関連付けられているか確認します。

> [!NOTE]
> 仲介サーバーの両方のインターフェイスが属する IP サブネットが構成され、ネットワーク サイト 1 に関連付けられているか確認します。

> [!NOTE]
> 詳細については、「[Associate a Subnet with a Network Site](/previous-versions/office/lync-server-2013/lync-server-2013-associate-a-subnet-with-a-network-site)」を参照してください。

### <a name="case-2-cac-between-the-mediation-server-and-a-third-party-pbx-with-media-termination-point"></a>ケース 2: 仲介サーバーとメディアターミネーション ポイントを持つサード パーティ製 PBX の間の CAC

この構成は、ケース 1 に似ています。 どちらの場合も、仲介サーバーは、WAN リンクの反対側の端でメディアを終了するデバイスを知り、次ホップとして仲介サーバーでメディアターミネーション ポイント (MTP) を使用する PSTN ゲートウェイまたは PBX の IP アドレスが構成されます。

**ケース 2: 仲介サーバーと MTP を使用するサード パーティ製 PBX の間の CAC**

![ケース 2: 仲介サーバー PBX と MTP の間の CAC](../../media/CAC_gateways_2.jpg)

この例では、仲介サーバーと PBX/MTP の間に CAC が適用されます。 ネットワーク サイト 1 の Skype for Business クライアント ユーザーが、ネットワーク サイト 2 にある PBX/MTP を介して PSTN 通話を行う場合、メディアは WAN リンクを流れます。 したがって、PSTN セッションごとに、次の 2 つの CAC チェックが実行されます。

- Skype for Business クライアント アプリケーションと仲介サーバーの間

- 仲介サーバーと PBX/MTP の間

これは、ネットワーク サイト 1 のクライアントへの着信 PSTN 呼び出しと、ネットワーク サイト 1 のクライアントから発信される発信 PSTN 通話の両方で機能します。

> [!NOTE]
> MTP が属する IP サブネットが構成され、ネットワーク サイト 2 に関連付けられているか確認します。

> [!NOTE]
> 仲介サーバーの両方のインターフェイスが属する IP サブネットが構成され、ネットワーク サイト 1 に関連付けられているか確認します。

> [!NOTE]
> 詳細については、「[Associate a Subnet with a Network Site](/previous-versions/office/lync-server-2013/lync-server-2013-associate-a-subnet-with-a-network-site)」を参照してください。

### <a name="case-3-cac-between-the-mediation-server-and-a-third-party-pbx-without-a-media-termination-point"></a>ケース 3: メディアターミネーション ポイントのない仲介サーバーとサードパーティ PBX の間の CAC

ケース 3 は、最初の 2 つのケースとは若干異なります。 サード パーティ PBX に MTP がない場合、サード パーティ PBX への送信セッション要求に対して仲介サーバーは、メディアが PBX 境界でどこで終了するのか分からない。 この場合、仲介サーバーとサードパーティのエンドポイント デバイスの間でメディアが直接流れます。

**ケース 3: 仲介サーバーと MTP のないサード パーティ製 PBX の間の CAC**

![ケース 3: 仲介サーバー PBX 間の CAC MTP なし](../../media/CAC_gateways_3.jpg)

この例では、ネットワーク サイト 1 の Skype for Business クライアント ユーザーが PBX を介してユーザーに通話を行う場合、仲介サーバーはプロキシ レグ (Skype for Business クライアント アプリケーションと仲介サーバーの間) でのみ CAC チェックを実行できます。 セッションが要求されている間、仲介サーバーはエンドポイント デバイスに関する情報を持たないので、呼び出しの確立前に (仲介サーバーとサード パーティエンドポイントの間の) WAN リンクで CAC チェックを実行できません。 ただし、セッションが確立されると、仲介サーバーはトランクで使用される帯域幅の会計を容易にします。

サード パーティエンドポイントから発信される呼び出しの場合、そのエンドポイント デバイスに関する情報はセッション要求時に利用できます。CAC チェックは仲介サーバーの両側で実行できます。

> [!NOTE]
> エンドポイント デバイスが属する IP サブネットが構成され、ネットワーク サイト 2 に関連付けられているか確認します。

> [!NOTE]
> 仲介サーバーの両方のインターフェイスが属する IP サブネットが構成され、ネットワーク サイト 1 に関連付けられているか確認します。

> [!NOTE]
> 詳細については、「[Associate a Subnet with a Network Site](/previous-versions/office/lync-server-2013/lync-server-2013-associate-a-subnet-with-a-network-site)」を参照してください。