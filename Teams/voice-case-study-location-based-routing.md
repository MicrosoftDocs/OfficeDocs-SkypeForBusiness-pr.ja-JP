---
title: Teams Contoso のケース スタディ
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 06/17/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: jowrig
search.appverid: MET150
f1.keywords:
- NOCSH
description: Teams企業向け音声ケース スタディ
appliesto:
- Microsoft Teams
ms.openlocfilehash: f1ba92794b2ba17cc23e1bca55800c9307707636
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/18/2020
ms.locfileid: "44786076"
---
# <a name="contoso-case-study-location-based-routing"></a>Contoso のケース スタディ: Location-Based ルーティング

Location-Based ルーティング (LBR) は、通話の設置時または受信時のポリシーとユーザーの物理的な場所に基づいて、有料バイパスを制限する機能です。  

## <a name="overview"></a>概要

Contoso は、公衆交換電話網 (PSTN) プロバイダーをバイパスして、遠距離通話コストを削減する違法な国に 2 つのオフィスを持っています。 メイン オフィスには、メイン オフィスと 2 つ目のオフィスで使用されるインターネット接続があります。 各オフィスには、PSTN 通信事業者に接続された独自のセッション ボーダー コントローラー (SBC) があります。  
 
この国では、Contoso は LBR を新しいデプロイ用にSkype for Businessしました。 ルーティング用に LBR を構成する方法を確認Teams Contoso は、「直接ルーティングの[ルーティングの計画Location-Based」を参照してください](location-based-routing-plan.md)。 contoso は、Teams と Skype for Business は、通話を発信できる状況、通話を受信できる時間、PSTN 通話を Teams ユーザーに転送できる場合、および別の Teams ユーザーを PSTN 通話に転送できる場合に、同じシナリオに従う必要があります。  

たとえばSkype for Business、PSTN 通信事業者に接続するセッション ボーダー コントローラー (SBC) SIP トランクを使用して LBR が構成されています。 この SBC について、Contoso は認定された [SBC](direct-routing-border-controllers.md) の一覧を確認し、デプロイされた SBC がダイレクト ルーティングの認定を受けたが、メディア バイパスの認定を受け取っていないと判断しました。 LBR をサポートするには、直接ルーティングをオンサイトの SBC に構成し、ローカルインターネットエグレスが必要であり、SBC をメディア バイパス用に構成する必要があります。 この情報に基づいて、Contoso は次の決定を行いました。

- 既存の SBC がメディア バイパスの認定Teams LBR の有効化を遅らせた場合。   

- Contoso は、メイン サイト SBC を使用して直接ルートを使用Office 365。  メイン サイト SBC は、リモート サイトのプロキシ SBC です。  

- Contoso は、インドに拠点を置くサード パーティのコンサルタントを使用して、国のテレフォニー会社との LBR 構成の認定を支援しました。  

- PSTN 通話を発信するためにオフィスの外部から作業しているユーザーをサポートするために、会社が発行した携帯電話が従業員に提供されました。 

次の図は、ルーティングを必要とするテレフォニー規制が適用された国の展開の前と後Location-Based示しています。

**元のデプロイ**

![状態の前を示す図](media/voice-case-study-5.png)

**直接ルーティングを使用したデプロイ**

![状態の前を示す図](media/voice-case-study-6.png)


## <a name="configuration"></a>構成: 

Teams でネットワーク コンポーネントを構成するために、Contoso は「クラウド音声機能のネットワーク トポロジを管理する」の[手順に従いました](manage-your-network-topology.md)。 Contoso は、次の手順を完了して、ルーティングをLocation-Basedしました。 

- [ネットワーク リージョンの定義] - 1 つのネットワーク リージョンが定義されています。 

- ネットワーク サイトの定義 - 2 つのネットワーク サイトが定義されています。 地域内のオフィスの場所ごとに 1 つのサイト。

- ネットワーク サブネットの定義 - オフィスの場所内の各フロアには、有線ネットワークとワイヤレス ネットワーク用の独自のサブネットがあります。 この構成により、Contoso のサブネットは 20 になります。 

- 信頼できる IP アドレスの定義 - SBC の外部に接続する IP アドレスが信頼済み IP アドレスに追加されました。  

