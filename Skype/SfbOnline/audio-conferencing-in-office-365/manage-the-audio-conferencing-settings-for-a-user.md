---
title: Skype for Business Online のユーザーの電話会議の設定を管理する
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
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 'Office 365 管理者としてSkype for Business Onlineの音声会議の設定 を編集することができます-プロバイダー、既定の有料または無料電話番号、会議 ID、暗証番号 (pin) など、組織内の個々 のユーザーの設定です。 '
ms.openlocfilehash: fe6814bee547e80d6bcb6fc367d055dce13d513d
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "43777992"
---
# <a name="manage-the-audio-conferencing-settings-for-a-user-in-skype-for-business-online"></a>Skype for Business Online のユーザーの電話会議の設定を管理する

> [!Note]
> Microsoft Teams でユーザー設定を管理する場合は、「 [Microsoft teams でユーザーの電話会議の設定を管理](/MicrosoftTeams/manage-the-audio-conferencing-settings-for-a-user-in-teams)する」を参照してください。

Office 365 管理者としてSkype for Business Onlineの電話会議の設定 を編集することができます-プロバイダー、既定の有料または無料電話番号、会議 ID、暗証番号 (pin) など、組織内の個々 のユーザーの設定です。 組織の設定を編集する場合は、「[組織の電話会議の設定を管理](manage-the-audio-conferencing-settings-for-my-organization.md)する」を参照してください。

 
1. 職場または学校のアカウントを使用してサインインします。
    
2. [**管理センター**]  >  [**Skype for Business**]を選択します。
    
3. Skype for Business 管理センターで、[**ユーザー**] を選びます。
    
4. 設定を管理するユーザーを選択し、操作 ウィンドウで、**編集** をクリックして![編集 アイコンを表示します](../images/4d8bea48-be68-4e0e-a54c-73decf7ea4ec.png)。
    
5. 左側のナビゲーションで、 **電話会議** を選択し、ユーザーの **プロパティ**  ページで、次のいずれかを変更します。
    
|**設定**|**説明**|
|:-----|:-----|
|**プロバイダー名** <br/> |リストからプロバイダーを選択します。  <br/><br/> **注:** このテーブル内の残りの設定は、音声会議プロバイダーとして Microsoft を選択した場合にのみ適用されます。           |
|**既定の有料電話番号** (必須) <br/> |これらの電話番号は、電話会議プロバイダーからサードパーティのプロバイダー用に入手したものです。 ユーザーが、Microsoft を電話会議プロバイダーとして使用している場合は、これらは電話会議ブリッジで設定されている番号となります。 Skype for Business および Microsoft Teams の会議出席依頼に表示する番号の書式を設定します。  <br/> |
|**既定の無料電話番号** <br/> |これらの電話番号は、電話会議プロバイダーからサードパーティのプロバイダー用に入手したものです。 ユーザーが、Microsoft を電話会議プロバイダーとして使用している場合は、これらは電話会議ブリッジで設定されている番号となります。 Skype for Business および Microsoft Teams の会議出席依頼に表示する番号の書式を設定します。  <br/> |
|**このユーザーのミーティングに参加するには、組織の Microsoft ブリッジで無料電話番号を使用できるようにします。** <br/> |フリー ダイヤル番号のユーザーに会議の参加を許可する場合は、このオプションを選択します。  <br/> |
|**会議情報をメールで送信する** <br/> |ユーザーに電子メールで会議 ID と電話番号とをすぐに送信する場合にのみ、このリンクをクリックします。 (PINはこのメールは含まれません。) [ユーザーに電子メールで電話会議の情報を送信する](send-an-email-to-a-user-with-their-dial-in-information.md)を参照してください。  <br/> |
|**会議 ID** <br/> |ユーザーの会議 ID をリセットする必要がある場合は、 **リセット** を選択します。 詳細については、 [ユーザーの会議 ID をリセットする](reset-a-conference-id-for-a-user.md)を参照してください。  <br/> |
|**ヒント** <br/> |ユーザーの PIN をリセットする必要がある場合は、 **リセット** を選択します。 詳細については、 [電話会議の PIN のリセット](reset-the-audio-conferencing-pin.md)を参照してください。  <br/> |
|**認証されていない呼び出し元が会議の最初のユーザーになることを許可します。** <br/> |認証されていない呼び出し元が最初にミーティングに参加することを許可するには、このオプションを選択します。  <br/> |
|**このユーザーの会議からのダイヤル アウトを制限** <br/> |ダイヤル アウトを国内のみに制限する場合、または会議からすべてのダイヤル  アウトを禁止したい場合、このリストでオプションを選択します。  <br/> |
  
![ユーザーの音声会議のプロパティ ページを示しています。](../images/228550f7-92be-416d-9ab1-7c2ef54dd4e6.png)

> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="related-topics"></a>関連トピック

[組織の電話会議の設定を管理する](manage-the-audio-conferencing-settings-for-my-organization.md)

[電話会議に関するよくある質問](/MicrosoftTeams/audio-conferencing-common-questions)
