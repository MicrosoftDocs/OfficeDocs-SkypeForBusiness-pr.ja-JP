---
title: Microsoft 365 for Teams で電話会議を試用または購入する
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: d080bb8c-3465-47bb-ad2b-9428f1a3fd24
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
- m365initiative-meetings
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- ms.lync.lac.CpcGettingStarted
- seo-marvel-mar2020
description: 'Microsoft 365 または Office 365 の電話会議 (PSTN 会議) ライセンスを試用または購入して、ユーザーがダイヤルインできる電話会議を設定する方法について説明します。 '
ms.openlocfilehash: 547e60b828c7baa36b21b8ad63ae08268c33d4dc
ms.sourcegitcommit: 380a96f1ed2cefb429286854f06546bdb28d7d74
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "49701205"
---
# <a name="try-or-purchase-audio-conferencing-in-microsoft-365-for-microsoft-teams"></a>Microsoft 365 for Microsoft Teams で電話会議を試用または購入する

組織内のユーザーが、会議にダイヤル インするために電話機を使用する必要がある場合があります。 Microsoft Teams には、このような状況専用の電話会議機能が含まれています。 ユーザーは、モバイル デバイスや PC で Microsoft Teams アプリを使用する代わりに、電話を使って Microsoft Teams 会議にコールインできます。

必要なのは、会議をスケジュールまたは開催する予定のユーザーのために電話会議を設定する場合のみです。 会議の出席者にミーティングへのライセンスが割り当てられている必要はなく、その他のセットアップも必要ありません。

価格情報については、「[電話会議の価格](https://products.office.com/skype-for-business/audio-conferencing#Requirements)」を参照してください。

## <a name="step-1-buy-and-assign-audio-conferencing-licenses"></a>手順 1: 電話会議ライセンスを購入して割り当てる

これらの手順を実行するには [、グローバル管理者または課金](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) 管理者である必要があります。

### <a name="to-buy-and-assign-user-audio-conferencing-licenses"></a>ユーザーの電話会議ライセンスを購入して割り当てるには

1. お客様の **国/地域で電話** 会議を利用できる場所を確認します。 [電話会議と通話プランの利用が可能な国と地域](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)。

2. **電話会議** のライセンスを取得します。 以下を希望する場合:

   - **購入前** にお試しください。電話会議を含む Office 365 Enterprise E5 の無料試用版にサインアップできます。 [Office 365 Enterprise E5 の試用版](https://portal.office.com/Signup?OfferId=101bde18-5ffb-4d79-a47b-f5b2c62525b3)を参照してください。

   - **購入する**: [Microsoft Teams アドオン ライセンスを参照してください](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing)。

3. [会議をスケジュールまたは開催](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users) する組織内のユーザーにライセンスを割り当てる。

4. 電話会議のアドオン ライセンスおよびコミュニケーション クレジットのライセンスを購入した場合も割り当てます。 手順については、「Microsoft Teams アドオン ライセンス [を割り当てる」を参照してください](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing)。

### <a name="to-buy-and-assign-pay-per-minute-audio-conferencing-licenses"></a>分単位支払い電話会議ライセンスを購入して割り当てるには

ライセンス供与されている大口の顧客の場合、分数ごと従量課金制電話会議のライセンスを取得できます。 分数ごと従量課金制電話会議のライセンスの詳細については、 [分数ごと従量課金制電話会議](audio-conferencing-pay-per-minute.md)を参照してください。
  
1. お客様の **国/地域で電話** 会議を利用できる場所を確認します。 [電話会議と通話プランの国と地域の可用性](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)。

2. **電話会議** のライセンスを取得します。 分数ごと従量課金ライセンスを取得するには、アカウントの担当者にお問い合わせください。

3. [組織のコミュニケーション クレジット](set-up-communications-credits-for-your-organization.md) を設定します。 コミュニケーション クレジットの設定については、「[コミュニケーション クレジットとは](what-are-communications-credits.md)」を参照してください 。

    > [!IMPORTANT]
    > コミュニケーション クレジットが設定されていない場合、電話会議が分数ごと従量課金ライセンスを持つすべてのユーザーに対して機能しません。

4. [会議をスケジュールまたは開催](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users) する組織内のユーザーにライセンスを割り当てる。

    > [!NOTE]
    > 電話会議の分単位支払いライセンスがある場合は、各ユーザーに通信クレジット ライセンスを個別に割り当てる必要があります。

## <a name="step-2-set-the-audio-conferencing-provider-for-people-who-lead-or-schedule-meetings"></a>手順 2: 会議の主催者または計画者のために電話会議プロバイダーを設定する

Skype for  Business がサードパーティの電話会議プロバイダーと統合されていない組織内のユーザーに電話会議ライセンスを割り当てると、すべてのライセンスがセットアップされ、準備が整います。 (電話会議プロバイダーを設定する必要はありません。)

サードパーティの電話会議プロバイダーでユーザーを有効にしている場合は、そのユーザーのプロバイダーを Microsoft に変更する必要があります。 ユーザーのプロバイダーを変更するには、「Microsoft を電話会議プロバイダーとして割り当てる [」を参照してください](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider)。

## <a name="step-3-other-admin-tasks"></a>手順 3: その他の管理タスク

次の手順は **オプション** ですが、管理者の多くは次の設定を行うのを好みます。

1. [会議出席依頼をカスタマイズします](/skypeforbusiness/set-up-skype-for-business-online/customize-meeting-invitations)。 ユーザー向けに設定されているダイヤルイン番号は、会議の出席者に送信される会議出席依頼に自動的に追加されます。 ただし、独自のヘルプや法的リンク、テキスト メッセージ、会社の小さな画像を追加できます。

2. [招待に含まれる電話番号を設定します](set-the-phone-numbers-included-on-invites-in-teams.md)。 これは、ユーザーが参加を予定している会議で表示される電話番号です。

3. [電話会議の自動応答](set-auto-attendant-languages-for-audio-conferencing-in-teams.md) が電話会議の電話番号にダイヤルインするときに発信者に挨拶メッセージを表示するために使用する電話会議の自動応答言語を設定します。 この手順は、Microsoft を電話会議プロバイダーとして使用している場合にのみ適用されます。

4. [電話会議の PIN の長さを設定します](set-the-pin-length-for-audio-conferencing-meetings-in-teams.md)。

> [!NOTE]
> この機能は、21Vianet が運営する Office 365 を中国で使用しているお客様にはまだご利用いただけません。詳細については、「 [21Vianet が運営する Office 365 について](https://support.office.com/article/A8AB5061-3346-4DA0-BB7C-5260822B53AE)」を参照してください。

## <a name="related-topics"></a>関連項目

[組織内の Teams を有効にする](office-365-set-up.md)

[電話会議の電話番号](phone-numbers-for-audio-conferencing-in-teams.md)

[オンライン会議、電話会議のオプションを設定](https://support.office.com/article/DCD1CA39-0C1F-466C-9573-F04138FEF5E2)
