---
title: 'Teams音声 Contoso のケース スタディ: 場所ベースのルーティング'
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
description: 'Teams多国籍企業の音声ケース スタディ: 場所ベースのルーティング'
appliesto:
- Microsoft Teams
ms.openlocfilehash: 974053f3e438ecaee3f9eb876eb99e2cf6e40d151be802acb31183620eabc583
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54319640"
---
# <a name="contoso-case-study-location-based-routing"></a>Contoso のケース スタディ: Location-Based ルーティング

Location-Based ルーティング (LBR) は、通話の発信または受信時のポリシーとユーザーの物理的な場所に基づいて有料バイパスを制限する機能です。  

## <a name="overview"></a>概要

Contoso は国に 2 つのオフィスを持ち、公衆交換電話網 (PSTN) プロバイダーをバイパスして長距離通話コストを削減することは違法です。 メイン オフィスには、メイン オフィスと 2 番目のオフィスで使用されるインターネット接続があります。 各オフィスには、PSTN キャリアに接続された独自のセッション ボーダー コントローラー (SBC) があります。  
 
この国では、Contoso はSkype for Businessデプロイ用に LBR を構成していました。 Teamsの LBR を構成する方法を確認するには、「[ダイレクト ルーティングの計画Location-Basedルーティング」を](location-based-routing-plan.md)参照してください。 Contoso は、TeamsとSkype for Businessが、通話を発信できるタイミング、着信できるタイミング、PSTN 通話をTeams ユーザーに転送できるタイミング、および PSTN 通話に別のTeams ユーザーを転送できる場合に、同じシナリオに従うことを決定しました。  

Skype for Businessの場合、LBR は PSTN キャリアに接続するセッション ボーダー コントローラー (SBC) SIP トランクで構成されました。 この SBC について、Contoso は認定された [SBC の一覧を](direct-routing-border-controllers.md) 確認し、展開された SBC がダイレクト ルーティングの認定を受けていますが、Media Bypass の認定を受けないことを確認しました。 LBR をサポートするには、直接ルーティングを SBC オンサイトに構成する必要があります。ローカル インターネット エグレスが必要であり、メディア バイパス用に SBC を構成する必要があります。 この情報に基づいて、Contoso は次のことを決定しました。

- 既存の SBC が Media Bypass の認定を受けるまで LBR Teams有効にすることを延期する。   

- Contoso は、Office 365へのダイレクト ルートにメイン サイト SBC を使用することにしました。  メイン サイト SBC は、リモート サイトのプロキシ SBC になります。  

- Contoso は、インドに拠点を置くサードパーティのコンサルタントを使用して、国のテレフォニー会社との LBR 構成の認定を支援しました。  

- オフィスの外部から PSTN 通話を発信するユーザーをサポートするために、会社から発行された携帯電話が従業員に提供されました。 

次の図は、Location-Basedルーティングが必要なテレフォニー規制がある国の展開の前後を示しています。

**元のデプロイ**

![前の状態を示す図。](media/voice-case-study-5.png)

**直接ルーティングを使用したデプロイ**

![前の状態を示す図 2。](media/voice-case-study-6.png)


## <a name="configuration"></a>構成： 

Teamsでネットワーク コンポーネントを構成するには、「[クラウド音声機能のネットワーク トポロジを管理する」](manage-your-network-topology.md)の手順に従いました。 Contoso は、Location-Basedルーティングを構成するために次の手順を完了しました。 

- ネットワーク リージョンを定義する - 1 つのネットワーク リージョンが定義されました。 

- ネットワーク サイトの定義 - 2 つのネットワーク サイトが定義されました。 リージョン内のオフィスの場所ごとに 1 つのサイト。

- ネットワーク サブネットを定義する - オフィスの場所内の各フロアには、有線ネットワークとワイヤレス ネットワーク用の独自のサブネットがあります。 この構成により、Contoso には 20 個のサブネットが作成されました。 

- 信頼できる IP アドレスを定義する - SBC の外部向け IP アドレスが信頼された IP アドレスに追加されました。  

