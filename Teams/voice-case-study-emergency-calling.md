---
title: 'Teams音声 Contoso のケース スタディ: 緊急通話'
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
description: '多国籍企業の音声ケース スタディのTeams : 緊急通話'
appliesto:
- Microsoft Teams
ms.openlocfilehash: 409293fd463b5cbc2792f6e6f485df6212fa6746f1ac445bd5ebd71aa01e87ed
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54296414"
---
# <a name="contoso-case-study-emergency-calling"></a>Contoso のケース スタディ: 緊急通話

緊急通報の可用性と緊急通報&mdash;に関連する用語を理解するために、Emergency Address、Place、Emergency Location、Registered addressContoso&mdash; のレビュー「 [緊急通話の管理](what-are-emergency-locations-addresses-and-call-routing.md) と [動的緊急通報の計画と構成](configure-dynamic-emergency-calling.md)」を参照しました。

Office 365では、通話プランのユーザーが緊急通話に対して自動的に有効になります。 ただし、緊急通報のルーティングに動的な場所を使用できるのは、米国内の計画ユーザーの呼び出しのみです。 

ダイレクト ルーティングの場合、Contoso は、緊急通話のルーティングと、場合によってはパートナー接続のために追加の構成が必要であることを学習しました。 管理者は、緊急ルーティング サービス プロバイダー (ERSP) (米国) への接続を構成するか、緊急場所識別番号 (ELIN) アプリケーションのセッション ボーダー コントローラー (SBC) を構成する必要があります。

Contoso は、米国および米国の外部にオフィスを持っています。

- 米国では、Contoso 通話プランのユーザーは、緊急通報のルーティングに動的な場所を使用できます。 

- 米国の外部には、通話プランを使用するサイトと、ダイレクト ルーティングを介して電話システムに接続されているサイトがあります。

## <a name="emergency-calling-use-cases"></a>緊急通報のユース ケース

Contoso が電話 システムに接続する方法を決定した後、Contoso は次の緊急通話のユース ケースを特定しました。 

- [米国でプラン ユーザーを呼び出す](#calling-plan-user-in-the-united-states) 

- [米国の外部でプラン ユーザーを呼び出す](#calling-plan-user-outside-of-the-united-states)

- [ダイレクト ルーティングを使用して電話システムに接続するユーザー](#user-who-connects-to-phone-system-through-direct-routing )


### <a name="calling-plan-user-in-the-united-states"></a>米国でプラン ユーザーを呼び出す  

電話番号を緊急の場所に関連付ける必要がある場合の要件があります。 これらの要件を理解するために、Contoso は [プランの呼び出しに関する考慮事項を](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-calling-plans)確認しました。 

これらの要件に基づいて、Contoso は、番号が米国のユーザーに割り当てられると、電話番号に場所を関連付けることにしました。

### <a name="calling-plan-user-outside-of-the-united-states"></a>米国の外部でプラン ユーザーを呼び出す 

電話番号を緊急対応の場所に関連付ける必要があるタイミングを理解するために、Contoso は計画の  [呼び出しに関する考慮事項を](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-calling-plans)確認しました。 要件に基づいて、Contoso は次のことを決定しました。  

-  Contoso は、カナダのユーザーに番号が割り当てられると、その場所を電話番号に関連付けます。 

- Contoso は、電話番号がOffice 365から取得されたとき、または番号が別のサービス プロバイダーまたは通信事業者から転送されたときに、緊急の場所を割り当てます。 

### <a name="user-who-connects-to-phone-system-through-direct-routing"></a>ダイレクト ルーティングを使用して電話システムに接続するユーザー 

このユース ケースの緊急ルーティングを計画するために、Contoso は [ダイレクト ルーティングに関する考慮事項を](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-direct-routing)確認しました。 Direct Routing ユーザーは通話プランのユーザーと同じ方法で緊急通話を受け取らないため、Contoso は緊急通話を提供する方法を決定する必要がありました。 ダイレクト ルーティングは、緊急ルーティング サービス プロバイダー (ERSP) に接続できます。 ダイレクト ルーティングには、緊急場所識別番号 (ELIN) を含む SBC を指定することもできます。   

#### <a name="emergency-routing-service-provider-ersp-considerations"></a>緊急ルーティング サービス プロバイダー (ERSP) に関する考慮事項

緊急ルーティング サービス プロバイダー (ERSP) は、発信者の場所に基づいて緊急通報を自動的にルーティングできます。  

- 緊急ルーティング サービス プロバイダーがダイレクト ルーティング展開に統合されている場合、動的に取得された場所を持つ緊急通話は、その場所にサービスを提供するパブリック セーフティ 応答ポイント (PSAP) に自動的にルーティングされます。 

- 動的に取得された場所のない緊急通話は、更新された場所に基づいて適切なディスパッチ センターに呼び出しを接続する前に、ユーザーの現在の場所を決定するために最初にスクリーニングされます。 


#### <a name="elin-considerations"></a>ELIN に関する考慮事項

SBC ELIN アプリケーションがダイレクト ルーティング展開に統合されている場合は、緊急アドレスを電話番号に関連付けるために追加の構成手順を実行する必要があります。  

Contoso は、緊急場所識別番号 (ELIN) アプリケーションを含むセッション ボーダー コントローラーを使用することにしました。  

## <a name="security-desk-notification"></a>セキュリティ デスクの通知

緊急通話が発信されたときにセキュリティ デスクに通知する機能は、Microsoft 通話プランと電話システムダイレクト ルーティングの両方で使用できます。 Contoso は、セキュリティ デスクの通知の詳細を確認して、これがオフィスで構成される必要があるかどうかを判断しました  

Contoso は、セキュリティ デスク通知を使用することにしました。

## <a name="configuration"></a>構成 

Contoso は、「 [動的緊急通報を構成](configure-dynamic-emergency-calling.md) する」の手順に従いました。 

- 緊急対応アドレスを割り当てる 

- ネットワーク設定を構成する 

- 場所情報サービスを構成する 

- 緊急ポリシーを構成する 

- ユーザーとサイトを有効にする 

- 緊急通報のテスト 

動的緊急通報が構成された後、Contoso は適切なユーザーに場所を割り当てる必要があります。  

- Contoso は、組織の緊急対応の場所を追加、変更、または削除するために、組織の[緊急対応の場所を追加、変更、または削除する](add-change-remove-emergency-location-organization.md)手順に従いました

- Contoso は、建物、フロア、オフィスの場所を作成するために、「緊急対応の場所を [追加、変更、または削除する](add-change-remove-emergency-place-organization.md) 」の手順に従いました。 

- Contoso は緊急対応の場所を割り当てるには、「 [ユーザーの緊急対応の場所を割り当てるか変更する](assign-change-emergency-location-user.md)」の手順に従いました。 

 
