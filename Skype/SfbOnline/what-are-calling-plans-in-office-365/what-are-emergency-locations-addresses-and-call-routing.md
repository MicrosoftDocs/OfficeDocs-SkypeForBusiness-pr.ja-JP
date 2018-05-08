---
title: 緊急対応の場所、アドレス、通話ルーティングの概要
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: 589bf5f5-490a-4215-8588-99bab7d33e31
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Priority
f1keywords:
- ms.lync.lac.AddressAndLocation
ms.custom:
- Calling Plans
description: 'Learn what emergency address, location, and emergency call routing are, and how to plan and assign them to your users. '
ms.openlocfilehash: 94613a9c001183dd96df98c5e46e0fdb77021dfa
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="what-are-emergency-locations-addresses-and-call-routing"></a>緊急対応の場所、アドレス、通話ルーティングの概要

Office 365 のプランの呼び出しを構成するときことが必要なすべてのユーザーを電話番号を取得するかするとき、または各電話番号に割り当てられた緊急時のアドレスは、緊急通話をサポートするためにユーザーに割り当てられたのです。 電話番号に緊急のアドレスを割り当てる前に、緊急時のアドレスを作成および検証される必要があります。 確認では、緊急時のアドレスが認識されると、緊急対応サービスで使用できる正しい形式であることが保証します。 必要に応じて、ユーザーの特定の場所を提供する緊急時のアドレス内の場所を追加できます。 たとえば、緊急の場所では、フロア、ウィング、または緊急時の特定のアドレスにリンクされている office に可能性があります。 場合でも、緊急時のアドレスが検証されると、場所がないです。
  
## <a name="what-are-emergency-addresses"></a>緊急対応の住所の概要

緊急アドレスですが必要です有効な電話番号の国または地域に依存することが必要な場合は。 アメリカ合衆国のいくつかがユーザーに割り当てられている場合、緊急時のアドレスが**必要**です。 他の国など、ヨーロッパ、中東、およびアフリカ (EMEA) の緊急時のアドレスが**必要**から Office 365 を使用するか、別のサービスプロバイダーまたは通信業者から転送電話番号を取得する場合です。
  
緊急時のアドレスは、都市の住所、番地、または物理アドレスと呼びます場合があります。 緊急対応の住所は、組織の事業所の場所を示す所在地住所または行政上の住所のことです。 などの適切な派遣機関への緊急電話をルーティングして、緊急時の呼び出し元を検索するを支援する*12345 北 Main Street、小田急サザンタワー*が使用されるアドレスです。 通常、事業所の所在地が複数である場合は複数の緊急対応の住所が必要になります。
  
緊急アドレスを検証するには、適正で緊急対応サービスの正しい形式であることを確認することが含まれます。 作成し、検証されていない緊急のアドレスを保存することが検証済みのアドレスのみをユーザーに関連付けることができます。 緊急対応の住所が検証および保存されると、ユーザーに割り当てることができます。 保存および検証した緊急対応の住所を変更する必要がある場合は、新しい緊急対応の住所を作成する必要があります。
  
## <a name="what-are-emergency-locations"></a>緊急対応の場所の概要

緊急の場所は、建物内のより正確な場所を提供する緊急時のアドレスに関連付けられます。 緊急対応の場所には、ユーザーがいる場所の階数、建物の棟、オフィスの番号などを使用できます。 緊急アドレスに関連付けられている場所の無制限の数を持つことができます。 
  
ユーザーに緊急対応の住所を割り当てる場合、実際にはそれは住所の割り当て時に参照する場所 ID です。 場所の ID には、参照先の緊急アドレス (番地または都市アドレス) が含まれています。 建物内の場所が不要である場合に対応するため、すべての緊急対応の住所には、既定の緊急対応の場所が含まれています。 
  
## <a name="what-is-emergency-call-routing"></a>緊急通話ルーティングの概要

緊急時のアドレスと場所は、緊急時の最初のレスポンダーをディスパッチする場合、適切なディスパッチ センターへの緊急通話のルーティングの処理中に使用されます。 Skype のビジネス ユーザーは、緊急電話番号をダイヤルするときは、国または地域によって異なりますサービス公開の安全性への応答ポイント (PSAP) に呼び出しをルーティングする方法。 米国、英国などの一部の国での呼び出しは、適切なディスパッチ ・ センターへの呼び出しを接続する前にユーザーの現在の場所を決定するスクリーニング最初。 呼び出しは、他の国/地域、緊急時の呼び出し元に関連付けられている電話番号にサービスを提供する派遣センターに直接ルーティングされます。
  
## <a name="creating-adding-and-assigning-emergency-locations-and-addresses-to-your-users"></a>作成、追加、および緊急時の場所とアドレスをユーザーに割り当てる

1. **緊急の場所の計画**最初の手順は、緊急時の場所を計画するが。 すべての物理アドレスの一覧を表示する必要があります。 緊急時のアドレスの場所が必要かどうかと、その場合に、次に、決定に基づきは何か。 たとえば、ビジネスでは、3 のオフィス ビル各 4 つのフロアではと、フロア 1 ~ 4 のそれぞれの場所として記載されていると、3 つの緊急アドレスする必要があること可能性があります。
    
2. **緊急対応の場所を作成および検証する** 次の手順では、緊急対応の住所を作成して検証します。 緊急対応の住所を作成すれば、それを検証できます。 緊急アドレスを作成するには、[追加または削除する組織の緊急時の対処](add-or-remove-an-emergency-address-for-your-organization.md)を参照してください。
    
    > [!IMPORTANT]
    > 住所の検証では、住所が正規の住所で、形式が正しいことが確認されます。 緊急対応の住所の一部が、市区町村名の誤入力などで正しくない場合でも、検証をパスすることがあります。 検証プロセスでは、適切な緊急派遣センターに通話をルーティングするために十分な情報が含まれるかどうかを判定するために、指定された住所のすべての情報を使用します。 場合は、検証で返され、電話番号に割り当てることができます。 
  
3. **電話番号を取得します。**次に、ユーザーの電話番号を取得します。 この操作を行うには、Office 365 から新しい電話番号を取得するか、既存の電話番号を Office 365 に「移行」または転送します。 詳細な手順を参照してください[Office 365 に電話番号を転送](transfer-phone-numbers-to-office-365.md)します。
    
4. **電話番号を割り当てる** 最後の手順では、ユーザーが通話を発信/受信できるようにします。 これには、そのユーザーに電話番号を割り当てる必要があります。 [割り当て、変更、またはユーザーの電話番号を削除する](assign-change-or-remove-a-phone-number-for-a-user.md)電話番号を割り当てるにを参照してください。

> [!NOTE]
> 無料電話番号

    
## <a name="related-topics"></a>[米国 (無料の電話番号) 用の承認状 (LOA) (v.2.0)](http://download.microsoft.com/download/F/0/1/F01AE714-0F3C-4D9D-B41A-DFD180EC1622/Letter of Authorization %28LOA%29 for the U.S. (Toll Free numbers) (v.3.1) (en-US).pdf)
[住所検証について](what-is-address-validation.md)

[通話プランで使用されるさまざまな種類の電話番号](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[緊急通話の利用条件](../legal-and-regulatory/emergency-calling-terms-and-conditions.md)

[Skype for Business Online: 緊急通話の免責事項ラベル](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

  
 