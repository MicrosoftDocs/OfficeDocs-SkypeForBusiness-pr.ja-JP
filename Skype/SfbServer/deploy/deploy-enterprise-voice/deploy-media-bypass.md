---
title: Skype for Business Server でメディアバイパスを展開する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: Skype for Business Server Enterprise Voice でメディアバイパスを展開します。 前提条件と展開プロセスのチェックリストも掲載しています。
ms.openlocfilehash: 744fe56b554bd6b97171798e5dcc7baab69b6dbf
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41767540"
---
# <a name="deploy-media-bypass-in-skype-for-business-server"></a>Skype for Business Server でメディアバイパスを展開する
 
Skype for Business Server Enterprise Voice でメディアバイパスを展開します。 前提条件と展開プロセスのチェックリストも掲載しています。
  
このトピックでは、少なくとも1つ以上の仲介サーバーと1つ以上のゲートウェイピアを使って、PSTN 接続を提供していることを前提としています。 これらのタスクの詳細については、「 [skype For Business server のトポロジビルダーに仲介サーバーを展開](deploy-a-mediation-server.md)する」と「 [Skype for Business Server のトポロジビルダーでゲートウェイを定義](define-a-gateway.md)する」を参照してください。
  
 接続するピアが SIP トランキング プロバイダーの SBC の場合は、プロバイダーが認定プロバイダーであることとプロバイダーがメディア バイパスをサポートしていることを確認してください。たとえば、多くの SIP トランキング プロバイダーが、その SBC に仲介サーバーからのトラフィックを受信することだけを許可します。その場合は、当該のトランクに対してバイパスを有効にしないでください。また、組織がその内部ネットワーク IP アドレスを SIP トランキング プロバイダーに公開していなければ、メディア バイパスを有効にすることはできません。
  
> [!NOTE]
> メディア バイパスは、すべての PSTN ゲートウェイ、IP-PBX、および SBC と相互運用できるとは限りません。 マイクロソフトでは、認定パートナーの PSTN ゲートウェイと SBC でテストを行い、Cisco IP-PBX でも一定のテストを行いました。 メディアのバイパスは、統合された通信の[オープンな相互運用性プログラム-Lync Server](https://go.microsoft.com/fwlink/p/?linkId=214406)でのみサポートされている製品とバージョンでのみサポートされます。 
  
もう 1 つの高度なエンタープライズ VoIP 機能に当たる、オプションの通話受付管理 (CAC) の構成が済んでいる場合は、通話受付管理が実行する帯域幅の予約がメディア バイパスを採用する通話に適用されないようにしてください。メディア バイパスが採用されているかどうかの検証は最初に行われます。採用されている場合は、その通話に対しては通話受付管理は使用されません。通話受付管理に対するチェックは、メディア バイパスのチェックが不合格の場合にのみ行われます。このため、PSTN にルーティングされる特定の通話に対して 2 つの機能がともに適用されることはありません。メディア バイパスは、通話のメディア エンドポイント間に帯域幅の制約がないことを前提にしているため、2 つの機能が両立しないという論理的結論にたどり着きます。メディア バイパスは、帯域幅制限のあるリンク上では実行できません。このことから、PSTN の通話には次のいずれかが適用されます。a) 仲介サーバーをメディア バイパスし、通話受付管理は通話に対して帯域幅を予約しない。または b) 通話受付管理が通話に帯域幅の予約を適用し、メディアはその通話に関わる仲介サーバーで処理される。
  
ピアに関連付けられている個々のトランク接続でメディア パイパスを有効にするほか、メディア バイパスをグローバルに有効にする必要もあります。グローバルなメディア バイパス設定では、PSTN への呼び出しで常にメディア バイパスを試行するか、ネットワーク サイトおよびネットワーク地域へのサブネットのマッピングを使用するメディア パイパスを採用するかを指定できます。後者の方法は、もう 1 つの高度な音声機能である通話受付管理での方法と似ています。メディア バイパスと通話受付管理が両方有効な場合は、ネットワーク地域、ネットワーク サイト、および通話受付管理用に指定されるサブネット情報が、メディア バイパスを使用するかどうかを決定する際に自動的に使用されます。つまり、通話受付管理が有効な場合は、PSTN の呼び出しで常にメディア バイパスを試行するよう指定することはできません。
  
> [!NOTE]
> こうした手順を使用してメディア バイパスを構成する場合は、クライアントと仲介サーバー ピア (PSTN ゲートウェイ、IP-PBX、SIP トランキング プロバイダーでの SBC など) の間の接続状態が良好であることが前提です。 リンクに帯域幅制限があると、メディア バイパスを通話に適用できません。 メディア バイパスは、すべての PSTN ゲートウェイ、IP-PBX、および SBC と相互運用できるわけではありません。 マイクロソフトでは、認定パートナーの PSTN ゲートウェイと SBC でテストを行い、Cisco IP-PBX でも一定のテストを行いました。 メディアのバイパスは、統合された通信の[オープンな相互運用性プログラム-Lync Server](https://go.microsoft.com/fwlink/p/?linkId=214406)でのみサポートされている製品とバージョンでのみサポートされます。 
  
## <a name="deployment-process-for-media-bypass"></a>メディア バイパスの展開プロセス

次の表に、メディア バイパスの展開プロセスの概要を示します。 
  
|**フェーズ**|**手順**|**Roles**|**「展開」のドキュメント**|
|:-----|:-----|:-----|:-----|
|メディア バイパスのトランクの構成  <br/> |メディア バイパスの 1 つ以上のトランクを構成します (まだ行っていない場合)。  <br/> | RTCUniversalServerAdmins group のメンバーであるか、CsVoiceAdministrator、CsServerAdministrator、または CsAdministrator の役割のメンバーである <br/> |[Skype for Business Server でメディアバイパスを使用してトランクを構成する](configure-trunk-with-media-bypass.md) <br/> |
|メディア バイパスをグローバルに構成する  <br/> |ネットワーク サイトおよびネットワーク地域に基づいて、PSTN へのすべての通話または特定の通話のメディア バイパスを構成します。  <br/> | RTCUniversalServerAdmins group のメンバーであるか、CsVoiceAdministrator、CsServerAdministrator、または CsAdministrator の役割のメンバーである <br/> |[Skype for Business Server でメディアバイパスを構成して、常に仲介サーバーをバイパスする](bypass-the-mediation-server.md) <br/> [サイトと地域の情報を使用するために、Skype for Business Server でメディアを無視するグローバル設定を構成する](use-site-and-region-information.md) <br/> |
|必要に応じたネットワーク サイトとサブネットの関連付け  <br/> |メディア バイパスを構成してサイトおよび地域の情報を使用するには、展開のサブネットをネットワーク サイトおよび地域に関連付ける必要があります (別の音声機能でまだ完了していない場合)。  <br/> | RTCUniversalServerAdmins group のメンバーであるか、CsVoiceAdministrator、CsServerAdministrator、または CsAdministrator の役割のメンバーである <br/> |[Associate a subnet with a network site](deploy-network.md#BKMK_AssociateSubnets) <br/> |
   

