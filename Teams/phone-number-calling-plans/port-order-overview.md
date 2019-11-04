---
title: ポート注文とは何ですか?
ms.author: v-lanac
author: lanachin
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: ms.teamsadmincenter.voice.phonenumbers.porting.overview
ms.custom:
- Calling Plans
description: ポート注文の概要と、サービスプロバイダーからチームに電話番号を移行する方法について説明します。
ms.openlocfilehash: 4edaac3722e8fc37ca856b240171f923a0a99f66
ms.sourcegitcommit: 100ba1409bf0af58e4430877c1d29622d793d23f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/01/2019
ms.locfileid: "37925673"
---
# <a name="whats-a-port-order"></a>ポート注文とは何ですか?

現在、電話サービスプロバイダーまたは電話会社をお持ちで、ユーザーまたはサービスの電話番号を既にお持ちの場合は、「*ポート注文*」を作成して、それらの電話番号を Microsoft Teams に転送する必要があります。 電話番号を移行するときは、電話会議 (会議ブリッジ用)、自動応答、および通話キューなどのユーザーやサービスに電話番号を割り当てることができます。
  
チームに電話番号を移行すると、Microsoft がサービスプロバイダになり、お客さまのサービスプロバイダーまたは携帯電話会社のサービスを切断することができます。

この記事の情報を確認して、番号の移行について理解してください。 その後、ポート注文を作成して電話番号を転送する準備ができました。 詳細な手順については、「[チームに電話番号を転送する](transfer-phone-numbers-to-teams.md)」を参照してください。
  
## <a name="what-countries-or-regions-support-number-porting"></a>番号の移行をサポートしている国または地域を教えてください。

サポートされているすべての国または地域で電話番号を移行または転送することはできますが、ポート注文の要求を送信する方法は、電話番号の取得元の国または地域によって異なります。 番号の移行をサポートしている国と地域の一覧については、「[組織の電話番号を管理](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)する」を参照してください。
  
## <a name="what-numbers-can-be-transferred"></a>どの番号を移行できますか?

 **転送できます。**
  
一般に、サポートされているプロバイダーからの電話番号は、次のようにすべて譲渡できます。
  
- 固定電話の番号です。

- 携帯電話やタブレットなどで使用されるモバイルデバイスの電話番号。

    > [!NOTE]
    > 携帯電話番号の譲渡は、米国とプエルトリコでのみ利用できます。
  
- 有料電話番号。

- フリー ダイヤル電話番号。

    > [!NOTE]
    > UIFN (世界共通国際フリーダイヤル番号) はマイクロソフトに移すことができません。 
  
- 会議ブリッジや自動応答などで使用されるサービス電話番号。

- Fax 電話番号 (ただし Fax 送信に使用することはできません)。 ユーザーに割り当てられている必要があります。

- Vonage や RingCentral などの電話会社からの VoIP 電話番号。

- Skype for Business ハイブリッド電話番号。 これらの番号を移行する場合は、メールで<ptn@microsoft.com>お送りください。

  **次の転送はできません。**
  
    > [!NOTE]
    > 現時点では、VoIP 電話会社の電話番号を含む、サポートされている国または地域以外の電話番号や電話番号を移行することはできません。 サポートされる国/地域の一覧については、「[電話会議と通話プランの国と地域の空き時間](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)情報」を参照してください。
  
- DSL 回線やブロードバンド インターネット接続などのデータ接続で使用される電話番号を移転することもできません。

- FAX 専用の電話番号。

    Fax に使用されている既存の専用電話番号がある場合は、これらの番号を Teams に転送する*ことはでき*ますが、fax サービスは期待どおりに動作しません。 電話システム、国内通話プラン、または国際通話プランのライセンスを所有している場合でも、チームのお客様は fax サービスを利用できません。

    電話番号を Teams に移植する場合は、この電話番号を fax に使用する代わりに、組織内のユーザーに割り当てることができます。

    > [!NOTE]
    > 現時点で英国では、市外局番0843、0844、0845、0870、0871、0872の共有コスト番号を含む、英国以外の番号の移行をサポートしていません。
  
## <a name="what-information-do-i-need-to-provide"></a>どのような情報を提供する必要がありますか?

現在の電話会社のすべてのアカウント情報が必要です。 ポート注文に入力した情報は、主に現在のサービスプロバイダーからの最新の請求書または請求書に記載されています。 また、アカウントに名前が付けられていることを確認する必要があります。また、どのような番号を移植するかも確認してください。
  
## <a name="what-are-full-port-and-partial-port-transfers"></a>フルポート移行およびパーシャルポート移行とは何ですか?

電話番号を Teams に移行している場合は、すべての番号または一部の番号を移行するオプションがあります。
  
- **フルポート**これは、現在のサービスプロバイダーからチームにすべての電話番号を転送する場合です。 転送する電話番号を入力するように求められた場合は、アカウントの他のすべての電話番号と共に、請求先電話番号 (BTN) を*含める必要があり*ます。

    たとえば、BTN が *+ 1 425-555-1234*で、25個の電話番号をすべて移植する場合 (*+ 1 425-555-1235 ~ 1259*) とします。 下の手順に従って番号を移行する場合、次のように入力します: **+14255551234 - +14255551259** 。

- **部分ポート**これは、現在のサービスプロバイダからの一部の電話番号だけを Teams に転送する場合です。 同じ BTN に関連付けられている電話番号の一部を移植する場合は、* * BTN と、アカウントの他のすべての電話番号と共に * * を含めることはでき*ません*。

    たとえば、BTN が *+ 1 425-555-1234*で、25個の電話番号のうちの5つのみを移植する (*+ 1 425-555-1235 ~ 1259*) とします。 下の手順に従って番号を移行する場合、次のように入力します: **+1 425 555 1235 - +1 425 555 1239** 。
    
## <a name="can-i-submit-a-single-number-porting-request-for-all-of-my-numbers-at-one-time"></a>すべての電話番号の移行を単一の要求で送信できますか?
<a name="bkmk_type_1"> </a>

移行する電話番号のそれぞれの電話会社と種類に対して個別の要求が必要です。
  
たとえば、次のそれぞれの種類の電話番号に対して、個別の番号移行要求を送信する必要があります。
  
- 加入者番号または地域番号とも呼ばれる国内の有料電話番号

- 800、844、855、866、877、および 888 のような市外局番を含むフリーダイヤル番号

- 携帯電話番号

- Office 365 で電話会議に使用できるサービス番号。

次に、これらの各種類の数値に対して番号移行要求を送信する方法について詳しく説明します。
  
- 各航空会社によって提供される**電話番号**には、各通信事業者との番号に対する固有の移植要求が必要です。

- 800、844、855、866、877、888などの市外局番を含むフリー**ダイヤル番号**は、他の種類の番号を使って、番号の移植要求に含めることはできません。 これらの無料電話番号を移植するには、[手動でポート注文を送信](manually-submit-port-order.md)する必要があります。 Microsoft Teams 管理センターでは、これらの番号に移植することはできません。 詳細については、「[組織のために電話番号を管理する](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)」をご覧ください。

    発信先の国と電話番号の種類に適切な承認状 (LOA) を使用することが重要です。 [ここで必要な LOA をダウンロード](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)できます。

- **携帯電話番号** には、移行を承認するための PIN コードが必要です。 したがって、個別の番号移行要求が必要です。

- **サービス電話番号** の移行要求は、別に送信する必要があります。 他の種類の電話番号で送信することはできません。

## <a name="how-long-does-it-take-to-port-numbers"></a>番号の移行にはどれくらいかかりますか?
<a name="bkmk_type_1"> </a>

ポート注文の要求が完了すると、処理が完了するまでに7-14 日がかかります。 ただし、サービス プロバイダーによっては、最大 30 日かかる場合があります。 電話番号を移行した後は、skype からメールを受信して、連絡を取ることができます。
  
ポート注文の状態を確認するには、Microsoft Teams 管理センターの左側のナビゲーションで、[**電話番号** **] に移動** > し、[**注文履歴**] をクリックします。 各ポート注文の状態は、[**状態**」列に表示されます。
  
## <a name="can-user-subscriber-phone-numbers-be-converted-to-service-numbers"></a>ユーザー (加入者番号) の電話番号をサービス番号に変更できますか?
<a name="bkmk_type_1"> </a>

はい、できます。 変換したい組織のテナント GUID と電話番号を含んでいるサービス要求を送信するだけです。 これを行うには、「[組織の電話番号を管理](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)する」を参照してください。

## <a name="common-mistakes-to-watch-out-for"></a>注意すべきよくあるミス
<a name="bkmk_type_1"> </a>

番号の移行は簡単です。 ただし、電話サービスプロバイダで問題が発生した場合は、注文が未完了であり、情報が不足している、または誤入力があります。
  
お客様が番号を移行される場合に最もよくあるミスを以下に示します。カスタマー サポートに問い合わせずにすむように、これらのミスについて慎重に確認してください。
  
- 入力したアカウント情報が電話会社に登録されている内容と正確に一致することを確認してください。これらの情報の不一致が、番号移行注文のエラーや遅延の最も一般的な原因です。以下の情報が正しいことを確認してください。

  - アカウントを変更することを許可された名前またはユーザーが正しい。

  - 住所があっている。

  - アカウント番号が正しい。

  - BTN が正しい。

- これらの電話番号で有効になっている "ハントの呼び出し"、"鳴り Ring" などの高度な通話管理機能がないことを確認してください。

- 現在のサービス プロバイダーとの新しいサービス オーダーの発注またはサービスの解除の発注を行っていないことを確認してください。

- すべての電話番号が、同じ携帯電話会社および同じアカウントのものであること。

- サービスが有効になっていることを確認してください。 アカウントを凍結すると、アカウント上で携帯電話会社を変更できません。 アカウントを変更する権限を持つユーザーは、現在の通信事業者に注文を送信して、固定を解除する必要があります。 このプロセスには、キャリアに応じて、1 ~ 3 週間かかることがあります。

## <a name="related-topics"></a>関連項目

- [ポート注文の状態は何ですか?](port-order-status.md)
- [通話プランで使用されるさまざまな種類の電話番号](../different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [組織の電話番号を管理する](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)
- [緊急通話の利用条件](../emergency-calling-terms-and-conditions.md)
- [緊急通話の免責事項ラベル](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)