---
title: Microsoft Teams での通話の共有およびグループ通話ピックアップ
ms.author: lolaj
author: LolaJacobsen
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
- ms.teamsadmincenter.users.voice.groupcallpickup.tooltip
- ms.teamsadmincenter.users.voice.callorderanddelay.tooltip
ms.custom:
- Phone System
description: 通話共有とグループ通話のピックアップユーザーが着信した通話を同僚と共有できるようにして、ユーザーが連絡不能なときに通話をキャプチャできるようにします。
ms.openlocfilehash: a39ed0a606b38a159473fbab9c35d21ae461c34b
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2020
ms.locfileid: "41684120"
---
# <a name="call-sharing-and-group-call-pickup-in-microsoft-teams"></a>Microsoft Teams での通話の共有およびグループ通話ピックアップ

Microsoft Teams の通話共有とグループ通話のピックアップ機能を使用すると、ユーザーは着信通話を同僚と共有できるため、ユーザーが連絡できない間に発生した通話に同僚が応答できます。

グループ通話のピックアップは、他の形式の通話共有 (着信の転送または同時呼び出しなど) よりも、受信者に対してはあまり影響がありません。ユーザーは、着信共有通話の通知方法 (音声と視覚的な通知を介して) を構成することができます。または、[Teams] アプリのバナーで、それに応答するかどうかを決定できます。

通話を他のユーザーと共有するには、ユーザーが通話グループを作成し、通話を共有するユーザーを追加します。 次に、同時呼び出しまたは転送設定を選択します。 詳しくは[、「Teams での着信の転送と同時](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)呼び出し」をご覧ください。

> [!IMPORTANT]
> ユーザー、通話グループの所有者、通話グループのメンバーは、Teams のみの展開モードである必要があります。 Teams の展開モードの詳細については、「 [Microsoft teams と Skype For business の共存と相互運用性につい](teams-and-skypeforbusiness-coexistence-and-interoperability.md)て」を参照してください。

## <a name="license-required"></a>ライセンスが必要

通話共有とグループ通話のピックアップをセットアップして使用するには、ユーザーはエンタープライズ Voip を有効にしている必要があります。 ライセンスモデルの詳細については、「 [Microsoft Teams の Office 365 ライセンス](office-365-licensing.md)」を参照してください。

## <a name="configure-group-call-pickup"></a>グループ通話のピックアップを構成する

グループ通話のピックアップを設定するために、ユーザーは最初に通話グループ (セキュリティグループまたは Office 365 グループとは異なります) を構成し、通話を共有するユーザーを追加します。 次に、同時呼び出しまたは [着信の転送] 設定を選択します。 詳細とステップバイステップの手順については、「 [Teams での着信の転送と同時呼び出し](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)」を参照してください。

通話グループの作成と通知の設定は、ユーザー主導の機能です。管理者は、これらの機能をユーザーに対して構成する必要はありません。 通話グループは、セキュリティグループまたは Office 365 グループから作成することはできません。チームで作成する必要があります。

管理者は、ユーザーの**Teampolicy のポリシー AllowCallGroups**の設定を使って、通話グループを有効にする必要があります。 管理者は、Teams 管理ポータルを使用してこれを有効にすることもできます。  また、構成されたユーザーは、クライアント経由で直接通話グループを構成することもできます。 管理者またはエンドユーザーが構成をブロックすることはできませんが、チーム管理ポータルとチームクライアントは、両方の場所でこのリレーションシップを正確に表示する必要があります。 

重要: 管理者がユーザーのコールグループを無効にする場合 (有効にした後、通話グループのリレーションシップが構成されている場合)、管理者は、不正な通話ルーティングを回避するために、Teams 管理センターでユーザーの通話グループのリレーションシップをクリーンアップする必要があります。 

## <a name="limitations"></a>伴う

テナントには、最大32768の通話グループを含めることができます。 各通話グループには最大25人のユーザーを指定できます。 

## <a name="more-information"></a>詳細情報

[チームでの着信の転送と同時呼び出し](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)
