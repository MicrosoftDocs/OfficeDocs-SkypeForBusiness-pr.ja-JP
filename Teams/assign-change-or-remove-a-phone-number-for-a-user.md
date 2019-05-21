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
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Calling Plans
description: 組織外の企業や顧客が電話をかけられるように、チームまたは Skype for Business ユーザーの勤務先電話番号を割り当て、変更、または削除する方法について説明します。
ms.openlocfilehash: f9792edf76d5d86a562516aa620bfbb62d26fdd9
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34286286"
---
# <a name="assign-change-or-remove-a-phone-number-for-a-user"></a>ユーザーの電話番号を割り当て、変更、または削除する

Office 365 で通話プランをセットアップするときに、ユーザーに電話番号を割り当てます。 

Microsoft Teams クライアントで、[**呼び出し**] をクリックすると、割り当てる電話番号が一覧表示されます。

![ユーザーの電話番号が Microsoft Teams に表示されます。](media/teams-phone-number.png)

Skype for Business クライアントで、割り当てる電話番号が [ **勤務先電話番号** ] ボックスに一覧にされますが、ユーザーが電話番号を変更することはできません。
  
![勤務先電話番号は、グレー表示されます。](media/5212fa64-b55c-4398-9709-a334f3ffa749.png)
  
> [!IMPORTANT]
> ユーザーが [Skype for Business の自分の電話番号を変更](https://support.office.com/article/20e03cc1-c023-4e5d-bafd-064ddb59ed5e) しようとしても、Skype for Business アプリで電話番号を変更できないか、グレー表示されます。つまり、電話番号は管理者がユーザーに対して設定したもので、ユーザーが変更することはできません。
  


ユーザーが電話をかけたり、受けたりできるようにユーザーをセットアップするときは、まず Skype for Business 管理センターを使用して電話番号を割り当てます。このとき、必要に応じて、電話番号を変更したり削除したりできます。
  
Office 365 の通話プランの取得方法とかかる費用については、[Skype for Business と Microsoft Teams アドオン ライセンシング](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing)を参照してください。
  
> [!NOTE]
> ユーザーが割り当てられたライセンスを持っているかを確認するには、**  [Skype for Business 管理センター]**   > **[音声] ** > **[音声ユーザー] **に移動して、ユーザーを選択します。 ライセンスが割り当てられている場合は、 **割り当てられたライセンス**の下にライセンスが表示されます。 Office 365 管理センターを使用することもできます。 
  
 ## <a name="assign-a-phone-number-to-a-user"></a>電話番号をユーザーに割り当てる
 
![sfb-logo-30x30.png](media/sfb-logo-30x30.png) **Skype for Business 管理センターを使用する**
 
1. 職場または学校のアカウントを使用して、Office 365 にサインインします。
    
2. **Microsoft Teams 管理センター** > の**従来のポータル**に移動します。
    
3. 左のナビゲーションで、[ **音声**]  > **[音声ユーザー] **の順にクリックします。
   > [!NOTE]
   > Skype for Business 管理センターの左のナビゲーションに [**音声**] オプションが表示されるようにするには、最初に **Enterprise E5 ライセンス**、**電話システム**アドオン ライセンス、または**電話会議**アドオン ライセンスを少なくとも 1 件購入する必要があります。
 
   
    
4. **ボイス ユーザー** ページで、ユーザー、または電話番号を割り当てるユーザーを見つけて、選択します。
    
5. [操作] ウィンドウで、 **割り当てる番号** をクリックします。
    
6. [**番号を割り当てる**] ページの [**割り当てる番号を選択**] ボックスの一覧で、ユーザー用の電話番号を選びます。
    
    > [!TIP]
    > 電話番号が表示されない場合は、最初に[ユーザーの電話番号を取得](/microsoftteams/getting-phone-numbers-for-your-users)する必要があります。 または、**Skype for Business 管理センター**を使用している場合は、 > **音声** > **電話番号** ページで、[**追加**] をクリックしてから、[ **新しいユーザーの番号**] をクリックします。 
  
7. **有効な緊急対応の場所を選択する**の下で、関連付けられている緊急対応の住所を割り当てるまたは変更するには、リストから場所を選択します。定義された場所が多くある場合は、[検索] ボックスに都市の名前を入力して、**[検索]** をクリックします。
    
8. 電話番号と緊急対応の場所を選択した後、[ **保存**] をクリックします。
    
    > [!NOTE]
    > Office 365 と Skype for Business Online の間の待機時間のために、ユーザーが有効になるまで最大24時間かかることがあります。 24 時間経過しても電話番号が正しく割り当てられない場合は、「[一般法人向けサポートへのお問い合わせ - 管理者向けヘルプ](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)」を参照してください。 ここでは、ご意見をお待ちしています。 
  


 ## <a name="change-a-phone-number-for-a-user"></a>ユーザーの電話番号を変更する
 
![sfb-logo-30x30.png](media/sfb-logo-30x30.png) **Skype for Business 管理センターを使用する**
 
1. 職場または学校のアカウントを使用して、Office 365 にサインインします。
    
2. **Microsoft Teams 管理センター** > の**従来のポータル**に移動します。
    
3. 左のナビゲーションで、[ **音声**]  > **[音声ユーザー] **の順にクリックします。
    
4. **音声ユーザー** ページで、ユーザー、または電話番号を変更するユーザーを見つけて、選択します。
    
5. 操作ウィンドウの [**割り当てられた番号**] で [**変更**] をクリックします。 
    
6. [**番号を割り当てる**] ページで、[**番号を変更**] をクリックします。
    
7. **番号の割り当て**ページの [ **割り当てる番号を選択する**の下で、リストを使用して、新しい電話番号を選択します。 
    
8. 関連付けられた緊急対応の住所を変更するには、[**場所を変更**] をクリックして、**緊急対応の住所の変更**の下で、一覧から場所を選択します。または、定義されている場所が多くある場合、[検索] ボックスに都市の名前を入力して、[**検索**] をクリックします。
    
9. [**保存**] をクリックします。
    


 ## <a name="remove-a-phone-number-from-a-user"></a>ユーザーの電話番号を削除する
 
![sfb-logo-30x30.png](media/sfb-logo-30x30.png) **Skype for Business 管理センターを使用する**
 
1. 職場または学校のアカウントを使用して、Office 365 にサインインします。
    
2. **Microsoft Teams 管理センター** > の**従来のポータル**に移動します。
    
3. 左のナビゲーションで、[ **音声**]  > **[音声ユーザー] **の順にクリックします。
    
4. **音声ユーザー** ページで、ユーザー、または電話番号を削除するユーザーを見つけて、選択します。
    
5. 操作ウィンドウの [**割り当てられた番号**] で、[**削除**] をクリックします。 
    
6. **選択されている割り当て番号を削除しますか？** ページで、[ **はい**] をクリックします。
    

## <a name="related-topics"></a>関連トピック
[住所検証とは何ですか?](/skypeforbusiness/what-are-calling-plans-in-office-365/what-is-address-validation)

[[[Skype for Business 新しい電話番号の申請](/microsoftteams/manage-phone-numbers-for-your-organization)] に移動することによって、電話番号を取得するために利用できるすべてのフォームを一覧表示してダウンロードすることができます。](/microsoftteams/manage-phone-numbers-for-your-organization)

[緊急通話の利用条件](/microsoftteams/emergency-calling-terms-and-conditions)

[Skype for Business Online: 緊急通話の免責事項ラベル](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

  
 