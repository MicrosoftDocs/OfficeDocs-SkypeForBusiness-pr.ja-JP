---
title: ダイレクト ルーティングの場所に基づくルーティングを計画する
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: roykuntz
search.appverid: MET150
description: ダイレクト ルーティングのルーティングをLocation-Basedする方法について説明します。
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: f05049cdc181aef72f9ed018f20cd8d2e3264909
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49822927"
---
# <a name="plan-location-based-routing-for-direct-routing"></a>ダイレクト ルーティングの場所に基づくルーティングを計画する

## <a name="overview-of-location-based-routing"></a>Location-Based ルーティングの概要

国や地域によっては、公衆交換電話網 (PSTN) プロバイダーをバイパスして、遠距離通話コストを削減する方法は違法です。 この記事では、地理的な場所に基Location-Basedユーザーの有料バイパスを制限するために、Microsoft Teams ルーティングを使用する方法について説明します。 この記事は、ダイレクト ルーティング電話システムにのみ適用されます。

ここでは、ルーティングの概要とLocation-Based計画に役立つガイダンスを示します。 ルーティングを適用して有効にする準備ができたら、次Location-Based参照してください。

- [ルーティングのネットワーク設定をLocation-Basedする](location-based-routing-configure-network-settings.md)
- [ダイレクト ルーティングの場所に基づくルーティングを有効にする](location-based-routing-enable.md)

> [!NOTE]
> Location-Based ルーティングは、Microsoft 365 Government Community Cloud (GCC) の高いデプロイまたは DoD デプロイでは使用できません。

Location-Based ルーティングは、着信または発信 PSTN 通話時のポリシーとユーザーの地理的な場所に基づいて、有料バイパスを制限できる機能です。 Location-Basedルーティングは、有料のバイパスを防ぐためのメカニズムを提供することを目的とします。 ユーザーの場所に基づいて PSTN 通話を動的にルーティングするメカニズムとして使用したり、意図しない結果が発生したりする可能性があります。

ユーザーがTeamsルーティングに対して有効Location-Based、次のことが適用されます。

- 発信 PSTN 通話を行う場合は、次のいずれかを満たしている必要があります。
    - ユーザーのエンドポイントは、Location-Based ルーティングが有効になっているネットワーク サイトにあり、Location-Based ルーティングに対して有効になっている対応するゲートウェイを介してエグレスを呼び出します。 
    - ユーザーのエンドポイントは、Location-Based ルーティングが有効になっていないネットワーク サイトにあり、Location-Based ルーティングが有効になっていないゲートウェイを介してエグレスを呼び出します。

    その他のシナリオでは、発信呼び出しは許可されません。

- 着信 PSTN 通話を受信するには、ユーザーの応答エンドポイントが、Location-Based ルーティングが有効になっているゲートウェイを介して通話が受信されるのと同じネットワーク サイトにある必要があります。 ユーザーがローミングしている場合など、その他のシナリオでは、通話は許可されません。また、ユーザーの通話転送設定 (通常はボイスメール) にルーティングされます。
- PSTN 通話を別の Teams ユーザーに転送するには、転送を開始するユーザーと同じネットワーク サイトにターゲット ユーザーのエンドポイントを移動する必要があります。 他のシナリオでは、転送は許可されません。 
- 別の Teams ユーザーを PSTN に転送するには、最初の呼び出し元と同じネットワーク サイトにある Location-Based ルーティングが有効なゲートウェイを介して通話を転送する必要があります。 他のシナリオでは、転送は許可されません。

Location-Basedルーティングでは、使用するネットワーク リージョン、サイト、サブネットの定義Skype for Business Serverします。 場所の有料バイパスが制限されている場合、管理者は各 IP サブネットと、その場所の各 PSTN ゲートウェイをネットワーク サイトに関連付ける。 ユーザーの場所は、PSTN 通話時にユーザーの Teams エンドポイントが接続されている IP サブネットによって決定されます。 ユーザーは複数の Teams クライアントが異なるサイトに位置している場合があります。その場合、Location-Based ルーティングでは、エンドポイントの場所に応じて各クライアントのルーティングが個別に適用されます。 

この記事で使用するネットワーク用語の一部を理解するには、「クラウド音声機能のネットワーク設定」を参照[Teams。](cloud-voice-network-settings.md)

## <a name="apply-location-based-routing"></a>ルーティングLocation-Based適用する

ユーザー、ネットワーク Location-Based PSTN ゲートウェイにルーティングを適用する必要があります。  

### <a name="apply-location-based-routing-at-the-user-location"></a>ユーザーLocation-Basedにルーティングを適用する

前述のように、Location-Basedルーティングは、直接ルーティング用に設定されているユーザーにのみ適用されます。 Location-Basedルーティングは、通話プランに設定されているユーザーには適用されません。 ユーザーが有料のバイパス制限を受ける場合、ユーザーは Location-Based ルーティングを有効にする必要があります。この制限により、PSTN 通話を発信および受信できる条件と、使用できる PSTN ゲートウェイが制御されます。 Location-Based ルーティングが有効になっているユーザーが Location-Based ルーティングが有効なサイトにある場合、ユーザーはサイトに接続されている Location-Based ルーティングが有効なゲートウェイを介して呼び出しを行う必要があります。 

Location-Basedルーティングは、ユーザーの Teams エンドポイントの IP アドレスに基づいてユーザーの現在の場所を決定することで機能し、規則を適切に適用します。 ルーティングを有効にしているユーザーのLocation-Basedは、次の方法で分類できます。 
- **ユーザーは、DID が割り当Location-Based PSTN ゲートウェイに関連付けられているルーティングが有効なサイトと同じ場所にあります。**<br>このシナリオでは、ユーザーは Location-Based ルーティングが有効になっている既知のネットワーク サイトにあり、ユーザーの直接の内向きダイヤル (DID) 番号は、同じネットワーク サイト内にある PSTN ゲートウェイで終了します。 たとえば、ユーザーは自分のオフィスにいます。 
- **ユーザーは、DID が割り当Location-Based PSTN ゲートウェイに関連付けられていないルーティングが有効なサイトの別の場所にあります。**<br>このシナリオでは、ユーザーは Location-Based ルーティングが有効になっている既知のネットワーク サイトにあり、そのサイトはユーザーの DID 番号が割り当てられている PSTN ゲートウェイに関連付けられていません。 たとえば、ユーザーは別のオフィスに移動します。  
- **ユーザーは、ルーティングを有効にしていない内部サイトにLocation-Basedされます。** <br>このシナリオでは、ユーザーは、ルーティングを有効にしていない既知の内部ネットワーク サイトLocation-Basedされます。 
- **ユーザーは不明なサイトにあります。** 
    - ユーザーは、ネットワーク サイトとして定義されていない内部ネットワーク内にあります。 
    - ユーザーは内部ネットワークの外部に位置しています。 たとえば、ユーザーは自宅やコーヒー ショップでインターネットに接続しています。 

### <a name="apply-location-based-routing-at-the-network-site"></a>ネットワーク Location-Basedルーティングを適用する 
ローミング時にルーティングが有効になっているLocation-Basedルーティングするゲートウェイを決定するには、ネットワーク Location-Basedを有効にする必要があります。 Location-Based ルーティングが有効になっているユーザーが Location-Based ルーティングが有効になっているサイトにローミングする場合、そのサイトで Location-Based ルーティングが有効になっている PSTN ゲートウェイのみを発信呼び出しに使用できます。 Location-Based ルーティングが有効になっているユーザーが、Location-Based ルーティングが有効になっていないサイトにローミングする場合は、Location-Based ルーティングが有効になっていないゲートウェイを発信呼び出しに使用できます。  

### <a name="apply-location-based-routing-at-the-pstn-gateway"></a>PSTN Location-Basedルーティングを適用する 

ゲートウェイはサイトに関連付けられるので、PSTN 通話を発信または受信するときに、Location-Based ルーティングが有効になっているユーザーを特定できます。 ゲートウェイを Location-Based ルーティングに対して有効にする必要があります。これにより、ゲートウェイが有料バイパス制限を受け、Location-Based ルーティングが有効になっていないユーザーは使用できません。 同じゲートウェイを複数のサイトに関連付け、Location-Based ルーティングに対して有効にするか、サイトに応じて Location-Based ルーティングが有効になっていないことを構成できます。

## <a name="scenarios-for-location-based-routing"></a>場所に基づくルーティングのシナリオ

このセクションでは、Location-Based ルーティングを使用して有料バイパスを制限するさまざまなシナリオについて説明し、Location-Based ルーティングが有効になっていないユーザーの呼び出しのルーティング方法と、Location-Based ルーティングが有効になっているユーザーを比較します。

- [Teamsユーザーが PSTN への発信通話を発信する](#teams-user-places-an-outbound-call-to-the-pstn)
- [Teams PSTN から受信通話を受信する](#teams-user-receives-an-inbound-call-from-the-pstn)
- [Teamsユーザーが別のユーザーに通話を転送Teamsする](#teams-user-transfers-or-forwards-call-to-another-teams-user)
- [Teams PSTN エンドポイントへの通話の転送または転送を行う](#teams-user-transfers-or-forwards-call-to-pstn-endpoint)
- [同時呼び出し](#simultaneous-ringing)
- [デリゲーション](#delegation)

次の図は、各シナリオでルーティングをLocation-Based制限を示しています。 ルーティングが有効になっているユーザー、ネットワーク サイト、ゲートウェイLocation-Based、その周囲に境界があります。 この図をガイドとして使用すると、各シナリオでのルーティングのLocation-Based理解するのに役立ちます。  

![ルーティングのシナリオを示Location-Based図](media/lbr-direct-routing.png "ルーティングのシナリオを示Location-Based図")

### <a name="teams-user-places-an-outbound-call-to-the-pstn"></a>Teamsユーザーが PSTN への発信通話を発信する

#### <a name="user-not-enabled-for-location-based-routing"></a>ユーザーがルーティングに対してLocation-Basedしない

Location-Based ルーティングが有効になっていないユーザーは、割り当てられた音声ルーティング ポリシーを介して Location-Based ルーティングが有効になっていない任意のサイトで、任意のゲートウェイを使用して発信通話を行います。 ただし、ゲートウェイが Location-Based ルーティングに対して有効になっている場合、ユーザーは、音声ルーティング ポリシーに割り当てられている場合でも、ゲートウェイを介して発信呼び出しを行う必要があります。 ユーザーが Location-Based ルーティングが有効になっているサイトにローミングする場合、ユーザーは、Location-Based ルーティングに対して有効になっていない通常のルーティング ゲートウェイを介した通話のみを行います。
 
#### <a name="user-enabled-for-location-based-routing"></a>ユーザーがルーティングをLocation-Based
一方、Location-Based ルーティングが有効になっているユーザーの発信呼び出しのルーティングは、ユーザーのエンドポイントのネットワークの場所の影響を受ける。 次の表は、Location-Basedの場所に応じて、User1 の送信呼び出しのルーティングに影響する方法を示しています。 

|User1 エンドポイントの場所  |User1 の送信呼び出しのルーティング  |
|---------|---------|
|ユーザーの DID が割り当てられているのと同じサイトで、Location-Basedルーティングが有効になっている (Site1)      |ユーザーの音声ルーティング ポリシーに基づいて、Site1 で Location-Based ルーティング (GW1) が有効になっているゲートウェイ経由でルーティングされた通話         |
|ユーザーの DID が割り当てられているサイトとは異なる、ルーティング (Site2) Location-Basedサイトが有効になっている    |ユーザーの音声ルーティング ポリシーに基づいて、ローミング サイト 2 で Location-Based ルーティング (GW2) が有効になっているゲートウェイ経由でルーティングされた通話        |
|ユーザーの DID が割り当てられているサイトとは異なる、サイトが Location-Based ルーティングに対して有効になっていない (Site3)  |ユーザーの音声ルーティング ポリシーに基づいて、Location-Based ルーティング (GW3) が有効になっていないサイトで Location-Based ルーティングが有効になっていないゲートウェイ経由でルーティングされた通話       |
|不明な内部ネットワーク (Location4)    |  PSTN 通話が許可されていない       |
|不明な外部ネットワーク (Location5)    | PSTN 通話が許可されていない        |

### <a name="teams-user-receives-an-inbound-call-from-the-pstn"></a>Teams PSTN から受信通話を受信する

#### <a name="user-not-enabled-for-location-based-routing"></a>ユーザーがルーティングに対してLocation-Basedしない

Location-Based ルーティングが有効になっていないユーザーは、割り当てられた DID 番号が受信される Location-Based ルーティングが有効になっていないゲートウェイから受信呼び出しを受信できます。 ユーザーが Location-Based ルーティングが有効になっていないサイトにローミングした場合でも、通常の PSTN ゲートウェイ経由で通話を受信できます。
  
#### <a name="user-enabled-for-location-based-routing"></a>ユーザーがルーティングをLocation-Based

一方、Location-Based ルーティングが有効になっているユーザーは、DID が割り当てられている PSTN ゲートウェイからの受信通話を同じサイトに存在する場合にのみ受信できます。 次の表は、User1 が別のネットワークの場所に移動するときに、User1 が受信呼び出しを受信する方法を示しています。 呼び出しがユーザーのエンドポイントにルーティングされていない場合、設定が構成されている場合は、ユーザーの呼び出し転送設定に移動します。 通常、これはボイスメールです。  

|User1 エンドポイントの場所  |User1 への受信呼び出しのルーティング  |
|---------|---------|
|ユーザーの DID が割り当てられているのと同じサイトで、Location-Based ルーティングが有効になっている (Site1)   | Site1 で User1 のエンドポイントにルーティングされた呼び出し        |
|ユーザーの DID が割り当てられているサイトとは異なる、ルーティング (Site2) Location-Basedサイトが有効になっている    | Site2 のエンドポイントにルーティングされない呼び出し        |
|ユーザーの DID が割り当てられているサイトとは異なる、サイトが Location-Based ルーティングに対して有効になっていない (Site3)    | Site3 のエンドポイントにルーティングされない呼び出し        |
|不明な内部ネットワーク (Location4)   | Location4 のエンドポイントにルーティングされない呼び出し        |
|不明な外部ネットワーク (Location5)     | Location5 のエンドポイントにルーティングされない呼び出し        |

### <a name="teams-user-transfers-or-forwards-call-to-another-teams-user"></a>Teamsユーザーが別のユーザーに通話を転送Teamsする

PSTN エンドポイントが関与する場合、Location-Based ルーティングは、一方または両方のユーザーが Location-Based ルーティングに対して有効になっているかどうかを分析し、両方のエンドポイントの場所に応じて通話を転送するか転送する必要かを決定します。 
 
通話転送では、開始ユーザーが通話を受け取る必要があります。通話の転送では、最初の通話に応答する必要はありません。 つまり[、User1](#teams-user-receives-an-inbound-call-from-the-pstn)が着信呼び出しを受信する場所にいなくても、呼び出しを転送できます (Teams ユーザーが PSTN セクションから受信通話を受信する表を参照してください)、User1 が着信通話を受信できない場合、通話を転送できません。 

#### <a name="user-not-enabled-for-location-based-routing"></a>ユーザーがルーティングに対してLocation-Basedしない

ルーティングが有効になっていないユーザーはLocation-Basedルーティングが有効になっていない他のユーザーに PSTN 通話を転送Location-Basedできます。 Location-Based ルーティングが有効なユーザーは通常、PSTN 通話に対して Location-Based ルーティングが有効なゲートウェイにのみ同じ場所に移動できるので、ユーザーは通常、Location-Based ルーティングが有効になっているユーザーに PSTN 通話を転送または転送することはできません。 例外は、ルーティングが有効Location-Basedユーザーが、ルーティングを有効にしていないサイトにローミングLocation-Basedです。 このシナリオでは、転送された呼び出しが許可されます。  

同様に、Location-Based ルーティングが有効になっていないユーザーは、Location-Based ルーティングが有効になっていない別のユーザーからの転送または転送された PSTN 通話のみを受信できます。 

#### <a name="user-enabled-for-location-based-routing"></a>ユーザーがルーティングをLocation-Based

一般に、Location-Based ルーティングが有効になっているゲートウェイからの着信 PSTN 通話の転送と転送は、ターゲット ユーザーが Location-Based ルーティングを有効にし、同じサイトにある場合にのみ許可されます。 それ以外の場合、通話の転送と転送は許可されません。 

次の表は、ターゲット ユーザーの場所に応じて、呼び出しの転送と通話転送を許可するかどうかを示しています。 この表では、Site1 にある User1 によって、Location-Based ルーティングが有効になっている他の Teams ユーザーと異なる場所にあるユーザーへの転送または転送が開始されます。  

|ターゲット ユーザー エンドポイントの場所|User1 が通話転送を開始する |User1 が呼び出し転送を開始する|
|---------|---------|---------|
|イニシエーターと同じネットワーク サイト (User2)|許可|許可|
|異なるネットワーク サイト、Location-Based ルーティングが有効 (User3)|許可されない|許可されない|
|異なるネットワーク サイト、サイトが Location-Based ルーティングに対して有効になっていない (User4)|許可されない|許可されない|
|不明な内部ネットワーク (User5)| 許可されない|許可されない|
|不明な外部ネットワーク (User6)| 許可されない|許可されない|

### <a name="teams-user-transfers-or-forwards-call-to-pstn-endpoint"></a>Teams PSTN エンドポイントへの通話の転送または転送を行う

#### <a name="user-not-enabled-for-location-based-routing"></a>ユーザーがルーティングに対してLocation-Basedしない

- PSTN 通話を別の PSTN 番号に転送および転送できます。 
- 着信 VOIP 通話を PSTN に転送および転送するには、発信者の有料バイパス制限を尊重する必要があります。 
    - 呼び出し元が Location-Based ルーティングに対して有効になっていない場合、呼び出し元をルーティングに対して有効になっていない PSTN ゲートウェイLocation-Basedできます。
    - 呼び出し元が Location-Based ルーティングに対して有効になっている場合は、同じネットワーク サイトにある Location-Based ルーティングが有効なゲートウェイにのみ転送できます。 

#### <a name="user-enabled-for-location-based-routing"></a>ユーザーがルーティングをLocation-Based

- PSTN 通話を別の PSTN 番号に転送および転送するには、着信通話が到着したLocation-Basedルーティングが有効なゲートウェイからルーティングする必要があります。 
- PSTN への着信 VOIP 通話の転送と転送は、発信者と呼び出されたユーザーの有料バイパス制限の両方を尊重する必要があります。 
    - 呼び出し元が Location-Based ルーティングに対して有効になっていない場合、呼び出し元をルーティングに対して有効になっていない PSTN ゲートウェイLocation-Basedできます。
    - 呼び出し元が Location-Based ルーティングに対して有効になっている場合は、同じネットワーク サイトにある Location-Based ルーティングが有効なゲートウェイにのみ転送できます。
 
次の表は、Location-Based ルーティングが、通話を PSTN エンドポイントに転送または転送するさまざまな場所のユーザーに対する、Site1 の User1 からの VOIP 通話のルーティングに及ぼす影響を示しています。  

|ユーザーが通話の転送または転送を開始する  |PSTN への転送  |PSTN に転送する  |
|---------|---------|---------|
|同じネットワーク サイト、Location-Based ルーティングが有効 (User2)   |通話転送は、User2 の音声ルーティング ポリシーLocation-Based基づいて、Site1 でルーティングが有効になっている Gateway1 経由でのみルーティングできます。         |コールフォワードは、User2 の音声ルーティング ポリシーLocation-Based基づいて、Site1 でルーティングが有効な Gateway1 経由でのみルーティングできます。         |
|異なるネットワーク サイト、Location-Based ルーティングが有効 (User3)    |通話転送は、User3 の音声ルーティング ポリシーLocation-Based基づいて、Site1 でルーティングが有効な Gateway1 経由でのみルーティングできます。         |コールフォワードは、User3 の音声ルーティング ポリシーLocation-Based基づいて、Site1 でルーティングが有効な Gateway1 経由でのみルーティングできます。         |
|異なるネットワーク サイト、サイトが Location-Based ルーティングに対して有効になっていない (User4)    |通話転送は、User4 の音声ルーティング ポリシーLocation-Based基づいて、Site1 でルーティングが有効な Gateway1 経由でのみルーティングできます。         |コールフォワードは、User4 の音声ルーティング ポリシーLocation-Based基づいて、Site1 でルーティングが有効な Gateway1 経由でのみルーティングできます。         |
|不明な内部ネットワーク (User5)     |通話転送は、User5 の音声ルーティング ポリシーLocation-Based基づいて、Site1 でルーティングが有効な Gateway1 経由でのみルーティングできます。         |コールフォワードは、User5 の音声ルーティング ポリシーLocation-Based基づいて、Site1 でルーティングが有効な Gateway1 経由でのみルーティングできます。         |
|不明な外部ネットワーク (User6)   |通話転送は、User6 の音声ルーティング ポリシーLocation-Based基づいて、Site1 でルーティングが有効な Gateway1 経由でのみルーティングできます。        |コールフォワードは、User6 の音声ルーティング ポリシーLocation-Based基づいて、Site1 でルーティングが有効な Gateway1 経由でのみルーティングできます。         |

### <a name="simultaneous-ringing"></a>同時呼び出し

Location-Based ルーティングを有効にしたユーザーが通話を受信し、同時呼び出しが有効になっている場合、Location-Based Routing は通話相手の場所と呼び出し元のエンドポイントを分析して、呼び出しをルーティングするかどうかを決定します。 同時呼び出しは、通話Location-Based転送と同じルールに従います。 

#### <a name="simultaneous-ringing-for-another-teams-user"></a>別のユーザーの同時呼びTeams呼び出し

次の表は、User1 Location-Based PSTN 通話に対して異なるユーザーへの同時呼び出しを許可するかどうかを示しています。

|ターゲット ユーザー エンドポイントの場所|同時呼び出し  |
|---------|---------|
|イニシエーターと同じネットワーク サイト (User2)   |許可         |
|ルーティング (User3) で有効Location-Based異なるローミング されたネットワーク サイト   |許可されない         |
|ローミングされたネットワーク サイトがルーティングに対してLocation-Based (User4)   |許可されない        |
|不明な内部ネットワーク (User5)    | 許可されない        |
|不明な外部ネットワーク (User6)    |許可されない        |
|ターゲット ユーザーが PSTN 番号である    |通話は、User1 の音声ルーティング ポリシーLocation-Based基づいて、Site1 でルーティングが有効な Gateway1 経由でのみルーティングできます。      |

#### <a name="simultaneous-ringing-to-a-pstn-endpoint"></a>PSTN エンドポイントへの同時呼び出し

次の表は Location-Based、Site1 にある User1 から PSTN 番号に同時呼び出しが設定された別の場所のユーザーへの受信 VOIP 通話のルーティング動作を示しています。 

|呼び出されたユーザー エンドポイントの場所  |同時呼び出し先は PSTN エンドポイント |
|---------|---------|
|同じネットワーク サイト、Location-Based ルーティングが有効 (User2)    |通話は、User2 の音声ルーティング ポリシーLocation-Based基づいて、Site1 のルーティング ゲートウェイ 1 経由でのみルーティングできます。       |
|ルーティング (User3) でLocation-Based異なるネットワーク サイト    |通話は、User3 の音声ルーティング ポリシーLocation-Based基づいて、Site1 のルーティング ゲートウェイ 1 経由でのみルーティングできます。        |
|ネットワーク ルーティング (User4) に対してLocation-Based異なるネットワーク サイト    |通話は、User4 の音声ルーティング ポリシーLocation-Based基づいて、Site1 のルーティング ゲートウェイ 1 経由でのみルーティングできます。         |
|不明な内部ネットワーク (User5)    |通話は、User5 の音声ルーティング ポリシーLocation-Based基づいて、Site1 のルーティング ゲートウェイ 1 経由でのみルーティングできます。         |
|不明な外部ネットワーク (User6)   |通話は、User6 の音声ルーティング ポリシーLocation-Based基づいて、Site1 のルーティング ゲートウェイ 1 経由でのみルーティングできます。         |

#### <a name="inbound-calls-through-voice-app-auto-attendant-or-call-queue"></a>音声アプリを介した着信通話 (自動応答 または通話キュー)

ルーティングが有効なゲートウェイLocation-Based着信 PSTN 通話は、自動応答または通話キューに接続できます。 Location-Based ルーティングが有効になっているユーザーは、受信 PSTN 通話の発信元と同じサイトに存在する場合にのみ、これらのアプリケーションからの着信通話転送を受信できます。 
 
ユーザーへの通話の転送と同時呼び出しと PSTN による音声アプリ転送が許可されます。 ターゲットへの呼び出しを完了するには、前に示したルーティング Location-Based同じ規則が適用されます。  
 
ボイスメールへの転送も許可されます。  

### <a name="delegation"></a>デリゲーション

ユーザー Teams、代理で通話を行って受信できる代理人を選択できます。 次のように、Teamsの委任機能は、Location-Basedルーティングの影響を受けます。 
- 委任者に代わってLocation-Basedルーティングが有効な代理人からの発信呼び出しの場合は、同じ規則が適用されます。 通話ルーティングは、代理人の通話承認ポリシー、音声ルーティング ポリシー、および場所に基づいて行います。 詳細については、「ユーザーが[PSTN Teams発信通話を発信する」を参照してください](#teams-user-places-an-outbound-call-to-the-pstn)。 
- 委任者への着信 PSTN 通話の場合、着信の転送または他のユーザーへの同時呼び出しに適用される同じ Location-Based ルーティング規則も代理人に適用されます。 詳細については、「Teams[ユーザー](#teams-user-transfers-or-forwards-call-to-another-teams-user)による別の Teams ユーザーへの呼び出しの転送または転送[」、pstn](#teams-user-transfers-or-forwards-call-to-pstn-endpoint)エンドポイントへの Teams ユーザー転送または転送呼び出し、および同時呼び出しに関するページを参照[してください。](#simultaneous-ringing) 代理人が PSTN エンドポイントを同時呼び出し先として設定すると、通話を PSTN にルーティングするために代理人の音声ルーティング ポリシーが使用されます。 
- 委任の場合は、委任者と関連付けられている代理人を同じネットワーク サイトに位置付けることです。 

## <a name="other-planning-considerations"></a>計画に関するその他の考慮事項

### <a name="changes-from-an-on-premises-location-based-routing-deployment"></a>オンプレミスのルーティング デプロイからのLocation-Based変更

ネットワーク サイト音声ルーティング ポリシーは使用されなくなりました。 代わりに、ユーザーの音声ルーティング ポリシーを使用します。 つまり、ユーザーが他のサイトにローミングするには、音声ルーティング ポリシーにローミングされたサイトのゲートウェイを含める必要があります。 

### <a name="technical-considerations-for-location-based-routing"></a>場所に基づくルーティングに関する技術的考慮事項

IPv4 サブネットと IPv6 サブネットがサポートされています。ただし、一致を確認する場合は IPv6 が優先されます。

### <a name="client-support-for-location-based-routing"></a>Location-Based ルーティングのクライアント サポート

次のTeamsクライアントがサポートされています。
- Teams クライアント (Windows Mac)
- Teams クライアント (iOS および Android)
- TeamsIP 電話

Web TeamsクライアントとSkype for Businessクライアントはサポートされていません。

### <a name="capabilities-not-supported-by-location-based-routing"></a>場所に基づくルーティングでサポートされていない機能

Location-Basedルーティングは、次の種類の対話には適用されません。 Location-Basedのシナリオでは、TEAMSエンドポイントが PSTN エンドポイントとやり取りする場合、ルーティングは適用されません。 
- 通話保留による PSTN 通話の保留または再開 
- オンプレミスのユーザーまたは Skype for Business Online ユーザーがSkype for Businessユーザーを呼び出Teamsします  

### <a name="location-based-routing-for-conferencing"></a>Location-Basedルーティング

PSTN Location-Basedルーティングが有効なユーザーは、別のユーザーまたは PSTN 番号との会議を開始できません。 自動応答または通話キューへの接続が許可されます。 ユーザーが会議ライセンスを持つ場合、ユーザーは関連するユーザーとの会議を開始し、会議ブリッジを介して PSTN を呼び出して電話会議を開始する必要があります。  

### <a name="media-bypass-requirement-for-location-based-routing"></a>Location-Based ルーティングのメディア バイパス要件

インドでルーティングをLocation-Basedする場合は、メディア バイパスも構成する必要があります。 詳細については、「ダイレクト ルーティングを使用したメディア [バイパスの](direct-routing-plan-media-bypass.md) 計画」と「直接ルーティングのための [ローカル メディアの最適化」を参照してください](direct-routing-media-optimization.md)。

### <a name="direct-voice-over-ip-voip"></a>Direct Voice over IP (VoIP)

インドでは、ダイレクト ボイス オーバー IP (VoIP) をテレフォニー機器と一緒にデプロイしなけい。

## <a name="next-steps"></a>次の手順

ルーティングの [ネットワーク設定の構成に関するLocation-Based進む](location-based-routing-configure-network-settings.md)。

## <a name="related-topics"></a>関連トピック

- [ダイレクト ルーティングの場所に基づくルーティングを有効にする](location-based-routing-enable.md)
- [Teams のクラウド音声機能のネットワーク設定](cloud-voice-network-settings.md)
