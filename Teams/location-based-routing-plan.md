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
description: 直接ルーティングのルーティングLocation-Basedする方法について説明します。
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

## <a name="overview-of-location-based-routing"></a>グループ ルーティングLocation-Based概要

国や地域によっては、公衆交換電話網 (PSTN) プロバイダーをバイパスして、長距離通話コストを削減する方法は違法です。 この記事では、地理的な場所に基づいて、Location-Based ルーティングを使用して、Microsoft Teams ユーザーの有料バイパスを制限する方法について説明します。 この記事は、電話システム ダイレクト ルーティングにのみ適用されます。

ここでは、ルーティングの概要とLocation-Basedに役立つガイダンスを示します。 自動ルーティングを適用して有効にする準備ができたらLocation-Basedを参照してください。

- [ルーティングのネットワーク設定をLocation-Basedする](location-based-routing-configure-network-settings.md)
- [ダイレクト ルーティングの場所に基づくルーティングを有効にする](location-based-routing-enable.md)

> [!NOTE]
> Location-Basedルーティングは、Microsoft 365 Government Community Cloud (GCC) High または DoD 展開では利用できません。

Location-Basedルーティングは、着信または発信 PSTN 通話の時点でのポリシーとユーザーの地理的な場所に基づいて有料バイパスを制限できる機能です。 Location-Basedルーティングは、有料バイパスを防止するメカニズムを提供することを目的としています。 ユーザーの場所に基づいて PSTN 通話を動的にルーティングするメカニズムとして使用したり、意図しない結果が発生したりする可能性があります。

Teams ユーザーが新しいルーティングを有効Location-Based、次の条件が適用されます。

- 発信 PSTN 通話を行う場合は、次のいずれかを満たしている必要があります。
    - ユーザーのエンドポイントは、Location-Based ルーティングが有効になっているネットワーク サイトにあり、Location-Based ルーティングに対して有効になっている対応するゲートウェイを経由して出口を呼び出します。 
    - ユーザーのエンドポイントは、Location-Based ルーティングが有効になっていないネットワーク サイトにあり、Location-Based Location-Based ルーティングが有効になっていないゲートウェイを経由して出口を呼び出します。

    その他のシナリオでは、発信通話は許可されません。

- 受信 PSTN 通話を受信するには、ユーザーの応答エンドポイントが、Location-Based ルーティングに対して有効になっているゲートウェイを経由して通話が入るのと同じネットワーク サイトに位置している必要があります。 ユーザーがローミングしている場合など、その他のシナリオでは、通話は許可されません。また、ユーザーの通話転送設定 (通常はボイスメール) にルーティングされます。
- PSTN 通話を別の Teams ユーザーに転送するには、ターゲット ユーザーのエンドポイントが、転送を開始するユーザーと同じネットワーク サイトにある必要があります。 その他のシナリオでは、転送は許可されません。 
- 別の Teams ユーザーを PSTN に転送するには、通話を最初の呼び出し元と同じネットワーク サイトにある Location-Based ルーティングが有効なゲートウェイを介して転送する必要があります。 その他のシナリオでは、転送は許可されません。

Location-Basedルーティングでは、Skype for Business Server と同じネットワーク領域、サイト、サブネットの定義が使用されます。 場所の有料バイパスが制限されている場合、管理者は、その場所の各 IP サブネットと各 PSTN ゲートウェイをネットワーク サイトに関連付けします。 ユーザーの場所は、ユーザーの Teams エンドポイントが PSTN 通話時に接続されている IP サブネットによって決定されます。 ユーザーが異なるサイトに複数の Teams クライアントを持つ場合があります。その場合、Location-Based Routing はエンドポイントの場所に応じて各クライアントのルーティングを個別に適用します。 

この記事で使用されるネットワーク用語の一部を理解するには、Teams のクラウド音声機能のネットワーク設定 [を参照してください](cloud-voice-network-settings.md)。

## <a name="apply-location-based-routing"></a>ルーティングLocation-Based適用する

ユーザー、ネットワーク Location-Based PSTN ゲートウェイにルーティングを適用する必要があります。  

### <a name="apply-location-based-routing-at-the-user-location"></a>ユーザーLocation-Basedにルーティングを適用する

前述のように、Location-Basedは、直接ルーティング用に設定されているユーザーにのみ適用されます。 Location-Basedは、通話プランを設定しているユーザーには適用されません。 ユーザーは、PSTN 通話を発信および受信できる条件と、使用できる PSTN ゲートウェイを制御する有料バイパス制限下にある場合、Location-Based ルーティングを有効にする必要があります。 Location-Based ルーティングが有効になっているユーザーが Location-Based ルーティングが有効なサイトにある場合、ユーザーはサイトに接続されている Location-Based ルーティングが有効なゲートウェイを介して通話を行う必要があります。 

Location-Basedルーティングは、ユーザーの Teams エンドポイントの IP アドレスに基づいてユーザーの現在の場所を特定することで機能し、ルールを適切に適用します。 グループ ルーティングが有効になっているユーザーのLocation-Based、次の方法で分類できます。 
- **ユーザーは、DID が割り当Location-Based PSTN ゲートウェイに関連付けられているルーティングが有効なサイトと同じ場所にあります。**<br>このシナリオでは、ユーザーは Location-Based ルーティングが有効になっている既知のネットワーク サイトにあり、ユーザーの直接ダイヤル (DID) 番号は、同じネットワーク サイトにある PSTN ゲートウェイで終了します。 たとえば、ユーザーが自分のオフィスにいます。 
- **ユーザーは、ルーティングが有効なサイトLocation-Based DID が割り当てられている PSTN ゲートウェイに関連付けられていない別の場所にあります。**<br>このシナリオでは、ユーザーは Location-Based ルーティングが有効になっている既知のネットワーク サイトにあり、そのサイトはユーザーの DID 番号が割り当てられている PSTN ゲートウェイに関連付けられていません。 たとえば、ユーザーは別のオフィスに出張します。  
- **ユーザーは内部サイトにあり、このサイトではルーティングをLocation-Basedできません。** <br>このシナリオでは、ユーザーは既知の内部ネットワーク サイトにあり、このサイトのネットワーク ルーティングがLocation-Basedされます。 
- **ユーザーは不明なサイトにあります。** 
    - ユーザーは、ネットワーク サイトとして定義されていない内部ネットワーク内にあります。 
    - ユーザーは内部ネットワークの外部に位置しています。 たとえば、ユーザーは自宅や喫茶店でインターネットに接続しています。 

### <a name="apply-location-based-routing-at-the-network-site"></a>ネットワーク Location-Basedルーティングを適用する 
ローミング時にルーティングが有効Location-Basedをルーティングするゲートウェイを決定するには、ネットワーク Location-Based有効にする必要があります。 Location-Based ルーティングが有効になっているユーザーが Location-Based ルーティングが有効なサイトにローミングする場合、そのサイトで Location-Based ルーティングに対して有効になっている PSTN ゲートウェイのみを発信通話に使用できます。 Location-Based ルーティングが有効になっているユーザーが Location-Based ルーティングが有効になっていないサイトにローミングする場合、Location-Based ルーティングに対して有効になっていないゲートウェイを発信通話に使用できます。  

### <a name="apply-location-based-routing-at-the-pstn-gateway"></a>PSTN Location-Basedルーティングを適用する 

ゲートウェイはサイトに関連付けられているので、PSTN 通話を発信または受信するときに、Location-Based ルーティングが有効になっているユーザーがどこにアクセスできるのか判断します。 ゲートウェイが Location-Based ルーティングに対して有効になっている必要があります。これは、ゲートウェイが有料バイパスの制限を受け、Location-Based ルーティングが有効になっていないユーザーが使用することはできません。 同じゲートウェイが複数のサイトに関連付けられている場合があります。また、サイトによっては、Location-Based ルーティングを有効にするか、Location-Based ルーティングに対して有効になっていないことを構成できます。

## <a name="scenarios-for-location-based-routing"></a>場所に基づくルーティングのシナリオ

このセクションでは、Location-Based ルーティングを使用して有料バイパスを制限するさまざまなシナリオについて説明し、Location-Based ルーティングが有効になっているユーザーと Location-Based ルーティングが有効になっていないユーザーの通話のルーティング方法を比較します。

- [Teams ユーザーが PSTN に発信通話を発信する](#teams-user-places-an-outbound-call-to-the-pstn)
- [Teams ユーザーが PSTN から受信通話を受信する](#teams-user-receives-an-inbound-call-from-the-pstn)
- [Teams ユーザーが通話を別の Teams ユーザーに転送または転送する](#teams-user-transfers-or-forwards-call-to-another-teams-user)
- [Teams ユーザーが PSTN エンドポイントに通話を転送または転送する](#teams-user-transfers-or-forwards-call-to-pstn-endpoint)
- [同時呼び出し](#simultaneous-ringing)
- [デリゲーション](#delegation)

次の図は、各シナリオでのルーティングのLocation-Basedを示しています。 ルーティングが有効になっているユーザー、ネットワーク サイト、Location-Based、ゲートウェイの周囲に罫線が表示されます。 図をガイドとして使用すると、各シナリオでのルーティングLocation-Based理解するのに役立ちます。  

![ネットワーク ルーティングのシナリオをLocation-Based図](media/lbr-direct-routing.png "ネットワーク ルーティングのシナリオをLocation-Based図")

### <a name="teams-user-places-an-outbound-call-to-the-pstn"></a>Teams ユーザーが PSTN に発信通話を発信する

#### <a name="user-not-enabled-for-location-based-routing"></a>ユーザーがルーティングをLocation-Basedされていない

Location-Based ルーティングが有効になっていないユーザーは、割り当てられた音声ルーティング ポリシーを通じて Location-Based ルーティングが有効になっていないサイトで、任意のゲートウェイを使用して発信通話を行います。 ただし、ゲートウェイが Location-Based ルーティングに対して有効になっている場合、ユーザーは、音声ルーティング ポリシーに割り当てられている場合でも、ゲートウェイを介して発信通話を発信することはできません。 ユーザーが Location-Based ルーティングが有効なサイトにローミングした場合、ユーザーは Location-Based ルーティングに対して有効になっていない通常のルーティング ゲートウェイを介してのみ通話を行います。
 
#### <a name="user-enabled-for-location-based-routing"></a>ユーザーがルーティングをLocation-Based
一方、Location-Based ルーティングが有効になっているユーザーの発信通話のルーティングは、ユーザーのエンドポイントのネットワークの場所の影響を受ける。 次の表は、User1 のLocation-Basedに応じて、ユーザー 1 の送信通話のルーティングに対するルーティングの影響を示しています。 

|User1 エンドポイントの場所  |User1 の送信通話のルーティング  |
|---------|---------|
|ユーザーの DID が割り当てられているのと同じサイトで、Location-Basedルーティングが有効になっている (サイト 1)      |ユーザーの音声ルーティング ポリシーに基づいて、Site1 Location-Based ルーティング (GW1) に対して有効になっているゲートウェイを介してルーティングされる通話         |
|ユーザーの DID が割り当てられているサイトとは異なる、サイトがルーティングに対してLocation-Based (Site2)    |ユーザーの音声ルーティング ポリシーに基づいて、ローミング サイト 2 で Location-Based ルーティング (GW2) が有効になっているゲートウェイ経由でルーティングされた通話        |
|ユーザーの DID が割り当てられているサイトとは異なる、サイトがルーティングに対してLocation-Based (Site3)  |ユーザーの音声ルーティング ポリシーに基づいて、Location-Based ルーティング (GW3) が有効になっていないサイトで Location-Based ルーティングが有効になっていないゲートウェイ経由でルーティングされた通話       |
|不明な内部ネットワーク (Location4)    |  PSTN 通話が許可されていない       |
|不明な外部ネットワーク (Location5)    | PSTN 通話が許可されていない        |

### <a name="teams-user-receives-an-inbound-call-from-the-pstn"></a>Teams ユーザーが PSTN から受信通話を受信する

#### <a name="user-not-enabled-for-location-based-routing"></a>ユーザーがルーティングをLocation-Basedされていない

Location-Based ルーティングが有効になっていないユーザーは、割り当てられた DID 番号が入力される Location-Based ルーティングに対して有効になっていないゲートウェイから受信通話を受信できます。 ユーザーが通話ルーティングに対して有効になっていないサイトにローミングLocation-Based、通常の PSTN ゲートウェイ経由で通話を受信できます。
  
#### <a name="user-enabled-for-location-based-routing"></a>ユーザーがルーティングをLocation-Based

一方、Location-Based ルーティングが有効になっているユーザーは、DID が割り当てられている PSTN ゲートウェイからの受信通話は、同じサイトに存在する場合にのみ受信できます。 次の表は、User1 が別のネットワークの場所に移動した場合に User1 が受信通話を受信する方法を示しています。 通話がユーザーのエンドポイントにルーティングされていない場合は、設定が構成されている場合は、ユーザーの呼び出し転送設定に転送されます。 通常、これはボイスメールです。  

|User1 エンドポイントの場所  |User1 への受信通話のルーティング  |
|---------|---------|
|ユーザーの DID が割り当てられているサイトと同じ、ルーティング (サイト 1) Location-Based有効なサイト   | Site1 で User1 のエンドポイントにルーティングされる通話        |
|ユーザーの DID が割り当てられているサイトとは異なる、サイトがルーティングに対してLocation-Based (Site2)    | サイト 2 のエンドポイントにルーティングされない通話        |
|ユーザーの DID が割り当てられているサイトとは異なる、サイトがルーティングに対してLocation-Based (Site3)    | サイト 3 のエンドポイントにルーティングされない通話        |
|不明な内部ネットワーク (Location4)   | Location4 でエンドポイントにルーティングされない通話        |
|不明な外部ネットワーク (Location5)     | Location5 でエンドポイントにルーティングされない通話        |

### <a name="teams-user-transfers-or-forwards-call-to-another-teams-user"></a>Teams ユーザーが通話を別の Teams ユーザーに転送または転送する

PSTN エンドポイントが関与する場合、Location-Based ルーティングは、1 人または両方のユーザーが Location-Based ルーティングに対して有効になっているかどうかを分析し、両方のエンドポイントの場所に応じて通話を転送するか転送するか決定します。 
 
通話転送では、通話の転送で最初の通話に応答する必要はありません。通話を開始するユーザーが通話を受け取る必要があります。 つまり、User1 が着信通話を受信する場所にいなくても [(Teams](#teams-user-receives-an-inbound-call-from-the-pstn) のユーザーが PSTN セクションから受信通話を受信する表を参照)、User1 が着信通話を受信できない場合、通話を転送できません。 

#### <a name="user-not-enabled-for-location-based-routing"></a>ユーザーがルーティングをLocation-Basedされていない

通話ルーティングが有効になっていないユーザーは、Location-Basedルーティングが有効になっていない他のユーザーに PSTN 通話を転送Location-Basedできます。 Location-Based ルーティングが有効なユーザーは通常、PSTN 通話用の Location-Based ルーティング有効ゲートウェイにのみコロケーションが許可されるため、ユーザーは通常、Location-Based ルーティングが有効になっているユーザーに PSTN 通話を転送または転送することはできません。 例外は、ルーティングがLocation-Based有効なユーザーが、ルーティングに対して有効になっていないサイトにLocation-Basedです。 このシナリオでは、転送された通話が許可されます。  

同様に、Location-Based ルーティングが有効になっていないユーザーは、Location-Based ルーティングが有効になっていない別のユーザーからの転送または転送された PSTN 通話のみを受信できます。 

#### <a name="user-enabled-for-location-based-routing"></a>ユーザーがルーティングをLocation-Based

一般に、Location-Based ルーティングが有効になっているゲートウェイからの着信 PSTN 通話の転送と転送は、ターゲット ユーザーが Location-Based ルーティングを有効にし、同じサイトにある場合にのみ許可されます。 そうしないと、通話の転送と転送は許可されません。 

次の表は、ターゲット ユーザーの場所に応じて、通話の転送と通話転送を許可するかどうかを示しています。 この表では、Site1 にある User1 が、Location-Based ルーティングが有効になっている他の Teams ユーザーと異なる場所にあるユーザーに転送または転送を開始します。  

|ターゲット ユーザー エンドポイントの場所|User1 が通話転送を開始する |User1 が通話転送を開始する|
|---------|---------|---------|
|開始側と同じネットワーク サイト (User2)|許可|許可|
|別のネットワーク サイト、サイトが Location-Based ルーティングに対応 (User3)|許可されません|許可されません|
|異なるネットワーク サイト、サイトが Location-Based ルーティングに対して有効になっていない (User4)|許可されません|許可されません|
|不明な内部ネットワーク (User5)| 許可されません|許可されません|
|不明な外部ネットワーク (User6)| 許可されません|許可されません|

### <a name="teams-user-transfers-or-forwards-call-to-pstn-endpoint"></a>Teams ユーザーが PSTN エンドポイントに通話を転送または転送する

#### <a name="user-not-enabled-for-location-based-routing"></a>ユーザーがルーティングをLocation-Basedされていない

- PSTN 通話を別の PSTN 番号に転送および転送できます。 
- 着信 VOIP 通話を PSTN に転送および転送するには、発信者の有料バイパス制限を尊重する必要があります。 
    - 呼び出し元が Location-Basedルーティングに対して有効になっていない場合、通話ルーティングが有効になっていないすべての PSTN ゲートウェイLocation-Basedできます。
    - 呼び出し元が Location-Based ルーティングに対して有効になっている場合、発信者は同じネットワーク サイトにある Location-Based ルーティングが有効なゲートウェイにのみ転送できます。 

#### <a name="user-enabled-for-location-based-routing"></a>ユーザーがルーティングをLocation-Based

- PSTN 通話を別の PSTN 番号に転送および転送するには、着信通話が着信した場合と同Location-Basedルーティングが有効なゲートウェイからルーティングする必要があります。 
- 着信 VOIP 通話を PSTN に転送および転送するには、発信者と呼び出されたユーザーの有料バイパス制限の両方を尊重する必要があります。 
    - 呼び出し元が Location-Basedルーティングに対して有効になっていない場合、通話ルーティングが有効になっていないすべての PSTN ゲートウェイLocation-Basedできます。
    - 呼び出し元が Location-Based ルーティングに対して有効になっている場合、発信者は同じネットワーク サイトにある Location-Based ルーティングが有効なゲートウェイにのみ転送できます。
 
次の表は、Location-Based ルーティングが、通話を PSTN エンドポイントに転送または転送するさまざまな場所のユーザーに対して、Site1 での User1 からの VOIP 通話のルーティングに与える影響を示しています。  

|通話の転送または転送を開始するユーザー  |PSTN への転送  |PSTN に転送  |
|---------|---------|---------|
|同じネットワーク サイト、サイトが Location-Basedルーティングに対して有効 (ユーザー 2)   |通話転送は、User2 の音声ルーティング Location-Basedに基づいて、Site1 でルーティングが有効になっているゲートウェイ 1 を介してのみルーティングできます。         |呼び出し転送は、User2 Location-Basedに基づいて、Site1 でルーティングが有効になっているゲートウェイ 1 を介してのみルーティングできます。         |
|別のネットワーク サイト、サイトが Location-Based ルーティングに対応 (User3)    |通話転送は、User3 の音声ルーティング Location-Basedに基づいて、Site1 でルーティングが有効なゲートウェイ 1 を介してのみルーティングできます。         |呼び出し転送は、User3 の音声ルーティング Location-Basedに基づいて、Site1 でルーティングが有効になっているゲートウェイ 1 を介してのみルーティングできます。         |
|異なるネットワーク サイト、サイトが Location-Based ルーティングに対して有効になっていない (User4)    |通話転送は、User4 の音声ルーティング Location-Basedに基づいて、Site1 でルーティングが有効になっているゲートウェイ 1 を介してのみルーティングできます。         |コール転送は、User4 の音声ルーティング Location-Basedに基づいて、Site1 でルーティングが有効になっているゲートウェイ 1 を介してのみルーティングできます。         |
|不明な内部ネットワーク (User5)     |通話転送は、User5 の音声ルーティング Location-Basedに基づいて、Site1 でルーティングが有効になっているゲートウェイ 1 を介してのみルーティングできます。         |呼び出し転送は、User5 の音声ルーティング Location-Basedに基づいて、Site1 でルーティングが有効になっているゲートウェイ 1 を介してのみルーティングできます。         |
|不明な外部ネットワーク (User6)   |通話転送は、User6 の音声ルーティング Location-Basedに基づいて、Site1 でルーティングが有効になっているゲートウェイ 1 を介してのみルーティングできます。        |呼び出し転送は、User6 の音声ルーティング Location-Basedに基づいて、Site1 でルーティングが有効になっているゲートウェイ 1 を介してのみルーティングできます。         |

### <a name="simultaneous-ringing"></a>同時呼び出し

Location-Based ルーティングが有効になっているユーザーが通話を受信し、同時呼び出しが有効になっている場合、Location-Based ルーティングは通話者の場所と呼び出し元のエンドポイントを分析して、通話をルーティングするかどうかを決定します。 同時呼び出しは、通話Location-Based転送と同じルールに従います。 

#### <a name="simultaneous-ringing-for-another-teams-user"></a>別の Teams ユーザーの同時呼び出し

次の表に、User1 の受信 PSTN 通話Location-Basedユーザーに対してルーティングを使用して同時呼び出しを許可するかどうかを示します。

|ターゲット ユーザー エンドポイントの場所|同時呼び出し  |
|---------|---------|
|開始側と同じネットワーク サイト (User2)   |許可         |
|別のローミング されたネットワーク サイトが、Location-Based (User3) に対して有効になっている   |許可されません         |
|ローミングされたネットワーク サイトが Location-Based (User4) に対して有効になっていない   |許可されません        |
|不明な内部ネットワーク (User5)    | 許可されません        |
|不明な外部ネットワーク (User6)    |許可されません        |
|対象ユーザーが PSTN 番号である    |通話は、User1 の音声ルーティング Location-Basedに基づいて、Site1 でルーティングが有効なゲートウェイ 1 を介してのみルーティングできます。      |

#### <a name="simultaneous-ringing-to-a-pstn-endpoint"></a>PSTN エンドポイントへの同時呼び出し

次の表は、Location-Basedが PSTN 番号に設定された同時呼び出しを使用して、異なる場所にあるユーザーに対する User1 からの受信 VOIP 通話に対するルーティング動作を示しています。 

|呼び出されたユーザー エンドポイントの場所  |同時呼び出しターゲットは PSTN エンドポイントです |
|---------|---------|
|同じネットワーク サイト、サイトが Location-Basedルーティングに対して有効 (ユーザー 2)    |通話は、User2 の音声ルーティング ポリシーLocation-Basedに基づいて、Site1 で Routing Gateway1 を介してのみルーティングできます。       |
|別のネットワーク サイトがルーティングLocation-Based有効 (User3)    |通話は、User3 の音声ルーティング Location-Basedに基づいて、Site1 の Routing Gateway1 経由でのみルーティングできます。        |
|別のネットワーク サイトがルーティングに対してLocation-Based (User4)    |通話は、User4 の音声ルーティング Location-Basedに基づいて、Site1 の Routing Gateway1 経由でのみルーティングできます。         |
|不明な内部ネットワーク (User5)    |通話は、User5 の音声ルーティング Location-Basedに基づいて、Site1 の Routing Gateway1 を介してのみルーティングできます。         |
|不明な外部ネットワーク (User6)   |通話は、User6 の音声ルーティング Location-Basedに基づいて、Site1 の Routing Gateway1 経由でのみルーティングできます。         |

#### <a name="inbound-calls-through-voice-app-auto-attendant-or-call-queue"></a>音声アプリ (自動応答 または通話キュー) を介した着信通話

ルーティングが有効なゲートウェイLocation-Basedからの受信 PSTN 通話は、自動応答または通話キューへの接続を許可されます。 通話ルーティングがLocation-Basedユーザーは、受信 PSTN 通話の発信元と同じサイトに存在する場合にのみ、これらのアプリケーションからの着信通話転送を受信できます。 
 
ユーザーへの通話の転送と同時呼び出しと PSTN は、音声アプリの転送に許可されます。 ターゲットへの呼び出しを完了する場合、前にLocation-Basedルールと同じ処理が適用されます。  
 
ボイスメールへの転送も許可されます。  

### <a name="delegation"></a>デリゲーション

Teams ユーザーは、自分の代わりに通話を送受信できる代理人を選ぶ場合があります。 Teams の委任機能は、次のように、Location-Basedルーティングの影響を受けます。 
- 委任者の代理でルーティングLocation-Basedを有効にした場合、同じルールが適用されます。 通話ルーティングは、代理人の通話承認ポリシー、音声ルーティング ポリシー、および場所に基づいて行います。 詳細については、「Teams ユーザーが PSTN に発信通話を発信 [する」を参照してください](#teams-user-places-an-outbound-call-to-the-pstn)。 
- 委任者への着信 PSTN 通話の場合、着信の転送または他のユーザーへの同時呼び出しに適用される Location-Based ルーティング ルールと同じも代理人に適用されます。 詳細については [、「Teams](#teams-user-transfers-or-forwards-call-to-another-teams-user)ユーザーが通話を別の Teams ユーザーに転送する [、Teams](#teams-user-transfers-or-forwards-call-to-pstn-endpoint)ユーザーが通話を PSTN エンドポイントに転送または転送する、同時呼び出しを行う」を参照 [してください](#simultaneous-ringing)。 代理人が PSTN エンドポイントを同時呼び出しターゲットとして設定する場合、通話を PSTN にルーティングするために代理人の音声ルーティング ポリシーが使用されます。 
- 委任の場合は、委任者と関連する代理人を同じネットワーク サイトに入れるのが推奨されます。 

## <a name="other-planning-considerations"></a>計画に関するその他の考慮事項

### <a name="changes-from-an-on-premises-location-based-routing-deployment"></a>オンプレミスおよびルーティング展開からのLocation-Based変更

ネットワーク サイトの音声ルーティング ポリシーは使用されなくなりました。 代わりに、ユーザーの音声ルーティング ポリシーを使用します。 つまり、ユーザーが他のサイトにローミングするには、音声ルーティング ポリシーにローミングされたサイトのゲートウェイを含める必要があります。 

### <a name="technical-considerations-for-location-based-routing"></a>場所に基づくルーティングに関する技術的考慮事項

ただし、IPv4 サブネットと IPv6 サブネットはサポートされます。ただし、一致を確認する場合は IPv6 が優先されます。

### <a name="client-support-for-location-based-routing"></a>Location-Based ルーティングのクライアント サポート

次の Teams クライアントがサポートされています。
- Teams デスクトップ クライアント (Windows と Mac)
- Teams モバイル クライアント (iOS および Android)
- Teams の IP 電話機

Teams Web クライアントと Skype for Business クライアントはサポートされていません。

### <a name="capabilities-not-supported-by-location-based-routing"></a>場所に基づくルーティングでサポートされていない機能

Location-Basedルーティングは、次の種類の対話には適用されません。 Location-Basedのシナリオで Teams エンドポイントが PSTN エンドポイントとやり取りする場合、ルーティングは適用されません。 
- 通話保留による PSTN 通話の保留または再開 
- オンプレミスの Skype for Business ユーザーまたは Skype for Business Online ユーザーが Teams ユーザーを呼び出す  

### <a name="location-based-routing-for-conferencing"></a>Location-Basedのルーティング

PSTN Location-Basedルーティングが有効なユーザーは、別のユーザーまたは PSTN 番号との電話会議を開始できません。 自動応答または通話キューへの接続は許可されます。 ユーザーが会議ライセンスを持つ場合、ユーザーは関連するユーザーとの会議を開始し、会議ブリッジを通じて PSTN を呼び出して電話会議を開始する必要があります。  

### <a name="media-bypass-requirement-for-location-based-routing"></a>Location-Based ルーティングのメディア バイパス要件

インドのルーティングをLocation-Basedする場合は、メディア バイパスも構成する必要があります。 詳細については、「ダイレクト ルーティングを使用したメディア [バイパス](direct-routing-plan-media-bypass.md) の計画」および「ダイレクト ルーティングの [ローカル メディア最適化」を参照してください](direct-routing-media-optimization.md)。

### <a name="direct-voice-over-ip-voip"></a>直接音声オーバー IP (VoIP)

インドでは、直接音声オーバー IP (VoIP) をテレフォニー機器と一緒に展開する必要があります。

## <a name="next-steps"></a>次の手順

「ルーティング [のネットワーク設定を構成する」Location-Based覧ください](location-based-routing-configure-network-settings.md)。

## <a name="related-topics"></a>関連項目

- [ダイレクト ルーティングの場所に基づくルーティングを有効にする](location-based-routing-enable.md)
- [Teams のクラウド音声機能のネットワーク設定](cloud-voice-network-settings.md)
