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
ms.openlocfilehash: e4503576df8d8e9f3d332cda45eb235d8162cf53
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/18/2020
ms.locfileid: "44786101"
---
# <a name="contoso-case-study-emergency-calling"></a>Contoso のケース スタディ: 緊急通話

緊急通話の可用性と緊急通話に関連する用語を理解するために、緊急対応の住所、場所、緊急対応の場所、および登録済み住所 Contoso は、「緊急通話の管理と動的緊急通話の計画と構成」を確認 &mdash; &mdash; [しました](configure-dynamic-emergency-calling.md)。 [](what-are-emergency-locations-addresses-and-call-routing.md)

このOffice 365プランのユーザーは、緊急通話に対して自動的に有効になります。 ただし、緊急通話のルーティングに動的な場所を使用できるのは、米国の通話プラン ユーザーのみです。 

直接ルーティングの場合、Contoso は、緊急通話をルーティングするために、および場合によってはパートナーの接続に追加の構成が必要なことを学習しました。 管理者は、緊急ルーティング サービス プロバイダー (ERSP) (米国) への接続を構成するか、緊急位置情報識別番号 (ELIN) アプリケーションのセッション ボーダー コントローラー (SBC) を構成する必要があります。

Contoso は、米国および米国外にオフィスを持っています。

- 米国では、Contoso 通話プランのユーザーは、緊急通話のルーティングに動的な場所を使用できます。 

- 米国外では、Contoso は通話プランを使用する一部のサイトと、直接ルーティングを介して電話システムに接続されている一部のサイトを持っています。

## <a name="emergency-calling-use-cases"></a>緊急通話の使用例

Contoso がシステムに接続する方法を決定電話、Contoso は次の緊急通話の使用例を特定しました。 

- [米国の通話プラン ユーザー](#calling-plan-user-in-the-united-states) 

- [米国外の通話プラン ユーザー](#calling-plan-user-outside-of-the-united-states)

- [ダイレクト ルーティングを介して電話システムに接続するユーザー](#user-who-connects-to-phone-system-through-direct-routing )


### <a name="calling-plan-user-in-the-united-states"></a>米国の通話プラン ユーザー  

電話番号を緊急対応の場所に関連付けする必要がある場合の要件があります。 これらの要件を理解するために、Contoso は「プランの呼び出し [に関する考慮事項」を確認しました](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-calling-plans)。 

Contoso は、これらの要件に基づいて、米国内のユーザーに番号が割り当てられると、場所を電話番号に関連付けすることを決定しました。

### <a name="calling-plan-user-outside-of-the-united-states"></a>米国外の通話プラン ユーザー 

緊急対応の場所に電話番号を関連付けする必要がある場合を理解するために、Contoso は「通話プランに関する考慮事項  [」を確認しました](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-calling-plans)。 Contoso は要件に基づいて、次の条件を決定しました。  

-  カナダのユーザーに番号が割り当てられると、その場所と電話番号が関連付けされます。 

- Contoso が緊急対応の場所を割り当てるのは、電話番号が Office 365 から取得された場合、または別のサービス プロバイダーまたは運送業者から番号が転送された場合です。 

### <a name="user-who-connects-to-phone-system-through-direct-routing"></a>ダイレクト ルーティングを介して電話システムに接続するユーザー 

この使用例の緊急ルーティングを計画するために、Contoso は直接ルーティングに関 [する考慮事項を確認しました](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-direct-routing)。 直接ルーティングユーザーは通話プランのユーザーと同じ方法で緊急通話を受信しないので、Contoso は緊急通話を提供する方法を決定する必要があります。 ダイレクト ルーティングは、緊急ルーティング サービス プロバイダー (ERSP) に接続できます。 直接ルーティングには、緊急位置情報識別番号 (ELIN) を含む SBC を含め、SBC を設定できます。   

#### <a name="emergency-routing-service-provider-ersp-considerations"></a>緊急ルーティング サービス プロバイダー (ERSP) に関する考慮事項

緊急ルーティング サービス プロバイダー (ERSP) は、発信者の場所に基づいて緊急通話を自動的にルーティングできます。  

- 緊急ルーティング サービス プロバイダーが直接ルーティング展開に統合されている場合、動的に取得された場所を持つ緊急通話は、その場所を提供するパブリック セーフティ応答ポイント (PSAP) に自動的にルーティングされます。 

- 動的に取得された場所がない緊急通話は、最初に、更新された場所に基づいて適切なディスパッチ センターに通話を接続する前に、ユーザーの現在の場所を決定するために画面が表示されます。 


#### <a name="elin-considerations"></a>ELIN に関する考慮事項

SBC ELIN アプリケーションが直接ルーティング展開に統合されている場合は、緊急対応の住所を電話番号に関連付ける追加の構成手順を実行する必要があります。  

Contoso は、緊急位置情報識別番号 (ELIN) アプリケーションを含むセッション ボーダー コントローラーを使用することを決定しました。  

## <a name="security-desk-notification"></a>セキュリティ デスクの通知

緊急通話が発信された場合にセキュリティ デスクに通知する機能は、Microsoft 通話プランと直接ルーティングの両方電話システム使用できます。 Contoso は、セキュリティ デスク通知の詳細を確認して、これがオフィスで構成される必要かどうかを判断しました  

Contoso は、セキュリティ デスク通知を使用することを決定しました。

## <a name="configuration"></a>構成 

Contoso は、「動的緊急通話を構成 [する」の手順に従って、次の手順を実行](configure-dynamic-emergency-calling.md) しました。 

- 緊急対応の住所を割り当てる 

- ネットワーク設定を構成する 

- Location Information Service の構成 

- 緊急ポリシーを構成する 

- ユーザーとサイトを有効にする 

- 緊急通話をテストする 

動的緊急通話が構成された後、Contoso は適切なユーザーに場所を割り当てる必要がありました。  

- 組織の緊急対応の場所を追加、変更、または削除するには、「組織の緊急対応の場所を追加、変更、または削除する」の手順 [に従いました。](add-change-remove-emergency-location-organization.md)

- 建物、フロア、オフィスの場所を作成するために、Contoso は「緊急対応の場所を追加、変更、または削除する」の手順 [に従いました](add-change-remove-emergency-place-organization.md) 。 

- 緊急対応の場所を割り当てるには、「ユーザーの緊急対応の場所を割り当てるまたは変更する」 [の手順に従いました](assign-change-emergency-location-user.md)。 

 