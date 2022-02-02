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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Phone System
- ms.teamsadmincenter.users.voice.calldelegation.tooltip
- seo-marvel-apr2020
description: Microsoft Teams で音声会議情報を記載したメールをユーザーに送信する方法について説明します。
ms.openlocfilehash: 1ec0b74bab289eaca1b1046eccebb870e8562a95
ms.sourcegitcommit: fd4d7557997c537c094e79ada21c569acde65aa6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/02/2022
ms.locfileid: "62312270"
---
# <a name="shared-line-appearance-in-microsoft-teams"></a>Microsoft Teams での共有回線の外観

回線共有機能は、ユーザーが代理で通話に応答または処理する代理人を選択できる委任機能の一部です。 この機能は、ユーザーの通話を定期的に処理する管理アシスタントがいる場合に役立ちます。 共有回線の外観のコンテキストでは、マネージャーは、代理人が自分に代わって電話をかけたり受けたりすることを許可するユーザーであり、代理人は他の人に代わって電話をかけたり受けたりすることができます。

> [!IMPORTANT]
> この機能を使用できるのは、Teams のみの展開モードだけです。 Teams 展開モードの詳細については、「[Microsoft Teams と Skype for Business の共存および相互運用性について理解する](teams-and-skypeforbusiness-coexistence-and-interoperability.md)」を参照してください。

## <a name="license-required"></a>必要なライセンス

ユーザーが PSTN 接続を持つ 電話システム (通話プラン ライセンスまたは直接ルーティング OnlineVoiceRoutingPolicy のいずれか) を委任または委任を設定し、他のユーザーが代わりに通話を発信または受信できる必要があります。

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
| 委任を設定する | はい | Yes | はい | いいえ | Yes |
| 別の人に代わって電話を受ける | はい | Yes | Yes | Yes | Yes |
| 別の人に代わって電話番号に電話する | はい | Yes | Yes | Yes | Yes |
| 別のユーザーに代わって Teams ユーザーに電話する | はい | Yes | Yes | Yes | Yes |
| 共有行の代理人ビューを表示する | Yes | Yes | はい | いいえ | はい |
| マネージャーの通話アクティビティの代理人ビューを表示する | Yes | Yes | はい | いいえ | はい |
| 委任のマネージャー ビューを参照してください | はい | Yes | はい | いいえ | はい |
| 代理人またはマネージャーが保留または再開できる | Yes | Yes | はい | いいえ | はい |

## <a name="limitations"></a>制限事項

管理者は最大 25 人の代理人を追加でき、代理人は最大 25 人の管理者を持つことができます。 テナントで作成できる委任関係の数に制限はありません。 
 
委任者と委任者が同じ地理的場所にいない場合、委任された (代理の) 通話のために発信者 ID が異なる地理的場所から表示されるようにするのは PSTN プロバイダーの責任です。 
 
## <a name="more-information"></a>詳細情報

[電話回線を代理人と共有する](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)
