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
description: 通話の共有とグループ通話の集荷を使用すると、ユーザーが利用できないときに通話をキャプチャできるよう、ユーザーは同僚と着信通話を共有できます。
ms.openlocfilehash: 98094ff0b4b5d7b037915273b2c2730d42517c22
ms.sourcegitcommit: 90615674e9703aa5ea32be64ab3638aa30e83127
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/02/2021
ms.locfileid: "52717838"
---
# <a name="call-sharing-and-group-call-pickup-in-microsoft-teams"></a>Microsoft Teams での通話の共有およびグループ通話ピックアップ

Microsoft Teams の通話共有機能とグループ通話集荷機能を使用すると、ユーザーは同僚と着信通話を共有して、ユーザーが利用できない間に発生した通話に同僚が応答できます。

グループ通話の集荷は、他の形式の通話共有 (着信の転送や同時呼び出しなど) よりも受信者に影響を及ばさないので、ユーザーは着信共有通話の通知方法を構成できます (Teams アプリの音声および視覚的な通知、ビジュアルのみ、またはバナーを使用して)、応答するかどうかを決定できます。

通話を他のユーザーと共有するために、ユーザーは通話グループを作成し、通話を共有するユーザーを追加します。 その後、同時呼び出しまたは転送設定を選択します。 詳細については[、「通話の転送と同時呼び出し」Teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)を参照してください。 モバイル デバイスは、バナーと着信音に設定されている場合にのみ通知を受け取る点に注意してください。

> [!IMPORTANT]
> ユーザー、呼び出しグループの所有者、および通話グループのメンバーは、Teamsモードである必要があります。 Teams 展開モードの詳細については、「[Microsoft Teams と Skype for Business の共存および相互運用性について理解する](teams-and-skypeforbusiness-coexistence-and-interoperability.md)」を参照してください。

## <a name="license-required"></a>必要なライセンス

通話共有とグループ通話の集荷Microsoft Teams 電話システムを設定して使用するには、ユーザーに新しいライセンスが割り当てられている必要があります。 ライセンス モデルの詳細については、ライセンス モデルに関するページを参照[電話システム。](https://docs.microsoft.com/MicrosoftTeams/here-s-what-you-get-with-phone-system)

## <a name="configure-group-call-pickup"></a>グループ通話の集荷を構成する

グループ通話の集荷を設定するには、ユーザーが最初に通話グループを構成し (これはセキュリティ グループや Microsoft 365 グループとは異なる)、通話を共有するユーザーを追加します。 次に、同時呼び出しまたは転送設定を選択します。 詳細と詳細な手順については、「通話の転送と同時呼び出し」を参照[Teams。](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)

通話グループの作成と通知の基本設定は、ユーザー駆動型の機能です。管理者は、ユーザーに対してこれらの機能を構成する必要があります。 通話グループは、セキュリティ グループまたはセキュリティ グループMicrosoft 365できません。これらのファイルは、Teams で作成する必要があります。

管理者は、ユーザーの **TeamsCallingPolicy AllowCallGroups** 設定を使用して通話グループを有効にする必要があります。 管理者は、管理者ポータルを使用してTeams有効にすることもできます。  さらに、構成されたユーザーは、クライアント経由で直接通話グループを構成することもできます。 管理者またはエンド ユーザーは互いに構成をブロックすることはできませんが、Teams ポータルと Teams クライアントは両方の場所でこの関係を正確に表示する必要があります。 

重要: 管理者がユーザーの通話グループをオフにした場合 (オンになっていて、通話グループの関係が構成された後)、管理者は、誤った通話ルーティングを回避するために、Teams 管理センターでユーザーの通話グループの関係をクリーンアップする必要があります。 

## <a name="limitations"></a>制限事項

構成された各呼び出しグループには、最大 25 人のユーザーまたは 32,768 文字を含めることができます。 

## <a name="more-information"></a>詳細情報

[通話の転送と同時呼び出し (Teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)
