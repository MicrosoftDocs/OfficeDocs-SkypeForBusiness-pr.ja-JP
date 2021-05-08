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
description: 電話番号を電話番号に移植するために必要なガイダンスをMicrosoft Teams。
ms.openlocfilehash: bb63e22b7cc3aa787ddb984f82180937c5aaf9fc
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802517"
---
# <a name="more-information-about-porting"></a>移植の詳細

電話番号を電話番号に移植する方法の詳細については、こちらをMicrosoft Teams。

詳しい手順については、「電話番号を電話番号に転送する」を[参照Teams。](transfer-phone-numbers-to-teams.md)

サポートが必要な場合、またはさらに電話番号を取得する必要がある場合は、PSTN サービス デスクの [ヘルプ にお問い合わせください](../manage-phone-numbers-for-your-organization/contact-pstn-service-desk.md)。

## <a name="port-order-account-information"></a>ポート注文アカウント情報

移植ウィザードの [アカウント情報の追加] ページでポート注文を送信する場合は、LOA で指定するのとほぼ同じ情報 (次を含む) を入力します。
  
- サービス プロバイダーまたは通信事業者のアカウント番号
    
- 請求先電話番号 (BTN)
    
- PIN - 現在のサービス プロバイダーまたは通信事業者が必要とする場合
    
- 組織名
    
    > [!NOTE]
    > これには、スペースを含む 25 文字のみを使用できます。 組織名が 25 文字を超える場合、名前の最初の 25 文字が送信され、ポートの順序は引き続き処理されます。
  
- アカウントを変更する権限を持つユーザーの名前
    
    > [!NOTE]
    > スペースを含む 15 文字のみを使用できます。 認証する人物の名前が 15 文字より長い場合は、名前の最初の 15 文字が発行され、番号移行注文が処理されます。 
  
- サービス アドレス
  
ポート注文の送信を簡単にし、エラーを回避するには、次の操作を行います。
  
- 番号に関連付けられている機能 (Hunt Groups など) を削除します。 これらの電話番号で通話の検索や独特の呼び出しなどの高度な通話制御機能が有効になっていないか確認します。
    
- 新しいサービス注文を行っていないか、現在のサービス プロバイダーとの接続が切断されていないことを確認します。
    
- すべての電話番号が、同じ携帯電話会社および同じアカウントのものであること。
    
- 入力したアカウント情報が電話会社に登録されている内容と正確に一致することを確認してください。 情報の不一致は、エラーの最も一般的な原因であり、ポートの順序を遅らせる可能性があります。
    
> [!CAUTION]
> サービス プロバイダーまたは通信事業者との間でサービスを切断しない。 電話番号を新しい電話番号に移植するには、以前のサービスをアクティブな状態Teams。 サービス プロバイダーまたは通信事業者でアカウントを凍結しないでください。 アカウントを凍結すると、アカウント上で携帯電話会社を変更できません。 認定ユーザーは、凍結を解除するために、現在の携帯電話会社に注文を送信する必要があります。 このプロセスは、運送業者によっては 1 ~ 3 週間かかる場合があります。

## <a name="authorized-person-on-the-account"></a>アカウントの承認されたユーザー

移植ウィザードで、サービス プロバイダーまたは通信事業者のアカウントを変更する権限を持つユーザーの名前を入力する必要があります。 この名前は、ポート注文の処理には使用されませんが、争議の場合、または番号の移植時に何かが正しくない場合に使用されます。 このユーザーは、ポート注文の承認状 (LOA) に対して責任を持つ必要があります。
  
> [!NOTE]
> ボックスは 15 文字 (スペースを含む) に制限されています。 ボックスに完全な名前を付けなかった場合、ポートの注文が遅れることも取り消される場合も、この問題は発生し得ない可能性があります。
  
## <a name="whats-my-billing-telephone-number"></a>請求先電話番号は何ですか?

請求先電話番号 (BTN) は、請求書に含まれており、サービス プロバイダーまたは通信事業者によって請求されるメイン電話番号です。 電話番号が 1 つのみであるアカウントから電話番号を転送する場合は、この電話番号を入力する必要があります。 複数の電話番号を持つアカウントから電話番号を転送する場合は、請求書を確認するか、サービス プロバイダーまたは通信事業者に連絡して、アカウントの BTN が何かを判断できます。

## <a name="what-should-i-put-in-for-the-account-number"></a>アカウント番号には何を入力する必要がありますか?

通常、アカウント番号は、サービス プロバイダーまたは運送業者から取得した請求書または請求書で確認できます。また、運送業者の Web サイトにログオンすることもできます。 それでもアカウント番号が分からない場合は、サービス プロバイダーまたは通信事業者に連絡して取得できます。
  
> [!CAUTION]
>  サービス プロバイダーまたは運送業者のアカウント番号を入力するときに、スペース、ダッシュ、ハイフンを使用しないでください。

## <a name="what-should-i-put-in-for-the-organization-name"></a>組織名には何を入力する必要がありますか?

これは組織の名前です。 組織名は、スペースを含む 25 文字に制限されています。 会社の名前は、ポート注文要求の処理には使用されません。 これは、紛争が発生した場合、または電話番号の移植時に何かが正しくない場合に使用されます。 ボックスに会社の名前全体を入力できない場合は、ポート注文を遅らせ、取り消す必要があります。
  
## <a name="what-should-i-put-in-for-the-service-address"></a>サービス アドレスには何を入力する必要がありますか?

サービス アドレスは、電話サービス プロバイダーまたは通信事業者に登録した請求先または緊急対応の住所とは異なります。 これを知らない場合は、サービス プロバイダーまたは通信事業者に問い合わせ、アカウントに記載されているサービス アドレスを確認してください。

## <a name="how-should-i-enter-the-phone-numbers"></a>電話番号を入力する方法
<a name="bkadding"> </a>

ポート注文を送信する場合は、適切に書式設定された CSV ファイルを使用して電話番号を送信する必要があります。 CSV ファイルの要件を次に示します。

 - ファイルには任意の名前を付けできます。
 - このファイルには、PhoneNumber という名前のヘッダーを含む 1 つの列のみを含む必要があります。
 - 各電話番号は個別の行に入る必要があります。
 - 電話は、数字のみ、または E.164 形式で指定できます。
 - 電話番号の形式は、選択した国または地域と一致している必要があります。 たとえば、移植ウィザードで英国を選択した場合は、国コードである 44 を使用し、その後に正しい桁数の電話番号を使用します。 たとえば、4420812341234 などです。

## <a name="how-do-i-see-the-status-of-my-port-order"></a>ポート注文の状態を確認する方法

「 [ポート注文の状態は何ですか?」を参照してください。](port-order-status.md)

## <a name="related-topics"></a>関連トピック

- [番号移行注文について](port-order-overview.md)
- [通話プランで使用されるさまざまな種類の電話番号](../different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [組織の電話番号を管理する](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)
- [緊急通話の利用条件](../emergency-calling-terms-and-conditions.md)
- [緊急通話の免責事項ラベル](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)
