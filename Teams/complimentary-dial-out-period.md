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
description: Microsoft Teams の Microsoft 365 または Office 365 通話プランと Office 365 電話会議の無料のダイヤルアウト期間について説明します。
ms.openlocfilehash: 0f40e35e30de5698ffcb4bf9592868685d8223ed
ms.sourcegitcommit: 212b2985591ca1109eb3643fbb49d8b18ab07a70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/21/2021
ms.locfileid: "49918883"
---
# <a name="audio-conferencing-complimentary-dial-out-period"></a>音声会議の無料ダイヤル アウト期間

## <a name="skype-for-business-pstn-services"></a>Skype for Business PSTN サービス

お客様は、Skype for Business Online PSTN サービス使用条件およびお客様のボリューム ライセンス契約で許可されている Microsoft 365 または Office 365 通話プランおよび Office 365 電話会議を使用できます。 PSTN サービスの使用条件については、ライセンス条項 [とドキュメントを参照してください](http://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=2&amp;Keyword=PSTN)。
  
### <a name="end-of-complimentary-dial-out-period"></a>無料のダイヤルアウト期間の終了

無料のダイヤルアウト機能は、2019 年 12 月 1 日に終了しました。 詳細については、「電話会議サブスクリプションをダイヤルアウトして、特典を受 [ける」を参照してください](audio-conferencing-subscription-dial-out.md)。 

この変更は、電話会議サブスクリプションが利用可能な国では行われなかったが、現在通信クレジットの設定は有効にしていない。 これらの特定の国は、ロシア、韓国、台湾です。

### <a name="complimentary-dial-out-period-details"></a>無料のダイヤルアウト期間の詳細

Microsoft 365 または Office 365 電話会議サービスを導入しているお客様のために、Microsoft は、2019 年 11 月まで Microsoft 365 または Office 365 電話会議サブスクリプション ライセンスが割り当てられたユーザーによって開催される会議からのダイヤルアウトに関連する追加の無料の特典を提供しています。 この無料期間中、Microsoft では、会議の開催者または承認された出席者が、会議ポリシーの設定で定義されている方法で、会議内から 44 ゾーン [A](audio-conferencing-zones.md)の国と地域のプレミアム以外の電話番号にダイヤルアウト通話を発信できます。 この特典は電話会議の月次サブスクリプション ライセンスに適用され、電話会議の分単位支払いライセンスには適用しません。

さらに、次のような無料のダイヤルアウト期間中は、900 分の制限があります。

ライセンスの使用場所 (場所は、Microsoft 365 管理センターのライセンス領域で定義されているユーザーの国の場所) を持つユーザーは、会議から 44 ゾーン[A](audio-conferencing-zones.md)の国と地域にダイヤルアウトできます。 各ユーザーは、テナント レベルでプールされているゾーン[A](audio-conferencing-zones.md)の国と地域に対して、ユーザーごとに毎月 900 分を受け取ります。  たとえば、お客様は 115 の電話会議サブスクリプション ライセンスを購入し、米国では 10 ユーザー、英国では 100 ユーザー、インドでは 5 人のユーザーを持ち、すべてユーザーに電話会議サブスクリプション ライセンスが割り当て済みです。

- 115 人のユーザー全員が、(115 ユーザー X 900 分) = 103,500 分の会議ダイヤルアウト 分を予定表月ごとに共有します。これは、ゾーン [A](audio-conferencing-zones.md)の国と地域に発信通話を発信するために使用できます。

- 1 か月あたり 103,500 分を超える通話はすべて、その宛先に公開されている料金で通信クレジットを使用して、分単位で請求されます。 (注: テナントはコミュニケーション クレジットを設定し、コミュニケーション クレジットのライセンスを会議開催者に割り当てる必要があります)。

- ゾーン [A](audio-conferencing-zones.md) の国と地域の一覧に含られていない発信通話はすべて、その発信先に公開されている料金で通信クレジットを使用して分単位で請求されます (指定されたテナントが通信クレジットを設定し、通信クレジット のライセンスを会議開催者に割り当てている場合)。

> [!NOTE]
> Skype for Business 管理センターでは、ダイヤルアウトミニト プールに対して使用状況を監視できます。 Microsoft Teams & Skype 管理センターで、[従来 **のポータル** レポート] PSTN ミニサイト プール  >    >  **に移動します**。 この無料の分プールは、レポートで "ゾーン A の国と地域への発信通話" としてラベル付けされます。

テナントのダイヤルアウト時間プールの使用率が 80% と 100% に達すると、指定した顧客のすべてのテナント管理者にメール通知が送信されます。

1 分あたりのダイヤルアウト通話 (テナントのダイヤルアウト分プールを超える通話、またはゾーン [A](audio-conferencing-zones.md) の国と地域の一覧ではない発信先への通話) の場合、通話と関連レートは、開催者または参加者がダイヤルアウト通話を開始する国や地域ではなく、通話の発信先に基づいて行います。 たとえば、フランスの電話番号への通話は、米国の会議参加者またはフランスの会議参加者が開始した場合と同じ料金で請求されます。

通信クレジットの詳細については、「コミュニケーション クレジット」 [を参照してください](what-are-communications-credits.md)。
     
## <a name="related-topics"></a>関連項目

- [国および地域ごとの電話会議および通話プランの利用可能性](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
- [電話会議の国と地域のゾーン](audio-conferencing-zones.md)
