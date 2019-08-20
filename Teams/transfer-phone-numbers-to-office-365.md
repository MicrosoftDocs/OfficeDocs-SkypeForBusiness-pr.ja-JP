---
title: Office 365 に電話番号を転送する
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: 47b3af8e-4171-4dec-8333-c956f108664e
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords:
- ms.lync.lac.PortingNumbersOverview
ms.custom:
- Calling Plans
- LIL_Placement
description: 電話番号を Teams に移行する前に知っておく必要があることと、それを転送するためのポートの順序を作成する方法について説明します。
ms.openlocfilehash: 4cd270fd01f0ec023181de7847914d8fdc8239b5
ms.sourcegitcommit: b914c044c43ff8147f35eea684fec1de01a7bcd2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/19/2019
ms.locfileid: "36464570"
---
# <a name="transfer-phone-numbers-to-office-365"></a>Office 365 に電話番号を転送する

現在のサービスプロバイダーから Microsoft Teams に電話番号を転送するのは簡単です。 お客さまの電話番号を Teams に移植すると、Microsoft はサービスプロバイダになり、これらの電話番号について請求されます。
  
電話番号の移行を開始する前に、「[電話番号の一般的な質問](transferring-phone-numbers-common-questions.md)」の情報を確認することをお勧めします。 ダイヤルイン会議ブリッジのサービス番号、自動応答、またはその他のサービス番号、有料電話番号、または Teams に移行する必要がある999ユーザー (サブスクライバー) 電話番号がある場合は、「[の電話番号を管理する」を参照してください。[組織](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)] は、適切なフォームをダウンロードして、それを microsoft に送信します。

  > [!NOTE]
  > お客様は、電話番号を米国の就業日にのみ転送するためのポート注文を処理します。これは、休日または週末ではありません。
  
## <a name="how-to-create-a-port-order-and-transfer-your-phone-numbers-to-teams"></a>ポート注文を作成して、電話番号を Teams に転送する方法
<a name="bk_LNPcountries_1"> </a>

  > [!NOTE]
  > ダイヤルイン会議ブリッジのサービス番号、自動応答、または他のサービス番号がある場合、または、無料の電話番号を使用している場合、または Teams への移行が必要な電話番号が999ではない場合は、「自分の電話番号を管理する」を参照してください。 [[組織](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)] 適切な国または地域を選択し、適切なフォームをダウンロードして、それを microsoft に送信します。
 
![](media/sfb-logo-30x30.png) **Skype for business 管理センターを使用し**た skype for business ロゴを示すアイコン

1. **Microsoft Teams 管理センター** > の**従来のポータル**に移動します。

2. In the left navigation go to **Voice** > **Port orders** > click **Add**.

3. [ **新しい電話番号のポート注文**] ページで、情報を読んで確認してから、[ **作業を開始する**] をクリックします。

4. [ **アカウント情報**] ページで以下の情報を入力し、[ **次へ**] をクリックします。

   - [ **アカウント番号**] サービス プロバイダーまたは電話会社のアカウント番号。

   - [ **請求先電話番号**] は E.164 形式である必要があります (番号の先頭に + 記号が必要です)。たとえば、北アメリカの電話番号には +1XXXYYYZZZZ の形式を使用します。

   - [ **番号をブロック解除する PIN**] - 現在のサービス プロバイダーまたは電話会社で必要な場合の PIN。

   - [ **会社名**] 会社または組織の名前。

     > [!NOTE]
     > [ **会社名**] ボックスに入力できるのは、スペースを含めて 25 文字までです。会社の名前が 25 文字より長い場合は、名前の最初の 25 文字が送信され、番号移行注文が処理されます。
  
   - [ **認証する人物**] 認証されたユーザーの名前。

     > [!NOTE]
     > [ **認証する人物**] ボックスに入力できるのは、スペースを含めて 15 文字以下です。認証する人物の名前が 15 文字より長い場合は、名前の最初の 15 文字が発行され、番号移行注文が処理されます。
  
   - [ **サービス アドレス**] アカウントのサービス アドレス。これは、サービス プロバイダーまたは電話会社からの請求書に記載されます。

   - サービス アドレスの [ **市区町村**]、[ **都道府県**]、[ **郵便番号**]。

6. [ **番号**] ページで、移行する電話番号を E.164 形式で入力します。 たとえば、北アメリカの電話番号には +1XXXYYYZZZZ の形式を使用します。 複数の電話番号を区切るには、カンマを使用します。

    > [!NOTE]
    > 完全な移行を行う場合は、リストにサービスの請求先電話番号 (BTN) を含める必要があります。部分的な移行を行う場合は、リストからサービスの請求先電話番号 (BTN) を除外します。 
  
    完全な移行を行う場合は、[ **現在の電話会社からすべての番号を転送する**] を選びます。部分的な移行を行う場合は、[ **一部の番号のみを転送する**] を選びます。適切な選択を行った後、[ **番号を移行できるかを確認**] をクリックします。

7. [ **続行**] をクリックします。

8. [**転送日**] ページの [**日**] ドロップダウンリストで日付を選び、[**開始時刻**] ドロップダウンリストで時刻 (EST) を選び、[**次へ**] をクリックします。

9. [ **承認状**] ページで、各ボックスをオンにします。続いて [ **署名**] ボックスの下で、アカウントを変更することが承認されているユーザーを入力します。これは、[ **アカウント情報**] ページの [ **認証する人物**] で使う同じ名前です。続いて [ **次へ**] をクリックします。

10. [ **送信**] ページの [ **その他の通知対象ユーザー**] に必要なユーザーの電子メール アドレスを入力し、[ **移行注文の送信**] をクリックします。移行注文は、[ **移行注文**] ページに一覧表示されます。[ **状態**] 列の下で状態をい表示できます。[ **注文 ID**]、[ **送信済み**]、[ **移行日**] および [ **状態**] などの移行注文の詳細を表示できます。操作ペインで携帯電話会社名などのさらに詳しい情報を表示できます。

## <a name="what-happens-next"></a>この後のステップは？
<a name="bk_LNPcountries_1"> </a>

ポート注文を送信し、受信されると、ポート注文を確認する電子メールを受け取ります。 
  
Your port order request will be checked and updated daily and you will be notified of its progress and status in email. If your request is rejected, you will be asked to open a support ticket and in that support ticket we ask that you provide **Port Order ID**. The port order ID can be found in the Skype for Business admin center under **Voice** > **Port orders** > **Order ID** column.
  
## <a name="what-if-i-have-problems"></a>問題が発生した場合
<a name="bk_LNPcountries_1"> </a>

 **サービス アドレスが請求先住所と違っている。注文時に送信した住所情報が、顧客の請求書のコピーと一致するのに拒否されることがあります。** ほとんどの携帯電話会社は、請求先住所ではなくサービス アドレスの情報に基づいて移行情報を特定します。請求書のコピーは請求の記録であるため、移行する電話番号のサービス アドレスと同じ情報が提供されない可能性があります。
  
 **注文の処理に時間がかかりすぎる場合はどうすればよいですか?** 番号の移行は、非常に単純で簡単なプロセスとして使います。 Skype for Business 管理センターで注文の状態が [完了] になっていないと思われる場合は、サポートチケットを開いて、ポート注文 ID を含めてください。

   
## <a name="related-topics"></a>関連トピック
[電話番号の移行に関するよくある質問](transferring-phone-numbers-common-questions.md)

[通話プランで使用されるさまざまな種類の電話番号](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[緊急通話の利用条件](emergency-calling-terms-and-conditions.md)

[緊急通話の免責事項ラベル](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

  
 
