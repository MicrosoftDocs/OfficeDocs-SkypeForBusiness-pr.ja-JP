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
description: Skype for Business Server エンタープライズ VoIP での場所に基づくルーティングの計画。同時呼び出しと委任の操作、場所に基づくルーティングでサポートされるシナリオを含む。
ms.openlocfilehash: 473ed77dce8edaee3b43822adcb8920027795d9e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825557"
---
# <a name="plan-for-location-based-routing-in-skype-for-business"></a>Skype for Business Location-Basedルーティングの計画

Skype for Business Server エンタープライズ VoIP での場所に基づくルーティングの計画。同時呼び出しと委任の操作、場所に基づくルーティングでサポートされるシナリオを含む。

Location-Basedルーティングを使用すると、VoIP エンドポイントと PSTN エンドポイント間の通話のルーティングを、通話内の関係者の場所に基づいて制限できます。 Location-Basedルーティングは、Skype for Business Server による通話のルーティング方法を制御する通話管理機能です。 これは、Skype for Business の発信者の地理的な場所に基づいて、通話を PBX または PSTN エンドポイントにルーティングできるかどうかに関する通話承認ルールを適用します。

Location-Basedルーティングでは、国内および国際 PSTN 通話のルーティングを変更して有料バイパスを防止する新しいルールセットが導入されています。 Location-Basedルーティングを使用すると、これらのルールを特定の地域、特定のゲートウェイ、または特定のユーザー セットにのみ柔軟に範囲指定できます。

次のシナリオは、ルーティングが適用できる主なLocation-Basedを示しています。

- 出口通話 - Location-Based ルーティングは、発信者が PSTN 有料バイパスを回避するのと同じ地域にある PSTN ゲートウェイへの発信呼び出しを強制的に実行できます。これは、通話が発信者として別の地域にある PSTN ゲートウェイに出るのを防ぐためです。

- 着信通話 - Location-Based ルーティングは、着信通話をルーティングする PSTN ゲートウェイが、呼び出された Skype for Business ユーザーと同じ地域にはない場合に、着信 PSTN 通話が Skype for Business エンドポイントを呼び出すのを防ぐ可能性があります。

- 不明な地域 - Location-Based ルーティングは、未決定の場所 (インターネットから接続しているリモート ユーザー、または不明な地域に存在するリモート ユーザー) との間の PSTN 通話の着信と発信を制限します。

- 国際地域 - ユーザーLocation-Basedの場所にローカルなゲートウェイが見つからない場合は、国際 PSTN ゲートウェイを介した発信通話のルーティングが適用されます。

## <a name="guidance-for-where-to-apply-location-based-routing"></a>ルーティングを適用する場所Location-Basedガイダンス

Location-Basedに応じて、ユーザーのエンドポイント ネットワーク サイトの場所または PSTN ゲートウェイのネットワーク サイトの場所でルーティングを適用できます。 このトピックでは、ルーティングを適用するLocation-Basedについて説明します。

### <a name="applying-location-based-routing-at-the-users-location"></a>ユーザーLocation-Basedでのルーティングの適用

Location-Basedルーティングでは、E9-1-1、CAC、およびメディア バイパスで使用される Skype for Business Server で定義されているのと同じネットワーク地域、サイト、サブネットを利用して、PSTN 有料バイパスを防止するために通話ルーティング制限を適用します。 ユーザーの場所は、ユーザーの Skype for Business エンドポイントが接続されている IP サブネットによって決まります。 各 IP サブネットはネットワーク サイトに関連付けされ、管理者によって定義されたネットワーク地域に集約されます。 Location-Basedルーティングは、ユーザーのネットワーク サイトに基づいて適用されます。

Location-Basedルールはネットワーク サイトごとに適用されます。つまり、同じネットワーク サイト内にある Location-Based ルーティングが有効なすべてのエンドポイントに特定のルールセットが適用されます。 管理者は、このLocation-Based必要なネットワーク サイトにルーティングを適用できます。

音声ルーティング ポリシーは、ネットワーク サイトごとに定義して、ネットワーク サイト内のすべてのユーザーが PSTN 電話番号を呼び出す際に使用する特定の PSTN ゲートウェイを定義できます。 このような音声ルーティング ポリシーは、ユーザーが Location-Based ルーティングが有効なネットワーク サイトに位置する場合に、ユーザーの音声ポリシーで定義されたルーティングよりも優先され、Location-Based ルーティングが有効な他の PSTN ゲートウェイを介した通話のルーティングを防止します。 Skype for Business ユーザーが PSTN 通話を発信すると、ユーザーの音声ポリシーによって、通話の発信を許可できるかどうかが決定されます。 ユーザーの音声ポリシーでユーザーが通話を発信できる場合は、Location-Based ルーティングによって、通話の発信に使用する PSTN ゲートウェイが決定されます。 Location-Basedルーティングは、ユーザーの場所に基づいてこの決定を行います。

ユーザーの場所は、次の方法で分類できます。

- ユーザーは Location-Based ルーティングが有効になっている既知のネットワーク サイトに配置され、DID (Direct Inward Dial) 番号は同じネットワーク サイト (オフィス) に配置された PSTN ゲートウェイで終了します。 発信通話のルーティングは、ユーザーが位置するネットワーク サイトの音声ルーティング ポリシーを介して行います。 ユーザーへの着信 PSTN 通話は、PSTN ゲートウェイと同じネットワーク サイトにあるエンドポイントにルーティングされます。

- ユーザーは、PSTN ゲートウェイが存在するネットワーク サイトとは異なる既知のネットワーク サイトに存在します。 (つまり、ユーザーが別の会社のオフィスに出張した)。 発信通話のルーティングでは、ユーザーが位置するネットワーク サイトの音声ルーティング ポリシーを使用します。 ユーザーへの着信 PSTN 通話は、PSTN ゲートウェイとは異なるサイトにあるエンドポイントにルーティングされないので、PSTN 料のバイパスを防ぐ必要があります。

- ユーザーが Skype for Business Server 展開で不明なネットワーク サイトに配置されている場合、発信通話のルーティングは、Location-Based ルーティング制限にバインドされていない PSTN ゲートウェイにユーザーに割り当てられた音声ポリシーに基づいて行います。 着信 PSTN 通話は、PSTN 料金のバイパスを防ぐために、不明なネットワーク サイトにあるエンドポイントにはルーティングされません。

### <a name="applying-location-based-routing-at-the-pstn-gateways-location"></a>PSTN Location-Basedでのルーティングの適用

PSTN ゲートウェイと PBX 経由でルーティングされる通話では、そのようなシステムLocation-Basedに応じて、ルーティングの制限が必要になる場合があります。 Location-Basedルーティングは、トランク単位で粒度で有効にできます。

Location-Basedルーティングでは、トランクで有効にした場合、次の一連のルールが導入されます。

- トランクLocation-Basedルーティングが有効になっている場合、そのトランクで定義されるルールは、そのトランク経由でルーティングされる通話にのみ適用されます。

- PSTN ゲートウェイが存在するネットワーク サイトとは異なるネットワーク サイトから通話が発信される場合の PSTN 有料バイパスを回避するために、Location-Based ルーティングでは、ネットワーク サイトと特定のトランクとの関連付けが導入されます。 これにより、通話を特定のトランクにルーティングできるネットワーク サイトが定義されます。

トランクは、次の 2 つのLocation-Basedルーティングに対して有効にできます。

- トランクは、通話を PSTN に出力する PSTN ゲートウェイに対して定義されます。 この種類のトランクによってルーティングされる着信通話は、トランクと同じネットワーク サイト内にあるエンドポイントにのみルーティングされます。

- トランクは、PSTN に通話を送信しない仲介サーバー ピアに対して定義され、静的な場所 (PBX 電話) に従来の電話を持つユーザーにサービスを提供します。 この特定の構成では、この種類のトランクによってルーティングされる着信呼び出しはすべて、トランクと同じネットワーク サイトから発信されたと見なされます。 PBX ユーザーからの通話には、トランクと同Location-Basedネットワーク サイトに存在する Skype for Business ユーザーと同じルーティングが適用されます。 別々のネットワーク サイトに存在する 2 つの PBX システムが Skype for Business Server を介して接続されている場合、Location-Based ルーティングでは、あるネットワーク サイトの PBX エンドポイントから別のネットワーク サイトの別の PBX エンドポイントへのルーティングが許可されます。 このシナリオは、ルーティングによってLocation-Basedされません。 このシナリオと同じ場所の Skype for Business ユーザーと同様の方法で、この構成を使用して仲介サーバー ピアに接続されたエンドポイントは、仲介サーバー ピアが関連付けられているネットワーク サイトに関係なく、PSTN への通話をルーティングしない他の仲介サーバー ピア (つまり、別の PBX に接続されたエンドポイント) との間で通話を発信または受信できます。 PSTN エンドポイントを含むすべての着信呼び出し、発信通話、通話転送、および着信転送は、このような仲介サーバー ピアに対してローカルとして定義されている PSTN ゲートウェイのみを使用するために、場所に基づくルーティングの対象になります。

## <a name="scenarios-for-location-based-routing"></a>ネットワーク ルーティングLocation-Basedシナリオ

Location-Basedルーティングは、次のシナリオで通話をルーティングするときに、次の一般的なルールを適用します。

### <a name="outgoing-calls"></a>発信通話

Location-Based ルーティングが有効になっているユーザーの発信通話のルーティングは、ユーザーのエンドポイントのネットワークの場所の影響を受ける。 次の表に、通話Location-Basedのエンドポイントの場所に応じて発信通話のルーティングに与える影響を示します。

**PSTN への発信通話の発信者**

||**ルーティングが有効なネットワーク サイトにあるLocation-Based エンドポイント**|**不明なネットワーク サイトにあるユーザー エンドポイント、またはネットワーク ルーティングが有効Location-Basedエンドポイント**|
|:-----|:-----|:-----|
|発信呼び出しの承認  <br/> |ユーザーの音声ポリシーに基づいて通話が承認される  <br/> |ユーザーの音声ポリシーに基づいて通話が承認される  <br/> |
|発信通話のルーティング  <br/> |通話はネットワーク サイトの音声ルーティング ポリシーに従ってルーティングされます。  <br/> |通話はユーザーの音声ポリシーに従ってルーティングされ、Location-Based ルーティングが有効になっていないトランクのみを経由します (使用可能な場合)  <br/> |

### <a name="incoming-calls"></a>着信呼び出し

通話ルーティングが有効になっているユーザーへの着信Location-Basedルーティングは、ユーザーのエンドポイントの場所によって異なります。 着信呼び出しのルーティングは、次の方法で影響を受ける。 ユーザーが Location-Based ルーティングが有効なネットワーク サイトにあるエンドポイントへの着信呼び出しを行い、そのエンドポイントが PSTN ゲートウェイと同じネットワーク サイトにある場合、通話はルーティングされます。 ユーザーが Location-Based ルーティングが有効なネットワーク サイトにあるエンドポイントへの着信呼び出しを行い、そのエンドポイントが PSTN ゲートウェイとは別のネットワーク サイトにある場合、通話はルーティングされません。 着信通話の発信元である PSTN ゲートウェイと同じネットワーク サイトにエンドポイントがない場合、着信呼び出しはユーザーのボイスメールに直接ルーティングされ、着信通知が呼び出し先に送信されます。

Location-Based ルーティングが有効になっているユーザーの着信転送設定は引き続き適用されます。ただし、転送される通話はユーザーの Location-Based ルーティング制限の対象になります。

次の表は、通話Location-Basedのエンドポイントの場所に応じて、通話のルーティングが着信通話のルーティングにどのように影響するかを示しています。 PSTN ゲートウェイのネットワーク サイトは Location-Based ルーティングに対して有効であり、Location-Based ルーティングでは、同じネットワーク サイト内のエンドポイントへの PSTN 通話のルーティングのみを許可します。

**PSTN からの着信呼び出しを受信する呼び出し先**

||**PSTN ゲートウェイと同じネットワーク サイトにある呼び出し先のエンドポイント**|**呼び出し先のエンドポイントが PSTN ゲートウェイと同じネットワーク サイトに位置しない**|**不明なネットワーク サイトにある呼び出し先のエンドポイント、または通話ルーティングがLocation-Basedされていない**|
|:-----|:-----|:-----|:-----|
|着信 PSTN 通話のルーティング  <br/> |着信呼び出しが呼び出し先のエンドポイントにルーティングされる  <br/> |着信呼び出しが呼び出し先のエンドポイントにルーティングされない  <br/> |着信呼び出しが呼び出し先のエンドポイントにルーティングされない  <br/> |

### <a name="call-transfers-and-call-forwarding"></a>通話転送と呼び出し転送

PSTN エンドポイントが関与する場合、Location-Based ルーティングは、通話の転送先または転送先の通話先のエンドポイント (転送/転送先) の場所を分析します。 Location-Basedルーティングは、両方のエンドポイントの場所に応じて、通話を転送するか転送するか決定します。

次の表は、PSTN エンドポイントを使用した通話での Skype for Business ユーザーのシナリオを示しています。Skype for Business ユーザーは通話を別の Skype for Business ユーザーに転送します。 転送先のエンドポイントのネットワーク サイトの場所に応じて、Location-Based ルーティングは、通話転送または転送のルーティングに影響します。

**通話転送または転送の開始**

|**通話の転送/転送を開始するユーザー**|**ターゲット エンドポイントが、通話転送または転送を開始するユーザーと同じネットワーク サイトにある**|**ユーザーが通話転送または転送を開始する場合、ターゲット エンドポイントが別のネットワーク サイトにある**|**ターゲット エンドポイントが不明なネットワーク サイトにあるか、ネットワーク サイトでネットワーク ルーティングがLocation-Basedされていない**|
|:-----|:-----|:-----|:-----|
|Skype for Business ユーザー  <br/> |通話の転送または転送が許可される  <br/> |転送または転送を許可しない  <br/> |呼び出しの転送または転送は許可されません  <br/> |

たとえば、PSTN エンドポイントを使用した通話の Skype for Business ユーザーが、同じネットワーク サイトにある別の Skype for Business ユーザーに通話を転送します。 この場合、通話の転送が許可されます。

次の表は、別の Skype for Business ユーザーとの通話での Skype for Business ユーザーのシナリオを示しています。ユーザーの 1 人が通話を PSTN エンドポイントに転送します。 この表では、通話の転送先ユーザーの場所に応じて、通話のルーティングLocation-Based詳細を示します。

**PSTN エンドポイントへの通話転送または転送**

|**通話転送/転送エンドポイント ターゲット**|**同じネットワーク サイト内の Skype for Business ユーザー**|**異なるネットワーク サイトの Skype for Business ユーザー**|**不明なネットワーク サイトまたはネットワーク サイトの Skype for Business ユーザーの一方または両方が、ネットワーク ルーティングに対して有効Location-Basedです。**|
|:-----|:-----|:-----|:-----|
|PSTN エンドポイント  <br/> |転送されたユーザーのサイト音声ルーティング ポリシーで許可されている転送または転送  <br/> |転送されたユーザーのサイト音声ルーティング ポリシーで許可されている転送または転送  <br/> |転送されたユーザーの音声ポリシーによって許可される、通話の転送または転送は、通話ルーティングに対して有効Location-Basedです。  <br/> |

たとえば、同じネットワーク サイトにある別の Skype for Business ユーザーとの通話中の Skype for Business ユーザーは、通話を PSTN エンドポイントに転送し、通話の転送を許可します。

### <a name="simultaneous-ringing"></a>同時呼び出し

呼び出し元が同時呼び出しを有効にした場合、Location-Based ルーティングは呼び出し元の場所と呼び出し元のエンドポイントを分析して、通話をルーティングするかどうかを決定します。

次の表は、同時呼び出しで構成されたユーザーを示しています。同時呼び出しターゲットは、同じネットワーク サイト、別のネットワーク サイト、または不明なネットワーク サイト内のユーザーです。

****

|**PSTN 通話の着信**|**呼び出し先と同じネットワーク サイトにある**|**呼び出し先とは異なるネットワーク サイトにある**|**不明なネットワーク サイトにあるか、ネットワーク ルーティングがLocation-Basedされていない**|
|:-----|:-----|:-----|:-----|
|Skype for Business ユーザー  <br/> |同時呼び出しが許可される  <br/> |同時呼び出しは許可されません  <br/> |同時呼び出しは許可されません  <br/> |

次の表は、同じネットワーク サイト、別のネットワーク サイト、または不明なネットワーク サイトの Skype for Business ユーザー (Skype for Business 発信者) からの通話を示しています。 呼び出し先には、PSTN エンドポイント (携帯電話) が同時呼び出しターゲットとして構成されています。 このシナリオでは、Location-Based ルーティングによって、呼び出し先の同時呼び出し先 (携帯電話) に通話をルーティングするかどうかを決定します。

****

|**同時呼び出しターゲット**|**呼び出し先と同じネットワーク サイトにある**|**呼び出し先とは異なるネットワーク サイトにある**|**不明なネットワーク サイトにあるか、ネットワーク ルーティングがLocation-Basedされていない**|
|:-----|:-----|:-----|:-----|
|PSTN エンドポイント  <br/> |発信者のサイト音声ルーティング ポリシーを介して同時呼び出しを許可する  <br/> |発信者のサイト音声ルーティング ポリシーを介して同時呼び出しを許可する  <br/> |呼び出し元の音声ポリシーを介して許可される同時呼び出しから、通話ルーティングが有効Location-Basedトランクへの呼び出し  <br/> |

### <a name="skype-for-business-cumulative-update-4"></a>Skype for Business 累積更新プログラム 4

累積的な更新プログラム 4 では、以下が表示されます。

- Location-Basedルーティングは、Skype for Business Mobile クライアントを含む音声ポリシー経由で引き続き有効になります。

- Skype for Business Mobile クライアントの呼び出し動作は、クライアントが Location-Based ルーティングと通信クライアントに対して有効になっているかどうかに基づいて行います。 これは静的に設計されています。ただし、状況によっては、Skype for Business Mobile クライアントをローカル PSTN ゲートウェイに関連付け、エスカレーションなどの特定の動作を許可する取り組みがある場合があります。

- OS に関係なく、Skype for Business Mobile クライアントの機能は同じ必要があります。

次の表では、累積的な更新プログラム 4 の後のシナリオについて説明します。

|**場所に基づくルーティング ユーザー**|**その他のユーザー**|**操作**|**結果**|
|:-----|:-----|:-----|:-----|
|Skype for Business Mobile  <br/> |PSTN  <br/> |Skype for Business Mobile は着信 PSTN 通話を受信します。  <br/> |通話は、VoIP ではなく、"作業から通話" (CvW) 経由でルーティングされます。  <br/> |
|Skype for Business Mobile  <br/> |PSTN  <br/> |Skype for Business Mobile は、発信 PSTN 通話を行います。  <br/> |通話は VoIP ではなく CvW 経由でルーティングされます。  <br/> |
|Skype for Business Mobile  <br/> |PSTN  <br/> |Skype for Business Mobile は PSTN 通話中です。 その後、Skype for Business Mobile は通話を別のユーザーまたは連絡先にエスカレートします。  <br/> |ユーザーまたは連絡先が PSTN ゲートウェイ レグにローカルである場合、通話は VoIP 経由でルーティングされます。  <br/> ユーザーまたは連絡先が PSTN ゲートウェイ レグからリモートの場合、通話は CvW 経由でルーティングされます。  <br/> ターゲット ユーザーが PSTN 経由で到達できない場合、通話は失敗します。  <br/> 対象の連絡先が電話会議会議自動応答 (CAA) の場合、通話はブロックされます。  <br/> |
|Skype for Business Mobile  <br/> |Skype for Business クライアントまたはフェデレーション ユーザー  <br/> |Skype for Business Mobile は、別の Skype for Business クライアントまたはフェデレーション ユーザーへの音声通話を開始します。  <br/> |通話は VoIP 経由で完了します。  <br/> |
|Skype for Business Mobile  <br/> |Skype for Business クライアントまたはフェデレーション ユーザー  <br/> | Skype for Business クライアントまたはフェデレーション ユーザーが、Skype for Business Mobile およびルーティング ユーザーへの音声Location-Based開始します。 <br/> |通話は VoIP 経由で完了します。  <br/> |
|Skype for Business Mobile  <br/> |Skype for Business クライアントまたはフェデレーション ユーザー  <br/> |Skype for Business クライアントまたはフェデレーション ユーザーは、Skype for Business Mobile ユーザーへの VoIP 通話を行っています。 どちらのユーザーも、追加の Skype for Business またはフェデレーション ユーザーにエスカレートします。  <br/> |通話は VoIP 経由で完了します。  <br/> |
|Skype for Business Mobile  <br/> |フェデレーション ユーザー  <br/> |フェデレーション ユーザーが Skype for Business Mobile およびルーティング ユーザーに対するLocation-Based呼び出しを行っている。Skype for Business Mobile パーティーは PSTN ユーザーにエスカレートします。  <br/> |呼び出しはブロックされます。  <br/> |
|Skype for Business Mobile  <br/> |フェデレーション ユーザー  <br/> |フェデレーション ユーザーが、Skype for Business Mobile およびルーティング ユーザーへの VoIP Location-Basedしている。いずれかのパーティが CAA 連絡先にエスカレートします。  <br/> |エスカレートされた通話はブロックされ、適切なエラー メッセージが表示されます。  <br/> |
|Skype for Business Mobile  <br/> |フェデレーション ユーザー  <br/> |フェデレーション ユーザーが Skype for Business Mobile Location-Based ルーティング ユーザーへの VoIP 通話を行い、フェデレーション ユーザーが PSTN ユーザーにエスカレートします。  <br/> |このエスカレーションは、フェデレーション ユーザーの Location-Basedルーティングに基づいて許可または禁止されます。 Skype for Business Mobile Location-Based ルーティング ユーザーのアプリケーションは、何も処理を実行しない。  <br/> |

### <a name="delegation"></a>委任

Skype for Business の委任機能は、次の方法Location-Basedルーティングの影響を受ける場合があります。

- Location-Based ルーティングが有効になっている代理人がマネージャーの代わりに通話を行う場合、代理人の音声ポリシーを使用して通話を承認し、代理人のサイト音声ルーティング ポリシーを使用して通話をルーティングします。

- マネージャーへの着信 PSTN 通話の場合、着信の転送または同時呼び出しに適用されるのと同じルールが、通話転送と転送および同時呼び出しのトピックの説明に従って適用されます。

- 代理人が PSTN エンドポイントを同時呼び出し先として設定すると、マネージャーへの着信呼び出しに対して、着信トランクに関連付けられているサイトの音声ルーティング ポリシーが、通話を代理人の PSTN エンドポイントにルーティングするために使用されます。

- 委任の場合、マネージャーと関連する代理人は、通常、同じネットワーク サイトに位置付けられることをお勧めします。

## <a name="other-planning-considerations"></a>計画に関するその他の考慮事項

ルーティングの計画Location-Based、次のシナリオへの影響を考慮する必要があります。

### <a name="disaster-recovery"></a>障害回復

プライマリ プールからバックアップ プールへのフェールオーバー中、および通常の操作をプライマリ プールに復元する場合、障害および復旧手順の間、Location-Based ルーティングは常に適用されたままです。

### <a name="survivable-branch-appliance"></a>存続可能ブランチ アプライアンス

このルーティングLocation-Based構成すると、存続可能ブランチ アプライアンスに関連付けられたゲートウェイを展開する場所の計画に影響します。 SBA に関連付けられているゲートウェイは、存続可能ブランチ アプライアンスと同じネットワーク サイトにある必要があります。そうしないと、存続可能ブランチ アプライアンスにホームのユーザーは、通話ルーティングが構成されている場合Location-Based発信を許可されません。 存続可能ブランチ アプライアンスと中央サイトの間の WAN 接続がダウンした場合、Location-Basedは適用されたままです。

## <a name="client-and-server-support-for-location-based-routing"></a>クライアントとサーバーでのルーティングLocation-Basedサポート

Location-Basedルーティングは Skype for Business Server によって適用されます。 Skype for Business Server は、ユーザーが企業ネットワーク内から接続しているネットワーク サイトを識別できます。 リモート ユーザーは企業ネットワークの外部にあるので、その場所は不明と見なされます。

### <a name="server-support"></a>サーバーのサポート

Location-Basedルーティングでは、特定のトポロジ内のすべてのフロントエンド プールおよび Standard Edition サーバーに Skype for Business Server または Lync Server 2013 CU1 が展開されている必要があります。 これらのバージョンのサーバーがインストールされていない場合、場所に基づくルーティング制限を完全に適用することはできません。

次の表に、サーバーの役割とバージョンの組み合わせを示します。この組み合わせは、Location-Basedです。

****

|**プールのバージョン**|**仲介サーバーのバージョン**|**サポート対象**|
|:-----|:-----|:-----|
|Skype for Business Server または Lync Server 2013 2013 年 2 月の累積的な更新プログラム  <br/> |Skype for Business Server または Lync Server 2013 2013 年 2 月の累積的な更新プログラム  <br/> |はい  <br/> |
|Skype for Business Server または Lync Server 2013 2013 年 2 月の累積的な更新プログラム  <br/> |Lync Server 2013  <br/> |no  <br/> |
|Skype for Business Server または Lync Server 2013 2013 年 2 月の累積的な更新プログラム  <br/> |Lync Server 2010  <br/> |no  <br/> |
|Skype for Business Server または Lync Server 2013 2013 年 2 月の累積的な更新プログラム  <br/> |Office Communications Server 2007 R2  <br/> |no  <br/> |
|Lync Server 2013  <br/> |any  <br/> |no  <br/> |
|Lync Server 2010  <br/> |any  <br/> |no  <br/> |
|Office Communications Server 2007 R2  <br/> |any  <br/> |no  <br/> |

### <a name="client-support"></a>クライアント サポート

次の表に、ルーティングがサポートするLocation-Based示します。

****

|**クライアントの種類**|**サポート対象**|**詳細**|
|:-----|:-----|:-----|
|Skype for Business  <br/> |はい  <br/> ||
|Lync 2013  <br/> |はい  <br/> ||
|Lync 2010  <br/> |はい  <br/> ||
|Office Communicator 2007 R2  <br/> |no  <br/> ||
|Lync Phone Edition  <br/> |はい  <br/> ||
|Lync Attendant  <br/> |はい  <br/> ||
|Lync for Windows 8  <br/> |no  <br/> ||
|Lync Mobile 2013  <br/> |no  <br/> |VoIP は、Lync Mobile 2013 クライアントで VoIP ルーティングが有効になっているユーザーが使用する場合Location-Based必要があります。  <br/> |
|Lync Mobile 2010  <br/> |はい  <br/> ||

> [!NOTE]
> Skype for Business クライアントの VoIP を無効にするには、ip Audio/Video という設定を持つモビリティ ポリシーを割り当て、すべてのユーザーが Location-Based ルーティングを有効にします。 モビリティ ポリシーの詳細については [、「New-CsMobilityPolicy」を参照してください](https://docs.microsoft.com/powershell/module/skype/new-csmobilitypolicy?view=skype-ps)。

## <a name="capabilities-not-supported-by-location-based-routing"></a>デバイス ルーティングでサポートLocation-Based機能

Location-Basedルーティングは、次の種類の操作には適用されません。 Location-Basedは、Skype for Business エンドポイントがこれらの機能を使用して PSTN エンドポイントとやり取りする場合には適用されません。

- 電話会議への PSTN ダイヤルイン

- 応答グループを介した PSTN 通話の着信と発信

- コール パークを介した PSTN 通話のコール パークまたは取得

- アナウンス サービスへの PSTN 通話の着信

- グループ通話ピックアップ経由で取得された着信 PSTN 通話

次のLocation-Based種類の操作にルーティング ルールを適用するには、電話会議のLocation-Based有効にする必要があります。

- 会議からの PSTN ダイヤルアウト

- ピアツーピア音声会話から PSTN エンドポイントが関係する会議へのエスカレーション

- PSTN エンドポイントが関係する取次転送

会議のLocation-Basedルーティングを有効にするには、「 [会議の場所に基づくルーティング」を参照してください](https://technet.microsoft.com/library/e1acb1ba-0ed2-4abf-8a7b-1ca3049e95e3.aspx)。


