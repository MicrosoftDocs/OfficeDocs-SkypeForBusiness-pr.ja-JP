---
title: ユーザーの電話番号を割り当て、変更、または削除する
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: 91089761-cb87-4119-885b-3713840dd9f7
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Calling Plans
description: 外部のビジネスやクライアントがコールインできるように、勤務先電話番号を Skype for Business ユーザーに割り当てる、変更する、または削除する方法を学びます。
ms.openlocfilehash: 0e354956d1077b2f81de7b889d8085f05db038c4
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32235694"
---
# <a name="assign-change-or-remove-a-phone-number-for-a-user"></a>ユーザーの電話番号を割り当て、変更、または削除する

Office 365 のプランの呼び出しを設定すると、ユーザーに電話番号を割り当てます。 

Microsoft Teams クライアントで、[**呼び出し**] をクリックすると、割り当てる電話番号が一覧表示されます。

![ユーザーの電話番号が Microsoft Teams に表示されます。](../images/teams-phone-number.png)

Skype for Business クライアントで、割り当てる電話番号が [ **勤務先電話番号** ] ボックスに一覧にされますが、ユーザーが電話番号を変更することはできません。
  
![勤務先電話番号は、グレー表示されます。](../images/5212fa64-b55c-4398-9709-a334f3ffa749.png)
  
> [!IMPORTANT]
> ユーザーが [Skype for Business の自分の電話番号を変更](https://support.office.com/article/20e03cc1-c023-4e5d-bafd-064ddb59ed5e) しようとしても、Skype for Business アプリで電話番号を変更できないか、グレー表示されます。つまり、電話番号は管理者がユーザーに対して設定したもので、ユーザーが変更することはできません。
  


ユーザーが電話をかけたり、受けたりできるようにユーザーをセットアップするときは、まず Skype for Business 管理センターを使用して電話番号を割り当てます。このとき、必要に応じて、電話番号を変更したり削除したりできます。
  
Office 365 の通話プランの取得方法とかかる費用については、[Skype for Business と Microsoft Teams アドオン ライセンシング](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)を参照してください。
  
> [!NOTE]
> One way to see whether a user has a license assigned is by going to **Skype for Business admin center** > **Voice** > **Voice users** and selecting the user. If a license is assigned, it will be noted under **Assigned license**. You also can use the Office 365 admin center. 
  
 ## <a name="assign-a-phone-number-to-a-user"></a>ユーザーに電話番号を割り当てる
 
![デバイスのロゴ-30x30.png](../images/sfb-logo-30x30.png) **ビジネス管理センターの Skype を使用します。**
 
1. 職場または学校のアカウントを使用して、Office 365 にサインインします。
    
2. **マイクロソフトのチーム管理センター**を参照して > **従来のポータル**です。
    
3. 左のナビゲーションで、[ **音声**]  > **[音声ユーザー] **の順にクリックします。
   > [!NOTE]
   > ビジネス管理センターの Skype では、左側のナビゲーションの**音声**オプションを表示するため、まず**E5 のエンタープライズ ライセンス**を少なくとも 1 つ、1 つの**電話システム**のアドオン ライセンスまたはアドオンのライセンスが 1 つの**電話会議**を購入する必要があります。
 
   
    
4. **ボイス ユーザー** ページで、ユーザー、または電話番号を割り当てるユーザーを見つけて、選択します。
    
5. [操作] ウィンドウで、 **割り当てる番号** をクリックします。
    
6. [**割り当てる番号の選択**] ボックスの一覧で**番号を割り当てる**] ページで、ユーザーの電話番号を選択します。
    
    > [!TIP]
    > 電話番号の一覧が表示されない場合する必要があります[、ユーザーの電話番号を取得](getting-phone-numbers-for-your-users.md)する最初にします。 または、**Skype for Business 管理センター**を使用している場合は、 > **音声** > **電話番号** ページで、[**追加**] をクリックしてから、[ **新しいユーザーの番号**] をクリックします。 
  
7. **有効な緊急対応の場所を選択する**の下で、関連付けられている緊急対応の住所を割り当てるまたは変更するには、リストから場所を選択します。定義された場所が多くある場合は、[検索] ボックスに都市の名前を入力して、**[検索]** をクリックします。
    
8. 電話番号と緊急対応の場所を選択した後、[ **保存**] をクリックします。
    
    > [!NOTE]
    > Because of the latency between Office 365 and Skype for Business Online, it can possibly take up to 24 hours for users to be enabled. If after 24 hours, if the phone number isn't assigned correctly, please [Contact support for business products - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b). We're here to help! 
  


 ## <a name="change-a-phone-number-for-a-user"></a>ユーザーの電話番号を変更します。
 
![デバイスのロゴ-30x30.png](../images/sfb-logo-30x30.png) **ビジネス管理センターの Skype を使用します。**
 
1. 職場または学校のアカウントを使用して、Office 365 にサインインします。
    
2. **マイクロソフトのチーム管理センター**を参照して > **従来のポータル**です。
    
3. 左のナビゲーションで、[ **音声**]  > **[音声ユーザー] **の順にクリックします。
    
4. **音声ユーザー** ページで、ユーザー、または電話番号を変更するユーザーを見つけて、選択します。
    
5. [操作] ウィンドウで、**割り当て番号**の下の [**変更**] をクリックします。 
    
6. **番号の割り当て**] ページで、**変更番号**をクリックします。
    
7. **番号の割り当て**ページの [ **割り当てる番号を選択する**の下で、リストを使用して、新しい電話番号を選択します。 
    
8. 関連付けられた緊急対応の住所を変更するには、[**場所を変更**] をクリックして、**緊急対応の住所の変更**の下で、一覧から場所を選択します。または、定義されている場所が多くある場合、[検索] ボックスに都市の名前を入力して、[**検索**] をクリックします。
    
9. **[保存]** をクリックします。
    


 ## <a name="remove-a-phone-number-from-a-user"></a>ユーザーの電話番号を削除する
 
![デバイスのロゴ-30x30.png](../images/sfb-logo-30x30.png) **ビジネス管理センターの Skype を使用します。**
 
1. 職場または学校のアカウントを使用して、Office 365 にサインインします。
    
2. **マイクロソフトのチーム管理センター**を参照して > **従来のポータル**です。
    
3. 左のナビゲーションで、[ **音声**]  > **[音声ユーザー] **の順にクリックします。
    
4. **音声ユーザー** ページで、ユーザー、または電話番号を削除するユーザーを見つけて、選択します。
    
5. [操作] ウィンドウで、[**割り当ての数**、[**削除**] をクリックします。 
    
6. **選択されている割り当て番号を削除しますか？** ページで、[ **はい**] をクリックします。
    

## <a name="related-topics"></a>関連トピック
[住所検証とは何ですか?](what-is-address-validation.md)

[[[Skype for Business 新しい電話番号の申請](/microsoftteams/manage-phone-numbers-for-your-organization)] に移動することによって、電話番号を取得するために利用できるすべてのフォームを一覧表示してダウンロードすることができます。](/microsoftteams/manage-phone-numbers-for-your-organization)

[緊急通話の利用条件](/microsoftteams/emergency-calling-terms-and-conditions)

[Skype for Business Online: 緊急通話の免責事項ラベル](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

  
 