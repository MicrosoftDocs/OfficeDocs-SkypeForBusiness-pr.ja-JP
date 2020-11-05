---
title: 無料のダイヤルアウト期間
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, OscarR
ms.topic: conceptual
ms.assetid: dc6e95cd-51e8-49ca-bcd3-78dc9dae486a
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-collaboration
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: None
f1.keywords:
- CSH
ms.custom:
- Legal
- seo-marvel-mar2020
description: Microsoft Teams の Microsoft 365 または Office 365 の通話プランと Office 365 電話会議の無料のダイヤルアウト期間について説明します。
ms.openlocfilehash: 112283bc971c1dbfd3ddd4a7baefa02eba693179
ms.sourcegitcommit: ee217e1d7188842c7becd19387fd421b485c3575
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/04/2020
ms.locfileid: "48908506"
---
# <a name="audio-conferencing-complimentary-dial-out-period"></a>音声会議の無料ダイヤル アウト期間

## <a name="skype-for-business-pstn-services"></a>Skype for Business PSTN サービス

お客様は、Skype for Business Online PSTN サービスの使用条件およびお客様のボリュームライセンス契約に従って、Microsoft 365 または Office 365 通話プランおよび Office 365 電話会議を使用できます。 PSTN サービスの使用条件は、 [ライセンス条項とドキュメント](http://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=2&amp;Keyword=PSTN)に記載されています。
  
### <a name="end-of-complimentary-dial-out-period"></a>無料のダイヤルアウト期間の終了

2019年12月1日から、無料ダイヤルアウト機能が終了します。 詳細については、「電話 [会議サブスクリプションのダイヤルアウトと通話に](audio-conferencing-subscription-dial-out.md) ついて」を参照してください。 

この変更は、電話会議の月額プランが利用可能な国では利用できませんが、現在通信クレジットを設定する機能は提供していません。 これらの特定の国はロシア、韓国、台湾です。

### <a name="complimentary-dial-out-period-details"></a>無料のダイヤルアウト期間の詳細

Microsoft 365 または Office 365 電話会議サービスをご2019利用のお客様の場合、microsoft は、Microsoft 365 または Office 365 電話会議のサブスクリプションライセンスを割り当てられたユーザーによって開催された会議からのダイヤルアウトに関連する追加の無料特典を提供します。 この無料期間中、Microsoft は会議のポリシー設定で定義されている会議の開催者または許可された出席者を許可し、その会議内からのダイヤルアウト通話を、44 Zone の有料以外の電話番号に  [国と地域](audio-conferencing-zones.md)で許可します。 この特典は、電話会議の月額プランライセンスに適用され、電話会議の1分あたりのライセンス数に延長されることはありません。

さらに、次のように、無料のダイヤルアウト期間中に900分の cap 制限があります。

ライセンス利用場所 (Microsoft 365 管理センターの [ライセンス] 領域で定義されたユーザーの国の場所) を持つユーザーは、どの国でも、会議からいずれかの 44 [ゾーン](audio-conferencing-zones.md)にダイヤルアウトすることができます。 各900ユーザーは、各ユーザーに対して、1か月あたり1人のユーザーに対して、テナントレベルでプールされている [国と地域](audio-conferencing-zones.md) を指定します。 たとえば、お客様は115の電話会議のライセンスを購入していて、100米国内のユーザーに対して10人のユーザーがいる場合、そのユーザーに割り当てられた電話会議のサブスクリプションライセンスを使用している場合があります。

> [!NOTE]
> プールサイズは、割り当て済みのライセンスに基づき、購入したライセンスはありません。
 
- すべての115ユーザーは、(115 ユーザー X 900 分) のプールを共有します。1ヶ月あたりの103500会議ダイヤルアウト分は、 [国と地域](audio-conferencing-zones.md)のいずれかに対して発信通話を発信するために使用できます。
- 1ヶ月あたり103500分を超えた通話はすべて、その送信先への公開料金で通信クレジットを使って分単位で課金されます。 (注: テナントは通信クレジットを設定し、会議の開催者に通信クレジットのライセンスを割り当てる必要があります)。
- ゾーンにない宛先へのすべての発信通話 [国と地域の](audio-conferencing-zones.md) リストは、その送信先への公開料金で通信クレジットを使用して請求されます (指定したテナントでは通信クレジットが設定され、会議の開催者には通信クレジットライセンスが割り当てられています)。

> [!NOTE]
> Skype for Business 管理センターでは、ダイヤルアウトの分プールに対する使用状況を監視できます。 Microsoft Teams & Skype 管理センターで、 **従来のポータル**  >  **レポート**  >  **PSTN 分プール** に移動します。 この無料の分数のプールには、"国と地域を対象とした発信通話" として報告されます。

テナントのダイヤルアウト分数プールの使用率が80% と100% に達した場合、メール通知は、特定の顧客のすべてのテナント管理者に送信されます。

1分あたりのダイヤルアウト通話 (テナントのダイヤルアウト分プールを超えているか、または [国と地域](audio-conferencing-zones.md) の一覧にない宛先への呼び出し) の場合、通話とその関連料金は主に通話の発信先に基づき、発信者の国または地域ではなく、ダイヤルアウト通話を開始します。 たとえば、フランスの電話番号への通話は、米国内の会議出席者によって開始された場合も、フランスの場合も、同じ料金で課金されます。

通信クレジットの詳細については、「 [通信クレジット](what-are-communications-credits.md)」を参照してください。
     
## <a name="related-topics"></a>関連項目

- [国および地域ごとの電話会議および通話プランの利用可能性](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
- [電話会議の国と地域のゾーン](audio-conferencing-zones.md)
