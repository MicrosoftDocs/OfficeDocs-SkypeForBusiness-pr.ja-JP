---
title: 緊急対応の場所、アドレス、通話ルーティングとは何ですか?
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: 589bf5f5-490a-4215-8588-99bab7d33e31
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords:
- ms.teamsadmincenter.locations.emergencyaddresses.overview
- ms.lync.lac.AddressAndLocation
ms.custom:
- Calling Plans
description: 'Learn what emergency address, location, and emergency call routing are, and how to plan and assign them to your users. '
ms.openlocfilehash: 979fab1cd099d568278efd61d06a3f8a75b04541
ms.sourcegitcommit: d4e69d46de564c445feb855cbee55954a7063bba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/21/2019
ms.locfileid: "36483867"
---
# <a name="what-are-emergency-locations-addresses-and-call-routing"></a>緊急対応の場所、アドレス、通話ルーティングとは何ですか?

Office 365 で通話プランを構成する場合、電話番号を取得するか、緊急通話をサポートするようにユーザーに割り当てるときに、各電話番号に緊急対応の住所を割り当てる必要があります。 電話番号に緊急対応の住所を割り当てる前に、緊急対応の住所を作成して検証する必要があります。 検証により、緊急対応の住所が認識され、緊急対応サービスで使用できる正しい形式であることが確認されます。 必要に応じて、緊急対応のアドレス内に場所を追加して、ユーザーにより具体的な場所を提供することができます。 たとえば、緊急対応の場所は、特定の緊急対応の住所にリンクされているフロア、翼、またはオフィスの場合があります。 緊急対応の住所が検証されますが、場所は確認できません。
  
## <a name="what-are-emergency-addresses"></a>緊急対応の住所の概要

有効な電話番号には緊急対応の住所が必要ですが、必要な場合は国/地域によって異なります。 米国では、ユーザーに電話番号が割り当てられている場合は、緊急対応の住所が必要です。 ヨーロッパ、中東、アフリカ (EMEA) などのその他の国では、Office 365 から電話番号を取得する場合、または別のサービスプロバイダーまたは携帯電話会社から電話番号を移行する場合は、緊急対応の住所が必要です。
  
緊急対応の住所は、都市の住所、住所、または住所と呼ばれることがあります。 緊急対応の住所は、組織の事業所の場所を示す所在地住所または行政上の住所のことです。 たとえば、住所*12345 北米、レドモンド、98052ワシントンの住所*は、適切なディスパッチ機関に緊急通報をルーティングするために使用され、緊急通報を見つけるのに役立ちます。 通常、事業所の所在地が複数である場合は複数の緊急対応の住所が必要になります。
  
緊急対応の住所を検証するには、緊急対応のサービス用に正当で適切に書式設定されていることを確認する必要があります。 有効になっていない緊急対応の住所を作成して保存することもできますが、ユーザーに関連付けることができるのは検証された住所のみです。 緊急対応の住所が検証および保存されると、ユーザーに割り当てることができます。 保存および検証した緊急対応の住所を変更する必要がある場合は、新しい緊急対応の住所を作成する必要があります。
  
## <a name="what-are-emergency-locations"></a>緊急対応の場所の概要

緊急対応の場所は、建物内の正確な位置情報を得るために、緊急対応の住所と関連付けられています。 緊急対応の場所には、ユーザーがいる場所の階数、建物の棟、オフィスの番号などを使用できます。 緊急対応の住所には、限定された場所を含めることができます。 
  
緊急対応の住所をユーザーに割り当てると、実際には、その住所を割り当てたときに参照される場所 ID が割り当てられます。 場所 ID には、参照されている緊急対応の住所 (住所または都市の住所) が含まれます。 建物内の場所が不要な場合、緊急対応の住所には既定の緊急対応の場所が含まれます。 
  
## <a name="what-is-emergency-call-routing"></a>緊急通話ルーティングの概要

緊急対応の住所と場所は、緊急通話を適切なディスパッチセンターにルーティングするプロセスの間に使用されます。 Teams または Skype for Business のユーザーが緊急電話番号をダイヤルすると、その通話が公開される公共の安全な応答ポイント (PSAP) にどのようにルーティングされるかは、国または地域によって異なります。 米国や英国などの一部の国では、通話を適切なディスパッチセンターに接続する前に、ユーザーの現在の位置情報を確認するために、通話が最初に表示されます。 その他の国/地域では、通話は、緊急通報に関連付けられた電話番号を提供するディスパッチセンターに直接送信されます。
  
## <a name="create-add-and-assign-emergency-locations-and-addresses-to-your-users"></a>ユーザーの緊急対応の場所と住所の作成、追加、割り当てを行う

1. **緊急対応の場所を計画**します。 最初の手順は、緊急対応の場所を計画することです。 すべての物理アドレスを一覧表示する必要があります。 それに基づいて、緊急対応の住所の場所が必要かどうかを判断し、必要に応じてその内容を確認します。 たとえば、4階で3つのオフィスで事業を行っている場合、3つの緊急対応の住所が必要になることもあります。各階1-4 はそれぞれの場所として表示されています。
    
2. **緊急対応の場所を作成して検証**します。 次の手順は、緊急対応の住所を作成して検証することです。 緊急対応の住所を作成すれば、それを検証できます。 緊急対応の住所を作成するには、「[組織の緊急対応の住所を追加または削除](/SkypeForBusiness/what-are-calling-plans-in-office-365/add-or-remove-an-emergency-address-for-your-organization)する」を参照してください。
    
    > [!IMPORTANT]
    > 住所の検証では、住所が正規の住所で、形式が正しいことが確認されます。 市区町村の間違った名前など、部分的に正しい緊急対応の住所を入力しても、引き続き検証に合格する可能性があります。 検証プロセスでは、適切な緊急派遣センターに通話をルーティングするために十分な情報が含まれるかどうかを判定するために、指定された住所のすべての情報を使用します。 その場合は、検証済みとして返され、電話番号に割り当てることができます。 
  
3. **電話番号を取得**します。 次の手順は、ユーザーの電話番号を取得することです。 この操作を行うには、Office 365 から新しい電話番号を取得するか、既存の電話番号を Office 365 に「移行」または転送します。 完全な手順については、「 [Office 365 に電話番号を転送](transfer-phone-numbers-to-office-365.md)する」を参照してください。
    
4. **電話番号を割り当て**ます。 最後の手順では、ユーザーが電話をかけたり受けたりすることができるようにします。 これには、そのユーザーに電話番号を割り当てる必要があります。 電話番号を割り当てるには、「[ユーザーに対して電話番号を割り当て、変更、または削除](/microsoftteams/assign-change-or-remove-a-phone-number-for-a-user)する」を参照してください。

> [!NOTE]
> さらに追加で電話番号が必要な場合は、「[一般法人向け Office 365 のサポートへのお問い合わせ - 管理者向けヘルプ](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)」をご覧ください。

    
## <a name="related-topics"></a>関連トピック
[住所検証とは何ですか?](/SkypeForBusiness/what-are-calling-plans-in-office-365/what-is-address-validation)

[通話プランで使用されるさまざまな種類の電話番号](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[緊急通話の利用条件](emergency-calling-terms-and-conditions.md)

[Skype for Business Online: 緊急通話の免責事項ラベル](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

