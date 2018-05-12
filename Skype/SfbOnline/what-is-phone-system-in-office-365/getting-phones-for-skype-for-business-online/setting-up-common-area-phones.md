---
title: 共通領域電話を設定します。
description: 適切なファームウェアを取得し、更新が必要な場合、ライセンスを割り当てる共通領域電話の設定を構成、展開の手順を説明します。
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
- Strat_SB_PSTN
ms.openlocfilehash: b7e3a20bc08af0900a64ceacc817bdeaffd5f326
ms.sourcegitcommit: febd51fd7988602a8c9839e4e9872ae8f5d77c63
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2018
---
# <a name="set-up-common-area-phones"></a>共通領域電話を設定します。

共通領域電話、または、CAP 共有領域では通常、配置は、個々 のユーザーに関連付けられていません。 例では、受信エリアの電話番号、ドアの電話や会議室電話、Cap は、ユーザーではなくデバイスとして設定して、ネットワークに自動的にサインインします。 以下の手順でお手伝いプランを呼び出すことでマイクロソフトの電話システムのアカウントを設定し、CAP を展開し、します。

## <a name="prerequisites-for-common-area-phones"></a>共通領域電話のための前提条件

次があることを確認します。

-   - 共通領域電話の SKU を購入しました。 
-   - 更新されたファームウェア (ここではサポートされているファームウェアを参照してください。https://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online)
-   - 電話を承認 (の一覧を表示します。            
        https://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/deploying-skype-for-business-online-phones)

## <a name="check-the-firmware-for-your-phone"></a>自分の携帯電話のファームウェアを確認します。
- **Polycom VVX phones**, go to **Settings** > **Status** > **Platform** > **Application** > **Main**.
- **Yealink 電話機** の場合は、メインの電話画面で [ **Status (情報)** ] に移動します。
- **AudioCodes phones**, go to **Menu** > **Device Status** > **Firmware version** from the start screen. 
- **Lync Phone Edition (LPE) phones**, go to **Menu** > **System Information** from the start screen.

ファームウェアの更新プログラムは、ビジネス サービス、Skype で管理されます。 ビジネスのすべての Skype は、ビジネスの更新のサーバーでは、Skype を携帯電話のファームウェアをアップロードし、デバイスの更新プログラムが既定で有効にすべての電話で認定します。 

電話とポーリング間隔の待ち時間によって、電話が自動的にダウンロードして認定された最新のビルドがインストールされます。 [セット CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx)コマンドレットを使用して、 _EnableDeviceUpdate_パラメーターを設定してデバイスの更新の設定を無効にすることができます`false`。

## <a name="create-cap"></a>キャップを作成します。
CAP を作成するには、物理的な電話を設定する前に設定を構成します。

#### <a name="purchase-the-common-area-phone-sku"></a>共通領域電話の SKU を購入します。 
    In the Office 365 admin center, go to **Billing > Purchase Services**, and add **Common Area Phone**.

#### <a name="set-up-the-common-area-phone-----this-section-could-use-a-screen-shot--"></a>共通領域電話を設定します。<!-- this section could use a screen shot-->

**ユーザーを作成します。** 
1. 共通領域電話の SKU を割り当てる
2. (マイクロソフトの電話システムを使用して、計画を呼び出すことで) 場合は、計画を呼び出すことを割り当てます。 
3. ビジネス管理センターでは、Skype で利用可能な電話番号を割り当てますか、新しい電話番号を要求します。

**新しいユーザーを作成します。**

1. プロビジョニングのウィンドウでは、最初と最後の名前 (たとえば、受信のメイン) を入力するオプションがあります。
2. 表示名を入力 (必須)、「メイン受信」などです。
3. ユーザー名を入力 (必須)、たとえば"MainReception"@"ドメイン"(会社名や企業名)
4. (国) の場所を入力します。

**共通領域電話の SKU を割り当てる**Office 365 管理センターに移動**請求 > 購買サービス****共通領域電話**の追加

**CAP の SKU での通話プランを割り当てる**

1. 携帯電話を有効にする計画を呼び出すことを選択します。 
2. ビジネス オンライン計画 2 キャップ SKU での電話システムと Skype を有効にするキャップを追加します。 <!-- odd order for step -->

**電話番号を割り当てる**
1. [使用可能な電話番号を確認**音声 > 電話番号**です。
2. 電話番号の番号の一覧から番号を選択します。
3. **音声**と**電話番号**を選択して選択内容を確認します。

    >[!NOTE]
    音声ユーザーは、適用した後でも更新するのには時間がかかることができますが適用されると、電話システムのライセンスがあるかどうかのみ表示されます。 センターは、ビジネス管理者のいずれかの時点 Skype を再び開くことができます。
    
## <a name="configure-phone"></a>電話を構成します。

**物理的な電話を準備します。**

選択された電話は、共通領域電話モードである必要があります。 

***VVX のポリコム電話の例***

次の手順で、ポリコム VVX の共通領域電話のモードを有効にします。
1. お使いのブラウザーで web インターフェイスを使用、VVX のキャップのモードを有効にするには
2. **設定**にし、ビジネスの設定オプションの Skype で、**共通領域電話**を選択します。
3. **[はい]** の構成設定を保存する] をクリックします。

キャップ電話モードを有効にすると、これでは、携帯電話のディスプレイを使用して電話を設定します。 「CaAP が有効な"表示が表示されます。

1. [**設定**] をクリックします。
2. **詳細設定**を選択します。
3. パスワードを入力します。
4. 管理の設定では、**共通領域電話の設定**を選択します。
5. **キャップ**と**キャップの管理モード**を有効にします。
6. **設定を保存**] をクリックします。

自分の携帯電話は、次のようなホーム画面にサインインするときの操作を準備する準備ができました。

1. **設定**を選択してサインイン > **機能** > **ビジネス用の Skype** 。
2. **ユーザーの資格情報**を選択し選択**web サインイン (CAP)** コードを生成する.
3. プロビジョニングのポータルに移動http://aka.ms/skypecap、し、**管理者**としてサインインします。
4. キャップを表示するのには (たとえば、メインの受信) の表示名を入力します。

>[!NOTE]
場合 [共通領域電話でのみの検索] がチェック ボックスをオフにして再度検索をオンになっている。

5. ペアリング コード ウィンドウで、携帯電話に表示されるコードを入力し、[**準備**] をクリックします。

この最後のステップでは、次の電話は自動的にサインインします。

[オンライン ビジネス電話の Skype の展開](https://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/deploying-skype-for-business-online-phones)で使用可能な電話の詳細について説明します。


