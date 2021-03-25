---
title: Microsoft Teams での回線共有機能
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 02/19/2019
ms.reviewer: srividhc
ms.topic: conceptual
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Phone System
- ms.teamsadmincenter.users.voice.calldelegation.tooltip
- seo-marvel-apr2020
description: Microsoft Teams の電話会議情報を含むメールをユーザーに送信する方法について説明します。
ms.openlocfilehash: b6a9e8dfba0db32eb4f02f1f4d4e9ea5f2c4be3e
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117045"
---
# <a name="shared-line-appearance-in-microsoft-teams"></a>Microsoft Teams での回線共有機能

共有行の外観は委任機能の一部で、ユーザーが代理人を選択して、自分の代わりに通話に応答したり処理したりすることができます。 この機能は、ユーザーが管理アシスタントを持ち、ユーザーの呼び出しを定期的に処理する場合に役立ちます。 共有された回線の外観の場合、マネージャーは代理人に代わって通話の送受信を許可するユーザーであり、代理人は他のユーザーの代わりに通話を行い、受信することができます。

> [!IMPORTANT]
> この機能を使用できるのは、Teams のみの展開モードだけです。 Teams 展開モードの詳細については、「Microsoft Teams と Skype for Business の共存と相互運用性について[」を参照してください](teams-and-skypeforbusiness-coexistence-and-interoperability.md)。

## <a name="license-required"></a>ライセンスが必要

ユーザーが代理または委任を設定し、他のユーザーが自分の代わりに通話を発信または受信するには、PSTN 接続を持つ電話システム (通話プラン ライセンスまたは直接ルーティング OnlineVoiceRoutingPolicy) が必要です。

マネージャーと代理人の両方が PSTN 接続の電話システム (通話プラン ライセンスまたは直接ルーティング OnlineVoiceRoutingPolicy) を持っている必要があります。 共有回線エクスペリエンスは委任の一部であり、電話システムに含まれます。 ライセンス モデルの詳細については、Microsoft Teams サービスの説明 [を参照してください](/office365/servicedescriptions/teams-service-description)。

## <a name="configuring-delegation-and-shared-line-appearance"></a>委任と共有行の外観を構成する

委任と共有の行の外観は、ユーザー駆動型の機能です。構成する管理者設定はありません。 この機能の使い方の詳細については、「代理人と電話回線を共有する」 [を参照してください。](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)

この機能を動作するには、テナント管理者は **TeamsCallingPolicy AllowDelegation** 設定または Teams 管理ポータルを介して委任を有効にできます。 

テナント管理者は、Teams 管理センターでユーザーの委任リレーションシップを構成できます。 さらに、エンド ユーザーは Teams で委任関係を直接構成することもできます。 テナント管理者またはユーザーが互いに構成をブロックすることはできませんが、Teams 管理センターと Teams クライアントは両方の場所でこの関係を正確に表示する必要があります。 

> [!IMPORTANT]
> テナント管理者がユーザーの委任を無効にした場合 (有効にした後)、誤った通話ルーティングを回避するには、Teams 管理センターでユーザーの委任関係をクリーンアップする必要もあります。

## <a name="shared-line-appearance-feature-availability"></a>共有線の外観機能の可用性

現在、共有線の外観は、次のアプリとデバイスでサポートされています。

| 機能 | Teams デスクトップ | Teams Mac アプリ | Teams Web アプリ (Edge) |Teams モバイル iOS/Android アプリ | Teams IP 電話 |
|------------|---------------|---------------|----------------------|-----------------------------|----------------|
| 委任を設定する | はい | はい | はい | いいえ | はい |
| 別のユーザーに代わって通話を受信する | はい | はい | はい | はい | はい |
| 別の電話番号に代わって電話番号に電話する | はい | はい | はい | はい | はい |
| 別のユーザーに代わって Teams ユーザーを呼び出す | はい | はい | はい | はい | はい |
| 共有行の管理ビューを表示する | はい | はい | はい | いいえ | いいえ |
| マネージャーの通話アクティビティの管理ビューを表示する | はい | はい | はい | いいえ | いいえ |
| 代理人のマネージャー ビューを表示する | はい | はい | はい | いいえ | いいえ |
| 管理者またはマネージャーが保留または再開できる | はい | はい | はい | いいえ | いいえ |

## <a name="limitations"></a>制限事項

マネージャーは最大 25 人の代理人を追加し、代理人には最大 25 人のマネージャーを追加できます。 テナントで作成できる委任リレーションシップの数に制限はありません。 
 
委任者と代理人が同じ地理的な場所にいない場合、委任された (代理で) 通話の別の地理的な場所から発信者番号を表示できるのは PSTN プロバイダーによって異なります。 
 
## <a name="more-information"></a>詳細情報

[代理人と電話回線を共有する](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)