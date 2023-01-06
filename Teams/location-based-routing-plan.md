---
title: ダイレクト ルーティングの場所に基づくルーティングを計画する
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: roykuntz
search.appverid: MET150
description: Teams 電話ダイレクト ルーティングのLocation-Basedルーティングを計画する方法について説明します。
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: 354a3ae6ec4fb482b6ba0d5136597438c37acbe2
ms.sourcegitcommit: eb0e754d7e2877f686021d3ab75b6d8d44db3a95
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/06/2023
ms.locfileid: "69727789"
---
# <a name="plan-location-based-routing-for-direct-routing"></a>ダイレクト ルーティングの場所に基づくルーティングを計画する

一部の国や地域では、公衆交換電話網 (PSTN) プロバイダーをバイパスして長距離通話コストを削減することは違法です。 

この記事では、Location-Based ルーティングを使用して、地理的な場所に基づいて Microsoft Teams ユーザーの有料バイパスを制限するために知っておくべきことを説明します。 この記事は、ダイレクト ルーティングにのみ適用されます。 Location-Based ルーティングは、通話プランまたはオペレーター接続には適用されません。

Location-Basedルーティングを有効にする準備ができたら、次を参照してください。

- [場所に基づくルーティングのネットワーク設定を構成する](location-based-routing-configure-network-settings.md)
- [ダイレクト ルーティングの場所に基づくルーティングを有効にする](location-based-routing-enable.md)

> [!NOTE]
> Location-Basedルーティングを使用して、ユーザーの場所に基づいて PSTN 呼び出しを動的にルーティングしないでください。 これを行うと、意図しない結果が発生する可能性があります。

## <a name="overview"></a>概要

Location-Basedルーティングを使用すると、インバウンドまたはアウトバウンド PSTN 通話時のポリシーとユーザーの地理的な場所に基づいて、ユーザーの有料バイパスを制限できます。 

Location-Based ルーティングでは、ネットワークリージョン、サイト、サブネットに対して定義したネットワーク トポロジが使用されます。 場所に対して有料バイパスが制限されている場合は、その場所の各 IP サブネットと各 PSTN ゲートウェイをネットワーク サイトに関連付けます。 

PSTN 通話の時点で、ユーザーの場所は、ユーザーの Teams エンドポイントが接続されている IP サブネットによって決まります。 ユーザーが複数の Teams クライアントを異なるサイトに配置している場合、Location-Basedルーティングでは、Teams エンドポイントの場所に応じて、各クライアントのルーティングが個別に適用されます。

ネットワーク設定の詳細については、「 [Teams のクラウド音声機能のネットワーク設定](cloud-voice-network-settings.md)」を参照してください。

この記事では、ネットワーク サイトを次のいずれかの状態にできることを前提としています。

- **有効** - テナント ネットワーク サブネットとサイトを使用して構成され、Location-Based ルーティングに対して有効になっているサイト。

- **[無効]** - テナント ネットワーク サブネットとサイトを使用して構成されているが、Location-Based ルーティングでは有効になっていないサイト。

- **不明** - テナント ネットワーク サブネットとサイトを使用して構成されていないサイト。 通常、このようなサイトは企業ネットワークの内部にありますが、設計上構成されていないか、企業ネットワークの外部にあります。 いずれの場合も、これらのサイトはLocation-Basedルーティングに対して有効になっていません。 

### <a name="toll-bypass-evaluation-and-outcome"></a>有料バイパスの評価と結果

Location-Basedルーティングを使用すると、Teams ユーザーと PSTN 間の通話が評価され、有料バイパスが制限されているかどうかを判断します。 結果に応じて、呼び出しは完了するか完了しません。 

ユーザーがLocation-Basedルーティングを有効にしていて、ユーザーがLocation-Basedルーティング制限が有効になっているサイトに配置されている場合、そのユーザーの料金バイパスは制限されます。 Teams では、次の情報を使用して、有料バイパスが制限されているかどうかを判断します。 

- Teams ユーザーが、ユーザーの Teams 通話ポリシーで定義されているLocation-Basedルーティングに対して有効になっているかどうか。

- Teams ユーザーのエンドポイント ネットワーク サイトの場所と、サイトが Location-Based ルーティングに対して有効になっているかどうか。

- 通話で使用されている PSTN ゲートウェイのネットワーク サイトの場所。

- 通話で使用されている PSTN ゲートウェイが、Location-Based ルーティングに対して有効になっているかどうか。

- 転送シナリオの場合、PSTN 通話のルートは、通話を転送するユーザーのルーティング設定と、通話の転送先となる Teams ユーザーのLocation-Basedルーティング設定に基づいています。  

- 電話会議とグループ通話のシナリオでは、有料バイパスが制限されている Teams ユーザーが通話の一部であるか、またはそのユーザーであるか。

通話が完了できない場合、Teams ユーザーには次のように通知されます。

- 発信 PSTN 通話の場合、通話ウィンドウに次のメッセージが表示されます。組織の設定により通話は許可されません。

- 着信 PSTN 通話の場合、通話は、着信した Teams ユーザーの未応答の通話転送設定 (通常はボイスメール) に基づいてルーティングされます。 Teams ユーザーが未応答の通話設定を構成していない場合、通話は切断されます。

## <a name="apply-location-based-routing"></a>Location-Basedルーティングを適用する

Location-Basedルーティングを次に適用する必要があります。

- [ユーザー](#apply-location-based-routing-at-the-user-location)
- [ネットワーク サイト](#apply-location-based-routing-at-the-network-site)
- [PSTN ゲートウェイ](#apply-location-based-routing-at-the-pstn-gateway)

次のベスト プラクティスに留意してください。

- ゲートウェイに関連付けられている PSTN ゲートウェイとネットワーク サイトの両方が、Location-Based ルーティングに対して有効になっている必要があります。

- Location-Based ルーティングが有効になっている PSTN ゲートウェイを介して通話を発信するには、ユーザーがLocation-Basedルーティングにも有効になっている必要があります。

- Location-Based ルーティングを有効にしているユーザーが不明なネットワーク サイトから発信 PSTN 通話を発信できるようにするには、次のことが必要です。

  - 呼び出しは、Location-Based ルーティングが有効になっている PSTN ゲートウェイから送信する必要があります。
  - PSTN ゲートウェイは、GatewayLbrEnabledUserOverride フラグを True に設定して構成する必要があります。


### <a name="apply-location-based-routing-at-the-user-location"></a>ユーザーの場所Location-Basedルーティングを適用する

有料バイパス制限は、ユーザーが PSTN 呼び出しを行って受信できる条件と、使用できる PSTN ゲートウェイを制御します。 

ユーザーが有料バイパスの制限を受けている場合は、そのユーザーがLocation-Basedルーティングに対して有効になっている必要があります。 有効なユーザーが、Location-Based ルーティングが有効になっているサイトにある場合、ユーザーは、サイトに接続され、Location-Basedルーティングが有効になっているゲートウェイを介して通話を行う必要があります。 

Location-Basedルーティングは、ユーザーの Teams エンドポイントの IP アドレスに基づいてユーザーの現在の場所を決定することで機能し、それに応じてルールを適用します。 Location-Based ルーティングが有効になっているユーザーの場所は、次のように分類できます。 

- **ユーザーは、DID が割り当てられている PSTN ゲートウェイに関連付けられている同じLocation-Basedルーティングが有効なサイトに配置されます。**<br>このシナリオでは、ユーザーは、Location-Based ルーティングが有効になっている構成済みのネットワーク サイトに配置され、ユーザーのダイレクト インワード ダイヤル (DID) 番号は、同じネットワーク サイト内の PSTN ゲートウェイで終了します。 たとえば、ユーザーは自分のオフィスにいるとします。 

- **ユーザーは、DID が割り当てられている PSTN ゲートウェイに関連付けられていない別のLocation-Basedルーティングが有効なサイトにあります。**<br>このシナリオでは、ユーザーは、Location-Based ルーティングが有効になっている構成済みのネットワーク サイトに配置され、そのサイトは、ユーザーの DID 番号が割り当てられている PSTN ゲートウェイに関連付けられません。 たとえば、ユーザーは別のオフィスに移動します。  

- **ユーザーは、Location-Based ルーティングが有効になっていない内部サイトにあります。** <br>このシナリオでは、ユーザーは、Location-Based ルーティングが有効になっていない構成済みのネットワーク サイトに配置されます。 

- **ユーザーは不明なサイトにあります。** 
    - ユーザーは、ネットワーク サイトとして定義されていない内部ネットワーク内にあります。 
    - ユーザーは内部ネットワークの外部に配置されます。 たとえば、ユーザーは自宅や喫茶店でインターネットに接続しています。 

### <a name="apply-location-based-routing-at-the-network-site"></a>ネットワーク サイトLocation-Basedルーティングを適用する 

Location-Based ルーティングが有効になっているユーザーがローミングしている場合、Location-Based ルーティングが有効になっているネットワーク サイトは、使用するゲートウェイを決定するのに役立ちます。 次に例を示します。

- Location-Based ルーティングを有効にしたユーザーが、Location-Based ルーティングが有効になっているサイトにローミングする場合、そのサイトでLocation-Basedルーティングが有効になっている PSTN ゲートウェイのみを送信呼び出しに使用できます。 

- Location-Based ルーティングを有効にしているユーザーが、Location-Based ルーティングが有効になっていないサイトにローミングする場合は、Location-Based ルーティングが有効になっていないゲートウェイを送信呼び出しに使用できます。  

### <a name="apply-location-based-routing-at-the-pstn-gateway"></a>PSTN ゲートウェイLocation-Basedルーティングを適用する  

PSTN ゲートウェイLocation-Basedルーティングを適用するには、次の操作を行う必要があります。

- Location-Based ルーティングのゲートウェイを有効にします。 (ゲートウェイは、Location-Based ルーティングを有効にして、Location-Based ルーティングを有効にしていないユーザーがゲートウェイを使用できないようにする必要があります)。

- ゲートウェイにネットワーク サイトを割り当てます。

その後、システムは、特定のサイト内の特定のユーザーがゲートウェイの使用を許可されているかどうかを判断します。 

さらに、GatewayLbrEnabledUserOverride を True に設定した場合、不明なサイトで場所ベースのルーティングが有効なユーザー (たとえば、自宅で作業しているユーザーは発信 PSTN 呼び出しを行うことができます)。


## <a name="restriction-rules"></a>制限規則

制限規則は、Teams ユーザーがLocation-Basedルーティングに対して有効になっているか、有効になっていないかによって異なります。

### <a name="user-is-enabled-for-location-based-routing"></a>ユーザーが Location-Based ルーティングに対して有効になっている

ユーザーがLocation-Basedルーティングを有効にすると、次のことが適用されます。

- **送信 PSTN 呼び出しを行うには**、次のいずれかが当てはまる必要があります。

  - ユーザーのエンドポイントは、Location-Based ルーティングが有効になっているサイトにあり、同じサイトでLocation-Basedルーティングが有効になっている PSTN ゲートウェイ経由でエグレスを呼び出します。  

  - ユーザーのエンドポイントは不明なサイトにあり、Location-Based ルーティングが有効になっている PSTN ゲートウェイを介してエグレスを呼び出します。 PSTN ゲートウェイは、GatewayLbrEnabledUserOverride パラメーターを True に設定して構成されます。

  - ユーザーのエンドポイントは、Location-Based ルーティングが有効になっていないサイトにあり、Location-Based ルーティングが有効になっていない PSTN ゲートウェイ経由でエグレスを呼び出します。

- **受信 PSTN 呼び出しを受信するには**、次のいずれかが当てはまる必要があります。 

   - ユーザーの応答エンドポイントと PSTN ゲートウェイ経由の通話受信は、Location-Based ルーティングが有効になっているのと同じサイトに配置する必要があります。 PSTN ゲートウェイは、Location-Based ルーティングに対して有効にする必要があります。

   - ユーザーの応答エンドポイントと PSTN ゲートウェイ経由の通話受信は、Location-Based ルーティングが有効になっていないのと同じサイトに配置する必要があります。 PSTN ゲートウェイは、Location-Based ルーティングに対して有効にしないでください。  (このシナリオでは、受信 PSTN 呼び出しをイングレスに再ルーティングしますが、通常はユーザーの電話番号への着信に使用されるゲートウェイとは別の PSTN ゲートウェイを使用します)。

   - ユーザーがローミングしている場合など、他のシナリオでは、呼び出しは許可されておらず、ユーザーの未応答の通話転送設定 (通常はボイスメール) にルーティングされます。  
   
- **1:1 Teams VoIP 通話と PSTN への転送の場合** は、次の点に注意してください。

  - 呼び出しのルーティング(つまり、通話を送信する PSTN ゲートウェイ)は、通話を転送するユーザーのルーティング設定に基づいています。

  - 譲渡が許可されるかどうかは、次に基づいています。
  
    - PSTN に転送されるユーザーのLocation-Basedルーティング設定。
    - エンドポイント ネットワーク サイトの場所。
    - 場所がLocation-Basedルーティングに対して有効になっているかどうか。

    転送されるユーザーが、同じ PSTN ゲートウェイを使用して現在の場所でその PSTN 通話を行うことができる場合は、転送が許可されます。

- **着信または発信の PSTN 通話と別の Teams ユーザーへの転送の場合**、転送が許可されるかどうかは、次によって異なります。

   - 転送された呼び出しを受信しているユーザーのルーティング設定。 
   - エンドポイント ネットワーク サイトの場所。
   - 場所がLocation-Basedルーティングに対して有効になっているかどうか。

   転送は、転送された通話を受信したユーザーが、進行中の PSTN 通話で使用されている PSTN ゲートウェイを使用して、現在の場所でその PSTN 通話を発信または受信できる場合に許可されます。


### <a name="user-is-not-enabled-for-location-based-routing"></a>ユーザーがLocation-Based ルーティングに対して有効になっていない

Teams ユーザーがLocation-Basedルーティングに対して有効になっていない場合、そのユーザーとの間のすべての呼び出しは、Location-Based ルーティングに対して有効になっていない PSTN ゲートウェイを介してルーティングする必要があります。 Location-Basedルーティングが有効になっている PSTN ゲートウェイを介してルーティングされたこのようなユーザーへの着信呼び出しは、ユーザーの未応答の通話転送設定 (通常はボイスメール) にルーティングされます。

### <a name="decision-flows-for-inbound-and-outbound-calls"></a>受信呼び出しと送信呼び出しの決定フロー

次の図は、受信呼び出しと送信呼び出しの決定フローを示しています。

**着信呼び出し**

![受信呼び出しの LBR を示す図](media/lbr-routing-inbound1.png "Location-Based ルーティングのシナリオを示す図")

**送信呼び出し**

![送信呼び出しの LBR を示す図](media/lbr-routing-outbound1.png "Location-Based ルーティングのシナリオを示す図")


## <a name="scenarios-for-location-based-routing"></a>場所に基づくルーティングのシナリオ

このセクションでは、Location-Based ルーティングを使用して有料バイパスを制限するさまざまなシナリオについて説明します。 このシナリオでは、Location-Based ルーティングが有効になっていないユーザーに対する呼び出しのルーティング方法と、Location-Based ルーティングが有効になっているユーザーを比較します。

- [Teams ユーザーが PSTN への発信呼び出しを行う](#teams-user-places-an-outbound-call-to-the-pstn)
- [Teams ユーザーが PSTN から受信通話を受信する](#teams-user-receives-an-inbound-call-from-the-pstn)
- [Teams ユーザーが別の Teams ユーザーに通話を転送または転送する](#teams-user-transfers-or-forwards-call-to-another-teams-user)
- [Teams ユーザーが PSTN エンドポイントに通話を転送または転送する](#teams-user-transfers-or-forwards-call-to-pstn-endpoint)
- [同時呼び出し](#simultaneous-ringing)
- [デリゲーション](#delegation)

次の図は、各シナリオでLocation-Basedルーティングによって有効になっている制限を示しています。 Location-Based ルーティングに対して有効になっているユーザー、ネットワーク サイト、ゲートウェイには、周囲に境界線があります。 図をガイドとして使用して、各シナリオでのLocation-Basedルーティングのしくみを理解するのに役立ちます。  

![Location-Based ルーティングのシナリオを示す図。](media/lbr-direct-routing.png "Location-Based ルーティングのシナリオを示す図")

### <a name="teams-user-places-an-outbound-call-to-the-pstn"></a>Teams ユーザーが PSTN への発信呼び出しを行う

#### <a name="user-not-enabled-for-location-based-routing"></a>ユーザーがLocation-Based ルーティングに対して有効になっていない

Location-Basedルーティングが有効になっていないユーザーは、割り当てられた音声ルーティング ポリシーを使用して、Location-Basedルーティングが有効になっていない任意のサイトのゲートウェイを使用して発信呼び出しを行うことができます。 ただし、ゲートウェイが Location-Based ルーティングに対して有効になっている場合、ユーザーは音声ルーティング ポリシーに割り当てられている場合でも、ゲートウェイを介して発信呼び出しを行うことはできません。 ユーザーが Location-Based ルーティングが有効になっているサイトにローミングする場合、ユーザーは、Location-Based ルーティングが有効になっていない通常のルーティング ゲートウェイ経由でのみ通話を行うことができます。
 
#### <a name="user-enabled-for-location-based-routing"></a>Location-Based ルーティングに対して有効なユーザー

これに対し、Location-Based ルーティングが有効になっているユーザーの送信呼び出しのルーティングは、ユーザーのエンドポイントのネットワークの場所の影響を受けます。 次の表は、Location-Basedルーティングが、User1 の場所に応じて User1 の送信呼び出しのルーティングにどのように影響するかを示しています。 

|User1 エンドポイントの場所  |User1 の送信呼び出しのルーティング  |
|---------|---------|
|ユーザーの DID が割り当てられているサイトと同じサイトで、Location-Based ルーティングが有効になっているサイト (Site1)      |ユーザーの音声ルーティング ポリシーに基づいて、Site1 でLocation-Based ルーティング (GW1) が有効になっているゲートウェイ経由でルーティングされた通話         |
|ユーザーの DID が割り当てられているサイトとは異なり、Location-Based ルーティングが有効になっているサイト (Site2)    |ユーザーの音声ルーティング ポリシーに基づいて、ローミング Site2 でLocation-Based ルーティング (GW2) が有効になっているゲートウェイ経由でルーティングされた通話        |
|ユーザーの DID が割り当てられているサイトとは異なり、サイトでLocation-Based ルーティングが有効になっていない (Site3)  |ユーザーの音声ルーティング ポリシーに基づいて、Location-Based ルーティング (GW3) が有効になっていないサイトでLocation-Based ルーティングが有効になっていないゲートウェイ経由でルーティングされた通話       |
|不明な内部ネットワーク (Location4)    |  ゲートウェイで GatewayLbrEnabledUserOverride が True に設定されていない限り、PSTN 呼び出しは許可されません       |
|不明な外部ネットワーク (Location5)    | ゲートウェイで GatewayLbrEnabledUserOverride が True に設定されていない限り、PSTN 呼び出しは許可されません       |

### <a name="teams-user-receives-an-inbound-call-from-the-pstn"></a>Teams ユーザーが PSTN から受信通話を受信する

#### <a name="user-not-enabled-for-location-based-routing"></a>ユーザーがLocation-Based ルーティングに対して有効になっていない

Location-Basedルーティングを有効にしていないユーザーは、割り当てられた DID 番号のイングレスを使用するLocation-Basedルーティングに対して有効になっていないゲートウェイから受信呼び出しを受け取ることができます。 ユーザーが Location-Based ルーティングが有効になっていないサイトにローミングした場合でも、通常の PSTN ゲートウェイを介して通話を受信できます。
  
#### <a name="user-enabled-for-location-based-routing"></a>Location-Based ルーティングに対して有効なユーザー

これに対し、Location-Based ルーティングを有効にしたユーザーは、同じサイトに配置されている場合にのみ、DID が割り当てられている PSTN ゲートウェイからの受信呼び出しを受信できます。 次の表は、User1 が異なるネットワークの場所に移動したときに、User1 が受信呼び出しを受け取る方法を示しています。 呼び出しがユーザーのエンドポイントにルーティングされない場合、設定が構成されている場合は、ユーザーの未応答の通話転送設定に移動します。 通常、通話はボイスメールに転送されます。  

|User1 エンドポイントの場所  |User1 への受信呼び出しのルーティング  |
|---------|---------|
|ユーザーの DID が割り当てられているサイトと同じサイト、Location-Based ルーティングが有効になっているサイト (Site1)   | Site1 で User1 のエンドポイントにルーティングされた呼び出し        |
|ユーザーの DID が割り当てられているサイトとは異なり、Location-Based ルーティングが有効になっているサイト (Site2)    | Site2 のエンドポイントにルーティングされない呼び出し        |
|ユーザーの DID が割り当てられているサイトとは異なり、サイトでLocation-Based ルーティングが有効になっていない (Site3)    | Site3 のエンドポイントにルーティングされない呼び出し        |
|不明な内部ネットワーク (Location4)   | Location4 のエンドポイントにルーティングされない呼び出し        |
|不明な外部ネットワーク (Location5)     | Location5 のエンドポイントにルーティングされない呼び出し        |

### <a name="teams-user-transfers-or-forwards-call-to-another-teams-user"></a>Teams ユーザーが別の Teams ユーザーに通話を転送または転送する

PSTN エンドポイントが関係する場合、Location-Basedルーティングでは、一方または両方のユーザーがLocation-Based ルーティングに対して有効になっているかどうかを分析し、両方のエンドポイントの場所に応じて通話を転送または転送するかどうかを決定します。 
 
通話転送では、発信側ユーザーが通話を受け取る必要があります。通話転送では、最初の呼び出しに応答する必要はありません。 着信呼び出しを受信する場所にユーザー 1 がいない場合でも通話を転送できます (Teams ユーザーの表は [PSTN セクションから着信通話を受信](#teams-user-receives-an-inbound-call-from-the-pstn) します)、User1 が着信呼び出しを受信できない場合は通話を転送できません。 

#### <a name="user-not-enabled-for-location-based-routing"></a>ユーザーがLocation-Based ルーティングに対して有効になっていない

Location-Based ルーティングが有効になっていないユーザーは、Location-Based ルーティングを有効にしていない他のユーザーに PSTN 通話を転送または転送できます。 Location-Based ルーティングが有効になっているユーザーは、通常、PSTN 呼び出しのルーティングが有効なゲートウェイLocation-Basedに併置されます。 そのため、有効になっていないユーザーは、Location-Based ルーティングを有効にしているユーザーに PSTN 通話を転送したり転送したりすることはできません。 例外は、Location-Based ルーティングが有効なユーザーが、Location-Based ルーティングが有効になっていないサイトにローミングする場合です。 このシナリオでは、転送された呼び出しが許可されます。  

同様に、Location-Based ルーティングを有効にしていないユーザーは、Location-Based ルーティングが有効になっていない別のユーザーからの転送または転送された PSTN 呼び出しのみを受信できます。 

#### <a name="user-enabled-for-location-based-routing"></a>Location-Based ルーティングに対して有効なユーザー

Location-Based ルーティングが有効になっているゲートウェイからの受信 PSTN 通話の転送と転送は、ターゲット ユーザーが Location-Based ルーティングに対して有効になっていて、同じサイトに配置されている場合にのみ許可されます。 それ以外の場合、通話の転送と転送は許可されません。 

次の表は、ターゲット ユーザーの場所に応じて、通話転送と通話転送が許可されるかどうかを示しています。 この表では、Site1 にある User1 によって、Location-Based ルーティングも有効になっている他の Teams ユーザーと、別の場所にいる他の Teams ユーザーへの転送が開始されます。  

|ターゲット ユーザー エンドポイントの場所|User1 が通話転送を開始する |User1 がコール フォワードを開始する|
|---------|---------|---------|
|イニシエーターと同じネットワーク サイト (User2)|許可|許可|
|Location-Based ルーティングが有効になっている別のネットワーク サイト (User3)|許可されていません|許可されていません|
|異なるネットワーク サイト、サイトがLocation-Based ルーティングに対して有効になっていない (User4)|許可されていません|許可されていません|
|不明な内部ネットワーク (User5)| 許可されていません|許可されていません|
|不明な外部ネットワーク (User6)| 許可されていません|許可されていません|

### <a name="teams-user-transfers-or-forwards-call-to-pstn-endpoint"></a>Teams ユーザーが PSTN エンドポイントに通話を転送または転送する

#### <a name="user-not-enabled-for-location-based-routing"></a>ユーザーがLocation-Based ルーティングに対して有効になっていない

- 別の PSTN 番号への PSTN 呼び出しの転送と転送が許可されます。 

- PSTN への受信 VOIP 呼び出しの転送と転送は、発信者の有料バイパス制限を遵守する必要があります。 

    - 呼び出し元が Location-Based ルーティングに対して有効になっていない場合は、Location-Based ルーティングが有効になっていない PSTN ゲートウェイに転送できます。
    - 呼び出し元がLocation-Basedルーティングに対して有効になっている場合は、同じネットワーク サイトにあるLocation-Basedルーティングが有効なゲートウェイにのみ転送できます。 

#### <a name="user-enabled-for-location-based-routing"></a>Location-Based ルーティングに対して有効なユーザー

- PSTN 呼び出しを別の PSTN 番号に転送および転送するには、着信呼び出しが到着したのと同じLocation-Basedルーティングが有効なゲートウェイをルーティングする必要があります。

- PSTN への受信 VOIP 呼び出しの転送と転送には、発信者と呼び出し元ユーザーの有料バイパス制限の両方が適用される必要があります。 

    - 呼び出し元が Location-Based ルーティングに対して有効になっていない場合は、Location-Based ルーティングが有効になっていない PSTN ゲートウェイに転送できます。

    - 呼び出し元が Location-Based ルーティングに対して有効になっている場合は、同じネットワーク サイトにある Location-Based ルーティングが有効なゲートウェイにのみ転送できます。
 
次の表は、Location-Based ルーティングが、呼び出しを転送または PSTN エンドポイントに転送する別の場所のユーザーに対Location-Basedルーティングが有効なユーザー 1 の Site1 からの VOIP 呼び出しのルーティングにどのように影響するかを示しています。  

|通話の転送または転送を開始するユーザー  |PSTN への転送または転送  |
|---------|---------|
|同じネットワーク サイト、Location-Based ルーティングで有効になっているサイト (User2)   |結果として得られる PSTN 呼び出しは、User2 の音声ルーティング ポリシーに基づいて計算されたルートが、Site1 でルーティングが有効なゲートウェイ 1 Location-Based経由するルートになる場合にのみ許可されます         |
|Location-Based ルーティングが有効になっている別のネットワーク サイト (User3)    |結果として得られる PSTN 呼び出しは、User3 の音声ルーティング ポリシーに基づいて計算されたルートが、Site1 でルーティングが有効なゲートウェイ 1 Location-Based経由するルートになる場合にのみ許可されます |
|異なるネットワーク サイト、サイトがLocation-Based ルーティングに対して有効になっていない (User4)    |結果として得られる PSTN 呼び出しは、User4 の音声ルーティング ポリシーに基づいて計算されたルートが、Site1 でルーティングが有効なゲートウェイ 1 Location-Based経由するルートになる場合にのみ許可されます          |
|不明な内部ネットワーク (User5)     |結果として得られる PSTN 呼び出しは、User5 の音声ルーティング ポリシーに基づいて計算されたルートが、Site1 でルーティングが有効なゲートウェイ 1 Location-Based経由するルートになる場合にのみ許可されます          |
|不明な外部ネットワーク (User6)   |結果として得られる PSTN 呼び出しは、User6 の音声ルーティング ポリシーに基づいて計算されたルートが、Site1 でルーティングが有効なゲートウェイ 1 Location-Based経由するルートになる場合にのみ許可されます          |

### <a name="simultaneous-ringing"></a>同時呼び出し

Location-Based ルーティングを有効にしたユーザーが通話を受信し、同時呼び出しが有効になっている場合、Location-Basedルーティングでは、発信側の場所と着信側のエンドポイントが分析され、通話をルーティングするかどうかを判断します。 同時呼び出しは、呼び出し転送と同じLocation-Based規則に従います。 

#### <a name="simultaneous-ringing-for-another-teams-user"></a>別の Teams ユーザーの同時呼び出し

次の表は、Location-Based ルーティングで、User1 の受信 PSTN 呼び出しに対して異なるユーザーへの同時呼び出しを許可するかどうかを示しています。

|ターゲット ユーザー エンドポイントの場所|同時リング  |
|---------|---------|
|イニシエーターと同じネットワーク サイト (User2)   |許可         |
|Location-Based ルーティングに対して有効になっているさまざまなローミング ネットワーク サイト (User3)   |許可されていません         |
|Location-Based ルーティングに対してローミング されたネットワーク サイトが有効になっていない (User4)   |許可されていません        |
|不明な内部ネットワーク (User5)    | 許可されていません        |
|不明な外部ネットワーク (User6)    |許可されていません        |
|ターゲット ユーザーが PSTN 番号である    |呼び出しは、ユーザー 1 の音声ルーティング ポリシーに基づいて、Site1 でルーティングが有効なゲートウェイ 1 Location-Based経由でのみルーティングできます      |

#### <a name="simultaneous-ringing-to-a-pstn-endpoint"></a>PSTN エンドポイントへの同時呼び出し

次の表はLocation-Based同時リングが PSTN 番号に設定されている別の場所のユーザーに対する、Site1 にある Location-Based ルーティングが有効な User1 からの受信 VoIP 通話のルーティング動作を示しています。 

|呼び出されたユーザー エンドポイントの場所  |同時リング ターゲットは PSTN エンドポイントです |
|---------|---------|
|同じネットワーク サイト、Location-Based ルーティングで有効になっているサイト (User2)    |結果として得られる PSTN 呼び出しは、User2 の音声ルーティング ポリシーに基づいて計算されたルートが、Site1 でルーティングが有効なゲートウェイ 1 Location-Based経由するルートになる場合にのみ許可されます        |
|Location-Based ルーティングに対して有効になっている別のネットワーク サイト (User3)    |結果として得られる PSTN 呼び出しは、User3 の音声ルーティング ポリシーに基づいて計算されたルートが、Site1 でルーティングが有効なゲートウェイ 1 Location-Based経由するルートになる場合にのみ許可されます         |
|Location-Based ルーティングに対して有効になっていない別のネットワーク サイト (User4)    |結果として得られる PSTN 呼び出しは、User4 の音声ルーティング ポリシーに基づいて計算されたルートが、Site1 でルーティングが有効なゲートウェイ 1 Location-Based経由するルートになる場合にのみ許可されます          |
|不明な内部ネットワーク (User5)    |結果として得られる PSTN 呼び出しは、User5 の音声ルーティング ポリシーに基づいて計算されたルートが、Site1 でルーティングが有効なゲートウェイ 1 Location-Based経由するルートになる場合にのみ許可されます          |
|不明な外部ネットワーク (User6)   |結果として得られる PSTN 呼び出しは、User6 の音声ルーティング ポリシーに基づいて計算されたルートが、Site1 でルーティングが有効なゲートウェイ 1 Location-Based経由するルートになる場合にのみ許可されます          |

#### <a name="inbound-calls-through-voice-apps-auto-attendant-or-call-queue"></a>音声アプリを介した着信呼び出し (自動応答または通話キュー)

Location-Based ルーティングが有効なゲートウェイからの受信 PSTN 呼び出しは、自動応答または通話キューへの接続を許可されます。 

Location-Basedルーティングが有効になっているユーザーは、受信 PSTN 呼び出しの発信元の同じサイトに配置されている場合に、これらのアプリケーションの着信通話転送を受信するためにサポートされます。 これらのシナリオでローカル メディアの最適化とメディア バイパスをサポートするには、通話キューを転送モード (会議モード = OFF) 用に構成する必要があります。
 
ユーザーと PSTN への通話転送と同時呼び出しは、音声アプリの転送に許可されます。 ターゲットへの呼び出しを完了すると、前に示したのと同じLocation-Basedルーティング 規則が適用されます。  
 
ボイスメールへの転送も許可されます。  

### <a name="delegation"></a>デリゲーション

Teams ユーザーは、代わりに通話を行って受信できる代理人を選択できます。 Teams の委任機能は、次のようにLocation-Basedルーティングの影響を受けます。 

- 委任者の代わりにLocation-Basedルーティングが有効なデリゲートからの送信呼び出しには、同じ規則が適用されます。 通話ルーティングは、デリゲートの通話承認ポリシー、音声ルーティング ポリシー、場所に基づいています。 詳細については、「 [Teams ユーザーが PSTN に発信通話を発信する」を](#teams-user-places-an-outbound-call-to-the-pstn)参照してください。 

- 委任者への受信 PSTN 呼び出しの場合、通話転送または他のユーザーへの同時呼び出しに適用されるのと同じLocation-Basedルーティング規則も代理人に適用されます。 詳細については、「 [Teams ユーザーが別の Teams ユーザーに通話を転送または転送する](#teams-user-transfers-or-forwards-call-to-another-teams-user)」、「 [Teams ユーザーが PSTN エンドポイントに通話を転送または転送する](#teams-user-transfers-or-forwards-call-to-pstn-endpoint)」、および [「同時呼び出](#simultaneous-ringing)し」を参照してください。 代理人が PSTN エンドポイントを同時リング ターゲットとして設定する場合、代理人の音声ルーティング ポリシーを使用して PSTN への呼び出しをルーティングします。 

- 委任の場合、委任者と関連するデリゲートを同じネットワーク サイトに配置することをお勧めします。 

## <a name="other-planning-considerations"></a>計画に関するその他の考慮事項

### <a name="changes-from-an-on-premises-location-based-routing-deployment"></a>オンプレミスのLocation-Basedルーティングデプロイからの変更

ネットワーク サイト音声ルーティング ポリシーは使用されなくなりました。 代わりに、ユーザーの音声ルーティング ポリシーを使用します。 ユーザーが他のサイトにローミングできるようにするには、音声ルーティング ポリシーにローミングされたサイトのゲートウェイが含まれている必要があります。 

### <a name="technical-considerations-for-location-based-routing"></a>場所に基づくルーティングに関する技術的考慮事項

IPv4 サブネットと IPv6 サブネットはサポートされていますが、一致を確認する場合は IPv6 が優先されます。

### <a name="client-support-for-location-based-routing"></a>Location-Based ルーティングのクライアント サポート

次の Teams クライアントがサポートされています。
- Teams デスクトップ クライアント (Windows と Mac)
- Teams モバイル クライアント (iOS および Android)
- Teams IP 電話

Teams Web クライアントとSkype for Business クライアントはサポートされていません。

### <a name="capabilities-not-supported-by-location-based-routing"></a>場所に基づくルーティングでサポートされていない機能

Location-Based ルーティングは、次の種類の操作には適用されません。 Location-Basedルーティングは、Teams エンドポイントが次のシナリオで PSTN エンドポイントと対話する場合に適用されません。 

- 通話保留による PSTN 通話の保留または再開 

- オンプレミス Skype for Business ユーザーまたは Skype for Business Online ユーザーが Teams ユーザーを呼び出す  

### <a name="location-based-routing-for-conferencing"></a>会議のLocation-Basedルーティング

PSTN 通話で電話会議ライセンスを持たないLocation-Basedルーティングが有効なユーザーは、別のユーザーまたは PSTN 番号で会議を開始することはできません。 自動応答または通話キューへの接続は許可されます。

ユーザーが電話会議ライセンスを持っている場合、ユーザーは関連するユーザーとの会議を開始し、電話会議ブリッジを介して PSTN を呼び出して電話会議を開始する必要があります。 ユーザーが既に PSTN 通話中の場合は、電話会議ブリッジを使用して通話をエスカレートしてダイヤルアウトすることで、別のユーザーまたは PSTN 番号を通話に追加できます。

電話会議ライセンスを持たないユーザーが開始した電話会議では、電話会議でルーティングが有効なユーザーが少なくとも 1 人Location-Based場合、PSTN 参加者の追加は許可されません。 ルーティングが有効な参加者が通話 Location-Basedに参加するように招待される前に、少なくとも 1 人の PSTN 参加者がそのような電話会議に参加している場合は、ルーティングが有効な参加者Location-Based通話に追加できません。

Location-Basedルーティングが有効なユーザーが、Location-Based ルーティングが有効になっていない内部サイトからの電話会議に参加している場合、上記の段落の制限は適用されません。 

電話会議のネットワーク上の会議は、インドのテレフォニー機器と共に展開しないでください。

PSTN 通話でLocation-Basedルーティングが有効なユーザーは、その呼び出しを別の呼び出しとマージすることはできません。 PSTN 通話の記録と PSTN 通話のコンプライアンス記録はサポートされていません。

### <a name="media-bypass-requirement-for-location-based-routing"></a>Location-Based ルーティングのメディア バイパス要件

インドで Location-Based ルーティングを展開する場合は、メディア バイパスも構成する必要があります。 詳細については、「[ダイレクト ルーティングを使用したメディア バイパスの計画」と「ダイレクト ルーティングの](direct-routing-plan-media-bypass.md)[ローカル メディアの最適化」を](direct-routing-media-optimization.md)参照してください。

### <a name="direct-voice-over-ip-voip"></a>Direct Voice over IP (VoIP)

Direct Voice over IP (VoIP) は、インドのテレフォニー機器と共に展開しないでください。


## <a name="related-articles"></a>関連記事

- [ダイレクト ルーティングの場所に基づくルーティングを有効にする](location-based-routing-enable.md)
- [Teams のクラウド音声機能のネットワーク設定](cloud-voice-network-settings.md)
