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
ms.openlocfilehash: b92cef4234823c53faf6193d2e9e90fe3e5b60f0
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32231157"
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
6. [追加] をクリックしていない場合は、このユーザーにライセンスを割り当てます。 同じページで、**[製品ライセンス]** をクリックして拡大してください。 次の機能をオンにします。
   - 共用エリア電話機
   - そして、 **[国内電話プラン]** または [国内および **国際電話プラン**] のいずれかを選択する必要があります。

     ライセンスの割り当ては次のように表示されます。

     ![TurnOnCapLicense.png](../../images/cap-license-turn-on.png)

     > [!Note]
     > ご存知のように、Skype for Business Plan 2 は、 **共用エリア電話機** のライセンスに含まれています。

詳細については、「[ユーザーを追加する](https://support.office.com/article/1970f7d6-03b5-442f-b385-5880b9c256ec)」を参照してください。

### <a name="step-3---assign-a-phone-number-to-the-common-area-phone-user-account"></a>手順 3  - 共用エリア電話機のユーザー アカウントに電話番号を割り当てる

![sfb-logo-30x30.png](../../images/sfb-logo-30x30.png) 電話番号を割り当てるには、 **Skype for Business 管理センター** を使用してください。

1. Office 365 の管理センター _gt**管理センター**内 > **ビジネス用の Skype**です。
2. **[Skype for Business 管理センター]** >  **[音声]** > **[電話番号]** に移動します。
3. 電話番号のリストから番号を選択し、** [割り当て]**  をクリックします。
4. **[割り当て]** ページで、**[音声ユーザー]** ボックスに電話機に使用するユーザーの名前を入力し、**[音声ユーザーを選択]** ドロップダウンでユーザーを選択します。
5. この作業の間に、緊急アドレスを追加する必要があります。 一度検索すると、 **[緊急アドレスを選択]** を参照して自分に合うものを選択します。
6. **[保存]** をクリックすると、ユーザーが以下のように表示されます。

    ![cap-user-number.png](../../images/cap-user-number.png)

   > [!Note]
   > **電話システム** ライセンスが適用さている場合のみ、ユーザーが表示されます。 この操作を実行したばかりだと、ユーザーがリストに表示されるまでに時間がかかることがあります。

さらなる情報については、 [[ユーザーの電話番号を取得する]](../../what-are-calling-plans-in-office-365/getting-phone-numbers-for-your-users.md) を参照してください。

迷っている場合は、別のキャリアや "*ポート* " で持っている電話番号を使用するか、それらをOffice 365 へ移行することもできます。 参照してください、 [Office 365 に電話番号を転送](/microsoftteams/transfer-phone-numbers-to-office-365)します。

### <a name="step-4---setting-up-your-phone"></a>手順 4  - 電話機を設定する

**電話機のモードを設定する**

電話機の**共用エリア電話機モード** をオンになっている必要があります。 オンになっているかどうか確認した方がよいかもしれません。

**Polycom VVX 電話を設定する方法の例を次に示します**

- Polycom VVX の共用エリア電話機モードを有効にするには、次の手順を実行します。
    1. ブラウザで、CAP モードを有効にできるように Web インターフェイスに接続します。
    2. 次に **[設定]** に移動し、 **[Skype for Business 設定]** オプションで、**[共用エリア電話]** を選択します。
    3. **[はい]**  をクリックして設定を保存します。

- 以上で CAP モードが有効になったので、電話機のディスプレイを使用して電話機を設定します。 ディスプレイに「 **CaAPが有効です**」と表示されます。 次に、以下を実行してください。

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
> CAP 事前設定サイトには、CAP アカウントのパスワードがランダムなパスワードにリセットされると記載されています。 CAP が参照しているアカウントが Azure Active Directory（AAD）アカウントであることに注意してください。 AAD でアカウントを作成した場合は、そのプロセスは簡単です。 設置型 AAD に Active Directory を同期して、サード ・ パーティ製の IDP または ad FS を使用して、CAP のプロビジョニングは失敗します。 この例では、する必要があります Office 365 と Azure Active Directory アカウントのみ (たとえば、 **onmicrosoft.com**ドメインでのアカウント) を使用するキャップが作業する準備をします。


### <a name="related-topics"></a>関連トピック

- 利用可能な電話の詳細については  「[Skype for Business Online 電話の導入](deploying-skype-for-business-online-phones.md)」をご覧ください。
- [Skype for Business Online を利用できる電話機の取得](getting-phones-for-skype-for-business-online.md)


