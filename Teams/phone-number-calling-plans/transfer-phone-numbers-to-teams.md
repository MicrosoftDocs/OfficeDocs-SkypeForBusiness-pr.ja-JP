---
title: Microsoft Teams に電話番号を転送する
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
description: 移植ウィザードを使用して、現在のサービス プロバイダーから Microsoft Teams に電話番号を転送する方法について説明します。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: dfc3141eea8d16a86c0f37221e597feac3bb957e
ms.sourcegitcommit: 6f7b91f573e2a034f8c5474be2c5cb2971f4b5ab
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2021
ms.locfileid: "50421282"
---
# <a name="transfer-phone-numbers-to-microsoft-teams"></a>Microsoft Teams に電話番号を転送する

Microsoft Teams 管理センターの移植ウィザードを使用して、現在のサービス プロバイダーから Teams に電話番号を転送します。 電話番号を Teams に移行した後、Microsoft がサービス プロバイダーになり、それらの電話番号に対する請求を行います。

開始する前に、番号番号注文の情報 [を確認することをお勧めします。](port-order-overview.md) ダイヤルイン会議ブリッジ、自動応答、その他のサービス番号、無料電話番号、または Teams に転送する必要がある 999 を超えるユーザー (サブスクライバー) 電話番号がある場合は、「組織の電話番号を[](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)管理して正しいフォームをダウンロードして送信する」を参照してください。

  > [!NOTE]
  > 電話番号の移行注文は、米国の営業日にのみ処理され、祝日や週末には処理できません。

## <a name="create-a-port-order-and-transfer-your-phone-numbers-to-teams"></a>ポート注文を作成し、電話番号を Teams に転送する

> [!NOTE]
> **現在、このウィザードを使用** して、英国、米国、およびカナダの電話番号を取得できます。 他の国や地域の電話番号を取得するには、ポート [注文を手動で送信します](manually-submit-port-order.md)。 ポート注文を手動で送信する必要があるフォームを取得するには、[組織の電話番号の管理] のドロップダウン リストで国または地域 [を選択します](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)。

1. Microsoft Teams 管理センターの左側のナビゲーションで、[音声電話番号]**に**  >  **移動します**。 [ **番号] を** クリックし、[ポート **] をクリック** して移植ウィザードを開始します。
2. [開始] ページの情報 **を** 確認し、準備ができたら 、[次へ] をクリック **します**。
3. [場所 **と数値の種類の選択] ページで** 、次を指定し、[次へ] を **クリックします**。

    - **国または地域**: 番号を取得している国または地域。
    - **電話番号の種類**: 地理的な電話番号やフリーダイヤル番号などの番号の種類です。
    - **割り当てられている数値**: 番号が割り当てられているもの。 たとえば、ユーザー、会議、音声機能などです。

4. [アカウント情報 **の追加] ページ** で、次の手順を実行し、[次へ] をクリック **します**。

    > [!IMPORTANT]
    > このページに表示される情報は、国または地域と番号の種類によって決まります。 国と地域ごとに、番号を移植するために必要な情報に関する規制が異なります。 このページに表示される情報は、ここで説明する情報とは異なる場合があります。

    - **ご注文の詳細**: 
        - **ご注文** 名: ご注文の名前
        - **通知メール**: 注文通知を受信するメール アドレス。 複数のメール アドレスを入力する場合は、セミコロンで区切ります。
        - **移行日**: 現在のサービス プロバイダーから発行された移行日。
    - **電話番号の詳細**
        - **ポートの** 種類: すべての番号を転送するためにフル ポートを実行しているか、一部の番号を転送する部分的なポートを実行しているか。
    - **詳細を要求するユーザー**  
        - 転送を要求するユーザーの組織名と連絡先の詳細。
    - **現在のプロバイダーの詳細**
        - **請求先電話番号 (BTN):** E.164 形式の BTN で、番号の先頭に + 記号が必要です。 たとえば、北米の数値の場合は、+1XXXYYYZZZZ 形式を使用します。
        - 現在のサービス プロバイダーの名前、アカウント番号、サービス アドレスなどのその他の詳細。
            
5. [番号 **の追加]** ページで、[ファイルの選択] をクリックし、転送する電話番号を含む CSV ファイルを参照して選択し、[次へ] をクリック **します**。  

    > [!NOTE]
    > CSV ファイルには、PhoneNumber という名前のヘッダーを含む 1 つの列のみを含む必要があります。 各電話番号は別々の行に入る必要があります。数字のみ、または E.164 形式を使用できます。

6. [注文 **の完了] ページ** で、[署名された承認状のアップロード] をクリックして、署名された承認状 (LOA) のスキャンしたコピーをアップロードします。

    LOA をまだダウンロードして署名していない場合は、次の操作を行います。
    
    1. [ **テンプレートのダウンロード] を** クリックして、お客様の国または地域の LOA をダウンロードします。 
    2. LOA を印刷します。
    3. アカウントを変更する権限を持つユーザーが LOA に署名します。
    4. 署名された LOA をスキャンし、[署名済み承認状のアップロード] をクリック **して** アップロードします。

    > [!NOTE]
    > LOA をアップロードした後、注文を送信します。 LOA をアップロードするだけで十分ではありません。 また、注文を処理するために送信する必要があります。

7. 注文の詳細を確認し、[送信] を **クリックします**。


## <a name="what-happens-next"></a>この後のステップは？

ポート注文を受け取った場合は、リクエストを確認するメールが届きます。 リクエストは毎日チェックおよび更新され、その進捗状況と状態がメールで通知されます。 通信事業者がポート要求を拒否した場合は、PSTN サービス デスク [にお問い合わせください](../manage-phone-numbers-for-your-organization/contact-pstn-service-desk.md)。

ポート注文の状態を表示するには、Microsoft Teams 管理センターの左側のナビゲーションで、[>**音声** ポート注文] に移動し、[注文履歴] を  >  **クリックします**。 各ポート注文の状態が [状態] 列に **一覧表示** されます。 詳細については、「ポート注文の [状態について」を参照してください。](port-order-status.md)

## <a name="related-topics"></a>関連トピック

- [番号移行注文について](port-order-overview.md)
- [通話プランで使用されるさまざまな種類の電話番号](../different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [組織の電話番号を管理する](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)
- [緊急通話の利用条件](../emergency-calling-terms-and-conditions.md)
- [緊急通話の免責事項ラベル](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)
