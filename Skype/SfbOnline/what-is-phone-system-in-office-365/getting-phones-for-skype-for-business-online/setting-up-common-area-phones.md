---
title: 共通エリア電話機を設定する
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: wasseemh
ms.topic: article
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
- Phone System
description: 適切なファームウェアを取得し、更新が必要な場合、ライセンスを割り当てる共通領域電話の設定を構成、展開の手順を説明します。
ms.openlocfilehash: 3faa66235f3c3364a0da6560a6dc52daa252915b
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/04/2018
ms.locfileid: "25370677"
---
# <a name="set-up-common-area-phones"></a>共通エリア電話機を設定する
A common area phone (CAP) is typically placed in an area like a lobby or another area that is available to a lot of people. For example, a reception area phone, door phone or meeting room phone, CAPs are set up as devices rather than users and automatically sign into a network. In the steps below, we’ll help you set up an account for Phone System with Calling Plans so you can deploy these types of phones for your organization.

## <a name="prerequisites-for-common-area-phones"></a>共用エリア電話の前提条件

まずはじめに、次のことを確認する必要があります。

- 共用エリア電話のライセンスとコールプランを購入してください。
- 承認された電話機を検索して購入してください（リストを表示する [ここに](deploying-skype-for-business-online-phones.md)）。
- Update the firmware on your phones (See supported firmware [in this topic](getting-phones-for-skype-for-business-online.md)).  You can check the firmware on you phone by doing this:
  - **VVX のポリコム電話**:**設定**に移動し > **ステータス** > **プラットフォーム** > **アプリケーション** > **メイン**です。
  - **Yealink 電話**: 電話のメイン画面の**ステータス**に移動します。
  - **電話**: **] メニュー**に移動 > **デバイスの状態** > 開始画面から、**ファームウェアのバージョン**です。
  - **Lync の電話のエディション (LPE) 電話**: **] メニュー**に移動 > 開始画面から**システム情報**です。

    Firmware updates are managed by the Skype for Business Service. Every Skype for Business certified phone's firmware is uploaded to the Skype for Business Update server, and device update is enabled on all phones by default.

    Depending on the inactivity time on the phone and polling intervals, phones will automatically download and install the latest certified builds. You can disable the device update settings by using the  [Set-CsIPPhonePolicy](https://docs.microsoft.com/powershell/module/skype/set-csipphonepolicy) cmdlet and setting the *EnableDeviceUpdate* parameter to `false`.

## <a name="setting-up-a-common-area-phone"></a>共用エリア電話機の設定
以下の手順を実行する必要があります：

### <a name="step-1---buy-the-licenses"></a>手順 1  - ライセンスを購入する
1. Office 365の管理センターでは、 **[請求]** > **[購入サービス]** に移動し、**[その他の計画]** を追加してください。

    ![CAP-license.png](../../images/cap-license.png)
2. **[共用エリア電話機]** > **[今すぐ購入]** をクリックし、**[チェックアウト]** ページで **[今すぐ購入]** をクリックします。
3. Click on to expand **Add-on subscriptions** and then click on to buy a Calling Plan. Choose either the **Domestic Calling Plan** or **Domestic and International Calling Plan**.

> [!Note]
> You don't need a Phone System license. It's included with the **Common Area Phone** license.

ライセンスの詳細については、 [Skype](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)を参照してください。

### <a name="step-2---create-a-new-user-account-for-the-phone-and-assign-the-licenses"></a>手順 2  - 電話機の新しいユーザアカウントを作成し、ライセンスを割り当てます
1. Office 365の管理センターでは、 **[ユーザー]** > **[アクティブユーザー]** > **[ユーザーを追加する]** に移動してください。
2. **ユーザー名** に、最初の名前を "Main"、2番目の名前を"Reception" のように入力します。
3. "Main Reception" のように自動生成しない場合は、**表示名** に入力してください。
4. **[ユーザー名]** に "Main Reception" または"Mainlobby" のように入力します。
5. For common area phones, you might want to set a password manually or have the same password for all of you common area phones. Also, you might think about unselecting **Make this user change their password when they first sign in**.

    > [!Tip]
    > WAIT!! Don't click **Add**!! Ugh, if you did click **Add** the do this: Office 365 admin center > **Users** > **Active users** and then find the user. Then on the user's properties page, click **Product licenses** and then click **Edit**. On the **Product licenses** page, turn on **Common Area Phone** and pick either a **Domestic Calling Plan** or a Domestic and **International Calling Plan**.

6. If you are still there, assign the licenses to this user. On the same page, click to expand **Product licenses**. Turn on the following:
   - 共用エリア電話機
   - そして、 **[国内電話プラン]** または [国内および **国際電話プラン**] のいずれかを選択する必要があります。

     ライセンスの割り当ては次のように表示されます。

     ![TurnOnCapLicense.png](../../images/cap-license-turn-on.png)

     > [!Note]
     > ご存知のように、Skype for Business Plan 2 は、 **共用エリア電話機** のライセンスに含まれています。

詳細については、「[ユーザーを追加する](https://support.office.com/article/1970f7d6-03b5-442f-b385-5880b9c256ec)」を参照してください。

### <a name="step-3---assign-a-phone-number-to-the-common-area-phone-user-account"></a>手順 3  - 共用エリア電話機のユーザー アカウントに電話番号を割り当てる

![sfb-logo-30x30.png](../../images/sfb-logo-30x30.png) 電話番号を割り当てるには、 **Skype for Business 管理センター** を使用してください。

1. Office 365 管理センター >**管理センター** > **ビジネス用の Skype**です。
2. **[Skype for Business 管理センター]** >  **[音声]** > **[電話番号]** に移動します。
3. 電話番号のリストから番号を選択し、** [割り当て]**  をクリックします。
4. **[割り当て]** ページで、**[音声ユーザー]** ボックスに電話機に使用するユーザーの名前を入力し、**[音声ユーザーを選択]** ドロップダウンでユーザーを選択します。
5. While you're there you will need to add an emergency address. Once you search, look under the **Select emergency address** to pick the right one for you.
6. **[保存]** をクリックすると、ユーザーが以下のように表示されます。

    ![cap-user-number.png](../../images/cap-user-number.png)

   > [!Note]
   > Users will only show up if they have a **Phone System** licence applied. If you just did this, then sometimes it takes a bit for the user to show up in the list.

さらなる情報については、 [[ユーザーの電話番号を取得する]](../../what-are-calling-plans-in-office-365/getting-phone-numbers-for-your-users.md) を参照してください。

If you're wondering, you can also take your phone number that you have with another carrier and "*port*" or transfer them over to Office 365. See, [Transfer phone numbers to Office 365](/microsoftteams/transfer-phone-numbers-to-office-365).

### <a name="step-4---setting-up-your-phone"></a>手順 4  - 電話機を設定する

**電話機のモードを設定する**

The phone or phones you have must have the **Common Area Phone mode** turned on. You might want to check on that to make sure they do.

**Polycom VVX 電話を設定する方法の例を次に示します**

- Polycom VVX の共用エリア電話機モードを有効にするには、次の手順を実行します。
    1. ブラウザで、CAP モードを有効にできるように Web インターフェイスに接続します。
    2. 次に **[設定]** に移動し、 **[Skype for Business 設定]** オプションで、**[共用エリア電話]** を選択します。
    3. **[はい]**  をクリックして設定を保存します。

- Now that CAP mode is enabled, set up the phone using the phone's display. The display should show **CaAP is enabled**. Then do the following:

    1. **[設定]** をクリックします。
    2. **詳細設定**を選択します。
    3. パスワードを入力します。
    4. **[管理設定]** で、**[共用エリア電話機の設定]** を選択します。
    5. **[CAP]** および **[CAP管理モード]** を有効にします。
    6. **[設定を保存]** をクリックします。

- さて、電話機の準備ができたので、ホームスクリーンにサインインすることができます。

    1. **[設定]** > **[機能]** > **[Skype for Business]** を選択してサインインします。
    2. **[ユーザーの資格情報]** を選択し、さらに **[ウェブサインイン（CAP）]** を選択してコードを生成します。
    3. [[事前設定ポータル]](https://aka.ms/skypecap) に移動し、**管理者** としてログインします。
    4. 表示名（Main Reception など）を入力します。

       > [!Note]
       > 「**共通エリア電話のみを検索する**」がチェックされている場合は、 チェックボックスをオフにして再度検索します。

    5. ペアリング コード ウィンドウで、電話機に表示されているコードを入力して **[事前設定]** をクリックします。

        この最後の手順の後、電話機は自動的にサインインします。


> [!NOTE]
> The CAP provisioning site states it will reset the CAP account's password to a random password. Take note that the account the CAP is referring is the Azure Active Directory (AAD) account. If you created the account in AAD only then the process is straightforward. If you have synced an on premises Active Directory to AAD make sure to take note of the credentials you are using that will be changed by CAP provisioning.


### <a name="related-topics"></a>関連トピック

- 利用可能な電話の詳細については  「[Skype for Business Online 電話の導入](deploying-skype-for-business-online-phones.md)」をご覧ください。
- [Skype for Business Online を利用できる電話機の取得](getting-phones-for-skype-for-business-online.md)


