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
ms.openlocfilehash: dd296bcf987016cf77af538edcb2e04328ab525b
ms.sourcegitcommit: fd56fb16ed60b027d3f8de96711d143825f9c184
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/20/2023
ms.locfileid: "69835480"
---
# <a name="transfer-phone-numbers-to-microsoft-teams"></a>Microsoft Teams に電話番号を転送する

Microsoft Teams 管理センターの移植ウィザードを使用して、現在のサービス プロバイダーから Teams に電話番号を転送します。 電話番号を Teams に移行した後、Microsoft がサービス プロバイダーになり、それらの電話番号に対する請求を行います。

開始する前に、「[ポート注文とは」](port-order-overview.md)の情報を確認することをお勧めします。 ダイヤルイン会議ブリッジ、自動応答、またはその他のサービス番号、フリーダイヤル電話番号、または Teams に転送する必要がある 999 を超えるユーザー (サブスクライバー) 電話番号がある場合は、「 [組織の電話番号を管理](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) して正しいフォームをダウンロードして Microsoft に送信する」を参照してください。

  > [!NOTE]
  > 私たちは、祝日や週末ではなく、米国営業日にのみ電話番号を転送するためのポート注文を処理します。
  >
  > 無料電話番号の移植の可否は、国と地域によって異なる場合があります。 詳細については、お住まいの国または地域固有のドキュメントを参照して、移植サービスの利用可能なサポートを参照してください。

## <a name="create-a-port-order-and-transfer-your-phone-numbers-to-teams"></a>ポート注文を作成し、電話番号を Teams に転送する

1. Microsoft Teams 管理センターの左側のナビゲーションで、[**音声** > 電話番号] に移動 **します**。 [ **数値**] を選択し、[ **ポート** ] を選択して移植ウィザードを開始します。
2. [ **作業の開始** ] ページで情報を確認し、準備ができたら [ **次へ**] を選択します。
3. [ **場所と番号の種類の選択]** ページで、次のように指定し、[ **次へ**] を選択します。

    - **国または地域**: 番号を取得している国または地域。
    - **電話番号の種類**: 地理的な番号やフリーダイヤル番号などの番号の種類。
    - **割り当てられた番号**: 番号の割り当て先。 たとえば、ユーザー、会議、音声機能などです。

4. [ **アカウント情報の追加]** ページで、次の手順を完了し、[ **次へ**] を選択します。

    > [!IMPORTANT]
    > このページに表示される情報は、国または地域と番号の種類によって決まります。 国と地域ごとに、ポート番号に必要な情報に関するさまざまな規制があります。 このページに表示される内容は、ここで説明されているものとは異なる場合があります。

    - **注文の詳細**: 
        - **注文名: 注文** の名前
        - **通知メール**: 注文通知を受信するアドレスをEmailします。 複数のメール アドレスを入力する場合は、それぞれをセミコロンで区切ります。
        - **転送日**: 現在のサービス プロバイダーによって発行された転送日。
    - **電話番号の詳細**
        - **ポートの種類**: すべての番号を転送するためにフル ポートを実行しているか、一部の番号を転送する部分ポートを実行しているか。
    - **詳細を要求するユーザー**  
        - 転送を要求するユーザーの組織名と連絡先の詳細。
    - **現在のプロバイダーの詳細**
        - **課金電話番号 (BTN)**: E.164 形式の BTN。番号の先頭に + 記号が必要です。 たとえば、北米番号の場合は、+1XXXYYYZZZZ 形式を使用します。
        - 現在のサービス プロバイダーの名前、アカウント番号、サービス アドレスなど、その他の詳細。
            
5. [ **番号の追加** ] ページ **で、[ファイルの選択**] を選択し、転送する電話番号を含む CSV ファイルを参照して選択し、[ **次へ**] を選択します。  

    > [!NOTE]
    > CSV ファイルには **、PhoneNumber** という名前のヘッダーを持つ列が 1 つだけ必要です。 各電話番号は別々の行に配置する必要があり、数字のみ、または E.164 形式で指定できます。

6. [ **注文の完了** ] ページで、[ **署名された承認状のアップロード** ] を選択して、署名された承認状 (LOA) のスキャンされたコピーをアップロードします。

    LOA をまだダウンロードして署名していない場合は、次の操作を行います。
    
    1. [ **テンプレートのダウンロード] を** 選択して、国または地域の LOA をダウンロードします。 
    2. LOA を印刷します。
    3. アカウントに変更を加える権限を持つユーザーが LOA に署名させます。
    4. 署名された LOA をスキャンし、[ **署名された承認状のアップロード** ] を選択してアップロードします。

    > [!NOTE]
    > LOA をアップロードしたら、注文を送信します。 LOA をアップロードするだけでは十分ではありません。 また、処理のために注文を送信する必要があります。
    >
    > 既存の電話番号を移植/転送するための LOA と追加のドキュメント要件の詳細については、「 [通話プランの電話番号を管理する](/microsoftteams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization)」を参照してください。
    >
    > 999 を超える電話番号を移植または転送する場合、または Microsoft Teams 管理センターで移植プロセスに問題が発生した場合は、お使いのリージョンの TNS Service Desk [に手動でポート注文を送信](/microsoftteams/phone-number-calling-plans/manually-submit-port-order) できます。

7. 注文の詳細を確認し、[送信] を選択 **します**。

## <a name="what-happens-next"></a>この後のステップは？

ポート注文を受け取ると、要求を確認するメールが届きます。 要求が毎日チェックされ、更新され、その進行状況と状態が電子メールで通知されます。 お客様のポート要求が運送業者によって拒否された場合は、 [TNS サービス デスク](../manage-phone-numbers-for-your-organization/contact-tns-service-desk.md) にお問い合わせください。

ポート注文の状態を表示するには、Microsoft Teams 管理センターの左側のナビゲーションで、[  **音声** > **ポートの注文**] に移動し、[ **注文履歴**] を選択します。 各ポート注文の状態が [ **状態]** 列に一覧表示されます。 詳細については、[ポート注文の状態に関するページを参照してください](port-order-status.md)。


## <a name="reporting-telephone-number-issues"></a>電話番号に関する問題の報告

ポートが完了してから最初の 24 から 48 時間以内に移植された番号に問題が発生した場合は、 [TNS Service Desk](../manage-phone-numbers-for-your-organization/contact-tns-service-desk.md) にお問い合わせください。 48 時間を超える問題については、Microsoft サポート チームにお問い合わせください。

## <a name="related-articles"></a>関連記事

- [番号移行注文について](port-order-overview.md)
- [通話プランで使用されるさまざまな種類の電話番号](../different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [組織の電話番号を管理する](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)
- [緊急通話の利用条件](../emergency-calling-terms-and-conditions.md)
- [緊急通話の免責事項ラベル](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)
