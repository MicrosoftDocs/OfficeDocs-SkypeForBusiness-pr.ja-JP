---
title: 無料のダイヤルアウト期間
ms.author: heidip
author: MicrosoftHeidi
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
- Microsoft Teams
ms.localizationpriority: ''
f1.keywords:
- CSH
ms.custom:
- Legal
- seo-marvel-mar2020
description: Microsoft Teams での Microsoft 365 通話プランと電話会議の無料ダイヤルアウト期間について説明します。
ms.openlocfilehash: 72ec36eb99a4a0eb2358195a52db00b26bb591e5
ms.sourcegitcommit: 5abfb6f1abe10b6d32cf6eb97a890cf3138ed0e6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2022
ms.locfileid: "67641898"
---
# <a name="audio-conferencing-complimentary-dial-out-period"></a>音声会議の無料ダイヤル アウト期間

## <a name="teams-pstn-services"></a>Teams PSTN サービス

お客様は、Teams PSTN サービス使用条件および顧客のボリューム ライセンス契約で許可されているとおり、Microsoft 365 または通話プランと Teams 電話会議を使用できます。 PSTN サービス使用条件は、 [ライセンス のリソースとドキュメントに記載されています](https://www.microsoft.com/licensing/docs)。

### <a name="end-of-complimentary-dial-out-period"></a>無料ダイヤルアウト期間の終了

無料のダイヤルアウト機能は、2019 年 12 月 1 日に終了しました。 詳細については、「 [電話会議サブスクリプションをダイヤルアウトして、特典を受けて電話をかける](audio-conferencing-subscription-dial-out.md)」を参照してください。

この変更は、電話会議サブスクリプションが利用可能な国では行われませんでしたが、現在、通信クレジットの設定は有効にしていません。 これらの特定の国は、ロシア、韓国、台湾です。

### <a name="complimentary-dial-out-period-details"></a>無料ダイヤルアウト期間の詳細

Microsoft 365 電話会議サービスを導入しているお客様に対して、Microsoft は、2019 年 11 月までの Microsoft 365 電話会議サブスクリプション ライセンスを割り当てられたユーザーが開催する会議からのダイヤルアウトに関連する追加の無料特典を提供しています。 この無料期間中、Microsoft では、会議ポリシー設定で定義されている会議の開催者または承認された出席者が、会議内から 44 [ゾーン A の国と地域](audio-conferencing-zones.md)の非プレミアム電話番号にダイヤルアウト通話を行うことができます。 この特典は、電話会議の月次サブスクリプション ライセンスに適用され、電話会議の分単位の有料ライセンスには適用されません。

さらに、無料のダイヤルアウト期間中は、次のように 900 分の制限があります。

任意の国のライセンス使用場所 (場所は、Microsoft 365 管理センターのライセンス _領域で定義_ されているユーザーの国の場所) を持つユーザーは、会議から 44 [ゾーン A の国と地域](audio-conferencing-zones.md)のいずれかにダイヤルアウトできます。 各ユーザーは、テナント レベルでプールされている [ゾーン A の国と地域](audio-conferencing-zones.md)_に_ 対して、1 人あたり 1 か月あたり 900 分を受け取ります。 たとえば、顧客は 115 個の電話会議サブスクリプション ライセンスを購入し、米国では 10 人、英国では 100 人、インドでは 5 人のユーザーを所有しており、すべて電話会議サブスクリプション ライセンスがユーザーに割り当てられます。

- 115 人のユーザー全員が 、(115 ユーザー X 900 分) = 103,500 会議のダイヤルアウト分 (カレンダー月あたり) のプールを共有します。これは、 [ゾーン A の国と地域](audio-conferencing-zones.md)に発信通話を発信するために使用できます。

- 1 暦月あたり 103,500 分を超えるすべての通話は、その宛先に対して発行された料金で通信クレジットを使用して 1 分あたり課金されます。 (注: テナントは、通信クレジットを設定し、会議の開催者に通信クレジット ライセンスを割り当てる必要があります)。

- [ゾーン A の国と地域](audio-conferencing-zones.md)リストにない宛先への発信通話はすべて、その宛先に対して発行された料金で通信クレジットを使用して 1 分あたり課金されます (テナントが通信クレジットを設定し、会議の開催者に通信クレジット ライセンスを割り当てた場合)。

> [!NOTE]
> Teams 管理センターでは、ダイヤルアウト分プールに対する使用状況を監視できます。 Microsoft Teams 管理センターで、 **レガシ ポータル** > **レポート** > **PSTN 分プール** に移動します。 この無料の分プールは、レポートに "ゾーン A の国と地域への発信通話" というラベルが付けられます。

Email通知は、テナントのダイヤルアウト分プールの使用率が 80% と 100% に達すると、特定の顧客のすべてのテナント管理者に送信されます。

1 分あたりに課金されるダイヤルアウト通話 (テナント ダイヤルアウト分プールを超える通話、または [ゾーン A の国と地域](audio-conferencing-zones.md) の一覧にない宛先への通話) の場合、通話とそれに関連する料金は、主に通話の宛先に基づいており、開催者の国や地域、ダイヤルアウト通話を開始する参加者には基づいていません。 たとえば、フランスの電話番号への通話は、米国またはフランスの会議参加者によって開始された場合、同じ料金で課金されます。

コミュニケーション クレジットの詳細については、「 [コミュニケーション クレジット](what-are-communications-credits.md)」を参照してください。

## <a name="related-topics"></a>関連項目

- [国および地域ごとの電話会議および通話プランの利用可能性](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
- [電話会議の国と地域のゾーン](audio-conferencing-zones.md)
