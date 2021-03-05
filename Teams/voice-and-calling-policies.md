---
title: Teams で音声と通話のポリシーを管理する
author: karlistites
ms.author: kastites
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: ''
search.appverid: ''
description: Teams の音声および通話ポリシーについて説明します。
audience: admin
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9056c9b81fcda9c0e7408c63b4af00c1aabbffd0
ms.sourcegitcommit: d62e6cefceebe481eb207c59872f1aa67f0fc528
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2021
ms.locfileid: "50460587"
---
# <a name="manage-voice-and-calling-policies-in-microsoft-teams"></a>Microsoft Teams で音声と通話のポリシーを管理する

音声と通話のポリシーは、Microsoft Teams での音声と通話を制御するために使用されます。

## <a name="emergency-calling-policies"></a>緊急通話ポリシー

緊急通話 [ポリシーを使用して](manage-emergency-calling-policies.md) 、組織内のユーザーが緊急通話を行った場合の対応を構成します。 これらのポリシーは、Teams 管理センターで管理するか、組織のWindows PowerShell。

![緊急通話ポリシーのスクリーンショット。](media/emergency-calling-policy2.png)

## <a name="emergency-call-routing-policies"></a>緊急通話ルーティング ポリシー

組織が電話システムダイレクトルーティングを展開している場合は、緊急[](manage-emergency-call-routing-policies.md)通話ルーティング ポリシーを使用して、緊急通話のルーティング先、拡張緊急サービスが有効かどうか、緊急サービスに使用する番号を決定できます。 これらのポリシーは、PowerShell または Microsoft Teams 管理センターを使用して管理されます。

![緊急通話ルーティング ポリシーのスクリーンショット。](media/emergency-call-routing-policy.png)

## <a name="caller-id-policies"></a>発信者番号ポリシー

[発信者番号ポリシーは、](caller-id-policies.md) 発信者番号を変更またはブロックするために使用されます。

![発信者番号ポリシーのスクリーンショット。](media/caller-id-policy.png)

## <a name="voice-routing-policies"></a>音声ルーティング ポリシー

音声 [ルーティング ポリシーは、](manage-voice-routing-policies.md) 公衆交換電話網 (PSTN) 利用状況レコードのコンテナーです。 組織が電話システムダイレクト ルーティングを展開している場合は、 **これらのポリシーを使用できます**。 音声ルーティング ポリシーは、PowerShell または Teams 管理センターで管理できます。

![音声ルーティング ポリシーのスクリーンショット。](media/voice-routing-policy.png)

## <a name="calling-policies"></a>通話ポリシー

[通話ポリシーは](teams-calling-policy.md) 、ユーザーがプライベート通話を行うかどうか、通話グループに通話を送信できるかどうか、通話をボイスメールにルーティングできるかどうかなど、ユーザーが使用できる通話と着信の転送機能を制御します。

![通話ポリシーのスクリーンショット。](media/calling-policy.png)

## <a name="call-park-and-retrieve-policies"></a>コール パークと取得ポリシー

[コール パークと取得により](call-park-and-retrieve.md) 、ユーザーは他のユーザーを保留にし、同じユーザーまたは他のユーザーが通話を継続できます。

![コール パークと取得ポリシーのスクリーンショット。](media/call-park-policy.png)

## <a name="create-and-manage-dial-plans"></a>ダイヤル プランを作成および管理する

[ダイヤル プランは、](create-and-manage-dial-plans.md) 通話の承認とルーティングのためにダイヤルされた電話番号を翻訳します。 ダイヤル プランは、PowerShell または Microsoft Teams 管理センターで作成および管理できます。

![ダイヤル プランのスクリーンショット。](media/dial-plans.png)

## <a name="related-topics"></a>関連トピック

* [Microsoft Teams で緊急通話ポリシーを管理する](manage-emergency-calling-policies.md)
* [緊急通話のルーティング ポリシーを管理する](manage-emergency-call-routing-policies.md)
* [Microsoft Teams で発信者番号ポリシーを管理する](caller-id-policies.md)
* [音声ルーティング ポリシーを管理する](manage-voice-routing-policies.md)
* [Microsoft Teams の発信通話制限ポリシー](teams-calling-policy.md)
* [Microsoft Teams でのコール パークおよび保留解除](call-park-and-retrieve.md)
* [ダイヤル プランを作成および管理する](create-and-manage-dial-plans.md)
* [ポリシーを使用して Teams を管理する](manage-teams-with-policies.md)
