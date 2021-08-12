---
title: 番号のアクティブ化に失敗した理由
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
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
f1.keywords:
- CSH
ms.custom:
- Calling Plans
- ms.lync.lac.NumberActivationStateFailed
description: アドレスの検証は、通話プランを設定する上で重要な部分です。 これにより、組織のユーザーに対して、緊急応答サービスで使用できる緊急通話の住所が提供されます。
ms.openlocfilehash: b1f9f8269028d81e7819972472bb7efb8054fc671fe1cf08e3f643f668449498
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54312275"
---
# <a name="why-has-number-activation-failed"></a>番号のアクティブ化に失敗した理由

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]?
アドレスの検証は、通話プランを設定する上で重要な部分です。 何らかの理由で住所の検証のために電話番号がアクティブ化されていない場合は、サービス要求を作成する必要があります。 これをどのように行うかは、所属する組織のサイズに基づきます。
  
## <a name="for-organizations-150-or-less-follow-these-steps"></a>150 ユーザー以下の組織の場合は、次の手順を実行します。
1. 管理センターで、[ヘルプが必要 **ですか**?
2. [**ヘルプが必要ですか?**] ペインで、どのようなヘルプが必要かを伝えて、[**問い合わせ**] を選択します。
3. [**解決策を表示**] セクションの結果が役に立たない場合は、次のいずれかを選択します。
    - [**電話連絡を許可 (推奨)**]: 連絡先番号を確認して、[**折り返し連絡**] を押します。 折り返し連絡されるまでの待ち時間の予測が [**ヘルプが必要ですか?**] ペインに示されます。
    - [**電子メールを送信**]: メールアドレスを確認して、[**送信**] を選択します。 通話の応答時間が [**ヘルプが必要ですか?**] ペインに示されます。

## <a name="for-organizations-with-more-than-150-users-create-a-service-request-to-validate-an-emergency-address"></a>150 ユーザーを超える組織では、緊急住所の検証をするためにサービス リクエストを作成します。

1. 管理者としてサインインし、Microsoft 365またはOffice 365アカウントを使用してログインします。
    
2. 管理センターの左側のナビゲーションで、[新しいサービス要求のサポート  >  **] をクリックします**。
    
3. [**サービス リクエスト**] で、[**追加**] をクリックします。
    
4. [**サービス リクエストの作成**] ページで、[**オンライン グループ作業**] をクリックします。
    
5. [**問題の特定**] ページで、次の項目を選んで、必要事項を入力します。
    
   - **機能:** **国内通話プラン** および/または **国内および国際通話プラン** を選択します。
    
   - **現象:** **緊急通話** と入力します。
    
   - **案件の概要:** **住所検証** と入力します。
    
   - **案件詳細:** 検証する必要がある住所について、次のような詳細情報を入力します。
    
      - 番地
    
      - 町名
    
      - 市区町村
    
      - 国または地域
    
     > [!IMPORTANT]
     > **電話番号を割り当てるときに緊急対応の住所を検証しようとしている通話プランを提供する国/地域を指定します。**
  
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
> 参照番号は、次のページの **[サービス要求**] ページにMicrosoft 365 管理センター。

> [!NOTE]
> さらに追加で電話番号が必要な場合は、「[一般法人向け Office 365 のサポートへのお問い合わせ - 管理者向けヘルプ](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)」をご覧ください。

  
## <a name="related-topics"></a>関連トピック
[電話番号の移行に関するよくある質問](/microsoftteams/transferring-phone-numbers-common-questions)

[通話プランで使用されるさまざまな種類の電話番号](/microsoftteams/different-kinds-of-phone-numbers-used-for-calling-plans)

[緊急通話の利用条件](/microsoftteams/emergency-calling-terms-and-conditions)

[Skype for Business Online: 緊急通話の免責事項ラベル](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)
  
 
