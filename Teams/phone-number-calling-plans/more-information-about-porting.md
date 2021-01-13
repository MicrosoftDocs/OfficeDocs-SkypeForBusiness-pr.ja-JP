---
title: 移植の詳細
author: cichur
ms.author: v-cichur
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
ms.openlocfilehash: bb63e22b7cc3aa787ddb984f82180937c5aaf9fc
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802517"
---
# <a name="more-information-about-porting"></a>移植の詳細

ここでは、電話番号を Microsoft Teams に移植する方法の詳細について説明します。

詳しい手順については、「電話番号を Teams に転送 [する」を参照してください](transfer-phone-numbers-to-teams.md)。

サポートが必要な場合、または電話番号を追加する必要がある場合は、PSTN サービス デスクの [ヘルプにお問い合わせください](../manage-phone-numbers-for-your-organization/contact-pstn-service-desk.md)。

## <a name="port-order-account-information"></a>番号注文のアカウント情報

移植注文を送信するために、移植ウィザードの [アカウント情報の追加] ページを開き、LOA で提供するのとほぼ同じ情報を入力します。次に示します。
  
- サービス プロバイダーまたは通信事業者のアカウント番号
    
- 請求先電話番号 (BTN)
    
- PIN - 現在のサービス プロバイダーまたは通信事業者が必要とする場合
    
- 組織名
    
    > [!NOTE]
    > この場合、スペースを含めて 25 文字のみを使用できます。 組織名が 25 文字を超える場合、名前の最初の 25 文字が送信され、番号の注文は処理されます。
  
- アカウントを変更する権限を持つユーザーの名前
    
    > [!NOTE]
    > この場合、スペースを含めて 15 文字しか使用できません。 認証する人物の名前が 15 文字より長い場合は、名前の最初の 15 文字が発行され、番号移行注文が処理されます。 
  
- サービス アドレス
  
移行注文を簡単に送信し、エラーを回避するには、次の操作を行います。
  
- 電話番号に関連付けられている機能 (Hunt Groups など) を削除します。 これらの電話番号で有効になっている通話の高度な通話制御機能 (通話探しや特有の呼び出しなど) が行えなかからず確認します。
    
- 現在のサービス プロバイダーとの新しいサービス注文や切断を行っていないか確認します。
    
- すべての電話番号が、同じ携帯電話会社および同じアカウントのものであること。
    
- 入力したアカウント情報が電話会社に登録されている内容と正確に一致することを確認してください。 情報の不一致がエラーの最も一般的な原因であり、ポート注文が遅れる可能性があります。
    
> [!CAUTION]
> サービス プロバイダーまたは通信事業者との間でサービスを切断しない。 電話番号を Teams に移植するには、以前のサービスをアクティブな状態に保つ必要があります。 サービス プロバイダーまたは通信事業者でアカウントを凍結しないでください。 アカウントを凍結すると、アカウント上で携帯電話会社を変更できません。 認定ユーザーは、凍結を解除するために、現在の携帯電話会社に注文を送信する必要があります。 このプロセスには、通信事業者によっては 1 ~ 3 週間かかる場合があります。

## <a name="authorized-person-on-the-account"></a>アカウントの認証されたユーザー

移植ウィザードで、サービス プロバイダーまたは通信事業者でアカウントを変更する権限を持つユーザーの名前を入力する必要があります。 この名前はポート注文の処理には使用されませんが、争議が発生した場合、または番号を移植するときに何かが間違っている場合に使用されます。 このユーザーは、ポート注文の承認状 (LOA) に対して責任を持つ必要があります。
  
> [!NOTE]
> ボックスの文字数は 15 文字までです (スペースを含む)。 ボックスに完全な名前が入力されていないと、ポート注文が遅れることや取り消されるという問題は発生し得ない。
  
## <a name="whats-my-billing-telephone-number"></a>請求先電話番号は何ですか?

請求先電話番号 (BTN) は、請求書に含まれており、サービス プロバイダーまたは通信事業者が請求するメインの電話番号です。 電話番号が 1 つのみであるアカウントから電話番号を移行する場合は、この電話番号を入力する必要があります。 複数の電話番号を持つアカウントから電話番号を移行する場合は、請求書を確認するか、サービス プロバイダーまたは通信事業者に問い合わせ、アカウントの BTN を決定できます。

## <a name="what-should-i-put-in-for-the-account-number"></a>アカウント番号に何を入力する必要がありますか?

通常、アカウント番号は、サービス プロバイダーまたは通信事業者の請求書や請求書で確認できます。また、通信事業者の Web サイトにログオンすることもできます。 それでもアカウント番号が分からない場合は、サービス プロバイダーまたは通信事業者に問い合わせ、番号を取得できます。
  
> [!CAUTION]
>  サービス プロバイダーまたは通信事業者のアカウント番号を入力するときに、スペース、ダッシュ、ハイフンを使用しないでください。

## <a name="what-should-i-put-in-for-the-organization-name"></a>組織名に何を入力する必要がありますか?

これは組織の名前です。 組織名は、スペースを含む 25 文字に制限されます。 会社の名前は、ポート注文要求の処理には使用されません。 争議が発生した場合、または電話番号の移植時に問題が発生した場合に使用されます。 ボックスに会社の名前全体を入れ替えきれな場合、ポート注文を遅らせ、取り消す必要があります。
  
## <a name="what-should-i-put-in-for-the-service-address"></a>サービス アドレスに何を入力する必要がありますか?

サービス アドレスは、電話サービス プロバイダーまたは通信事業者に登録した請求先または緊急対応の住所とは異なります。 この情報が分からない場合は、サービス プロバイダーまたは通信事業者に問い合わせ、アカウントに記載されているサービス アドレスを確認してください。

## <a name="how-should-i-enter-the-phone-numbers"></a>電話番号を入力する方法
<a name="bkadding"> </a>

ポート注文を送信する場合、電話番号を送信するには、適切に書式設定された CSV ファイルを使用する必要があります。 CSV ファイルの要件は次のとおりです。

 - ファイルには任意の名前を付けできます。
 - ファイルには、PhoneNumber という名前のヘッダーを含む 1 つの列のみを含む必要があります。
 - 各電話番号は個別の行に入力する必要があります。
 - 電話番号には、数字のみ、または E.164 形式を使用できます。
 - 電話番号の形式は、選択した国または地域と一致している必要があります。 たとえば、移植ウィザードで英国を選ぶ場合は、国コードである 44 を使用し、その後に正しい桁数で電話番号を入力します。 たとえば、4420812341234 などです。

## <a name="how-do-i-see-the-status-of-my-port-order"></a>ポート注文の状態を確認する方法

ポート [注文の状態を確認する](port-order-status.md)

## <a name="related-topics"></a>関連項目

- [番号移行注文について](port-order-overview.md)
- [通話プランで使用されるさまざまな種類の電話番号](../different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [組織の電話番号を管理する](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)
- [緊急通話の利用条件](../emergency-calling-terms-and-conditions.md)
- [緊急通話の免責事項ラベル](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)
