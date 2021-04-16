---
title: Microsoft Teams での共有回線の外観
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
description: Microsoft Teams で音声会議情報を記載したメールをユーザーに送信する方法について説明します。
ms.openlocfilehash: b6a9e8dfba0db32eb4f02f1f4d4e9ea5f2c4be3e
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117045"
---
# <a name="shared-line-appearance-in-microsoft-teams"></a>Microsoft Teams での共有回線の外観

回線共有機能は、ユーザーが代理で通話に応答または処理する代理人を選択できる委任機能の一部です。 この機能は、ユーザーの通話を定期的に処理する管理アシスタントがいる場合に役立ちます。 共有回線の外観のコンテキストでは、マネージャーは、代理人が自分に代わって電話をかけたり受けたりすることを許可するユーザーであり、代理人は他の人に代わって電話をかけたり受けたりすることができます。

> [!IMPORTANT]
> この機能を使用できるのは、Teams のみの展開モードだけです。 Teams 展開モードの詳細については、「[Microsoft Teams と Skype for Business の共存および相互運用性について理解する](teams-and-skypeforbusiness-coexistence-and-interoperability.md)」を参照してください。

## <a name="license-required"></a>必要なライセンス

ユーザーは、委任または委任を設定し、他のユーザーが自分に代わって電話をかけたり受けたりできるようにするには、PSTN 接続 (通話プラン ライセンスまたは Direct Routing OnlineVoiceRoutingPolicy のいずれか) を備えた電話システムを持っている必要があります。

管理者と代理人の両方が、PSTN 接続 (通話プラン ライセンスまたは Direct Routing OnlineVoiceRoutingPolicy のいずれか) を備えた電話システムを持っている必要があります。 共有回線エクスペリエンスは委任の一部であり、電話システムに含まれています。 ライセンス モデルの詳細については、「[Microsoft Teams サービスの説明](/office365/servicedescriptions/teams-service-description)」を参照してください。

## <a name="configuring-delegation-and-shared-line-appearance"></a>委任と共有回線の外観の構成

委任と共有回線の外観はユーザー主導の機能です。構成する管理者設定はありません。 この機能の使用方法については、「[電話回線を代理人と共有する](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)」を参照してください。

テナント管理者は、**TeamsCallingPolicy AllowDelegation** 設定を介して、または Teams Admin Portal を介して委任を有効にして、この機能を機能させることができます。 

テナント管理者は、Teams 管理センターでユーザーの委任関係を構成することもできます。 さらに、エンド ユーザーはチームで直接委任関係を構成することもできます。 テナント管理者またはユーザーは相互に構成をブロックすることはできませんが、Teams 管理センターと Teams クライアントは両方の場所でこの関係を正確に示す必要があります。 

> [!IMPORTANT]
> テナント管理者がユーザーの委任をオフにした場合 (オンにした後)、Teams 管理センターでそのユーザーの委任関係をクリーンアップして、誤ったコールルーティングを回避する必要もあります。

## <a name="shared-line-appearance-feature-availability"></a>共有回線の外観機能の可用性

共有回線の外観は現在、次のアプリとデバイスでサポートされています。

| 機能 | Teams デスクトップ | Teams Mac アプリ | Teams Web アプリ (Edge) |Teams モバイル iOS/Android アプリ | Teams IP 電話 |
|------------|---------------|---------------|----------------------|-----------------------------|----------------|
| 委任を設定する | はい | はい | はい | いいえ | はい |
| 別の人に代わって電話を受ける | はい | はい | はい | はい | はい |
| 別の人に代わって電話番号に電話する | はい | はい | はい | はい | はい |
| 別のユーザーに代わって Teams ユーザーに電話する | はい | はい | はい | はい | はい |
| 共有回線の管理ビューを表示する | はい | はい | はい | いいえ | いいえ |
| マネージャーの通話アクティビティの管理ビューを表示する | はい | はい | はい | いいえ | いいえ |
| 委任のマネージャー ビューを参照してください | はい | はい | はい | いいえ | いいえ |
| 管理者またはマネージャーは保留または再開できます | はい | はい | はい | いいえ | いいえ |

## <a name="limitations"></a>制限事項

管理者は最大 25 人の代理人を追加でき、代理人は最大 25 人の管理者を持つことができます。 テナントで作成できる委任関係の数に制限はありません。 
 
委任者と委任者が同じ地理的場所にいない場合、委任された (代理の) 通話のために発信者 ID が異なる地理的場所から表示されるようにするのは PSTN プロバイダーの責任です。 
 
## <a name="more-information"></a>詳細情報

[電話回線を代理人と共有する](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)