---
title: 電話番号のアクティブ化に失敗する理由
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: c4e54d00-e096-474c-a457-56e785439ff6
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
f1keywords:
- ms.lync.lac.NumberActivationStateFailed
ms.custom:
- Calling Plans
description: 住所検証は、Office 365 の通話プランのセットアップで重要な部分です。 これにより、組織のユーザーに対して、緊急応答サービスで使用できる緊急通話の住所が提供されます。
ms.openlocfilehash: 1748211718b1e25a6f5bfcdcd512e0e2d7d2c587
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "23864811"
---
# <a name="why-has-number-activation-failed"></a>電話番号のアクティブ化に失敗する理由
住所検証は、Office 365 の通話プランのセットアップで重要な部分です。 場合は何らかの理由により、電話番号はアドレスの検証のためにアクティブには、サービス リクエストを作成する必要があります。 これをどのように行うかは、所属する組織のサイズに基づきます。
  
## <a name="for-organizations-150-or-less-follow-these-steps"></a>150 ユーザー以下の組織の場合は、次の手順を実行します。
1. [**Office 365 管理センター**] で、[**ヘルプが必要ですか?**] を選択します。
2. [**ヘルプが必要ですか?**] ペインで、どのようなヘルプが必要かを伝えて、[**問い合わせ**] を選択します。
3. [**解決策を表示**] セクションの結果が役に立たない場合は、次のいずれかを選択します。
    - [**電話連絡を許可 (推奨)**]: 連絡先番号を確認して、[**折り返し連絡**] を押します。 折り返し連絡されるまでの待ち時間の予測が [**ヘルプが必要ですか?**] ペインに示されます。
    - [**電子メールを送信**]: メールアドレスを確認して、[**送信**] を選択します。 通話の応答時間が [**ヘルプが必要ですか?**] ペインに示されます。

## <a name="for-organizations-with-more-than-150-users-create-a-service-request-to-validate-an-emergency-address"></a>150 ユーザーを超える組織では、緊急住所の検証をするためにサービス リクエストを作成します。

1. 職場または学校のアカウントを使用して、Office 365 に管理者としてサインインします。
    
2. Office 365 管理センターの左側のナビゲーションで、[**サポート**] > [**新しいサービス リクエスト**] をクリックします。
    
3. [**サービス リクエスト**] で、[**追加**] をクリックします。
    
4. [**サービス リクエストの作成**] ページで、[**オンライン グループ作業**] をクリックします。
    
5. [**問題の特定**] ページで、次の項目を選んで、必要事項を入力します。
    
  - **機能:** **国内通話プラン**および/または**国内および国際通話プラン**を選択します。
    
  - **現象:** **緊急通話**と入力します。
    
  - **案件の概要:** **住所検証**と入力します。
    
  - **案件詳細:** 検証する必要がある住所について、次のような詳細情報を入力します。
    
      - 番地
    
      - 町名
    
      - 市区町村
    
      - 国または地域
    
    > [!IMPORTANT]
    > **電話番号を割り当てるときに検証しようとしている緊急住所がある、Office 365 の通話プランが提供されている国/地域を入力します。**
  
      - 郵便番号
    
6. [**次へ**] ページをクリックし、[**はい、処理を続行します**] をクリックして続行します。
    
7. [**詳細の追加**] ページで、次の項目を選んで、必要事項を入力します。
    
  - [**サービスが利用できませんか?**]:  [**いいえ**] を選択します。
    
  - [**影響を受けているユーザーの数**]:  [**一部のユーザー**] を選択します。
    
  - [**この問題の影響を受けるユーザーのメール アドレスの入力**] を入力するか、空白のままにします。
    
  - [**一覧表示するドメインを選択する**]
    
  - 複数の住所を検証する必要がある場合は、**ファイルを添付します**。
    
  - [**次へ**] をクリックします。
    
  - 連絡先の電話番号を入力します。
    
8. 情報を確認して、[**リクエストの送信**] をクリックします。
    
> [!TIP]
> Office 365 管理センターの [**サービス リクエスト**] ページに、参照番号が表示されます。

> [!NOTE]
> 無料電話番号

  
## <a name="related-topics"></a>関連トピック
[電話番号の移行に関するよくある質問](/microsoftteams/transferring-phone-numbers-common-questions)

[通話プランで使用されるさまざまな種類の電話番号](/microsoftteams/different-kinds-of-phone-numbers-used-for-calling-plans)

[緊急通話の利用条件](/microsoftteams/emergency-calling-terms-and-conditions)

[Skype for Business Online: 緊急通話の免責事項ラベル](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)
  
 