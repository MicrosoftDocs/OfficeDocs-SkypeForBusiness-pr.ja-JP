---
title: Skype for Business Location-Basedルーティングの計画
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
ms.assetid: 4aa494bd-0d66-4335-b9e8-f758d44a7202
description: Skype for Business Server エンタープライズ VoIP での場所ベースのルーティングの計画 (同時呼び出しと委任との対話、場所ベースのルーティングでサポートされるシナリオなど)。
ms.openlocfilehash: 99a76d3cda40bb1fdc71bdffc7f6c896c96c5cc2
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51101483"
---
# <a name="plan-for-location-based-routing-in-skype-for-business"></a>Skype for Business Location-Basedルーティングの計画

Skype for Business Server エンタープライズ VoIP での場所ベースのルーティングの計画 (同時呼び出しと委任との対話、場所ベースのルーティングでサポートされるシナリオなど)。

Location-Basedルーティングを使用すると、通話内の関係者の場所に基づいて、VoIP エンドポイントと PSTN エンドポイント間の通話のルーティングを制限できます。 Location-Basedルーティングは、Skype for Business Server による通話のルーティング方法を制御する通話管理機能です。 Skype for Business 発信者の地理的な場所に基づいて、通話を PBX エンドポイントまたは PSTN エンドポイントにルーティングできるかどうかに関する通話承認ルールを適用します。

Location-Basedルーティングでは、有料バイパスを防止するために国内および国際 PSTN 通話のルーティングを変更する新しいルールセットが導入されています。 Location-Basedルーティングでは、これらのルールを特定の地域、特定のゲートウェイ、または特定の一連のユーザーにのみ柔軟に範囲指定できます。

次のシナリオは、ルーティングが適用できる主なLocation-Basedを示しています。

- 出力呼び出し - Location-Based ルーティングは、発信者が PSTN 有料バイパスを防止する場所と同じ地域にある PSTN ゲートウェイへの発信呼び出しを強制できます。これは、発信者として別の地域にある PSTN ゲートウェイへの発信を防止します。

- 入力呼び出し - Location-Based ルーティングは、着信呼び出しをルーティングする PSTN ゲートウェイが呼び出された Skype for Business ユーザーと同じ地域にはない場合、Skype for Business エンドポイントを呼び出す着信 PSTN 呼び出しを防止できます。

- 不明な地域 - Location-Based ルーティングは、未決定の場所にあるユーザー (つまり、インターネットから接続しているリモート ユーザー、または不明な地域にあるリモート ユーザー) との間の着信および発信 PSTN 通話を制限します。

- 国際地域 - Location-Basedユーザーの場所にローカルなゲートウェイが見つからない場合、国際 PSTN ゲートウェイを介した発信通話のルーティングが適用されます。

## <a name="guidance-for-where-to-apply-location-based-routing"></a>ルーティングを適用する場所Location-Basedガイダンス

Location-Based状況に応じてルーティングは、ユーザーのエンドポイント ネットワーク サイトの場所または PSTN ゲートウェイのネットワーク サイトの場所に適用できます。 このトピックでは、ルーティングの適用方法Location-Based説明します。

### <a name="applying-location-based-routing-at-the-users-location"></a>ユーザーLocation-Based場所でのルーティングの適用

Location-Basedルーティングは、E9-1-1、CAC、メディア バイパスで使用される Skype for Business Server で定義されているのと同じネットワーク領域、サイト、サブネットを利用して、PSTN 有料バイパスを防止するために通話ルーティング制限を適用します。 ユーザーの場所は、ユーザーの Skype for Business エンドポイントが接続されている IP サブネットによって決まります。 各 IP サブネットはネットワーク サイトに関連付けされ、管理者によって定義されたネットワーク領域に集約されます。 Location-Basedルーティングは、ユーザーのネットワーク サイトに基づいて適用されます。

Location-Basedルーティング ルールはネットワーク サイトごとに適用されます。つまり、同じネットワーク サイト内にある Location-Based ルーティングに対して有効になっているすべてのエンドポイントにルールのセットが適用されます。 管理者は、ルーティングをLocation-Basedネットワーク サイトに適用できます。

音声ルーティング ポリシーは、ネットワーク サイトごとに定義して、ネットワーク サイト内のすべてのユーザーが PSTN 電話番号を呼び出す際に使用する特定の PSTN ゲートウェイを定義できます。 このような音声ルーティング ポリシーは、ユーザーが Location-Based ルーティングが有効なネットワーク サイトにユーザーが入っている場合に、ユーザーの音声ポリシーによって定義されたルーティングよりも優先され、Location-Based ルーティングが有効になっている他の PSTN ゲートウェイを介した通話のルーティングが防止されます。 Skype for Business ユーザーが PSTN 通話を発信すると、ユーザーの音声ポリシーによって、ユーザーが通話の発信を承認できるかどうかが決定されます。 ユーザーの音声ポリシーでユーザーが通話を発信できる場合は、Location-Basedが発信する PSTN ゲートウェイを決定します。 Location-Basedルーティングは、ユーザーの場所に基づいてこの決定を行います。

ユーザーの場所は、次の方法で分類できます。

- ユーザーは Location-Based ルーティングが有効な既知のネットワーク サイトにあり、同じネットワーク サイト (つまり office) に配置された PSTN ゲートウェイで DID (ダイレクト インワード ダイヤル) 番号が終了します。 発信呼び出しのルーティングは、ユーザーが位置するネットワーク サイトの音声ルーティング ポリシーを介して行います。 ユーザーへの着信 PSTN 呼び出しは、PSTN ゲートウェイと同じネットワーク サイトにあるエンドポイントにルーティングされます。

- ユーザーは、PSTN ゲートウェイが存在するネットワーク サイトとは異なる既知のネットワーク サイトに存在します。 (つまり、ユーザーが別の会社のオフィスに移動した場合)。 発信呼び出しのルーティングは、ユーザーが位置するネットワーク サイトの音声ルーティング ポリシーを使用します。 ユーザーへの着信 PSTN 呼び出しは、PSTN 有料バイパスを防止するために、PSTN ゲートウェイとは異なるサイトにあるエンドポイントにルーティングされません。

- Skype for Business Server 展開では不明なネットワーク サイトにユーザーが配置されている場合、発信呼び出しのルーティングは、Location-Based ルーティング制限にバインドされていない PSTN ゲートウェイにユーザーに割り当てられた音声ポリシーに基づいて行います。 PSTN 通話の着信は、PSTN 料金のバイパスを防止するために、不明なネットワーク サイトにあるエンドポイントにルーティングされません。

### <a name="applying-location-based-routing-at-the-pstn-gateways-location"></a>PSTN Location-Basedの場所でのルーティングの適用

PSTN ゲートウェイと PBX を介してルーティングされる呼び出しでは、Location-Basedの場所に応じてルーティングの制限が必要になる場合があります。 Location-Basedルーティングは、トランク単位で細分化して有効にできます。

Location-Basedルーティングでは、トランクで有効にすると、次のルールセットが導入されます。

- トランクLocation-Basedルーティングが有効になっている場合、そのトランクで定義されるルールは、そのトランク経由でルーティングされる呼び出しにのみ適用されます。

- PSTN ゲートウェイが存在するネットワーク サイトとは異なるネットワーク サイトから通話が発信される PSTN 通行料がバイパスされるのを防ぐため、Location-Based Routing では、特定のトランクに対するネットワーク サイトの関連付けを導入します。 これにより、呼び出しを特定のトランクにルーティングできるネットワーク サイトが定義されます。

トランクは、次の 2 つのLocation-Basedルーティングに対して有効にできます。

- トランクは、PSTN への呼び出しを出力する PSTN ゲートウェイに対して定義されます。 この種類のトランクによってルーティングされる着信呼び出しは、トランクと同じネットワーク サイト内にあるエンドポイントにのみルーティングされます。

- トランクは、PSTN への呼び出しを出力しない仲介サーバー ピアと、静的な場所 (つまり PBX 電話) の従来の電話を持つサービス ユーザーに対して定義されます。 この特定の構成では、この種類のトランクによってルーティングされる着信呼び出しはすべて、トランクと同じネットワーク サイトから発信されたと見なされます。 PBX ユーザーからの呼び出しは、トランクLocation-Based同じネットワーク サイトに存在する Skype for Business ユーザーと同じルーティングの適用を受け取る必要があります。 別のネットワーク サイトにある 2 つの PBX システムが Skype for Business Server を介して接続されている場合、Location-Based Routing は、あるネットワーク サイト内の 1 つの PBX エンドポイントから他のネットワーク サイトの別の PBX エンドポイントへのルーティングを許可します。 このシナリオは、ルーティングによってLocation-Basedされません。 このシナリオに加えて、同じ場所の Skype for Business ユーザーと同様の方法で、この構成を使用して仲介サーバー ピアに接続されているエンドポイントは、仲介サーバー ピアが関連付けられているネットワーク サイトに関係なく、PSTN (つまり、別の PBX に接続されたエンドポイント) への通話をルーティングしない他の仲介サーバー ピアとの間で通話を発信または受信できます。 PSTN エンドポイントを含むすべての着信呼び出し、発信呼び出し、通話転送、および通話転送は、このような仲介サーバー ピアに対してローカルとして定義されている PSTN ゲートウェイのみを使用する場所ベースのルーティングの対象になります。

## <a name="scenarios-for-location-based-routing"></a>ルーティングのLocation-Basedシナリオ

Location-Basedルーティングは、次のシナリオで呼び出しをルーティングするときに、次の一般的なルールを適用します。

### <a name="outgoing-calls"></a>発信呼び出し

ルーティングに対して有効になっているユーザーLocation-Based発信呼び出しのルーティングは、ユーザーのエンドポイントのネットワークの場所の影響を受ける。 次の表は、呼び出Location-Basedのエンドポイントの場所に応じて、ルーティングが発信呼び出しのルーティングにどのように影響するかを示しています。

**PSTN への発信呼び出しを発信する発信者**

||**ネットワーク サイト内にあるユーザー エンドポイントがルーティングに対して有効Location-Basedエンドポイント**|**不明なネットワーク サイトにあるユーザー エンドポイント、またはユーザー ルーティングが有効Location-Basedエンドポイント**|
|:-----|:-----|:-----|
|発信呼び出しの承認  <br/> |通話は、ユーザーの音声ポリシーに基づいて承認されます。  <br/> |通話は、ユーザーの音声ポリシーに基づいて承認されます。  <br/> |
|発信呼び出しのルーティング  <br/> |通話は、ネットワーク サイトの音声ルーティング ポリシーに従ってルーティングされます。  <br/> |通話は、ユーザーの音声ポリシーに従ってルーティングされ、Location-Basedルーティングが有効になっていないトランクのみを経由します (使用可能な場合)  <br/> |

### <a name="incoming-calls"></a>着信呼び出し

ルーティングが有効になっているユーザーに対する着信Location-Basedルーティングは、ユーザーのエンドポイントの場所によって異なります。 着信呼び出しのルーティングは、次の方法で影響を受ける。 ユーザーが Location-Based ルーティングが有効なネットワーク サイトにあるエンドポイントへの着信呼び出しを持ち、そのエンドポイントが PSTN ゲートウェイと同じネットワーク サイトにある場合、その呼び出しはルーティングされます。 ユーザーが Location-Based ルーティングが有効なネットワーク サイトにあるエンドポイントへの着信呼び出しを持ち、そのエンドポイントが PSTN ゲートウェイとは異なるネットワーク サイトにある場合、その呼び出しはルーティングされません。 着信呼び出しの発信元である PSTN ゲートウェイと同じネットワーク サイトにエンドポイントがない場合、着信呼び出しはユーザーのボイスメールに直接ルーティングされ、着信通知が着信側に送信されます。

Location-Based ルーティングが有効になっているユーザーの通話転送設定は引き続き適用されます。ただし、転送される通話は、ユーザーの Location-Based ルーティング制限の対象になります。

次の表は、呼び出Location-Basedのエンドポイントの場所に応じて、着信呼び出しのルーティングに対するルーティングの影響を示しています。 PSTN ゲートウェイのネットワーク サイトは Location-Based ルーティングに対して有効であり、Location-Based ルーティングでは、同じネットワーク サイト内のエンドポイントへの PSTN 通話のルーティングのみを許可します。

**PSTN から受信呼び出しを受信する着信者**

||**PSTN ゲートウェイと同じネットワーク サイトにある呼び出し先のエンドポイント**|**PSTN ゲートウェイと同じネットワーク サイトに位置しない通話先のエンドポイント**|**不明なネットワーク サイトにある呼び出し先のエンドポイント、またはルーティングに対して有効Location-Based。**|
|:-----|:-----|:-----|:-----|
|受信 PSTN 通話のルーティング  <br/> |着信呼び出しは、呼び出し先のエンドポイントにルーティングされます。  <br/> |着信呼び出しが呼び出し先のエンドポイントにルーティングされない  <br/> |着信呼び出しが呼び出し先のエンドポイントにルーティングされない  <br/> |

### <a name="call-transfers-and-call-forwarding"></a>通話転送と通話転送

PSTN エンドポイントが関係する場合、Location-Based ルーティングは通話のエンドポイントの場所と、通話が転送または転送されるエンドポイント (転送/転送ターゲット) を分析します。 Location-Basedルーティングは、両方のエンドポイントの場所に応じて、呼び出しを転送または転送するかどうかを決定します。

次の表は、PSTN エンドポイントを使用した通話における Skype for Business ユーザーのシナリオを示し、Skype for Business ユーザーは通話を別の Skype for Business ユーザーに転送します。 転送先のエンドポイントのネットワーク サイトの場所に応じて、Location-Basedルーティングは通話転送または転送のルーティングに影響します。

**通話転送または転送の開始**

|**通話の転送/転送を開始するユーザー**|**ターゲット エンドポイントは、ユーザーが通話の転送または転送を開始するのと同じネットワーク サイト内にある**|**ユーザーが通話の転送または転送を開始する場合、ターゲット エンドポイントが異なるネットワーク サイト内にある**|**ターゲット エンドポイントが不明なネットワーク サイトまたはネットワーク サイト内のネットワーク Location-Basedルーティング**|
|:-----|:-----|:-----|:-----|
|Skype for Business ユーザー  <br/> |転送または転送が許可されている  <br/> |転送または転送は許可されません  <br/> |転送または転送は許可されません  <br/> |

たとえば、PSTN エンドポイントを使用する呼び出しの Skype for Business ユーザーは、同じネットワーク サイト内にある別の Skype for Business ユーザーに通話を転送します。 この場合、通話の転送が許可されます。

次の表は、別の Skype for Business ユーザーとの通話における Skype for Business ユーザーのシナリオを示し、ユーザーの 1 人が PSTN エンドポイントに通話を転送します。 呼び出しが転送されるユーザーの場所に応じて、ルーティングが呼び出しにLocation-Based詳細を示します。

**PSTN エンドポイントへの通話転送または転送**

|**通話転送/転送エンドポイント ターゲット**|**同じネットワーク サイト内の Skype for Business ユーザー**|**異なるネットワーク サイトの Skype for Business ユーザー**|**不明なネットワーク サイトまたはネットワーク サイト内の Skype for Business ユーザーの 1 人または両方がルーティングにLocation-Basedします**|
|:-----|:-----|:-----|:-----|
|PSTN エンドポイント  <br/> |転送されたユーザーのサイト音声ルーティング ポリシーで許可されている転送または転送  <br/> |転送されたユーザーのサイト音声ルーティング ポリシーで許可されている転送または転送  <br/> |転送されたユーザーの音声ポリシーによって許可される転送または転送は、ルーティングに対して有効になっていないトランクLocation-Basedします。  <br/> |

たとえば、同じネットワーク サイト内にある別の Skype for Business ユーザーとの通話中の Skype for Business ユーザーは、PSTN エンドポイントに通話を転送し、通話の転送を許可します。

### <a name="simultaneous-ringing"></a>同時呼び出し

呼び出し側が同時呼び出しを有効にしている場合、Location-Based Routing は通話相手の場所と呼び出し元のエンドポイントを分析して、通話をルーティングするかどうかを決定します。

次の表は、同時呼び出しで構成されたユーザーを示しています。同時呼び出しターゲットは、同じネットワーク サイト、別のネットワーク サイト、または不明なネットワーク サイト内のユーザーです。

****

|**PSTN の着信呼び出し**|**呼び出し先と同じネットワーク サイトに位置する**|**呼び出し先とは異なるネットワーク サイトに位置する**|**不明なネットワーク サイトにあるか、ルーティングが有効になっていないLocation-Basedします。**|
|:-----|:-----|:-----|:-----|
|Skype for Business ユーザー  <br/> |同時呼び出し可能  <br/> |同時呼び出しは許可されません  <br/> |同時呼び出しは許可されません  <br/> |

次の表は、同じネットワーク サイト、別のネットワーク サイト、または不明なネットワーク サイトの Skype for Business ユーザー (Skype for Business 呼び出し元) からの呼び出しを示しています。 呼び出し先には、PSTN エンドポイント (つまり、携帯電話) が同時リング ターゲットとして構成されています。 このシナリオでは、Location-Based ルーティングによって、呼び出し先の同時呼び出し先 (つまり携帯電話) に通話をルーティングするかどうかを決定します。

****

|**同時リング ターゲット**|**呼び出し先と同じネットワーク サイトに位置する**|**呼び出し先とは異なるネットワーク サイトに位置する**|**不明なネットワーク サイトにあるか、ルーティングが有効になっていないLocation-Basedします。**|
|:-----|:-----|:-----|:-----|
|PSTN エンドポイント  <br/> |発信者のサイト音声ルーティング ポリシーを介して許可される同時呼び出し  <br/> |発信者のサイト音声ルーティング ポリシーを介して許可される同時呼び出し  <br/> |呼び出し元の音声ポリシーを介して、ルーティングに対して有効になっていないトランクへの同時Location-Basedリング  <br/> |

### <a name="skype-for-business-cumulative-update-4"></a>Skype for Business 累積的な更新プログラム 4

累積的な更新プログラム 4 では、次の情報が表示されます。

- Location-Basedルーティングは、Skype for Business Mobile クライアントを含む音声ポリシーを介して引き続き有効になります。

- Skype for Business Mobile クライアントの呼び出し動作は、ユーザールーティングが有効になっているかどうか、およびLocation-Basedクライアントに基づいて行います。 これは静的な設計ですが、特定の状況では、Skype for Business Mobile クライアントをローカル PSTN ゲートウェイに関連付け、エスカレーションなどの特定の動作を許可する努力がある場合があります。

- OS に関係なく、Skype for Business Mobile クライアントには同じ機能が必要です。

次の表では、累積的な更新プログラム 4 の後のシナリオについて説明します。

|**場所ベースのルーティング ユーザー**|**その他のパーティ**|**Action**|**結果**|
|:-----|:-----|:-----|:-----|
|Skype for Business Mobile  <br/> |PSTN  <br/> |Skype for Business Mobile は、PSTN の着信呼び出しを受信します。  <br/> |通話は VoIP ではなく、作業時間 (CvW) 経由でルーティングされます。  <br/> |
|Skype for Business Mobile  <br/> |PSTN  <br/> |Skype for Business Mobile では、発信 PSTN 通話を行います。  <br/> |通話は VoIP ではなく CvW 経由でルーティングされます。  <br/> |
|Skype for Business Mobile  <br/> |PSTN  <br/> |Skype for Business Mobile は PSTN 通話中です。 その後、Skype for Business Mobile は通話を別のユーザーまたは連絡先にエスカレートします。  <br/> |ユーザーまたは連絡先が PSTN ゲートウェイ の脚にローカルである場合、通話は VoIP 経由でルーティングされます。  <br/> ユーザーまたは連絡先が PSTN ゲートウェイ の脚からリモートである場合、通話は CvW 経由でルーティングされます。  <br/> ターゲット ユーザーが PSTN 経由で到達できない場合、呼び出しは失敗します。  <br/> ターゲット連絡先が電話会議 (CAA) 自動応答場合、呼び出しはブロックされます。  <br/> |
|Skype for Business Mobile  <br/> |Skype for Business クライアントまたはフェデレーション ユーザー  <br/> |Skype for Business Mobile は、別の Skype for Business クライアントまたはフェデレーション ユーザーへの音声通話を開始します。  <br/> |通話は VoIP 経由で完了します。  <br/> |
|Skype for Business Mobile  <br/> |Skype for Business クライアントまたはフェデレーション ユーザー  <br/> | Skype for Business クライアントまたはフェデレーション ユーザーは、Skype for Business Mobile ユーザーへの音声通話を開始し、ルーティング ユーザーLocation-Basedします。 <br/> |通話は VoIP 経由で完了します。  <br/> |
|Skype for Business Mobile  <br/> |Skype for Business クライアントまたはフェデレーション ユーザー  <br/> |Skype for Business クライアントまたはフェデレーション ユーザーは、Skype for Business Mobile ユーザーへの VoIP 呼び出しを行っています。 いずれかのパーティが、追加の Skype for Business またはフェデレーション ユーザーにエスカレートします。  <br/> |通話は VoIP 経由で完了します。  <br/> |
|Skype for Business Mobile  <br/> |フェデレーション ユーザー  <br/> |フェデレーション ユーザーは、Skype for Business Mobile ユーザーへの音声通話中で、ルーティング ユーザーLocation-Based呼び出します。Skype for Business Mobile パーティーは PSTN ユーザーにエスカレートします。  <br/> |呼び出しがブロックされます。  <br/> |
|Skype for Business Mobile  <br/> |フェデレーション ユーザー  <br/> |フェデレーション ユーザーは、Skype for Business Mobile ユーザーへの VoIP 呼び出しLocation-Basedルーティング ユーザーです。いずれかのパーティが CAA 連絡先にエスカレートします。  <br/> |エスカレートされた呼び出しはブロックされ、適切なエラー メッセージが表示されます。  <br/> |
|Skype for Business Mobile  <br/> |フェデレーション ユーザー  <br/> |フェデレーション ユーザーが Skype for Business Mobile Location-Based ルーティング ユーザーに VoIP 呼び出しを行い、フェデレーション ユーザーが PSTN ユーザーにエスカレートします。  <br/> |このエスカレーションは、フェデレーション ユーザーのルーティングのLocation-Basedに基づいて許可または禁止されます。 Skype for Business Mobile Location-Basedルーティング ユーザーのアプリケーションは何も実行しない。  <br/> |

### <a name="delegation"></a>委任

Skype for Business の委任機能は、次の方法でLocation-Basedルーティングの影響を受ける。

- Location-Based ルーティングが有効になっている代理人がマネージャーの代わりに通話を行う場合、代理人の音声ポリシーを使用して通話を承認し、代理人のサイト音声ルーティング ポリシーを使用して通話をルーティングします。

- マネージャーへの着信 PSTN 呼び出しの場合、通話転送または同時呼び出しに適用されるのと同じルールが、「通話転送と転送」および「同時呼び出し」のトピックで説明されているとおりに適用されます。

- 代理人が PSTN エンドポイントを同時リング ターゲットとして設定すると、マネージャーへの着信呼び出しに対して、着信トランクに関連付けられているサイトの音声ルーティング ポリシーを使用して、通話を代理人の PSTN エンドポイントにルーティングします。

- 委任の場合は、マネージャーと関連付けられている代理人を通常は同じネットワーク サイトに入れる必要があります。

## <a name="other-planning-considerations"></a>その他の計画上の考慮事項

ルーティングの計画Location-Based、次のシナリオへの影響を考慮する必要があります。

### <a name="disaster-recovery"></a>障害回復

プライマリ プールからバックアップ プールへのフェールオーバー中、および通常の操作をプライマリ プールに復元する場合、Location-Based ルーティングは障害および回復手順中に常に適用されたままです。

### <a name="survivable-branch-appliance"></a>存続可能ブランチ アプライアンス

ルーティングLocation-Based構成すると、存続可能ブランチ アプライアンスに関連付けられたゲートウェイを展開する場所の計画に影響します。 SBA に関連付けられているゲートウェイは、存続可能ブランチ アプライアンスと同じネットワーク サイトにある必要があります。それ以外の場合、存続可能ブランチ アプライアンスに接続されているユーザーは、ルーティングが構成されている場合、Location-Based発信を許可されません。 存続可能ブランチ アプライアンスと中央サイト間の WAN 接続がダウンしている場合、ルーティングLocation-Based適用されます。

## <a name="client-and-server-support-for-location-based-routing"></a>クライアントとサーバーのネットワーク ルーティングLocation-Basedサポート

Location-Basedは Skype for Business Server によって適用されます。 Skype for Business Server は、ユーザーが企業ネットワーク内から接続しているネットワーク サイトを識別できます。 リモート ユーザーは企業ネットワークの外部にあるので、その場所は不明と見なされます。

### <a name="server-support"></a>サーバーのサポート

Location-Basedルーティングでは、Skype for Business Server または Lync Server 2013 CU1 が、特定のトポロジ内のすべてのフロントエンド プールおよび Standard Edition サーバーに展開されている必要があります。 これらのバージョンのサーバーがインストールされていない場合、場所ベースのルーティング制限を完全に適用することはできません。

次の表は、サーバー の役割と、ルーティングでサポートされているバージョンの組み合わせをLocation-Basedします。

****

|**プールのバージョン**|**仲介サーバーのバージョン**|**サポートされている**|
|:-----|:-----|:-----|
|Skype for Business Server または Lync Server 2013 2013 年 2 月累積的な更新プログラム  <br/> |Skype for Business Server または Lync Server 2013 2013 年 2 月累積的な更新プログラム  <br/> |はい  <br/> |
|Skype for Business Server または Lync Server 2013 2013 年 2 月累積的な更新プログラム  <br/> |Lync Server 2013  <br/> |no  <br/> |
|Skype for Business Server または Lync Server 2013 2013 年 2 月累積的な更新プログラム  <br/> |Lync Server 2010  <br/> |no  <br/> |
|Skype for Business Server または Lync Server 2013 2013 年 2 月累積的な更新プログラム  <br/> |Office Communications Server 2007 R2  <br/> |no  <br/> |
|Lync Server 2013  <br/> |any  <br/> |no  <br/> |
|Lync Server 2010  <br/> |any  <br/> |no  <br/> |
|Office Communications Server 2007 R2  <br/> |any  <br/> |no  <br/> |

### <a name="client-support"></a>クライアント サポート

次の表は、ルーティングがサポートするLocation-Based示します。

****

|**クライアントの種類**|**サポートされている**|**詳細**|
|:-----|:-----|:-----|
|Skype for Business  <br/> |はい  <br/> ||
|Lync 2013  <br/> |はい  <br/> ||
|Lync 2010  <br/> |はい  <br/> ||
|Office Communicator 2007 R2  <br/> |no  <br/> ||
|Lync Phone Edition  <br/> |はい  <br/> ||
|Lync Attendant  <br/> |はい  <br/> ||
|Lync for Windows 8  <br/> |no  <br/> ||
|Lync Mobile 2013  <br/> |no  <br/> |ルーティングが有効になっているユーザーが Lync Mobile 2013 クライアントで使用する場合は、VoIP をLocation-Based必要があります。  <br/> |
|Lync Mobile 2010  <br/> |はい  <br/> ||

> [!NOTE]
> Skype for Business クライアントの VoIP を無効にするには、モビリティ ポリシーに IP Audio/Video という設定を割り当て、ルーティングを有効にしているすべてのユーザーに対して無効Location-Basedします。 モビリティ ポリシーの詳細については [、「New-CsMobilityPolicy」を参照してください](/powershell/module/skype/new-csmobilitypolicy?view=skype-ps)。

## <a name="capabilities-not-supported-by-location-based-routing"></a>ルーティングでサポートされていないLocation-Based機能

Location-Basedルーティングは、次の種類の操作には適用されません。 Location-Based Skype for Business エンドポイントがこれらの機能を使用して PSTN エンドポイントとやり取りする場合、ルーティングは適用されません。

- PSTN ダイヤルインから電話会議へ

- 応答グループを介した着信および発信 PSTN 通話

- 通話パークまたは通話パークを介した PSTN 通話の取得

- アナウンス サービスへの PSTN 着信呼び出し

- グループ通話ピックアップを介して取得される着信 PSTN 通話

次のLocation-Basedの種類にルーティング ルールを適用するには、会議のルーティングLocation-Based有効にする必要があります。

- 電話会議からの PSTN ダイヤルアウト

- ピアツーピアの音声会話から PSTN エンドポイントを含む会議へのエスカレーション

- PSTN エンドポイントに関するコンサルティング転送

会議のLocation-Basedを有効にするには、「会議の [場所ベースのルーティング」を参照してください](/previous-versions/office/lync-server-2013/lync-server-2013-location-based-routing-for-conferencing)。