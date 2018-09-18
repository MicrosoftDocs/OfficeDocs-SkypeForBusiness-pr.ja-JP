---
title: Microsoft Teams でユーザーの電話会議の設定を管理する
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 0f39dc9d-eb60-4c5a-9ae3-e34a01834d9b
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Office 365 の管理者は、組織内の個別のユーザーについて、プロバイダー、既定の有料電話番号または無料電話番号、会議 ID、または PIN などの Microsoft Teams の電話会議の設定を編集することができます。 '
ms.openlocfilehash: c101b84044e98ce44c374847aeab59f23d1a41be
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "23882953"
---
# <a name="manage-the-audio-conferencing-settings-for-a-user-in-microsoft-teams"></a>Microsoft Teams でユーザーの電話会議の設定を管理する

Office 365 管理者としてSkype for Business Onlineの電話会議の設定 を編集することができます-プロバイダー、既定の有料または無料電話番号、会議 ID、暗証番号 (pin) など、組織内の個々 のユーザーの設定です。 所属する組織について、設定を編集する場合は、「[組織の電話会議の設定を管理する](manage-the-audio-conferencing-settings-for-my-organization-in-teams.md)」をご覧ください。


1. 左側のナビゲーションで、[**ユーザー**] をクリックしてから、空いているユーザーのリストからユーザーを選択します。

2. ページの上部で、[**編集**] をクリックします。

3. [**電話会議**] の下で、次を変更することができます。

|**設定**|**説明**|
|:-----|:-----|
|**電話会議**|ユーザーについて、電話会議をオンまたはオフにするには、[ **電話会議**] の隣にある [**編集**] をクリックしてから、[**電話会議**] ペインで [**電話会議**] をオンまたはオフに切り替えます。|
|[**電話会議] の [電話会議情報をメールで送信**] をクリックします。  |ユーザーに電子メールで会議 ID と電話番号とをすぐに送信する場合にのみ、このリンクをクリックします。 (PINはこのメールは含まれません。) [ユーザーに電子メールで電話会議の情報を送信する](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)を参照してください。  |
|**会議 ID**  |ユーザーの会議 ID をリセットする必要がある場合は、[**会議 ID のリセット**] をクリックします。 詳細については、「[ユーザーのために会議 ID をリセットする](reset-a-conference-id-for-a-user-in-teams.md)」をご覧ください。  |
|**PIN** |ユーザーの PIN をリセットする必要がある場合は、[**PIN のリセット**] をクリックします。 詳細については、「[電話会議の PIN をリセットする](reset-the-audio-conferencing-pin-in-teams.md)」をご覧ください。 |
|**既定の電話会議の有料電話番号** (必須) |これらは電話会議ブリッジで設定される電話番号になります。 Skype for Business および Microsoft Teams の会議出席依頼に表示される電話番号の書式を設定します。 既定の有料電話番号を変更するには、[**電話会議**] の隣にある [**編集**] をクリックして、[**電話会議**] ペインの [**有料電話番号**] の下で電話番号を選択します。 |
|**このユーザーからの招待状に無料電話番号を含めることができます**|この設定を変更するには、[**電話会議**] の隣にある [**編集**] をクリックして、[**電話会議**] ペインで、[**Include toll-free numbers in meeting requests from this user (このユーザーからの会議依頼に無料電話番号を含める)**] をオンまたはオフに切り替えます。 |
|**ダイヤルアウトの許可**|この設定を変更するには、[**電話会議**] の隣にある [**編集**] をクリックして、[**電話会議**] ペインで、[**Dial-out permission from meetings (会議からのダイヤルアウトの許可)**] でオプションを選びます。|

![ユーザーの電話会議の設定を表示する](media/sfbaudioconf-usersettings.png)
 

> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="related-topics"></a>関連トピック

[組織の電話会議の設定を管理する](manage-the-audio-conferencing-settings-for-my-organization-in-teams.md)

[電話会議に関するよくある質問](audio-conferencing-common-questions.md)
