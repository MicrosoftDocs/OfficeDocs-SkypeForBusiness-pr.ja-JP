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
ms.openlocfilehash: e4503576df8d8e9f3d332cda45eb235d8162cf53
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/18/2020
ms.locfileid: "44786101"
---
# <a name="contoso-case-study-emergency-calling"></a>Contoso のケーススタディ: 緊急通話

緊急通話の利用可否、緊急通報の &mdash; 緊急対応の住所、場所、緊急対応の場所、および登録済みの住所については、「緊急通話の管理」と「緊急 &mdash; 通報の[計画と設定](configure-dynamic-emergency-calling.md)」を確認してください。 [Manage emergency calling](what-are-emergency-locations-addresses-and-call-routing.md)

Office 365 では、通話プランのユーザーは緊急通話に対して自動的に有効になります。 ただし、アメリカ国内の通話プランのユーザーのみが、緊急通話のルーティングに動的な場所を使用できます。 

直接ルーティングの場合、Contoso は緊急通話をルーティングするために追加の構成が必要であるということを伝えましたが、パートナー接続の場合もあります。 管理者は、緊急ルーティングサービスプロバイダ (ERSP) (米国) への接続を構成するか、緊急対応の位置情報識別番号 (ELIN) アプリケーションのセッションボーダーコントローラー (SBC) を構成する必要があります。

Contoso には米国と米国外の支社があります。

- 米国では、Contoso 通話プランのユーザーは、緊急通話のルーティングに動的な場所を使用できます。 

- 米国外では、Contoso には、通話プランと、電話システムに接続されたいくつかのサイトを、直接ルーティング経由で使用しているサイトがあります。

## <a name="emergency-calling-use-cases"></a>緊急通話の使用例

Contoso が電話システムに接続する方法を決定したら、Contoso は次の緊急通話のユースケースを特定しました。 

- [米国の通話プランユーザー](#calling-plan-user-in-the-united-states) 

- [米国外への通話プランユーザー](#calling-plan-user-outside-of-the-united-states)

- [直接ルーティングを介して電話システムに接続しているユーザー](#user-who-connects-to-phone-system-through-direct-routing )


### <a name="calling-plan-user-in-the-united-states"></a>米国の通話プランユーザー  

緊急対応の場所に電話番号を関連付ける必要がある場合は、条件があります。 これらの要件について理解するために、Contoso は[通話プランの考慮事項について](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-calling-plans)検討しています。 

これらの要件に基づき、Contoso は、米国のユーザーに番号が割り当てられたときに、その場所を電話番号に関連付けます。

### <a name="calling-plan-user-outside-of-the-united-states"></a>米国外への通話プランユーザー 

緊急対応の場所に電話番号が関連付けられている必要があるタイミングを理解するために、Contoso は[通話プランの考慮事項につい](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-calling-plans)て検討しています。 Contoso は要件に基づいて、次のことを決定しました。  

-  Contoso は、カナダのユーザーに番号が割り当てられたときに、その場所を電話番号に関連付けます。 

- Contoso は、電話番号が Office 365 から取得された場合、または別のサービスプロバイダーまたは携帯電話会社から電話番号が移行された場合に、緊急対応の場所を割り当てます。 

### <a name="user-who-connects-to-phone-system-through-direct-routing"></a>直接ルーティングを介して電話システムに接続しているユーザー 

このユースケースで緊急ルーティングを計画するには、Contoso が[直接ルーティングの考慮事項](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-direct-routing)を確認します。 直接ルーティングユーザーは、プランのユーザーと同じ方法で緊急電話を受けることはできないため、Contoso は緊急通話の提供方法を決定する必要がありました。 ダイレクトルーティングは、緊急ルーティングサービスプロバイダ (ERSP) に接続できます。 直接ルーティングには、緊急対応の場所識別番号 (ELIN) を含む SBC も含まれています。   

#### <a name="emergency-routing-service-provider-ersp-considerations"></a>緊急ルーティングサービスプロバイダ (ERSP) に関する考慮事項

緊急ルーティングサービスプロバイダ (ERSPs) では、発信者の場所に基づいて緊急通話が自動的にルーティングされます。  

- 緊急ルーティングサービスプロバイダーが、ダイレクトルーティングの展開に統合されている場合は、動的に取得した場所での緊急通話は、その場所を提供する公共の安全な応答ポイント (PSAP) に自動的にルーティングされます。 

- 動的に取得した場所のない緊急通話は、更新された場所に基づいて適切なディスパッチセンターに通話を接続する前に、ユーザーの現在の位置を特定するために最初にスクリーニングされます。 


#### <a name="elin-considerations"></a>ELIN に関する考慮事項

SBC ELIN アプリケーションがダイレクトルーティング展開に統合されている場合は、緊急対応の住所を電話番号に関連付けるために、追加の構成手順を実行する必要があります。  

Contoso は、緊急対応の場所識別番号 (ELIN) アプリケーションを含むセッション境界コントローラーの使用を決定しました。  

## <a name="security-desk-notification"></a>セキュリティデスクの通知

緊急通話が行われたときに、セキュリティデスクに通知する機能は、Microsoft の通話プランと電話システムによる直接ルーティングの両方で利用できます。 Contoso はセキュリティデスク通知の詳細を確認して、オフィスでこれを構成する必要があるかどうかを判断しました。  

Contoso はセキュリティデスクの通知を使用することを決定しました。

## <a name="configuration"></a>構成 

Contoso は以下の手順に従って、[[動的な緊急通話の構成](configure-dynamic-emergency-calling.md): 

- 緊急対応の住所を割り当てる 

- ネットワーク設定を構成する 

- 位置情報サービスを構成する 

- 緊急ポリシーを構成する 

- ユーザーとサイトを有効にする 

- 緊急通話のテスト 

動的な緊急通話が構成されると、Contoso はその場所を適切なユーザーに割り当てる必要がありました。  

- 組織の緊急対応の場所を追加、変更、または削除するには、「[組織の緊急対応の場所を追加、変更、または削除](add-change-remove-emergency-location-organization.md)する」の手順に従います。

- 建物、床、オフィスの場所を作成するために、Contoso は[緊急対応の場所を追加、変更、または削除](add-change-remove-emergency-place-organization.md)する手順に従います。 

- 緊急対応の場所を割り当てるには、「[ユーザーの緊急対応の場所を割り当てまたは変更](assign-change-emergency-location-user.md)する」の手順に従ってください。 

 