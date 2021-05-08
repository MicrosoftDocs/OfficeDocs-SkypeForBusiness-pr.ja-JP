---
title: Microsoft 365 で電話会議を試用または購入Teams
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
ms.openlocfilehash: b4cf789289bc1f05e9e8bba79409f204112f288b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51116535"
---
# <a name="try-or-purchase-audio-conferencing-in-microsoft-365-for-microsoft-teams"></a>Microsoft 365 で電話会議を試用または購入Microsoft Teams

組織内のユーザーが、会議にダイヤル インするために電話機を使用する必要がある場合があります。 Microsoft Teams、この状況に合った電話会議機能が含まれています。 ユーザーは、モバイル デバイスまたは PC Microsoft Teamsアプリを使用する代わりに、電話を使用してMicrosoft Teams会議にコールインできます。

会議をスケジュールまたは開催する予定のユーザーに対して電話会議を設定する必要があります。 会議の出席者にミーティングへのライセンスが割り当てられている必要はなく、その他のセットアップも必要ありません。

価格情報については、「[電話会議の価格](https://www.microsoft.com/microsoft-teams/audio-conferencing?rtc=3)」を参照してください。

## <a name="step-1-buy-and-assign-audio-conferencing-licenses"></a>手順 1: 電話会議ライセンスを購入して割り当てる

これらの手順を実行するには [、グローバル管理者または課金](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) 管理者である必要があります。

### <a name="to-buy-and-assign-user-audio-conferencing-licenses"></a>ユーザーの電話会議ライセンスを購入して割り当てるには

1. 電話会議 **が国** /地域で利用できるのか確認します。 [電話会議と通話プランの国と地域の可用性](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)。

2. **電話会議** のライセンスを取得します。 以下を希望する場合:

   - **購入する** 前に試してください。電話会議を含む Office 365 Enterprise E5 無料試用版にサインアップできます。 [Office 365 Enterprise E5 の試用版](https://portal.office.com/Signup?OfferId=101bde18-5ffb-4d79-a47b-f5b2c62525b3)を参照してください。

   - **購入:**「Microsoft Teams [ライセンス」を参照してください](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。

3. [会議をスケジュールまたは開催](/microsoft-365/admin/manage/assign-licenses-to-users) する組織内のユーザーにライセンスを割り当てる。

4. 電話会議のアドオン ライセンスおよびコミュニケーション クレジットのライセンスを購入した場合も割り当てます。 手順については、「アドオン ライセンスの[割りMicrosoft Teams割り当て」を参照してください](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。

### <a name="to-buy-and-assign-pay-per-minute-audio-conferencing-licenses"></a>分単位の電話会議ライセンスを購入して割り当てるには

ライセンス供与されている大口の顧客の場合、分数ごと従量課金制電話会議のライセンスを取得できます。 分数ごと従量課金制電話会議のライセンスの詳細については、 [分数ごと従量課金制電話会議](audio-conferencing-pay-per-minute.md)を参照してください。
  
1. 電話会議 **が国** /地域で利用できるのか確認します。 [電話会議と通話プランの国と地域の可用性](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)。

2. **電話会議** のライセンスを取得します。 分数ごと従量課金ライセンスを取得するには、アカウントの担当者にお問い合わせください。

3. [組織のコミュニケーション クレジットを設定](set-up-communications-credits-for-your-organization.md) します。 コミュニケーション クレジットの設定については、「[コミュニケーション クレジットとは](what-are-communications-credits.md)」を参照してください 。

    > [!IMPORTANT]
    > コミュニケーション クレジットが設定されていない場合、電話会議が分数ごと従量課金ライセンスを持つすべてのユーザーに対して機能しません。

4. [会議をスケジュールまたは開催](/microsoft-365/admin/manage/assign-licenses-to-users) する組織内のユーザーにライセンスを割り当てる。

    > [!NOTE]
    > 電話会議の分単位支払いライセンスがある場合は、各ユーザーに通信クレジット ライセンスを個別に割り当てる必要があります。

## <a name="step-2-set-the-audio-conferencing-provider-for-people-who-lead-or-schedule-meetings"></a>手順 2: 会議の主催者または計画者のために電話会議プロバイダーを設定する

Skype for Business がサードパーティの電話会議プロバイダーと統合されていない組織内のユーザーに電話会議ライセンスを割り当てると、すべてがセットアップされ、準備が整います。 (電話会議プロバイダーを設定する必要はありません。)

サードパーティの電話会議プロバイダーでユーザーを有効にしている場合は、そのユーザーのプロバイダーを Microsoft に変更する必要があります。 ユーザーのプロバイダーを変更するには、「電話会議プロバイダーとして Microsoft を割り当 [てる」を参照してください](/skypeforbusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider)。

## <a name="step-3-other-admin-tasks"></a>手順 3: その他の管理タスク

次の手順は **オプション** ですが、管理者の多くは次の設定を行うのを好みます。

1. [会議出席依頼をカスタマイズします](/skypeforbusiness/set-up-skype-for-business-online/customize-meeting-invitations)。 ユーザー向けに設定されているダイヤルイン番号は、会議の出席者に送信される会議出席依頼に自動的に追加されます。 ただし、独自のヘルプや法的リンク、テキスト メッセージ、会社の小さな画像を追加できます。

2. [招待に含まれる電話番号を設定します](set-the-phone-numbers-included-on-invites-in-teams.md)。 これは、ユーザーが参加を予定している会議で表示される電話番号です。

3. [電話会議の自動応答](set-auto-attendant-languages-for-audio-conferencing-in-teams.md) が電話会議の電話番号にダイヤルインするときに発信者にあいさつするために使用する電話会議の自動応答言語を設定します。 この手順は、電話会議プロバイダーとして Microsoft を使用している場合にのみ適用されます。

4. [電話会議会議の PIN の長さを設定します](set-the-pin-length-for-audio-conferencing-meetings-in-teams.md)。

> [!NOTE]
> この機能は、21Vianet が運営する Office 365 を中国で使用しているお客様にはまだご利用いただけません。詳細については、「 [21Vianet が運営する Office 365 について](https://support.office.com/article/A8AB5061-3346-4DA0-BB7C-5260822B53AE)」を参照してください。

## <a name="related-topics"></a>関連トピック

[組織Teamsを有効にする](office-365-set-up.md)

[電話会議の電話番号](phone-numbers-for-audio-conferencing-in-teams.md)

[オンライン会議、電話会議のオプションを設定](https://support.office.com/article/DCD1CA39-0C1F-466C-9573-F04138FEF5E2)