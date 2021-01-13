---
title: Skype for Business Server でのメディア バイパスの展開
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 1bd35f90-8587-48a1-b0c2-095a4053fc77
description: Skype for Business Server サービスにメディア バイパスをエンタープライズ VoIP。 前提条件と展開プロセスのチェックリストが含まれます。
ms.openlocfilehash: c6820438d969ce3c802060eba9bcababc0b1315d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812447"
---
# <a name="deploy-media-bypass-in-skype-for-business-server"></a>Skype for Business Server でのメディア バイパスの展開
 
Skype for Business Server サービスにメディア バイパスをエンタープライズ VoIP。 前提条件と展開プロセスのチェックリストが含まれます。
  
このトピックでは、PSTN 接続を提供するために、少なくとも 1 つ以上の仲介サーバーと少なくとも 1 つのゲートウェイ ピアが既に公開および構成されていることを前提とします。 これらのタスクの詳細については [、「Deploy a Mediation Server in Topology Builder in Skype for Business Server」](deploy-a-mediation-server.md) および [「Define a gateway in Topology Builder in Skype for Business Server」](define-a-gateway.md)を参照してください。
  
 接続するピアが SIP トランキング プロバイダーの SBC である場合は、プロバイダーが認定プロバイダーであり、プロバイダーがメディア バイパスをサポートしている必要があります。 たとえば、多くの SIP トランキング プロバイダーは、SBC が仲介サーバーからのトラフィックの受信のみを許可します。 その場合は、問題のトランクに対してバイパスを有効にすることはできません。 また、組織が SIP トランキング プロバイダーに内部ネットワーク IP アドレスを公開しない限り、メディア バイパスを有効にすることはできません。
  
> [!NOTE]
> メディア バイパスは、すべての PSTN ゲートウェイ、IP-PBX、および SBC と相互運用できるとは限りません。 Microsoft は、認定パートナーと一連の PSTN ゲートウェイと SBC をテストし、Cisco IP-PBX でいくつかのテストを行っています。 メディア バイパスは、Unified Communications Open Interoperability Program - Lync Server に記載されている製品とバージョン [でのみサポートされます](https://go.microsoft.com/fwlink/p/?linkId=214406)。 
  
もう 1 つの高度なエンタープライズ VoIP 機能に当たる、オプションの通話受付管理 (CAC) の構成が済んでいる場合は、通話受付管理が実行する帯域幅の予約がメディア バイパスを採用する通話に適用されないようにしてください。 メディア バイパスが採用されているかどうかの検証は最初に行われます。採用されている場合は、その通話に対しては通話受付管理は使用されません。通話受付管理に対するチェックは、メディア バイパスのチェックが不合格の場合にのみ行われます。 このため、PSTN にルーティングされる特定の通話に対して 2 つの機能がともに適用されることはありません。 メディア バイパスは、通話のメディア エンドポイント間に帯域幅の制約がないことを前提にしているため、2 つの機能が両立しないという論理的結論にたどり着きます。メディア バイパスは、帯域幅制限のあるリンク上では実行できません。 このことから、PSTN の通話には次のいずれかが適用されます。 a) 仲介サーバーをメディア バイパスし、通話受付管理は通話に対して帯域幅を予約しない。または b) 通話受付管理が通話に帯域幅の予約を適用し、メディアはその通話に関わる仲介サーバーで処理される。
  
ピアに関連付けられた個々のトランク接続でメディア バイパスを有効にできるだけでなく、メディア バイパスをグローバルに有効にする必要があります。 グローバル メディア バイパス設定では、PSTN への通話に対してメディア バイパスが常に試行される、またはネットワーク サイトおよびネットワーク地域へのサブネットのマッピングを使用してメディア バイパスが使用される (通話受付管理、もう 1 つの高度な音声機能) を指定できます。 メディア バイパスと通話受付管理の両方が有効になっている場合、通話受付管理用に指定されたネットワーク地域、ネットワーク サイト、およびサブネット情報は、メディア バイパスを使用するかどうかを決定するときに自動的に使用されます。 つまり、通話受付管理が有効な場合、メディア バイパスが常に PSTN への通話に対して試行されるという指定はできないことを意味します。
  
> [!NOTE]
> こうした手順を使用してメディア バイパスを構成する場合は、クライアントと仲介サーバー ピア (PSTN ゲートウェイ、IP-PBX、または SIP トランキング プロバイダーでの SBC など) の間の接続状態が良好であることを前提とします。 リンクに帯域幅制限があると、メディア バイパスを通話に適用できません。 メディア バイパスは、あらゆる PSTN ゲートウェイ、IP-PBX、および SBC と相互運用できるわけではありません。 Microsoft は、認定パートナーと一連の PSTN ゲートウェイと SBC をテストし、Cisco IP-PBX でいくつかのテストを行っています。 メディア バイパスは、Unified Communications Open Interoperability Program - Lync Server に記載されている製品とバージョン [でのみサポートされます](https://go.microsoft.com/fwlink/p/?linkId=214406)。 
  
## <a name="deployment-process-for-media-bypass"></a>メディア バイパスの展開プロセス

次の表に、メディア バイパス展開プロセスの概要を示します。 
  
|**フェーズ**|**手順**|**Roles**|**展開のドキュメント**|
|:-----|:-----|:-----|:-----|
|メディア バイパスのトランクを構成する  <br/> |まだ構成していない場合は、メディア バイパス用に 1 つ以上のトランクを構成します。  <br/> | RTCUniversalServerAdmins グループのメンバー、または CsVoiceAdministrator、CsServerAdministrator、または CsAdministrator の役割のメンバー <br/> |[Skype for Business Server でメディア バイパスを使用してトランクを構成する](configure-trunk-with-media-bypass.md) <br/> |
|メディア バイパスをグローバルに構成する  <br/> |PSTN へのすべての通話、またはネットワーク サイトとネットワーク地域に基づく特定の通話のメディア バイパスを構成します。  <br/> | RTCUniversalServerAdmins グループのメンバー、または CsVoiceAdministrator、CsServerAdministrator、または CsAdministrator の役割のメンバー <br/> |[Skype for Business Server でメディア バイパスを構成して、常に仲介サーバーをバイパスする](bypass-the-mediation-server.md) <br/> [サイトおよび地域情報を使用するために Skype for Business Server のメディア バイパス グローバル設定を構成する](use-site-and-region-information.md) <br/> |
|サブネットをネットワーク サイトに関連付ける (必要な場合)  <br/> |メディア バイパスを構成してサイトおよび地域情報を使用する場合は、展開のサブネットをネットワーク サイトおよび地域に関連付ける必要があります (別の音声機能に対してまだ関連付けしていない場合)。  <br/> | RTCUniversalServerAdmins グループのメンバー、または CsVoiceAdministrator、CsServerAdministrator、または CsAdministrator の役割のメンバー <br/> |[サブネットをネットワーク サイトに関連付ける](deploy-network.md#BKMK_AssociateSubnets) <br/> |
   

