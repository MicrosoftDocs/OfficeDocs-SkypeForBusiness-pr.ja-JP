---
title: 組織内の電話システムの設定
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: makolomi
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service:
- skype-for-business-online
- msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: '組織の電話システム (PBX をクラウド) を設定する方法について説明します。 '
ms.openlocfilehash: 0ae2d890e87ecef217bfdafd2c547de7ae35414d
ms.sourcegitcommit: 60e8365281ec6d780f1b2439bedef0bd71f002d8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2019
ms.locfileid: "30047563"
---
# <a name="setting-up-phone-system-in-your-organization"></a>組織内の電話システムの設定

The following is a step-by-step guide for setting up Phone System in Office 365. Links to additional, detailed information are available at the end of each step.

## <a name="step-1-make-sure-that-phone-system-is-available-in-your-country-or-region"></a>ステップ 1: 電話システムは、国または地域で利用可能なことを確認します。

1.  最初に [オーディオ会議や通話プランのための国および地域の可用性](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md) へ進み、ページの上部にある一覧表から国または地域を選択します。 
2.   **電話システム** での機能と詳細の一覧を確認します。 
3.  電話システムが使用可能な場合は、手順 2 に進みます。 

**電話システムおよびオーディオ会議の地域別利用可能時間に関する詳細については、 [オーディオ会議や通話プランのための国および地域の可用性](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md) を参照してください。**

## <a name="step-2-buy-and-assign-phone-system-and-calling-plan-licenses"></a>手順 2: 電話システムおよび通話プランのライセンスを購入し、割り当てる

To assign a Phone System and Calling Plan license to a single user the steps are the same as assigning an Office 365 license. See [Assign Skype for Business and Microsoft Teams licenses](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses). If you want to assign multiple users in bulk, see [Assign Skype for Business and Microsoft Teams licenses](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses).

## <a name="step-3-get-phone-numbers-for-your-users"></a>手順 3: ユーザーの電話番号を取得します。

[] 組織内でユーザーが電話を発着信できるように設定するには、組織のための電話番号を取得する必要があります。

ユーザーに番号を取得する 3 つの方法があります。
- Skype for Business 管理センターを使用して、新しい電話番号を取得する。
- Skype for Business管理センターでは使用できない、新しい番号を取得します。
- 現在のサービス プロバイダーまたは携帯電話会社から Office 365 に既存の番号を移行する。

You must use the **Add new user numbers** page to see, search, acquire, and reserve those numbers. You can search by Country/Region, State, and City, and then enter the number of phone numbers you will need for your users.

### <a name="get-new-user-phone-numbers"></a>新しいユーザーの電話番号を取得します。 
 
![sfb-logo-30x30.png](media/sfb-logo-30x30.png) **Skype for Business の管理センターを使用する**

1. You can go to Dial-in conferencingDial-in users and select the user's properties to change the default number for a user by choosing a new number from the list of numbers that are available in your organization.

2. Go to the **Office 365 admin center** > **Skype for Business**.
    
3. 左側のナビゲーションでは、**音声**に移動 > **電話番号**、**新しい番号を追加**をクリックして![[追加] ボタン](media/c224fbd0-f0f5-46ce-a1a7-73adf4540ef7.png)、し、**新しいユーザーの番号**をクリックします。
    
### <a name="get-new-numbers-that-arent-available-in-the-skype-for-business-admin-center"></a>Skype for Business管理センターでは使用できない、新しい番号を取得します。
  
Sometimes (depending on your country/region) you won't be able to get your new numbers using the Skype for Business admin center. In this case, you will need to download a form and send it back to us. See [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) to learn how to request new user numbers.   
  
### <a name="port-or-transfer-phone-numbers-from-your-service-provider-or-phone-carrier"></a>使用中のサービス プロバイダーまたは携帯電話会社から電話番号を移行する
  
- If you need 999 or fewer phone numbers for your users, you can use the **New Local Number Port Order** wizard in the Skype for Business admin center. Follow the steps found in [Transfer phone numbers to Office 365](transfer-phone-numbers-to-office-365.md) to transfer your phone numbers over to Skype for Business Online.
    
- 999 を超える数の電話番号のポートが必要な場合は、ポート注文サービスの要求またはすべての Office 365 に移植されたこれらの電話番号を取得する順序を送信するのには[、組織の電話番号の管理](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)を参照してください。 

**新しい電話番号を取得するか、既存の番号を転送する方法の詳細については、 [組織の電話番号の管理](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) を参照してください。**

## <a name="step-4-get-service-phone-numbers-audio-conferencing-call-queues-auto-attendants"></a>手順 4: サービス用の電話番号 (電話会議、通話キュー、自動応答) を取得します。

In addition to getting phone numbers for your users from Office 365, you can search and acquire toll or toll-free phone numbers for services such as audio conferencing (for conference bridges), auto attendants, and call queues (also called service numbers). Service phone numbers have a higher concurrent calling capacity than user or subscriber phone numbers. For example, a service number can handle 100s of calls simultaneously, whereas a user's phone number can only handle a few calls simultaneously.

### <a name="get-new-service-numbers"></a>新しいサービス番号を取得する

![sfb-logo-30x30.png](media/sfb-logo-30x30.png) **Skype for Business の管理センターを使用する**


1. You can go to Dial-in conferencingDial-in users and select the user's properties to change the default number for a user by choosing a new number from the list of numbers that are available in your organization.

2. Go to the **Office 365 admin center** > **Skype for Business**.

3. 左側のナビゲーションでは、**音声**に移動 > **電話番号** > **新しい番号を追加**し、**新しいサービスの番号**をクリックします。

    > [!IMPORTANT]
    > ビジネス管理センターの Skype では、左側のナビゲーションの**音声**オプションを表示するため、まず**E5 のエンタープライズ ライセンス**を少なくとも 1 つ、1 つの**電話システム**のアドオン ライセンスまたはアドオンのライセンスが 1 つの**電話会議**を購入する必要があります。

### <a name="get-new-numbers-that-arent-available-in-the-skype-for-business-admin-center"></a>Skype for Business管理センターでは使用できない、新しい番号を取得します。
  
Sometimes (depending on your country/region) you won't be able to get your new numbers using the Skype for Business admin center. In this case, you will need to download a form and send it back to us. See [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) to learn how to request new numbers. 

### <a name="port-or-transfer-existing-service-numbers"></a>既存のサービス番号を移行または転送する

If you want to transfer service numbers from your current service provider or carrier, you need to manually submit a port order to Microsoft. You have to submit separate port orders for each type of service number (toll vs. toll-free) that you will be transferring using a Letter of Authorization (LOA). In the Letter of Authorization (LOA), you must select the correct type of service number. When contacting Microsoft support, please make sure you specify that you are transferring a service number (*and not a user or subscriber number*), or the concurrent calling capacity may not be enough to handle call volumes. If you want to transfer phone numbers or do other things with your phone numbers, see [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).

## <a name="step-5-if-you-want-to-set-up-calling-plans"></a>手順 5: 通話プランを設定する場合

If you have been following the steps above, you have already bought and assigned Phone System and licenses and a Calling Plan (step 2) and acquired phone numbers for your users (step 3), so your calling plan is partially set up. Follow the three procedures below to complete the setup of your Calling Plan.

### <a name="add-emergency-addresses-and-locations-for-your-organization"></a>緊急時のアドレスと、組織の場所を追加します。

1. **緊急の場所**を選択して [**音声**] ページで、 > **新しいアドレスを追加**します。

2. [ **新しい住所**] ウィンドウで、住所の名前を入力し、残りのボックスの入力を完了します。
    
     ![新しい緊急時のアドレスを入力すると、住所の書式設定がエラーを引き起こす可能性があります。](media/dc1c5ef3-0554-4fb7-9ab1-5ea3ac9e5eb5.png)
  
    > [!TIP]
    > 上の図のように、英語圏のお客様で街路名が数字の場合は、必ず末尾に「st」または「th」を付けます。

3. [ **検証**] を選択します。

    必要な場合は、住所の訂正を求められます。

    > [!CAUTION]
    > Validating a street or civic address involves making sure that it is legitimate and correctly formatted. It is possible that a partially correct emergency address, such as if you mistyped the name of the city, may still pass validation. Even though it's misspelled and passed validation, the combination of the misspelled name of city along with the other correct parts of the address are enough information to route the call to the appropriate emergency dispatch center.

    > [!TIP]
    > 緊急応答用に住所に修正が必要な場合は、住所が更新されたことを通知する緑色のバナーが表示されます。

4. 住所が検証されたら、[ **保存**] を選びます。

### <a name="assign-phone-numbers-and-emergency-addresses-to-users"></a>ユーザーに電話番号と緊急対応の住所を割り当てる

> [!TIP]
> この手順を実行する直前にさらにユーザーを追加すると、[ **音声ユーザー**] ページにユーザーが表示されるまでに **数時間** かかることがあります。これには遅延時間があります。

1. **ボイス ユーザー**ページで、電話番号と緊急時のアドレスを割り当てたいユーザーを選択します。

2. [操作] ウィンドウで、 **割り当てる番号** をクリックします。

3. **番号の割り当て**] ページで、**割り当てる番号の選択**] ボックスの一覧で、ユーザーの電話番号を選択します。

4. 緊急アドレスを選択するには、都市の名前をボックスに入力し、**検索**を選択します。

    > [!IMPORTANT]
    > If you are outside the United States, your numbers already have an emergency address, but you can change it now. See [Assign or change an emergency address for a user](/skypeforbusiness/what-are-calling-plans-in-office-365/assign-or-change-an-emergency-address-for-a-user). 
  
5. 電話番号と緊急対応の住所の両方を割り当てたら、[ **保存**] を選びます。

### <a name="tell-your-users-about-their-new-phone-numbers"></a>に関する新しい電話番号をユーザーに連絡します。


新しい電話番号をユーザーに通知する場合は、メールを送信するか、または各組織が指定する方法で行うことをお勧めします。

以下は、**ビジネスの Skype**アプリでは、その電話番号を表示できる方法です。

1. デスクトップで Skype for Business にサインインします。
    
2.  **Settings** > **Tools** > **Options** を選択します。 
    
     ![電話番号を表示するには、設定 > ツール > オプション。](media/20637117-91d7-4a7e-9f06-7abc634a9211.png)
  
3. 次に、[ **電話**] を選びます。 
    
    ![A user can see their assign number in the Skype for Business app by choosing Settings > Tools > Options > Phone.](media/0128d667-2bf8-4165-b703-e9b78a15b63c.png)
 
In **Microsoft Teams**, users can see their phone number by clicking **Calls** in the left navigation. The phone number is shown above the dial pad.

![ユーザーは、左側のナビゲーションで呼び出しをクリックすると、Microsoft Teams で番号を確認できます。](media/teams-phone-number.png)

**通話プランを設定する手順すべての詳細については、 [通話プランの設定](set-up-calling-plans.md) を参照してください。**


## <a name="step-6-if-you-want-to-set-up-audio-conferencing"></a>手順 6: 電話会議を設定する場合

Sometimes people in your organization will need to use a phone to call in to a meeting. Skype for Business and Microsoft Teams include the audio conferencing feature for just this situation! People can call in to Skype for Business or Microsoft Teams meetings using a phone, instead of using the Skype for Business or Microsoft Teams app on a mobile device or PC.

You only need to set up Audio Conferencing for people who plan to schedule or lead meetings. Meeting attendees who dial in don't need any licenses assigned to them or other setup.
  
電話会議についてよく寄せられる質問については、 [電話会議についてよくある質問](audio-conferencing-common-questions.md) を参照してください。
    
1. If you purchased **Audio Conferencing** add-on licenses and Communications Credits licenses, assign them too. For instructions, see [Assign Skype for Business and Microsoft Teams licenses](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses).

    Decide on your audio conferencing provider. An audio conferencing provider supplies an audio conferencing bridge. The conferencing bridge sets your dial-in phone numbers, PINs, and conference IDs for meetings. Decide whether to use Microsoft or a third-party audio conferencing provider:

    > [!NOTE]
    > Microsoft Teams のユーザーには、Microsoft 以外の電話会議プロバイダーを使うことはできません。

    - **電話会議プロバイダーとしての Microsoft**: 電話会議の最も簡単なソリューションをお求めなら、電話会議プロバイダーとして Microsoft を選択します。
    
    - **Third party as your audio conferencing provider**: If you are in a country where Audio Conferencing in Office 365 isn't available, the service quality isn't great because of its location, or you have an existing contract, choose a third-party audio conferencing provider. To find a provider, go to [Microsoft PinPoint](http://go.microsoft.com/fwlink/?LinkId=797530).
 
2. Assign the audio conferencing provider to people who lead or schedule meetings. See [Assign Microsoft as the audio conferencing provider](/skypeforbusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider).

3. Set up meeting invitations. The following steps are optional, but a lot of admins like to do them: 
  
   1. [ビジネス用の Skype でミーティングの招待状をカスタマイズ](/skypeforbusiness/set-up-skype-for-business-online/customize-meeting-invitations)します。 ユーザー向けに設定されているダイヤルイン番号は、会議の出席者に送信される会議出席依頼に自動的に追加されます。 ただし、独自のヘルプや法務関連リンク、テキスト メッセージ、会社の小さな画像を追加できます。
    
   2. [ビジネス用の Skype](/skypeforbusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites)または[マイクロソフトのチームで](set-the-phone-numbers-included-on-invites-in-teams.md)ミーティングの開催者に含まれているへの招待には、電話会議の電話番号を設定します。 これは、ユーザーが開催を予定している会議で表示される電話番号です。
    
   3. [ビジネス用の Skype で](/skypeforbusiness/audio-conferencing-in-office-365/set-auto-attendant-languages-for-audio-conferencing)電話会議、または[マイクロソフトのチームで](set-auto-attendant-languages-for-audio-conferencing-in-teams.md)の電話会議の電話番号にダイヤルするときに、呼び出し元を呼びかけられるように設定するのには、オーディオ会議自動アテンダントを使用するには、自動アテンダントの言語を設定します。 この手順は、Microsoft を電話会議プロバイダーとして使用している場合にのみ適用されます。
    
   4. オーディオ会議の会議の暗証番号 (pin) の長さを設定する[ビジネス用の Skype](/skypeforbusiness/audio-conferencing-in-office-365/set-the-pin-length-for-audio-conferencing-meetings)または[マイクロソフトのチームで](set-the-pin-length-for-audio-conferencing-meetings-in-teams.md)。
    
      > [!NOTE]
      > This feature is not yet available to customers using Office 365 operated by 21Vianet in China. To learn more, see [Learn about Office 365 operated by 21Vianet](https://support.office.com/article/A8AB5061-3346-4DA0-BB7C-5260822B53AE).

**電話会議の詳細については、 [電話会議の設定](/skypeforbusiness/audio-conferencing-in-office-365/set-up-audio-conferencing) を参照してください。**

## <a name="step-7-if-you-want-to-set-up-a-phone-system-call-queue"></a>手順 7: 電話システムの通話キューを設定する場合

Phone System call queues include greetings that are used when someone calls in to a phone number for your organization, the ability to automatically put the calls on hold, and the ability to search for the next available call agent to handle the call while the people who call are listening to music on hold. You can create single or multiple call queues for your organization.

Before you can create and set up your call queues, you will need to get or transfer your existing toll or toll-free service numbers. After you get the toll or toll-free service phone numbers, they will show up in **Skype for Business admin center** > **Voice** > **Phone numbers**, and the **Number type** listed will be listed as **Service - Toll-Free**. To get your service numbers, see [Getting service phone numbers for Skype for Business and Microsoft Teams](/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers) or if you want to transfer and existing service number, see [Transfer phone numbers to Office 365](transfer-phone-numbers-to-office-365.md).
  
> [!NOTE]
> If you are outside the United States, you can't use the Skype for Business admin center to get service numbers. Go to [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) instead to see how to do it from the outside of the United States.

  **Skype for Business 管理センター** で、新しい通話キューを作成するには、 **通話ルーティング** > **通話キュー** をクリックし、  **新規追加** をクリックし、 [電話システム呼び出しキューを作成する](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue#step-3---create-a-new-call-queue) の  **手順 3** の指示に従います。

**通話キューの詳細については、 [電話システムの通話キューを作成する](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue) を参照してください。**

## <a name="step-8-if-you-want-to-set-up-a-phone-system-auto-attendant"></a>手順 8: 自動応答電話システムを設定する場合

Auto attendants let people that call in to your organization and navigate a menu system to get them to the right department, call queue, person, or the operator. You can create an auto attendant for your organization by using the Skype for Business admin center.

Skype for Business 管理センターで、新しい自動応答を作成するには、 **通話ルーティング** > **自動応答** をクリックし、 **新規追加**をクリックし、 [自動応答電話システム設定](/SkypeForBusiness/what-is-phone-system-in-office-365/set-up-a-phone-system-auto-attendant#step-2---create-a-new-auto-attendant) の **ステップ 2** の指示に従って下さい。

**電話システムの自動応答の詳細については、 [電話システムの自動応答の設定](/SkypeForBusiness/what-is-phone-system-in-office-365/set-up-a-phone-system-auto-attendant) を参照してください。**

## <a name="step-9-assign-service-phone-numbers-audio-conferencing-call-queues-auto-attendants"></a>手順 9: サービス用電話番号 (電話会議、通話キュー、自動応答) の割り当て

Once you have your service numbers from **Step 4 above**, you need to assign them to each type of service that you want. For example, if you want a dedicated service phone number (toll or toll-free), you will need to assign the number to the conferencing bridge.

- 電話会議用に専用番号を会議用ブリッジに割り当てることができます。それには、 **Office 365 の管理センター** > **管理センター** > **Skype for Business** > **電話会議** に進み、会議ブリッジをクリックするか、 [電話会議ブリッジ上の有料・無料番号を変更する](change-the-phone-numbers-on-your-audio-conferencing-bridge.md) を参照してください。

- For Auto Attendants, you can assign a dedicated number to an auto attendant by going to **Office 365 admin center** > **Admin centers** > **Skype for Business** > **Call routing** > **Auto attendants** and click on the auto attendant. On the **General** page the service number you already have will be listed in the **Phone number** drop down. For details, see [Set up a Phone System Auto Attendant](/SkypeForBusiness/what-is-phone-system-in-office-365/set-up-a-phone-system-auto-attendant).

- For Call Queues, you can assign a dedicated number to a call queue by going to **Office 365 admin center** > **Admin centers** > **Skype for Business** > **Call routing** > **Call queues** and click on the call queue. On the **General** page the service number you already have will be listed in the **Phone number** drop down. For details, see [Create a Phone System call queue](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue).

**新しいサービス番号を取得し、既存のサービス番号を転送する方法の詳細については、 [サービスの電話番号の取得](/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers)  を参照してください。**

## <a name="step-10-set-up-communications-credits-for-your-organization"></a>通信のクレジット、組織の設定手順 10。

You will need to set up Communications Credits if you would like to use toll-free numbers with Skype for Business and Microsoft Teams. Also, we recommend that you set up Communications Credits for your Calling Plans (Domestic or International) and Audio Conferencing users who need the ability to dial out to **any destination**. Many countries/regions are included, but some destinations may not be included in your Calling Plan or Audio Conferencing subscriptions. If you don't set up Communications Credits billing and assign a **Communications Credits** license to your users and you run out minutes for your organization (depending on your Calling Plan or Audio Conferencing plan in your country/region), those users won't be able to make calls or dial out from Audio Conferencing meetings. You can get more information, including recommended funding amounts, by reading [What are Communications Credits?](what-are-communications-credits.md)
  
> [!NOTE]
> 費用を確認するには、[こちらで料金をご覧ください](https://go.microsoft.com/fwlink/p/?LinkId=799523 )。

### <a name="to-set-up-communications-credits"></a>通信のクレジットを設定するには

1. 職場または学校のアカウントを使用して、Office 365 にサインインします。

2. Office 365 管理ページ左側のナビゲーションで  **請求** > **サブスクリプション** > **アドオン** > **アドオンの購入** に進み、 **コミュニケーションクレジット** > **今すぐ購入** を選択してください。

3. **通信のクレジット**申し込みのページでの情報を入力し、[**次へ**] をクリックします。

4. 支払い情報を入力して、[ **注文**] をクリックします。
    >[!IMPORTANT]
    >If you are a volume licensing customer, you may choose your enterprise agreement number for payment. If you have multiple enterprise agreement numbers, you will be able to select which enterprise agreement you would like to use for payment. You will also be given an opportunity to specify a purchase order number to associate with the enterprise agreement number (if applicable).
    
**コミュニケーションクレジットの設定に関する詳細については、 [組織のコミュニケーションクレジットを設定](set-up-communications-credits-for-your-organization.md) を参照してください。**
  
### <a name="assign-a-communications-credits-license-to-users"></a>通信のクレジットのライセンスをユーザーに割り当てる

1. 職場または学校のアカウントを使用して、Office 365 にサインインします。

2. Office 365 管理ページの左側のナビゲーションで、 **ユーザー** > **アクティブなユーザー** に進み、そのリストから一人、または複数のユーザーを選択します。

3. 操作ウィンドウの [ **製品ライセンス**] で [ **編集**] をクリックします。

4. [**製品ライセンス**] ページで、**上**、本ライセンスを割り当てるには、**通信のクレジット**を切り替えるし、[**保存**] をクリックします。

    > [!NOTE]
    > **Enterprise E5** ライセンスが割り当てられているユーザーがいる場合でも、この手順を行うことをお勧めします。

**コミュニケーションクレジットのライセンスの割り当ての詳細については、 [組織用コミュニケーションクレジットの設定](set-up-communications-credits-for-your-organization.md) を参照してください。**

## <a name="related-topics"></a>関連トピック
[Office 365 での電話システムで利用できる機能](here-s-what-you-get-with-phone-system.md)

[Skype for Business および Microsoft Teams のサービス電話番号の取得](/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers)

[国および地域ごとの電話会議および通話プランの利用可能性](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
    
  
 
