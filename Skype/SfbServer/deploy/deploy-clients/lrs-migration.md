---
title: Lync ルーム システム デバイスを Skype ルーム システム バージョン 2 に移行します。
ms.author: jambirk
author: jambirk
ms.reviewer: sohailta
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ''
description: Skype ルーム システム v2 のソフトウェアを使用して Lync ルーム システム デバイスを移行する方法の詳細については、このトピックを参照してください。
ms.openlocfilehash: b2d748a37e7e060e19d0708b6979f9254af13682
ms.sourcegitcommit: 454ded73af5854d7b81a3b996702a6464b3fc313
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/09/2019
ms.locfileid: "27772904"
---
# <a name="migrate-lync-room-system-lrs-devices-to-skype-room-system-v2"></a>Lync ルーム システム (LRS) デバイスを Skype ルーム システム v2 に移行します。 
Skype ルーム システム バージョン 1 (SRS v1) ソフトウェアとデバイスを Lync ルーム システム (LRS) は[、2018 年 10 月 9 日のサポート終了](https://support.microsoft.com/en-us/help/4043450/products-reaching-end-of-support-for-2018)に達しました。 つまり Skype ルーム システム v1 のソフトウェアは不要になったすべての製品の更新プログラムや修正もはや。 Skype ルーム システム v1 のソフトウェアを使用して Lync ルームのシステム デバイスを持つお客様は Skype ルーム システム バージョン 2 (SRS v2) にそのデバイスをアップグレードするのにはお勧めします。

Skype ルーム システムのバージョン 2 (SRS v2) ソフトウェアでは、会議およびすべての SRS v2 はサポートされているデバイスでの通話のビジネス サーバーとオンラインのサービスの Skype の他のマイクロソフトのチームで動作します。

Skype ルーム システム v1 のソフトウェアのサポートは動作を継続、既存のデバイス**があります**。 ただし、このソフトウェアには、マイクロソフトが修正プログラムをリリースする必要のあるソフトウェアのバグが発生する場合にサポートされません。 SRS v1 は、TLS 1.0 を使用して/1.1 を将来的に Microsoft によって推奨されません。 [TLS 1.0 または 1.1 の廃止の準備](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Preparing-for-TLS-1-0-1-1-Deprecation-O365-Skype-for-Business/bc-p/223608)に関する詳細については。 Skype ルーム システムの V2 では、TLS 1.2 のサポートを追加して、2018 年 10 月 31日過去の作業を続行します。 前提のお客様にビジネス用の Skype には、Skype ルーム システム V2 annouces は TLS 1.0 または 1.1 の廃止に関する一般的なガイドラインとは無関係に TLS 1.2 のサポートになるまで、TLS 1.0 または 1.1 が無効にしないでください。

## <a name="which-devices-are-affected"></a>どのデバイスが影響を受けるでしょうか。
この変更によって影響を受けるデバイスの一覧を以下に示します。
- [スマート ルーム システム](https://support.smarttech.com/en/hardware/room-systems-skype)
- [Crestron RL2](https://www.crestron.com/en-US/Products/Featured-Solutions/Crestron-RL-2)
- [ポリコム CX8000](http://www.polycom.com/products-services/products-for-microsoft/skype-for-business/cx8000.html)
- Crestron RL

## <a name="upgrade-options"></a>アップグレード オプション
Skype ルーム システム (SRS v2) の次の世代に Lync の部屋のシステムをアップグレードするための複数のオプションがあります。

### <a name="crestron-hardware-trade-in-program"></a>Crestron ハードウェアの下取りプログラム
Crestron に、すべての非 Crestron Lync ルーム システムのお客様の[Crestron SR システム](https://www.crestron.com/en-us/products/featured-solutions/crestron-sr)またはそれと同等にアップグレードを提供します。 このプログラムの詳細を参照してください[ここで](https://support.crestron.com/app/answers/answer_view/a_id/1000220)または<!-- For details, -->[電子メール](mailto:lrsupgrade@crestron.com)Crestron LRS のサポート。  


### <a name="crestron-rl2-upgrade-to-srs-v2"></a>SRS V2 にアップグレードを Crestron RL2
Crestron RL2 が (Crestron RL200 とも呼ばれます) の既存のお客様が RL3 を使用する現在の RL2 をアップグレードするのには、アップ グレード キットを入手できます、デバイス 1 台あたりコストを最小限に抑える。 このプログラムの詳細を参照してください[ここで](https://crestron.com/en-US/Products/Workspace-Solutions/Unified-Communications/Crestron-RL-2/CCS-UC-250-KIT)。 


### <a name="smart-room-systems-upgrade"></a>スマート ルーム システムをアップグレードします。 
Crestron ハードウェアの下取りプログラムとは別のスマート LRS お客様は、マイクロソフトとスマートも担当している Skype ルーム システム v2 にアップグレードするソリューションを提供します。 スマート テクノロジー社でこのアップグレードを提供します。この[ここで](https://support.smarttech.com/docs/hardware/room-systems-skype/srs-skype-v2/en/about/default.cshtml)の詳細を参照してください。

<!--  
For later 
### Do-It-Yourself
A Do-It-Yourself option is also available for customers with upgrade to Windows 10 and Skype Room Systems v2 software. Windows 10 Enterprise Licenses are available through [approved resellers](https://www.microsoft.com/en-us/Licensing/how-to-buy/how-to-buy.aspx) and Skype Room System V2 software will be available through this guide. 
 
  
To use this option however, customers must additionaly buy a [Logitech Screen Share](https://www.logitech.com/en-us/product/screen-share) adapter. Microsoft will provide instructions on how to use this adapter with Skype Room System v2 software. 


Look for upgrade instructions on this page shortly. 
  
### Summary of upgrade options
This table lists summary of all available options for existing LRS devices:
<!--  For later 
| Upgrade Option | SMART Room Systems | Crestron RL2 | Polycom CX8000 | Crestron RL |
|:--- |:--- |:--- |:--- |:--- |
|**Crestron hardware </br>Trade-in program**|Available|Available|Available|Available|
|**Crestron RL3**|Not Available|Available|Not Available|Not Available|
|**Do-It-Yourself**|Available|Not Available|Not Available|Not Available|
| | | | | |
-->

## <a name="what-should-you-do"></a>何ですか。
上記のアップグレード オプションを使用して TLS 1.0 または 1.1 廃止する前に Skype ルーム システム v2 に Lync ルーム システム デバイスを更新することをお勧めします。 また、SRS v2 の認定、新しいデバイスと既存のデバイスを置き換えることを検討可能性があります。 詳細については、[ルームのデバイス](https://aka.ms/roomdevices)を参照してくださいし、 [Skype ルーム システム v2 の要件](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/requirements)を参照してください。  

> [!NOTE]
> タッチとホワイト ボードの機能が Skype ルーム システム v2 でまだサポートされていません。 タッチとホワイト ボードのサポートでは、Skype ルーム システム v2 のバックログし、H1 CY2019 に追加される予定です。

> [!NOTE]
> ルーム システム V2 の Skype ソフトウェアは、現在 TLS 1.2 プロトコルをサポートしていません。 TLS 1.2 のサポートは、作業対象と、TLS 1.0 または 1.1 を廃止する前に完了します。 SRS v2 に顧客 upgradging SRS v2 アプリケーションの最新バージョンを実行しているルームのデバイスに TLS 1.0 または 1.1 の廃止の影響を与える表示されません。 前提のお客様にビジネス用の Skype には、Skype ルーム システム V2 annouces TLS 1.2 をサポートするまで、TLS 1.0 または 1.1 が無効にしないでください。 
