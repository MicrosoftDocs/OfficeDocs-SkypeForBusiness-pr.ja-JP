---
title: マイクロソフトのチーム内のユーザーの電話会議の設定を管理します。
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
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Office 365 管理者としてマイクロソフト チームの電話会議の設定を編集することができます-プロバイダー、既定の有料または無料電話番号、会議 ID、暗証番号 (pin) など、組織内の個々 のユーザーのです。 '
ms.openlocfilehash: 3f6adffcccfeee38b2a8af2d56759aabee25f16c
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "23857624"
---
# <a name="manage-the-audio-conferencing-settings-for-a-user-in-microsoft-teams"></a>マイクロソフトのチーム内のユーザーの電話会議の設定を管理します。

Office 365 管理者としてSkype for Business Onlineの電話会議の設定 を編集することができます-プロバイダー、既定の有料または無料電話番号、会議 ID、暗証番号 (pin) など、組織内の個々 のユーザーの設定です。 組織の設定を編集する場合は、[組織内でのオーディオ会議設定の管理](manage-the-audio-conferencing-settings-for-my-organization-in-teams.md)を参照してください。


1. 左側のナビゲーションでは、**ユーザー**] をクリックしてで使用可能なユーザーの一覧からユーザーを選択します。

2. ページの上部で、[**編集**] をクリックします。

3. [**オーディオ会議**では、次のいずれかを変更します。

|**設定**|**説明**|
|:-----|:-----|
|**電話会議**|音声会議をオンまたはオフ、ユーザーをクリックして**音声会議**の横にあるし、[**電話会議**] ウィンドウで**編集**を、**オーディオ会議**で、オフを切り替えます。|
|**会議の情報を電子メールで送信します。**  |ユーザーに電子メールで会議 ID と電話番号とをすぐに送信する場合にのみ、このリンクをクリックします。 (PINはこのメールは含まれません。) [ユーザーに電子メールで電話会議の情報を送信する](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)を参照してください。  |
|**会議 ID**  |ユーザーの会議 ID をリセットする必要がある場合は、**会議 ID のリセット**をクリックします。 詳細については、 [ユーザーの会議 ID をリセットする](reset-a-conference-id-for-a-user-in-teams.md)を参照してください。  |
|**暗証番号 (PIN)** |ユーザーの PIN をリセットする必要がある場合は、 **PIN のリセット**をクリックします。 詳細については、 [電話会議の PIN のリセット](reset-the-audio-conferencing-pin-in-teams.md)を参照してください。 |
|**既定の会議通話の電話番号**(必須) |これらをオーディオ会議ブリッジで設定されている番号となります。 ビジネスおよびマイクロソフトのチームの会議出席依頼の Skype に表示する数値書式を設定します。 既定の有料電話番号を変更するには、**編集**をクリックします次に**電話会議**をしに、**オーディオ会議**ウィンドウで、**有料電話番号**の下の番号を選択します。 |
|**このユーザーからの招待は、フリー ダイヤル番号を含めることができます。**|この設定を変更するには、**オーディオ会議**の横にあると、[**電話会議**] ウィンドウで**編集**をクリックして、**このユーザーからの要求を達成するためのフリー ダイヤル番号**で、オフを切り替えます。 |
|**ダイヤルアウトのアクセス許可**|この設定を変更するには、**オーディオ会議**の横にあると、[**電話会議**] ウィンドウで**編集**をクリックして、**会議からの発信アクセス許可**] の下のオプションを選択します。|

![ユーザーの電話会議の設定を示しています。](media/sfbaudioconf-usersettings.png)
 

> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="related-topics"></a>このモジュールは、64 ビットのコンピューターでのみサポートされ、Microsoft ダウンロード センターの「Skype for Business Online 用 Windows PowerShell モジュール」からダウンロードできます。

[組織の電話会議の設定を管理する](manage-the-audio-conferencing-settings-for-my-organization-in-teams.md)

[電話会議に関するよくある質問](audio-conferencing-common-questions.md)
