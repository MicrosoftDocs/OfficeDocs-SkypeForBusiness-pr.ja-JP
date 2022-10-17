---
title: Microsoft Teams に電話番号を転送する
author: CarolynRowe
ms.author: crowe
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
- highpri
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: 移植ウィザードを使用して、現在のサービス プロバイダーから Microsoft Teams に電話番号を転送する方法について説明します。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 4dd814f81bb7c48c331ebaa1178f8f3069f7b156
ms.sourcegitcommit: cbcf37f395832bed871fe709b87c6eecb1fdfd72
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2022
ms.locfileid: "68584168"
---
# <a name="transfer-phone-numbers-to-microsoft-teams"></a>Microsoft Teams に電話番号を転送する

Microsoft Teams 管理センターの移植ウィザードを使用して、現在のサービス プロバイダーから Teams に電話番号を転送します。 電話番号を Teams に移行した後、Microsoft がサービス プロバイダーになり、それらの電話番号に対する請求を行います。

開始する前に、[ポートの順序](port-order-overview.md)に関する情報を確認することをお勧めします。 ダイヤルイン会議ブリッジ、自動応答、その他のサービス番号、無料電話番号、または Teams に転送する必要がある 999 人を超えるユーザー (サブスクライバー) 電話番号がある場合は、「 [組織の電話番号を管理](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) して正しいフォームをダウンロードして送信する」を参照してください。

  > [!NOTE]
  > 電話番号を転送するポート注文は、祝日や週末ではなく、米国営業日にのみ処理されます。
  > 無料電話番号の移植の可用性は、国と地域によって異なる場合があります。 詳細については、お客様の国または地域固有のドキュメントを参照して、移植サービスのサポートを参照してください。

## <a name="create-a-port-order-and-transfer-your-phone-numbers-to-teams"></a>ポート注文を作成し、Teams に電話番号を転送する

> [!NOTE]
> **現在、このウィザードを使用して、英国、米国、カナダの電話番号を取得できます**。 他の国と地域の電話番号を取得するには、 [ポート注文を手動で送信](manually-submit-port-order.md)できます。 ポート注文を手動で送信する必要があるフォームを取得するには、[ [組織の電話番号の管理](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)] のドロップダウン リストで国または地域を選択します。

1. Microsoft Teams 管理センターの左側のナビゲーションで、**音声** > 電話番号に移動 **します**。 [ **数値**] をクリックし、[ **ポート** ] をクリックして移植ウィザードを開始します。
2. [ **作業の開始** ] ページの情報を確認し、準備ができたら、[ **次へ**] をクリックします。
3. [ **場所と番号の種類の選択]** ページで、次を指定し、[ **次へ**] をクリックします。

    - **国または地域**: 数値を取得する国または地域。
    - **電話番号の種類**: 電話番号の種類 (地理的な電話番号やフリーダイヤル番号など)。
    - **割り当てられている番号**: 数値の割り当て対象。 たとえば、ユーザー、会議、音声機能などです。

4. [ **アカウント情報の追加]** ページで、次の手順に従って [ **次へ**] をクリックします。

    > [!IMPORTANT]
    > このページに表示される情報は、国または地域と番号の種類によって決まります。 ポート番号に必要な情報については、国と地域ごとに異なる規制があります。 このページに表示される内容は、ここで説明したものとは異なる場合があります。

    - **注文の詳細**: 
        - **注文名**: 注文の名前
        - **通知メール**: 注文通知を受け取るアドレスをEmailします。 複数のメール アドレスを入力する場合は、それぞれセミコロンで区切ります。
        - **転送日**: 現在のサービス プロバイダーによって発行された転送日。
    - **電話番号の詳細**
        - **ポートの種類**: すべての番号を転送するフル ポートを実行しているか、一部の番号を転送する部分ポートを実行しているか。
    - **詳細を要求するユーザー**  
        - 転送を要求するユーザーの組織名と連絡先の詳細。
    - **現在のプロバイダーの詳細**
        - **課金電話番号 (BTN)**: E.164 形式の BTN。番号の先頭に + 記号が必要です。 たとえば、北米番号の場合は、+1XXXYYYYZZZZ 形式を使用します。
        - 現在のサービス プロバイダーの名前、アカウント番号、サービス アドレスなど、その他の詳細。
            
5. [ **番号の追加** ] ページ **で、[ファイルの選択**] をクリックし、転送する電話番号を含む CSV ファイルを参照して選択し、[ **次へ**] をクリックします。  

    > [!NOTE]
    > CSV ファイルには、PhoneNumber という名前のヘッダーを含む列が 1 つだけ含まれている必要があります。 各電話番号は個別の行に配置する必要があり、数字のみ、または E.164 形式で指定できます。

6. **[注文の完了**] ページで、[**署名された承認状のアップロード**] をクリックして、署名された承認状 (LOA) のスキャンされたコピーをアップロードします。

    LOA をまだダウンロードして署名していない場合は、次の操作を行います。
    
    1. **[テンプレートのダウンロード]** をクリックして、お使いの国または地域の LOA をダウンロードします。 
    2. LOA を印刷します。
    3. アカウントに変更を加える権限を持つユーザーが LOA に署名します。
    4. 署名された LOA をスキャンし、[ **署名された承認状のアップロード** ] をクリックしてアップロードします。

    > [!NOTE]
    > LOA をアップロードしたら、注文を送信します。 LOA をアップロードするだけでは十分ではありません。 また、処理する注文も送信する必要があります。

7. 注文の詳細を確認し、[送信] をクリック **します**。


## <a name="what-happens-next"></a>この後のステップは？

ポート注文を受け取ると、要求を確認する電子メールが届きます。 要求は毎日チェックされ、更新され、その進行状況と状態が電子メールで通知されます。 ポート要求が失われる通信事業者によって拒否された場合は、 [TNS サービス デスク](../manage-phone-numbers-for-your-organization/contact-tns-service-desk.md)にお問い合わせください。

ポート注文の状態を表示するには、Microsoft Teams 管理センターの左側のナビゲーションで、 **音声** > **ポートの注文**>移動し、[ **注文履歴**] をクリックします。 各ポートの順序の状態が [ **状態]** 列に一覧表示されます。 詳細については、 [ポート注文の状態に関するページを参照してください。](port-order-status.md)


## <a name="reporting-telephone-number-issues"></a>電話番号の問題を報告しますか?
ポートの完了後、最初の 24 時間から 48 時間以内に移植された番号に関する問題が発生した場合は、 [TNS サービス デスク](../manage-phone-numbers-for-your-organization/contact-tns-service-desk.md)にお問い合わせください。 48 時間を超える問題については、Microsoft サポート チームにお問い合わせください。

## <a name="related-topics"></a>関連項目

- [番号移行注文について](port-order-overview.md)
- [通話プランで使用されるさまざまな種類の電話番号](../different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [組織の電話番号を管理する](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)
- [緊急通話の利用条件](../emergency-calling-terms-and-conditions.md)
- [緊急通話の免責事項ラベル](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)
