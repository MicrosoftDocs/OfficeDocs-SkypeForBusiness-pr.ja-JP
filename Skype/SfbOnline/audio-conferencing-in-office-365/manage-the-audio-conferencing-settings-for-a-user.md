---
title: ビジネス オンラインの Skype のユーザーの電話会議の設定を管理します。
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
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Office 365 管理者としてSkype for Business Onlineの音声会議の設定 を編集することができます-プロバイダー、既定の有料または無料電話番号、会議 ID、暗証番号 (pin) など、組織内の個々 のユーザーの設定です。 '
ms.openlocfilehash: 06fd99987df725e235f308af20542fa45b0286fd
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32229627"
---
# <a name="manage-the-audio-conferencing-settings-for-a-user-in-skype-for-business-online"></a>ビジネス オンラインの Skype のユーザーの電話会議の設定を管理します。

> [!Note]
> マイクロソフトのチームでのユーザー設定を管理する場合は、[マイクロソフトのチーム内のユーザーの電話会議の設定を管理する](/MicrosoftTeams/manage-the-audio-conferencing-settings-for-a-user-in-teams)を参照してください。

As an Office 365 admin, you can edit the Audio Conferencing settings—such as the provider, default toll or toll-free number, conference ID, or PIN—for an individual user in your organization. If you want to edit settings for your organization, see [Manage the Audio Conferencing settings for my organization](manage-the-audio-conferencing-settings-for-my-organization.md).

 
1. 職場または学校のアカウントを使用して、Office 365 にサインインします。
    
2. [**管理センター**]  >  [**Skype for Business**]を選択します。
    
3. ビジネス管理センターの Skype、**ユーザー**を選択します。
    
4. 設定を管理するユーザーを選択し、操作 ウィンドウで、**編集** をクリックして![編集 アイコンを表示します](../images/4d8bea48-be68-4e0e-a54c-73decf7ea4ec.png)。
    
5. 左側のナビゲーションで、 **電話会議** を選択し、ユーザーの **プロパティ**  ページで、次のいずれかを変更します。
    
|**設定**|**説明**|
|:-----|:-----|
|**プロバイダー名** <br/> |リストから、プロバイダーを選択します。  <br/><br/> **注:** このテーブル内の残りの設定は、音声会議プロバイダーとして Microsoft を選択した場合にのみ適用されます。           |
|**既定の有料電話番号** (必須) <br/> |For a third-party providers, these phone numbers are the ones you received from the audio conferencing provider. If the user is using Microsoft as the audio conferencing provider, these will be numbers that are set on the audio conferencing bridge. Format the numbers as you want them to appear in Skype for Business and Microsoft Teams meeting requests.  <br/> |
|**既定の無料電話番号** <br/> |For a third-party providers, these phone numbers are the ones you received from the audio conferencing provider. If the user is using Microsoft as the audio conferencing provider, these will be numbers that are set on the audio conferencing bridge. Format the numbers as you want them to appear in Skype for Business and Microsoft Teams meeting requests.  <br/> |
|**このユーザーのミーティングに参加するには、組織の Microsoft ブリッジで無料電話番号を使用できるようにします。** <br/> |フリー ダイヤル番号のユーザーに会議の参加を許可する場合は、このオプションを選択します。  <br/> |
|**会議の情報を電子メールを送信します。** <br/> |Click this link only if you want to immediately send an email to the user with his or her conference ID and phone number. (This email does not include the PIN.) See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).  <br/> |
|**会議 ID** <br/> |Select **Reset** if you need to reset the conference ID for the user. For more information, see [Reset a conference ID for a user](reset-a-conference-id-for-a-user.md).  <br/> |
|**暗証番号 (PIN)** <br/> |Select **Reset** if you need to reset the PIN for the user. For more information, see [Reset the Audio Conferencing PIN](reset-the-audio-conferencing-pin.md).  <br/> |
|**認証されていない呼び出し元が会議の最初のユーザーになることを許可します。** <br/> |認証されていない呼び出し元が最初にミーティングに参加することを許可するには、このオプションを選択します。  <br/> |
|**このユーザーの会議からのダイヤル アウトを制限** <br/> |ダイヤル アウトを国内のみに制限する場合、または会議からすべてのダイヤル  アウトを禁止したい場合、このリストでオプションを選択します。  <br/> |
  
![ユーザーの音声会議のプロパティ ページを示しています。](../images/228550f7-92be-416d-9ab1-7c2ef54dd4e6.png)

> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="related-topics"></a>関連トピック

[組織の電話会議の設定を管理する](manage-the-audio-conferencing-settings-for-my-organization.md)

[電話会議に関するよくある質問](/MicrosoftTeams/audio-conferencing-common-questions)
