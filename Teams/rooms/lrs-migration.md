---
title: Lync Room システムデバイスを Microsoft Teams ルームに移行する
ms.author: v-lanac
author: lanachin
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
description: このトピックでは、Lync Room System デバイスを移行して Microsoft Teams のルームソフトウェアを使用する方法について説明します。
ms.openlocfilehash: 4f0c255c40c64274ff4b104a8706eb8f73ee792f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42155109"
---
# <a name="migrate-lync-room-system-lrs-devices-to-microsoft-teams-rooms"></a>Lync Room System (LRS) デバイスを Microsoft Teams ルームに移行する

Skype Room System バージョン 1 (SRS v1) ソフトウェアが搭載された Lync Room System (LRS) デバイスは[、2018年10月9日にサポート終了に](https://support.microsoft.com/help/4043450/products-reaching-end-of-support-for-2018)なりました。 これは、Skype ミーティング システム V1 ソフトウェアがもはや製品の更新プログラムや修正を取得しなくなることを意味します。 Skype ミーティング システム V1 ソフトウェアを使用している Lync Room System デバイスをお持ちのお客様には、デバイスを Microsoft Teams ミーティングにアップグレードすることをお勧めします。

Microsoft Teams ルームソフトウェアは、Skype for Business Server やオンラインサービスに加えて、microsoft teams でサポートされているすべてのデバイスで会議や通話を行うことができます。

既存のデバイスは、Skype Room System v1 ソフトウェアのサポート終了後も引き続き機能する**可能性があり**ます。 ただし、このソフトウェアが、Microsoft が修正プログラムをリリースする必要があるソフトウェアバグを発見した場合は、サポートされません。 SRS v1 は、今後 Microsoft によって廃止される TLS 1.0/1.1 を使用しています。 [TLS 1.0/1.1 の廃止を準備](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Preparing-for-TLS-1-0-1-1-Deprecation-O365-Skype-for-Business/bc-p/223608)する方法については、こちらを参照してください。 

## <a name="which-devices-are-affected"></a>影響を受けるデバイス

この変更の影響を受けるデバイスの一覧を次に示します。

- Crestron RL
- [Crestron RL2](https://www.crestron.com/Products/Featured-Solutions/Crestron-RL-2)
- [スマートルームシステム](https://support.smarttech.com/en/hardware/room-systems-skype)
- [Polycom CX8000](https://www.polycom.com/products-services/products-for-microsoft/skype-for-business/cx8000.html)

## <a name="upgrade-options"></a>アップグレードオプション

Lync Room Systems を次世代の Microsoft Teams ルームにアップグレードするには、複数のオプションがあります。

### <a name="crestron-hardware-trade-in-program"></a>ハードウェアのトレードインプログラムについて

Crestron は、ユーザーが Lync Room System のすべてのユーザー (たとえば、スマートまたは Polycom LRS) で、 [CRESTRON SR システム](https://www.crestron.com/products/featured-solutions/crestron-sr)または同等のものにアップグレードします。 このプログラムの詳細を[ご覧ください](https://support.crestron.com/app/answers/answer_view/a_id/1000220)。 <!-- For details, -->[メール](mailto:lrsupgrade@crestron.com)Crestron LRS サポート。  

### <a name="crestron-rl2-upgrade-to-microsoft-teams-rooms"></a>RL2 を Microsoft Teams ルームにアップグレードする

既存の Crestron RL2 (Crestron RL200 とも呼ばれます) ユーザーは、アップグレードキットを取得して、現在の RL2 を RL3 にアップグレードし、デバイスごとに最小のコストを使用することができます。 このプログラムの詳細[はこちら](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-RL-2/CCS-UC-250-KIT)をご覧ください。

### <a name="smart-room-systems-upgrade"></a>スマートルームシステムのアップグレード

スマート LRS をお使いのお客様の場合は、「Crestron hardware トレードインプログラム」を参照してください。また、Microsoft Teams ルームにアップグレードするための解決策を提供することもできます。 このアップグレードは、「製品サポート」の下で SMART Technologies Inc. によって提供されます。 詳細[はこちら](https://support.smarttech.com/docs/hardware/room-systems-skype/srs-skype-v2/en/about/default.cshtml)をご覧ください。


## <a name="what-should-you-do"></a>どうすればよいですか?

TLS 1.0/1.1 が廃止されてから、上記のアップグレードオプションを使用する前に、Lync Room システムデバイスを Microsoft Teams ルームに更新することを計画しておくことをお勧めします。 また、既存のデバイスを、Microsoft Teams のルームで認定された新しいデバイスに置き換えることを検討することもできます。 詳細については、「[会議室デバイス](https://aka.ms/roomdevices)」を参照してください。また、 [Microsoft Teams の会議の要件](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/requirements)についてもご覧ください。  


> [!NOTE]
> Microsoft Teams のルームソフトウェアでは、2018年12月14日の4.0.64.0 で TLS 1.2 プロトコルがサポートされています。 オンプレミスのお客様の場合、Microsoft Teams の TLS 1.2 での通信を有効にするには、Skype for Business Server 2015 累積更新プログラム 9 (CU9) または Skype for Business Server 2019 累積更新プログラム 1 (CU1) が必要です。 クライアントの変更が転送され、下位に準拠しているため、この変更は Skype for Business Online のユーザーに影響を与えないようにする必要があります。
