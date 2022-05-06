---
title: 移植の詳細
author: SerdarSoysal
ms.author: serdars
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
ms.localizationpriority: medium
search.appverid: MET150
ROBOTS: NOINDEX, NOFOLLOW
f1.keywords:
- CSH
ms.custom: ms.teamsadmincenter.voice.phonenumbers.porting.moreinfo
description: 電話番号をMicrosoft Teamsに移植するために必要なガイダンスを取得します。
ms.openlocfilehash: 6c1bca140c5842e36ddd82ae6417228caea75c9e
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/05/2022
ms.locfileid: "62414240"
---
# <a name="more-information-about-porting"></a>移植の詳細

電話番号をMicrosoft Teamsに移植する方法の詳細については、以下をご覧ください。

詳細な手順については、「[Teamsに電話番号を転送する」を](transfer-phone-numbers-to-teams.md)参照してください。

ヘルプが必要な場合、または電話番号を増やす必要がある場合は、 [TNS サービス デスクのヘルプ](../manage-phone-numbers-for-your-organization/contact-tns-service-desk.md)にお問い合わせください。

## <a name="port-order-account-information"></a>ポート注文アカウント情報

移植ウィザードの **[アカウント情報の追加]** ページでポート注文を送信する場合は、LOA で提供する情報とほぼ同じ情報を次のように入力します。
  
- サービス プロバイダーまたは運送業者のアカウント番号
    
- 請求先電話番号 (BTN)
    
- PIN - 現在のサービス プロバイダーまたは通信事業者が必要とする場合
    
- 組織名
    
    > [!NOTE]
    > これは、スペースを含め、25 文字のみを受け入れます。 組織名が 25 文字より長い場合、名前の最初の 25 文字が送信され、ポートの順序は引き続き処理されます。
  
- アカウントに変更を加える権限を持つユーザーの名前
    
    > [!NOTE]
    > これは、スペースを含む 15 文字のみを受け入れます。 認証する人物の名前が 15 文字より長い場合は、名前の最初の 15 文字が発行され、番号移行注文が処理されます。 
  
- サービス アドレス
  
ポートの順序を簡単に送信し、エラーを回避するには、次の操作を行うことを確認します。
  
- 番号に関連付けられているすべての機能 (ハント グループなど) を削除します。 これらの電話番号で、通話ハントや特性リングなどの高度な通話制御機能が有効になっていないことを確認します。
    
- 新しいサービス注文を行っていないか、現在のサービス プロバイダーとの接続を切断していないことを確認します。
    
- すべての電話番号が、同じ携帯電話会社および同じアカウントのものであること。
    
- 入力したアカウント情報が電話会社に登録されている内容と正確に一致することを確認してください。 情報の不一致はエラーの最も一般的な原因であり、ポートの順序を遅らせる可能性があります。
    
> [!CAUTION]
> サービス プロバイダーまたは通信事業者とサービスを切断しないでください。 電話番号をTeamsに移植するには、以前のサービスをアクティブにしておく必要があります。 サービス プロバイダーまたは通信事業者でアカウントを凍結しないでください。 アカウントを凍結すると、アカウント上で携帯電話会社を変更できません。 認定ユーザーは、凍結を解除するために、現在の携帯電話会社に注文を送信する必要があります。 このプロセスは、運送業者によっては、1 週間から 3 週間かかる場合があります。

## <a name="authorized-person-on-the-account"></a>アカウントの承認されたユーザー

移植ウィザードで、サービス プロバイダーまたは運送業者を使用してアカウントを変更する権限を持つユーザーの名前を入力する必要があります。 この名前は、ポートの順序を処理するために使用されませんが、問題が発生した場合や、番号が移植されたときに正しくない場合に使用されます。 このユーザーは、ポート注文の承認レター (LOA) に対して責任を負います。
  
> [!NOTE]
> ボックスは 15 文字 (スペースを含む) に制限されています。 ボックスに完全な名前が含まれていないと、ポートの順序が遅延したり取り消されたりすることはありません。
  
## <a name="whats-my-billing-telephone-number"></a>請求先の電話番号は何ですか?

課金電話番号 (BTN) は、請求書に含まれており、サービス プロバイダーまたは運送業者によって請求される主要な電話番号です。 電話番号が 1 つしかないアカウントから電話番号を転送する場合は、この電話番号を入力する必要があります。 複数のアカウントから電話番号を転送する場合は、請求書を確認するか、サービス プロバイダーまたは通信事業者に問い合わせて、アカウントの BTN が何であるかを判断できます。

## <a name="what-should-i-put-in-for-the-account-number"></a>アカウント番号には何を入力する必要がありますか?

通常、アカウント番号は、サービス プロバイダーまたは運送業者から取得した請求書または請求書で確認できます。または、配送業者の Web サイトにログオンすることもできます。 アカウント番号がわからない場合は、サービス プロバイダーまたは通信事業者に問い合わせて取得できます。
  
> [!CAUTION]
>  サービス プロバイダーまたは運送業者のアカウント番号を入力するときに、スペース、ダッシュ、ハイフンを使用しないようにすることが重要です。

## <a name="what-should-i-put-in-for-the-organization-name"></a>組織名には何を入力する必要がありますか?

これは組織の名前です。 組織名は、スペースを含む 25 文字に制限されています。 会社の名前は、ポート注文要求を処理するために使用されません。 これは、問題が発生した場合、または電話番号が移植されているときに何かが正しくない場合に使用されます。 会社の名前全体をボックスに収めることができない場合、ポート注文を遅延したり取り消したりすることはありません。
  
## <a name="what-should-i-put-in-for-the-service-address"></a>サービス アドレスには何を入力する必要がありますか?

サービス アドレスは、電話サービス プロバイダーまたは通信事業者に登録した請求先または緊急対応の住所とは異なります。 不明な場合は、サービス プロバイダーまたは通信事業者に問い合わせて、アカウントに一覧表示されているサービス アドレスを確認してください。

## <a name="how-should-i-enter-the-phone-numbers"></a>電話番号を入力する方法を教えてください。
<a name="bkadding"> </a>

ポート注文を送信するときは、適切に書式設定された CSV ファイルを使用して電話番号を送信する必要があります。 CSV ファイルの要件を次に示します。

 - ファイルに任意の名前を付けることができます。
 - このファイルには、PhoneNumber という名前のヘッダーを含む列が 1 つだけ含まれている必要があります。
 - 各電話番号は、個別の行にある必要があります。
 - 電話数字は数字のみ、または E.164 形式で指定できます。
 - 電話番号の形式は、選択した国または地域と一致する必要があります。 たとえば、移植ウィザードで英国を選択した場合は、国番号である 44 を使用し、電話番号の後に正しい数字を付けます。 たとえば、4420812341234。

## <a name="how-do-i-see-the-status-of-my-port-order"></a>ポート注文の状態を確認操作方法。

[ポート注文の状態を確認してください。](port-order-status.md)

## <a name="related-topics"></a>関連項目

- [番号移行注文について](port-order-overview.md)
- [通話プランで使用されるさまざまな種類の電話番号](../different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [組織の電話番号を管理する](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)
- [緊急通話の利用条件](../emergency-calling-terms-and-conditions.md)
- [緊急通話の免責事項ラベル](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)
