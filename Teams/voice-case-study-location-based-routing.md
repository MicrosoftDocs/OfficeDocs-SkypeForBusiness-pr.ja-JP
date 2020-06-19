---
title: チームボイスの Contoso のケーススタディ
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
description: 多国籍企業向けの Teams の音声のケーススタディ
appliesto:
- Microsoft Teams
ms.openlocfilehash: f1ba92794b2ba17cc23e1bca55800c9307707636
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/18/2020
ms.locfileid: "44786076"
---
# <a name="contoso-case-study-location-based-routing"></a>Contoso のケーススタディ: 場所に基づくルーティング

位置情報に基づくルーティング (LBR) は、通話を発信または受信するときに、ポリシーとユーザーの物理的な場所に基づいて、有料でのバイパスを制限する機能です。  

## <a name="overview"></a>概要

Contoso には、公衆交換電話網 (PSTN) プロバイダーをバイパスして長距離通話料金を削減することができない2つの支社が含まれています。 メインの office には、本社と2番目の office で使用されるインターネット接続があります。 各 office には、PSTN キャリアに接続された独自のセッションボーダーコントローラー (SBC) があります。  
 
この国では、Contoso は Skype for Business 展開用に LBR が構成されています。 Teams 用に LBR を構成する方法を決定するために、Contoso は[ダイレクトルーティング用の位置情報に基づくルーティングを](location-based-routing-plan.md)参照します。 Contoso は、Skype for Business が通話の発信元として、着信可能なときには、PSTN 通話を Teams ユーザーに転送でき、別の Teams ユーザーを PSTN 通話に移行できるようになったときに、同じシナリオに従っていることを確認しました。  

Skype for Business については、「セッションボーダーコントローラー (SBC) SIP トランクで PSTN キャリアに接続する」を使用して LBR を構成しました。 この SBC では、Contoso は認定された[SBCs のリスト](direct-routing-border-controllers.md)を確認しました。 SBC は、ダイレクトルーティングが認定されているが、メディアのバイパスは認められていないことがわかりました。 LBR をサポートするには、直接ルーティングが SBC オンサイトに設定されている必要があります。そのためには、ローカルのインターネット出口が必要であり、SBC はメディアバイパス用に構成されている必要があります。 この情報に基づいて、Contoso は以下を決定しました。

- 既存の SBC がメディアバイパスに対して認定されるまで、Teams の有効化を延期します。   

- Contoso は、Office 365 への直接ルートとして、メインサイト SBC の使用を決定しました。  メインサイトの SBC は、リモートサイト用のプロキシとして使用されます。  

- Contoso は、インドに基づくサードパーティコンサルタントを使用して、国内のテレフォニー会社での LBR 構成の認定を支援しました。  

- Office の外部で PSTN 通話を行うことができるようにするため、会社が発行した携帯電話は従業員に提供されました。 

次の図は、場所に基づくルーティングが必要なテレフォニーの規則を使用している国の前と後の展開を示しています。

**元の展開**

![以前の状態を示す図](media/voice-case-study-5.png)

**ダイレクトルーティングを使用した展開**

![以前の状態を示す図](media/voice-case-study-6.png)


## <a name="configuration"></a>構成 

Teams のネットワークコンポーネントを構成するには、「[クラウド音声機能のネットワークトポロジを管理](manage-your-network-topology.md)する」の手順に従ってください。 Contoso は、次の手順を完了して、位置情報に基づくルーティングを構成しました。 

- ネットワーク領域の定義-1 つのネットワークリージョンが定義されました。 

- ネットワークサイトを定義します。2つのネットワークサイトが定義されています。 地域内のオフィスの場所ごとに1つのサイト。

- ネットワークサブネットを定義する-オフィス内の各フロアには、有線およびワイヤレスネットワーク用の独自のサブネットがあります。 この構成により、Contoso に20個のサブネットが生まれました。 

- 信頼できる IP アドレスを定義する-SBC の外部の IP アドレスが、信頼できる IP アドレスに追加されました。  

