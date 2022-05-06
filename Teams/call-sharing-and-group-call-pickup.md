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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.users.voice.groupcallpickup.tooltip
- ms.teamsadmincenter.users.voice.callorderanddelay.tooltip
- Phone System
- seo-marvel-mar2020
description: 通話共有とグループ通話ピックアップを使用すると、ユーザーは、ユーザーが利用できないときに通話をキャプチャできるように、着信通話を同僚と共有できます。
ms.openlocfilehash: 7f9e24114d47ff331ad36a653a2bbe0f31fcad08
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/30/2021
ms.locfileid: "60014131"
---
# <a name="call-sharing-and-group-call-pickup-in-microsoft-teams"></a>Microsoft Teams での通話の共有およびグループ通話ピックアップ

Microsoft Teamsの通話共有機能とグループ通話ピックアップ機能を使用すると、ユーザーは自分の着信通話を同僚と共有し、ユーザーが利用できない間に発生した通話に同僚が応答できるようにします。

グループ通話ピックアップは、他の形式の通話共有 (通話転送や同時呼び出しなど) よりも受信者に対する中断が少なく、ユーザーは着信共有通話の通知方法 (音声とビジュアルの通知、ビジュアルのみ、またはTeams アプリ内のバナーを介して) を構成でき、応答するかどうかを決定できるためです。

他のユーザーと通話を共有するために、ユーザーは通話グループを作成し、通話を共有するユーザーを追加します。 次に、同時リングまたは前方設定を選択します。 詳細については、「[Teamsの通話転送と同時リング](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)」を参照してください。 モバイル デバイスは、バナーと着信音に設定されている場合にのみ通知を受け取ります。

> [!IMPORTANT]
> ユーザー、通話グループの所有者、および通話グループのメンバーは、Teamsのみ展開モードである必要があります。 Teams展開モードの詳細については、「[Microsoft TeamsとSkype for Business共存と相互運用性について理解](teams-and-skypeforbusiness-coexistence-and-interoperability.md)する」を参照してください。

## <a name="license-required"></a>必要なライセンス

通話共有とグループ通話ピックアップを設定して使用するには、ユーザーにMicrosoft Teams 電話システム ライセンスを割り当てる必要があります。 ライセンス モデルの詳細については、電話システムに関[するページを](/MicrosoftTeams/here-s-what-you-get-with-phone-system)参照してください。

## <a name="configure-group-call-pickup"></a>グループ通話ピックアップを構成する

グループ通話ピックアップを設定するには、ユーザーが最初に通話グループを構成し (これはセキュリティ グループやMicrosoft 365 グループと同じではありません)、次に通話を共有するユーザーを追加します。 次に、同時リングまたはコール フォワード設定を選択します。 詳細と詳細な手順については、「[Teamsでの通話転送と同時リング](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)」を参照してください。

通話グループの作成と通知の基本設定は、ユーザー主導の機能です。管理者は、ユーザーに対してこれらの機能を構成する必要はありません。 呼び出しグループは、セキュリティ グループまたはMicrosoft 365 グループから作成することはできません。Teamsで作成する必要があります。

管理者は、ユーザーの **TeamsCallingPolicy AllowCallGroups** 設定を使用して通話グループを有効にする必要があります。 管理者は、Teams管理ポータルを使用してこれを有効にすることもできます。  さらに、構成されたユーザーは、クライアントを介して直接通話グループを構成することもできます。 管理者またはエンド ユーザーは互いに構成をブロックできませんが、管理者ポータルとTeams クライアントTeams両方の場所でこのリレーションシップを正確に表示する必要があります。 

重要: 管理者がユーザーの通話グループをオフにした場合 (有効にし、通話グループのリレーションシップを構成した後)、管理者は、不適切な通話ルーティングを回避するために、Teams管理センターのユーザーの通話グループ関係をクリーンアップする必要があります。 

## <a name="limitations"></a>制限事項

構成された各呼び出しグループには、最大 25 人のユーザーまたは 32,768 文字を指定できます。 

## <a name="more-information"></a>詳細情報

[Teamsでの通話転送と同時リング](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)
