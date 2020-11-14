---
title: Microsoft Teams に電話番号を転送する
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: tonysmit
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
- m365initiative-voice
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: 移植ウィザードを使用して、現在のサービスプロバイダーから Microsoft Teams に電話番号を移行する方法について説明します。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 2a70f6b1cec2658cb2348d21895bfc3b30717d75
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/13/2020
ms.locfileid: "49030763"
---
# <a name="transfer-phone-numbers-to-microsoft-teams"></a>Microsoft Teams に電話番号を転送する

[!INCLUDE [preview-feature](../includes/preview-feature.md)]

Microsoft Teams 管理センターの [移植] ウィザードを使用して、現在のサービスプロバイダーからチームに電話番号を移行します。 電話番号を Teams に移行した後、Microsoft がサービス プロバイダーになり、それらの電話番号に対する請求を行います。

始める前に、「[ポート注文とは](port-order-overview.md)」の情報を確認することをお勧めします。 ダイヤルイン会議ブリッジのサービス番号、自動応答、またはその他のサービス番号、有料電話番号、またはチームに移行する必要がある999ユーザー (サブスクライバー) 電話番号がある場合は、「 [組織の電話](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) 番号を管理して、適切なフォームをダウンロードして送信する」を参照してください。

  > [!NOTE]
  > お客様は、電話番号の転送先として米国営業日のみを処理します。

## <a name="create-a-port-order-and-transfer-your-phone-numbers-to-teams"></a>ポート注文を作成して、電話番号を Teams に転送する

> [!NOTE]
> **現時点では、このウィザードを使って英国、米国、およびカナダの電話番号を取得することができ** ます。 他の国や地域の電話番号を取得するには、 [手動でポート注文を送信](manually-submit-port-order.md)することができます。 フォームを取得するには、手動でポート注文を送信する必要があります。 [ [組織の電話番号の管理](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)] のドロップダウンリストで、お住まいの国または地域を選択します。

1. Microsoft Teams 管理センターの左のナビゲーションで、[電話番号 **] に移動**  >  **Phone numbers** します。 [ **番号** ] をクリックし、[ **ポート** ] をクリックして、移植ウィザードを開始します。
2. [ **はじめ** に] ページで情報を確認し、準備ができたら、[ **次へ** ] をクリックします。
3. [ **場所と番号の種類の選択** ] ページで、次を指定し、[ **次へ** ] をクリックします。

    - **国または地域** : 電話番号を取得している国または地域。
    - [ **電話番号の種類** ]: 市外局番または無料電話番号などの番号の種類。
    - **割り当てられ** ている番号: 番号が割り当てられます。 たとえば、ユーザー、会議、音声機能などです。

4. [ **アカウント情報の追加** ] ページで、次の手順を実行し、[ **次へ** ] をクリックします。

    > [!IMPORTANT]
    > このページに表示される情報は、国または地域と番号の種類によって決まります。 各国と地域には、番号の入力に必要な情報に関するさまざまな規則があります。 このページに表示される内容は、ここで説明する内容と異なる場合があります。

    - **ご注文の詳細** : 
        - **注文名** : ご注文の名前
        - **通知メール** : 注文の通知を受け取るための電子メールアドレス。 複数のメールアドレスを入力する場合は、セミコロンで区切ります。
        - **移行日** : 現在のサービスプロバイダーによって発行された振替日付です。
    - **電話番号の詳細**
        - **ポートの種類** : すべての番号を転送する場合はフル・ポートを使用しているか、一部の番号を転送する場合は部分的なポートを使用します。
    - **詳細をリクエストしている人**  
        - 組織名と、転送を要求したユーザーの詳細。
    - **現在のプロバイダーの詳細**
        - **請求先電話番号 (BTN)** : BTN は、番号の先頭に + 記号が必要です。 たとえば、北アメリカの番号の場合は、+ 1XXXYYYZZZZ 形式を使用します。
        - 現在のサービスプロバイダの名前、アカウント番号、お客さまのサービスの住所などのその他の情報。
            
5. [ **番号の追加** ] ページで、[ **ファイルの選択** ] をクリックし、転送する電話番号を含む CSV ファイルを参照して選び、[ **次へ** ] をクリックします。  

    > [!NOTE]
    > CSV ファイルには、PhoneNumber という名前のヘッダーを持つ1つの列のみが含まれている必要があります。 各電話番号は、個別の行に指定する必要があります。また、数字のみまたは E.i 形式で指定する必要があります。

6. [ **注文が完了** しました] ページで、[署名された **承認状のアップロード** ] をクリックし、スキャンした署名済みレター (loa) をアップロードします。

    LOA をダウンロードして署名していない場合は、次の操作を行います。
    
    1. 「 **テンプレートをダウンロード** 」をクリックして、お住まいの国または地域の loa をダウンロードします。 
    2. LOA を印刷します。
    3. アカウントを変更する権限を持つユーザーによって署名されていることを確認します。
    4. 署名済みの LOA をスキャンし、[署名され **た承認状をアップロード** ] をクリックしてアップロードします。

    > [!NOTE]
    > LOA をアップロードしたら、注文を送信します。 LOA をアップロードしても十分ではありません。 また、処理される注文を送信する必要があります。

7. 注文の詳細を確認して、[ **送信** ] をクリックします。


## <a name="what-happens-next"></a>この後のステップは？

ポート注文が届くと、お客様のリクエストを確認するメールが届きます。 リクエストが毎日チェックされて更新され、メールの進捗状況と状態が通知されます。 紛失しているキャリアでポート要求が拒否された場合は、 [PSTN サービスデスク](../manage-phone-numbers-for-your-organization/contact-pstn-service-desk.md)に問い合わせてください。

ポート注文の状態を表示するには、Microsoft Teams 管理センターの左のナビゲーションで > [ **音声** ポートの注文] に移動し、  >  **Port orders** [ **注文履歴** ] をクリックします。 各ポート注文の状態は、[ **状態** 」列に表示されます。 詳細については、「[ポート注文の状態は何ですか?](port-order-status.md) 」を参照してください。

## <a name="related-topics"></a>関連項目

- [番号移行注文について](port-order-overview.md)
- [通話プランで使用されるさまざまな種類の電話番号](../different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [組織の電話番号を管理する](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)
- [緊急通話の利用条件](../emergency-calling-terms-and-conditions.md)
- [緊急通話の免責事項ラベル](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)
