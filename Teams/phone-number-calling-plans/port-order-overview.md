---
title: 番号移行注文について
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.voice.phonenumbers.porting.overview
- Calling Plans
description: ポート注文の概要と、サービス プロバイダーから Teams に電話番号を転送する方法について説明します。
ms.collection:
- M365-voice
- m365initiative-voice
- highpri
ms.openlocfilehash: f4160d8e5fac5ec1f706bb7c82a881248d092a59
ms.sourcegitcommit: cbcf37f395832bed871fe709b87c6eecb1fdfd72
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2022
ms.locfileid: "68584918"
---
# <a name="whats-a-port-order"></a>番号移行注文について

現在、電話サービス プロバイダーまたは通信事業者があり、ユーザーまたはサービスの電話番号が既にある場合は、Microsoft Teams に電話番号を転送するための "*ポート 注文*" を作成する必要があります。 番号を移植すると、電話会議 (会議ブリッジの場合)、自動応答、通話キューなどのユーザーやサービスにこれらの電話番号を割り当てることができます。
  
Teams に電話番号を移植すると、Microsoft がサービス プロバイダーになり、古いサービス プロバイダーまたは通信事業者とサービスを切断できます。

この記事の情報を確認して、番号の移植について理解してください。 その後、ポート注文を作成し、電話番号を転送する準備が整う必要があります。 詳細な手順については、「 [Teams に電話番号を転送](transfer-phone-numbers-to-teams.md) する」を参照してください。
  
## <a name="what-countries-or-regions-support-number-porting"></a>番号の移植をサポートする国または地域は何ですか?

サポートされているすべての国または地域で電話番号を移植または転送できますが、ポート注文要求を送信する方法は、電話番号の発信元の国または地域によって異なります。 番号の移植をサポートする国と地域の一覧については、「 [組織の電話番号を管理する」を参照してください](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)。  

現在、Microsoft Teams 管理センターの[移植ウィザード](transfer-phone-numbers-to-teams.md)では、英国、米国、カナダの電話番号の取得がサポートされています。 他の国と地域の電話番号を取得するには、 [ポート注文を手動で送信](manually-submit-port-order.md)できます。
  
## <a name="what-numbers-can-be-transferred"></a>どの番号を移行できますか?

 **転送できます**
  
一般に、次のような、サポートされているプロバイダーから任意の電話番号を転送できます。
  
- 固定電話の番号です。

- 携帯電話やタブレットに使用されるものなど、モバイル デバイスの電話番号。

    > [!NOTE]
    > 携帯電話番号の転送は、米国とプエルトリコでのみ使用できます。
  
- 有料電話番号。

- フリー ダイヤル電話番号。

    > [!NOTE]
    > UIFN (世界共通国際フリーダイヤル番号) はマイクロソフトに移すことができません。
    > 無料電話番号の移植の可用性は、国と地域によって異なる場合があります。 詳細については、お客様の国または地域固有のドキュメントを参照して、移植サービスのサポートを参照してください。 
  
- 会議ブリッジや自動応答などで使用されるサービス電話番号。

- Fax 電話番号 (ただし Fax 送信に使用することはできません)。 ユーザーに割り当てる必要があります。

- Vonage や RingCentral などの電話会社からの VoIP 電話番号。

- ハイブリッド電話番号を移植する場合 (ダイレクト ルーティングまたはオペレーター接続から通話プランに移行する場合) は、 [電話番号サービス チーム](../manage-phone-numbers-for-your-organization/contact-tns-service-desk.md)にお問い合わせください。ハイブリッド電話番号であることを示すメモが含まれていることを確認してください。

**次を転送することはできません。**
  
> [!NOTE]
> 現時点では、VoIP 電話プロバイダーの電話番号を含め、サポートされている国または地域からではない電話番号または電話番号を転送することはできません。 サポートされている国/地域の一覧については、「[電話会議と通話プランの国と地域の可用性](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)」を参照してください。
  
- DSL 回線やブロードバンド インターネット接続などのデータ接続で使用される電話番号を移転することもできません。

- FAX 専用の電話番号。

    FAX に使用されている専用電話番号が既にある場合は、Teams にこれらの番号を転送  *できますが*  、FAX サービスは引き続き期待どおりに機能しません。 電話システム、国内通話プラン、または国際通話プランのライセンスをお持ちであっても、Teams のお客様は FAX サービスを利用できません。

    Teams に電話番号を移植する場合は、FAX に使用する代わりに、組織内のユーザーにこの電話番号を割り当てることができます。

> [!NOTE]
> 現時点では、英国では現在、地域コード 0843、0844、0845、0870、0871、0872 の共有コスト番号を含む英国以外の番号の転送はサポートされていません。
  
## <a name="what-information-do-i-need-to-provide"></a>どのような情報を提供する必要がありますか?

現在の運送業者のすべてのアカウント情報が必要です。 ポートの順序で入力した情報は、ほとんどの場合、現在のサービス プロバイダーからの最新の請求書または請求書に記載されています。 また、アカウントに含まれる名前と、移植する番号も知る必要があります。
  
## <a name="what-are-full-port-and-partial-port-transfers"></a>フルポート移行およびパーシャルポート移行とは何ですか?

Teams に電話番号を移植する場合は、すべての電話番号またはその一部を転送できます。
  
- **フルポート** これは、現在のサービス プロバイダーから Teams にすべての番号を転送する場合です。 転送する電話番号を求められたら、課金電話番号 (BTN) とアカウントの他のすべての電話番号を *含める必要があります* 。

    たとえば、BTN が  *+1 425-555-1234 で、25*  個の電話番号 (*+1 425-555-1235 ~ 1259*) をすべて移植するとします。 下の手順に従って番号を移行する場合、次のように入力します: **+14255551234 - +14255551259** 。

- **部分ポート** これは、現在のサービス プロバイダーから Teams に電話番号の一部のみを転送する場合です。 同じ BTN に関連付けられている電話番号の一部を移植する場合は、**アカウントの他のすべての電話番号と共に **BTN を *含めてはなりません* 。

    たとえば、BTN が  *+1 425-555-1234 で、25*  の電話番号のうち 5 つだけを移植するとします (*+1 425-555-1235 ~ 1259*)。 下の手順に従って番号を移行する場合、次のように入力します: **+1 425 555 1235 - +1 425 555 1239** 。
    
## <a name="can-i-submit-a-single-number-porting-request-for-all-of-my-numbers-at-one-time"></a>すべての電話番号の移行を単一の要求で送信できますか?
<a name="bkmk_type_1"> </a>

移行する電話番号のそれぞれの電話会社と種類に対して個別の要求が必要です。
  
たとえば、次のそれぞれの種類の電話番号に対して、個別の番号移行要求を送信する必要があります。
  
- ローカルの有料電話番号 (サブスクライバー番号または地理的な番号とも呼ばれます)

- 800、844、855、866、877、および 888 のような市外局番を含むフリーダイヤル番号

- 携帯電話番号

- Microsoft 365 またはOffice 365の電話会議に使用できるサービス番号。

これらの種類の番号ごとに番号の移植要求を送信する方法の詳細を次に示します。
  
- 異なる通信事業者によって提供される **電話番号** には、各通信事業者の番号に対する一意の移植要求が必要です。

- 市外局番が 800、844、855、866、877、888 などの **フリーダイヤル** 番号は、他の種類の番号と共に番号の移植要求に含めることはできません。 これらの無料電話番号を移植するには、 [ポート注文を手動で送信する](manually-submit-port-order.md)必要があります。 Microsoft Teams 管理センターでこれらの番号を移植することはできません。 詳細については、「[組織のために電話番号を管理する](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)」をご覧ください。

    移植する国と電話番号の種類には、正しい承認文字 (LOA) を使用することが重要です。 [ここで必要な LOA をダウンロード](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)できます。

- **携帯電話番号** には、移行を承認するための PIN コードが必要です。 したがって、個別の番号移行要求が必要です。

- **サービス電話番号** の移行要求は、別に送信する必要があります。 他の種類の番号で送信することはできません。

## <a name="how-long-does-it-take-to-port-numbers"></a>番号の移行にはどれくらいかかりますか?
<a name="bkmk_type_1"> </a>

ポート注文要求を完了すると、処理に 7 ~ 14 日かかります。 ただし、サービス プロバイダーによっては、最大 30 日かかる場合があります。 電話番号を移植すると、お客様が適切であることをお知らせするメールが送信されます。
  
ポート注文の状態を確認するには、Microsoft Teams 管理センターの左側のナビゲーションで **音声** > **電話番号** に移動し、[ **注文履歴**] をクリックします。 各ポートの順序の状態が [ **状態]** 列に一覧表示されます。
  
## <a name="can-user-subscriber-phone-numbers-be-converted-to-service-numbers"></a>ユーザー (加入者番号) の電話番号をサービス番号に変更できますか?
<a name="bkmk_type_1"> </a>

はい。可能です。 これを行うには、「 [電話番号の使用状況を管理する](../manage-the-usage-of-a-phone-number.md)」を参照してください。

## <a name="can-i-port-out-my-numbers-from-teams-to-a-different-phone-service-provider-or-carrier"></a>Teams から別の電話サービス プロバイダーまたは通信事業者に番号を移植できますか?

Teams から別の通信事業者に番号を移植するには、新しい通信事業者に要求を送信する必要があります。 また、Microsoft Teams 管理センターで移植 PIN を設定する必要もあります。

移植 PIN を定義するには、Microsoft Teams 管理センターの左側のナビゲーションで、 **音声** > **電話番号** に移動し、ページの右上隅にある [ **移植 PIN の管理**] を選択し、10 桁の PIN を入力します。

新しい運送業者から移植要求を受け取った場合は、お客様が定義した PIN を提供するようお願いします。

PIN を設定する必要がある場合は、[電話番号サービス チーム](../manage-phone-numbers-for-your-organization/contact-tns-service-desk.md)にお問い合わせください

## <a name="common-mistakes-to-watch-out-for"></a>注意すべきよくあるミス
<a name="bkmk_type_1"> </a>

番号の移行は簡単です。 ただし、電話サービス プロバイダーに問題がある場合、注文が不完全で情報が不足しているか、入力ミスがある場合は、注文が混乱する可能性があります。
  
Here are the most common mistakes we see customers make when they port numbers. Save yourself a call to customer support and double-check for these errors.
  
- Make sure the account information you give matches exactly what your phone carrier has on record. Mismatched information is the most common cause of errors and delay your port order. Verify the following is true:

  - アカウントに変更を加える権限を持つ名前または人物が正しい。

  - 住所があっている。

  - アカウント番号が正しい。

  - BTN は正しいです。

- これらの電話番号で有効になっている高度な通話制御機能 (Call Hunt、Distinctive Ring など) がないことを確認します。

- 現在のサービス プロバイダーとの新しいサービス オーダーの発注またはサービスの解除の発注を行っていないことを確認してください。

- すべての電話番号が、同じ携帯電話会社および同じアカウントのものであること。

- サービスが有効になっていることを確認してください。 アカウントを凍結すると、アカウント上で携帯電話会社を変更できません。 アカウントに変更を加える権限を持つユーザーは、凍結を削除するために現在の運送業者に注文を送信する必要があります。 このプロセスは、運送業者によっては 1 ~ 3 週間かかる場合があります。

## <a name="related-topics"></a>関連項目

- [番号移行注文の状況](port-order-status.md)
- [通話プランで使用されるさまざまな種類の電話番号](../different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [組織の電話番号を管理する](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)
- [緊急通話の利用条件](../emergency-calling-terms-and-conditions.md)
- [緊急通話の免責事項ラベル](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)
