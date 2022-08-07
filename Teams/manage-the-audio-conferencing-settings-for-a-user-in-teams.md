---
title: ユーザーの電話会議設定を管理する
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 0f39dc9d-eb60-4c5a-9ae3-e34a01834d9b
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: Microsoft 365 またはOffice 365管理者は、ユーザーのプロバイダー、既定の有料電話番号、フリーダイヤル番号、会議 ID、PIN など、Teams 電話会議の設定を編集できます。
ms.openlocfilehash: 13e44c9f7d8d983325c5f4cf3bb88237a9ad1fb9
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2022
ms.locfileid: "67269692"
---
# <a name="manage-the-audio-conferencing-settings-for-a-user-in-microsoft-teams"></a>Microsoft Teams でユーザーの電話会議の設定を管理する

Microsoft 365 またはOffice 365管理者は、組織内の個々のユーザーの電話会議設定 (プロバイダー、既定の有料電話番号、フリーダイヤル番号、会議 ID、PIN など) を編集できます。 組織の設定を編集する場合は、「組織 [の電話会議設定を管理する」を参照してください](manage-the-audio-conferencing-settings-for-my-organization-in-teams.md)。

## <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターの使用

1. 左側のナビゲーションで、[**ユーザー**] をクリックしてから、空いているユーザーのリストからユーザーを選択します。

2. [ **編集]** をクリックします。

3. [ **電話会議]** で、次のいずれかを変更します。

|**設定**|**説明**|
|:-----|:-----|
|**電話会議**|ユーザーの電話会議をオンまたはオフにするには、**電話会議** の横にある **[編集]** をクリックし、[**電話会議**] ウィンドウで [**電話会議**] の [オン] または [オフ] を切り替えます。|
|**会議情報を電子メールで送信する**  |ユーザーに電子メールで会議 ID と電話番号とをすぐに送信する場合にのみ、このリンクをクリックします。 (PINはこのメールは含まれません。) [ユーザーに電子メールで電話会議の情報を送信する](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)を参照してください。  |
|**電話会議 ID**  |ユーザー **の会議 ID をリセット** する必要がある場合は、[会議 ID のリセット] をクリックします。 詳細については、 [ユーザーの会議 ID をリセットする](reset-a-conference-id-for-a-user-in-teams.md)を参照してください。  |
|**ピン** |ユーザー **の PIN をリセット** する必要がある場合は、[PIN のリセット] をクリックします。 詳細については、 [電話会議の PIN のリセット](reset-the-audio-conferencing-pin-in-teams.md)を参照してください。 |
|**既定の会議の有料電話番号** (必須) |これらは、電話会議ブリッジで設定される番号です。 Skype for Businessと Microsoft Teams の会議出席依頼に表示する数値を書式設定します。 既定の有料電話番号を変更するには、[**電話会議**] の横にある **[編集]** をクリックし、[**電話会議**] ウィンドウで **[有料電話番号**] の下にある番号を選択します。 TeamsAudioConferencingPolicy に電話番号を追加し、ポリシーをユーザーに割り当てることで電話番号を設定することもできます。 ポリシーに追加された電話番号は、 **既定の会議の有料** 電話番号を使用して設定された電話番号よりも優先されます。 TeamsAudioConferencingPolicy に電話番号が追加されていない場合は、 **既定の会議の有料電話番号を** 使用して設定された電話番号が Microsoft Teams の会議出席依頼に表示されます。 |
|**このユーザーからの招待には、フリーダイヤル番号を含めることができます**|この設定は TeamsAudioconferecningPolicy を使用してのみ変更できます。 |
|**認証されていないユーザーは、会議の最初のユーザーにすることができます**|この設定を変更するには、認証 **されていないユーザーを会議の最初のユーザーとして** オンまたはオフに切り替えます。
|**ダイヤルアウトアクセス許可**|この設定を変更するには、[**電話会議**] の横にある **[編集]** をクリックし、[**電話会議**] ウィンドウの [**会議からのダイヤルアウト**] でオプションを選択します。|

![ユーザーの電話会議の設定を表示します。](media/teams-manage-audio-conferencing-settings-for-a-user-image1.png)

> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="related-topics"></a>関連項目

[組織の電話会議の設定を管理する](manage-the-audio-conferencing-settings-for-my-organization-in-teams.md)

[電話会議に関するよくある質問](audio-conferencing-common-questions.md)
