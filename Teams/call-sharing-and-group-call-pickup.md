---
title: 通話の共有およびグループ通話ピックアップ
author: CarolynRowe
ms.author: crowe
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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.users.voice.groupcallpickup.tooltip
- ms.teamsadmincenter.users.voice.callorderanddelay.tooltip
- Phone System
- seo-marvel-mar2020
description: 通話共有とグループ通話ピックアップを使用すると、ユーザーは、ユーザーが利用できないときに通話をキャプチャできるように、着信通話を同僚と共有できます。
ms.openlocfilehash: 70b1be389309d52b01852e575d08093ef7095a04
ms.sourcegitcommit: 0dda332951df3b946097d90a4923eb191fd86b4c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/14/2022
ms.locfileid: "66789952"
---
# <a name="call-sharing-and-group-call-pickup-in-microsoft-teams"></a>Microsoft Teams での通話の共有およびグループ通話ピックアップ

Microsoft Teams の通話共有機能とグループ通話ピックアップ機能を使用すると、ユーザーは、ユーザーが利用できない間に発生した通話に同僚が応答できるように、着信通話を同僚と共有できます。

グループ通話のピックアップは、他の形式の通話共有 (通話転送や同時呼び出しなど) よりも受信者に対して中断が少ないため、ユーザーは着信共有通話の通知方法を構成できます (音声とビジュアルの通知、ビジュアルのみ、または Teams アプリのバナーを介して)、応答するかどうかを決定できます。

他のユーザーと通話を共有するために、ユーザーは通話グループを作成し、通話を共有するユーザーを追加します。 次に、同時リングまたは前方設定を選択します。 詳細については、「 [Teams での通話転送と同時リング](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e) 」を参照してください。 モバイル デバイスは、バナーと着信音に設定されている場合にのみ通知を受け取ります。

> [!IMPORTANT]
> ユーザー、通話グループの所有者、および通話グループのメンバーは、Teams のみ展開モードである必要があります。 Teams 展開モードの詳細については、「[Microsoft Teams について理解し、共存と相互運用性をSkype for Business](teams-and-skypeforbusiness-coexistence-and-interoperability.md)する」を参照してください。

## <a name="license-required"></a>必要なライセンス

通話共有とグループ通話ピックアップを設定して使用するには、ユーザーにMicrosoft Teams 電話システム ライセンスを割り当てる必要があります。 ライセンス モデルの詳細については、 [電話システム](/MicrosoftTeams/here-s-what-you-get-with-phone-system)に関するページを参照してください。

## <a name="configure-group-call-pickup"></a>グループ通話ピックアップを構成する

グループ通話ピックアップを設定するには、ユーザーが最初に通話グループを構成し (これはセキュリティ グループや Microsoft 365 グループと同じではありません)、通話を共有するユーザーを追加します。 次に、同時リングまたはコール フォワード設定を選択します。 詳細と詳細な手順については、「 [Teams での通話転送と同時リング](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)」を参照してください。

通話グループの作成と通知の基本設定は、ユーザー主導の機能です。管理者は、ユーザーに対してこれらの機能を構成する必要はありません。 通話グループは、セキュリティ グループまたは Microsoft 365 グループから作成することはできません。これらは Teams で作成する必要があります。

管理者は、ユーザーの **TeamsCallingPolicy AllowCallGroups** 設定を使用して通話グループを有効にする必要があります。 管理者は、Teams 管理 ポータルを使用してこれを有効にすることもできます。  さらに、構成されたユーザーは、クライアントを介して直接通話グループを構成することもできます。 管理ユーザーまたはエンド ユーザーは互いに構成をブロックできませんが、Teams 管理 ポータルと Teams クライアントは両方の場所でこの関係を正確に表示する必要があります。 

重要: 管理者がユーザーの通話グループをオフにした場合 (有効にし、通話グループのリレーションシップを構成した後)、管理者は、不適切な通話ルーティングを回避するために、Teams 管理センターのユーザーの通話グループ関係をクリーンアップする必要があります。 

## <a name="limitations"></a>制限事項

構成された各呼び出しグループには、最大 25 人のユーザーまたは 32,768 文字を指定できます。 

## <a name="more-information"></a>詳細情報

[Teams での通話転送と同時呼び出し](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)
