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
description: Teams Phone Direct Routing のLocation-Basedルーティングを計画する方法について説明します。
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: 795433f832d57767a7937be1a9d3e7f31e73f240
ms.sourcegitcommit: 41a75f1ba5ceb09f8db7d468aa41b63a89ab9c30
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2022
ms.locfileid: "67647441"
---
# <a name="plan-location-based-routing-for-direct-routing"></a>ダイレクト ルーティングの場所に基づくルーティングを計画する

一部の国と地域では、公衆交換電話網 (PSTN) プロバイダーをバイパスして、長距離通話コストを削減することは違法です。 

この記事では、Location-Based ルーティングを使用して、地理的な場所に基づいて Microsoft Teams ユーザーの有料バイパスを制限するために知っておくべきことについて説明します。 この記事は、ダイレクト ルーティングにのみ適用されます。 Location-Basedルーティングは、通話プランまたはオペレーター接続には適用されません。

Location-Basedルーティングを有効にする準備ができたら、次を参照してください。

- [場所に基づくルーティングのネットワーク設定を構成する](location-based-routing-configure-network-settings.md)
- [Location-Based ルーティングのネットワーク設定を展開する](location-based-routing-configure-network-settings.md)
- [ダイレクト ルーティングの場所に基づくルーティングを有効にする](location-based-routing-enable.md)

> [!NOTE]
> Location-Based ルーティングを使用して、ユーザーの場所に基づいて PSTN 通話を動的にルーティングしないでください。 これを行うと、意図しない結果が発生する可能性があります。

## <a name="overview"></a>概要

Location-Based ルーティングを使用すると、ポリシーと、着信または発信 PSTN 通話時のユーザーの地理的な場所に基づいて、ユーザーの有料バイパスを制限できます。 

Location-Based ルーティングでは、ネットワークリージョン、サイト、サブネットに対して定義したネットワーク トポロジが使用されます。 場所に対して有料バイパスが制限されている場合は、その場所の各 IP サブネットと各 PSTN ゲートウェイをネットワーク サイトに関連付けます。 

PSTN 通話時に、ユーザーの場所は、ユーザーの Teams エンドポイントが接続されている IP サブネットによって決まります。 ユーザーが複数の Teams クライアントを異なるサイトに配置している場合、Location-Based ルーティングでは、Teams エンドポイントの場所に応じて、各クライアントのルーティングが個別に適用されます。

ネットワーク設定の詳細については、「 [Teams のクラウド音声機能のネットワーク設定](cloud-voice-network-settings.md)」を参照してください。

この記事では、ネットワーク サイトが次のいずれかの状態にある可能性があることを前提としています。

- **有効** - テナント ネットワーク サブネットとサイトを使用して構成され、Location-Based ルーティングが有効になっているサイト。

- **無効** - テナント ネットワーク サブネットとサイトを使用して構成されたサイトで、Location-Based ルーティングが有効になっていません。

- **不明** - テナント ネットワーク サブネットとサイトを使用して構成されていないサイト。 通常、このようなサイトは企業ネットワークの内部ですが、設計上は構成されていないか、企業ネットワークの外部です。 いずれの場合も、これらのサイトはLocation-Basedルーティングに対して有効になっていません。 

### <a name="toll-bypass-evaluation-and-outcome"></a>有料バイパスの評価と結果

Location-Basedルーティングを使用すると、Teams ユーザーと PSTN の間の通話が評価され、有料バイパスが制限されているかどうかを判断します。 結果に応じて、呼び出しは完了するか、完了しません。 

ユーザーがLocation-Basedルーティングを有効にしていて、ユーザーがLocation-Basedルーティング制限が有効になっているサイトにある場合、そのユーザーの有料バイパスが制限されます。 Teams では、次の情報を使用して、有料バイパスが制限されているかどうかを判断します。 

- ユーザーの Teams 通話ポリシーで定義されているLocation-Basedルーティングに対して Teams ユーザーが有効になっているかどうか。

- Teams ユーザーのエンドポイント ネットワーク サイトの場所と、サイトがLocation-Basedルーティングに対して有効になっているかどうか。

- 通話で使用されている PSTN ゲートウェイのネットワーク サイトの場所。

- 通話で使用されている PSTN ゲートウェイがLocation-Basedルーティングに対して有効になっているかどうか。

- 転送シナリオでは、PSTN 通話のルートは、通話を転送するユーザーのルーティング設定と、通話の転送先である Teams ユーザーのLocation-Basedルーティング設定に基づいています。  

- 会議とグループ通話のシナリオでは、有料バイパスが制限されている Teams ユーザーが通話の一部であるか、または通話の一部であったか。

通話を完了できない場合は、Teams ユーザーに次のように通知されます。

- 発信 PSTN 通話の場合、通話ウィンドウに次のメッセージが表示されます。組織の設定により通話は許可されません。

- 着信 PSTN 通話の場合、通話は、呼び出された Teams ユーザーの応答のない通話転送設定 (通常はボイスメール) に基づいてルーティングされます。 Teams ユーザーに未回答の通話設定が構成されていない場合、通話は切断されます。

## <a name="apply-location-based-routing"></a>Location-Basedルーティングを適用する

Location-Basedルーティングを次に適用する必要があります。

- [ユーザー](#apply-location-based-routing-at-the-user-location)
- [ネットワーク サイト](#apply-location-based-routing-at-the-network-site)
- [PSTN ゲートウェイ](#apply-location-based-routing-at-the-pstn-gateway)

次のベスト プラクティスに留意してください。

- ゲートウェイに関連付けられている PSTN ゲートウェイとネットワーク サイトは、両方ともLocation-Basedルーティングを有効にする必要があります。

- Location-Based ルーティングが有効になっている PSTN ゲートウェイを介して通話を発信するには、Location-Based ルーティングも有効にする必要があります。

- Location-Based ルーティングを有効にしているユーザーが不明なネットワーク サイトから発信 PSTN 通話を発信できるようにするには、次の点に該当する必要があります。

  - この呼び出しは、Location-Based ルーティングが有効になっている PSTN ゲートウェイからエグレスする必要があります。
  - PSTN ゲートウェイは、GatewayLbrEnabledUserOverride が True に設定されているフラグを使用して構成する必要があります。


### <a name="apply-location-based-routing-at-the-user-location"></a>ユーザーの場所でLocation-Basedルーティングを適用する

有料バイパス制限は、ユーザーが PSTN 通話を発信および受信できる条件と、使用できる PSTN ゲートウェイを制御します。 

ユーザーが有料バイパス制限を受けている場合、そのユーザーはLocation-Basedルーティングを有効にする必要があります。 有効なユーザーが、Location-Based ルーティングが有効になっているサイトに配置されている場合、ユーザーは、サイトに接続され、Location-Based ルーティングが有効になっているゲートウェイを介して呼び出す必要があります。 

Location-Based ルーティングは、ユーザーの Teams エンドポイントの IP アドレスに基づいてユーザーの現在の場所を決定することで機能し、それに応じてルールを適用します。 Location-Based ルーティングが有効になっているユーザーの場所は、次のように分類できます。 

- **ユーザーは、DID が割り当てられている PSTN ゲートウェイに関連付けられているのと同じLocation-Basedルーティングが有効なサイトにあります。**<br>このシナリオでは、ユーザーは、Location-Based ルーティングが有効になっている構成済みのネットワーク サイトに配置され、同じネットワーク サイト内にある PSTN ゲートウェイでユーザーの直接内向きダイヤル (DID) 番号が終了します。 たとえば、ユーザーは自分のオフィスにいるとします。 

- **ユーザーは、DID が割り当てられている PSTN ゲートウェイに関連付けられていない別のLocation-Based ルーティングが有効なサイトにあります。**<br>このシナリオでは、ユーザーは、Location-Basedルーティングが有効になっている構成済みのネットワーク サイトにあり、そのサイトは、ユーザーの DID 番号が割り当てられている PSTN ゲートウェイに関連付けられていない。 たとえば、ユーザーは別のオフィスに移動します。  

- **ユーザーは、Location-Based ルーティングが有効になっていない内部サイトにあります。** <br>このシナリオでは、ユーザーは、Location-Based ルーティングが有効になっていない構成済みのネットワーク サイトに配置されます。 

- **ユーザーは不明なサイトにあります。** 
    - ユーザーは、ネットワーク サイトとして定義されていない内部ネットワーク内にあります。 
    - ユーザーは内部ネットワークの外部にあります。 たとえば、ユーザーは自宅やコーヒー ショップでインターネット上にいます。 

### <a name="apply-location-based-routing-at-the-network-site"></a>ネットワーク サイトでLocation-Basedルーティングを適用する 

Location-Based ルーティングを有効にしているユーザーがローミングしている場合、Location-Based ルーティングが有効になっているネットワーク サイトは、使用するゲートウェイを決定するのに役立ちます。 次に例を示します。

- Location-Based ルーティングを有効にしたユーザーが、Location-Based ルーティングが有効になっているサイトにローミングする場合は、そのサイトでLocation-Based ルーティングが有効になっている PSTN ゲートウェイのみを発信通話に使用できます。 

- Location-Based ルーティングを有効にしたユーザーが、Location-Based ルーティングが有効になっていないサイトにローミングする場合、Location-Based ルーティングに対して有効になっていないゲートウェイを送信呼び出しに使用できます。  

### <a name="apply-location-based-routing-at-the-pstn-gateway"></a>PSTN ゲートウェイでLocation-Basedルーティングを適用する  

PSTN ゲートウェイでLocation-Basedルーティングを適用するには、次の操作を行う必要があります。

- Location-Based ルーティングのゲートウェイを有効にします。 (Location-Based ルーティングが有効になっていないユーザーがゲートウェイを使用できないようにするには、Location-Based ルーティングを有効にする必要があります)。

- ゲートウェイにネットワーク サイトを割り当てます。

その後、システムは、特定のサイト内の特定のユーザーがゲートウェイを使用できるかどうかを判断します。 

さらに、GatewayLbrEnabledUserOverride を True に設定した場合、場所ベースのルーティングが有効なユーザーは不明なサイトで実行されます。たとえば、自宅で作業しているユーザーは、発信 PSTN 通話を行うことができます。


## <a name="restriction-rules"></a>制限規則

制限規則は、Teams ユーザーがLocation-Basedルーティングを有効にしているかどうかによって異なります。

### <a name="user-is-enabled-for-location-based-routing"></a>ユーザーがLocation-Basedルーティングに対して有効になっている

ユーザーがLocation-Basedルーティングを有効にすると、次のことが適用されます。

- **発信 PSTN 通話を行うには**、次のいずれかに該当する必要があります。

  - ユーザーのエンドポイントは、Location-Based ルーティングが有効なサイトにあり、同じサイトでLocation-Basedルーティングが有効になっている PSTN ゲートウェイを介してエグレスを呼び出します。  

  - ユーザーのエンドポイントは不明なサイトにあり、Location-Basedルーティングが有効になっている PSTN ゲートウェイを介してエグレスを呼び出します。 PSTN ゲートウェイは、GatewayLbrEnabledUserOverride パラメーターを True に設定して構成されます。

  - ユーザーのエンドポイントは、Location-Based ルーティングが有効になっていないサイトにあり、Location-Based ルーティングが有効になっていない PSTN ゲートウェイを介してエグレスを呼び出します。

- **受信 PSTN 通話を受信するには**、次のいずれかに該当する必要があります。 

   - ユーザーの応答エンドポイントと PSTN ゲートウェイの呼び出しの受信は、Location-Based ルーティングが有効になっているのと同じサイトに配置する必要があります。 Location-Based ルーティングに対して PSTN ゲートウェイを有効にする必要があります。

   - ユーザーの応答エンドポイントと PSTN ゲートウェイの呼び出しの受信は、Location-Based ルーティングが有効になっていない同じサイトに配置されている必要があります。 Location-Based ルーティングに対して PSTN ゲートウェイを有効にしないでください。  (このシナリオでは、ユーザーの電話番号への着信に通常使用される PSTN ゲートウェイよりも別の PSTN ゲートウェイを使用して、着信 PSTN 通話をイングレスに再ルーティングする必要があります)。

   - ユーザーがローミングしている場合など、その他のシナリオでは、通話は許可されておらず、ユーザーの応答のない通話転送設定 (通常はボイスメール) にルーティングされます。  
   
- **1:1 Teams VoIP 通話と PSTN への転送については**、次の点に注意してください。

  - 通話のルーティング(つまり、通話を発信する PSTN ゲートウェイ) は、通話を転送するユーザーのルーティング設定に基づいています。

  - 転送が許可されるかどうかは、次に基づいています。
  
    - PSTN に転送されるユーザーのLocation-Basedルーティング設定。
    - エンドポイント ネットワーク サイトの場所。
    - 場所が Location-Based ルーティングに対して有効になっているかどうか。

    転送されるユーザーが同じ PSTN ゲートウェイを使用してその PSTN 通話を現在の場所で行うことができる場合、転送は許可されます。

- **着信または発信の PSTN 通話と別の Teams ユーザーへの転送の場合**、転送が許可されるかどうかは、次によって異なります。

   - 転送された通話を受信しているユーザーのルーティング設定。 
   - エンドポイント ネットワーク サイトの場所。
   - 場所が Location-Based ルーティングに対して有効になっているかどうか。

   転送された通話を受け取ったユーザーが、進行中の PSTN 通話で使用される PSTN ゲートウェイを使用してその PSTN 通話を現在の場所で発信または受信できる場合、転送が許可されます。


### <a name="user-is-not-enabled-for-location-based-routing"></a>ユーザーがLocation-Basedルーティングに対して有効になっていない

Teams ユーザーが Location-Based ルーティングを有効にしていない場合、そのユーザーとの間のすべての通話は、Location-Based ルーティングが有効になっていない PSTN ゲートウェイ経由でルーティングする必要があります。 Location-Basedルーティングが有効になっている PSTN ゲートウェイを介してルーティングされたこのようなユーザーへの受信通話は、ユーザーの応答のない通話転送設定 (通常はボイスメール) にルーティングされます。

### <a name="decision-flows-for-inbound-and-outbound-calls"></a>着信呼び出しと送信呼び出しのデシジョン フロー

次の図は、着信呼び出しと送信呼び出しの決定フローを示しています。

**受信呼び出し**

![受信呼び出しの LBR を示す図](media/lbr-routing-inbound1.png "Location-Based ルーティングのシナリオを示す図")

**発信呼び出し**

![発信呼び出しの LBR を示す図](media/lbr-routing-outbound1.png "Location-Based ルーティングのシナリオを示す図")


## <a name="scenarios-for-location-based-routing"></a>場所に基づくルーティングのシナリオ

このセクションでは、Location-Based ルーティングを使用して有料バイパスを制限するためのさまざまなシナリオについて説明します。 このシナリオでは、Location-Based ルーティングが有効になっていないユーザーに対して呼び出しをルーティングする方法と、Location-Based ルーティングが有効になっているユーザーを比較します。

- [Teams ユーザーが PSTN への発信通話を発信する](#teams-user-places-an-outbound-call-to-the-pstn)
- [Teams ユーザーが PSTN から受信通話を受信する](#teams-user-receives-an-inbound-call-from-the-pstn)
- [Teams ユーザーが別の Teams ユーザーに通話を転送または転送する](#teams-user-transfers-or-forwards-call-to-another-teams-user)
- [Teams ユーザーが PSTN エンドポイントに通話を転送または転送する](#teams-user-transfers-or-forwards-call-to-pstn-endpoint)
- [同時呼び出し](#simultaneous-ringing)
- [デリゲーション](#delegation)

次の図は、各シナリオでLocation-Basedルーティングによって有効になっている制限を示しています。 Location-Based ルーティングが有効になっているユーザー、ネットワーク サイト、ゲートウェイには、その周囲に境界線があります。 図をガイドとして使用すると、各シナリオでルーティングLocation-Based動作する方法を理解するのに役立ちます。  

![Location-Based ルーティングのシナリオを示す図。](media/lbr-direct-routing.png "Location-Based ルーティングのシナリオを示す図")

### <a name="teams-user-places-an-outbound-call-to-the-pstn"></a>Teams ユーザーが PSTN への発信通話を発信する

#### <a name="user-not-enabled-for-location-based-routing"></a>Location-Based ルーティングが有効になっていないユーザー

Location-Based ルーティングを有効にしていないユーザーは、割り当てられた音声ルーティング ポリシーを使用したLocation-Basedルーティングが有効になっていないサイトで、任意のゲートウェイを使用して発信通話を行うことができます。 ただし、ゲートウェイが Location-Based ルーティングに対して有効になっている場合、ユーザーは、音声ルーティング ポリシーに割り当てられている場合でも、ゲートウェイ経由で発信通話を行うことはできません。 ユーザーが Location-Based ルーティングが有効になっているサイトにローミングする場合、Location-Based ルーティングが有効になっていない通常のルーティング ゲートウェイを介してのみ呼び出すことができます。
 
#### <a name="user-enabled-for-location-based-routing"></a>Location-Based ルーティングに対して有効なユーザー

これに対して、Location-Based ルーティングが有効になっているユーザーの送信呼び出しのルーティングは、ユーザーのエンドポイントのネットワークの場所の影響を受けます。 次の表は、Location-Based ルーティングが、User1 の場所に応じて、User1 の送信呼び出しのルーティングにどのように影響するかを示しています。 

|User1 エンドポイントの場所  |User1 の送信呼び出しのルーティング  |
|---------|---------|
|ユーザーの DID が割り当てられているのと同じサイト、Location-Based ルーティングが有効なサイト (Site1)      |ユーザーの音声ルーティング ポリシーに基づいて、Site1 で Location-Based ルーティング (GW1) が有効になっているゲートウェイ経由でルーティングされる呼び出し         |
|ユーザーの DID が割り当てられているサイトとは異なるサイト、Location-Based ルーティングが有効なサイト (Site2)    |ユーザーの音声ルーティング ポリシーに基づいて、ローミング サイト 2 で Location-Based ルーティング (GW2) が有効になっているゲートウェイ経由でルーティングされる呼び出し        |
|ユーザーの DID が割り当てられている場所とは異なるサイト、サイトがLocation-Based ルーティングに対して有効になっていない (Site3)  |ユーザーの音声ルーティング ポリシーに基づいて、Location-Based ルーティング (GW3) が有効になっていないサイトで、Location-Based ルーティングが有効になっていないゲートウェイ経由でルーティングされる呼び出し       |
|不明な内部ネットワーク (Location4)    |  ゲートウェイに GatewayLbrEnabledUserOverride が True に設定されていない限り、PSTN 通話は許可されません       |
|不明な外部ネットワーク (Location5)    | ゲートウェイに GatewayLbrEnabledUserOverride が True に設定されていない限り、PSTN 通話は許可されません       |

### <a name="teams-user-receives-an-inbound-call-from-the-pstn"></a>Teams ユーザーが PSTN から受信通話を受信する

#### <a name="user-not-enabled-for-location-based-routing"></a>Location-Based ルーティングが有効になっていないユーザー

Location-Based ルーティングを有効にしていないユーザーは、割り当てられた DID 番号のイングレス元のLocation-Basedルーティングが有効になっていないゲートウェイから受信呼び出しを受信できます。 ユーザーが Location-Based ルーティングが有効になっていないサイトにローミングした場合でも、通常の PSTN ゲートウェイを介して通話を受信できます。
  
#### <a name="user-enabled-for-location-based-routing"></a>Location-Based ルーティングに対して有効なユーザー

これに対し、Location-Based ルーティングを有効にしたユーザーは、同じサイトに配置されている場合にのみ、DID が割り当てられている PSTN ゲートウェイからの受信通話を受信できます。 次の表は、ユーザー 1 が異なるネットワークの場所に移動したときに、ユーザー 1 が受信呼び出しを受信する方法を示しています。 通話がユーザーのエンドポイントにルーティングされていない場合、設定が構成されている場合は、ユーザーの応答のない通話転送設定に移動します。 通常、通話はボイスメールに転送されます。  

|User1 エンドポイントの場所  |ユーザー 1 への受信呼び出しのルーティング  |
|---------|---------|
|ユーザーの DID が割り当てられているサイトと同じサイト、Location-Based ルーティングが有効なサイト (Site1)   | Site1 で User1 のエンドポイントにルーティングされた呼び出し        |
|ユーザーの DID が割り当てられているサイトとは異なるサイト、Location-Based ルーティングが有効なサイト (Site2)    | Site2 のエンドポイントにルーティングされない呼び出し        |
|ユーザーの DID が割り当てられている場所とは異なるサイト、サイトがLocation-Based ルーティングに対して有効になっていない (Site3)    | Site3 のエンドポイントにルーティングされない呼び出し        |
|不明な内部ネットワーク (Location4)   | Location4 のエンドポイントにルーティングされない呼び出し        |
|不明な外部ネットワーク (Location5)     | Location5 のエンドポイントにルーティングされない呼び出し        |

### <a name="teams-user-transfers-or-forwards-call-to-another-teams-user"></a>Teams ユーザーが別の Teams ユーザーに通話を転送または転送する

PSTN エンドポイントが関係している場合、Location-Based ルーティングは、一方または両方のユーザーがLocation-Basedルーティングに対して有効になっているかどうかを分析し、両方のエンドポイントの場所に応じて通話を転送するか転送するかを決定します。 
 
通話転送では、開始ユーザーが通話を受け取る必要がありますが、通話転送では最初の呼び出しに応答する必要はありません。 着信呼び出しを受信する場所に User1 がない場合 ( [Teams ユーザーが PSTN セクションから受信通話を受信](#teams-user-receives-an-inbound-call-from-the-pstn) する表を参照)、ユーザー 1 が着信通話を受信できない場合は通話を転送できない場合でも、通話を転送できます。 

#### <a name="user-not-enabled-for-location-based-routing"></a>Location-Based ルーティングが有効になっていないユーザー

Location-Based ルーティングを有効にしていないユーザーは、Location-Based ルーティングが有効になっていない他のユーザーに PSTN 通話を転送または転送できます。 Location-Based ルーティングを有効にしているユーザーは、通常、PSTN 通話のルーティングが有効なゲートウェイLocation-Basedに併置されます。 そのため、有効になっていないユーザーは、Location-Based ルーティングが有効になっているユーザーに PSTN 通話を転送したり転送したりすることはできません。 例外は、Location-Based ルーティングが有効なユーザーが、Location-Based ルーティングが有効になっていないサイトにローミングする場合です。 このシナリオでは、転送された呼び出しが許可されます。  

同様に、Location-Based ルーティングを有効にしていないユーザーは、Location-Based ルーティングを有効にしていない別のユーザーからの転送または転送された PSTN 通話のみを受け取ることができます。 

#### <a name="user-enabled-for-location-based-routing"></a>Location-Based ルーティングに対して有効なユーザー

Location-Based ルーティングが有効になっているゲートウェイからの着信 PSTN 通話の転送と転送は、ターゲット ユーザーがLocation-Based ルーティングが有効で、同じサイトにある場合にのみ許可されます。 それ以外の場合、通話の転送と転送は許可されません。 

次の表は、ターゲット ユーザーの場所に応じて、通話転送と通話転送を許可するかどうかを示しています。 この表では、サイト 1 にある User1 は、Location-Based ルーティングも有効になっている他の Teams ユーザーと異なる場所にいる他の Teams ユーザーへの転送または転送を開始します。  

|ターゲット ユーザー エンドポイントの場所|User1 が通話転送を開始する |User1 が転送呼び出しを開始する|
|---------|---------|---------|
|イニシエーターと同じネットワーク サイト (User2)|許可|許可|
|異なるネットワーク サイト、Location-Based ルーティングが有効なサイト (User3)|許可されていません|許可されていません|
|異なるネットワーク サイト、Location-Based ルーティングに対してサイトが有効になっていない (User4)|許可されていません|許可されていません|
|不明な内部ネットワーク (User5)| 許可されていません|許可されていません|
|不明な外部ネットワーク (User6)| 許可されていません|許可されていません|

### <a name="teams-user-transfers-or-forwards-call-to-pstn-endpoint"></a>Teams ユーザーが PSTN エンドポイントに通話を転送または転送する

#### <a name="user-not-enabled-for-location-based-routing"></a>Location-Based ルーティングが有効になっていないユーザー

- PSTN 通話を別の PSTN 番号に転送および転送できます。 

- PSTN への着信 VOIP 通話の転送と転送は、発信者の有料バイパスの制限に従う必要があります。 

    - 呼び出し元がLocation-Basedルーティングに対して有効になっていない場合は、Location-Based ルーティングが有効になっていない PSTN ゲートウェイに転送できます。
    - 呼び出し元がLocation-Based ルーティングに対して有効になっている場合は、同じネットワーク サイトにあるLocation-Basedルーティングが有効なゲートウェイにのみ転送できます。 

#### <a name="user-enabled-for-location-based-routing"></a>Location-Based ルーティングに対して有効なユーザー

- PSTN 通話を別の PSTN 番号に転送および転送するには、着信通話が到着したのと同じLocation-Basedルーティングが有効なゲートウェイにルーティングする必要があります。

- PSTN への着信 VOIP 通話の転送と転送は、呼び出し元と呼び出し元ユーザーの有料バイパスの両方の制限を遵守する必要があります。 

    - 呼び出し元がLocation-Basedルーティングに対して有効になっていない場合は、Location-Based ルーティングが有効になっていない PSTN ゲートウェイに転送できます。

    - 呼び出し元が Location-Based ルーティングに対して有効になっている場合は、同じネットワーク サイトにある Location-Based ルーティングが有効なゲートウェイにのみ転送できます。
 
次の表は、Location-Based ルーティングが、Location-Based ルーティングが有効な User1 at Site1 から PSTN エンドポイントに通話を転送または転送するさまざまな場所のユーザーへの VOIP 通話のルーティングに影響を与える方法を示しています。  

|通話の転送または転送を開始するユーザー  |PSTN に転送または転送する  |
|---------|---------|
|同じネットワーク サイト、Location-Based ルーティングが有効なサイト (User2)   |結果の PSTN 通話は、User2 の音声ルーティング ポリシーに基づいて計算されたルートが Site1 でルーティングが有効なゲートウェイ 1 Location-Based経由のルートになる場合にのみ許可されます。         |
|異なるネットワーク サイト、Location-Based ルーティングが有効なサイト (User3)    |結果の PSTN 通話は、User3 の音声ルーティング ポリシーに基づいて計算されたルートが Site1 でルーティングが有効なゲートウェイ 1 Location-Based経由のルートになる場合にのみ許可されます。 |
|異なるネットワーク サイト、Location-Based ルーティングに対してサイトが有効になっていない (User4)    |結果の PSTN 通話は、User4 の音声ルーティング ポリシーに基づいて計算されたルートが Site1 でルーティングが有効なゲートウェイ 1 Location-Based経由のルートになる場合にのみ許可されます。          |
|不明な内部ネットワーク (User5)     |結果の PSTN 通話は、User5 の音声ルーティング ポリシーに基づいて計算されたルートが Site1 でルーティングが有効なゲートウェイ 1 Location-Based経由のルートになる場合にのみ許可されます。          |
|不明な外部ネットワーク (User6)   |結果の PSTN 通話は、User6 の音声ルーティング ポリシーに基づいて計算されたルートが Site1 でルーティングが有効なゲートウェイ 1 Location-Based経由のルートになる場合にのみ許可されます。          |

### <a name="simultaneous-ringing"></a>同時呼び出し

Location-Based ルーティングを有効にしたユーザーが通話を受信し、同時呼び出しが有効になっている場合、Location-Based ルーティングでは、発信側の場所と呼び出し元のエンドポイントが分析され、通話をルーティングする必要があるかどうかを判断します。 同時呼び出しは、呼び出しの転送と転送と同じLocation-Based規則に従います。 

#### <a name="simultaneous-ringing-for-another-teams-user"></a>別の Teams ユーザーの同時呼び出し音

次の表は、Location-Based ルーティングで、ユーザー 1 の受信 PSTN 通話に対して異なるユーザーへの同時呼び出しを許可するかどうかを示しています。

|ターゲット ユーザー エンドポイントの場所|同時リング  |
|---------|---------|
|イニシエーターと同じネットワーク サイト (User2)   |許可         |
|Location-Based ルーティングに対して有効になっているローミングされた別のネットワーク サイト (User3)   |許可されていません         |
|ローミングされたネットワーク サイトがLocation-Basedルーティングに対して有効になっていない (User4)   |許可されていません        |
|不明な内部ネットワーク (User5)    | 許可されていません        |
|不明な外部ネットワーク (User6)    |許可されていません        |
|ターゲット ユーザーが PSTN 番号である    |通話は、User1 の音声ルーティング ポリシーに基づいて、Site1 でルーティングが有効なゲートウェイ 1 Location-Based経由でのみルーティングできます。      |

#### <a name="simultaneous-ringing-to-a-pstn-endpoint"></a>PSTN エンドポイントへの同時呼び出し

次の表は、サイト 1 にある Location-Based ルーティングが有効なユーザー 1 から PSTN 番号に同時リングが設定されている異なる場所のユーザーへの受信 VoIP 呼び出しのルーティング動作のLocation-Basedを示しています。 

|呼び出されたユーザー エンドポイントの場所  |同時リング ターゲットは PSTN エンドポイントです |
|---------|---------|
|同じネットワーク サイト、Location-Based ルーティングが有効なサイト (User2)    |結果の PSTN 通話は、User2 の音声ルーティング ポリシーに基づいて計算されたルートが Site1 でルーティングが有効なゲートウェイ 1 Location-Based経由のルートになる場合にのみ許可されます。        |
|Location-Based ルーティングに対して有効になっている別のネットワーク サイト (User3)    |結果の PSTN 通話は、User3 の音声ルーティング ポリシーに基づいて計算されたルートが Site1 でルーティングが有効なゲートウェイ 1 Location-Based経由のルートになる場合にのみ許可されます。         |
|Location-Based ルーティングに対して異なるネットワーク サイトが有効になっていない (User4)    |結果の PSTN 通話は、User4 の音声ルーティング ポリシーに基づいて計算されたルートが Site1 でルーティングが有効なゲートウェイ 1 Location-Based経由のルートになる場合にのみ許可されます。          |
|不明な内部ネットワーク (User5)    |結果の PSTN 通話は、User5 の音声ルーティング ポリシーに基づいて計算されたルートが Site1 でルーティングが有効なゲートウェイ 1 Location-Based経由のルートになる場合にのみ許可されます。          |
|不明な外部ネットワーク (User6)   |結果の PSTN 通話は、User6 の音声ルーティング ポリシーに基づいて計算されたルートが Site1 でルーティングが有効なゲートウェイ 1 Location-Based経由のルートになる場合にのみ許可されます。          |

#### <a name="inbound-calls-through-voice-apps-auto-attendant-or-call-queue"></a>音声アプリを介した受信通話 (自動応答または通話キュー)

Location-Based ルーティングが有効なゲートウェイからの着信 PSTN 通話は、自動応答または通話キューに接続できます。 

Location-Based ルーティングを有効にしたユーザーは、着信 PSTN 通話の発信元のサイトと同じサイトに配置されている場合に、これらのアプリケーションの受信通話転送を受信することがサポートされます。
 
音声アプリ転送では、ユーザーと PSTN への通話転送と同時呼び出しが許可されます。 ターゲットへの呼び出しを完了すると、前に示したのと同じLocation-Basedルーティング規則が適用されます。  
 
ボイスメールへの転送も許可されます。  

### <a name="delegation"></a>デリゲーション

Teams ユーザーは、代理で通話を発信および受信できる代理人を選択できます。 Teams の委任機能は、次のようにLocation-Basedルーティングの影響を受ける。 

- 委任者に代わってLocation-Basedルーティングが有効なデリゲートからの送信呼び出しの場合、同じ規則が適用されます。 通話ルーティングは、代理人の通話承認ポリシー、音声ルーティング ポリシー、および場所に基づいています。 詳細については、「 [Teams ユーザーが PSTN への発信通話を発信する」を](#teams-user-places-an-outbound-call-to-the-pstn)参照してください。 

- 委任者への着信 PSTN 通話の場合、通話転送または同時に他のユーザーへの呼び出しを適用するのと同じLocation-Basedルーティング規則も代理人に適用されます。 詳細については、「 [Teams ユーザーが別の Teams ユーザーに通話を転送または転送する](#teams-user-transfers-or-forwards-call-to-another-teams-user)」、 [Teams ユーザーによる PSTN エンドポイントへの通話の転送または転送](#teams-user-transfers-or-forwards-call-to-pstn-endpoint)、および [同時呼び出しを](#simultaneous-ringing)参照してください。 代理人が PSTN エンドポイントを同時リング ターゲットとして設定すると、通話を PSTN にルーティングするために代理人の音声ルーティング ポリシーが使用されます。 

- 委任の場合、委任者と関連するデリゲートを同じネットワーク サイトに配置することをお勧めします。 

## <a name="other-planning-considerations"></a>計画に関するその他の考慮事項

### <a name="changes-from-an-on-premises-location-based-routing-deployment"></a>オンプレミス Location-Based ルーティングデプロイからの変更

ネットワーク サイトの音声ルーティング ポリシーは使用されなくなりました。 代わりに、ユーザーの音声ルーティング ポリシーを使用します。 ユーザーが他のサイトにローミングできるようにするには、音声ルーティング ポリシーにローミングされたサイトのゲートウェイを含める必要があります。 

### <a name="technical-considerations-for-location-based-routing"></a>場所に基づくルーティングに関する技術的考慮事項

IPv4 サブネットと IPv6 サブネットはサポートされていますが、一致をチェックする場合は IPv6 が優先されます。

### <a name="client-support-for-location-based-routing"></a>Location-Based ルーティングのクライアント サポート

次の Teams クライアントがサポートされています。
- Teams デスクトップ クライアント (Windows と Mac)
- Teams モバイル クライアント (iOS と Android)
- Teams IP Phone

Teams Web クライアントとSkype for Business クライアントはサポートされていません。

### <a name="capabilities-not-supported-by-location-based-routing"></a>場所に基づくルーティングでサポートされていない機能

Location-Based ルーティングは、次の種類の操作には適用されません。 Location-Based ルーティングは、Teams エンドポイントが次のシナリオで PSTN エンドポイントと対話するときに適用されません。 

- 通話保留による PSTN 通話の保留または再開 

- オンプレミスのSkype for Business ユーザーまたは Skype for Business Online ユーザーが Teams ユーザーを呼び出す  

### <a name="location-based-routing-for-conferencing"></a>会議のLocation-Basedルーティング

PSTN 通話で電話会議ライセンスのないLocation-Basedルーティングが有効なユーザーは、別のユーザーまたは PSTN 番号を使用して会議を開始することはできません。 自動応答または呼び出しキューへの接続は許可されます。

ユーザーが電話会議ライセンスを持っている場合、ユーザーは関連するユーザーと会議を開始し、会議ブリッジを介して PSTN を呼び出して電話会議を開始する必要があります。 ユーザーが既に PSTN 通話中の場合は、会議ブリッジを使用して通話をエスカレートしてダイヤルアウトすることで、別のユーザーまたは PSTN 番号を通話に追加できます。

電話会議ライセンスを持たないユーザーが開始した電話会議では、電話会議でルーティングが有効なユーザーが少なくとも 1 人いる場合、または少なくとも 1 人のLocation-Basedルーティングが有効になっている場合、PSTN 参加者の追加は許可されません。 Location-Based ルーティングが有効な参加者が通話に参加するように招待される前に、少なくとも 1 人の PSTN 参加者がこのような電話会議に参加していた場合、そのようなLocation-Basedルーティングが有効な参加者を通話に追加することはできません。

Location-Based ルーティングが有効なユーザーが、Location-Based ルーティングが有効になっていない内部サイトからの電話会議に参加している場合、上記の段落の制限は適用されません。 

電話会議のネットワーク上会議は、インドのテレフォニー機器と共に展開しないでください。

PSTN 通話でルーティングが有効なLocation-Based ユーザーは、その通話を別の呼び出しとマージすることはできません。

### <a name="media-bypass-requirement-for-location-based-routing"></a>Location-Based ルーティングのメディア バイパス要件

インドでLocation-Basedルーティングを展開する場合は、メディア バイパスも構成する必要があります。 詳細については、「[ダイレクト ルーティングを使用したメディア バイパスの計画」と「ダイレクト ルーティング用](direct-routing-plan-media-bypass.md)[のローカル メディアの最適化」を](direct-routing-media-optimization.md)参照してください。

### <a name="direct-voice-over-ip-voip"></a>Direct Voice over IP (VoIP)

Direct Voice over IP (VoIP) は、インドのテレフォニー機器と共に展開しないでください。


## <a name="related-articles"></a>関連記事

- [ダイレクト ルーティングの場所に基づくルーティングを有効にする](location-based-routing-enable.md)
- [Teams のクラウド音声機能のネットワーク設定](cloud-voice-network-settings.md)
