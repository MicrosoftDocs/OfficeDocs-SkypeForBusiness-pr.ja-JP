---
title: 番号移行注文について
ms.author: v-cichur
author: cichur
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
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.voice.phonenumbers.porting.overview
- Calling Plans
description: ポート注文の概要と、サービス プロバイダーからサービス プロバイダーに電話番号を転送する方法Teams。
ms.openlocfilehash: d7ca4769dcd1f320a7d0b8a8ed18fdba5b06abbd
ms.sourcegitcommit: 31a585cc0fe6350efacf3a7771d1e590d5e4233c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/10/2021
ms.locfileid: "50615053"
---
# <a name="whats-a-port-order"></a>番号移行注文について

現在、電話サービス プロバイダーまたは携帯電話会社をお持ちで、ユーザーまたはサービスの電話番号を既に持っている場合は、"ポート *注文"* を作成して、これらの電話番号を Microsoft Teams に転送する必要があります。 番号を移植すると、電話会議 (会議ブリッジの場合)、自動応答、通話キューなどのユーザーとサービスにそれらの電話番号を割り当てできます。
  
電話番号を Teams に移植すると、Microsoft がサービス プロバイダーになり、古いサービス プロバイダーまたは通信事業者とサービスを切断できます。

番号の移植について理解するために、この記事の情報を確認してください。 その後、ポート注文を作成し、電話番号を転送する準備が整います。 詳[しい手順については、「](transfer-phone-numbers-to-teams.md)電話番号を Teamsに転送する」を参照してください。
  
## <a name="what-countries-or-regions-support-number-porting"></a>番号の移植をサポートしている国または地域

サポートされているすべての国または地域で電話番号を移植または転送できますが、ポート注文要求を送信する方法は、電話番号が届く国または地域によって異なります。 番号の移植をサポートする国と地域の一覧については、「組織の電話番号を管理する」 [を参照してください](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)。  

現在[、Microsoft Teams](transfer-phone-numbers-to-teams.md)管理センターの移植ウィザードでは、英国、米国、カナダの電話番号の取得がサポートされています。 他の国や地域の電話番号を取得するには、ポート注文 [を手動で送信します](manually-submit-port-order.md)。
  
## <a name="what-numbers-can-be-transferred"></a>どの番号を移行できますか?

 **を転送できます。**
  
一般に、次の情報を含め、サポートされているプロバイダーから任意の電話番号を転送できます。
  
- 固定電話の番号です。

- 携帯電話やタブレットに使用される携帯電話の電話番号など、モバイル デバイスの電話番号。

    > [!NOTE]
    > 携帯電話番号の転送は、米国とプエルトリコでのみ利用できます。
  
- 有料電話番号。

- フリー ダイヤル電話番号。

    > [!NOTE]
    > UIFN (世界共通国際フリーダイヤル番号) はマイクロソフトに移すことができません。 
  
- 会議ブリッジや自動応答などで使用されるサービス電話番号。

- Fax 電話番号 (ただし Fax 送信に使用することはできません)。 ユーザーに割り当てる必要があります。

- Vonage や RingCentral などの電話会社からの VoIP 電話番号。

- Skype for Businessハイブリッド電話番号を作成します。 これらの番号を転送する場合は、 までメールでお問い合わせください <ptn@microsoft.com> 。

  **次の情報を転送できない:**
  
    > [!NOTE]
    > 現時点では、VoIP 電話プロバイダーからの電話番号を含め、サポートされている国または地域からではない電話番号や電話番号を転送する必要があります。 サポートされている国/地域の一覧については、「電話会議と通話プランの国と地域の可用性 [」を参照してください。](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
  
- DSL 回線やブロードバンド インターネット接続などのデータ接続で使用される電話番号を移転することもできません。

- FAX 専用の電話番号。

    FAX に使用されている専用の電話番号が既存の場合は、これらの番号をTeams に転送できますが、FAX サービスは期待した通り動作し続けません。 faxing サービスは、Teams、国内通話プラン、または国際通話プランのライセンスを持っている場合でも、電話システム のお客様は利用できません。

    電話番号を電話番号にTeams、FAX 送信に使用する代わりに、組織内のユーザーにこの電話番号を割り当てできます。

    > [!NOTE]
    > 現在、英国では、市外コード 0843、0844、0845、0870、0871、0872 の共有コスト番号を含む、英国以外の地域番号の転送はサポートされていません。
  
## <a name="what-information-do-i-need-to-provide"></a>どのような情報を提供する必要がありますか?

現在の運送業者のすべてのアカウント情報が必要です。 ポート注文で入力した情報は、ほとんどの場合、現在のサービス プロバイダーからの最新の請求書に表示されます。 また、アカウントに登録されている名前と、移植する番号を知る必要があります。
  
## <a name="what-are-full-port-and-partial-port-transfers"></a>フルポート移行およびパーシャルポート移行とは何ですか?

電話番号を新しい電話番号にTeams、すべての電話番号または電話番号の一部を転送するオプションがあります。
  
- **Full-port** これは、すべての番号を現在のサービス プロバイダーからサービス プロバイダーに転送Teams。 転送する電話番号を求めるメッセージが表示された場合は、請求先電話番号(BTN) とアカウントの他のすべての電話番号を含める必要があります。

    たとえば、BTN が  *+1 425-555-1234*  で、25 の電話番号 *(+1 425-555-1235 ~ 1259)* を移植するとします。 下の手順に従って番号を移行する場合、次のように入力します: **+14255551234 - +14255551259** 。

- **部分ポート** これは、現在のサービス プロバイダーから現在のサービス プロバイダーに電話番号の一部のみを転送Teams。 同じ BTN に関連付けられている電話番号の一部を移植する場合は *、*** をアカウントの他のすべての電話番号と共に含めすることはできません。

    たとえば、BTN が  *+1 425-555-1234*  で、25 の電話番号 *(+1 425-555-1235 ~ 1259)* の 5 つのみを移植するとします。 下の手順に従って番号を移行する場合、次のように入力します: **+1 425 555 1235 - +1 425 555 1239** 。
    
## <a name="can-i-submit-a-single-number-porting-request-for-all-of-my-numbers-at-one-time"></a>すべての電話番号の移行を単一の要求で送信できますか?
<a name="bkmk_type_1"> </a>

移行する電話番号のそれぞれの電話会社と種類に対して個別の要求が必要です。
  
たとえば、次のそれぞれの種類の電話番号に対して、個別の番号移行要求を送信する必要があります。
  
- ローカルの有料電話番号 (サブスクライバー番号または地理的な番号とも呼ばれる)

- 800、844、855、866、877、および 888 のような市外局番を含むフリーダイヤル番号

- 携帯電話番号

- 電話会議で使用できるサービス番号は、Microsoft 365またはOffice 365。

これらの種類の番号ごとに番号の移植要求を送信する方法の詳細を次に示します。
  
- **電話提供される** 番号には、各運送業者との番号に対して一意の移植要求が必要です。

- 市 **番**(800、844、855、866、877、888 など) を含む無料電話番号は、他の種類の番号を含む番号の移植要求に含めません。 これらの無料電話番号を移植するには、ポート注文 [を手動で送信する必要があります](manually-submit-port-order.md)。 これらの番号は、管理センターのMicrosoft Teamsで行う必要があります。 詳細については、「[組織のために電話番号を管理する](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)」をご覧ください。

    移植する国と電話番号の種類に適切な承認状 (LOA) を使用することが重要です。 必要な [LOA は、 からダウンロードできます](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)。

- **携帯電話番号** には、移行を承認するための PIN コードが必要です。したがって、個別の番号移行要求が必要です。

- **サービス電話番号** の移行要求は、別に送信する必要があります。 他の種類の数値と一緒に送信できません。

## <a name="how-long-does-it-take-to-port-numbers"></a>番号の移行にはどれくらいかかりますか?
<a name="bkmk_type_1"> </a>

ポート注文要求が完了したら、処理に 7 ~ 14 日かかります。 ただし、サービス プロバイダーによっては、最大 30 日かかる場合があります。 電話番号が移植された後、お知らせするメールが届きます。
  
ポート注文の状態を確認するには、Microsoft Teams 管理センターの左側のナビゲーションで、[音声 電話 番号]に移動し、[注文履歴] を  >  **クリックします**。 各ポート注文の状態は、[状態] 列に **一覧表示** されます。
  
## <a name="can-user-subscriber-phone-numbers-be-converted-to-service-numbers"></a>ユーザー (加入者番号) の電話番号をサービス番号に変更できますか?
<a name="bkmk_type_1"> </a>

はい、できます。 変換したい組織のテナント GUID と電話番号を含んでいるサービス要求を送信するだけです。 これを行うには、「組織の [電話番号を管理する」を参照してください](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)。

## <a name="can-i-port-out-my-numbers-from-teams-to-a-different-phone-service-provider-or-carrier"></a>電話番号を別の電話サービス プロバイダー Teams携帯電話会社に移植できますか?

電話番号を別の運送業者にTeamsするには、新しい運送業者に要求を送信する必要があります。 また、管理センターでポート PIN を設定Microsoft Teams必要があります。

移植 PIN を定義するには、Microsoft Teams 管理センターの左側のナビゲーションで、ページの右上隅にある [音声 電話 番号] に移動し、[移植 PIN の管理] を選択し  >  、10 桁の PINを入力します。

新しい運送業者から移植要求を受け取った場合は、定義した PIN の入力を求めるメッセージが表示されます。

## <a name="common-mistakes-to-watch-out-for"></a>注意すべきよくあるミス
<a name="bkmk_type_1"> </a>

番号の移行は簡単です。 ただし、電話サービス プロバイダーに問題がある場合、注文が不完全で情報が不足している場合、または入力ミスがある場合は、注文が乱れる可能性があります。
  
お客様が番号を移行される場合に最もよくあるミスを以下に示します。カスタマー サポートに問い合わせずにすむように、これらのミスについて慎重に確認してください。
  
- 入力したアカウント情報が電話会社に登録されている内容と正確に一致することを確認してください。これらの情報の不一致が、番号移行注文のエラーや遅延の最も一般的な原因です。以下の情報が正しいことを確認してください。

  - アカウントに変更を加える権限を持つ名前またはユーザーが正しい。

  - 住所があっている。

  - アカウント番号が正しい。

  - BTN が正しい。

- これらの電話番号で有効になっている高度な通話制御機能 (通話の呼び出し、独特の呼び出しなど) が表示されません。

- 現在のサービス プロバイダーとの新しいサービス オーダーの発注またはサービスの解除の発注を行っていないことを確認してください。

- すべての電話番号が、同じ携帯電話会社および同じアカウントのものであること。

- サービスが有効になっていることを確認してください。 アカウントを凍結すると、アカウント上で携帯電話会社を変更できません。 アカウントを変更する権限を持つユーザーは、凍結を削除するために、現在の運送業者に注文を送信する必要があります。 このプロセスは、運送業者によっては 1 ~ 3 週間かかる場合があります。

## <a name="related-topics"></a>関連トピック

- [番号移行注文の状況](port-order-status.md)
- [通話プランで使用されるさまざまな種類の電話番号](../different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [組織の電話番号を管理する](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)
- [緊急通話の利用条件](../emergency-calling-terms-and-conditions.md)
- [緊急通話の免責事項ラベル](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)
