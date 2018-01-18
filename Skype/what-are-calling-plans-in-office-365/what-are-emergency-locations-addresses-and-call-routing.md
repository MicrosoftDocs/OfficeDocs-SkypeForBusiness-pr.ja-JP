---
title: "緊急対応の場所、アドレス、通話ルーティングの概要"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 589bf5f5-490a-4215-8588-99bab7d33e31
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
ROBOTS: None
f1keywords: ms.lync.lac.AddressAndLocation
ms.custom:
- Calling Plans
- Strat_SB_PSTN
description: 'Learn what emergency address, location, and emergency call routing are, and how to plan and assign them to your users. '
ms.openlocfilehash: b6f9ffcbba68a7892a137a68565de97fe390d00f
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/15/2017
---
# <a name="what-are-emergency-locations-addresses-and-call-routing"></a>緊急対応の場所、アドレス、通話ルーティングの概要

Office 365 のプランの呼び出しを構成するときことが必要なすべてのユーザーを電話番号を取得するかするとき、または各電話番号に割り当てられた緊急時のアドレスは、緊急通話をサポートするためにユーザーに割り当てられたのです。 電話番号に緊急のアドレスを割り当てる前に、緊急時のアドレスを作成および検証される必要があります。 確認では、緊急時のアドレスが認識されると、緊急対応サービスで使用できる正しい形式であることが保証します。 必要に応じて、ユーザーの特定の場所を提供する緊急時のアドレス内の場所を追加できます。 たとえば、緊急の場所では、フロア、ウィング、または緊急時の特定のアドレスにリンクされている office に可能性があります。 場合でも、緊急時のアドレスが検証されると、場所がないです。
  
## <a name="what-are-emergency-addresses"></a>緊急対応の住所の概要

緊急アドレスですが必要です有効な電話番号の国または地域に依存することが必要な場合は。 アメリカ合衆国のいくつかがユーザーに割り当てられている場合、緊急時のアドレスが**必要**です。 他の国など、ヨーロッパ、中東、およびアフリカ (EMEA) の緊急時のアドレスが**必要**から Office 365 を使用するか、別のサービスプロバイダーまたは通信業者から転送電話番号を取得する場合です。
  
緊急時のアドレスは、都市の住所、番地、または物理アドレスと呼びます場合があります。 組織のビジネスの場所の住所や都市のアドレスです。 などの適切な派遣機関への緊急電話をルーティングして、緊急時の呼び出し元を検索するを支援する*12345 北 Main Street、小田急サザンタワー*が使用されるアドレスです。 1 つ以上の物理的な事業所では, 緊急時の 1 つ以上のアドレスを指定する必要ことがあります。
  
緊急アドレスを検証するには、適正で緊急対応サービスの正しい形式であることを確認することが含まれます。 作成し、検証されていない緊急のアドレスを保存することが検証済みのアドレスのみをユーザーに関連付けることができます。 緊急アドレスを検証して保存して後、ユーザーに割り当てることができます。 保存されている検証済みの緊急アドレスを変更する場合は、新規に作成する必要があります。
  
## <a name="what-are-emergency-locations"></a>緊急対応の場所の概要

緊急の場所は、建物内のより正確な場所を提供する緊急時のアドレスに関連付けられます。 緊急の場所は、通常フロア、建物の翼、またはオフィスの番号は、ユーザーです。 緊急アドレスに関連付けられている場所の無制限の数を持つことができます。 
  
ユーザー緊急アドレスの割り当て、ときに、実際には、アドレスを割り当てるときに参照されている場所 ID です。 場所の ID には、参照先の緊急アドレス (番地または都市アドレス) が含まれています。 緊急時の既定の場所は、建物の場所が必要ないときにケースの緊急時のアドレスに含まれています。 
  
## <a name="what-is-emergency-call-routing"></a>緊急通話ルーティングの概要

緊急時のアドレスと場所は、緊急時の最初のレスポンダーをディスパッチする場合、適切なディスパッチ センターへの緊急通話のルーティングの処理中に使用されます。 Skype のビジネス ユーザーは、緊急電話番号をダイヤルするときは、国または地域によって異なりますサービス公開の安全性への応答ポイント (PSAP) に呼び出しをルーティングする方法。 米国、英国などの一部の国での呼び出しは、適切なディスパッチ ・ センターへの呼び出しを接続する前にユーザーの現在の場所を決定するスクリーニング最初。 呼び出しは、他の国/地域、緊急時の呼び出し元に関連付けられている電話番号にサービスを提供する派遣センターに直接ルーティングされます。
  
## <a name="creating-adding-and-assigning-emergency-locations-and-addresses-to-your-users"></a>作成、追加、および緊急時の場所とアドレスをユーザーに割り当てる

1. **緊急の場所の計画**最初の手順は、緊急時の場所を計画するが。 すべての物理アドレスの一覧を表示する必要があります。 緊急時のアドレスの場所が必要かどうかと、その場合に、次に、決定に基づきは何か。 たとえば、ビジネスでは、3 のオフィス ビル各 4 つのフロアではと、フロア 1 ~ 4 のそれぞれの場所として記載されていると、3 つの緊急アドレスする必要があること可能性があります。
    
2. **を作成し、緊急時の場所を検証**次の手順を作成し、緊急時の住所を確認します。 緊急アドレスを作成するときを検証することができます。 緊急アドレスを作成するには、[追加または削除する組織の緊急時の対処](add-or-remove-an-emergency-address-for-your-organization.md)を参照してください。
    
    > [!IMPORTANT]
    > 番地または都市のアドレスを検証するには、正当で正しい形式であることを確認することが含まれます。 入力ミスをした、都市の名前など、部分的に正しい緊急のアドレスがまだパス検証で渡すことことが可能です。 検証プロセスは、適切な緊急派遣センターへの呼び出しをルーティングするのにための十分な情報が含まれているかどうか、指定したアドレスのすべての部分を使用します。 場合は、検証で返され、電話番号に割り当てることができます。 
  
3. **電話番号を取得します。**次に、ユーザーの電話番号を取得します。 これは、「移植」、Office 365 で、既存の電話番号に転送するかを Office 365 から新しい電話番号を取得することによって行うことができます。 詳細な手順を参照してください[Office 365 に電話番号を転送](transfer-phone-numbers-to-office-365.md)します。
    
4. **電話番号を割り当てる**最後の手順は、電話の通話を送受信するユーザーを有効にするのには。 これを行うには、各ユーザーに電話番号を割り当てる必要があります。 [割り当て、変更、またはユーザーの電話番号を削除する](assign-change-or-remove-a-phone-number-for-a-user.md)電話番号を割り当てるにを参照してください。

> [!NOTE]
> これよりも、他の電話番号を取得する場合は、[ビジネス製品の管理のヘルプのサポートに連絡](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)してください。

    
## <a name="related-topics"></a>関連トピック
[アドレスの検証とは何ですか。](what-is-address-validation.md)

[さまざまな種類の計画を呼び出すための電話番号](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[緊急通話の利用条件](../what-are-calling-plans-in-office-365/emergency-calling-terms-and-conditions.md)

[Skype for Business Online: 緊急通話の免責事項ラベル](https://go.microsoft.com/fwlink/?LinkID=692099)
