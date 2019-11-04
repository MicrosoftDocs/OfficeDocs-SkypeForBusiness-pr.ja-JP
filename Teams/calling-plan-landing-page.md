---
title: Microsoft Teams の通話プラン
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 01/28/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: crowe
search.appverid: MET150
description: 通話プランのランディングページ
appliesto:
- Microsoft Teams
ms.openlocfilehash: d27169d5f65fb693ce49453f7e7c965f867198ad
ms.sourcegitcommit: 100ba1409bf0af58e4430877c1d29622d793d23f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/01/2019
ms.locfileid: "37925588"
---
# <a name="which-calling-plan-is-right-for-you"></a>どの通話プランが適していますか? 

[作業を開始](get-started-with-teams-quick-start.md)しました。 Teams の[チャット、チーム、チャネル、およびアプリ](deploy-chat-teams-channels-microsoft-teams-landing-page.md)を組織全体に展開しました。 会議[&](deploy-meetings-microsoft-teams-landing-page.md)会議を展開したことがあるかもしれません。 これで、クラウド音声のワークロードを追加する準備ができました。電話システムを使用して公衆交換電話網 (PSTN) に接続しています。 

この記事では、組織のニーズに基づいて、通話プランの主要な展開決定と、構成する必要があるその他の考慮事項について説明します。 Microsoft のクラウド音声サービスの詳細については、「 [Microsoft Teams でクラウド音声](cloud-voice-landing-page.md)を読む」もご覧ください。


## <a name="learn-more-about-calling-plans"></a>通話プランについて、詳細はこちらをご覧ください

次の記事では、Microsoft の通話プランの展開と使用に関する詳細情報を提供しています。

- [Office 365 の電話システム](what-is-phone-system-in-office-365.md)
- [Office 365 の通話プラン](calling-plans-for-office-365.md)
- [通話プランの設定](set-up-calling-plans.md)


## <a name="core-deployment-decisions"></a>展開に関する重要な決定事項

Microsoft をテレフォニーキャリアとして使用するには、通話プランのライセンスを取得し、電話システムのユーザーに割り当てる必要があります。 

利用可能な通話プランには、次の2種類があります。

- 国内通話プラン 
- 国内および国際通話プラン

|確認事項|アクション |
|------------|-------|
|地域で通話プランを利用できますか? どのユーザーの場所で通話プランサービスを利用できますか? | 詳細については、「[電話会議と通話プランの国と地域の空き時間](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)情報」を参照してください。 | 
ユーザーには国際通話が必要ですか? | 詳細については、「 [Office 365 の通話プラン](calling-plans-for-office-365.md)」を参照してください。 |
ユーザーが通話プランのライセンスを持っているかどうかを確認する | ライセンスを購入して割り当てるには、「[手順 2: ライセンスを購入して割り当てる](set-up-calling-plans.md#step-2-buy-and-assign-licenses)」を参照してください。 |
各ユーザーは、それぞれに1つの内向きダイヤル (DID) 電話番号を持っていますか? | 電話番号を取得するには、「[手順 3: 電話番号を取得](set-up-calling-plans.md#step-3-get-phone-numbers)する」を参照してください。 |
|||

### <a name="transfer-phone-numbers-to-office-365"></a>Office 365 に電話番号を転送する

現在のサービスプロバイダから Teams に電話番号を転送するのは簡単です。 お客さまの電話番号を Teams に移植すると、Microsoft はサービスプロバイダになり、これらの電話番号について請求されます。 詳細については、「[チームに電話番号を転送する](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)」を参照してください。


### <a name="phone-numbers-and-emergency-locations"></a>電話番号と緊急対応の場所

Office 365 の通話プランでは、組織内のすべてのユーザーが、固有の直通電話番号と、対応する有効な緊急対応の住所を持っている必要があります。 緊急対応の住所に緊急対応の場所を指定することもできます (たとえば、オフィス番号やフロア番号)。 

|確認事項|アクション |
|:------------|:-------|
|緊急対応の住所と住所の情報を詳細に確認するには、どうすればよいですか。 |詳細については、「[緊急対応の場所、アドレス、通話ルーティング](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-emergency-locations-addresses-and-call-routing)の概要」を参照してください。


### <a name="calling-identity"></a>通話 id

既定では、すべての発信通話で、割り当てられた電話番号が発信 id (発信者番号) として使用されます。 通話の受信者は、すぐに発信者を特定して、通話を承諾または拒否するかどうかを決定できます。

|確認事項|アクション |
|:------------|:-------|
|発信者番号認識を無効にするか、無効にしますか? | 発信者番号通知を変更またはブロックするには、「[ユーザーに発信者番号を設定](set-the-caller-id-for-a-user.md)する」を参照してください。 |
|||




