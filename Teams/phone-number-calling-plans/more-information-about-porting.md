---
title: 移植に関する詳細情報
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: tonysmit,jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
ROBOTS: NOINDEX, NOFOLLOW
f1.keywords:
- CSH
ms.custom: ms.teamsadmincenter.voice.phonenumbers.porting.moreinfo
description: 電話番号を Microsoft Teams に移植するために必要なガイダンスを取得します。
ms.openlocfilehash: 2c84b8bcba4b41488db64cbda42c9162daaf268d
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41827965"
---
# <a name="more-information-about-porting"></a>移植に関する詳細情報

ここでは、電話番号を Microsoft Teams に移植する方法についての詳細情報を参照してください。

詳細な手順については、「[チームに電話番号を転送する](transfer-phone-numbers-to-teams.md)」を参照してください。

ヘルプが必要な場合や、その他の電話番号を取得する必要がある場合は、 [PSTN サービスデスクのヘルプを参照](../manage-phone-numbers-for-your-organization/contact-pstn-service-desk.md)してください。

## <a name="port-order-account-information"></a>ポート注文のアカウント情報

ポート注文を送信するために、移植ウィザードの [**アカウント情報の追加**] ページを表示している場合、loa で提供するものと同じ情報をほとんどすべて入力します。
  
- サービスプロバイダーまたは携帯電話会社のアカウント番号
    
- 請求先電話番号 (BTN)
    
- PIN-現在のサービスプロバイダーまたは携帯電話会社で必要な場合
    
- 組織名
    
    > [!NOTE]
    > この場合、スペースを含めて25文字のみを受け入れます。 組織名が25文字を超える場合、名前の最初の25文字が送信され、ポート注文は処理されたままになります。
  
- アカウントの変更を許可されたユーザーの名前
    
    > [!NOTE]
    > この場合、スペースを含む15文字のみが受け入れられます。 認証する人物の名前が 15 文字より長い場合は、名前の最初の 15 文字が発行され、番号移行注文が処理されます。 
  
- サービス アドレス
  
ポート注文を簡単に送信してエラーが発生しないようにするには、次の操作を行ってください。
  
- 電話番号に関連付けられている機能 (ハントグループなど) を削除します。 これらの電話番号に対して有効になっている「ハントや鳴り呼」などの高度な通話管理機能がないことを確認してください。
    
- 現在のサービスプロバイダーとの新しいサービス注文またはサービスの切断を行っていないことを確認してください。
    
- すべての電話番号が、同じ携帯電話会社および同じアカウントのものであること。
    
- 入力したアカウント情報が電話会社に登録されている内容と正確に一致することを確認してください。 情報の不一致は、最も一般的なエラーの原因であり、ポート注文の遅延につながる可能性があります。
    
> [!CAUTION]
> サービスプロバイダーまたは携帯電話会社のサービスを切断しないでください。 電話番号を Teams に移植するには、以前のサービスを有効のままにしておく必要があります。 お客さまのアカウントをサービスプロバイダまたは携帯電話会社で凍結しないでください。 アカウントを凍結すると、アカウント上で携帯電話会社を変更できません。 認定ユーザーは、凍結を解除するために、現在の携帯電話会社に注文を送信する必要があります。 このプロセスは、通信事業者によっては、1 ~ 3 週間かかることがあります。

## <a name="authorized-person-on-the-account"></a>アカウントの認証済みユーザー

[移植] ウィザードでは、サービスプロバイダーまたは携帯電話会社のアカウントに変更を加える権限を持つユーザーの名前を入力する必要があります。 この名前は、ポート注文の処理には使用されませんが、紛争の場合に使用されます。または、番号の移植時に何らかの問題が発生した場合に使います。 このユーザーは、ポート注文の承認状 (LOA) の責任を持ちます。
  
> [!NOTE]
> ボックスは15文字 (スペースを含む) に制限されています。 ボックスに完全な名前を入力しないと、ポート注文が遅延したり、キャンセルされたりすることはありません。
  
## <a name="whats-my-billing-telephone-number"></a>請求先電話番号とは何ですか?

請求先電話番号 (BTN) は、請求書に記載され、サービスプロバイダまたは携帯電話会社によって請求される主要な電話番号です。 1つの電話番号しかないアカウントから電話番号を転送する場合は、この電話番号を入力する必要があります。 複数の電話番号を使用しているアカウントから電話番号を移行する場合は、請求書を確認するか、サービスプロバイダーまたは通信事業者に連絡して、アカウントの BTN が何であるかを判断してください。

## <a name="what-should-i-put-in-for-the-account-number"></a>アカウント番号には何を入力すればよいですか?

通常、アカウント番号は、お客さまのサービスプロバイダまたは携帯電話から購入した請求書または請求書で確認できます。または、電話会社の web サイトにログインできます。 まだアカウント番号がわからない場合は、サービスプロバイダーまたは携帯電話会社に問い合わせてください。
  
> [!CAUTION]
>  サービスプロバイダーまたは電話会社のアカウント番号を入力するときは、スペース、ダッシュ、ハイフンを使用しないようにすることが重要です。

## <a name="what-should-i-put-in-for-the-organization-name"></a>組織名には何を入力すればよいですか?

これは組織の名前です。 組織名は25文字に制限されています。空白を含めることができます。 会社名は、ポート注文の要求を処理するために使用されることはありません。 問題が発生した場合、または電話番号の移植中に何らかの問題が発生した場合に使用されます。 ボックスに会社の名前全体が収まらない場合は、ポート注文の遅延またはキャンセルは行われません。
  
## <a name="what-should-i-put-in-for-the-service-address"></a>サービスアドレスに何を入力するべきですか?

サービスの住所が、電話サービスプロバイダーまたは携帯電話会社に登録した請求書または緊急対応のアドレスと異なります。 この情報がわからない場合は、お使いのサービスプロバイダーまたは携帯電話会社にお問い合わせください。

## <a name="how-should-i-enter-the-phone-numbers"></a>電話番号を入力する方法を教えてください。
<a name="bkadding"> </a>

ポート注文を送信する場合、適切に書式設定された CSV ファイルを使用して電話番号を送信する必要があります。 CSV ファイルの要件を次に示します。

 - ファイルに任意の名前を付けることができます。
 - ファイルには、PhoneNumber という名前のヘッダーを持つ1つの列のみを指定する必要があります。
 - 各電話番号は、別々の行にある必要があります。
 - 電話番号は、数字のみ、または E.i 形式にすることができます。
 - 電話番号の形式は、選択した国または地域と一致する必要があります。 たとえば、移植ウィザードで英国を選択した場合、44 (国コード) を使用し、その後に正しい数字の電話番号が続くようにします。 たとえば、4420812341234のようになります。

## <a name="how-do-i-see-the-status-of-my-port-order"></a>ポート注文の状態を確認する方法を教えてください。

「[ポート注文の状態を確認する方法](port-order-status.md)」を参照してください。

## <a name="related-topics"></a>関連トピック

- [番号移行注文について](port-order-overview.md)
- [通話プランで使用されるさまざまな種類の電話番号](../different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [組織の電話番号を管理する](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)
- [緊急通話の利用条件](../emergency-calling-terms-and-conditions.md)
- [緊急通話の免責事項ラベル](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)
