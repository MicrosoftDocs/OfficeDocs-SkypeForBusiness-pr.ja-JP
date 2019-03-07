---
title: マイクロソフトのチームでの通話プラン
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 01/28/2019
ms.topic: article
ms.service: msteams
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- M365-voice
ms.reviewer: crowe
search.appverid: MET150
description: 計画のランディング ページを呼び出す
appliesto:
- Microsoft Teams
ms.openlocfilehash: 412797a52e82c03937670e895fea7b42a3ce7b4a
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/07/2019
ms.locfileid: "30460757"
---
# <a name="phone-system-with-calling-plans"></a>通話プランが設定された電話システム 

[開始](get-started-with-teams-quick-start.md)するが完了しました。 Teams の[チャット、チーム、チャネル、およびアプリ](deploy-chat-teams-channels-microsoft-teams-landing-page.md)を組織全体に展開しました。 かもしれません[& 会議の会議](deploy-meetings-microsoft-teams-landing-page.md)を導入しました。 クラウド音声のワークロードを追加する準備が整いましたし、を公衆交換電話網 (PSTN) を接続する計画を呼び出すことでマイクロソフトの電話システムを使用すると判断しました。 

この資料を構成すること、組織のニーズに基づいて計画を呼び出すと、追加の考慮事項の中核となる展開の決定について説明します。 マイクロソフトのクラウドの音声サービスの詳細については[マイクロソフトのチームでのクラウドの音声](cloud-voice-landing-page.md)を参照することもあります。


## <a name="learn-more-about-calling-plans"></a>プランの呼び出しの詳細については

次の記事では、展開して、マイクロソフトでは予定の呼び出しを使用しての詳細についてを提供します。

- [Office 365 での電話システム](what-is-phone-system-in-office-365.md)
- [Office 365 の通話プラン](calling-plans-for-office-365.md)
- [通話プランの設定](set-up-calling-plans.md)


## <a name="core-deployment-decisions"></a>展開に関する重要な決定事項

テレフォニー キャリアでは、Microsoft を使用するには、計画を呼び出してライセンスを取得し、電話システムのユーザーに割り当てる必要があります。 

利用は 2 種類のプランを呼び出すことがあります。

- 国内通話プラン 
- 国内または国際通話プラン

|確認事項|アクション |
|------------|-------|
|計画を呼び出して自分の地域ではでしょうか。 どのユーザーの場所には、サービスの計画を呼び出すことはありますか。 | 詳細については、[オーディオ会議や予定を呼び出すための国および地域の可用性](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)を参照してください。 | 
ユーザーに国際通話が必要ですか。 | 詳細については、 [Office 365 のプランを呼び出す](calling-plans-for-office-365.md)を参照してください。 |
自分のユーザーにはライセンスの計画を呼び出すことがありますか。 | 購入し、ライセンスを割り当てるを参照してください[手順 2: を購入し、ライセンスを割り当てる](set-up-calling-plans.md#step-2-buy-and-assign-licenses)。 |
各ユーザーには直接内側 (DID) 電話番号をダイヤルがありますか。 | 電話番号を取得するを参照してください[手順 3: 電話番号を取得する](set-up-calling-plans.md#step-3-get-phone-numbers)です。 |
|||

### <a name="transfer-phone-numbers-to-office-365"></a>Office 365 に電話番号を転送する

チーム、現在のサービス プロバイダーから自分の電話番号に転送するのには簡単です。 チームに自分の電話番号を移植した後、Microsoft は、サービス ・ プロバイダーになり、に対する料金を請求している電話番号。 詳細については、 [Office 365 に電話番号を転送する](transfer-phone-numbers-to-office-365.md)を参照してください。


### <a name="phone-numbers-and-emergency-locations"></a>電話番号と緊急対応の場所

Office 365 のプランを呼び出すこと、内向きの一意な直通を組織のニーズのすべてのユーザーは、番号と対応する検証済みの緊急アドレス電話 (でした)。 緊急のアドレス (オフィス番号またはフロア番号など) では、緊急の場所を指定することもできます。 

|確認事項|アクション |
|:------------|:-------|
|詳細な方法が必要に緊急時のアドレスと場所の情報か、 |詳細についてを参照してください[緊急の場所、住所、および通話のルーティングには何ですか?](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-emergency-locations-addresses-and-call-routing)です。


### <a name="calling-identity"></a>発信者番号

既定では、すべての発信呼び出しは、呼び出し元の id (呼び出し元 ID) として割り当てられた電話番号を使用します。 通話の受信者は即座にその発信者を識別して通話を受け入れるか拒否するか決めることができます。

|確認事項|アクション |
|:------------|:-------|
|マスクしたり、発信者番号通知を無効にするか。 | 呼び出し元 ID のブロックを変更または、[ユーザーの発信者番号の設定](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/set-the-caller-id-for-a-user)を参照してください。 |
|||




