---
title: 共通エリア電話機を設定する
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: wasseemh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
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
description: 適切なファームウェアを入手し、必要に応じてアップデートし、ライセンスを割り当て、共用エリア電話の設定を構成するための展開手順を学びます。
ms.openlocfilehash: 25605e7538792080213eebb898e612be6ce5bfab
ms.sourcegitcommit: bdf9946b7c65ef7985d6b03a1479ea3a5c17a304
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/23/2018
ms.locfileid: "19426803"
---
# <a name="set-up-common-area-phones"></a>共通エリア電話機を設定する
共用エリア電話機（CAP）は、一般に、ロビーや多くの人々が利用できるエリアに配置されます。 たとえば、受付エリアの電話機、ドアホンまたは会議室の電話機など、CAPは、ユーザーではなくデバイスとして設定され、自動的にネットワークにサインインされます。 以下の手順では、電話システムとコールプランのアカウントを設定して、所属する組織にこれらのタイプの電話機を導入する方法を説明します。

## <a name="prerequisites-for-common-area-phones"></a>共用エリア電話の前提条件

まずはじめに、次のことを確認する必要があります。

 - 共用エリア電話のライセンスとコールプランを購入してください。
 - 承認された電話機を検索して購入してください（リストを表示する [ここに](deploying-skype-for-business-online-phones.md)）。         
 - 電話機のファームウェアを更新します（[ このトピックで](getting-phones-for-skype-for-business-online.md) 、サポートされているファームウェアを参照してください）。  以下のことを行うことで電話機のファームウェアを確認することができます：       
    - **Polycom VVX 電話機**： **[設定]** >  **[ステータス]** > **[プラットフォーム]** > **[アプリケーション]** > **[メイン]** に移動します。
    - **Yealink 電話機**：メインの電話画面で   **[ステータス]** に移動します。
    - **AudioCodes 電話機 **：スタート画面から **[メニュー]** > **[デバイスメニュー]** > **[ファームウェアのバージョン]** に移動します。 
    - **Lync Phone Edition (LPE) 電話機**：スタート画面から **[メニュー]** > **[システム情報]** に移動します。

    ファームウェアのアップデートは、Skype for Business Serviceによって管理されます。 Skype for Business で認証された電話機のファームウェアはすべて Skype for Business Update サーバーにアップロードされ、既定ではすべての電話機でデバイス アップデートが有効になります。 

    電話機の非アクティブ時間とポーリング間隔に応じて、電話機は自動的に最新の認定ビルドをダウンロードしてインストールします。 デバイスのアップデート設定を無効にするには、 [Set-CsIPPhonePolicy](https://docs.microsoft.com/powershell/module/skype/set-csipphonepolicy) コマンドレットを使用し、 *EnableDeviceUpdate* パラメータを `false` に設定します。

## <a name="setting-up-a-common-area-phone"></a>共用エリア電話機の設定
以下の手順を実行する必要があります：

### <a name="step-1---buy-the-licenses"></a>手順 1  - ライセンスを購入する
1. Office 365の管理センターでは、 **[請求]** > **[購入サービス]** に移動し、**[その他の計画]** を追加してください。

    ![CAP-license.png](../../images/cap-license.png)
2. **[共用エリア電話機]** > **[今すぐ購入]** をクリックし、**[チェックアウト]** ページで **[今すぐ購入]** をクリックします。
3. クリックして **[アドオン購読]** を拡大し、さらにクリックしてコールプランを購入します。 **[国内コールプラン]** または **[国際コールプラン]** のいずれかを選択します。

> [!Note]
> 電話システムのライセンスは必要ありません。 ** 共用エリア電話機 ** のライセンスに含まれています。

ライセンスの詳細については、「[Skype for Business とMicrosoft Teams アドオン ライセンス](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md) 」を参照してください。

### <a name="step-2---create-a-new-user-account-for-the-phone-and-assign-the-licenses"></a>手順 2  - 電話機の新しいユーザアカウントを作成し、ライセンスを割り当てます
1. Office 365の管理センターでは、 **[ユーザー]** > **[アクティブユーザー]** > **[ユーザーを追加する]** に移動してください。
2. **ユーザー名** に、最初の名前を "Main"、2番目の名前を"Reception" のように入力します。
3. "Main Reception" のように自動生成しない場合は、**表示名** に入力してください。
4. **[ユーザー名]** に "Main Reception" または"Mainlobby" のように入力します。
5. 共用エリア電話機では、パスワードを手動で設定するか、すべての共用エリア電話機に対して同じパスワードを設定した方がよい場合があります。 また、 **このユーザーが最初にログインしたときにパスワードを変更する** を選択しないという方法も考えられます。

    > [!Tip]
    > お待ちください！！ **[追加]** をクリックしないでください！！ クリックしてしまったら、 **[追加]** をクリックして次のことを行ってください：[Office 365管理センター] > **[ユーザー]** > **[アクティブユーザー]** でユーザーを見つけてください。 次に、ユーザーのプロパティ ページで、**[製品ライセンス]** をクリックし、さらに **[編集]** をクリックしてください。 **[製品ライセンス]** ページで、**[共用エリア電話]** をオンにして、**[国内コールプラン]** または[国内および **国外コールプラン**] のいずれかを選択してください。

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

1. [Office 365 管理センター] で、**[管理センター]**  > **[Skype for Business]** に移動します。
2. **[Skype for Business 管理センター]** >  **[音声]** > **[電話番号]** に移動します。
3. 電話番号のリストから番号を選択し、** [割り当て]**  をクリックします。
4. **[割り当て]** ページで、**[音声ユーザー]** ボックスに電話機に使用するユーザーの名前を入力し、**[音声ユーザーを選択]** ドロップダウンでユーザーを選択します。 
5. この作業の間に、緊急アドレスを追加する必要があります。 一度検索すると、 **[緊急アドレスを選択]** を参照して自分に合うものを選択します。
6. **[保存]** をクリックすると、ユーザーが以下のように表示されます。

    ![cap-user-number.png](../../images/cap-user-number.png)

   > [!Note]
   > **電話システム** ライセンスが適用さている場合のみ、ユーザーが表示されます。 この操作を実行したばかりだと、ユーザーがリストに表示されるまでに時間がかかることがあります。

さらなる情報については、 [[ユーザーの電話番号を取得する]](../../what-are-calling-plans-in-office-365/getting-phone-numbers-for-your-users.md) を参照してください。

迷っている場合は、別のキャリアや "*ポート* " で持っている電話番号を使用するか、それらをOffice 365 へ移行することもできます。 「[ Office 365 に電話番号を移行する](../../what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365.md) 」を参照してくさい。

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
    2. **[詳細設定]** を選択します 。
    3. パスワードを入力します。
    4. **[管理設定]** で、**[共用エリア電話機の設定]** を選択します。
    5. **[CAP]** および **[CAP管理モード]** を有効にします。
    6. **[設定を保存]** をクリックします。

- さて、電話機の準備ができたので、ホームスクリーンにサインインすることができます。

    1. **[設定]** > **[機能]** > **[Skype for Business]** を選択してサインインします。
    2. **[ユーザーの資格情報]** を選択し、さらに **[ウェブサインイン（CAP）]** を選択してコードを生成します。
    3.  [[事前設定ポータル]](http://aka.ms/skypecap) に移動し、**管理者** としてログインします。
    4. 表示名（Main Reception など）を入力します。

       > [!Note]
       > 「**共通エリア電話のみを検索する**」がチェックされている場合は、 チェックボックスをオフにして再度検索します。

    5. ペアリング コード ウィンドウで、電話機に表示されているコードを入力して **[事前設定]** をクリックします。

        この最後の手順の後、電話機は自動的にサインインします。

### <a name="related-topics"></a>関連トピック

- 利用可能な電話の詳細については  「[Skype for Business Online 電話の導入](deploying-skype-for-business-online-phones.md)」をご覧ください。
- [Skype for Business Online で使う電話を入手する](getting-phones-for-skype-for-business-online.md)


