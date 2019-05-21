---
title: 電話番号の移行に関するよくある質問
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: 28cbf7d7-97f3-4a99-aa76-897022c14a24
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
f1keywords: None
ms.custom:
- Calling Plans
description: 次に、Skype for Business への電話番号の移行についてよく寄せられる質問を示します。 回答を確認したら、ポート注文を作成して電話番号を転送する準備ができました。 手順については、「Office 365 に電話番号を転送する」を参照してください。
ms.openlocfilehash: 889a74a0648e7a7ae7f3e1b6e286fd368ff86d2c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34293880"
---
# <a name="transferring-phone-numbers-common-questions"></a>電話番号の移行に関するよくある質問

次に、Skype for Business への電話番号の移行についてよく寄せられる質問を示します。 回答を確認したら、ポート注文を作成して電話番号を転送する準備ができました。 手順については、「 [Office 365 に電話番号を転送する」を](transfer-phone-numbers-to-office-365.md)参照してください。
  
## <a name="what-countriesregions-support-number-porting"></a>番号の移行をサポートしている国/地域について

サポート対象のすべての国や地域で電話番号を移行することができますが、移行注文の申請を送信する方法は、移行元の電話番号の国または地域によって異なります。 [電話会議と通話プランでは、国と地域](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)でサポートされている国と地域のリストを確認できます。 

電話番号の移動や、Skype for Business 管理センターで使用できない電話番号の取得など、電話番号の管理タスクを実行する場合は、「[組織の電話番号を管理](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)する」を参照してください。
  
## <a name="what-numbers-can-be-transferred"></a>どの番号を移行できますか?

 **移行できます:**
  
一般に、サポートされているプロバイダーからの電話番号は、次を含めてすべて移行できます。
  
- 固定電話の番号です。
    
- 携帯電話やタブレットなどで使用されるモバイル デバイス電話番号。
    
    > [!NOTE]
    > 携帯電話番号の移行は米国とプエルトリコでのみ利用できます。 
  
- 有料電話番号。
    
- フリー ダイヤル電話番号。
    
    > [!NOTE]
    > UIFN (世界共通国際フリーダイヤル番号) はマイクロソフトに移すことができません。 
  
- 会議ブリッジや自動応答などで使用されるサービス電話番号。
    
- Fax 電話番号 (ただし Fax 送信に使用することはできません)。ユーザーに割り当てられる必要があります。
    
- Vonage や RingCentral などの電話会社からの VoIP 電話番号。
    
- Skype for Business ハイブリッド電話番号。 これらの番号を移行する場合は、にメールを送信する必要<ptn@microsoft.com>があります。
    
  **移行できません:**
  
> [!NOTE]
> 現時点では、VoIP 電話会社の電話番号を含む、サポートされている国/地域以外の電話番号や電話番号を移行することはできません。 サポートされる国/地域のリストを表示するには、「[電話会議と通話プランの国と地域の空き時間](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)情報」を参照してください。
  
- DSL 回線やブロードバンド インターネット接続などのデータ接続で使用される電話番号を移転することもできません。
    
- FAX 専用の電話番号。
    
    FAX に使用する既存の専用の番号がある場合は、これらの番号を Skype for Business に移行 *できます*  が FAX サービスは期待どおりには、動作しません。 **電話システム**、**国内通話プラン**、または**国際通話プラン**のライセンスをお持ちの場合でも、Skype for business のお客様は fax サービスを利用できません。
    
    電話番号を Skype for Business に移行する場合、この電話番号を FAX に使用するのではなく、組織のユーザーに割り当てることができます。
    
> [!NOTE]
> 現時点での英国 (UK) において、市外局番 0843、0844、0845、0870、0871、0872 の費用分担番号を含む、UK バーチャル番号の移行はサポートしません。 
  
## <a name="what-information-will-i-need-to-provide"></a>どんな情報を提供する必要がありますか?

現在ご利用の通信事業者のアカウント情報をすべて用意する必要があります。番号の移行を注文するために必要な情報は現在のサービス プロバイダーの最近の請求書に記載されています。また、アカウントに登録された名前や、移行したい番号も用意する必要があります。
  
## <a name="what-are-full-port-and-partial-port-transfers"></a>フルポート移行およびパーシャルポート移行とは何ですか?

電話番号を Office 365 に移行する場合、すべての番号を移行するか、一部の番号を移行するかを選択できます。
  
- **フルポート** これは、現在のサービス プロバイダーから Skype for Business Online にすべての番号を移行する場合です。 転送する電話番号を入力するように求められた場合は、お客さまの電話番号とその他のすべての電話番号をアカウントに*追加する必要があり*ます。
    
    たとえば、請求先の電話番号が *+ 1 425-555-1234*であり、25個の電話番号のすべてを移植する場合 (*+ 1 425-555-1235 ~ 1259*) とします。 下の手順に従って番号を移行する場合、次のように入力します: **+14255551234 - +14255551259** 。
    
- **パーシャルポート** これは、現在のサービス プロバイダーから Skype for Business Online に一部の番号を移行する場合です。同じ電話番号に結び付けられた一部を移行する場合、請求電話番号およびアカウントのその他すべての電話番号を ** *含めないでください* ** 。
    
    たとえば、請求先電話番号 (BTN) が *+ 1 425-555-1234*であり、25個の電話番号のうち5個のみを移植する (*+ 1 425-555-1235 ~ 1259*) とします。 下の手順に従って番号を移行する場合、次のように入力します: **+1 425 555 1235 - +1 425 555 1239** 。
    
## <a name="can-i-submit-a-single-number-porting-request-for-all-of-my-numbers-at-one-time"></a>すべての電話番号の移行を単一の要求で送信できますか?
<a name="bkmk_type_1"> </a>

移行する電話番号のそれぞれの電話会社と種類に対して個別の要求が必要です。
  
たとえば、次のそれぞれの種類の電話番号に対して、個別の番号移行要求を送信する必要があります。
  
- 加入者番号または地域番号とも呼ばれる市外通話番号
    
- 800、844、855、866、877、および 888 のような市外局番を含むフリーダイヤル番号
    
- 携帯電話番号
    
- Office 365 で電話会議に使用できるサービス番号。
    
次に、それぞれの種類の電話番号に対する番号移行要求の送信に関する詳しい情報を示します。
  
- 各携帯電話会社が提供する **電話番号** には、電話会社ごとに個別の移行要求が必要です。
    
- 800、844、855、866、877、888などの市外局番を含むフリー**ダイヤル番号**は、他の種類の電話番号の移植要求に含めることはできません。 この無料電話番号を移植するには、[カスタムサービスリクエストを手動で送信](/SkypeForBusiness/what-are-calling-plans-in-office-365/manually-submit-a-custom-service-request)する必要があります。Skype for Business 管理センターで送信することはできません。 「[組織の電話番号を管理](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)する」を参照してください。
    
    国や移行する電話番号の種類に対して適切な LOA を使用することが重要です。 必要な[承認状 (loa) をダウンロード](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)する必要がある loa をダウンロードできます。
    
- **携帯電話番号** には、移行を承認するための PIN コードが必要です。したがって、個別の番号移行要求が必要です。
    
- **サービス電話番号** の移行要求は、別に送信する必要があります。他の種類の電話番号と一緒に送信することはできません。
    
## <a name="how-long-does-it-take-to-port-numbers"></a>番号の移行にはどれくらいかかりますか?
<a name="bkmk_type_1"> </a>

番号移行注文の申請を完了すると、その申請が処理されるまでに 7 日から 14 日かかります。ただし、サービス プロバイダーによっては、最大 30 日かかる場合があります。電話番号が移行されたら、準備が完了したことを知らせる電子メールを受け取ります。
  
You can check the status of your port order by going to the Skype for Business admin center > **Voice** > **Port orders**. The status will be listed in the window under the **Status** column.
  
## <a name="can-user-subscriber-phone-numbers-be-converted-to-service-numbers"></a>ユーザー (加入者番号) の電話番号をサービス番号に変更できますか?
<a name="bkmk_type_1"> </a>

はい、できます。 変換したい組織のテナント GUID と電話番号を含んでいるサービス要求を送信するだけです。 この操作を行うには[、「組織の電話番号を管理](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)する」を参照してください。 
  
## <a name="common-mistakes-to-watch-out-for"></a>注意すべきよくあるミス
<a name="bkmk_type_1"> </a>

番号の移行は簡単です。ただし、電話サービス プロバイダーに問題がある場合、注文が不完全で情報が欠落している場合、入力ミスがある場合などには、注文が無効になる場合があります。
  
お客様が番号を移行される場合に最もよくあるミスを以下に示します。カスタマー サポートに問い合わせずにすむように、これらのミスについて慎重に確認してください。
  
- 入力したアカウント情報が電話会社に登録されている内容と正確に一致することを確認してください。これらの情報の不一致が、番号移行注文のエラーや遅延の最も一般的な原因です。以下の情報が正しいことを確認してください。
    
  - 認証された名前が正しい。
    
  - 住所があっている。
    
  - アカウント番号が正しい。
    
  - 請求書電話番号 (BTN) が正しい。
    
- 高度な通話管理機能 (Call Hunt、Distinctive Ring など) がこれらの電話番号で有効になっていないことを確認してください。
    
- 現在のサービス プロバイダーとの新しいサービス オーダーの発注またはサービスの解除の発注を行っていないことを確認してください。
    
- すべての電話番号が、同じ携帯電話会社および同じアカウントのものであること。
    
- サービスが有効になっていることを確認してください。アカウントを凍結すると、アカウント上で携帯電話会社を変更できません。認定ユーザーは、凍結を解除するために、現在の携帯電話会社に注文を送信する必要があります。このプロセスは、携帯電話会社によって異なりますが、1 週間から 3 週間かかる場合があります。
    
## <a name="can-you-transfer-or-port-out-numbers"></a>番号を移行したり、発信したりすることはできますか?
<a name="bkmk_type_1"> </a>

Skype for Business Online から別の電話サービスプロバイダーまたは通信事業者に電話番号を移行または*移植*するには、PIN を設定する必要があります。 PIN を設定した後、電話番号の移植を要求するときに、PIN を含める必要があります。PIN の設定方法については、「[新しいサービスプロバイダーに番号を転送するために pin を設定](/SkypeForBusiness/what-are-calling-plans-in-office-365/set-your-pin-for-transferring-numbers-to-a-new-service-provider)する」を参照してください。

> [!NOTE]
> さらに追加で電話番号が必要な場合は、「[一般法人向け Office 365 のサポートへのお問い合わせ - 管理者向けヘルプ](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)」をご覧ください。

  
## <a name="related-topics"></a>関連トピック

[通話プランで使用されるさまざまな種類の電話番号](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[緊急通話の利用条件](emergency-calling-terms-and-conditions.md)

[Skype for Business Online: 緊急通話の免責事項ラベル](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)
  
 
