---
title: 共有エリア電話のセットアップ
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
description: 共有エリア電話について、適切なファームウェアを入手し、必要に応じて更新し、ライセンスを割り当て、設定を行うための導入手順を学びます。
ms.openlocfilehash: bcf7d8eaf287af0b801168c62e7c22915f735aa2
ms.sourcegitcommit: 265fbdc1a8ac566751e707874656bd6b90de980d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/16/2018
ms.locfileid: "19170538"
---
# <a name="set-up-common-area-phones"></a>共有エリア電話のセットアップ
共有エリア電話機（CAP）は一般に、多くの人々が利用できるロビーなどの領域に置かれます。 たとえば、受付の電話機、ドアホン（インターホン）または会議室の電話機、CAP は、ユーザーではなくデバイスとしてセットアップされ、自動的にネットワークにサインインされます。 以下の手順では、これらのタイプの電話機をユーザーが組織に導入できるように、通話プラン付きの電話システムのアカウントを設定する方法を説明します。

## <a name="prerequisites-for-common-area-phones"></a>共有エリア電話の必須条件

まず、以下の事柄を行ったことを確認する必要があります。

 - 共有エリア電話のライセンスと通話プランを購入します。
 - 承認済みの電話機を検索して購入します（[こちら](deploying-skype-for-business-online-phones.md) で一覧を表示してください）。         
 - 電話機のファームウェアを更新します（[このトピックで](getting-phones-for-skype-for-business-online.md) サポートされているファームウェアをご覧ください。  お手持ちの電話機のファームウェアは次のように確認できます。       
    - **Polycom VVX の電話機** の場合は、[ **設定** > ][**状態** > ][**プラットフォーム** > ][**アプリケーション** > ][**メイン**] に移動します。
    - **Yealink の電話機**の場合は、メイン電話画面で [ **状態（情報）** ] に移動します。
    - **AudioCodes の電話機** の場合は、スタート画面から [**メニュー** > ][**デバイス状態** > ][**ファームウェア バージョン** ] に移動します。 
    - **Lync Phone Edition (LPE) の電話機** の場合は、スタート画面から [**メニュー** > ][**システム情報** ] に移動します。

    ファームウェアの更新は、Skype for Business のサービスによって管理されます。 Skype for Business のすべての認定電話機のファームウェアは、Skype for Business の更新サーバーにアップロードされており、既定ではすべての電話機についてデバイス更新が有効となっています。 

    電話機の非アクティブ時間とポーリング間隔に応じて、電話機は最新の認定ビルドを自動的にダウンロードしてインストールします。 デバイスの更新設定を無効にするには、 [Set-CsIPPhonePolicy](https://docs.microsoft.com/powershell/module/skype/set-csipphonepolicy) コマンドレットを使用して、 *EnableDeviceUpdate* パラメータを `false` に設定します。

## <a name="setting-up-a-common-area-phone"></a>共有エリア電話のセットアップ
以下の手順を実行する必要があります。

### <a name="set-up-your-user-account-for-the-phone"></a>電話機のユーザー アカウントをセットアップします。

#### <a name="step-1---buy-the-licenses"></a>ステップ 1  - ライセンスを購入します
1. Office 365 管理センターで、[ **請求書** > ][**購入サービス**] に移動し、**その他のプラン** を追加します。

    ![CAP-license.png](../../images/cap-license.png)
2. [ **共有エリア電話** >  ][**今購入する** ] をクリックします。> [ **チェックアウト** ] ページで [**今購入する** ] をクリックします。
3. [ **アドオン購読** ] をクリックして展開し、さらにクリックして通話プランを購入します。 [**国内通話プラン** ] または [ **国内および国際通話プラン** ] のいずれかを選択します。

> [!Note]
> 電話システムのライセンスは必要ありません。 それは **共通エリア電話** のライセンスに含まれています。

ライセンスの詳細については、「[Skype for Business および Microsoft Teams のアドオンのライセンス](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)」をご覧ください。

#### <a name="step-2---create-a-new-user-account-for-the-phone-and-assign-the-licenses"></a>ステップ 2  - 電話の新しいユーザー アカウントを作成してライセンスを割り当てます
1. Office 365 管理センターで、[**ユーザー** > ][**アクティブ ユーザー** > ][**ユーザーを追加** ] に移動します。
2. 最初の名前に「Main」のような **ユーザー名** を入力し、2番目の名前に「Reception」を入力します。
3. 「Main Reception」のような名前を自動生成しない場合は、**表示名** を入力します。
4. 「MainReception」や「Mainlobby」のような **ユーザー名** を入力します。
5. 共有エリア電話機については、パスワードを手動で設定するか、すべての共通エリア電話機に対して同じパスワードを設定すると便利な場合があります。 また、**このユーザーが最初にサインインしたときにパスワードを変更する** の選択を解除すると良い場合もあります。

    > [!Tip]
    > 待って!! [**追加**] をクリックしないでください!! おっと、[ **追加** ] をクリックしてしまったら、こうしてください： Office 365 管理センターで > [ **ユーザー** >  ][**アクティブ ユーザー** ] を選択して、ユーザーを見つけます。 次に、ユーザーのプロパティ ページで、[**製品ライセンス** ] をクリックして、[ **編集** ] をクリックします。 [**製品ライセンス** ] ページで [ **共通エリア電話** ] をオンにして、[ **国内通話プラン** ] または [国内および **国際通話プラン** ] のいずれかを選びます。

6. まだそこにいる場合は、このユーザーにライセンスを割り当てます。 同じページで [**製品ライセンス**] をクリックして展開します。 次の機能をオンにします:
    - 共有エリア電話
    - 次に、[**国内通話プラン** ] または [国内および **国際通話プラン** ] のいずれかを選ぶ必要があります。
     
    ライセンスの割り当ては次のようになります。

    ![TurnOnCapLicense.png](../../images/cap-license-turn-on.png)

    > [!Note]
    > ご存知のように、Skype for Business のプラン 2 は、 **共有エリア電話** のライセンスに含まれています。

詳細については、「[ユーザーを追加](https://support.office.com/article/1970f7d6-03b5-442f-b385-5880b9c256ec) 」をご覧ください。

#### <a name="step-3---assign-a-phone-number-to-the-user"></a>ステップ 3  - ユーザーに電話番号を割り当てます
![sfb-logo-30x30.png](../../images/sfb-logo-30x30.png) **Skype for Business の管理センターを使用する**
1. Office 365 管理センターで、[**管理センター**]  >  [**Skype for Business**] に移動します。
2. [**Skype for Business 管理センター** >  ][**音声** > ][**電話番号**] で、
3. 電話番号のリストから番号を選択し、[**割り当てる** ] をクリックします。
4. [ **割り当てる** ] ページの [ **音声ユーザー** ] ボックスに、電話機に用いるユーザーの名前を入力し、[ **音声ユーザーを選択する** ] コンボボックスからユーザーを選択します。 
5. そこにいる間に、緊急アドレスを追加する必要があります。 一度検索したら、[ **緊急アドレスを選択** ] の下から適切なものを選びます。
6. [ **保存** ] をクリックすると、あなたのユーザーは次のようになります。

    ![cap-user-number.png](../../images/cap-user-number.png)

   > [!Note]
   > ユーザーは **電話システム** ライセンスが適用されたときにのみ表示されます。 これを行ったばかりのときは、ユーザーがリストに表示されるまでに時間がかかる場合があります。

より詳しくは、 「[ユーザーの電話番号を取得する](../../what-are-calling-plans-in-office-365/getting-phone-numbers-for-your-users.md) 」をご覧ください。

不思議に思う場合は、別の通信事業者に使用しているあなたの電話番号を、Office 365 に*移植*または移行することができます。 「[Office 365 に電話番号を移行する](../../what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365.md) 」をご覧ください。

## <a name="step-4---setting-up-your-phone"></a>ステップ 4  - 電話機をセットアップします

**電話機のモードの設定**

使用する電話機で、共通エリア電話モードをオンにする必要があります。 オンになっていることを確認したい場合もあるかもしれません。 

**Polycom VVX の電話機をセットアップする方法の例を次に示します。**

- Polycom VVX の共有エリア電話モードを有効にするには、次の手順に従います。
    1. ブラウザで、CAP モードを有効にできるように Web インターフェイスに接続します。
    2. 次に [**設定**] へ移動し、[**Skype for Business の設定**] オプションで [**共有エリア電話**] を選択します。
    3. [ **はい** ] をクリックして設定を保存します。

- CAP モードが有効になりましたので、電話機のディスプレイを使用して電話機をセットアップします。 ディスプレイには「**CAP が有効になってます** 」と表示されるはずです。 その後以下を実行します。

    1. [**設定**] をクリックします。
    2. [**詳細設定** ] を選択します。
    3. パスワードを入力します。
    4. [**管理設定**] で [**共有エリア電話の設定**] を選択します。
    5. [**CAP** ] と [ **CAP 管理者モード** ] を有効にします。
    6. [**設定を保存** ] をクリックします。

- さて、電話機の準備が整いましたので、ホーム画面でサインインすることができます。

    1. [**設定** > ][**機能** > ][**Skype for Business**] を選択してサインインします。
    2. [ **ユーザー資格情報**] を選択した後 [ **Web サインイン（CAP）** ] を選択してコードを生成します。
    3. [[プロビジョニング ポータル](http://aka.ms/skypecap)] へ行き、[**管理者**] としてサインインします。
    4. 表示名（「Main Reception」など）を入力します。

       > [!Note]
       >  **共有エリア電話のみを検索する** チェックボックスにチェックが入っていた場合は、クリアして再び検索します。

    5. ペアリング コード ウィンドウで、電話機に表示されているコードを入力して [**対応** ] をクリックします。

        この最後の手順の後、電話機は自動的にサインインされます。

### <a name="related-topics"></a>関連するトピック

- 使用可能な電話機の詳細については、「[Skype for Business Online の電話機の導入](deploying-skype-for-business-online-phones.md)」ををご覧ください。
- [Skype for Business Online で使う電話を入手する](getting-phones-for-skype-for-business-online.md)


