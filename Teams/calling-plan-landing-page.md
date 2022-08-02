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
description: Teams の Cloud Voice で組織に最適な Microsoft Phone システム通話プランを決定します。
ms.custom: seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0040814b12e98c4f44d1dff5939651938580fa4d
ms.sourcegitcommit: 07761c26b53d92fc36b82cab7b3e38a6de4ff945
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/02/2022
ms.locfileid: "67156555"
---
# <a name="which-calling-plan-is-right-for-you"></a>どの通話プランが適していますか?

[使用開始](get-started-with-teams-quick-start.md)の手順は完了しています。 Teams の[チャット、チーム、チャネル、アプリ](deploy-chat-teams-channels-microsoft-teams-landing-page.md)を組織全体に展開しました。 [会議および電話会議](deploy-meetings-microsoft-teams-landing-page.md)を展開した可能性があります。 クラウド ボイスのワークロードを追加する準備ができました。通話プランが設定された Microsoft 電話システムを使用して公衆交換電話網 (PSTN) に接続することを決定しました。

この記事では、組織のニーズに基づいて、計画の呼び出しに関する主要な展開の決定と、構成する必要があるその他の考慮事項について説明します。 また、Microsoft のクラウド ボイス サービスの詳細については、「[Microsoft Teams でのクラウド ボイス](cloud-voice-landing-page.md)」を参照してください。

## <a name="learn-more-about-calling-plans"></a>通話プランに関する詳細情報

Microsoft 通話プランの展開と使用の詳細については、次の記事をご覧ください。

- [Microsoft 365 またはOffice 365の電話システム](what-is-phone-system-in-office-365.md)
- [Microsoft 365 または Office 365 のプランを呼び出す](calling-plans-for-office-365.md)
- [通話プランの設定](set-up-calling-plans.md)

## <a name="core-deployment-decisions"></a>展開に関する重要な決定事項

Microsoft をテレフォニー通信事業者として使用するには、通話プランのライセンスを取得して、そのライセンスを電話システムのユーザーに割り当てる必要があります。

利用できる通話プランには、次の 3 種類があります。

- 国内通話プラン
- 国際通話プラン
- 従量課金制通話プラン

| 確認事項 | アクション |
|--------------|--------|
| 自分の住んでいる地域で通話プランを利用できますか? 通話プラン サービスを利用できるのはどのユーザーの場所ですか? | 詳細については、「[国および地域ごとの電話会議および通話プランの利用可能性](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)」を参照してください。 |
| ユーザーは国際電話を利用する必要がありますか? | 詳細については、「[Microsoft 365 または Office 365のプランの呼び出し](calling-plans-for-office-365.md)」を参照してください。 |
| 一部のユーザーが大量の発信呼び出しを行わない場合、従量課金制通話プランが最も経済的なオプションですか? | 詳細については、「[Microsoft 365 または Office 365のプランの呼び出し](calling-plans-for-office-365.md)」を参照してください。 |
| ユーザーは通話プランのライセンスを持っていますか? | ライセンスを購入して割り当てるには、「[手順 2: ライセンスを購入して割り当てる](set-up-calling-plans.md#step-2-buy-and-assign-licenses)」を参照してください。 |
| ユーザーはそれぞれ直通社内通話 (DID) 電話番号がありますか? | 電話番号を取得するには、「[手順 3: 電話番号を取得する](set-up-calling-plans.md#step-3-get-phone-numbers)」を参照してください。 |

### <a name="transfer-phone-numbers-to-microsoft-365-or-office-365"></a>Microsoft 365 またはOffice 365に電話番号を転送する

電話番号を現在のサービス プロバイダーから Teams に簡単に移行できます。 電話番号を Teams に移行した後、Microsoft がサービス プロバイダーになり、それらの電話番号に対する請求を行います。 詳細については、「[電話番号を Teams に転送する](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)」を参照してください。

### <a name="phone-numbers-and-emergency-locations"></a>電話番号と緊急対応の場所

Microsoft 365 または Office 365の通話プランでは、組織内のすべてのユーザーに、一意の直接内向きダイヤル (DID) 電話番号と対応する検証済みの緊急用アドレスが必要です。 緊急対応の住所に、緊急対応の場所 (たとえば、部屋番号や階数) を指定することもできます。

|確認事項|アクション |
|:------------|:-------|
|緊急対応の住所と場所をどれほど詳しく指定しますか? |詳細については、[緊急対応の場所、住所、通話ルーティングの概要](/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-emergency-locations-addresses-and-call-routing)をご覧ください。

### <a name="calling-identity"></a>通話 ID

既定で、すべての発信通話は、割り当てられた電話番号を通話 ID (発信者 ID) として使用します。 通話の受信者は、発信者をすばやく特定して、通話を承諾または拒否するかどうかを決定できます。

|確認事項|アクション |
|:------------|:-------|
|発信者 ID のマスクや無効化を行いますか? | 発信者 ID を変更またはブロックするには、「[ユーザーの発信者 ID を設定する](set-the-caller-id-for-a-user.md)」を参照してください。 |
|||
