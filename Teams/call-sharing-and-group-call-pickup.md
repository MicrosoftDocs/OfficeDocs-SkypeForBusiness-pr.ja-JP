---
title: 通話の共有およびグループ通話ピックアップ
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 02/19/2019
ms.reviewer: srividhc
ms.topic: article
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
- ms.teamsadmincenter.users.voice.groupcallpickup.tooltip
- ms.teamsadmincenter.users.voice.callorderanddelay.tooltip
- Phone System
- seo-marvel-mar2020
description: 通話共有とグループ通話の受け取りを使用すると、ユーザーは着信通話を同僚と共有し、ユーザーが応答できないときに通話をキャプチャすることができます。
ms.openlocfilehash: 825e174a6b6f68adcc7b5aade212689b01309c24
ms.sourcegitcommit: 6b24c82837ca2c11f450a162ca4fab3dfa4ac8d4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "49620728"
---
# <a name="call-sharing-and-group-call-pickup-in-microsoft-teams"></a>Microsoft Teams での通話の共有およびグループ通話ピックアップ

Microsoft Teams の通話共有機能とグループ通話の受け取り機能を使用すると、ユーザーは着信通話を同僚と共有して、ユーザーが応答できない間に発生した通話に同僚が応答することができます。

グループ通話の受け取りは、他の形式の通話共有 (着信の転送や同時呼び出しなど) よりも受信者の混乱を減らします。これは、ユーザーが着信共有通話の通知方法 (音声と視覚的な通知、視覚的な通知、Teams アプリの視覚的な通知、バナー) を構成し、応答するかどうかを決定することができるためです。

他のユーザーと通話を共有するために、ユーザーは通話グループを作成し、通話を共有するユーザーを追加します。 次に、同時呼び出しまたは転送設定を選択します。 詳細 [については、「Teams での通話の転送と同時呼](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e) び出し」を参照してください。 モバイル デバイスには、バナーと着信音が設定されている場合にのみ通知されます。

> [!IMPORTANT]
> ユーザー、通話グループの所有者、および通話グループのメンバーは、Teams のみ展開モードである必要があります。 Teams 展開モードの詳細については、「Microsoft Teams と Skype for Business の共存と相互運用性について[」を参照してください](teams-and-skypeforbusiness-coexistence-and-interoperability.md)。

## <a name="license-required"></a>ライセンスが必要

通話共有とグループエンタープライズ VoIPを設定して使用するには、ユーザーが有効になっている必要があります。 ライセンス モデルの詳細については、Microsoft Teams サービスの [説明を参照してください](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description)。

## <a name="configure-group-call-pickup"></a>グループ通話の受け取りを構成する

グループ通話の受け取りを設定するには、ユーザーが最初に通話グループを構成し (これはセキュリティ グループや Microsoft 365 グループとは異なる)、通話を共有するユーザーを追加します。 次に、同時呼び出しまたは呼び出し転送の設定を選択します。 詳細と詳しい手順については、「Teams での通話の転送と同時呼び出し [」を参照してください](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)。

通話グループの作成と通知の基本設定は、ユーザー駆動型の機能です。管理者は、ユーザーに対してこれらの機能を構成する必要があります。 通話グループは、セキュリティ グループまたは Microsoft 365 グループから作成することはできません。Teams で作成する必要があります。

管理者は、ユーザーの **TeamsCallingPolicy AllowCallGroups** 設定を使用して通話グループを有効にする必要があります。 管理者は、Teams 管理ポータルからこれを有効にすることもできます。  さらに、構成済みのユーザーは、クライアント経由で通話グループを直接構成することもできます。 管理者またはエンド ユーザーは、互いに構成をブロックすることはできませんが、Teams 管理ポータルと Teams クライアントは両方の場所でこの関係を正確に表示する必要があります。 

重要: 管理者がユーザーの通話グループをオフにすると (有効になっていて、通話グループの関係が構成された後)、管理者は、不適切な通話ルーティングを回避するために、Teams 管理センターでユーザーの通話グループの関係をクリーンアップする必要があります。 

## <a name="limitations"></a>制限事項

テナントには、最大 32,768 の通話グループを含めできます。 各通話グループには最大 25 人のユーザーを含めできます。 

## <a name="more-information"></a>詳細情報

[Teams での通話の転送と同時呼び出し](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)
