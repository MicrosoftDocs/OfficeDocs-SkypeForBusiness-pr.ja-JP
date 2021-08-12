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
- m365initiative-voice
f1.keywords:
- NOCSH
ms.reviewer: crowe
search.appverid: MET150
description: 組織が Microsoft 電話 Cloud Voice で最適なサービスを提供するシステム呼び出しプランを決定Teams。
ms.custom: seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: c71c52f8209cc0030ee978b8c8b051c5d8101a55700f80f9dbe52fe36e84b3c3
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54347532"
---
# <a name="which-calling-plan-is-right-for-you"></a>どの通話プランが適していますか? 

[使用開始](get-started-with-teams-quick-start.md)の手順は完了しています。 Teams の[チャット、チーム、チャネル、アプリ](deploy-chat-teams-channels-microsoft-teams-landing-page.md)を組織全体に展開しました。 [会議および電話会議](deploy-meetings-microsoft-teams-landing-page.md)を展開した可能性があります。 クラウド ボイスのワークロードを追加する準備ができました。通話プランが設定された Microsoft 電話システムを使用して公衆交換電話網 (PSTN) に接続することを決定しました。 

この記事では、通話プランの展開に関する重要な決定事項に加え、お客様の組織のニーズに合わせて構成する必要があるその他の考慮事項について説明します。 また、Microsoft のクラウド ボイス サービスの詳細については、「[Microsoft Teams でのクラウド ボイス](cloud-voice-landing-page.md)」を参照してください。


## <a name="learn-more-about-calling-plans"></a>通話プランに関する詳細情報

Microsoft 通話プランの展開と使用の詳細については、次の記事をご覧ください。

- [電話システム または Microsoft 365 でOffice 365](what-is-phone-system-in-office-365.md)
- [通話プラン (Microsoft 365 または Office 365](calling-plans-for-office-365.md)
- [通話プランの設定](set-up-calling-plans.md)


## <a name="core-deployment-decisions"></a>展開に関する重要な決定事項

Microsoft をテレフォニー通信事業者として使用するには、通話プランのライセンスを取得して、そのライセンスを電話システムのユーザーに割り当てる必要があります。 

使用できる通話プランには次の 2 つの種類があります。

- 国内通話プラン 
- 国内および国際通話プラン

|確認事項|Action |
|------------|-------|
|自分の住んでいる地域で通話プランを利用できますか? 通話プラン サービスを利用できるのはどのユーザーの場所ですか? | 詳細については、「[国および地域ごとの電話会議および通話プランの利用可能性](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)」を参照してください。 | 
ユーザーは国際電話を利用する必要がありますか? | 詳細については、「通話プランの呼び[出し」または「Microsoft 365」をOffice 365。](calling-plans-for-office-365.md) |
ユーザーは通話プランのライセンスを持っていますか? | ライセンスを購入して割り当てるには、「[手順 2: ライセンスを購入して割り当てる](set-up-calling-plans.md#step-2-buy-and-assign-licenses)」を参照してください。 |
ユーザーはそれぞれ直通社内通話 (DID) 電話番号がありますか? | 電話番号を取得するには、「[手順 3: 電話番号を取得する](set-up-calling-plans.md#step-3-get-phone-numbers)」を参照してください。 |
|||

### <a name="transfer-phone-numbers-to-microsoft-365-or-office-365"></a>電話番号を電話番号にMicrosoft 365またはOffice 365

電話番号を現在のサービス プロバイダーから Teams に簡単に移行できます。 電話番号を Teams に移行した後、Microsoft がサービス プロバイダーになり、それらの電話番号に対する請求を行います。 詳細については、「[電話番号を Teams に転送する](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)」を参照してください。


### <a name="phone-numbers-and-emergency-locations"></a>電話番号と緊急対応の場所

Microsoft 365 または Office 365 の通話プランでは、組織内のすべてのユーザーが一意の内向きダイヤル (DID) 電話番号と、対応する検証済み緊急対応の住所を持っている必要があります。 緊急対応の住所に、緊急対応の場所 (たとえば、部屋番号や階数) を指定することもできます。 

|確認事項|Action |
|:------------|:-------|
|緊急対応の住所と場所をどれほど詳しく指定しますか? |詳細については、[緊急対応の場所、住所、通話ルーティングの概要](/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-emergency-locations-addresses-and-call-routing)をご覧ください。


### <a name="calling-identity"></a>通話 ID

既定で、すべての発信通話は、割り当てられた電話番号を通話 ID (発信者 ID) として使用します。 通話の受信者は、発信者をすばやく特定して、通話を承諾または拒否するかどうかを決定できます。

|確認事項|Action |
|:------------|:-------|
|発信者 ID のマスクや無効化を行いますか? | 発信者 ID を変更またはブロックするには、「[ユーザーの発信者 ID を設定する](set-the-caller-id-for-a-user.md)」を参照してください。 |
|||