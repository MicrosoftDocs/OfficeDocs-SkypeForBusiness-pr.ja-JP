---
title: Microsoft Teams での回線共有機能
ms.author: lolaj
author: lolaj
manager: serdars
ms.date: 02/19/2019
ms.reviewer: srividhc
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: 共有行の外観は、回答や、ユーザーに代わって呼び出しを処理する代理人を選択するユーザーをことができます。
ms.openlocfilehash: 0a110e18cb8a939870528d2700ec54103cf91a6e
ms.sourcegitcommit: 70d4d02a3cc894f2f197aeea459ac079cde63877
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/11/2019
ms.locfileid: "30541697"
---
# <a name="shared-line-appearance-in-microsoft-teams"></a>Microsoft Teams での回線共有機能

共有行の外観は、回答や、ユーザーに代わって呼び出しを処理する代理人を選択するユーザーをできるようにする委任の機能の一部です。 この機能は、ユーザーが定期的にユーザーの呼び出しを処理している管理アシスタントを持っている場合に便利です。 外観の回線を共有するのでは、マネージャーは、他のユーザーを承認するか、ユーザーに代わって呼び出しを受信するデリゲートと、デリゲートが作成および他のユーザーに代わって呼び出しを受信します。

> [!IMPORTANT]
> この機能は、配置モードのチームのみで利用可能なだけです。 チームの展開方法の詳細については、[マイクロソフト チームの理解と Skype ビジネスの共存と相互運用性を](teams-and-skypeforbusiness-coexistence-and-interoperability.md)参照してください。

## <a name="license-required"></a>ライセンスが必要

ユーザーは、代理人または委任を設定または、ユーザーに代わって呼び出しを受信する他のユーザーを有効にすると、エンタープライズ ボイスのユーザーである必要があります。

管理者と代理人の両方は、エンタープライズ ボイスを有効にする必要があります。 回線を共有する経験は、委任の一部であるし、追加ライセンスは必要ありません。 ライセンス ・ モデルの詳細については、 [Office 365 は、マイクロソフトのチームのライセンス](office-365-licensing.md)を参照してください。

## <a name="configuring-delegation-and-shared-line-appearance"></a>委任、および共有の線の外観を構成します。

委任と回線を共有する外観は、ユーザーによる機能: 構成するのには管理者の設定はありません。 機能を使用する方法の詳細については、[代理人に電話回線の共有](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)を参照してください。

テナント管理は、作業には、この機能の**TeamsCallingPolicy の AllowDelegation**設定を使用して委任を有効にする必要があります。

## <a name="shared-line-appearance-feature-availability"></a>行の外観の機能の可用性を共有

共有行の外観は、現在、次のアプリケーションとデバイスです。

| 機能 | チームのデスクトップ | チームの Mac アプリケーション | チームの Web アプリケーション (エッジ) |チーム モバイル iOS と Android アプリ | チームの IP 電話 |
|------------|---------------|---------------|----------------------|-----------------------------|----------------|
| 委任を設定します | 可 | 可 | あり | なし | いいえ |
| 代理人の呼び出しを受信します。 | 可 | 可 | 可 | 可 | あり |
| 代理人の電話番号を呼び出す | 可 | 可 | 可 | 可 | あり |
| 代理人のチームのユーザーを呼び出し | 可 | 可 | 可 | 可 | あり |
| 共有回線の管理ビューを参照してください。 | 可 | 可 | あり | なし | いいえ |
| マネージャーの待機活動の管理ビューを参照してください。 | 可 | 可 | あり | なし | いいえ |
| 代理人のマネージャーのビューを参照してください。 | 可 | 可 | あり | なし | いいえ |
| 管理者またはマネージャーを保持したり、再開 | 可 | 可 | あり | なし | いいえ |

## <a name="limitations"></a>制限

マネージャーは、25 の代理人まで追加でき、代理人は、最大 25 個のマネージャーを持つことができます。 テナントが作成されることができます委任関係の数に制限はありません。 
 
委任者と代理人が同じ地理的な場所にない場合は、(上の人の代理) に委任された呼び出しを別の地理的な場所から表示するのには発信者番号通知を許可するのには、PSTN のプロバイダーの役目です。 
 
## <a name="more-information"></a>詳細情報

[代理人と電話回線を共有します。](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)
