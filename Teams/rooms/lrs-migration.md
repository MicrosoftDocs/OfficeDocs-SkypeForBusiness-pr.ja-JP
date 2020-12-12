---
title: Lync Room システムデバイスを Microsoft Teams Rooms に移行する
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.assetid: ''
description: このトピックでは、 Lync Room システムデバイスを移行して、Microsoft Teams Rooms のソフトウェアを使用する方法について説明します。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: d8da14f2d5f3ec75c6a9fb9c03a33d7e83cd1aed
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662622"
---
# <a name="migrate-lync-room-system-lrs-devices-to-microsoft-teams-rooms"></a>Microsoft Teams Rooms にLync Room System (LRS) デバイスを移行する

Skype Room System バージョン1 (SRS v1) ソフトウェアを搭載した Lync Room System (LRS) デバイスは、[2018年10月9日にサポートが終了しました](https://support.microsoft.com/help/4043450/products-reaching-end-of-support-for-2018)。 これは、Skype ミーティング システム V1 ソフトウェアがもはや製品の更新プログラムや修正を取得しなくなることを意味します。 Skype ミーティング システム V1 ソフトウェアを使用している Lync Room System デバイスをお持ちのお客様には、デバイスを Microsoft Teams Rooms にアップグレードすることをお勧めします。

Microsoft Teams Rooms のソフトウェアは、Skype for Business Server、会議のためのオンラインサービス、Microsoft Teams Rooms にサポートされたデバイスと同じく、Microsoft Teamsと連携します。

Skype 会議システムv1のソフトウェアサポートが終了しても、既存のデバイス が引き続き動作する **かもしれません**。 ただし、このソフトウェアにMicrosoft の修正プログラムのリリースが必要とされるソフトウェアバグが発見された場合は、サポートされません。 SRS v1 は、今後 Microsoft によって廃止される予定の TLS 1.0/1.1 を使用します。 [TLS 1.0/1.1 の廃止を準備する](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Preparing-for-TLS-1-0-1-1-Deprecation-O365-Skype-for-Business/bc-p/223608) について参照してください。 

## <a name="which-devices-are-affected"></a>どのデバイスが影響を受けますか?

この変更の影響を受けるデバイスを次に示します。

- Crestron SR
- [Crestron RL2](https://www.crestron.com/Products/Featured-Solutions/Crestron-RL-2)
- [SMART Roomシステム](https://support.smarttech.com/en/hardware/room-systems-skype)
- [Polycom CX8000](https://www.polycom.com/products-services/products-for-microsoft/skype-for-business/cx8000.html)

## <a name="upgrade-options"></a>アップグレード方法

Microsoft Teams Rooms の次世代に、Lync Room システムをアップグレードする方法は複数あります。

### <a name="crestron-hardware-trade-in-program"></a>Crestronハードウェアの下取りプログラム

Crestronは、 [Crestron SR システム](https://www.crestron.com/products/featured-solutions/crestron-sr)へアップグレードします。 または、非Crestron Lync Room Systemのお客様(例：SmartまたはPolycom LRS)に対しては、同等のアップグレードを提供します。 このプログラムの詳細については、[こちら](https://support.crestron.com/app/answers/answer_view/a_id/1000220)をご覧 ください。または、 <!-- For details, -->[メール](mailto:lrsupgrade@crestron.com) Creon LRS サポート。  

### <a name="crestron-rl2-upgrade-to-microsoft-teams-rooms"></a>Crestron RL2 を Microsoft Teams Rooms にアップグレードします。

既存の Crestron RL2 (Crestron RL200 とも呼ばれます)の お客様は、デバイスあたりのコストを最小限に抑えるために、現在の RL2をRL3にアップグレードするためのアップグレードキットを 入手できます。 このプログラムの詳細については、[こちら](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-RL-2/CCS-UC-250-KIT)をご覧ください。

### <a name="smart-room-systems-upgrade"></a>SMART Roomシステムアップグレード

SMART LRS のお客様のために、Crestron hardware の下取りプログラムとは別に、Microsoft Teams Rooms にアップグレードするためのソリューションをSMARTは提供しています。 このアップグレードは、製品サポートの対象のお客様に対して、SMART Technologies Inc. が提供します。 詳細については、[こちら](https://support.smarttech.com/docs/hardware/room-systems-skype/srs-skype-v2/en/about/default.cshtml)を参照してください。


## <a name="what-should-you-do"></a>どうすればよいですか?

以前に説明したアップグレードオプションを使用して、TLS 1.0/1.1 が廃止される前に、Lync Room Systemデバイスを Microsoft Teams Rooms に更新することをお勧めします。 また、既存のデバイスを、Microsoft Teams Rooms 用の新しい承認済デバイスに置き換えることもできます。 詳細については、「[ミーティングの デバイス](https://aka.ms/roomdevices) 」を参照してください。また、「[Microsoft Teams Rooms の要件](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/requirements)」 を参照してください。  


> [!NOTE]
> Microsoft Teams Rooms のソフトウェアは、アプリバージョン4.0.64.0 を使用して2018年12月14日に TLS 1.2 プロトコルをサポートしています。 オンプレミスのお客様の場合は、Microsoft Teams Rooms の TLS 1.2 経由の通信を有効にするには、Skype for Business Server 2015 累積更新プログラム 9 (CU9) または Skype for Business Server 2019 累積更新プログラム 1 (CU1) が必要です。 クライアントの変更は、前方および後方準拠として行われるため、変更は Skype for Business Online の顧客には影響しません。
