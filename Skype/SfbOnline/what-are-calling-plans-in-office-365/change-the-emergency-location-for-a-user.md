---
title: ユーザーの緊急対応の場所の割り当てまたは変更
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: 2d5d3c87-af1e-487e-b86c-261f2e5a0661
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Calling Plans
description: 'Learn how to change the emergency location for your users. With an unlimited number of locations, you can change emergency locations as employees move floors or buildings. '
ms.openlocfilehash: 49410b0ba98e6d193749b558e479d98de1f4ef29
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34303836"
---
# <a name="assign-or-change-the-emergency-location-for-a-user"></a>ユーザーの緊急対応の場所の割り当てまたは変更

電話番号をユーザーに割り当てるときは、有効な電話番号ごとに対応する緊急対応の住所が必要です。 (住所は、Office 365 で電話番号を取得する場合、または電話番号を移行する場合に関連付けます)。電話番号を緊急対応の住所に関連付けている場合は、緊急対応の場所を追加して、物理的な場所でより正確な位置情報を提供することもできます。 An emergency location can be the floor, building wing, or office number where the user is located. 特定の緊急対応の住所には無制限の場所を含めることができます。また、ユーザーがフロア34からフロア35に移動した場合など、ユーザーが別のオフィスや建物に移動した場合は、緊急対応の場所を変更することができます。
  
Office 365 の通話プランの取得方法とかかる費用については、「[Skype for Business と Microsoft Teams アドオン ライセンシング](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)」を参照してください。
  
## <a name="assign-or-change-the-emergency-location"></a>緊急対応の場所を割り当てる、または変更する

1. 職場または学校のアカウントを使用して、Office 365 にサインインします。
    
2. **Microsoft Teams 管理センター** > の**従来のポータル**に移動します。
    
3. 左のナビゲーションで、[**音声** > **音声ユーザー**に移動します。
    
    > [!IMPORTANT]
    > Skype for Business 管理センターの左のナビゲーションに [**音声**] オプションが表示されるようにするには、最初に **Enterprise E5 ライセンス**、**電話システム**アドオン ライセンス、または**電話会議**アドオン ライセンスを少なくとも 1 件購入する必要があります。
    
4. [**音声ユーザー** ] ページで、緊急対応の場所を変更するユーザーを探して選びます。
    
5. 操作ウィンドウの [ **緊急対応の場所**] で [ **変更**] をクリックします。
    
6. [**番号を割り当てる**] ページで、[**場所の変更**] をクリックします。 
    
7. [**緊急対応の住所の変更先**] で、ボックスに市区町村の名前を入力し、[**検索**] をクリックします。

8. ドロップダウンリストから [**場所で検索**] を選択し、場所の部分名 (「**床面**」など) を入力して、「**検索**」をクリックします。 
    
8. リストから緊急対応の場所を選択し、[**保存**] をクリックします。
    
    リストに表示される新しい緊急対応の場所を追加する場合は、「[組織の緊急対応の場所を追加、変更、削除](add-change-or-remove-an-emergency-location-for-your-organization.md)する」を参照してください。
    
## <a name="related-topics"></a>関連トピック

[Powershell を使用して緊急対応の場所を割り当てる](https://github.com/MicrosoftDocs/office-docs-powershell/blob/master/skype/skype-ps/skype/Set-CsOnlineVoiceUser.md)

[組織の緊急対応の住所を追加または削除する](add-or-remove-an-emergency-address-for-your-organization.md)

[組織の緊急対応の場所を追加、変更、削除する](add-change-or-remove-an-emergency-location-for-your-organization.md)

[住所検証とは何ですか?](what-is-address-validation.md)

[[[Skype for Business 新しい電話番号の申請](/microsoftteams/manage-phone-numbers-for-your-organization)] に移動することによって、電話番号を取得するために利用できるすべてのフォームを一覧表示してダウンロードすることができます。](/microsoftteams/manage-phone-numbers-for-your-organization)

[緊急通話の利用条件](/microsoftteams/emergency-calling-terms-and-conditions)

[Skype for Business Online: 緊急通話の免責事項ラベル](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

[CsOnlineVoiceUser コマンドレット](https://docs.microsoft.com/en-us/powershell/module/skype/set-csonlinevoiceuser?view=skype-ps)

  
 
