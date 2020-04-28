---
title: Microsoft Teams での回線共有機能
ms.author: lolaj
author: LolaJacobsen
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
description: Microsoft Teams で電話会議情報を記載したメールをユーザーに送信する方法について説明します。
ms.openlocfilehash: 52f4257d5e5603c0f7ed812d5ab677a18ed47fb9
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2020
ms.locfileid: "43905549"
---
# <a name="shared-line-appearance-in-microsoft-teams"></a>Microsoft Teams での回線共有機能

共有された線の外観は、委任機能の一部であり、ユーザーは代理として応答したり、通話を処理したりすることができます。 この機能は、ユーザーの通話を定期的に処理する管理アシスタントがある場合に便利です。 共有線の外観のコンテキストでは、マネージャーは代理人を代理として発信または受信するために代理人を承認し、代理人が他のユーザーの代わりに通話を発信および受信することができます。

> [!IMPORTANT]
> この機能を使用できるのは、Teams のみの展開モードだけです。 Teams の展開モードの詳細については、「 [Microsoft teams と Skype For business の共存と相互運用性につい](teams-and-skypeforbusiness-coexistence-and-interoperability.md)て」を参照してください。

## <a name="license-required"></a>ライセンスが必要

代理人になるには、PSTN 接続 (通話プランライセンスまたは直接ルーティング OnlineVoiceRoutingPolicy) を持つ電話システムが必要です。または、委任を設定するか、他のユーザーに代わって通話を発信または受信することができます。

管理者と代理人は両方とも、PSTN 接続 (通話プランライセンスまたは直接ルーティング OnlineVoiceRoutingPolicy のいずれか) を持つ電話システムを使用している必要があります。 共有回線のエクスペリエンスは、委任の一部であり、電話システムにも含まれています。 ライセンスモデルの詳細については、「 [Microsoft Teams の Office 365 ライセンス](office-365-licensing.md)」を参照してください。

## <a name="configuring-delegation-and-shared-line-appearance"></a>委任および共有の線の外観を設定する

委任および共有の線の外観は、ユーザーによる機能です。構成する管理設定はありません。 この機能を使用する方法については、「[代理人と電話回線を共有](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)する」を参照してください。

この機能を使用するには、テナント管理者が**teamadministration のポリシー AllowDelegation**設定または Teams 管理ポータルを使って委任を有効にすることができます。 

テナント管理者は、Teams 管理センターでユーザーの委任関係を構成することもできます。 さらに、エンドユーザーは、チームに直接委任関係を構成することもできます。 テナント管理者またはユーザーは、構成を相互にブロックすることはできませんが、Teams 管理センターとチームクライアントは、両方の場所でこの関係を正確に表示する必要があります。 

> [!IMPORTANT]
> テナント管理者が、(有効になった後に) ユーザーの委任をオフにすると、誤った通話ルーティングが行われないように、Teams 管理センターでそのユーザーの委任関係をクリーンアップする必要があります。

## <a name="shared-line-appearance-feature-availability"></a>共有線の外観機能の可用性

共有線の外観は、現在、次のアプリとデバイスでサポートされています。

| 機能 | Teams デスクトップ | Teams Mac アプリ | Teams Web アプリ (Edge) |Teams モバイル iOS/Android アプリ | Teams IP 電話 |
|------------|---------------|---------------|----------------------|-----------------------------|----------------|
| 代理人を設定する | はい | はい | はい | いいえ | いいえ |
| 他の人の代理で通話を受信する | はい | はい | はい | はい | はい |
| 別の電話番号に代わって電話番号に通話を発信する | はい | はい | はい | はい | はい |
| 他のユーザーの代理として Teams ユーザーに電話をかける | はい | はい | はい | はい | はい |
| 共有行の管理ビューを表示する | はい | はい | はい | いいえ | いいえ |
| マネージャーの通話活動の管理ビューを表示する | はい | はい | はい | いいえ | いいえ |
| 代理人のマネージャービューを表示する | はい | はい | はい | いいえ | いいえ |
| 管理者またはマネージャーが保留または再開できる | はい | はい | はい | いいえ | いいえ |

## <a name="limitations"></a>伴う

マネージャーは最高25人まで追加できます。代理人は最大25人までのマネージャーを持つことができます。 テナントで作成できる委任関係の数に制限はありません。 
 
委任者と代理人が同じ地理的な場所にない場合は、PSTN プロバイダーが、委任されている (代理として) 呼び出しについて別の地理的な場所から表示することを許可します。 
 
## <a name="more-information"></a>詳細情報

[代理人と電話回線を共有する](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)
