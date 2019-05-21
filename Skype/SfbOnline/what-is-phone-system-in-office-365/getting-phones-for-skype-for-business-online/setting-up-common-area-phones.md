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
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: 適切なファームウェアを取得し、必要に応じて更新し、ライセンスを割り当て、一般的な市外電話の設定を構成するための展開手順について説明します。
ms.openlocfilehash: 59b681fecfe4fe6c2b9d89c7dbea875f30152340
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34297990"
---
# <a name="set-up-common-area-phones"></a>共通エリア電話機を設定する
共用エリア電話機（CAP）は、一般に、ロビーや多くの人々が利用できるエリアに配置されます。 たとえば、受付エリアの電話機、ドアホンまたは会議室の電話機など、CAPは、ユーザーではなくデバイスとして設定され、自動的にネットワークにサインインされます。 以下の手順では、電話システムとコールプランのアカウントを設定して、所属する組織にこれらのタイプの電話機を導入する方法を説明します。

## <a name="prerequisites-for-common-area-phones"></a>共用エリア電話の前提条件

まずはじめに、次のことを確認する必要があります。

- 共用エリア電話のライセンスとコールプランを購入してください。
- 承認された電話機を検索して購入してください（リストを表示する [ここに](deploying-skype-for-business-online-phones.md)）。
- 電話機のファームウェアを更新します（[ このトピックで](getting-phones-for-skype-for-business-online.md) 、サポートされているファームウェアを参照してください）。  以下のことを行うことで電話機のファームウェアを確認することができます：
  - **Polycom vvx 電話**:**設定** > **状態** > **プラットフォーム** > **アプリケーション** > の**メイン**に移動します。
  - **携帯**電話: メインの電話画面で [**ステータス**] に移動します。
  - **Audiocodes 電話**: スタート画面から**メニュー** > **デバイス状態** > の**ファームウェアバージョン**に移動します。
  - **Lync Phone Edition (lpe) 電話**: スタート画面から**メニュー** > **システム情報**に移動します。

    ファームウェアのアップデートは、Skype for Business Serviceによって管理されます。 Skype for Business で認証された電話機のファームウェアはすべて Skype for Business Update サーバーにアップロードされ、既定ではすべての電話機でデバイス アップデートが有効になります。

    電話機の非アクティブ時間とポーリング間隔に応じて、電話機は自動的に最新の認定ビルドをダウンロードしてインストールします。 デバイスのアップデート設定を無効にするには、 [Set-CsIPPhonePolicy](https://docs.microsoft.com/powershell/module/skype/set-csipphonepolicy) コマンドレットを使用し、 *EnableDeviceUpdate* パラメータを `false` に設定します。

## <a name="setting-up-a-common-area-phone"></a>共用エリア電話機の設定
以下の手順を実行する必要があります：

### <a name="step-1---buy-the-licenses"></a>手順 1  - ライセンスを購入する
1. Office 365の管理センターでは、 **[請求]** > **[購入サービス]** に移動し、**[その他の計画]** を追加してください。

    ![CAP-license.png](../../images/cap-license.png)
2. **[共用エリア電話機]** > **[今すぐ購入]** をクリックし、**[チェックアウト]** ページで **[今すぐ購入]** をクリックします。
3. クリックして **[アドオン購読]** を拡大し、さらにクリックしてコールプランを購入します。 **国内通話プラン**または**国内および国際通話プラン**のいずれかを選択します。

> [!Note]
> 電話システムのライセンスは必要ありません。 ** 共用エリア電話機 ** のライセンスに含まれています。

ライセンスの詳細については、「 [Skype For business および Microsoft Teams のアドオンライセンス](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)」を参照してください。

### <a name="step-2---create-a-new-user-account-for-the-phone-and-assign-the-licenses"></a>手順 2  - 電話機の新しいユーザアカウントを作成し、ライセンスを割り当てます
1. Office 365の管理センターでは、 **[ユーザー]** > **[アクティブユーザー]** > **[ユーザーを追加する]** に移動してください。
2. **ユーザー名** に、最初の名前を "Main"、2番目の名前を"Reception" のように入力します。
3. "Main Reception" のように自動生成しない場合は、**表示名** に入力してください。
4. **[ユーザー名]** に "Main Reception" または"Mainlobby" のように入力します。
5. 共用エリア電話機では、パスワードを手動で設定するか、すべての共用エリア電話機に対して同じパスワードを設定した方がよい場合があります。 また、 **このユーザーが最初にログインしたときにパスワードを変更する** を選択しないという方法も考えられます。
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

1. Office 365 管理センターで、>**管理センター** > **Skype for business**を管理します。
2. **[Skype for Business 管理センター]** >  **[音声]** > **[電話番号]** に移動します。
3. 電話番号のリストから番号を選択し、** [割り当て]**  をクリックします。
4. **[割り当て]** ページで、**[音声ユーザー]** ボックスに電話機に使用するユーザーの名前を入力し、**[音声ユーザーを選択]** ドロップダウンでユーザーを選択します。
5. この作業の間に、緊急アドレスを追加する必要があります。 一度検索すると、 **[緊急アドレスを選択]** を参照して自分に合うものを選択します。
6. **[保存]** をクリックすると、ユーザーが以下のように表示されます。

    ![cap-user-number.png](../../images/cap-user-number.png)

   > [!Note]
   > **電話システム** ライセンスが適用さている場合のみ、ユーザーが表示されます。 この操作を実行したばかりだと、ユーザーがリストに表示されるまでに時間がかかることがあります。

さらなる情報については、 [[ユーザーの電話番号を取得する]](/microsoftteams/getting-phone-numbers-for-your-users) を参照してください。

迷っている場合は、別のキャリアや "*ポート* " で持っている電話番号を使用するか、それらをOffice 365 へ移行することもできます。 「 [Office 365 に電話番号を転送する](/microsoftteams/transfer-phone-numbers-to-office-365)」を参照してください。

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
    2. [**詳細設定**] を選びます。
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
> CAP 事前設定サイトには、CAP アカウントのパスワードがランダムなパスワードにリセットされると記載されています。 CAP が参照しているアカウントが Azure Active Directory（AAD）アカウントであることに注意してください。 AAD でアカウントを作成した場合は、そのプロセスは簡単です。 オンプレミスの Active Directory を AAD と同期していて、サードパーティの IDP または ADFS を使用している場合、CAP プロビジョニングは失敗します。 この場合は、CAP provisioning を機能させるために、Office 365/Azure Active Directory アカウントのみ (たとえば、 **onmicrosoft.com**ドメインのアカウント) を使用する必要があります。


### <a name="related-topics"></a>関連トピック

- 利用可能な電話の詳細については  「[Skype for Business Online 電話の導入](deploying-skype-for-business-online-phones.md)」をご覧ください。
- [Skype for Business Online を利用できる電話機の取得](getting-phones-for-skype-for-business-online.md)


