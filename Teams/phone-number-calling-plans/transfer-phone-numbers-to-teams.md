---
title: 電話番号を別の電話番号にMicrosoft Teams
author: cichur
ms.author: v-cichur
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
description: 移植ウィザードを使用して、現在のサービス プロバイダーから現在のサービス プロバイダーに電話番号を転送する方法Microsoft Teams。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: dfc3141eea8d16a86c0f37221e597feac3bb957e
ms.sourcegitcommit: 6f7b91f573e2a034f8c5474be2c5cb2971f4b5ab
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2021
ms.locfileid: "50421282"
---
# <a name="transfer-phone-numbers-to-microsoft-teams"></a>電話番号を別の電話番号にMicrosoft Teams

Microsoft Teams 管理センターの移植ウィザードを使用して、現在のサービス プロバイダーから現在のサービス プロバイダーに電話番号をTeams。 電話番号を Teams に移行した後、Microsoft がサービス プロバイダーになり、それらの電話番号に対する請求を行います。

開始する前に、「ポート注文とは」 [の情報を確認することをお勧めします。](port-order-overview.md) ダイヤルイン会議ブリッジ、自動応答、その他のサービス番号、無料電話番号、または Teams に転送する必要がある 999 を超えるユーザー (サブスクライバー) 電話番号のサービス番号がある場合は、「組織の電話番号[](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)を管理する」を参照して、正しいフォームをダウンロードして送信してください。

  > [!NOTE]
  > 米国の営業日にのみ電話番号を転送する場合は、祝日や週末ではなく、移行注文を処理します。

## <a name="create-a-port-order-and-transfer-your-phone-numbers-to-teams"></a>ポート注文を作成し、電話番号を電話番号に転送Teams

> [!NOTE]
> **現時点では、このウィザードを使用して**、英国、米国、およびカナダの電話番号を取得できます。 他の国や地域の電話番号を取得するには、ポート注文 [を手動で送信します](manually-submit-port-order.md)。 ポート注文を手動で送信する必要があるフォームを取得するには、[組織の電話番号の管理] のドロップダウン リストで国または地域 [を選択します](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)。

1. 管理センターの左側のナビゲーションMicrosoft Teams、[Voice 電話  >  **に移動します**。 [ **数値]** をクリックし、[ **ポート] をクリック** して移植ウィザードを開始します。
2. [開始] ページの情報 **を確認** し、準備ができたら [次へ] をクリック **します**。
3. [場所 **と番号の種類の選択] ページで** 、次を指定し、[次へ] を **クリックします**。

    - **国または地域**: 数値を取得する国または地域。
    - **電話の種類**: 地理的な番号やフリーダイヤル番号などの番号の種類。
    - **[割り当てられた数値**]: 数値の割り当て方法。 たとえば、ユーザー、会議、音声機能などです。

4. [アカウント **情報の追加] ページ** で、次の手順を実行し、[次へ] を **クリックします**。

    > [!IMPORTANT]
    > このページに表示される情報は、国または地域と番号の種類によって決まります。 番号を移植するために必要な情報に関する規制は、国と地域によって異なります。 このページに表示される情報は、ここで説明されているのとは異なる場合があります。

    - **注文の詳細**: 
        - **注文名**: ご注文の名前
        - **通知メール**: 注文通知を受信するメール アドレス。 複数のメール アドレスを入力する場合は、それぞれをセミコロンで区切ります。
        - **譲渡日**: 現在のサービス プロバイダーによって発行された譲渡日。
    - **電話番号の詳細**
        - **ポートの** 種類: すべての番号を転送するために完全なポートを実行するか、一部の番号を転送する部分的なポートを実行するか。
    - **詳細を要求するユーザー**  
        - 譲渡を要求するユーザーの組織名と連絡先の詳細。
    - **現在のプロバイダーの詳細**
        - **請求先電話番号 (BTN): BTN** は E.164 形式で、番号の前に + 記号が必要です。 たとえば、北米の数値の場合は、+1XXXYYYZZZZ 形式を使用します。
        - その他の詳細 (現在のサービス プロバイダーの名前、アカウント番号、サービス アドレスなど)。
            
5. [番号 **の追加**] ページで、[ファイルの選択] をクリックし、転送する電話番号を含む CSV ファイルを参照して選択し、[次へ] をクリック **します**。  

    > [!NOTE]
    > CSV ファイルには、PhoneNumber という名前のヘッダーを含む 1 つの列のみを含む必要があります。 各電話番号は個別の行に入る必要があります。数字のみ、または E.164 形式で指定できます。

6. [**注文の完了**] ページで **、[署名アップロード** をクリックして、署名された承認状 (LOA) のスキャンコピーをアップロードします。

    LOA をまだダウンロードして署名していない場合は、次の操作を行います。
    
    1. [ **テンプレートのダウンロード] を** クリックして、お客様の国または地域の LOA をダウンロードします。 
    2. LOA を印刷します。
    3. アカウントを変更する権限を持つユーザーが LOA に署名します。
    4. 署名された LOA をスキャンし、署名アップロード **をクリックして** アップロードします。

    > [!NOTE]
    > LOA をアップロードした後、注文を送信します。 LOA をアップロードするだけで十分ではありません。 また、処理する注文を送信する必要があります。

7. ご注文の詳細を確認し、[送信] を **クリックします**。


## <a name="what-happens-next"></a>この後のステップは？

お客様のポート注文を受信すると、要求を確認する電子メールが届きます。 要求は毎日チェックおよび更新され、その進行状況と状態がメールで通知されます。 ポート要求が失った通信事業者によって拒否された場合は、PSTN サービス デスクにお [問い合わせください](../manage-phone-numbers-for-your-organization/contact-pstn-service-desk.md)。

ポート注文の状態を表示するには、Microsoft Teams 管理センターの左側のナビゲーションで、[>**音声** ポート注文] に移動し、[注文履歴]  >  **をクリックします**。 各ポート注文の状態は、[状態] 列に **一覧表示** されます。 詳細については、「ポート注文の [状態は何ですか?」を参照してください。](port-order-status.md)

## <a name="related-topics"></a>関連トピック

- [番号移行注文について](port-order-overview.md)
- [通話プランで使用されるさまざまな種類の電話番号](../different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [組織の電話番号を管理する](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)
- [緊急通話の利用条件](../emergency-calling-terms-and-conditions.md)
- [緊急通話の免責事項ラベル](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)
